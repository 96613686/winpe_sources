# GetAppDisplayInfoFromPath(winrt::hstring)

- ea: `0x180028b14`
- end: `0x180028f59`
- name: `?GetAppDisplayInfoFromPath@@YA?AUAppDisplayInfo@@Uhstring@winrt@@@Z`
- size: `1093`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(struct winrt::impl::shared_hstring_header **, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180014700`

## callees

- `0x1800021c0`
- `0x180002d55`
- `0x180002d91`
- `0x180003db5`
- `0x180007940`
- `0x18000b058`
- `0x18000bbe8`
- `0x18000f098`
- `0x1800148d0`
- `0x180014c14`
- `0x1800264d8`
- `0x180026618`
- `0x180028b14`
- `0x180029118`
- `0x18002919c`
- `0x180029358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028e37`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f3d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028e37`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f3d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180028b8a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180028bf6`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180028b8a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180028bf6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180028c26`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180028c26`
- `FirewallAPI!FwGetVersionField` at `0x180028cc7`
- `FirewallAPI!FwGetVersionField` at `0x180028cc7`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadImageW` at `0x180028dcf`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadImageW` at `0x180028dcf`
- `ext-ms-win-shell-shell32-l1-2-1!ExtractIconExW` at `0x180028d9d`
- `ext-ms-win-shell-shell32-l1-2-1!ExtractIconExW` at `0x180028d9d`

## string_xrefs

- `0x180028cc0`: `CompanyName`
- `0x180028f47`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct winrt::impl::shared_hstring_header **__fastcall GetAppDisplayInfoFromPath(
        struct winrt::impl::shared_hstring_header **a1,
        void *a2)
{
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r8
  HRESULT v6; // eax
  WCHAR *v7; // rax
  const WCHAR *v8; // r8
  HRESULT v9; // ebx
  const WCHAR *v10; // rcx
  LPWSTR FileNameW; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  LPWSTR *v14; // rdi
  __int64 v15; // rbx
  unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // rcx
  int VersionField; // ebx
  __int64 v19; // rcx
  __int64 v20; // r8
  const wchar_t *v21; // r9
  unsigned __int64 v22; // rdx
  void **v23; // rdi
  __int64 v24; // rbx
  void *v25; // rbx
  int v26; // eax
  HANDLE ProcessHeap; // rax
  UINT v28; // eax
  void *v29; // rdx
  unsigned int v30; // r8d
  const char *v31; // r9
  void *v32; // rdx
  unsigned int v33; // r8d
  const char *v34; // r9
  const void **v35; // rbx
  char **v36; // rax
  unsigned int v37; // edx
  char **v38; // rdi
  char *v39; // r12
  __int64 v40; // r15
  struct winrt::impl::shared_hstring_header *v41; // rsi
  const void *v42; // r12
  __int64 v43; // rsi
  struct winrt::impl::shared_hstring_header *v44; // r15
  volatile signed __int32 *v45; // rbx
  int v46; // eax
  HANDLE v47; // rax
  int pszOut; // [rsp+20h] [rbp-B9h]
  DWORD pcchOut; // [rsp+30h] [rbp-A9h] BYREF
  HICON phiconLarge; // [rsp+38h] [rbp-A1h] BYREF
  LPVOID lpMem[7]; // [rsp+40h] [rbp-99h] BYREF
  _BYTE v53[32]; // [rsp+78h] [rbp-61h] BYREF
  char v54[32]; // [rsp+98h] [rbp-41h] BYREF
  void *v55[2]; // [rsp+B8h] [rbp-21h] BYREF
  unsigned __int64 v56; // [rsp+C8h] [rbp-11h]
  unsigned __int64 v57; // [rsp+D0h] [rbp-9h]
  LPWSTR Src[2]; // [rsp+D8h] [rbp-1h] BYREF
  unsigned __int64 v59; // [rsp+E8h] [rbp+Fh]
  unsigned __int64 v60; // [rsp+F0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  lpMem[3] = a1;
  lpMem[4] = a2;
  pcchOut = 0;
  v4 = &szFile;
  if ( *(_QWORD *)a2 )
    v5 = *(const WCHAR **)(*(_QWORD *)a2 + 16LL);
  else
    v5 = &szFile;
  v6 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, v5, 0, 0, &pcchOut);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x20,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v6,
      pszOut);
  *(_OWORD *)Src = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(Src[0]) = 0;
  std::wstring::resize(Src);
  v7 = (WCHAR *)Src;
  if ( v60 > 7 )
    v7 = Src[0];
  if ( *(_QWORD *)a2 )
    v8 = *(const WCHAR **)(*(_QWORD *)a2 + 16LL);
  else
    v8 = &szFile;
  v9 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, v8, 0, v7, &pcchOut);
  TrimString(Src);
  if ( v9 < 0 || !v59 )
  {
    if ( *(_QWORD *)a2 )
      v10 = *(const WCHAR **)(*(_QWORD *)a2 + 16LL);
    else
      v10 = &szFile;
    FileNameW = PathFindFileNameW(v10);
    v13 = -1;
    do
      ++v13;
    while ( FileNameW[v13] );
    if ( v13 > v60 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        Src,
        v13,
        v12,
        FileNameW);
    }
    else
    {
      v14 = Src;
      if ( v60 > 7 )
        v14 = (LPWSTR *)Src[0];
      v59 = v13;
      v15 = 2 * v13;
      memmove_0(v14, FileNameW, 2 * v13);
      *(_WORD *)((char *)v14 + v15) = 0;
    }
  }
  *(_OWORD *)v55 = 0;
  v56 = 0;
  v57 = 7;
  LOWORD(v55[0]) = 0;
  std::wstring::resize(v55);
  v16 = (unsigned __int16 *)v55;
  if ( v57 > 7 )
    v16 = (unsigned __int16 *)v55[0];
  if ( *(_QWORD *)a2 )
    v17 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  else
    v17 = &szFile;
  VersionField = FwGetVersionField(v17, L"CompanyName", v16, 0x104u);
  TrimString(v55);
  if ( VersionField < 0 || !v56 )
  {
    v19 = *(_QWORD *)GetResourceString(lpMem, 60);
    if ( v19 )
    {
      v21 = *(const wchar_t **)(v19 + 16);
      v22 = *(unsigned int *)(v19 + 4);
    }
    else
    {
      v21 = &szFile;
      v22 = 0;
    }
    if ( v22 > v57 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v55,
        v22,
        v20,
        v21);
    }
    else
    {
      v23 = v55;
      if ( v57 > 7 )
        v23 = (void **)v55[0];
      v56 = v22;
      v24 = 2 * v22;
      memmove_0(v23, v21, 2 * v22);
      *(_WORD *)((char *)v23 + v24) = 0;
    }
    v25 = lpMem[0];
    if ( lpMem[0] )
    {
      v26 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v26 )
      {
        if ( v26 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v25);
      }
    }
  }
  phiconLarge = 0;
  if ( *(_QWORD *)a2 )
    v4 = *(const WCHAR **)(*(_QWORD *)a2 + 16LL);
  v28 = ExtractIconExW(v4, 0, &phiconLarge, 0, 1u);
  if ( v28 != 1 )
  {
    if ( v28 == -1 )
      wil::details::in1diag3::Log_GetLastError(retaddr, v29, v30, v31);
    phiconLarge = (HICON)LoadImageW(0, (LPCWSTR)0x7F00, 1u, 0, 0, 0x8040u);
    if ( !phiconLarge )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v32, v33, v34);
  }
  lpMem[0] = phiconLarge;
  lpMem[5] = v53;
  v35 = (const void **)std::wstring::wstring(v53, v55);
  lpMem[6] = v35;
  v36 = (char **)std::wstring::wstring(v54, Src);
  v38 = v36;
  lpMem[2] = v36;
  if ( (unsigned __int64)v36[3] <= 7 )
    v39 = (char *)v36;
  else
    v39 = *v36;
  v40 = *((unsigned int *)v36 + 4);
  if ( (_DWORD)v40 )
  {
    v41 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v40, v37);
    memcpy_s((char *)v41 + 28, 2 * v40, v39, 2 * v40);
  }
  else
  {
    v41 = 0;
  }
  *a1 = v41;
  if ( (unsigned __int64)v35[3] <= 7 )
    v42 = v35;
  else
    v42 = *v35;
  v43 = *((unsigned int *)v35 + 4);
  if ( (_DWORD)v43 )
  {
    v44 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v43, v37);
    memcpy_s((char *)v44 + 28, 2 * v43, v42, 2 * v43);
  }
  else
  {
    v44 = 0;
  }
  a1[1] = v44;
  a1[2] = (struct winrt::impl::shared_hstring_header *)lpMem[0];
  std::wstring::~wstring(v38);
  std::wstring::~wstring((char **)v35);
  std::wstring::~wstring((char **)v55);
  std::wstring::~wstring((char **)Src);
  v45 = *(volatile signed __int32 **)a2;
  if ( *(_QWORD *)a2 )
  {
    v46 = _InterlockedDecrement(v45 + 6);
    if ( v46 )
    {
      if ( v46 < 0 )
        abort();
    }
    else
    {
      v47 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v47, 0, (LPVOID)v45);
    }
    *(_QWORD *)a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180028b14  mov     [rsp-8+arg_10], rbx
0x180028b19  push    rbp
0x180028b1a  push    rsi
0x180028b1b  push    rdi
0x180028b1c  push    r12
0x180028b1e  push    r13
0x180028b20  push    r14
0x180028b22  push    r15
0x180028b24  lea     rbp, [rsp-27h]
0x180028b29  sub     rsp, 100h
0x180028b30  mov     rax, cs:__security_cookie
0x180028b37  xor     rax, rsp
0x180028b3a  mov     [rbp+57h+var_38], rax
0x180028b3e  mov     r14, rdx
0x180028b41  mov     r13, rcx
0x180028b44  mov     [rsp+130h+var_D8], rcx
0x180028b49  mov     [rbp+57h+var_D0], rdx
0x180028b4d  xor     r12d, r12d
0x180028b50  mov     [rsp+130h+var_100], r12d
0x180028b55  mov     rax, [rdx]
0x180028b58  lea     rsi, szFile
0x180028b5f  test    rax, rax
0x180028b62  jz      short loc_180028B6A
0x180028b64  mov     r8, [rax+10h]
0x180028b68  jmp     short loc_180028B6D
0x180028b6a  mov     r8, rsi; pszAssoc
0x180028b6d  lea     rax, [rsp+130h+var_100]
0x180028b72  mov     [rsp+130h+pcchOut], rax; pcchOut
0x180028b77  mov     [rsp+130h+pszOut], r12; int
0x180028b7c  xor     r9d, r9d; pszExtra
0x180028b7f  lea     ebx, [r9+4]
0x180028b83  mov     edx, ebx; str
0x180028b85  lea     edi, [rbx-2]
0x180028b88  mov     ecx, edi; flags
0x180028b8a  call    cs:__imp_AssocQueryStringW
0x180028b90  mov     rcx, [rbp+5Fh]; this
0x180028b94  test    eax, eax
0x180028b96  js      loc_180028F44
0x180028b9c  xorps   xmm0, xmm0
0x180028b9f  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180028ba3  mov     [rbp+57h+var_48], r12
0x180028ba7  mov     [rbp+57h+var_40], 7
0x180028baf  mov     word ptr [rbp+57h+Src], r12w
0x180028bb4  mov     edx, [rsp+130h+var_100]
0x180028bb8  lea     rcx, [rbp+57h+Src]; Src
0x180028bbc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180028bc1  lea     rax, [rbp+57h+Src]
0x180028bc5  cmp     [rbp+57h+var_40], 7
0x180028bca  cmova   rax, [rbp+57h+Src]
0x180028bcf  mov     r8, [r14]
0x180028bd2  test    r8, r8
0x180028bd5  jz      short loc_180028BDD
0x180028bd7  mov     r8, [r8+10h]
0x180028bdb  jmp     short loc_180028BE0
0x180028bdd  mov     r8, rsi; pszAssoc
0x180028be0  lea     r9, [rsp+130h+var_100]
0x180028be5  mov     [rsp+130h+pcchOut], r9; pcchOut
0x180028bea  mov     [rsp+130h+pszOut], rax; pszOut
0x180028bef  xor     r9d, r9d; pszExtra
0x180028bf2  mov     edx, ebx; str
0x180028bf4  mov     ecx, edi; flags
0x180028bf6  call    cs:__imp_AssocQueryStringW
0x180028bfc  mov     ebx, eax
0x180028bfe  lea     rcx, [rbp+57h+Src]
0x180028c02  call    ?TrimString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrimString(std::wstring &)
0x180028c07  or      r15, 0FFFFFFFFFFFFFFFFh
0x180028c0b  test    ebx, ebx
0x180028c0d  js      short loc_180028C15
0x180028c0f  cmp     [rbp+57h+var_48], r12
0x180028c13  jnz     short loc_180028C76
0x180028c15  mov     rax, [r14]
0x180028c18  test    rax, rax
0x180028c1b  jz      short loc_180028C23
0x180028c1d  mov     rcx, [rax+10h]
0x180028c21  jmp     short loc_180028C26
0x180028c23  mov     rcx, rsi; pszPath
0x180028c26  call    cs:__imp_PathFindFileNameW
0x180028c2c  mov     rdx, r15
0x180028c2f  inc     rdx
0x180028c32  cmp     [rax+rdx*2], r12w
0x180028c37  jnz     short loc_180028C2F
0x180028c39  cmp     rdx, [rbp+57h+var_40]
0x180028c3d  ja      short loc_180028C6A
0x180028c3f  lea     rdi, [rbp+57h+Src]
0x180028c43  cmp     [rbp+57h+var_40], 7
0x180028c48  cmova   rdi, [rbp+57h+Src]
0x180028c4d  mov     [rbp+57h+var_48], rdx
0x180028c51  lea     rbx, [rdx+rdx]
0x180028c55  mov     r8, rbx; Size
0x180028c58  mov     rdx, rax; Src
0x180028c5b  mov     rcx, rdi; void *
0x180028c5e  call    memmove_0
0x180028c63  mov     [rdi+rbx], r12w
0x180028c68  jmp     short loc_180028C76
0x180028c6a  mov     r9, rax
0x180028c6d  lea     rcx, [rbp+57h+Src]
0x180028c71  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180028c76  xorps   xmm0, xmm0
0x180028c79  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180028c7d  mov     [rbp+57h+var_68], r12
0x180028c81  mov     [rbp+57h+var_60], 7
0x180028c89  mov     word ptr [rbp+57h+var_78], r12w
0x180028c8e  mov     ebx, 104h
0x180028c93  mov     edx, ebx
0x180028c95  lea     rcx, [rbp+57h+var_78]; Src
0x180028c99  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180028c9e  lea     r8, [rbp+57h+var_78]
0x180028ca2  cmp     [rbp+57h+var_60], 7
0x180028ca7  cmova   r8, [rbp+57h+var_78]
0x180028cac  mov     rcx, [r14]
0x180028caf  test    rcx, rcx
0x180028cb2  jz      short loc_180028CBA
0x180028cb4  mov     rcx, [rcx+10h]
0x180028cb8  jmp     short loc_180028CBD
0x180028cba  mov     rcx, rsi
0x180028cbd  mov     r9d, ebx
0x180028cc0  lea     rdx, aCompanyname; "CompanyName"
0x180028cc7  call    cs:__imp_?FwGetVersionField@@YAJPEBG0PEAGI@Z; FwGetVersionField(ushort const *,ushort const *,ushort *,uint)
0x180028ccd  mov     ebx, eax
0x180028ccf  lea     rcx, [rbp+57h+var_78]
0x180028cd3  call    ?TrimString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrimString(std::wstring &)
0x180028cd8  test    ebx, ebx
0x180028cda  js      short loc_180028CE6
0x180028cdc  cmp     [rbp+57h+var_68], r12
0x180028ce0  jnz     loc_180028D76
0x180028ce6  mov     edx, 3Ch ; '<'
0x180028ceb  lea     rcx, [rsp+130h+lpMem]
0x180028cf0  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180028cf5  nop
0x180028cf6  mov     rcx, [rax]
0x180028cf9  test    rcx, rcx
0x180028cfc  jz      short loc_180028D07
0x180028cfe  mov     r9, [rcx+10h]
0x180028d02  mov     edx, [rcx+4]
0x180028d05  jmp     short loc_180028D0D
0x180028d07  mov     r9, rsi
0x180028d0a  mov     rdx, r12
0x180028d0d  cmp     rdx, [rbp+57h+var_60]
0x180028d11  ja      short loc_180028D3E
0x180028d13  lea     rdi, [rbp+57h+var_78]
0x180028d17  cmp     [rbp+57h+var_60], 7
0x180028d1c  cmova   rdi, [rbp+57h+var_78]
0x180028d21  mov     [rbp+57h+var_68], rdx
0x180028d25  lea     rbx, [rdx+rdx]
0x180028d29  mov     r8, rbx; Size
0x180028d2c  mov     rdx, r9; Src
0x180028d2f  mov     rcx, rdi; void *
0x180028d32  call    memmove_0
0x180028d37  mov     [rdi+rbx], r12w
0x180028d3c  jmp     short loc_180028D48
0x180028d3e  lea     rcx, [rbp+57h+var_78]
0x180028d42  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180028d47  nop
0x180028d48  mov     rbx, [rsp+130h+lpMem]
0x180028d4d  test    rbx, rbx
0x180028d50  jz      short loc_180028D76
0x180028d52  mov     eax, r15d
0x180028d55  lock xadd [rbx+18h], eax
0x180028d5a  sub     eax, 1
0x180028d5d  jnz     loc_180028E2F
0x180028d63  nop
0x180028d64  call    WINRT_IMPL_GetProcessHeap
0x180028d69  mov     rcx, rax; hHeap
0x180028d6c  mov     r8, rbx; lpMem
0x180028d6f  xor     edx, edx; dwFlags
0x180028d71  call    WINRT_IMPL_HeapFree
0x180028d76  mov     [rsp+130h+phiconLarge], r12
0x180028d7b  mov     rax, [r14]
0x180028d7e  test    rax, rax
0x180028d81  jz      short loc_180028D87
0x180028d83  mov     rsi, [rax+10h]
0x180028d87  mov     ebx, 1
0x180028d8c  mov     dword ptr [rsp+130h+pszOut], ebx; nIcons
0x180028d90  xor     r9d, r9d; phiconSmall
0x180028d93  lea     r8, [rsp+130h+phiconLarge]; phiconLarge
0x180028d98  xor     edx, edx; nIconIndex
0x180028d9a  mov     rcx, rsi; lpszFile
0x180028d9d  call    cs:__imp_ExtractIconExW
0x180028da3  cmp     eax, ebx
0x180028da5  jz      short loc_180028DE8
0x180028da7  cmp     eax, 0FFFFFFFFh
0x180028daa  jnz     short loc_180028DB5
0x180028dac  mov     rcx, [rbp+5Fh]; this
0x180028db0  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180028db5  mov     dword ptr [rsp+130h+pcchOut], 8040h; fuLoad
0x180028dbd  mov     dword ptr [rsp+130h+pszOut], r12d; cy
0x180028dc2  xor     r9d, r9d; cx
0x180028dc5  mov     r8d, ebx; type
0x180028dc8  mov     edx, 7F00h; name
0x180028dcd  xor     ecx, ecx; hInst
0x180028dcf  call    cs:__imp_LoadImageW
0x180028dd5  mov     [rsp+130h+phiconLarge], rax
0x180028dda  mov     rcx, [rbp+5Fh]; this
0x180028dde  test    rax, rax
0x180028de1  jnz     short loc_180028DE8
0x180028de3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180028de8  mov     rax, [rsp+130h+phiconLarge]
0x180028ded  mov     [rsp+130h+lpMem], rax
0x180028df2  lea     rcx, [rbp+57h+var_B8]
0x180028df6  mov     [rbp+57h+var_C8], rcx
0x180028dfa  lea     rdx, [rbp+57h+var_78]
0x180028dfe  lea     rcx, [rbp+57h+var_B8]
0x180028e02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028e07  mov     rbx, rax
0x180028e0a  mov     [rbp+57h+var_C0], rax
0x180028e0e  lea     rdx, [rbp+57h+Src]
0x180028e12  lea     rcx, [rbp+57h+var_98]
0x180028e16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028e1b  mov     rdi, rax
0x180028e1e  mov     [rsp+130h+var_E0], rax
0x180028e23  cmp     qword ptr [rax+18h], 7
0x180028e28  jbe     short loc_180028E3E
0x180028e2a  mov     r12, [rax]
0x180028e2d  jmp     short loc_180028E41
0x180028e2f  test    eax, eax
0x180028e31  jns     loc_180028D76
0x180028e37  call    cs:__imp_abort
0x180028e3e  mov     r12, rdi
0x180028e41  mov     r15d, [rax+10h]
0x180028e45  test    r15d, r15d
0x180028e48  jnz     short loc_180028E4E
0x180028e4a  xor     esi, esi
0x180028e4c  jmp     short loc_180028E6E
0x180028e4e  mov     ecx, r15d; this
0x180028e51  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180028e56  mov     rsi, rax
0x180028e59  mov     rdx, r15
0x180028e5c  add     rdx, rdx; DestinationSize
0x180028e5f  lea     rcx, [rax+1Ch]; Destination
0x180028e63  mov     r9, rdx; SourceSize
0x180028e66  mov     r8, r12; Source
0x180028e69  call    memcpy_s
0x180028e6e  mov     [r13+0], rsi
0x180028e72  cmp     qword ptr [rbx+18h], 7
0x180028e77  jbe     short loc_180028E7E
0x180028e79  mov     r12, [rbx]
0x180028e7c  jmp     short loc_180028E81
0x180028e7e  mov     r12, rbx
0x180028e81  mov     esi, [rbx+10h]
0x180028e84  test    esi, esi
0x180028e86  jnz     short loc_180028E8D
0x180028e88  xor     r15d, r15d
0x180028e8b  jmp     short loc_180028EAC
0x180028e8d  mov     ecx, esi; this
0x180028e8f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180028e94  mov     r15, rax
0x180028e97  mov     rdx, rsi
0x180028e9a  add     rdx, rdx; DestinationSize
0x180028e9d  lea     rcx, [rax+1Ch]; Destination
0x180028ea1  mov     r9, rdx; SourceSize
0x180028ea4  mov     r8, r12; Source
0x180028ea7  call    memcpy_s
0x180028eac  mov     [r13+8], r15
0x180028eb0  mov     rax, [rsp+130h+lpMem]
0x180028eb5  mov     [r13+10h], rax
0x180028eb9  mov     rcx, rdi
0x180028ebc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028ec1  nop
0x180028ec2  mov     rcx, rbx
0x180028ec5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028eca  nop
0x180028ecb  lea     rcx, [rbp+57h+var_78]
0x180028ecf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028ed4  nop
0x180028ed5  lea     rcx, [rbp+57h+Src]
0x180028ed9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028ede  nop
0x180028edf  mov     rbx, [r14]
0x180028ee2  test    rbx, rbx
0x180028ee5  jz      short loc_180028F0F
0x180028ee7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028eeb  lock xadd [rbx+18h], eax
0x180028ef0  sub     eax, 1
0x180028ef3  jnz     short loc_180028F39
0x180028ef5  nop
0x180028ef6  call    WINRT_IMPL_GetProcessHeap
0x180028efb  mov     rcx, rax; hHeap
0x180028efe  mov     r8, rbx; lpMem
0x180028f01  xor     edx, edx; dwFlags
0x180028f03  call    WINRT_IMPL_HeapFree
0x180028f08  mov     qword ptr [r14], 0
0x180028f0f  mov     rax, r13
0x180028f12  mov     rcx, [rbp+57h+var_38]
0x180028f16  xor     rcx, rsp; StackCookie
0x180028f19  call    __security_check_cookie
0x180028f1e  mov     rbx, [rsp+130h+arg_10]
0x180028f26  add     rsp, 100h
0x180028f2d  pop     r15
0x180028f2f  pop     r14
0x180028f31  pop     r13
0x180028f33  pop     r12
0x180028f35  pop     rdi
0x180028f36  pop     rsi
0x180028f37  pop     rbp
0x180028f38  retn
0x180028f39  test    eax, eax
0x180028f3b  jns     short loc_180028F08
0x180028f3d  call    cs:__imp_abort
0x180028f44  mov     r9d, eax; char *
0x180028f47  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
  ... truncated ...
```
