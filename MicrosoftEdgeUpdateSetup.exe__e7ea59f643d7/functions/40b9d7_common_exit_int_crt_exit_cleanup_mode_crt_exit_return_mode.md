# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x40b9d7`
- end: `0x40ba3a`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `99`
- prototype: `void __cdecl(UINT uExitCode, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x40bb22`
- `0x40bb31`
- `0x40bb40`
- `0x40bb7c`

## callees

- `0x40b89d`
- `0x40b9d7`
- `0x40ba3b`
- `0x40ba7d`
- `0x40bac0`

## pseudocode

```c
void __cdecl common_exit(UINT uExitCode, enum _crt_exit_cleanup_mode a2, enum _crt_exit_return_mode a3)
{
  _DWORD v3[3]; // [esp+0h] [ebp-18h] BYREF
  int v4; // [esp+Ch] [ebp-Ch] BYREF
  int v5; // [esp+10h] [ebp-8h] BYREF
  char v6; // [esp+17h] [ebp-1h] BYREF

  if ( a3 == _crt_exit_terminate_process && (unsigned __int8)__scrt_is_managed_app_0() )
    try_cor_exit_process(uExitCode);
  v6 = 0;
  v3[0] = &a2;
  v3[1] = &a3;
  v3[2] = &v6;
  v5 = 2;
  v4 = 2;
  __crt_seh_guarded_call<void>::operator()<_lambda_4fdada1b837b2abbf20876fac97688ad_,_lambda_b57350f2640456a0859d250846f69caf_ &,_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_>(
    &v4,
    v3,
    &v5);
  if ( a3 == _crt_exit_terminate_process )
    exit_or_terminate_process(uExitCode);
}

```

## disassembly

```asm
0x40b9d7  mov     edi, edi
0x40b9d9  push    ebp
0x40b9da  mov     ebp, esp
0x40b9dc  sub     esp, 18h
0x40b9df  cmp     [ebp+arg_8], 0
0x40b9e3  jnz     short loc_40B9F7
0x40b9e5  call    ___scrt_is_managed_app_0
0x40b9ea  test    al, al
0x40b9ec  jz      short loc_40B9F7
0x40b9ee  push    [ebp+uExitCode]; unsigned int
0x40b9f1  call    ?try_cor_exit_process@@YAXI@Z
0x40b9f6  pop     ecx
0x40b9f7  lea     eax, [ebp+arg_4]
0x40b9fa  mov     [ebp+var_1], 0
0x40b9fe  mov     [ebp+var_18], eax
0x40ba01  lea     ecx, [ebp+var_2]
0x40ba04  lea     eax, [ebp+arg_8]
0x40ba07  mov     [ebp+var_14], eax
0x40ba0a  lea     eax, [ebp+var_1]
0x40ba0d  push    2
0x40ba0f  mov     [ebp+var_10], eax
0x40ba12  pop     eax
0x40ba13  mov     [ebp+var_8], eax
0x40ba16  mov     [ebp+var_C], eax
0x40ba19  lea     eax, [ebp+var_8]
0x40ba1c  push    eax
0x40ba1d  lea     eax, [ebp+var_18]
0x40ba20  push    eax
0x40ba21  lea     eax, [ebp+var_C]
0x40ba24  push    eax
0x40ba25  call    ??$?RV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@V_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@$$QAV_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@Z
0x40ba2a  cmp     [ebp+arg_8], 0
0x40ba2e  jz      short loc_40BA32
0x40ba30  leave
0x40ba31  retn
0x40ba32  push    [ebp+uExitCode]; uExitCode
0x40ba35  call    ?exit_or_terminate_process@@YAXI@Z
```
