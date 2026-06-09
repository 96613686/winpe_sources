# common_exit

- ea: `0x1800041c8`
- end: `0x1800042ab`
- name: `common_exit`
- size: `227`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c4`
- `0x1800043d8`
- `0x1800043e8`
- `0x1800043f8`
- `0x180004448`
- `0x180004454`

## callees

- `0x180003f9c`
- `0x1800041c8`
- `0x1800042ac`
- `0x180004360`
- `0x1800071c0`
- `0x180007404`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800041ef`
- `KERNEL32!GetModuleHandleW` at `0x1800041ef`

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
0x1800041c8  mov     [rsp-8+arg_10], r8d
0x1800041cd  mov     [rsp-8+arg_8], edx
0x1800041d1  push    rbp
0x1800041d2  mov     rbp, rsp
0x1800041d5  sub     rsp, 50h
0x1800041d9  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1800041e1  mov     [rsp+50h+arg_0], rbx
0x1800041e6  mov     ebx, ecx
0x1800041e8  test    r8d, r8d
0x1800041eb  jnz     short loc_180004237
0x1800041ed  xor     ecx, ecx; lpModuleName
0x1800041ef  call    cs:__imp_GetModuleHandleW
0x1800041f5  test    rax, rax
0x1800041f8  jz      short loc_180004237
0x1800041fa  mov     ecx, 5A4Dh
0x1800041ff  cmp     [rax], cx
0x180004202  jnz     short loc_180004237
0x180004204  movsxd  rcx, dword ptr [rax+3Ch]
0x180004208  add     rcx, rax
0x18000420b  cmp     dword ptr [rcx], 4550h
0x180004211  jnz     short loc_180004237
0x180004213  mov     eax, 20Bh
0x180004218  cmp     [rcx+18h], ax
0x18000421c  jnz     short loc_180004237
0x18000421e  cmp     dword ptr [rcx+84h], 0Eh
0x180004225  jbe     short loc_180004237
0x180004227  cmp     dword ptr [rcx+0F8h], 0
0x18000422e  jz      short loc_180004237
0x180004230  mov     ecx, ebx
0x180004232  call    try_cor_exit_process
0x180004237  mov     [rbp+arg_18], 0
0x18000423b  lea     rax, [rbp+arg_8]
0x18000423f  mov     [rbp+var_18], rax
0x180004243  lea     rax, [rbp+arg_10]
0x180004247  mov     [rbp+var_10], rax
0x18000424b  lea     rax, [rbp+arg_18]
0x18000424f  mov     [rbp+var_8], rax
0x180004253  mov     eax, 2
0x180004258  mov     [rbp+var_2C], eax
0x18000425b  mov     [rbp+var_28], eax
0x18000425e  lea     r9, [rbp+var_2C]
0x180004262  lea     r8, [rbp+var_18]
0x180004266  lea     rdx, [rbp+var_28]
0x18000426a  lea     rcx, [rbp+var_30]
0x18000426e  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x180004273  nop
0x180004274  cmp     [rbp+arg_10], 0
0x180004278  jnz     short loc_180004298
0x18000427a  call    __acrt_get_process_end_policy
0x18000427f  cmp     eax, 1
0x180004282  jnz     short loc_180004288
0x180004284  xor     dl, dl
0x180004286  jmp     short loc_180004292
0x180004288  call    __acrt_app_verifier_enabled
0x18000428d  test    al, al
0x18000428f  setz    dl
0x180004292  cmp     [rbp+arg_10], 0
0x180004296  jz      short loc_1800042A3
0x180004298  mov     rbx, [rsp+50h+arg_0]
0x18000429d  add     rsp, 50h
0x1800042a1  pop     rbp
0x1800042a2  retn
0x1800042a3  mov     ecx, ebx; uExitCode
0x1800042a5  call    exit_or_terminate_process
```
