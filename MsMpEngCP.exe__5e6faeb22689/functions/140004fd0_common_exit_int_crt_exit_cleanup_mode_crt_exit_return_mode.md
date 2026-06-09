# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x140004fd0`
- end: `0x1400050b3`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `227`
- prototype: `void __fastcall(unsigned int, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005150`
- `0x140005160`
- `0x140005170`
- `0x1400051b8`

## callees

- `0x140004ed8`
- `0x140004fd0`
- `0x1400050b4`
- `0x1400050e4`
- `0x140008264`
- `0x140008298`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140004ff7`
- `KERNEL32!GetModuleHandleW` at `0x140004ff7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  {
    if ( (unsigned int)_acrt_get_process_end_policy() != 1 )
      _acrt_app_verifier_enabled();
    if ( v12 == _crt_exit_terminate_process )
      sub_1400050B4(a1);
  }
}

```

## disassembly

```asm
0x140004fd0  mov     [rsp-8+arg_10], r8d
0x140004fd5  mov     [rsp-8+arg_8], edx
0x140004fd9  push    rbp
0x140004fda  mov     rbp, rsp
0x140004fdd  sub     rsp, 50h
0x140004fe1  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140004fe9  mov     [rsp+50h+arg_0], rbx
0x140004fee  mov     ebx, ecx
0x140004ff0  test    r8d, r8d
0x140004ff3  jnz     short loc_14000503F
0x140004ff5  xor     ecx, ecx; lpModuleName
0x140004ff7  call    cs:GetModuleHandleW
0x140004ffd  test    rax, rax
0x140005000  jz      short loc_14000503F
0x140005002  mov     ecx, 5A4Dh
0x140005007  cmp     [rax], cx
0x14000500a  jnz     short loc_14000503F
0x14000500c  movsxd  rcx, dword ptr [rax+3Ch]
0x140005010  add     rcx, rax
0x140005013  cmp     dword ptr [rcx], 4550h
0x140005019  jnz     short loc_14000503F
0x14000501b  mov     eax, 20Bh
0x140005020  cmp     [rcx+18h], ax
0x140005024  jnz     short loc_14000503F
0x140005026  cmp     dword ptr [rcx+84h], 0Eh
0x14000502d  jbe     short loc_14000503F
0x14000502f  cmp     dword ptr [rcx+0F8h], 0
0x140005036  jz      short loc_14000503F
0x140005038  mov     ecx, ebx; unsigned int
0x14000503a  call    ?try_cor_exit_process@@YAXI@Z
0x14000503f  mov     [rbp+arg_18], 0
0x140005043  lea     rax, [rbp+arg_8]
0x140005047  mov     [rbp+var_18], rax
0x14000504b  lea     rax, [rbp+arg_10]
0x14000504f  mov     [rbp+var_10], rax
0x140005053  lea     rax, [rbp+arg_18]
0x140005057  mov     [rbp+var_8], rax
0x14000505b  mov     eax, 2
0x140005060  mov     [rbp+var_2C], eax
0x140005063  mov     [rbp+var_28], eax
0x140005066  lea     r9, [rbp+var_2C]
0x14000506a  lea     r8, [rbp+var_18]
0x14000506e  lea     rdx, [rbp+var_28]
0x140005072  lea     rcx, [rbp+var_30]
0x140005076  call    ??$?RV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@V_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@?$__crt_seh_guarded_call@X@@QEAAX$$QEAV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@$$QEAV_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@Z
0x14000507b  nop
0x14000507c  cmp     [rbp+arg_10], 0
0x140005080  jnz     short loc_1400050A0
0x140005082  call    __acrt_get_process_end_policy
0x140005087  cmp     eax, 1
0x14000508a  jnz     short loc_140005090
0x14000508c  xor     dl, dl
0x14000508e  jmp     short loc_14000509A
0x140005090  call    __acrt_app_verifier_enabled
0x140005095  test    al, al
0x140005097  setz    dl
0x14000509a  cmp     [rbp+arg_10], 0
0x14000509e  jz      short loc_1400050AB
0x1400050a0  mov     rbx, [rsp+50h+arg_0]
0x1400050a5  add     rsp, 50h
0x1400050a9  pop     rbp
0x1400050aa  retn
0x1400050ab  mov     ecx, ebx; unsigned int
0x1400050ad  call    sub_1400050B4
```
