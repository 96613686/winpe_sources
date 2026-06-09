# CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x18003101c`
- end: `0x1800311ce`
- name: `?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z`
- size: `434`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180030cc8`

## callees

- `0x180002714`
- `0x180002a40`
- `0x18000e0d0`
- `0x18000e6e0`
- `0x180011884`
- `0x1800122d8`
- `0x180023a30`
- `0x180030324`
- `0x18003101c`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800310be`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180031119`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18003116d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800310be`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180031119`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18003116d`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18003108f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18003108f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180031053`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180031053`

## string_xrefs

- `0x18003114b`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiSupport::GetDllDetailsFromPath(LPCWSTR lpwstrFilename, __int64 a2, __int64 a3)
{
  unsigned int v6; // esi
  DWORD FileVersionInfoSize; // eax
  DWORD v8; // ebx
  void *lpData; // rax
  void *v10; // rdi
  unsigned int v11; // ebx
  LPCWSTR *v12; // rax
  BOOL v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rcx
  LPCWSTR *v16; // rax
  BOOL v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // rcx
  DWORD dwHandle; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h] BYREF
  __int64 v24; // [rsp+48h] [rbp-8h] BYREF
  unsigned int puLen; // [rsp+98h] [rbp+48h] BYREF

  v6 = 1;
  dwHandle = 0;
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, lpwstrFilename, &dwHandle);
  v8 = FileVersionInfoSize;
  if ( FileVersionInfoSize )
  {
    lpData = operator new[](FileVersionInfoSize, (const struct std::nothrow_t *)&std::nothrow);
    v10 = lpData;
    if ( lpData )
    {
      if ( GetFileVersionInfoExW(3u, lpwstrFilename, dwHandle, v8, lpData) )
      {
        lpBuffer = 0;
        puLen = 0;
        if ( VerQueryValueW(v10, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          v11 = *(_DWORD *)lpBuffer;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v23);
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
            &v23,
            L"\\StringFileInfo\\%04X%04X\\",
            (unsigned __int16)v11,
            HIWORD(v11));
          v12 = (LPCWSTR *)ATL::operator+(&v24, &v23, L"FileVersion");
          v13 = VerQueryValueW(v10, *v12, &lpBuffer, &puLen);
          ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
          if ( v13 )
          {
            v14 = ocslen((const wchar_t *)lpBuffer);
            ATL::CSimpleStringT<wchar_t,0>::SetString(a2, v15, v14);
            v6 = 0;
            v16 = (LPCWSTR *)ATL::operator+(&v24, &v23, L"CompanyName");
            v17 = VerQueryValueW(v10, *v16, &lpBuffer, &puLen);
            ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
            if ( v17 )
            {
              v18 = ocslen((const wchar_t *)lpBuffer);
              ATL::CSimpleStringT<wchar_t,0>::SetString(a3, v19, v18);
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
        }
      }
      operator delete(v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18003101c  mov     [rsp-28h+arg_0], rbx
0x180031021  mov     [rsp-28h+arg_8], rsi
0x180031026  push    rbp
0x180031027  push    rdi
0x180031028  push    r12
0x18003102a  push    r14
0x18003102c  push    r15
0x18003102e  mov     rbp, rsp
0x180031031  sub     rsp, 50h
0x180031035  mov     r15, r8
0x180031038  mov     r12, rdx
0x18003103b  mov     r14, rcx
0x18003103e  mov     esi, 1
0x180031043  mov     [rbp+dwHandle], 0
0x18003104a  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18003104e  mov     rdx, rcx; lpwstrFilename
0x180031051  mov     ecx, esi; dwFlags
0x180031053  call    cs:__imp_GetFileVersionInfoSizeExW
0x180031059  mov     ebx, eax
0x18003105b  test    eax, eax
0x18003105d  jz      loc_1800311B3
0x180031063  mov     ecx, ebx; unsigned __int64
0x180031065  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003106c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180031071  mov     rdi, rax
0x180031074  test    rax, rax
0x180031077  jz      loc_1800311B3
0x18003107d  mov     [rsp+50h+lpData], rax; lpData
0x180031082  mov     r9d, ebx; dwLen
0x180031085  mov     r8d, [rbp+dwHandle]; dwHandle
0x180031089  mov     rdx, r14; lpwstrFilename
0x18003108c  lea     ecx, [rsi+2]; dwFlags
0x18003108f  call    cs:__imp_GetFileVersionInfoExW
0x180031095  test    eax, eax
0x180031097  jz      loc_1800311AB
0x18003109d  mov     [rbp+lpBuffer], 0
0x1800310a5  mov     [rbp+puLen], 0
0x1800310ac  lea     r9, [rbp+puLen]; puLen
0x1800310b0  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x1800310b4  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x1800310bb  mov     rcx, rdi; pBlock
0x1800310be  call    cs:__imp_VerQueryValueW
0x1800310c4  test    eax, eax
0x1800310c6  jz      loc_1800311AB
0x1800310cc  mov     rax, [rbp+lpBuffer]
0x1800310d0  mov     ebx, [rax]
0x1800310d2  lea     rcx, [rbp+var_10]
0x1800310d6  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800310db  nop
0x1800310dc  mov     r9d, ebx
0x1800310df  shr     r9d, 10h
0x1800310e3  movzx   r8d, bx
0x1800310e7  lea     rdx, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\"
0x1800310ee  lea     rcx, [rbp+var_10]
0x1800310f2  call    ?Format@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x1800310f7  lea     r8, aFileversion; "FileVersion"
0x1800310fe  lea     rdx, [rbp+var_10]
0x180031102  lea     rcx, [rbp+var_8]
0x180031106  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18003110b  lea     r9, [rbp+puLen]; puLen
0x18003110f  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180031113  mov     rdx, [rax]; lpSubBlock
0x180031116  mov     rcx, rdi; pBlock
0x180031119  call    cs:__imp_VerQueryValueW
0x18003111f  mov     ebx, eax
0x180031121  mov     rcx, [rbp+var_8]
0x180031125  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031129  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003112e  test    ebx, ebx
0x180031130  jz      short loc_18003119E
0x180031132  mov     rcx, [rbp+lpBuffer]; wchar_t *
0x180031136  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18003113b  mov     r8d, eax
0x18003113e  mov     rdx, rcx
0x180031141  mov     rcx, r12
0x180031144  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031149  xor     esi, esi
0x18003114b  lea     r8, aCompanyname; "CompanyName"
0x180031152  lea     rdx, [rbp+var_10]
0x180031156  lea     rcx, [rbp+var_8]
0x18003115a  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18003115f  lea     r9, [rbp+puLen]; puLen
0x180031163  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180031167  mov     rdx, [rax]; lpSubBlock
0x18003116a  mov     rcx, rdi; pBlock
0x18003116d  call    cs:__imp_VerQueryValueW
0x180031173  mov     ebx, eax
0x180031175  mov     rcx, [rbp+var_8]
0x180031179  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003117d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031182  test    ebx, ebx
0x180031184  jz      short loc_18003119E
0x180031186  mov     rcx, [rbp+lpBuffer]; wchar_t *
0x18003118a  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18003118f  mov     r8d, eax
0x180031192  mov     rdx, rcx
0x180031195  mov     rcx, r15
0x180031198  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003119d  nop
0x18003119e  mov     rcx, [rbp+var_10]
0x1800311a2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800311a6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800311ab  mov     rcx, rdi; Block
0x1800311ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800311b3  mov     eax, esi
0x1800311b5  lea     r11, [rsp+50h+var_s0]
0x1800311ba  mov     rbx, [r11+30h]
0x1800311be  mov     rsi, [r11+38h]
0x1800311c2  mov     rsp, r11
0x1800311c5  pop     r15
0x1800311c7  pop     r14
0x1800311c9  pop     r12
0x1800311cb  pop     rdi
0x1800311cc  pop     rbp
0x1800311cd  retn
```
