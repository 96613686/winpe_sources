# DiagHubCommon::HubTask<long,0>::ThreadMain(void *)

- ea: `0x140008e80`
- end: `0x140008ef4`
- name: `?ThreadMain@?$HubTask@J$0A@@DiagHubCommon@@CAKPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008e80`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140008eb9`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x140008eb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::HubTask<long,0>::ThreadMain(_QWORD *lpThreadParameter)
{
  __int64 v3; // rcx
  __int64 v4; // [rsp+28h] [rbp-20h] BYREF

  if ( !lpThreadParameter )
    return 0xFFFFFFFFLL;
  try
  {
    v4 = lpThreadParameter[10];
    v3 = lpThreadParameter[9];
    if ( !v3 )
      std::_Xbad_function_call();
    *((_DWORD *)lpThreadParameter + 26) = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v3 + 16LL))(
                                            v3,
                                            (char *)lpThreadParameter + 88,
                                            &v4);
  }
  catch ( ... )
  {
    return 4294967294LL;
  }
  return 0;
}

```

## disassembly

```asm
0x140008e80  push    rbx
0x140008e82  sub     rsp, 40h
0x140008e86  mov     rax, cs:__security_cookie
0x140008e8d  xor     rax, rsp
0x140008e90  mov     [rsp+48h+var_18], rax
0x140008e95  mov     rbx, rcx
0x140008e98  test    rcx, rcx
0x140008e9b  jnz     short loc_140008EA2
0x140008e9d  or      eax, 0FFFFFFFFh
0x140008ea0  jmp     short loc_140008EE1
0x140008ea2  mov     [rsp+48h+var_28], 0
0x140008ea7  mov     rax, [rcx+50h]
0x140008eab  mov     [rsp+48h+var_20], rax
0x140008eb0  mov     rcx, [rcx+48h]
0x140008eb4  test    rcx, rcx
0x140008eb7  jnz     short loc_140008EBF
0x140008eb9  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140008ebf  lea     rdx, [rbx+58h]
0x140008ec3  mov     rax, [rcx]
0x140008ec6  lea     r8, [rsp+48h+var_20]
0x140008ecb  mov     rax, [rax+10h]
0x140008ecf  call    cs:__guard_dispatch_icall_fptr
0x140008ed5  mov     [rbx+68h], eax
0x140008ed8  xor     eax, eax
0x140008eda  jmp     short loc_140008EE1
0x140008edc  mov     eax, 0FFFFFFFEh
0x140008ee1  mov     rcx, [rsp+48h+var_18]
0x140008ee6  xor     rcx, rsp; StackCookie
0x140008ee9  call    __security_check_cookie
0x140008eee  add     rsp, 40h
0x140008ef2  pop     rbx
0x140008ef3  retn
```
