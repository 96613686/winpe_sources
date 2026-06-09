# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppCompatInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180074170`
- end: `0x180074717`
- name: `??$make_cloud_store_reference_vector@UAppCompatInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UAppCompatInfo@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppCompatInfo@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1447`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180072e64`

## callees

- `0x180008570`
- `0x180072098`
- `0x180072464`
- `0x1800726b4`
- `0x180073b78`
- `0x180074170`
- `0x180076ddc`
- `0x1800948e8`
- `0x1802174f0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180074320`
- `KERNEL32!CompareStringOrdinal` at `0x180074320`
- `KERNEL32!GetLastError` at `0x1800742d4`
- `KERNEL32!GetLastError` at `0x1800743e2`
- `KERNEL32!GetLastError` at `0x180074451`
- `KERNEL32!GetLastError` at `0x1800742d4`
- `KERNEL32!GetLastError` at `0x1800743e2`
- `KERNEL32!GetLastError` at `0x180074451`
- `KERNEL32!SetLastError` at `0x1800742e7`
- `KERNEL32!SetLastError` at `0x1800743f5`
- `KERNEL32!SetLastError` at `0x180074464`
- `KERNEL32!SetLastError` at `0x1800742e7`
- `KERNEL32!SetLastError` at `0x1800743f5`
- `KERNEL32!SetLastError` at `0x180074464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800742df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800743ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007463a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800742df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800743ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007463a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800744a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800744f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800744a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800744f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppCompatInfo>(
        _QWORD *a1,
        __int64 *a2)
{
  int v4; // eax
  int v5; // ecx
  unsigned int v6; // r12d
  __int64 v7; // rax
  int v8; // eax
  HSTRING v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  HSTRING v12; // r15
  HSTRING v13; // r14
  DWORD LastError; // ebx
  const WCHAR *v15; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v17; // rax
  int v18; // eax
  HSTRING v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  HSTRING v22; // r15
  HSTRING v23; // r14
  DWORD v24; // ebx
  __int64 v25; // rax
  int v26; // eax
  HSTRING v27; // r15
  HSTRING v28; // r14
  DWORD v29; // ebx
  PCWSTR v30; // rax
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  void **v33; // rdi
  __int64 v34; // rbx
  PCWSTR v35; // rax
  __int64 v36; // r8
  unsigned __int64 v37; // rdx
  void **v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rdx
  int v42; // [rsp+28h] [rbp-B9h]
  HSTRING v43; // [rsp+40h] [rbp-A1h] BYREF
  int v44; // [rsp+48h] [rbp-99h]
  __int64 v45; // [rsp+50h] [rbp-91h] BYREF
  HSTRING v46; // [rsp+58h] [rbp-89h]
  HSTRING v47; // [rsp+60h] [rbp-81h] BYREF
  int v48; // [rsp+68h] [rbp-79h]
  HSTRING string; // [rsp+70h] [rbp-71h]
  HSTRING v50; // [rsp+78h] [rbp-69h]
  HSTRING v51; // [rsp+80h] [rbp-61h]
  __int64 v52; // [rsp+88h] [rbp-59h]
  _QWORD *v53; // [rsp+90h] [rbp-51h]
  void *v54[2]; // [rsp+98h] [rbp-49h] BYREF
  unsigned __int64 v55; // [rsp+A8h] [rbp-39h]
  unsigned __int64 v56; // [rsp+B0h] [rbp-31h]
  void *v57[2]; // [rsp+B8h] [rbp-29h] BYREF
  unsigned __int64 v58; // [rsp+C8h] [rbp-19h]
  unsigned __int64 v59; // [rsp+D0h] [rbp-11h]
  LPCWCH lpString2[4]; // [rsp+D8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v52 = -2;
  v53 = a1;
  v48 = 0;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppCompatInfo>(lpString2);
  LODWORD(v45) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 56))(a2, &v45);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      v42);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v48 = 1;
  v5 = v45;
  v47 = (HSTRING)(unsigned int)v45;
  if ( (_DWORD)v45 )
  {
    std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(a1, &v47);
    v5 = v45;
  }
  v6 = 0;
  if ( v5 )
  {
    do
    {
      v46 = 0;
      v7 = *a2;
      v43 = 0;
      LOBYTE(v44) = 1;
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v7 + 48))(a2, v6, &v43);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x565,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v8,
          v42);
      if ( (_BYTE)v44 )
      {
        v9 = v46;
        v46 = v43;
        if ( v9 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v47 = 0;
      v10 = *(_QWORD *)v46;
      v43 = 0;
      LOBYTE(v44) = 1;
      v11 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v10 + 64))(v46, &v43);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x568,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v11,
          v42);
      if ( (_BYTE)v44 )
      {
        v12 = v43;
        v13 = v47;
        if ( v47 )
        {
          LastError = GetLastError();
          WindowsDeleteString(v13);
          SetLastError(LastError);
        }
        v47 = v12;
      }
      v15 = (const WCHAR *)lpString2;
      if ( lpString2[3] > (LPCWCH)7 )
        v15 = lpString2[0];
      StringRawBuffer = WindowsGetStringRawBuffer(v47, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v15, -1, 1) == 2 )
      {
        v51 = 0;
        v17 = *(_QWORD *)v46;
        v43 = 0;
        LOBYTE(v44) = 1;
        v18 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v17 + 48))(v46, &v43);
        if ( v18 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x56C,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v18,
            v42);
        if ( (_BYTE)v44 )
        {
          v19 = v51;
          v51 = v43;
          if ( v19 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v50 = 0;
        v20 = *(_QWORD *)v51;
        v43 = 0;
        LOBYTE(v44) = 1;
        v21 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v20 + 48))(v51, &v43);
        if ( v21 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v21,
            v42);
        if ( (_BYTE)v44 )
        {
          v22 = v43;
          v23 = v50;
          if ( v50 )
          {
            v24 = GetLastError();
            WindowsDeleteString(v23);
            SetLastError(v24);
          }
          v50 = v22;
        }
        string = 0;
        v25 = *(_QWORD *)v46;
        v43 = 0;
        LOBYTE(v44) = 1;
        v26 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v25 + 56))(v46, &v43);
        if ( v26 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x572,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v26,
            v42);
        if ( (_BYTE)v44 )
        {
          v27 = v43;
          v28 = string;
          if ( string )
          {
            v29 = GetLastError();
            WindowsDeleteString(v28);
            SetLastError(v29);
          }
          string = v27;
        }
        *(_OWORD *)v54 = 0;
        v55 = 0;
        v56 = 7;
        LOWORD(v54[0]) = 0;
        *(_OWORD *)v57 = 0;
        v58 = 0;
        v59 = 7;
        LOWORD(v57[0]) = 0;
        v30 = WindowsGetStringRawBuffer(string, 0);
        v32 = -1;
        do
          ++v32;
        while ( v30[v32] );
        if ( v32 > v56 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v54,
            v32,
            v31,
            v30);
        }
        else
        {
          v33 = v54;
          if ( v56 > 7 )
            v33 = (void **)v54[0];
          v55 = v32;
          v34 = 2 * v32;
          memmove_0(v33, v30, 2 * v32);
          *(_WORD *)((char *)v33 + v34) = 0;
        }
        v35 = WindowsGetStringRawBuffer(v50, 0);
        v37 = -1;
        do
          ++v37;
        while ( v35[v37] );
        if ( v37 > v59 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v57,
            v37,
            v36,
            v35);
        }
        else
        {
          v38 = v57;
          if ( v59 > 7 )
            v38 = (void **)v57[0];
          v58 = v37;
          v39 = 2 * v37;
          memmove_0(v38, v35, 2 * v37);
          *(_WORD *)((char *)v38 + v39) = 0;
        }
        v40 = a1[1];
        if ( v40 == a1[2] )
        {
          std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(
            a1,
            v40,
            v54);
        }
        else
        {
          *(_OWORD *)v40 = 0;
          *(_QWORD *)(v40 + 16) = 0;
          *(_QWORD *)(v40 + 24) = 0;
          *(void **)v40 = v54[0];
          *(void **)(v40 + 8) = v54[1];
          *(_QWORD *)(v40 + 16) = v55;
          *(_QWORD *)(v40 + 24) = v56;
          v55 = 0;
          v56 = 7;
          LOWORD(v54[0]) = 0;
          *(_OWORD *)(v40 + 32) = 0;
          *(_QWORD *)(v40 + 48) = 0;
          *(_QWORD *)(v40 + 56) = 0;
          *(void **)(v40 + 32) = v57[0];
          *(void **)(v40 + 40) = v57[1];
          *(_QWORD *)(v40 + 48) = v58;
          *(_QWORD *)(v40 + 56) = v59;
          v58 = 0;
          v59 = 7;
          LOWORD(v57[0]) = 0;
          a1[1] += 64LL;
        }
        std::wstring::~wstring(v57);
        std::wstring::~wstring(v54);
        if ( string )
          WindowsDeleteString(string);
        if ( v50 )
          WindowsDeleteString(v50);
        if ( v51 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v51 + 16LL))(v51);
      }
      if ( v47 )
        WindowsDeleteString(v47);
      if ( v46 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v46 + 16LL))(v46);
      ++v6;
    }
    while ( v6 < (unsigned int)v45 );
  }
  std::wstring::~wstring(lpString2);
  return a1;
}

```

## disassembly

```asm
0x180074170  mov     rax, rsp
0x180074173  push    rbp
0x180074174  push    rsi
0x180074175  push    rdi
0x180074176  push    r12
0x180074178  push    r13
0x18007417a  push    r14
0x18007417c  push    r15
0x18007417e  lea     rbp, [rax-5Fh]
0x180074182  sub     rsp, 100h
0x180074189  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x180074191  mov     [rax+18h], rbx
0x180074195  mov     rax, cs:__security_cookie
0x18007419c  xor     rax, rsp
0x18007419f  mov     [rbp+57h+var_40], rax
0x1800741a3  mov     r13, rdx
0x1800741a6  mov     rsi, rcx
0x1800741a9  mov     [rbp+57h+var_A8], rcx
0x1800741ad  xor     ebx, ebx
0x1800741af  mov     [rbp+57h+var_D0], ebx
0x1800741b2  lea     rcx, [rbp+57h+lpString2]
0x1800741b6  call    ??$get_type_name_wide_string@UAppCompatInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppCompatInfo>(void)
0x1800741bb  nop
0x1800741bc  mov     dword ptr [rsp+130h+var_E8], ebx
0x1800741c0  mov     rax, [r13+0]
0x1800741c4  lea     rdx, [rsp+130h+var_E8]
0x1800741c9  mov     rcx, r13
0x1800741cc  mov     rax, [rax+38h]
0x1800741d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800741d5  mov     rcx, [rbp+5Fh]; this
0x1800741d9  test    eax, eax
0x1800741db  js      loc_1800746C3
0x1800741e1  mov     [rsi], rbx
0x1800741e4  mov     [rsi+8], rbx
0x1800741e8  mov     [rsi+10h], rbx
0x1800741ec  mov     [rbp+57h+var_D0], 1
0x1800741f3  mov     ecx, dword ptr [rsp+130h+var_E8]
0x1800741f7  mov     [rsp+130h+var_D8], rcx
0x1800741fc  test    ecx, ecx
0x1800741fe  jz      short loc_180074211
0x180074200  lea     rdx, [rsp+130h+var_D8]
0x180074205  mov     rcx, rsi
0x180074208  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(unsigned __int64 &)
0x18007420d  mov     ecx, dword ptr [rsp+130h+var_E8]
0x180074211  mov     r12d, ebx
0x180074214  test    ecx, ecx
0x180074216  jz      loc_180074666
0x18007421c  mov     [rsp+130h+var_E0], rbx
0x180074221  mov     rax, [r13+0]
0x180074225  lea     rcx, [rsp+130h+var_E0]
0x18007422a  mov     [rsp+130h+var_100], rcx
0x18007422f  mov     [rsp+130h+var_F8], rbx
0x180074234  mov     byte ptr [rsp+130h+var_F0], 1
0x180074239  lea     r8, [rsp+130h+var_F8]
0x18007423e  mov     edx, r12d
0x180074241  mov     rcx, r13
0x180074244  mov     rax, [rax+30h]
0x180074248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007424d  mov     rcx, [rbp+5Fh]; this
0x180074251  test    eax, eax
0x180074253  js      loc_1800746AE
0x180074259  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007425d  jz      short loc_180074281
0x18007425f  mov     rdx, [rsp+130h+var_F8]
0x180074264  mov     rax, [rsp+130h+var_100]
0x180074269  mov     rcx, [rax]
0x18007426c  mov     [rax], rdx
0x18007426f  test    rcx, rcx
0x180074272  jz      short loc_180074281
0x180074274  mov     rax, [rcx]
0x180074277  mov     rax, [rax+10h]
0x18007427b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074280  nop
0x180074281  mov     [rsp+130h+var_D8], rbx
0x180074286  mov     rcx, [rsp+130h+var_E0]
0x18007428b  mov     rax, [rcx]
0x18007428e  lea     rdx, [rsp+130h+var_D8]
0x180074293  mov     [rsp+130h+var_100], rdx
0x180074298  mov     [rsp+130h+var_F8], rbx
0x18007429d  mov     byte ptr [rsp+130h+var_F0], 1
0x1800742a2  lea     rdx, [rsp+130h+var_F8]
0x1800742a7  mov     rax, [rax+40h]
0x1800742ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742b0  mov     rcx, [rbp+5Fh]; this
0x1800742b4  test    eax, eax
0x1800742b6  js      loc_180074699
0x1800742bc  cmp     byte ptr [rsp+130h+var_F0], bl
0x1800742c0  jz      short loc_1800742F0
0x1800742c2  mov     r15, [rsp+130h+var_F8]
0x1800742c7  mov     rdi, [rsp+130h+var_100]
0x1800742cc  mov     r14, [rdi]
0x1800742cf  test    r14, r14
0x1800742d2  jz      short loc_1800742ED
0x1800742d4  call    cs:__imp_GetLastError
0x1800742da  mov     ebx, eax
0x1800742dc  mov     rcx, r14; string
0x1800742df  call    cs:__imp_WindowsDeleteString
0x1800742e5  mov     ecx, ebx; dwErrCode
0x1800742e7  call    cs:__imp_SetLastError
0x1800742ed  mov     [rdi], r15
0x1800742f0  lea     rbx, [rbp+57h+lpString2]
0x1800742f4  cmp     [rbp+57h+var_48], 7
0x1800742f9  cmova   rbx, [rbp+57h+lpString2]
0x1800742fe  xor     edx, edx; length
0x180074300  mov     rcx, [rsp+130h+var_D8]; string
0x180074305  call    cs:__imp_WindowsGetStringRawBuffer
0x18007430b  mov     dword ptr [rsp+20h], 1; int
0x180074313  or      r9d, 0FFFFFFFFh; cchCount2
0x180074317  mov     r8, rbx; lpString2
0x18007431a  or      edx, r9d; cchCount1
0x18007431d  mov     rcx, rax; lpString1
0x180074320  call    cs:__imp_CompareStringOrdinal
0x180074326  xor     ebx, ebx
0x180074328  cmp     eax, 2
0x18007432b  jnz     loc_180074630
0x180074331  mov     [rbp+57h+var_B8], rbx
0x180074335  mov     rcx, [rsp+130h+var_E0]
0x18007433a  mov     rax, [rcx]
0x18007433d  lea     rdx, [rbp+57h+var_B8]
0x180074341  mov     [rsp+130h+var_100], rdx
0x180074346  mov     [rsp+130h+var_F8], rbx
0x18007434b  mov     byte ptr [rsp+130h+var_F0], 1
0x180074350  lea     rdx, [rsp+130h+var_F8]
0x180074355  mov     rax, [rax+30h]
0x180074359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007435e  mov     rcx, [rbp+5Fh]; this
0x180074362  test    eax, eax
0x180074364  js      loc_180074702
0x18007436a  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007436e  jz      short loc_180074392
0x180074370  mov     rdx, [rsp+130h+var_F8]
0x180074375  mov     rax, [rsp+130h+var_100]
0x18007437a  mov     rcx, [rax]
0x18007437d  mov     [rax], rdx
0x180074380  test    rcx, rcx
0x180074383  jz      short loc_180074392
0x180074385  mov     rax, [rcx]
0x180074388  mov     rax, [rax+10h]
0x18007438c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074391  nop
0x180074392  mov     [rbp+57h+var_C0], rbx
0x180074396  mov     rcx, [rbp+57h+var_B8]
0x18007439a  mov     rax, [rcx]
0x18007439d  lea     rdx, [rbp+57h+var_C0]
0x1800743a1  mov     [rsp+130h+var_100], rdx
0x1800743a6  mov     [rsp+130h+var_F8], rbx
0x1800743ab  mov     byte ptr [rsp+130h+var_F0], 1
0x1800743b0  lea     rdx, [rsp+130h+var_F8]
0x1800743b5  mov     rax, [rax+30h]
0x1800743b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800743be  mov     rcx, [rbp+5Fh]; this
0x1800743c2  test    eax, eax
0x1800743c4  js      loc_1800746ED
0x1800743ca  cmp     byte ptr [rsp+130h+var_F0], bl
0x1800743ce  jz      short loc_180074400
0x1800743d0  mov     r15, [rsp+130h+var_F8]
0x1800743d5  mov     rdi, [rsp+130h+var_100]
0x1800743da  mov     r14, [rdi]
0x1800743dd  test    r14, r14
0x1800743e0  jz      short loc_1800743FD
0x1800743e2  call    cs:__imp_GetLastError
0x1800743e8  mov     ebx, eax
0x1800743ea  mov     rcx, r14; string
0x1800743ed  call    cs:__imp_WindowsDeleteString
0x1800743f3  mov     ecx, ebx; dwErrCode
0x1800743f5  call    cs:__imp_SetLastError
0x1800743fb  xor     ebx, ebx
0x1800743fd  mov     [rdi], r15
0x180074400  mov     [rbp+57h+string], rbx
0x180074404  mov     rcx, [rsp+130h+var_E0]
0x180074409  mov     rax, [rcx]
0x18007440c  lea     rdx, [rbp+57h+string]
0x180074410  mov     [rsp+130h+var_100], rdx
0x180074415  mov     [rsp+130h+var_F8], rbx
0x18007441a  mov     byte ptr [rsp+130h+var_F0], 1
0x18007441f  lea     rdx, [rsp+130h+var_F8]
0x180074424  mov     rax, [rax+38h]
0x180074428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007442d  mov     rcx, [rbp+5Fh]; this
0x180074431  test    eax, eax
0x180074433  js      loc_1800746D8
0x180074439  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007443d  jz      short loc_18007446F
0x18007443f  mov     r15, [rsp+130h+var_F8]
0x180074444  mov     rdi, [rsp+130h+var_100]
0x180074449  mov     r14, [rdi]
0x18007444c  test    r14, r14
0x18007444f  jz      short loc_18007446C
0x180074451  call    cs:__imp_GetLastError
0x180074457  mov     ebx, eax
0x180074459  mov     rcx, r14; string
0x18007445c  call    cs:__imp_WindowsDeleteString
0x180074462  mov     ecx, ebx; dwErrCode
0x180074464  call    cs:__imp_SetLastError
0x18007446a  xor     ebx, ebx
0x18007446c  mov     [rdi], r15
0x18007446f  xorps   xmm0, xmm0
0x180074472  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180074476  mov     [rbp+57h+var_90], rbx
0x18007447a  mov     [rbp+57h+var_88], 7
0x180074482  mov     word ptr [rbp+57h+var_A0], bx
0x180074486  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18007448a  mov     [rbp+57h+var_70], rbx
0x18007448e  mov     [rbp+57h+var_68], 7
0x180074496  mov     word ptr [rbp+57h+var_80], bx
0x18007449a  xor     edx, edx; length
0x18007449c  mov     rcx, [rbp+57h+string]; string
0x1800744a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800744a6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800744aa  inc     rdx
0x1800744ad  cmp     [rax+rdx*2], bx
0x1800744b1  jnz     short loc_1800744AA
0x1800744b3  cmp     rdx, [rbp+57h+var_88]
0x1800744b7  ja      short loc_1800744E7
0x1800744b9  lea     rdi, [rbp+57h+var_A0]
0x1800744bd  cmp     [rbp+57h+var_88], 7
0x1800744c2  cmova   rdi, [rbp+57h+var_A0]
0x1800744c7  mov     [rbp+57h+var_90], rdx
0x1800744cb  lea     rbx, [rdx+rdx]
0x1800744cf  mov     r8, rbx; Size
0x1800744d2  mov     rdx, rax; Src
0x1800744d5  mov     rcx, rdi; void *
0x1800744d8  call    memmove_0
0x1800744dd  xor     eax, eax
0x1800744df  mov     [rbx+rdi], ax
0x1800744e3  xor     ebx, ebx
0x1800744e5  jmp     short loc_1800744F3
0x1800744e7  mov     r9, rax
0x1800744ea  lea     rcx, [rbp+57h+var_A0]
0x1800744ee  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800744f3  xor     edx, edx; length
0x1800744f5  mov     rcx, [rbp+57h+var_C0]; string
0x1800744f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800744ff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180074503  inc     rdx
0x180074506  cmp     [rax+rdx*2], bx
0x18007450a  jnz     short loc_180074503
0x18007450c  cmp     rdx, [rbp+57h+var_68]
0x180074510  ja      short loc_180074540
0x180074512  lea     rdi, [rbp+57h+var_80]
0x180074516  cmp     [rbp+57h+var_68], 7
0x18007451b  cmova   rdi, [rbp+57h+var_80]
0x180074520  mov     [rbp+57h+var_70], rdx
0x180074524  lea     rbx, [rdx+rdx]
0x180074528  mov     r8, rbx; Size
0x18007452b  mov     rdx, rax; Src
0x18007452e  mov     rcx, rdi; void *
0x180074531  call    memmove_0
0x180074536  xor     eax, eax
0x180074538  mov     [rdi+rbx], ax
0x18007453c  xor     ebx, ebx
0x18007453e  jmp     short loc_18007454C
0x180074540  mov     r9, rax
0x180074543  lea     rcx, [rbp+57h+var_80]
0x180074547  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18007454c  mov     rdx, [rsi+8]
0x180074550  cmp     rdx, [rsi+10h]
0x180074554  jz      loc_1800745DA
0x18007455a  xorps   xmm0, xmm0
0x18007455d  movups  xmmword ptr [rdx], xmm0
0x180074560  mov     [rdx+10h], rbx
0x180074564  mov     [rdx+18h], rbx
0x180074568  mov     rax, [rbp+57h+var_A0]
0x18007456c  mov     [rdx], rax
0x18007456f  mov     rax, [rbp+57h+var_A0+8]
0x180074573  mov     [rdx+8], rax
0x180074577  mov     rax, [rbp+57h+var_90]
0x18007457b  mov     [rdx+10h], rax
0x18007457f  mov     rax, [rbp+57h+var_88]
0x180074583  mov     [rdx+18h], rax
0x180074587  mov     [rbp+57h+var_90], rbx
0x18007458b  mov     [rbp+57h+var_88], 7
0x180074593  mov     word ptr [rbp+57h+var_A0], bx
0x180074597  movups  xmmword ptr [rdx+20h], xmm0
0x18007459b  mov     [rdx+30h], rbx
0x18007459f  mov     [rdx+38h], rbx
0x1800745a3  mov     rax, [rbp+57h+var_80]
0x1800745a7  mov     [rdx+20h], rax
0x1800745ab  mov     rax, [rbp+57h+var_80+8]
0x1800745af  mov     [rdx+28h], rax
0x1800745b3  mov     rax, [rbp+57h+var_70]
0x1800745b7  mov     [rdx+30h], rax
0x1800745bb  mov     rax, [rbp+57h+var_68]
0x1800745bf  mov     [rdx+38h], rax
0x1800745c3  mov     [rbp+57h+var_70], rbx
0x1800745c7  mov     [rbp+57h+var_68], 7
0x1800745cf  mov     word ptr [rbp+57h+var_80], bx
0x1800745d3  add     qword ptr [rsi+8], 40h ; '@'
0x1800745d8  jmp     short loc_1800745E7
0x1800745da  lea     r8, [rbp+57h+var_A0]
0x1800745de  mov     rcx, rsi
0x1800745e1  call    ??$_Emplace_reallocate@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> * const,Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x1800745e6  nop
0x1800745e7  lea     rcx, [rbp+57h+var_80]
0x1800745eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800745f0  lea     rcx, [rbp+57h+var_A0]
0x1800745f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800745f9  nop
0x1800745fa  mov     rcx, [rbp+57h+string]; string
0x1800745fe  test    rcx, rcx
  ... truncated ...
```
