# Dossier::GetServicingBranchBuild(ulong,ulong,ulong,ulong &)

- ea: `0x18000e0f0`
- end: `0x18000e2ec`
- name: `?GetServicingBranchBuild@Dossier@@UEAAJKKKAEAK@Z`
- size: `508`
- prototype: `int(Dossier *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2d8`
- `0x18000e0f0`
- `0x18000efec`
- `0x180018a50`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e24f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e24f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e12a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e21b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e208`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetServicingBranchBuild(Dossier *this, unsigned int a2, int a3, int a4, unsigned int *a5)
{
  int v6; // r14d
  unsigned int v7; // r15d
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v14; // rax
  int v15; // esi
  void *v16; // r12
  LPVOID *v17; // r14
  void *v18; // r15
  DWORD LastError; // edi
  int v20; // [rsp+20h] [rbp-40h]
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+28h] [rbp-38h]
  unsigned int v23; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v25; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-24h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-18h]
  void *v29; // [rsp+50h] [rbp-10h] BYREF
  char v30; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v6 = a3;
  v7 = a2;
  pv = 0;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v10 = v9;
  if ( v9 )
    memset_0(v9, 0, 0x208u);
  v22 = a4;
  v20 = v6;
  v11 = StringCchPrintfW(v10, 0x104u, L"%d.%d.%d.SB", v7, v20, v22);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( v10 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v10[v14] );
      v10 = (unsigned __int16 *)CoTaskMemRealloc(v10, 2LL * (unsigned int)(v14 + 1));
    }
    p_pv = &pv;
    v29 = 0;
    v30 = 1;
    v15 = (*(__int64 (__fastcall **)(Dossier *, unsigned __int16 *, void **))(*(_QWORD *)this + 48LL))(this, v10, &v29);
    if ( v30 )
    {
      v16 = v29;
      v17 = p_pv;
      v18 = *p_pv;
      if ( *p_pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(v18);
        SetLastError(LastError);
      }
      *v17 = v16;
      v6 = a3;
      v7 = a2;
    }
    if ( v15 >= 0 )
    {
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      if ( (unsigned int)GetVersionElements((const unsigned __int16 *)pv, &v23, &v24, &v25, &v26) == 4
        && v23 == v7
        && v24 == v6
        && v25 == a4 )
      {
        *a5 = v26;
      }
      CoTaskMemFree(v10);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
        (const char *)(unsigned int)v15,
        v21);
      CoTaskMemFree(v10);
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v11,
      v21);
    CoTaskMemFree(v10);
    return v12;
  }
}

```

## disassembly

```asm
0x18000e0f0  mov     [rsp-38h+arg_0], rbx
0x18000e0f5  mov     [rsp-38h+arg_10], r8d
0x18000e0fa  mov     [rsp-38h+arg_8], edx
0x18000e0fe  push    rbp
0x18000e0ff  push    rsi
0x18000e100  push    rdi
0x18000e101  push    r12
0x18000e103  push    r13
0x18000e105  push    r14
0x18000e107  push    r15
0x18000e109  mov     rbp, rsp
0x18000e10c  sub     rsp, 60h
0x18000e110  mov     r13d, r9d
0x18000e113  mov     r14d, r8d
0x18000e116  mov     r15d, edx
0x18000e119  mov     rsi, rcx
0x18000e11c  xor     r12d, r12d
0x18000e11f  mov     [rbp+pv], r12
0x18000e123  mov     edi, 208h
0x18000e128  mov     ecx, edi; cb
0x18000e12a  call    cs:__imp_CoTaskMemAlloc
0x18000e130  mov     rbx, rax
0x18000e133  test    rax, rax
0x18000e136  jz      short loc_18000E145
0x18000e138  mov     r8d, edi; Size
0x18000e13b  xor     edx, edx; Val
0x18000e13d  mov     rcx, rax; void *
0x18000e140  call    memset_0
0x18000e145  mov     [rsp+60h+var_38], r13d
0x18000e14a  mov     dword ptr [rsp+60h+var_40], r14d; int
0x18000e14f  mov     r9d, r15d
0x18000e152  lea     r8, aDDDSb; "%d.%d.%d.SB"
0x18000e159  mov     edx, 104h; unsigned __int64
0x18000e15e  mov     rcx, rbx; unsigned __int16 *
0x18000e161  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e166  mov     edi, eax
0x18000e168  test    eax, eax
0x18000e16a  jns     short loc_18000E1A5
0x18000e16c  mov     rcx, [rbp+38h]; this
0x18000e170  mov     r9d, eax; char *
0x18000e173  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e17a  mov     edx, 1EFh; void *
0x18000e17f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e184  mov     rcx, rbx; pv
0x18000e187  call    cs:__imp_CoTaskMemFree
0x18000e18d  nop
0x18000e18e  mov     rcx, [rbp+pv]; pv
0x18000e192  test    rcx, rcx
0x18000e195  jz      short loc_18000E19E
0x18000e197  call    cs:__imp_CoTaskMemFree
0x18000e19d  nop
0x18000e19e  mov     eax, edi
0x18000e1a0  jmp     loc_18000E2D4
0x18000e1a5  test    rbx, rbx
0x18000e1a8  jz      short loc_18000E1CA
0x18000e1aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e1ae  inc     rax
0x18000e1b1  cmp     [rbx+rax*2], r12w
0x18000e1b6  jnz     short loc_18000E1AE
0x18000e1b8  lea     edx, [rax+1]
0x18000e1bb  add     rdx, rdx; cb
0x18000e1be  mov     rcx, rbx; pv
0x18000e1c1  call    cs:__imp_CoTaskMemRealloc
0x18000e1c7  mov     rbx, rax
0x18000e1ca  lea     rax, [rbp+pv]
0x18000e1ce  mov     [rbp+var_18], rax
0x18000e1d2  mov     [rbp+var_10], r12
0x18000e1d6  mov     [rbp+var_8], 1
0x18000e1da  mov     rax, [rsi]
0x18000e1dd  lea     r8, [rbp+var_10]
0x18000e1e1  mov     rdx, rbx
0x18000e1e4  mov     rcx, rsi
0x18000e1e7  mov     rax, [rax+30h]
0x18000e1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1f0  mov     esi, eax
0x18000e1f2  cmp     [rbp+var_8], r12b
0x18000e1f6  jz      short loc_18000E230
0x18000e1f8  mov     r12, [rbp+var_10]
0x18000e1fc  mov     r14, [rbp+var_18]
0x18000e200  mov     r15, [r14]
0x18000e203  test    r15, r15
0x18000e206  jz      short loc_18000E222
0x18000e208  call    cs:__imp_GetLastError
0x18000e20e  mov     edi, eax
0x18000e210  mov     rcx, r15; pv
0x18000e213  call    cs:__imp_CoTaskMemFree
0x18000e219  mov     ecx, edi; dwErrCode
0x18000e21b  call    cs:__imp_SetLastError
0x18000e221  nop
0x18000e222  mov     [r14], r12
0x18000e225  mov     r14d, [rbp+arg_10]
0x18000e229  mov     r15d, [rbp+arg_8]
0x18000e22d  xor     r12d, r12d
0x18000e230  test    esi, esi
0x18000e232  jns     short loc_18000E26A
0x18000e234  mov     rcx, [rbp+38h]; this
0x18000e238  mov     r9d, esi; char *
0x18000e23b  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e242  mov     edx, 1F1h; void *
0x18000e247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e24c  mov     rcx, rbx; pv
0x18000e24f  call    cs:__imp_CoTaskMemFree
0x18000e255  nop
0x18000e256  mov     rcx, [rbp+pv]; pv
0x18000e25a  test    rcx, rcx
0x18000e25d  jz      short loc_18000E266
0x18000e25f  call    cs:__imp_CoTaskMemFree
0x18000e265  nop
0x18000e266  mov     eax, esi
0x18000e268  jmp     short loc_18000E2D4
0x18000e26a  mov     [rbp+var_30], r12d
0x18000e26e  mov     [rbp+var_2C], r12d
0x18000e272  mov     [rbp+var_28], r12d
0x18000e276  mov     [rbp+var_24], r12d
0x18000e27a  lea     rax, [rbp+var_24]
0x18000e27e  mov     [rsp+60h+var_40], rax; unsigned int *
0x18000e283  lea     r9, [rbp+var_28]; unsigned int *
0x18000e287  lea     r8, [rbp+var_2C]; unsigned int *
0x18000e28b  lea     rdx, [rbp+var_30]; unsigned int *
0x18000e28f  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000e293  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000e298  cmp     eax, 4
0x18000e29b  jnz     short loc_18000E2B8
0x18000e29d  cmp     [rbp+var_30], r15d
0x18000e2a1  jnz     short loc_18000E2B8
0x18000e2a3  cmp     [rbp+var_2C], r14d
0x18000e2a7  jnz     short loc_18000E2B8
0x18000e2a9  cmp     [rbp+var_28], r13d
0x18000e2ad  jnz     short loc_18000E2B8
0x18000e2af  mov     rcx, [rbp+arg_20]
0x18000e2b3  mov     eax, [rbp+var_24]
0x18000e2b6  mov     [rcx], eax
0x18000e2b8  mov     rcx, rbx; pv
0x18000e2bb  call    cs:__imp_CoTaskMemFree
0x18000e2c1  nop
0x18000e2c2  mov     rcx, [rbp+pv]; pv
0x18000e2c6  test    rcx, rcx
0x18000e2c9  jz      short loc_18000E2D2
0x18000e2cb  call    cs:__imp_CoTaskMemFree
0x18000e2d1  nop
0x18000e2d2  xor     eax, eax
0x18000e2d4  mov     rbx, [rsp+60h+arg_0]
0x18000e2dc  add     rsp, 60h
0x18000e2e0  pop     r15
0x18000e2e2  pop     r14
0x18000e2e4  pop     r13
0x18000e2e6  pop     r12
0x18000e2e8  pop     rdi
0x18000e2e9  pop     rsi
0x18000e2ea  pop     rbp
0x18000e2eb  retn
```
