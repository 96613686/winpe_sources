# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x40ebee`
- end: `0x40ec51`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `99`
- prototype: `void __cdecl(UINT uExitCode, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x40ed39`
- `0x40ed48`
- `0x40ed57`
- `0x40ed93`

## callees

- `0x40eab4`
- `0x40ebee`
- `0x40ec52`
- `0x40ec94`
- `0x40ecd7`

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
0x40ebee  mov     edi, edi
0x40ebf0  push    ebp
0x40ebf1  mov     ebp, esp
0x40ebf3  sub     esp, 18h
0x40ebf6  cmp     [ebp+arg_8], 0
0x40ebfa  jnz     short loc_40EC0E
0x40ebfc  call    ___scrt_is_managed_app_0
0x40ec01  test    al, al
0x40ec03  jz      short loc_40EC0E
0x40ec05  push    [ebp+uExitCode]; unsigned int
0x40ec08  call    ?try_cor_exit_process@@YAXI@Z
0x40ec0d  pop     ecx
0x40ec0e  lea     eax, [ebp+arg_4]
0x40ec11  mov     [ebp+var_1], 0
0x40ec15  mov     [ebp+var_18], eax
0x40ec18  lea     ecx, [ebp+var_2]
0x40ec1b  lea     eax, [ebp+arg_8]
0x40ec1e  mov     [ebp+var_14], eax
0x40ec21  lea     eax, [ebp+var_1]
0x40ec24  push    2
0x40ec26  mov     [ebp+var_10], eax
0x40ec29  pop     eax
0x40ec2a  mov     [ebp+var_8], eax
0x40ec2d  mov     [ebp+var_C], eax
0x40ec30  lea     eax, [ebp+var_8]
0x40ec33  push    eax
0x40ec34  lea     eax, [ebp+var_18]
0x40ec37  push    eax
0x40ec38  lea     eax, [ebp+var_C]
0x40ec3b  push    eax
0x40ec3c  call    ??$?RV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@V_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_4fdada1b837b2abbf20876fac97688ad_@@AAV_lambda_b57350f2640456a0859d250846f69caf_@@$$QAV_lambda_eed5e4f92b5b7d55fa22c48c484aaa54_@@@Z
0x40ec41  cmp     [ebp+arg_8], 0
0x40ec45  jz      short loc_40EC49
0x40ec47  leave
0x40ec48  retn
0x40ec49  push    [ebp+uExitCode]; uExitCode
0x40ec4c  call    ?exit_or_terminate_process@@YAXI@Z
```
