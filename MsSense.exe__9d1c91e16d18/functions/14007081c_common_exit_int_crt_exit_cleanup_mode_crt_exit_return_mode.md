# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x14007081c`
- end: `0x1400708ff`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `227`
- prototype: `void __fastcall(unsigned int, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007099c`
- `0x1400709ac`
- `0x1400709bc`
- `0x140070a04`

## callees

- `0x140070724`
- `0x14007081c`
- `0x140070900`
- `0x140070930`
- `0x14007a98c`
- `0x14007ae50`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140070843`
- `KERNEL32!GetModuleHandleW` at `0x140070843`

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
      sub_140070900(a1);
  }
}

```

## disassembly

```asm
0x14007081c  mov     [rsp-8+arg_10], r8d
0x140070821  mov     [rsp-8+arg_8], edx
0x140070825  push    rbp
0x140070826  mov     rbp, rsp
0x140070829  sub     rsp, 50h
0x14007082d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140070835  mov     [rsp+50h+arg_0], rbx
0x14007083a  mov     ebx, ecx
0x14007083c  test    r8d, r8d
0x14007083f  jnz     short loc_14007088B
0x140070841  xor     ecx, ecx; lpModuleName
0x140070843  call    cs:GetModuleHandleW
0x140070849  test    rax, rax
0x14007084c  jz      short loc_14007088B
0x14007084e  mov     ecx, 5A4Dh
0x140070853  cmp     [rax], cx
0x140070856  jnz     short loc_14007088B
0x140070858  movsxd  rcx, dword ptr [rax+3Ch]
0x14007085c  add     rcx, rax
0x14007085f  cmp     dword ptr [rcx], 4550h
0x140070865  jnz     short loc_14007088B
0x140070867  mov     eax, 20Bh
0x14007086c  cmp     [rcx+18h], ax
0x140070870  jnz     short loc_14007088B
0x140070872  cmp     dword ptr [rcx+84h], 0Eh
0x140070879  jbe     short loc_14007088B
0x14007087b  cmp     dword ptr [rcx+0F8h], 0
0x140070882  jz      short loc_14007088B
0x140070884  mov     ecx, ebx; unsigned int
0x140070886  call    ?try_cor_exit_process@@YAXI@Z
0x14007088b  mov     [rbp+arg_18], 0
0x14007088f  lea     rax, [rbp+arg_8]
0x140070893  mov     [rbp+var_18], rax
0x140070897  lea     rax, [rbp+arg_10]
0x14007089b  mov     [rbp+var_10], rax
0x14007089f  lea     rax, [rbp+arg_18]
0x1400708a3  mov     [rbp+var_8], rax
0x1400708a7  mov     eax, 2
0x1400708ac  mov     [rbp+var_2C], eax
0x1400708af  mov     [rbp+var_28], eax
0x1400708b2  lea     r9, [rbp+var_2C]
0x1400708b6  lea     r8, [rbp+var_18]
0x1400708ba  lea     rdx, [rbp+var_28]
0x1400708be  lea     rcx, [rbp+var_30]
0x1400708c2  call    ??$?RV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@V_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@?$__crt_seh_guarded_call@X@@QEAAX$$QEAV_lambda_99476a1ad63dd22509b5d3e65b0ffc95_@@AEAV_lambda_ad1ced32f4ac17aa236e5ef05d6b3b7c_@@$$QEAV_lambda_f7424dd8d45958661754dc4f2697e9c3_@@@Z
0x1400708c7  nop
0x1400708c8  cmp     [rbp+arg_10], 0
0x1400708cc  jnz     short loc_1400708EC
0x1400708ce  call    __acrt_get_process_end_policy
0x1400708d3  cmp     eax, 1
0x1400708d6  jnz     short loc_1400708DC
0x1400708d8  xor     dl, dl
0x1400708da  jmp     short loc_1400708E6
0x1400708dc  call    __acrt_app_verifier_enabled
0x1400708e1  test    al, al
0x1400708e3  setz    dl
0x1400708e6  cmp     [rbp+arg_10], 0
0x1400708ea  jz      short loc_1400708F7
0x1400708ec  mov     rbx, [rsp+50h+arg_0]
0x1400708f1  add     rsp, 50h
0x1400708f5  pop     rbp
0x1400708f6  retn
0x1400708f7  mov     ecx, ebx; unsigned int
0x1400708f9  call    sub_140070900
```
