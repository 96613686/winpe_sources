# common_exit

- ea: `0x140012b90`
- end: `0x140012c73`
- name: `common_exit`
- size: `227`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012d10`
- `0x140012d20`
- `0x140012d30`
- `0x140012d78`

## callees

- `0x140012a98`
- `0x140012b90`
- `0x140012c74`
- `0x140012ca4`
- `0x140016900`
- `0x14001768c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140012bb7`
- `KERNEL32!GetModuleHandleW` at `0x140012bb7`

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
0x140012b90  mov     [rsp-8+arg_10], r8d
0x140012b95  mov     [rsp-8+arg_8], edx
0x140012b99  push    rbp
0x140012b9a  mov     rbp, rsp
0x140012b9d  sub     rsp, 50h
0x140012ba1  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140012ba9  mov     [rsp+50h+arg_0], rbx
0x140012bae  mov     ebx, ecx
0x140012bb0  test    r8d, r8d
0x140012bb3  jnz     short loc_140012BFF
0x140012bb5  xor     ecx, ecx; lpModuleName
0x140012bb7  call    cs:__imp_GetModuleHandleW
0x140012bbd  test    rax, rax
0x140012bc0  jz      short loc_140012BFF
0x140012bc2  mov     ecx, 5A4Dh
0x140012bc7  cmp     [rax], cx
0x140012bca  jnz     short loc_140012BFF
0x140012bcc  movsxd  rcx, dword ptr [rax+3Ch]
0x140012bd0  add     rcx, rax
0x140012bd3  cmp     dword ptr [rcx], 4550h
0x140012bd9  jnz     short loc_140012BFF
0x140012bdb  mov     eax, 20Bh
0x140012be0  cmp     [rcx+18h], ax
0x140012be4  jnz     short loc_140012BFF
0x140012be6  cmp     dword ptr [rcx+84h], 0Eh
0x140012bed  jbe     short loc_140012BFF
0x140012bef  cmp     dword ptr [rcx+0F8h], 0
0x140012bf6  jz      short loc_140012BFF
0x140012bf8  mov     ecx, ebx
0x140012bfa  call    try_cor_exit_process
0x140012bff  mov     [rbp+arg_18], 0
0x140012c03  lea     rax, [rbp+arg_8]
0x140012c07  mov     [rbp+var_18], rax
0x140012c0b  lea     rax, [rbp+arg_10]
0x140012c0f  mov     [rbp+var_10], rax
0x140012c13  lea     rax, [rbp+arg_18]
0x140012c17  mov     [rbp+var_8], rax
0x140012c1b  mov     eax, 2
0x140012c20  mov     [rbp+var_2C], eax
0x140012c23  mov     [rbp+var_28], eax
0x140012c26  lea     r9, [rbp+var_2C]
0x140012c2a  lea     r8, [rbp+var_18]
0x140012c2e  lea     rdx, [rbp+var_28]
0x140012c32  lea     rcx, [rbp+var_30]
0x140012c36  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x140012c3b  nop
0x140012c3c  cmp     [rbp+arg_10], 0
0x140012c40  jnz     short loc_140012C60
0x140012c42  call    __acrt_get_process_end_policy
0x140012c47  cmp     eax, 1
0x140012c4a  jnz     short loc_140012C50
0x140012c4c  xor     dl, dl
0x140012c4e  jmp     short loc_140012C5A
0x140012c50  call    __acrt_app_verifier_enabled
0x140012c55  test    al, al
0x140012c57  setz    dl
0x140012c5a  cmp     [rbp+arg_10], 0
0x140012c5e  jz      short loc_140012C6B
0x140012c60  mov     rbx, [rsp+50h+arg_0]
0x140012c65  add     rsp, 50h
0x140012c69  pop     rbp
0x140012c6a  retn
0x140012c6b  mov     ecx, ebx; uExitCode
0x140012c6d  call    exit_or_terminate_process
```
