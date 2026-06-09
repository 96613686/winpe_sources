# BrpDeleteBrokeredEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *)

- ea: `0x18000b2b0`
- end: `0x18000b39d`
- name: `?BrpDeleteBrokeredEvent@@YAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b290`
- `0x180010080`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x18000b2b0`
- `0x18000b3a4`
- `0x18000b3cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrpDeleteBrokeredEvent(unsigned int a1, const void *a2, __int64 a3)
{
  unsigned int v6; // ebx
  __int64 result; // rax
  Broker::Win32Error *v8; // [rsp+20h] [rbp-48h] BYREF
  struct _RTL_SRWLOCK *v9; // [rsp+28h] [rbp-40h] BYREF
  std::_Ref_count_base *v10; // [rsp+30h] [rbp-38h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids);
  if ( !a2 || !a3 )
  {
    v6 = 87;
    goto LABEL_13;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v9, a2);
    Broker::BrokerBase::DeleteBrokeredEventEA(v9, a1, a3);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    v6 = 14;
    goto LABEL_13;
  }
  catch ( Broker::InvalidParameter )
  {
    v6 = 87;
    goto LABEL_13;
  }
  catch ( Broker::NotFound )
  {
    v6 = 1168;
    goto LABEL_13;
  }
  catch ( Broker::Win32Error *v8 )
  {
    v6 = *((_DWORD *)v8 + 8);
    if ( !v6 )
      return v6;
LABEL_13:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids, v6);
    return v6;
  }
  catch ( ... )
  {
    v6 = 1287;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x18000b2b0  push    rbx
0x18000b2b2  push    rsi
0x18000b2b3  push    rdi
0x18000b2b4  push    r14
0x18000b2b6  sub     rsp, 48h
0x18000b2ba  mov     rdi, r8
0x18000b2bd  mov     rbx, rdx
0x18000b2c0  mov     esi, ecx
0x18000b2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2c9  test    dword ptr [rcx+1Ch], 800h
0x18000b2d0  jz      short loc_18000B2D8
0x18000b2d2  cmp     byte ptr [rcx+19h], 5
0x18000b2d6  jnb     short loc_18000B2E7
0x18000b2d8  test    rbx, rbx
0x18000b2db  jnz     short loc_18000B2FE
0x18000b2dd  mov     ebx, 57h ; 'W'
0x18000b2e2  jmp     loc_18000B36D
0x18000b2e7  mov     edx, 0Eh
0x18000b2ec  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18000b2f3  mov     rcx, [rcx+10h]
0x18000b2f7  call    WPP_SF_
0x18000b2fc  jmp     short loc_18000B2D8
0x18000b2fe  xor     r14d, r14d
0x18000b301  test    rdi, rdi
0x18000b304  jz      short loc_18000B2DD
0x18000b306  mov     rdx, rbx
0x18000b309  lea     rcx, [rsp+68h+var_40]
0x18000b30e  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18000b313  nop
0x18000b314  mov     r8, rdi
0x18000b317  mov     edx, esi
0x18000b319  mov     rcx, [rsp+68h+var_40]
0x18000b31e  call    ?DeleteBrokeredEventEA@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::DeleteBrokeredEventEA(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *)
0x18000b323  nop
0x18000b324  mov     rcx, [rsp+68h+var_38]; this
0x18000b329  test    rcx, rcx
0x18000b32c  jz      short loc_18000B334
0x18000b32e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b333  nop
0x18000b334  mov     eax, r14d
0x18000b337  add     rsp, 48h
0x18000b33b  pop     r14
0x18000b33d  pop     rdi
0x18000b33e  pop     rsi
0x18000b33f  pop     rbx
0x18000b340  retn
0x18000b341  mov     eax, ebx
0x18000b343  add     rsp, 48h
0x18000b347  pop     r14
0x18000b349  pop     rdi
0x18000b34a  pop     rsi
0x18000b34b  pop     rbx
0x18000b34c  retn
0x18000b34d  mov     ebx, [rsp+68h+arg_8]
0x18000b351  jmp     short loc_18000B36D
0x18000b353  mov     ebx, [rsp+68h+arg_8]
0x18000b357  jmp     short loc_18000B36D
0x18000b359  mov     ebx, [rsp+68h+arg_8]
0x18000b35d  jmp     short loc_18000B36D
0x18000b35f  mov     ebx, [rsp+68h+arg_8]
0x18000b363  test    ebx, ebx
0x18000b365  jz      short loc_18000B341
0x18000b367  jmp     short loc_18000B36D
0x18000b369  mov     ebx, [rsp+68h+arg_8]
0x18000b36d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b374  test    dword ptr [rcx+1Ch], 800h
0x18000b37b  jz      short loc_18000B341
0x18000b37d  cmp     byte ptr [rcx+19h], 2
0x18000b381  jb      short loc_18000B341
0x18000b383  mov     edx, 0Fh
0x18000b388  mov     r9d, ebx
0x18000b38b  lea     r8, WPP_aedb1da3e26b324cbac6301bae0d271e_Traceguids
0x18000b392  mov     rcx, [rcx+10h]
0x18000b396  call    WPP_SF_d
0x18000b39b  jmp     short loc_18000B341
```
