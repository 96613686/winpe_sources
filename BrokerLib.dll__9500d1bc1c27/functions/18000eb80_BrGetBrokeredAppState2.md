# BrGetBrokeredAppState2

- ea: `0x18000eb80`
- end: `0x18000ed11`
- name: `BrGetBrokeredAppState2`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180005a00`
- `0x180009e94`
- `0x18000eb80`
- `0x18000ed18`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrGetBrokeredAppState2(const void *a1, __int64 a2, int a3, int a4, bool *a5)
{
  unsigned int v8; // ebx
  __int64 *Event; // rcx
  __int64 v10; // r15
  __int64 v11; // rax
  bool v12; // di
  __int64 AppState; // rax
  Broker::Win32Error *v15; // [rsp+20h] [rbp-58h] BYREF
  __int128 v16; // [rsp+28h] [rbp-50h]
  std::_Ref_count_base *v17[2]; // [rsp+40h] [rbp-38h]
  std::_Ref_count_base *v18[2]; // [rsp+50h] [rbp-28h] BYREF

  *(_OWORD *)v17 = 0;
  v16 = 0;
  if ( a1 && (v8 = 0, a2) )
  {
    try
    {
      Broker::BrokerBase::GetInstance(v18, a1);
      *(_OWORD *)v17 = *(_OWORD *)v18;
      Event = (__int64 *)Broker::BrokerBase::FindEvent(v18[0], v18, a2);
      v10 = *Event;
      v11 = Event[1];
      *Event = 0;
      Event[1] = 0;
      *((_QWORD *)&v16 + 1) = v11;
      if ( v18[1] )
        std::_Ref_count_base::_Decref(v18[1]);
      if ( a3 )
      {
        v8 = 87;
      }
      else
      {
        v12 = 1;
        if ( a4 != 1 )
        {
          v8 = 87;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, 87);
        }
        AppState = Broker::BrokerEvent::GetAppState(v10, v18);
        if ( *(_QWORD *)(*(_QWORD *)AppState + 72LL) )
          v12 = *(_DWORD *)(*(_QWORD *)AppState + 140LL) > 0;
        if ( v18[1] )
          std::_Ref_count_base::_Decref(v18[1]);
        *a5 = v12;
      }
    }
    catch ( Broker::NotFound )
    {
      v8 = 1168;
      goto LABEL_19;
    }
    catch ( Broker::Win32Error *v15 )
    {
      v8 = *((_DWORD *)v15 + 8);
    }
    catch ( ... )
    {
      v8 = 1287;
      goto LABEL_19;
    }
  }
  else
  {
    v8 = 87;
  }
  if ( v8 )
  {
LABEL_19:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v8);
  }
  if ( *((_QWORD *)&v16 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v16 + 1));
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
  return v8;
}

```

## disassembly

```asm
0x18000eb80  mov     rax, rsp
0x18000eb83  mov     [rax+10h], rbx
0x18000eb87  mov     [rax+18h], rsi
0x18000eb8b  push    rdi
0x18000eb8c  push    r14
0x18000eb8e  push    r15
0x18000eb90  sub     rsp, 60h
0x18000eb94  mov     r14d, r9d
0x18000eb97  mov     esi, r8d
0x18000eb9a  mov     rdi, rdx
0x18000eb9d  xorps   xmm0, xmm0
0x18000eba0  movdqa  xmmword ptr [rax-38h], xmm0
0x18000eba5  movdqu  xmmword ptr [rax-50h], xmm0
0x18000ebaa  test    rcx, rcx
0x18000ebad  jz      loc_18000ECA2
0x18000ebb3  xor     ebx, ebx
0x18000ebb5  test    rdx, rdx
0x18000ebb8  jz      loc_18000ECA2
0x18000ebbe  mov     rdx, rcx
0x18000ebc1  lea     rcx, [rax-28h]
0x18000ebc5  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18000ebca  movaps  xmm0, xmmword ptr [rsp+78h+var_28]
0x18000ebcf  movdqa  xmmword ptr [rsp+78h+var_38], xmm0
0x18000ebd5  mov     r8, rdi
0x18000ebd8  lea     rdx, [rsp+78h+var_28]
0x18000ebdd  movq    rcx, xmm0
0x18000ebe2  call    ?FindEvent@BrokerBase@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@PEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::FindEvent(_BROKERED_EVENT *)
0x18000ebe7  mov     rcx, rax
0x18000ebea  mov     r15, [rax]
0x18000ebed  mov     rax, [rax+8]
0x18000ebf1  mov     [rcx], rbx
0x18000ebf4  mov     [rcx+8], rbx
0x18000ebf8  mov     [rsp+78h+var_48], rax
0x18000ebfd  mov     rcx, [rsp+78h+var_28+8]; this
0x18000ec02  test    rcx, rcx
0x18000ec05  jz      short loc_18000EC0C
0x18000ec07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ec0c  test    esi, esi
0x18000ec0e  jz      short loc_18000EC17
0x18000ec10  mov     ebx, 57h ; 'W'
0x18000ec15  jmp     short loc_18000EC8C
0x18000ec17  mov     edi, 1
0x18000ec1c  cmp     r14d, edi
0x18000ec1f  jz      short loc_18000EC50
0x18000ec21  lea     ebx, [rdi+56h]
0x18000ec24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec2b  test    dword ptr [rcx+1Ch], 800h
0x18000ec32  jz      short loc_18000EC50
0x18000ec34  cmp     byte ptr [rcx+19h], 2
0x18000ec38  jb      short loc_18000EC50
0x18000ec3a  lea     edx, [rdi+1Ah]
0x18000ec3d  mov     r9d, ebx
0x18000ec40  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000ec47  mov     rcx, [rcx+10h]
0x18000ec4b  call    WPP_SF_d
0x18000ec50  lea     rdx, [rsp+78h+var_28]
0x18000ec55  mov     rcx, r15
0x18000ec58  call    ?GetAppState@BrokerEvent@Broker@@QEBA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@XZ; Broker::BrokerEvent::GetAppState(void)
0x18000ec5d  mov     rcx, [rax]
0x18000ec60  cmp     qword ptr [rcx+48h], 0
0x18000ec65  jz      short loc_18000EC72
0x18000ec67  cmp     dword ptr [rcx+8Ch], 0
0x18000ec6e  setnle  dil
0x18000ec72  mov     rcx, [rsp+78h+var_28+8]; this
0x18000ec77  test    rcx, rcx
0x18000ec7a  jz      short loc_18000EC81
0x18000ec7c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ec81  mov     rax, [rsp+78h+arg_20]
0x18000ec89  mov     [rax], dil
0x18000ec8c  jmp     short loc_18000ECA7
0x18000ec8e  mov     ebx, [rsp+78h+arg_0]
0x18000ec95  jmp     short loc_18000ECAB
0x18000ec97  mov     ebx, [rsp+78h+arg_0]
0x18000ec9e  jmp     short loc_18000ECA7
0x18000eca0  jmp     short loc_18000EC8E
0x18000eca2  mov     ebx, 57h ; 'W'
0x18000eca7  test    ebx, ebx
0x18000eca9  jz      short loc_18000ECDA
0x18000ecab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecb2  test    dword ptr [rcx+1Ch], 800h
0x18000ecb9  jz      short loc_18000ECDA
0x18000ecbb  cmp     byte ptr [rcx+19h], 2
0x18000ecbf  jb      short loc_18000ECDA
0x18000ecc1  mov     edx, 1Ch
0x18000ecc6  mov     r9d, ebx
0x18000ecc9  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000ecd0  mov     rcx, [rcx+10h]
0x18000ecd4  call    WPP_SF_d
0x18000ecd9  nop
0x18000ecda  mov     rcx, [rsp+78h+var_48]; this
0x18000ecdf  test    rcx, rcx
0x18000ece2  jz      short loc_18000ECEA
0x18000ece4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ece9  nop
0x18000ecea  mov     rcx, [rsp+78h+var_38+8]; this
0x18000ecef  test    rcx, rcx
0x18000ecf2  jz      short loc_18000ECF9
0x18000ecf4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ecf9  mov     eax, ebx
0x18000ecfb  lea     r11, [rsp+78h+var_18]
0x18000ed00  mov     rbx, [r11+28h]
0x18000ed04  mov     rsi, [r11+30h]
0x18000ed08  mov     rsp, r11
0x18000ed0b  pop     r15
0x18000ed0d  pop     r14
0x18000ed0f  pop     rdi
0x18000ed10  retn
```
