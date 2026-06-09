# common_exit

- ea: `0x18000d9f0`
- end: `0x18000daab`
- name: `common_exit`
- size: `187`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000db5c`
- `0x18000db6c`

## callees

- `0x18000d8e8`
- `0x18000d9f0`
- `0x18000daac`
- `0x18000daf8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000da0f`
- `KERNEL32!GetModuleHandleW` at `0x18000da0f`

## pseudocode

```c
__int64 __fastcall common_exit(UINT uExitCode, int a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  char *v5; // rcx
  __int64 result; // rax
  _BYTE v7[4]; // [rsp+20h] [rbp-30h] BYREF
  int v8; // [rsp+24h] [rbp-2Ch] BYREF
  int v9; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v10[4]; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+68h] [rbp+18h] BYREF
  int v12; // [rsp+70h] [rbp+20h] BYREF
  char v13; // [rsp+78h] [rbp+28h] BYREF

  v12 = a3;
  v11 = a2;
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
  v13 = 0;
  v10[0] = &v11;
  v10[1] = &v12;
  v10[2] = &v13;
  v8 = 2;
  v9 = 2;
  result = _crt_seh_guarded_call_void_::operator()__lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___(
             v7,
             &v9,
             v10,
             &v8);
  if ( !v12 )
    exit_or_terminate_process(uExitCode);
  return result;
}

```

## disassembly

```asm
0x18000d9f0  mov     [rsp-8+arg_0], rbx
0x18000d9f5  mov     [rsp-8+arg_10], r8d
0x18000d9fa  mov     [rsp-8+arg_8], edx
0x18000d9fe  push    rbp
0x18000d9ff  mov     rbp, rsp
0x18000da02  sub     rsp, 50h
0x18000da06  mov     ebx, ecx
0x18000da08  test    r8d, r8d
0x18000da0b  jnz     short loc_18000DA57
0x18000da0d  xor     ecx, ecx; lpModuleName
0x18000da0f  call    cs:__imp_GetModuleHandleW
0x18000da15  test    rax, rax
0x18000da18  jz      short loc_18000DA57
0x18000da1a  mov     ecx, 5A4Dh
0x18000da1f  cmp     [rax], cx
0x18000da22  jnz     short loc_18000DA57
0x18000da24  movsxd  rcx, dword ptr [rax+3Ch]
0x18000da28  add     rcx, rax
0x18000da2b  cmp     dword ptr [rcx], 4550h
0x18000da31  jnz     short loc_18000DA57
0x18000da33  mov     eax, 20Bh
0x18000da38  cmp     [rcx+18h], ax
0x18000da3c  jnz     short loc_18000DA57
0x18000da3e  cmp     dword ptr [rcx+84h], 0Eh
0x18000da45  jbe     short loc_18000DA57
0x18000da47  cmp     dword ptr [rcx+0F8h], 0
0x18000da4e  jz      short loc_18000DA57
0x18000da50  mov     ecx, ebx
0x18000da52  call    try_cor_exit_process
0x18000da57  lea     rax, [rbp+arg_8]
0x18000da5b  mov     [rbp+arg_18], 0
0x18000da5f  mov     [rbp+var_20], rax
0x18000da63  lea     r9, [rbp+var_2C]
0x18000da67  lea     rax, [rbp+arg_10]
0x18000da6b  mov     [rbp+var_18], rax
0x18000da6f  lea     r8, [rbp+var_20]
0x18000da73  lea     rax, [rbp+arg_18]
0x18000da77  mov     [rbp+var_10], rax
0x18000da7b  lea     rdx, [rbp+var_28]
0x18000da7f  mov     eax, 2
0x18000da84  lea     rcx, [rbp+var_30]
0x18000da88  mov     [rbp+var_2C], eax
0x18000da8b  mov     [rbp+var_28], eax
0x18000da8e  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x18000da93  cmp     [rbp+arg_10], 0
0x18000da97  jz      short loc_18000DAA4
0x18000da99  mov     rbx, [rsp+50h+arg_0]
0x18000da9e  add     rsp, 50h
0x18000daa2  pop     rbp
0x18000daa3  retn
0x18000daa4  mov     ecx, ebx; uExitCode
0x18000daa6  call    exit_or_terminate_process
```
