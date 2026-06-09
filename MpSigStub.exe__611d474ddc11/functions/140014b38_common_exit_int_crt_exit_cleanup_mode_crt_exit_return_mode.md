# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x140014b38`
- end: `0x140014bfd`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `197`
- prototype: `void __fastcall(unsigned int, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014cc8`
- `0x140014cd8`
- `0x140014ce8`
- `0x140014d34`

## callees

- `0x140014a3c`
- `0x140014b38`
- `0x140014c00`
- `0x140014c58`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140014b5f`
- `KERNEL32!GetModuleHandleW` at `0x140014b5f`

## pseudocode

```c
void __fastcall common_exit(unsigned int a1, enum _crt_exit_cleanup_mode a2, enum _crt_exit_return_mode a3)
{
  HMODULE ModuleHandleW; // rax
  char *v5; // rcx
  _BYTE v6[4]; // [rsp+20h] [rbp-30h] BYREF
  int v7; // [rsp+24h] [rbp-2Ch] BYREF
  int v8; // [rsp+28h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-20h]
  _QWORD v10[3]; // [rsp+38h] [rbp-18h] BYREF
  enum _crt_exit_cleanup_mode v11; // [rsp+68h] [rbp+18h] BYREF
  enum _crt_exit_return_mode v12; // [rsp+70h] [rbp+20h] BYREF
  char v13; // [rsp+78h] [rbp+28h] BYREF

  v12 = a3;
  v11 = a2;
  v9 = -2;
  if ( a3 == _crt_exit_terminate_process )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      if ( *(_WORD *)ModuleHandleW == 23117 )
      {
        v5 = (char *)ModuleHandleW + *((int *)ModuleHandleW + 15);
        if ( *(_DWORD *)v5 == 17744 && *((_WORD *)v5 + 12) == 523 && *((_DWORD *)v5 + 33) > 0xEu && *((_DWORD *)v5 + 62) )
          try_cor_exit_process(a1);
      }
    }
  }
  v13 = 0;
  v10[0] = &v11;
  v10[1] = &v12;
  v10[2] = &v13;
  v7 = 2;
  v8 = 2;
  __crt_seh_guarded_call<void>::operator()<_lambda_99476a1ad63dd22509b5d3e65b0ffc95_,_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_ &,_lambda_f7424dd8d45958661754dc4f2697e9c3_>(
    v6,
    &v8,
    v10,
    &v7);
  if ( v12 == _crt_exit_terminate_process )
    exit_or_terminate_process(a1);
}

```

## disassembly

```asm
0x140014b38  mov     [rsp-8+arg_10], r8d
0x140014b3d  mov     [rsp-8+arg_8], edx
0x140014b41  push    rbp
0x140014b42  mov     rbp, rsp
0x140014b45  sub     rsp, 50h
0x140014b49  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140014b51  mov     [rsp+50h+arg_0], rbx
0x140014b56  mov     ebx, ecx
0x140014b58  test    r8d, r8d
0x140014b5b  jnz     short loc_140014BA7
0x140014b5d  xor     ecx, ecx; lpModuleName
0x140014b5f  call    cs:GetModuleHandleW
0x140014b65  test    rax, rax
0x140014b68  jz      short loc_140014BA7
0x140014b6a  mov     ecx, 5A4Dh
0x140014b6f  cmp     [rax], cx
0x140014b72  jnz     short loc_140014BA7
0x140014b74  movsxd  rcx, dword ptr [rax+3Ch]
0x140014b78  add     rcx, rax
0x140014b7b  cmp     dword ptr [rcx], 4550h
0x140014b81  jnz     short loc_140014BA7
0x140014b83  mov     eax, 20Bh
0x140014b88  cmp     [rcx+18h], ax
0x140014b8c  jnz     short loc_140014BA7
0x140014b8e  cmp     dword ptr [rcx+84h], 0Eh
0x140014b95  jbe     short loc_140014BA7
0x140014b97  cmp     dword ptr [rcx+0F8h], 0
0x140014b9e  jz      short loc_140014BA7
0x140014ba0  mov     ecx, ebx; unsigned int
0x140014ba2  call    ?try_cor_exit_process@@YAXI@Z
0x140014ba7  mov     [rbp+arg_18], 0
0x140014bab  lea     rax, [rbp+arg_8]
0x140014baf  mov     [rbp+var_18], rax
0x140014bb3  lea     rax, [rbp+arg_10]
0x140014bb7  mov     [rbp+var_10], rax
0x140014bbb  lea     rax, [rbp+arg_18]
0x140014bbf  mov     [rbp+var_8], rax
0x140014bc3  mov     eax, 2
0x140014bc8  mov     [rbp+var_2C], eax
0x140014bcb  mov     [rbp+var_28], eax
0x140014bce  lea     r9, [rbp+var_2C]
0x140014bd2  lea     r8, [rbp+var_18]
0x140014bd6  lea     rdx, [rbp+var_28]
0x140014bda  lea     rcx, [rbp+var_30]
0x140014bde  call    ??$?RV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@V_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@?$__crt_seh_guarded_call@X@@QEAAX$$QEAV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@$$QEAV_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@Z
0x140014be3  nop
0x140014be4  cmp     [rbp+arg_10], 0
0x140014be8  jz      short loc_140014BF5
0x140014bea  mov     rbx, [rsp+50h+arg_0]
0x140014bef  add     rsp, 50h
0x140014bf3  pop     rbp
0x140014bf4  retn
0x140014bf5  mov     ecx, ebx; unsigned int
0x140014bf7  call    ?exit_or_terminate_process@@YAXI@Z
```
