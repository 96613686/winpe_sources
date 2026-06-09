# BrGetBrokeredEventState

- ea: `0x18000fd10`
- end: `0x18000fddd`
- name: `BrGetBrokeredEventState`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180005a00`
- `0x180009e94`
- `0x18000fd10`
- `0x1800149f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrGetBrokeredEventState(const void *a1, unsigned __int64 a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  Broker::Win32Error *v7; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v9; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+38h] [rbp-20h] BYREF
  std::_Ref_count_base *v11; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+60h] [rbp+8h]
  int v14; // [rsp+60h] [rbp+8h]
  int v15; // [rsp+60h] [rbp+8h]

  if ( !a1 || !a2 || (v5 = 0, !a3) )
  {
    v5 = 87;
LABEL_13:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v5);
    return v5;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v10, a1);
    Broker::BrokerBase::FindEvent(v10, &v8, a2);
    *a3 = Broker::BrokerEvent::GetState(v8);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
  }
  catch ( std::bad_alloc )
  {
    v13 = 14;
    v5 = v13;
    goto LABEL_13;
  }
  catch ( Broker::InvalidParameter )
  {
    v14 = 87;
    v5 = v14;
    goto LABEL_13;
  }
  catch ( Broker::Win32Error *v7 )
  {
    v5 = *((_DWORD *)v7 + 8);
    if ( !v5 )
      return v5;
    goto LABEL_13;
  }
  catch ( ... )
  {
    v15 = 1287;
    v5 = v15;
    goto LABEL_13;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fd10  mov     [rsp+arg_8], rbx
0x18000fd15  mov     [rsp+arg_10], rsi
0x18000fd1a  push    rdi
0x18000fd1b  sub     rsp, 50h
0x18000fd1f  mov     rsi, r8
0x18000fd22  mov     rdi, rdx
0x18000fd25  test    rcx, rcx
0x18000fd28  jnz     short loc_18000FD31
0x18000fd2a  mov     ebx, 57h ; 'W'
0x18000fd2f  jmp     short loc_18000FDAD
0x18000fd31  test    rdi, rdi
0x18000fd34  jz      short loc_18000FD2A
0x18000fd36  xor     ebx, ebx
0x18000fd38  test    rsi, rsi
0x18000fd3b  jz      short loc_18000FD2A
0x18000fd3d  mov     rdx, rcx
0x18000fd40  lea     rcx, [rsp+58h+var_20]
0x18000fd45  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18000fd4a  nop
0x18000fd4b  mov     r8, rdi
0x18000fd4e  lea     rdx, [rsp+58h+var_30]
0x18000fd53  mov     rcx, [rsp+58h+var_20]
0x18000fd58  call    ?FindEvent@BrokerBase@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@PEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::FindEvent(_BROKERED_EVENT *)
0x18000fd5d  mov     rcx, [rsp+58h+var_30]
0x18000fd62  call    ?GetState@BrokerEvent@Broker@@QEBA?AW4_BROKERED_EVENT_STATE@@XZ; Broker::BrokerEvent::GetState(void)
0x18000fd67  mov     [rsi], eax
0x18000fd69  mov     rcx, [rsp+58h+var_28]; this
0x18000fd6e  test    rcx, rcx
0x18000fd71  jz      short loc_18000FD79
0x18000fd73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fd78  nop
0x18000fd79  mov     rcx, [rsp+58h+var_18]; this
0x18000fd7e  test    rcx, rcx
0x18000fd81  jz      short loc_18000FD89
0x18000fd83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fd88  nop
0x18000fd89  mov     eax, ebx
0x18000fd8b  mov     rbx, [rsp+58h+arg_8]
0x18000fd90  mov     rsi, [rsp+58h+arg_10]
0x18000fd95  add     rsp, 50h
0x18000fd99  pop     rdi
0x18000fd9a  retn
0x18000fd9b  jmp     short $+2
0x18000fd9d  mov     ebx, [rsp+58h+arg_0]
0x18000fda1  jmp     short loc_18000FDAD
0x18000fda3  jmp     short loc_18000FD9D
0x18000fda5  mov     ebx, [rsp+58h+arg_0]
0x18000fda9  test    ebx, ebx
0x18000fdab  jz      short loc_18000FD89
0x18000fdad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdb4  test    dword ptr [rcx+1Ch], 800h
0x18000fdbb  jz      short loc_18000FD89
0x18000fdbd  cmp     byte ptr [rcx+19h], 2
0x18000fdc1  jb      short loc_18000FD89
0x18000fdc3  mov     edx, 21h ; '!'
0x18000fdc8  mov     r9d, ebx
0x18000fdcb  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000fdd2  mov     rcx, [rcx+10h]
0x18000fdd6  call    WPP_SF_d
0x18000fddb  jmp     short loc_18000FD89
```
