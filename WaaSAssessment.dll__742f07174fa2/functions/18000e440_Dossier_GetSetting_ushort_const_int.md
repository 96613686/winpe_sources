# Dossier::GetSetting(ushort const *,int &)

- ea: `0x18000e440`
- end: `0x18000e527`
- name: `?GetSetting@Dossier@@UEAAJPEBGAEAH@Z`
- size: `231`
- prototype: `__int64 __fastcall(Dossier *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000e440`
- `0x18000efec`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000e4f2`
- `msvcrt!_wtoi` at `0x18000e4f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e505`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e4b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetSetting(Dossier *this, const unsigned __int16 *a2, int *a3)
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
      (void *)0x91,
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
0x18000e440  mov     [rsp-28h+arg_8], rbx
0x18000e445  mov     [rsp-28h+arg_10], rsi
0x18000e44a  push    rbp
0x18000e44b  push    rdi
0x18000e44c  push    r12
0x18000e44e  push    r14
0x18000e450  push    r15
0x18000e452  mov     rbp, rsp
0x18000e455  sub     rsp, 40h
0x18000e459  mov     r12, r8
0x18000e45c  mov     [rbp+pv], 0
0x18000e464  lea     rax, [rbp+pv]
0x18000e468  mov     [rbp+var_20], rax
0x18000e46c  mov     [rbp+var_18], 0
0x18000e474  mov     [rbp+var_10], 1
0x18000e478  mov     rax, [rcx]
0x18000e47b  lea     r8, [rbp+var_18]
0x18000e47f  mov     rax, [rax+30h]
0x18000e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e488  mov     edi, eax
0x18000e48a  cmp     [rbp+var_10], 0
0x18000e48e  jz      short loc_18000E4BD
0x18000e490  mov     r15, [rbp+var_18]
0x18000e494  mov     rsi, [rbp+var_20]
0x18000e498  mov     r14, [rsi]
0x18000e49b  test    r14, r14
0x18000e49e  jz      short loc_18000E4BA
0x18000e4a0  call    cs:__imp_GetLastError
0x18000e4a6  mov     ebx, eax
0x18000e4a8  mov     rcx, r14; pv
0x18000e4ab  call    cs:__imp_CoTaskMemFree
0x18000e4b1  mov     ecx, ebx; dwErrCode
0x18000e4b3  call    cs:__imp_SetLastError
0x18000e4b9  nop
0x18000e4ba  mov     [rsi], r15
0x18000e4bd  test    edi, edi
0x18000e4bf  jns     short loc_18000E4EE
0x18000e4c1  mov     rcx, [rbp+28h]; this
0x18000e4c5  mov     r9d, edi; char *
0x18000e4c8  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e4cf  mov     edx, 91h; void *
0x18000e4d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4d9  nop
0x18000e4da  mov     rcx, [rbp+pv]; pv
0x18000e4de  test    rcx, rcx
0x18000e4e1  jz      short loc_18000E4EA
0x18000e4e3  call    cs:__imp_CoTaskMemFree
0x18000e4e9  nop
0x18000e4ea  mov     eax, edi
0x18000e4ec  jmp     short loc_18000E50E
0x18000e4ee  mov     rcx, [rbp+pv]; String
0x18000e4f2  call    cs:__imp__wtoi
0x18000e4f8  mov     [r12], eax
0x18000e4fc  mov     rcx, [rbp+pv]; pv
0x18000e500  test    rcx, rcx
0x18000e503  jz      short loc_18000E50C
0x18000e505  call    cs:__imp_CoTaskMemFree
0x18000e50b  nop
0x18000e50c  xor     eax, eax
0x18000e50e  lea     r11, [rsp+40h+var_s0]
0x18000e513  mov     rbx, [r11+38h]
0x18000e517  mov     rsi, [r11+40h]
0x18000e51b  mov     rsp, r11
0x18000e51e  pop     r15
0x18000e520  pop     r14
0x18000e522  pop     r12
0x18000e524  pop     rdi
0x18000e525  pop     rbp
0x18000e526  retn
```
