# common_exit

- ea: `0x180003a6c`
- end: `0x180003b4f`
- name: `common_exit`
- size: `227`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003c68`
- `0x180003c7c`
- `0x180003c8c`
- `0x180003c9c`
- `0x180003cec`
- `0x180003cf8`

## callees

- `0x180003840`
- `0x180003a6c`
- `0x180003b50`
- `0x180003c04`
- `0x180006a60`
- `0x180006ca4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180003a93`
- `KERNEL32!GetModuleHandleW` at `0x180003a93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall common_exit(UINT uExitCode, int a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  char *v5; // rcx
  __int64 result; // rax
  _BYTE v7[4]; // [rsp+20h] [rbp-30h] BYREF
  int v8; // [rsp+24h] [rbp-2Ch] BYREF
  int v9; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  _QWORD v11[3]; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+68h] [rbp+18h] BYREF
  int v13; // [rsp+70h] [rbp+20h] BYREF
  char v14; // [rsp+78h] [rbp+28h] BYREF

  v13 = a3;
  v12 = a2;
  v10 = -2;
  if ( !a3 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      if ( *(_WORD *)ModuleHandleW == 23117 )
      {
        v5 = (char *)ModuleHandleW + *((int *)ModuleHandleW + 15);
        if ( *(_DWORD *)v5 == 17744 && *((_WORD *)v5 + 12) == 523 && *((_DWORD *)v5 + 33) > 0xEu && *((_DWORD *)v5 + 62) )
          try_cor_exit_process(uExitCode);
      }
    }
  }
  v14 = 0;
  v11[0] = &v12;
  v11[1] = &v13;
  v11[2] = &v14;
  v8 = 2;
  v9 = 2;
  result = _crt_seh_guarded_call_void_::operator()__lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___(
             v7,
             &v9,
             v11,
             &v8);
  if ( !v13 )
  {
    result = _acrt_get_process_end_policy();
    if ( (_DWORD)result != 1 )
      result = _acrt_app_verifier_enabled();
    if ( !v13 )
      exit_or_terminate_process(uExitCode);
  }
  return result;
}

```

## disassembly

```asm
0x180003a6c  mov     [rsp-8+arg_10], r8d
0x180003a71  mov     [rsp-8+arg_8], edx
0x180003a75  push    rbp
0x180003a76  mov     rbp, rsp
0x180003a79  sub     rsp, 50h
0x180003a7d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180003a85  mov     [rsp+50h+arg_0], rbx
0x180003a8a  mov     ebx, ecx
0x180003a8c  test    r8d, r8d
0x180003a8f  jnz     short loc_180003ADB
0x180003a91  xor     ecx, ecx; lpModuleName
0x180003a93  call    cs:__imp_GetModuleHandleW
0x180003a99  test    rax, rax
0x180003a9c  jz      short loc_180003ADB
0x180003a9e  mov     ecx, 5A4Dh
0x180003aa3  cmp     [rax], cx
0x180003aa6  jnz     short loc_180003ADB
0x180003aa8  movsxd  rcx, dword ptr [rax+3Ch]
0x180003aac  add     rcx, rax
0x180003aaf  cmp     dword ptr [rcx], 4550h
0x180003ab5  jnz     short loc_180003ADB
0x180003ab7  mov     eax, 20Bh
0x180003abc  cmp     [rcx+18h], ax
0x180003ac0  jnz     short loc_180003ADB
0x180003ac2  cmp     dword ptr [rcx+84h], 0Eh
0x180003ac9  jbe     short loc_180003ADB
0x180003acb  cmp     dword ptr [rcx+0F8h], 0
0x180003ad2  jz      short loc_180003ADB
0x180003ad4  mov     ecx, ebx
0x180003ad6  call    try_cor_exit_process
0x180003adb  mov     [rbp+arg_18], 0
0x180003adf  lea     rax, [rbp+arg_8]
0x180003ae3  mov     [rbp+var_18], rax
0x180003ae7  lea     rax, [rbp+arg_10]
0x180003aeb  mov     [rbp+var_10], rax
0x180003aef  lea     rax, [rbp+arg_18]
0x180003af3  mov     [rbp+var_8], rax
0x180003af7  mov     eax, 2
0x180003afc  mov     [rbp+var_2C], eax
0x180003aff  mov     [rbp+var_28], eax
0x180003b02  lea     r9, [rbp+var_2C]
0x180003b06  lea     r8, [rbp+var_18]
0x180003b0a  lea     rdx, [rbp+var_28]
0x180003b0e  lea     rcx, [rbp+var_30]
0x180003b12  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x180003b17  nop
0x180003b18  cmp     [rbp+arg_10], 0
0x180003b1c  jnz     short loc_180003B3C
0x180003b1e  call    __acrt_get_process_end_policy
0x180003b23  cmp     eax, 1
0x180003b26  jnz     short loc_180003B2C
0x180003b28  xor     dl, dl
0x180003b2a  jmp     short loc_180003B36
0x180003b2c  call    __acrt_app_verifier_enabled
0x180003b31  test    al, al
0x180003b33  setz    dl
0x180003b36  cmp     [rbp+arg_10], 0
0x180003b3a  jz      short loc_180003B47
0x180003b3c  mov     rbx, [rsp+50h+arg_0]
0x180003b41  add     rsp, 50h
0x180003b45  pop     rbp
0x180003b46  retn
0x180003b47  mov     ecx, ebx; uExitCode
0x180003b49  call    exit_or_terminate_process
```
