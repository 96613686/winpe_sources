# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x140018590`
- end: `0x140018673`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `227`
- prototype: `void __fastcall(unsigned int, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018710`
- `0x140018720`
- `0x140018730`
- `0x140018778`

## callees

- `0x140018498`
- `0x140018590`
- `0x140018674`
- `0x1400186a4`
- `0x14001d2a4`
- `0x14001e27c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400185b7`
- `KERNEL32!GetModuleHandleW` at `0x1400185b7`

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
  {
    if ( (unsigned int)_acrt_get_process_end_policy() != 1 )
      _acrt_app_verifier_enabled();
    if ( v12 == _crt_exit_terminate_process )
      sub_140018674(a1);
  }
}

```

## disassembly

```asm
0x140018590  mov     [rsp-8+arg_10], r8d
0x140018595  mov     [rsp-8+arg_8], edx
0x140018599  push    rbp
0x14001859a  mov     rbp, rsp
0x14001859d  sub     rsp, 50h
0x1400185a1  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1400185a9  mov     [rsp+50h+arg_0], rbx
0x1400185ae  mov     ebx, ecx
0x1400185b0  test    r8d, r8d
0x1400185b3  jnz     short loc_1400185FF
0x1400185b5  xor     ecx, ecx; lpModuleName
0x1400185b7  call    cs:GetModuleHandleW
0x1400185bd  test    rax, rax
0x1400185c0  jz      short loc_1400185FF
0x1400185c2  mov     ecx, 5A4Dh
0x1400185c7  cmp     [rax], cx
0x1400185ca  jnz     short loc_1400185FF
0x1400185cc  movsxd  rcx, dword ptr [rax+3Ch]
0x1400185d0  add     rcx, rax
0x1400185d3  cmp     dword ptr [rcx], 4550h
0x1400185d9  jnz     short loc_1400185FF
0x1400185db  mov     eax, 20Bh
0x1400185e0  cmp     [rcx+18h], ax
0x1400185e4  jnz     short loc_1400185FF
0x1400185e6  cmp     dword ptr [rcx+84h], 0Eh
0x1400185ed  jbe     short loc_1400185FF
0x1400185ef  cmp     dword ptr [rcx+0F8h], 0
0x1400185f6  jz      short loc_1400185FF
0x1400185f8  mov     ecx, ebx; unsigned int
0x1400185fa  call    ?try_cor_exit_process@@YAXI@Z
0x1400185ff  mov     [rbp+arg_18], 0
0x140018603  lea     rax, [rbp+arg_8]
0x140018607  mov     [rbp+var_18], rax
0x14001860b  lea     rax, [rbp+arg_10]
0x14001860f  mov     [rbp+var_10], rax
0x140018613  lea     rax, [rbp+arg_18]
0x140018617  mov     [rbp+var_8], rax
0x14001861b  mov     eax, 2
0x140018620  mov     [rbp+var_2C], eax
0x140018623  mov     [rbp+var_28], eax
0x140018626  lea     r9, [rbp+var_2C]
0x14001862a  lea     r8, [rbp+var_18]
0x14001862e  lea     rdx, [rbp+var_28]
0x140018632  lea     rcx, [rbp+var_30]
0x140018636  call    ??$?RV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@V_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@?$__crt_seh_guarded_call@X@@QEAAX$$QEAV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@$$QEAV_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@Z
0x14001863b  nop
0x14001863c  cmp     [rbp+arg_10], 0
0x140018640  jnz     short loc_140018660
0x140018642  call    __acrt_get_process_end_policy
0x140018647  cmp     eax, 1
0x14001864a  jnz     short loc_140018650
0x14001864c  xor     dl, dl
0x14001864e  jmp     short loc_14001865A
0x140018650  call    __acrt_app_verifier_enabled
0x140018655  test    al, al
0x140018657  setz    dl
0x14001865a  cmp     [rbp+arg_10], 0
0x14001865e  jz      short loc_14001866B
0x140018660  mov     rbx, [rsp+50h+arg_0]
0x140018665  add     rsp, 50h
0x140018669  pop     rbp
0x14001866a  retn
0x14001866b  mov     ecx, ebx; unsigned int
0x14001866d  call    sub_140018674
```
