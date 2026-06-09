# Dossier::GetSetting(ushort const *,ulong &)

- ea: `0x18000e530`
- end: `0x18000e617`
- name: `?GetSetting@Dossier@@UEAAJPEBGAEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(Dossier *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000e530`
- `0x18000efec`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000e5e2`
- `msvcrt!_wtoi` at `0x18000e5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e590`

## pseudocode

```c
__int64 __fastcall Dossier::GetSetting(Dossier *this, const unsigned __int16 *a2, unsigned int *a3)
{
  int v4; // edi
  void *v5; // r15
  void *v6; // r14
  DWORD LastError; // ebx
  void *v9; // [rsp+28h] [rbp-18h] BYREF
  char v10; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF

  pv = 0;
  v9 = 0;
  v10 = 1;
  v4 = (*(__int64 (__fastcall **)(Dossier *, const unsigned __int16 *, void **))(*(_QWORD *)this + 48LL))(this, a2, &v9);
  if ( v10 )
  {
    v5 = v9;
    v6 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    pv = v5;
  }
  if ( v4 >= 0 )
  {
    *a3 = _wtoi((const wchar_t *)pv);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v4,
      (int)&pv);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x18000e530  mov     [rsp-28h+arg_8], rbx
0x18000e535  mov     [rsp-28h+arg_10], rsi
0x18000e53a  push    rbp
0x18000e53b  push    rdi
0x18000e53c  push    r12
0x18000e53e  push    r14
0x18000e540  push    r15
0x18000e542  mov     rbp, rsp
0x18000e545  sub     rsp, 40h
0x18000e549  mov     r12, r8
0x18000e54c  mov     [rbp+pv], 0
0x18000e554  lea     rax, [rbp+pv]
0x18000e558  mov     [rbp+var_20], rax
0x18000e55c  mov     [rbp+var_18], 0
0x18000e564  mov     [rbp+var_10], 1
0x18000e568  mov     rax, [rcx]
0x18000e56b  lea     r8, [rbp+var_18]
0x18000e56f  mov     rax, [rax+30h]
0x18000e573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e578  mov     edi, eax
0x18000e57a  cmp     [rbp+var_10], 0
0x18000e57e  jz      short loc_18000E5AD
0x18000e580  mov     r15, [rbp+var_18]
0x18000e584  mov     rsi, [rbp+var_20]
0x18000e588  mov     r14, [rsi]
0x18000e58b  test    r14, r14
0x18000e58e  jz      short loc_18000E5AA
0x18000e590  call    cs:__imp_GetLastError
0x18000e596  mov     ebx, eax
0x18000e598  mov     rcx, r14; pv
0x18000e59b  call    cs:__imp_CoTaskMemFree
0x18000e5a1  mov     ecx, ebx; dwErrCode
0x18000e5a3  call    cs:__imp_SetLastError
0x18000e5a9  nop
0x18000e5aa  mov     [rsi], r15
0x18000e5ad  test    edi, edi
0x18000e5af  jns     short loc_18000E5DE
0x18000e5b1  mov     rcx, [rbp+28h]; this
0x18000e5b5  mov     r9d, edi; char *
0x18000e5b8  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e5bf  mov     edx, 76h ; 'v'; void *
0x18000e5c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5c9  nop
0x18000e5ca  mov     rcx, [rbp+pv]; pv
0x18000e5ce  test    rcx, rcx
0x18000e5d1  jz      short loc_18000E5DA
0x18000e5d3  call    cs:__imp_CoTaskMemFree
0x18000e5d9  nop
0x18000e5da  mov     eax, edi
0x18000e5dc  jmp     short loc_18000E5FE
0x18000e5de  mov     rcx, [rbp+pv]; String
0x18000e5e2  call    cs:__imp__wtoi
0x18000e5e8  mov     [r12], eax
0x18000e5ec  mov     rcx, [rbp+pv]; pv
0x18000e5f0  test    rcx, rcx
0x18000e5f3  jz      short loc_18000E5FC
0x18000e5f5  call    cs:__imp_CoTaskMemFree
0x18000e5fb  nop
0x18000e5fc  xor     eax, eax
0x18000e5fe  lea     r11, [rsp+40h+var_s0]
0x18000e603  mov     rbx, [r11+38h]
0x18000e607  mov     rsi, [r11+40h]
0x18000e60b  mov     rsp, r11
0x18000e60e  pop     r15
0x18000e610  pop     r14
0x18000e612  pop     r12
0x18000e614  pop     rdi
0x18000e615  pop     rbp
0x18000e616  retn
```
