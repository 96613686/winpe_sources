# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppMetaData>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180074720`
- end: `0x180074cc7`
- name: `??$make_cloud_store_reference_vector@UAppMetaData@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1447`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800730a4`

## callees

- `0x180008570`
- `0x180072098`
- `0x180072464`
- `0x1800726b4`
- `0x180073c14`
- `0x180074720`
- `0x180076ddc`
- `0x1800948e8`
- `0x1802174f0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800748d0`
- `KERNEL32!CompareStringOrdinal` at `0x1800748d0`
- `KERNEL32!GetLastError` at `0x180074884`
- `KERNEL32!GetLastError` at `0x180074992`
- `KERNEL32!GetLastError` at `0x180074a01`
- `KERNEL32!GetLastError` at `0x180074884`
- `KERNEL32!GetLastError` at `0x180074992`
- `KERNEL32!GetLastError` at `0x180074a01`
- `KERNEL32!SetLastError` at `0x180074897`
- `KERNEL32!SetLastError` at `0x1800749a5`
- `KERNEL32!SetLastError` at `0x180074a14`
- `KERNEL32!SetLastError` at `0x180074897`
- `KERNEL32!SetLastError` at `0x1800749a5`
- `KERNEL32!SetLastError` at `0x180074a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007488f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007499d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074a0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007488f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007499d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074a0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800748b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074a50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074aa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800748b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074a50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074aa9`

## pseudocode

```c
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppMetaData>(
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
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppMetaData>(lpString2);
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
0x180074720  mov     rax, rsp
0x180074723  push    rbp
0x180074724  push    rsi
0x180074725  push    rdi
0x180074726  push    r12
0x180074728  push    r13
0x18007472a  push    r14
0x18007472c  push    r15
0x18007472e  lea     rbp, [rax-5Fh]
0x180074732  sub     rsp, 100h
0x180074739  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x180074741  mov     [rax+18h], rbx
0x180074745  mov     rax, cs:__security_cookie
0x18007474c  xor     rax, rsp
0x18007474f  mov     [rbp+57h+var_40], rax
0x180074753  mov     r13, rdx
0x180074756  mov     rsi, rcx
0x180074759  mov     [rbp+57h+var_A8], rcx
0x18007475d  xor     ebx, ebx
0x18007475f  mov     [rbp+57h+var_D0], ebx
0x180074762  lea     rcx, [rbp+57h+lpString2]
0x180074766  call    ??$get_type_name_wide_string@UAppMetaData@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppMetaData>(void)
0x18007476b  nop
0x18007476c  mov     dword ptr [rsp+130h+var_E8], ebx
0x180074770  mov     rax, [r13+0]
0x180074774  lea     rdx, [rsp+130h+var_E8]
0x180074779  mov     rcx, r13
0x18007477c  mov     rax, [rax+38h]
0x180074780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074785  mov     rcx, [rbp+5Fh]; this
0x180074789  test    eax, eax
0x18007478b  js      loc_180074C73
0x180074791  mov     [rsi], rbx
0x180074794  mov     [rsi+8], rbx
0x180074798  mov     [rsi+10h], rbx
0x18007479c  mov     [rbp+57h+var_D0], 1
0x1800747a3  mov     ecx, dword ptr [rsp+130h+var_E8]
0x1800747a7  mov     [rsp+130h+var_D8], rcx
0x1800747ac  test    ecx, ecx
0x1800747ae  jz      short loc_1800747C1
0x1800747b0  lea     rdx, [rsp+130h+var_D8]
0x1800747b5  mov     rcx, rsi
0x1800747b8  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(unsigned __int64 &)
0x1800747bd  mov     ecx, dword ptr [rsp+130h+var_E8]
0x1800747c1  mov     r12d, ebx
0x1800747c4  test    ecx, ecx
0x1800747c6  jz      loc_180074C16
0x1800747cc  mov     [rsp+130h+var_E0], rbx
0x1800747d1  mov     rax, [r13+0]
0x1800747d5  lea     rcx, [rsp+130h+var_E0]
0x1800747da  mov     [rsp+130h+var_100], rcx
0x1800747df  mov     [rsp+130h+var_F8], rbx
0x1800747e4  mov     byte ptr [rsp+130h+var_F0], 1
0x1800747e9  lea     r8, [rsp+130h+var_F8]
0x1800747ee  mov     edx, r12d
0x1800747f1  mov     rcx, r13
0x1800747f4  mov     rax, [rax+30h]
0x1800747f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747fd  mov     rcx, [rbp+5Fh]; this
0x180074801  test    eax, eax
0x180074803  js      loc_180074C5E
0x180074809  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007480d  jz      short loc_180074831
0x18007480f  mov     rdx, [rsp+130h+var_F8]
0x180074814  mov     rax, [rsp+130h+var_100]
0x180074819  mov     rcx, [rax]
0x18007481c  mov     [rax], rdx
0x18007481f  test    rcx, rcx
0x180074822  jz      short loc_180074831
0x180074824  mov     rax, [rcx]
0x180074827  mov     rax, [rax+10h]
0x18007482b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074830  nop
0x180074831  mov     [rsp+130h+var_D8], rbx
0x180074836  mov     rcx, [rsp+130h+var_E0]
0x18007483b  mov     rax, [rcx]
0x18007483e  lea     rdx, [rsp+130h+var_D8]
0x180074843  mov     [rsp+130h+var_100], rdx
0x180074848  mov     [rsp+130h+var_F8], rbx
0x18007484d  mov     byte ptr [rsp+130h+var_F0], 1
0x180074852  lea     rdx, [rsp+130h+var_F8]
0x180074857  mov     rax, [rax+40h]
0x18007485b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074860  mov     rcx, [rbp+5Fh]; this
0x180074864  test    eax, eax
0x180074866  js      loc_180074C49
0x18007486c  cmp     byte ptr [rsp+130h+var_F0], bl
0x180074870  jz      short loc_1800748A0
0x180074872  mov     r15, [rsp+130h+var_F8]
0x180074877  mov     rdi, [rsp+130h+var_100]
0x18007487c  mov     r14, [rdi]
0x18007487f  test    r14, r14
0x180074882  jz      short loc_18007489D
0x180074884  call    cs:__imp_GetLastError
0x18007488a  mov     ebx, eax
0x18007488c  mov     rcx, r14; string
0x18007488f  call    cs:__imp_WindowsDeleteString
0x180074895  mov     ecx, ebx; dwErrCode
0x180074897  call    cs:__imp_SetLastError
0x18007489d  mov     [rdi], r15
0x1800748a0  lea     rbx, [rbp+57h+lpString2]
0x1800748a4  cmp     [rbp+57h+var_48], 7
0x1800748a9  cmova   rbx, [rbp+57h+lpString2]
0x1800748ae  xor     edx, edx; length
0x1800748b0  mov     rcx, [rsp+130h+var_D8]; string
0x1800748b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800748bb  mov     dword ptr [rsp+20h], 1; int
0x1800748c3  or      r9d, 0FFFFFFFFh; cchCount2
0x1800748c7  mov     r8, rbx; lpString2
0x1800748ca  or      edx, r9d; cchCount1
0x1800748cd  mov     rcx, rax; lpString1
0x1800748d0  call    cs:__imp_CompareStringOrdinal
0x1800748d6  xor     ebx, ebx
0x1800748d8  cmp     eax, 2
0x1800748db  jnz     loc_180074BE0
0x1800748e1  mov     [rbp+57h+var_B8], rbx
0x1800748e5  mov     rcx, [rsp+130h+var_E0]
0x1800748ea  mov     rax, [rcx]
0x1800748ed  lea     rdx, [rbp+57h+var_B8]
0x1800748f1  mov     [rsp+130h+var_100], rdx
0x1800748f6  mov     [rsp+130h+var_F8], rbx
0x1800748fb  mov     byte ptr [rsp+130h+var_F0], 1
0x180074900  lea     rdx, [rsp+130h+var_F8]
0x180074905  mov     rax, [rax+30h]
0x180074909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007490e  mov     rcx, [rbp+5Fh]; this
0x180074912  test    eax, eax
0x180074914  js      loc_180074CB2
0x18007491a  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007491e  jz      short loc_180074942
0x180074920  mov     rdx, [rsp+130h+var_F8]
0x180074925  mov     rax, [rsp+130h+var_100]
0x18007492a  mov     rcx, [rax]
0x18007492d  mov     [rax], rdx
0x180074930  test    rcx, rcx
0x180074933  jz      short loc_180074942
0x180074935  mov     rax, [rcx]
0x180074938  mov     rax, [rax+10h]
0x18007493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074941  nop
0x180074942  mov     [rbp+57h+var_C0], rbx
0x180074946  mov     rcx, [rbp+57h+var_B8]
0x18007494a  mov     rax, [rcx]
0x18007494d  lea     rdx, [rbp+57h+var_C0]
0x180074951  mov     [rsp+130h+var_100], rdx
0x180074956  mov     [rsp+130h+var_F8], rbx
0x18007495b  mov     byte ptr [rsp+130h+var_F0], 1
0x180074960  lea     rdx, [rsp+130h+var_F8]
0x180074965  mov     rax, [rax+30h]
0x180074969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007496e  mov     rcx, [rbp+5Fh]; this
0x180074972  test    eax, eax
0x180074974  js      loc_180074C9D
0x18007497a  cmp     byte ptr [rsp+130h+var_F0], bl
0x18007497e  jz      short loc_1800749B0
0x180074980  mov     r15, [rsp+130h+var_F8]
0x180074985  mov     rdi, [rsp+130h+var_100]
0x18007498a  mov     r14, [rdi]
0x18007498d  test    r14, r14
0x180074990  jz      short loc_1800749AD
0x180074992  call    cs:__imp_GetLastError
0x180074998  mov     ebx, eax
0x18007499a  mov     rcx, r14; string
0x18007499d  call    cs:__imp_WindowsDeleteString
0x1800749a3  mov     ecx, ebx; dwErrCode
0x1800749a5  call    cs:__imp_SetLastError
0x1800749ab  xor     ebx, ebx
0x1800749ad  mov     [rdi], r15
0x1800749b0  mov     [rbp+57h+string], rbx
0x1800749b4  mov     rcx, [rsp+130h+var_E0]
0x1800749b9  mov     rax, [rcx]
0x1800749bc  lea     rdx, [rbp+57h+string]
0x1800749c0  mov     [rsp+130h+var_100], rdx
0x1800749c5  mov     [rsp+130h+var_F8], rbx
0x1800749ca  mov     byte ptr [rsp+130h+var_F0], 1
0x1800749cf  lea     rdx, [rsp+130h+var_F8]
0x1800749d4  mov     rax, [rax+38h]
0x1800749d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749dd  mov     rcx, [rbp+5Fh]; this
0x1800749e1  test    eax, eax
0x1800749e3  js      loc_180074C88
0x1800749e9  cmp     byte ptr [rsp+130h+var_F0], bl
0x1800749ed  jz      short loc_180074A1F
0x1800749ef  mov     r15, [rsp+130h+var_F8]
0x1800749f4  mov     rdi, [rsp+130h+var_100]
0x1800749f9  mov     r14, [rdi]
0x1800749fc  test    r14, r14
0x1800749ff  jz      short loc_180074A1C
0x180074a01  call    cs:__imp_GetLastError
0x180074a07  mov     ebx, eax
0x180074a09  mov     rcx, r14; string
0x180074a0c  call    cs:__imp_WindowsDeleteString
0x180074a12  mov     ecx, ebx; dwErrCode
0x180074a14  call    cs:__imp_SetLastError
0x180074a1a  xor     ebx, ebx
0x180074a1c  mov     [rdi], r15
0x180074a1f  xorps   xmm0, xmm0
0x180074a22  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180074a26  mov     [rbp+57h+var_90], rbx
0x180074a2a  mov     [rbp+57h+var_88], 7
0x180074a32  mov     word ptr [rbp+57h+var_A0], bx
0x180074a36  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180074a3a  mov     [rbp+57h+var_70], rbx
0x180074a3e  mov     [rbp+57h+var_68], 7
0x180074a46  mov     word ptr [rbp+57h+var_80], bx
0x180074a4a  xor     edx, edx; length
0x180074a4c  mov     rcx, [rbp+57h+string]; string
0x180074a50  call    cs:__imp_WindowsGetStringRawBuffer
0x180074a56  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180074a5a  inc     rdx
0x180074a5d  cmp     [rax+rdx*2], bx
0x180074a61  jnz     short loc_180074A5A
0x180074a63  cmp     rdx, [rbp+57h+var_88]
0x180074a67  ja      short loc_180074A97
0x180074a69  lea     rdi, [rbp+57h+var_A0]
0x180074a6d  cmp     [rbp+57h+var_88], 7
0x180074a72  cmova   rdi, [rbp+57h+var_A0]
0x180074a77  mov     [rbp+57h+var_90], rdx
0x180074a7b  lea     rbx, [rdx+rdx]
0x180074a7f  mov     r8, rbx; Size
0x180074a82  mov     rdx, rax; Src
0x180074a85  mov     rcx, rdi; void *
0x180074a88  call    memmove_0
0x180074a8d  xor     eax, eax
0x180074a8f  mov     [rbx+rdi], ax
0x180074a93  xor     ebx, ebx
0x180074a95  jmp     short loc_180074AA3
0x180074a97  mov     r9, rax
0x180074a9a  lea     rcx, [rbp+57h+var_A0]
0x180074a9e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180074aa3  xor     edx, edx; length
0x180074aa5  mov     rcx, [rbp+57h+var_C0]; string
0x180074aa9  call    cs:__imp_WindowsGetStringRawBuffer
0x180074aaf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180074ab3  inc     rdx
0x180074ab6  cmp     [rax+rdx*2], bx
0x180074aba  jnz     short loc_180074AB3
0x180074abc  cmp     rdx, [rbp+57h+var_68]
0x180074ac0  ja      short loc_180074AF0
0x180074ac2  lea     rdi, [rbp+57h+var_80]
0x180074ac6  cmp     [rbp+57h+var_68], 7
0x180074acb  cmova   rdi, [rbp+57h+var_80]
0x180074ad0  mov     [rbp+57h+var_70], rdx
0x180074ad4  lea     rbx, [rdx+rdx]
0x180074ad8  mov     r8, rbx; Size
0x180074adb  mov     rdx, rax; Src
0x180074ade  mov     rcx, rdi; void *
0x180074ae1  call    memmove_0
0x180074ae6  xor     eax, eax
0x180074ae8  mov     [rdi+rbx], ax
0x180074aec  xor     ebx, ebx
0x180074aee  jmp     short loc_180074AFC
0x180074af0  mov     r9, rax
0x180074af3  lea     rcx, [rbp+57h+var_80]
0x180074af7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180074afc  mov     rdx, [rsi+8]
0x180074b00  cmp     rdx, [rsi+10h]
0x180074b04  jz      loc_180074B8A
0x180074b0a  xorps   xmm0, xmm0
0x180074b0d  movups  xmmword ptr [rdx], xmm0
0x180074b10  mov     [rdx+10h], rbx
0x180074b14  mov     [rdx+18h], rbx
0x180074b18  mov     rax, [rbp+57h+var_A0]
0x180074b1c  mov     [rdx], rax
0x180074b1f  mov     rax, [rbp+57h+var_A0+8]
0x180074b23  mov     [rdx+8], rax
0x180074b27  mov     rax, [rbp+57h+var_90]
0x180074b2b  mov     [rdx+10h], rax
0x180074b2f  mov     rax, [rbp+57h+var_88]
0x180074b33  mov     [rdx+18h], rax
0x180074b37  mov     [rbp+57h+var_90], rbx
0x180074b3b  mov     [rbp+57h+var_88], 7
0x180074b43  mov     word ptr [rbp+57h+var_A0], bx
0x180074b47  movups  xmmword ptr [rdx+20h], xmm0
0x180074b4b  mov     [rdx+30h], rbx
0x180074b4f  mov     [rdx+38h], rbx
0x180074b53  mov     rax, [rbp+57h+var_80]
0x180074b57  mov     [rdx+20h], rax
0x180074b5b  mov     rax, [rbp+57h+var_80+8]
0x180074b5f  mov     [rdx+28h], rax
0x180074b63  mov     rax, [rbp+57h+var_70]
0x180074b67  mov     [rdx+30h], rax
0x180074b6b  mov     rax, [rbp+57h+var_68]
0x180074b6f  mov     [rdx+38h], rax
0x180074b73  mov     [rbp+57h+var_70], rbx
0x180074b77  mov     [rbp+57h+var_68], 7
0x180074b7f  mov     word ptr [rbp+57h+var_80], bx
0x180074b83  add     qword ptr [rsi+8], 40h ; '@'
0x180074b88  jmp     short loc_180074B97
0x180074b8a  lea     r8, [rbp+57h+var_A0]
0x180074b8e  mov     rcx, rsi
0x180074b91  call    ??$_Emplace_reallocate@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> * const,Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180074b96  nop
0x180074b97  lea     rcx, [rbp+57h+var_80]
0x180074b9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180074ba0  lea     rcx, [rbp+57h+var_A0]
0x180074ba4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180074ba9  nop
0x180074baa  mov     rcx, [rbp+57h+string]; string
0x180074bae  test    rcx, rcx
  ... truncated ...
```
