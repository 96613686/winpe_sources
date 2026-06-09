# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x410774`
- end: `0x4107d7`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `99`
- prototype: `void __cdecl(UINT uExitCode, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4108bf`
- `0x4108ce`
- `0x4108dd`
- `0x410919`

## callees

- `0x41061b`
- `0x410774`
- `0x4107d8`
- `0x41081a`
- `0x41085d`

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
0x410774  mov     edi, edi
0x410776  push    ebp
0x410777  mov     ebp, esp
0x410779  sub     esp, 18h
0x41077c  cmp     [ebp+arg_8], 0
0x410780  jnz     short loc_410794
0x410782  call    ___scrt_is_managed_app_0
0x410787  test    al, al
0x410789  jz      short loc_410794
0x41078b  push    [ebp+uExitCode]; unsigned int
0x41078e  call    ?try_cor_exit_process@@YAXI@Z
0x410793  pop     ecx
0x410794  lea     eax, [ebp+arg_4]
0x410797  mov     [ebp+var_1], 0
0x41079b  mov     [ebp+var_18], eax
0x41079e  lea     ecx, [ebp+var_2]
0x4107a1  lea     eax, [ebp+arg_8]
0x4107a4  mov     [ebp+var_14], eax
0x4107a7  lea     eax, [ebp+var_1]
0x4107aa  push    2
0x4107ac  mov     [ebp+var_10], eax
0x4107af  pop     eax
0x4107b0  mov     [ebp+var_8], eax
0x4107b3  mov     [ebp+var_C], eax
0x4107b6  lea     eax, [ebp+var_8]
0x4107b9  push    eax
0x4107ba  lea     eax, [ebp+var_18]
0x4107bd  push    eax
0x4107be  lea     eax, [ebp+var_C]
0x4107c1  push    eax
0x4107c2  call    ??$?RV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@V_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@$$QAV_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@Z
0x4107c7  cmp     [ebp+arg_8], 0
0x4107cb  jz      short loc_4107CF
0x4107cd  leave
0x4107ce  retn
0x4107cf  push    [ebp+uExitCode]; uExitCode
0x4107d2  call    ?exit_or_terminate_process@@YAXI@Z
```
