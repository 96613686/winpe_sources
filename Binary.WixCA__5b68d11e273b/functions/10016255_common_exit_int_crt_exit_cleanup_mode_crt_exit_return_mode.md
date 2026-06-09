# common_exit(int,_crt_exit_cleanup_mode,_crt_exit_return_mode)

- ea: `0x10016255`
- end: `0x100162ba`
- name: `?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z`
- size: `101`
- prototype: `void __cdecl(UINT uExitCode, enum _crt_exit_cleanup_mode, enum _crt_exit_return_mode)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100163a4`
- `0x100163b3`

## callees

- `0x1001612f`
- `0x10016255`
- `0x100162bb`
- `0x100162fd`
- `0x10016340`

## pseudocode

```c
void __cdecl common_exit(UINT uExitCode, enum _crt_exit_cleanup_mode a2, enum _crt_exit_return_mode a3)
{
  _DWORD v3[3]; // [esp+0h] [ebp-18h] BYREF
  int v4; // [esp+Ch] [ebp-Ch] BYREF
  int v5; // [esp+10h] [ebp-8h] BYREF
  char v6; // [esp+17h] [ebp-1h] BYREF

  if ( a3 == _crt_exit_terminate_process && (unsigned __int8)__scrt_is_managed_app() )
    try_cor_exit_process(uExitCode);
  v6 = 0;
  v3[0] = &a2;
  v3[1] = &a3;
  v3[2] = &v6;
  v5 = 2;
  v4 = 2;
  __crt_seh_guarded_call<void>::operator()<_lambda_c76fdea48760d5f9368b465f31df4405_,_lambda_e378711a6f6581bf7f0efd7cdf97f5d9_ &,_lambda_e927a58b2a85c081d733e8c6192ae2d2_>(
    &v4,
    v3,
    &v5);
  if ( a3 == _crt_exit_terminate_process )
    exit_or_terminate_process(uExitCode);
}

```

## disassembly

```asm
0x10016255  mov     edi, edi
0x10016257  push    ebp
0x10016258  mov     ebp, esp
0x1001625a  sub     esp, 18h
0x1001625d  cmp     [ebp+arg_8], 0
0x10016261  jnz     short loc_10016275
0x10016263  call    ___scrt_is_managed_app
0x10016268  test    al, al
0x1001626a  jz      short loc_10016275
0x1001626c  push    [ebp+uExitCode]; unsigned int
0x1001626f  call    ?try_cor_exit_process@@YAXI@Z
0x10016274  pop     ecx
0x10016275  lea     eax, [ebp+arg_4]
0x10016278  mov     [ebp+var_1], 0
0x1001627c  mov     [ebp+var_18], eax
0x1001627f  lea     ecx, [ebp+var_2]
0x10016282  lea     eax, [ebp+arg_8]
0x10016285  mov     [ebp+var_14], eax
0x10016288  lea     eax, [ebp+var_1]
0x1001628b  push    2
0x1001628d  mov     [ebp+var_10], eax
0x10016290  pop     eax
0x10016291  mov     [ebp+var_8], eax
0x10016294  mov     [ebp+var_C], eax
0x10016297  lea     eax, [ebp+var_8]
0x1001629a  push    eax
0x1001629b  lea     eax, [ebp+var_18]
0x1001629e  push    eax
0x1001629f  lea     eax, [ebp+var_C]
0x100162a2  push    eax
0x100162a3  call    ??$?RV_lambda_c76fdea48760d5f9368b465f31df4405_@@AAV_lambda_e378711a6f6581bf7f0efd7cdf97f5d9_@@V_lambda_e927a58b2a85c081d733e8c6192ae2d2_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_c76fdea48760d5f9368b465f31df4405_@@AAV_lambda_e378711a6f6581bf7f0efd7cdf97f5d9_@@$$QAV_lambda_e927a58b2a85c081d733e8c6192ae2d2_@@@Z
0x100162a8  cmp     [ebp+arg_8], 0
0x100162ac  jz      short loc_100162B2
0x100162ae  mov     esp, ebp
0x100162b0  pop     ebp
0x100162b1  retn
0x100162b2  push    [ebp+uExitCode]; uExitCode
0x100162b5  call    ?exit_or_terminate_process@@YAXI@Z
```
