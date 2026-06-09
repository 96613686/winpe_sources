# EnterpriseFeatureControl::ReadPolicyState(bool *)

- ea: `0x180036ac8`
- end: `0x180036dc7`
- name: `?ReadPolicyState@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `767`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800359e4`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x180018f7c`
- `0x1800298cc`
- `0x180036ac8`
- `0x180036efc`
- `0x180037440`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036bfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036bfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036c34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036bec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036c26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036bec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036c26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d5b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180036b43`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180036bcc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180036b43`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180036bcc`

## string_xrefs

- `0x180036b3c`: `WindowsUpdate`
- `0x180036bc5`: `WindowsUpdate`
- `0x180036b35`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180036bb6`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180036cbb`: `\UpdatePolicy\PolicyState`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::ReadPolicyState(bool *a1)
{
  int PersistedRegistryLocationW; // eax
  __int64 v4; // rdx
  unsigned int v5; // esi
  __int64 v6; // rdx
  void *v7; // rbx
  void *v8; // rdi
  unsigned int v9; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v11; // edi
  HANDLE v12; // rax
  _WORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rdi
  int v18; // eax
  HKEY v19; // rcx
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  int v26; // [rsp+20h] [rbp-30h]
  int *v27; // [rsp+20h] [rbp-30h]
  unsigned int v28; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  int v30; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v28 = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  v30 = 0;
  v27 = &v30;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdate",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate",
                                 0,
                                 0);
  v5 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v5 = -2147418113;
    v6 = 93;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v5,
      (int)&v30);
    goto LABEL_34;
  }
  v7 = 0;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v5 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v5,
        (int)&v30);
      goto LABEL_13;
    }
    goto LABEL_14;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpMem,
    v4,
    (unsigned int)v30);
  v8 = lpMem;
  if ( !lpMem )
  {
    v5 = -2147024882;
    v6 = 97;
    goto LABEL_33;
  }
  LODWORD(v27) = 0;
  v9 = GetPersistedRegistryLocationW(L"WindowsUpdate", L"SOFTWARE\\Microsoft\\WindowsUpdate", lpMem, (unsigned int)v30);
  if ( v9 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x63,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
           (const char *)v9,
           0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
LABEL_13:
    if ( (v5 & 0x80000000) != 0 )
    {
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v5,
        (int)v27);
      return v5;
    }
    goto LABEL_14;
  }
  v7 = v8;
  if ( !v8 )
  {
LABEL_14:
    v11 = -2147024809;
    goto LABEL_15;
  }
  v13 = v8;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v11 = v14 == 0 ? 0x80070057 : 0;
  v15 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v16 = v15 + 28;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpMem,
      0x7FFFFFFF - v14,
      v15 + 28);
    v17 = (unsigned __int16 *)lpMem;
    if ( lpMem )
    {
      v18 = StringCchPrintfW((unsigned __int16 *)lpMem, v16, L"%s\\%s", v7);
      v5 = v18;
      if ( v18 >= 0 )
      {
        v18 = EnterpriseFeatureControl::RegQueryDwordValue(v19, v17, v20, &v28);
        v5 = v18;
        if ( v18 >= 0 )
        {
          *a1 = v28 - 1 <= 1;
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v17);
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v7);
          return 0;
        }
        v21 = 171;
      }
      else
      {
        v21 = 165;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)(unsigned int)v18,
        (int)L"\\UpdatePolicy\\PolicyState");
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v17);
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)0x8007000ELL,
        0);
    }
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v7);
    return v5;
  }
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x99,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)v11,
    (int)v27);
  if ( v7 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v7);
  }
  return v11;
}

```

## disassembly

```asm
0x180036ac8  mov     [rsp-28h+arg_8], rbx
0x180036acd  mov     [rsp-28h+arg_10], rsi
0x180036ad2  push    rbp
0x180036ad3  push    rdi
0x180036ad4  push    r12
0x180036ad6  push    r14
0x180036ad8  push    r15
0x180036ada  mov     rbp, rsp
0x180036add  sub     rsp, 50h
0x180036ae1  mov     rax, cs:__security_cookie
0x180036ae8  xor     rax, rsp
0x180036aeb  mov     [rbp+var_8], rax
0x180036aef  xor     r12d, r12d
0x180036af2  mov     r15, rcx
0x180036af5  mov     [rbp+var_20], r12d
0x180036af9  test    rcx, rcx
0x180036afc  jnz     short loc_180036B22
0x180036afe  mov     rcx, [rbp+28h]; this
0x180036b02  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036b09  mov     ebx, 80004003h
0x180036b0e  mov     edx, 95h; void *
0x180036b13  mov     r9d, ebx; char *
0x180036b16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b1b  mov     eax, ebx
0x180036b1d  jmp     loc_180036DA2
0x180036b22  lea     rax, [rbp+var_10]
0x180036b26  mov     [rbp+var_10], r12d
0x180036b2a  xor     r9d, r9d
0x180036b2d  mov     qword ptr [rsp+50h+var_30], rax; int
0x180036b32  xor     r8d, r8d
0x180036b35  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180036b3c  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180036b43  call    cs:__imp_GetPersistedRegistryLocationW
0x180036b49  lea     r14, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036b50  mov     esi, eax
0x180036b52  test    eax, eax
0x180036b54  jnz     short loc_180036B63
0x180036b56  mov     esi, 8000FFFFh
0x180036b5b  lea     edx, [rax+5Dh]
0x180036b5e  jmp     loc_180036D7D
0x180036b63  mov     rbx, r12
0x180036b66  cmp     eax, 0EAh
0x180036b6b  jz      short loc_180036B98
0x180036b6d  test    eax, eax
0x180036b6f  jle     short loc_180036B7A
0x180036b71  movzx   esi, ax
0x180036b74  or      esi, 80070000h
0x180036b7a  test    esi, esi
0x180036b7c  jns     loc_180036C08
0x180036b82  mov     rcx, [rbp+28h]; this
0x180036b86  mov     r9d, esi; char *
0x180036b89  mov     r8, r14; unsigned int
0x180036b8c  mov     edx, 5Eh ; '^'; void *
0x180036b91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b96  jmp     short loc_180036C00
0x180036b98  mov     r8d, [rbp+var_10]
0x180036b9c  lea     rcx, [rbp+lpMem]
0x180036ba0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180036ba5  mov     rdi, [rbp+lpMem]
0x180036ba9  test    rdi, rdi
0x180036bac  jz      loc_180036D73
0x180036bb2  mov     r9d, [rbp+var_10]
0x180036bb6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180036bbd  mov     r8, rdi
0x180036bc0  mov     qword ptr [rsp+50h+var_30], r12; int
0x180036bc5  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180036bcc  call    cs:__imp_GetPersistedRegistryLocationW
0x180036bd2  test    eax, eax
0x180036bd4  jz      short loc_180036C41
0x180036bd6  mov     rcx, [rbp+28h]; this
0x180036bda  mov     r9d, eax; char *
0x180036bdd  mov     r8, r14; unsigned int
0x180036be0  mov     edx, 63h ; 'c'; void *
0x180036be5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036bea  mov     esi, eax
0x180036bec  call    cs:__imp_GetProcessHeap
0x180036bf2  mov     r8, rdi; lpMem
0x180036bf5  xor     edx, edx; dwFlags
0x180036bf7  mov     rcx, rax; hHeap
0x180036bfa  call    cs:__imp_HeapFree
0x180036c00  test    esi, esi
0x180036c02  js      loc_180036D8C
0x180036c08  mov     edi, 80070057h
0x180036c0d  mov     rcx, [rbp+28h]; this
0x180036c11  mov     r9d, edi; char *
0x180036c14  mov     r8, r14; unsigned int
0x180036c17  mov     edx, 99h; void *
0x180036c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c21  test    rbx, rbx
0x180036c24  jz      short loc_180036C3A
0x180036c26  call    cs:__imp_GetProcessHeap
0x180036c2c  mov     r8, rbx; lpMem
0x180036c2f  xor     edx, edx; dwFlags
0x180036c31  mov     rcx, rax; hHeap
0x180036c34  call    cs:__imp_HeapFree
0x180036c3a  mov     eax, edi
0x180036c3c  jmp     loc_180036DA2
0x180036c41  mov     rbx, rdi
0x180036c44  test    rdi, rdi
0x180036c47  jz      short loc_180036C08
0x180036c49  mov     edx, 7FFFFFFFh
0x180036c4e  mov     rax, rbx
0x180036c51  mov     ecx, edx
0x180036c53  cmp     [rax], r12w
0x180036c57  jz      short loc_180036C63
0x180036c59  add     rax, 2
0x180036c5d  sub     rcx, 1
0x180036c61  jnz     short loc_180036C53
0x180036c63  mov     rax, rcx
0x180036c66  neg     rax
0x180036c69  mov     rax, rcx
0x180036c6c  sbb     edi, edi
0x180036c6e  sub     rdx, rcx
0x180036c71  not     edi
0x180036c73  and     edi, 80070057h
0x180036c79  neg     rax
0x180036c7c  sbb     r8, r8
0x180036c7f  and     r8, rdx
0x180036c82  test    rcx, rcx
0x180036c85  jz      short loc_180036C0D
0x180036c87  lea     rsi, [r8+1Ch]
0x180036c8b  mov     r8, rsi
0x180036c8e  lea     rcx, [rbp+lpMem]
0x180036c92  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180036c97  mov     rdi, [rbp+lpMem]
0x180036c9b  test    rdi, rdi
0x180036c9e  jnz     short loc_180036CBB
0x180036ca0  mov     rcx, [rbp+28h]; this
0x180036ca4  mov     esi, 8007000Eh
0x180036ca9  mov     r9d, esi; char *
0x180036cac  mov     r8, r14; unsigned int
0x180036caf  mov     edx, 9Eh; void *
0x180036cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036cb9  jmp     short loc_180036D23
0x180036cbb  lea     rax, aUpdatepolicyPo; "\\UpdatePolicy\\PolicyState"
0x180036cc2  mov     r9, rbx
0x180036cc5  lea     r8, aSS; "%s\\%s"
0x180036ccc  mov     qword ptr [rsp+50h+var_30], rax; int
0x180036cd1  mov     rdx, rsi; unsigned __int64
0x180036cd4  mov     rcx, rdi; unsigned __int16 *
0x180036cd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036cdc  mov     esi, eax
0x180036cde  test    eax, eax
0x180036ce0  jns     short loc_180036CE9
0x180036ce2  mov     edx, 0A5h
0x180036ce7  jmp     short loc_180036D00
0x180036ce9  lea     r9, [rbp+var_20]; unsigned int *
0x180036ced  mov     rdx, rdi; unsigned __int16 *
0x180036cf0  call    ?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z; EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180036cf5  mov     esi, eax
0x180036cf7  test    eax, eax
0x180036cf9  jns     short loc_180036D39
0x180036cfb  mov     edx, 0ABh; void *
0x180036d00  mov     rcx, [rbp+28h]; this
0x180036d04  mov     r9d, eax; char *
0x180036d07  mov     r8, r14; unsigned int
0x180036d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d0f  call    cs:__imp_GetProcessHeap
0x180036d15  mov     r8, rdi; lpMem
0x180036d18  xor     edx, edx; dwFlags
0x180036d1a  mov     rcx, rax; hHeap
0x180036d1d  call    cs:__imp_HeapFree
0x180036d23  call    cs:__imp_GetProcessHeap
0x180036d29  mov     r8, rbx; lpMem
0x180036d2c  xor     edx, edx; dwFlags
0x180036d2e  mov     rcx, rax; hHeap
0x180036d31  call    cs:__imp_HeapFree
0x180036d37  jmp     short loc_180036DA0
0x180036d39  mov     eax, [rbp+var_20]
0x180036d3c  dec     eax
0x180036d3e  cmp     eax, 1
0x180036d41  setbe   al
0x180036d44  mov     [r15], al
0x180036d47  call    cs:__imp_GetProcessHeap
0x180036d4d  mov     r8, rdi; lpMem
0x180036d50  xor     edx, edx; dwFlags
0x180036d52  mov     rcx, rax; hHeap
0x180036d55  call    cs:__imp_HeapFree
0x180036d5b  call    cs:__imp_GetProcessHeap
0x180036d61  mov     r8, rbx; lpMem
0x180036d64  xor     edx, edx; dwFlags
0x180036d66  mov     rcx, rax; hHeap
0x180036d69  call    cs:__imp_HeapFree
0x180036d6f  xor     eax, eax
0x180036d71  jmp     short loc_180036DA2
0x180036d73  mov     esi, 8007000Eh
0x180036d78  mov     edx, 61h ; 'a'; void *
0x180036d7d  mov     rcx, [rbp+28h]; this
0x180036d81  mov     r9d, esi; char *
0x180036d84  mov     r8, r14; unsigned int
0x180036d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d8c  mov     rcx, [rbp+28h]; this
0x180036d90  mov     r9d, esi; char *
0x180036d93  mov     r8, r14; unsigned int
0x180036d96  mov     edx, 97h; void *
0x180036d9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036da0  mov     eax, esi
0x180036da2  mov     rcx, [rbp+var_8]
0x180036da6  xor     rcx, rsp; StackCookie
0x180036da9  call    __security_check_cookie
0x180036dae  lea     r11, [rsp+50h+var_s0]
0x180036db3  mov     rbx, [r11+38h]
0x180036db7  mov     rsi, [r11+40h]
0x180036dbb  mov     rsp, r11
0x180036dbe  pop     r15
0x180036dc0  pop     r14
0x180036dc2  pop     r12
0x180036dc4  pop     rdi
0x180036dc5  pop     rbp
0x180036dc6  retn
```
