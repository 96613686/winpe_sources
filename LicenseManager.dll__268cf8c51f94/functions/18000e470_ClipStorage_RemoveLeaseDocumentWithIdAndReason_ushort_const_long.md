# ClipStorage::RemoveLeaseDocumentWithIdAndReason(ushort const *,long)

- ea: `0x18000e470`
- end: `0x18000eb2f`
- name: `?RemoveLeaseDocumentWithIdAndReason@ClipStorage@@UEAAJPEBGJ@Z`
- size: `1727`
- prototype: `int(ClipStorage *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004738`
- `0x18000b750`
- `0x18000b7a4`
- `0x18000d600`
- `0x18000e470`
- `0x180011960`
- `0x180011a00`
- `0x180013b50`
- `0x1800293f4`
- `0x180042d58`
- `0x1800593bc`
- `0x180075e60`
- `0x1800767e0`
- `0x180076a00`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea03`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea22`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea22`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e4b2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e4b2`

## string_xrefs

- `0x18000e711`: `ClipStorage::RemoveLeaseDocumentWithIdAndReason`
- `0x18000e82e`: `ClipStorage::RemoveLeaseDocumentWithIdAndReason`
- `0x18000e8ba`: `ClipStorage::RemoveLeaseDocumentWithIdAndReason`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ClipStorage::RemoveLeaseDocumentWithIdAndReason(
        ClipStorage *this,
        const unsigned __int16 *a2,
        int a3)
{
  HRESULT v6; // eax
  __int64 v7; // rcx
  _DWORD *v8; // rax
  char *v9; // rbx
  __int64 *v10; // r14
  __int64 v11; // r15
  __int64 v12; // r12
  __int64 v13; // rdx
  int v14; // eax
  _DWORD **v15; // rbx
  int v16; // eax
  _DWORD *v17; // rax
  int v18; // eax
  int v19; // eax
  _QWORD *v20; // rcx
  int LastError; // eax
  int v23; // ecx
  _QWORD *v24; // rcx
  __int64 *v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  _QWORD *v30; // rcx
  volatile signed __int32 *v31; // rbx
  int v32; // eax
  int Format; // [rsp+20h] [rbp-238h]
  int Formata; // [rsp+20h] [rbp-238h]
  int Formatb; // [rsp+20h] [rbp-238h]
  int v36; // [rsp+40h] [rbp-218h] BYREF
  _QWORD *v37; // [rsp+48h] [rbp-210h] BYREF
  __int64 v38; // [rsp+50h] [rbp-208h] BYREF
  __int64 v39; // [rsp+58h] [rbp-200h] BYREF
  int v40; // [rsp+60h] [rbp-1F8h] BYREF
  void **v41; // [rsp+68h] [rbp-1F0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-1E8h]
  __int64 v43; // [rsp+78h] [rbp-1E0h] BYREF
  int v44[2]; // [rsp+80h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v45; // [rsp+88h] [rbp-1D0h]
  __int64 v46; // [rsp+90h] [rbp-1C8h] BYREF
  _OWORD v47[9]; // [rsp+98h] [rbp-1C0h] BYREF
  __int64 v48; // [rsp+128h] [rbp-130h]
  void **pExceptionObject; // [rsp+130h] [rbp-128h] BYREF
  __int128 v50; // [rsp+138h] [rbp-120h]
  _BYTE v51[152]; // [rsp+148h] [rbp-110h] BYREF
  __int64 v52; // [rsp+1E0h] [rbp-78h]
  __int64 v53; // [rsp+1E8h] [rbp-70h]
  __int64 v54; // [rsp+1F0h] [rbp-68h]
  __int64 v55; // [rsp+1F8h] [rbp-60h]
  GUID v56; // [rsp+200h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v56 = 0;
  v6 = CLSIDFromString(a2, &v56);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
      (const char *)(unsigned int)v6,
      Format);
  CreateQuery(&v41, L"%1=%2!s!", L"FileId", a2);
  v7 = *((_QWORD *)this + 2);
  v38 = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v39 = 0;
  v8 = operator new(0x20u);
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable';
  v9 = (char *)(v8 + 4);
  *((_QWORD *)v8 + 2) = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  *((_QWORD *)v8 + 3) = 0;
  *(_QWORD *)v44 = v8 + 4;
  v45 = (std::_Ref_count_base *)v8;
  v10 = (__int64 *)*((_QWORD *)this + 2);
  v11 = *v10;
  v12 = v42;
  v13 = v39;
  if ( !v39 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v39);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\ClipHelpers.h",
        (const char *)(unsigned int)v14,
        Format);
    v13 = v39;
  }
  v15 = (_DWORD **)(v9 + 8);
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD))(v11 + 64))(v10, v13, v12, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
      (const char *)(unsigned int)v16,
      (int)v15);
  v17 = *v15;
  if ( !*v15 || !*v17 || v17[1] != 6 )
  {
    v50 = 0;
    pExceptionObject = &wil::ResultException::`vftable';
    memset(v47, 0, sizeof(v47));
    DWORD2(v47[0]) = -2147023728;
    v48 = 0;
    v52 = 0;
    v53 = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)v51, (const struct wil::FailureInfo *)v47);
    v54 = 0;
    v55 = 0;
    throw (wil::ResultException *)&pExceptionObject;
  }
  v40 = 0;
  v36 = 0;
  v46 = 0;
  v43 = *((_QWORD *)this + 2);
  MakeCom<ClipLeaseDocument,IClipStore *,std::nullptr_t,int,std::shared_ptr<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>> &>(
    (unsigned int)&v37,
    (unsigned int)&v43,
    (unsigned int)&v46,
    (unsigned int)&v36,
    (__int64)v44);
  v18 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v37 + 88LL))(v37, &v40);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
      (const char *)(unsigned int)v18,
      Formata);
  if ( v40 != 3 )
  {
    v36 = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD *, int *))(v37[1] + 152LL))(v37 + 1, &v36);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        (const char *)(unsigned int)v19,
        Formata);
    if ( v36 && ((a3 & 0xF000) != 0x8000 || (a3 & 0x1FFF0000) != 0x3F0000 || a3 >= 0) )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x1F5u,
        "ClipStorage::RemoveLeaseDocumentWithIdAndReason",
        (wchar_t *)L"Ignoring lease removal with reason 0x%08x because this is an offline lease\n",
        a3);
      v20 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
      }
      if ( v45 )
        std::_Ref_count_base::_Decref(v45);
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 32LL))(v38);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
      v41 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      if ( v42 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v41) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RaiseException(LastError, 1u, 0, 0);
        __debugbreak();
      }
      return 0;
    }
    v23 = a3 & 0xF000;
    if ( v23 != 0x8000 )
      goto LABEL_40;
    if ( (a3 & 0x1FFF0000) != 0x3F0000 )
    {
LABEL_41:
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x1FEu,
        "ClipStorage::RemoveLeaseDocumentWithIdAndReason",
        (wchar_t *)L"Ignoring lease removal request with reason 0x%08x\n",
        a3);
      v24 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
      }
      if ( v45 )
        std::_Ref_count_base::_Decref(v45);
      HClip::~HClip((HClip *)&v38);
      v41 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v41);
      return 0;
    }
    if ( a3 >= 0 )
    {
LABEL_40:
      if ( v23 != 36864 || (a3 & 0x1FFF0000) != 0x3F0000 || a3 >= 0 )
        goto LABEL_41;
    }
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
    0x203u,
    "ClipStorage::RemoveLeaseDocumentWithIdAndReason",
    (wchar_t *)L"Removing lease document with file ID %s and reason 0x%08x");
  v25 = (__int64 *)*((_QWORD *)this + 2);
  v26 = *v25;
  v27 = v39;
  if ( !v39 )
  {
    v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v39);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\ClipHelpers.h",
        (const char *)(unsigned int)v28,
        Formatb);
    v27 = v39;
  }
  v29 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *))(v26 + 88))(v25, v27, &v56);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
      (const char *)(unsigned int)v29,
      Formatb);
  v30 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  }
  v31 = (volatile signed __int32 *)v45;
  if ( v45 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 32LL))(v38);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  v41 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  if ( v42 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v41) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    RaiseException(v32, 1u, 0, 0);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x18000e470  mov     r11, rsp
0x18000e473  push    rbx
0x18000e474  push    rsi
0x18000e475  push    rdi
0x18000e476  push    r12
0x18000e478  push    r13
0x18000e47a  push    r14
0x18000e47c  push    r15
0x18000e47e  sub     rsp, 220h
0x18000e485  mov     rax, cs:__security_cookie
0x18000e48c  xor     rax, rsp
0x18000e48f  mov     [rsp+258h+var_48], rax
0x18000e497  mov     r13d, r8d
0x18000e49a  mov     rsi, rdx
0x18000e49d  mov     rdi, rcx
0x18000e4a0  xor     r14d, r14d
0x18000e4a3  xorps   xmm0, xmm0
0x18000e4a6  movups  xmmword ptr [r11-58h], xmm0
0x18000e4ab  lea     rdx, [r11-58h]; pclsid
0x18000e4af  mov     rcx, rsi; lpsz
0x18000e4b2  call    cs:__imp_CLSIDFromString
0x18000e4b8  mov     rcx, [rsp+258h]; this
0x18000e4c0  test    eax, eax
0x18000e4c2  jns     short loc_18000E4D8
0x18000e4c4  mov     r9d, eax; char *
0x18000e4c7  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e4ce  mov     edx, 1DAh; void *
0x18000e4d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e4d8  mov     r9, rsi
0x18000e4db  lea     r8, aFileid; "FileId"
0x18000e4e2  lea     rdx, a12S; "%1=%2!s!"
0x18000e4e9  lea     rcx, [rsp+258h+var_1F0]
0x18000e4ee  call    CreateQuery
0x18000e4f3  nop
0x18000e4f4  mov     rcx, [rdi+10h]
0x18000e4f8  mov     [rsp+258h+var_208], rcx
0x18000e4fd  test    rcx, rcx
0x18000e500  jz      short loc_18000E50F
0x18000e502  mov     rax, [rcx]
0x18000e505  mov     rax, [rax+8]
0x18000e509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50e  nop
0x18000e50f  mov     [rsp+258h+var_200], r14
0x18000e514  mov     ecx, 20h ; ' '; Size
0x18000e519  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e51e  mov     dword ptr [rax+8], 1
0x18000e525  mov     dword ptr [rax+0Ch], 1
0x18000e52c  lea     rcx, ??_7?$_Ref_count_obj2@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable'
0x18000e533  mov     [rax], rcx
0x18000e536  lea     rbx, [rax+10h]
0x18000e53a  lea     rcx, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000e541  mov     [rbx], rcx
0x18000e544  mov     [rbx+8], r14
0x18000e548  mov     qword ptr [rsp+258h+var_1D8], rbx
0x18000e550  mov     [rsp+258h+var_1D0], rax
0x18000e558  mov     r14, [rdi+10h]
0x18000e55c  mov     r15, [r14]
0x18000e55f  mov     r12, [rsp+258h+var_1E8]
0x18000e564  mov     rdx, [rsp+258h+var_200]
0x18000e569  test    rdx, rdx
0x18000e56c  jnz     short loc_18000E5A9
0x18000e56e  mov     rcx, [rsp+258h+var_208]
0x18000e573  mov     rax, [rcx]
0x18000e576  lea     rdx, [rsp+258h+var_200]
0x18000e57b  mov     rax, [rax+18h]
0x18000e57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e584  mov     rcx, [rsp+258h]; this
0x18000e58c  test    eax, eax
0x18000e58e  jns     short loc_18000E5A4
0x18000e590  mov     r9d, eax; char *
0x18000e593  lea     r8, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e59a  mov     edx, 81h; void *
0x18000e59f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e5a4  mov     rdx, [rsp+258h+var_200]
0x18000e5a9  add     rbx, 8
0x18000e5ad  mov     [rsp+258h+Format], rbx; int
0x18000e5b2  xor     r9d, r9d
0x18000e5b5  mov     r8, r12
0x18000e5b8  mov     rcx, r14
0x18000e5bb  mov     rax, [r15+40h]
0x18000e5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c4  mov     rcx, [rsp+258h]; this
0x18000e5cc  test    eax, eax
0x18000e5ce  jns     short loc_18000E5E4
0x18000e5d0  mov     r9d, eax; char *
0x18000e5d3  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e5da  mov     edx, 1E0h; void *
0x18000e5df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e5e4  mov     rax, [rbx]
0x18000e5e7  test    rax, rax
0x18000e5ea  jz      loc_18000EA30
0x18000e5f0  cmp     dword ptr [rax], 0
0x18000e5f3  jbe     loc_18000EA30
0x18000e5f9  cmp     dword ptr [rax+4], 6
0x18000e5fd  jnz     loc_18000EA30
0x18000e603  xor     r14d, r14d
0x18000e606  mov     [rsp+258h+var_1F8], r14d
0x18000e60b  mov     [rsp+258h+var_218], r14d
0x18000e610  mov     [rsp+258h+var_1C8], r14
0x18000e618  mov     rax, [rdi+10h]
0x18000e61c  mov     [rsp+258h+var_1E0], rax
0x18000e621  lea     rax, [rsp+258h+var_1D8]
0x18000e629  mov     [rsp+258h+Format], rax; int
0x18000e62e  lea     r9, [rsp+258h+var_218]
0x18000e633  lea     r8, [rsp+258h+var_1C8]
0x18000e63b  lea     rdx, [rsp+258h+var_1E0]
0x18000e640  lea     rcx, [rsp+258h+var_210]
0x18000e645  call    ??$MakeCom@VClipLeaseDocument@@PEAUIClipStore@@$$THAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@@YA?AV?$ComPtr@VClipLeaseDocument@@@WRL@Microsoft@@$$QEAPEAUIClipStore@@$$QEA$$T$$QEAHAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@Z
0x18000e64a  nop
0x18000e64b  mov     rcx, [rsp+258h+var_210]
0x18000e650  mov     rax, [rcx]
0x18000e653  lea     rdx, [rsp+258h+var_1F8]
0x18000e658  mov     rax, [rax+58h]
0x18000e65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e661  mov     rcx, [rsp+258h]; this
0x18000e669  test    eax, eax
0x18000e66b  jns     short loc_18000E681
0x18000e66d  mov     r9d, eax; char *
0x18000e670  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e677  mov     edx, 1E9h; void *
0x18000e67c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e681  cmp     [rsp+258h+var_1F8], 3
0x18000e686  jz      loc_18000E8A4
0x18000e68c  mov     [rsp+258h+var_218], r14d
0x18000e691  mov     rcx, [rsp+258h+var_210]
0x18000e696  add     rcx, 8
0x18000e69a  mov     rax, [rcx]
0x18000e69d  lea     rdx, [rsp+258h+var_218]
0x18000e6a2  mov     rax, [rax+98h]
0x18000e6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ae  mov     rcx, [rsp+258h]; this
0x18000e6b6  test    eax, eax
0x18000e6b8  jns     short loc_18000E6CE
0x18000e6ba  mov     r9d, eax; char *
0x18000e6bd  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e6c4  mov     edx, 1EEh; void *
0x18000e6c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e6ce  cmp     [rsp+258h+var_218], 0
0x18000e6d3  jz      loc_18000E7D4
0x18000e6d9  mov     eax, r13d
0x18000e6dc  and     eax, 0F000h
0x18000e6e1  cmp     eax, 8000h
0x18000e6e6  jnz     short loc_18000E700
0x18000e6e8  mov     eax, r13d
0x18000e6eb  and     eax, 1FFF0000h
0x18000e6f0  cmp     eax, 3F0000h
0x18000e6f5  jnz     short loc_18000E700
0x18000e6f7  test    r13d, r13d
0x18000e6fa  js      loc_18000E7D4
0x18000e700  mov     dword ptr [rsp+258h+var_230], r13d
0x18000e705  lea     rax, aIgnoringLeaseR; "Ignoring lease removal with reason 0x%0"...
0x18000e70c  mov     [rsp+258h+Format], rax; Format
0x18000e711  lea     r9, aClipstorageRem; "ClipStorage::RemoveLeaseDocumentWithIdA"...
0x18000e718  mov     r8d, 1F5h; unsigned int
0x18000e71e  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e725  mov     ecx, 3; unsigned int
0x18000e72a  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000e72f  nop
0x18000e730  mov     rcx, [rsp+258h+var_210]
0x18000e735  test    rcx, rcx
0x18000e738  jz      short loc_18000E74C
0x18000e73a  mov     [rsp+258h+var_210], r14
0x18000e73f  mov     rax, [rcx]
0x18000e742  mov     rax, [rax+10h]
0x18000e746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e74b  nop
0x18000e74c  mov     rcx, [rsp+258h+var_1D0]; this
0x18000e754  test    rcx, rcx
0x18000e757  jz      short loc_18000E75F
0x18000e759  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e75e  nop
0x18000e75f  mov     rdx, [rsp+258h+var_200]
0x18000e764  test    rdx, rdx
0x18000e767  jz      short loc_18000E77A
0x18000e769  mov     rcx, [rsp+258h+var_208]
0x18000e76e  mov     rax, [rcx]
0x18000e771  mov     rax, [rax+20h]
0x18000e775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e77a  lea     rcx, [rsp+258h+var_208]
0x18000e77f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e784  nop
0x18000e785  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000e78c  mov     [rsp+258h+var_1F0], rax
0x18000e791  cmp     [rsp+258h+var_1E8], 0
0x18000e797  jz      short loc_18000E7CD
0x18000e799  lea     rcx, [rsp+258h+var_1F0]
0x18000e79e  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x18000e7a3  test    al, al
0x18000e7a5  jnz     short loc_18000E7CD
0x18000e7a7  call    cs:__imp_GetLastError
0x18000e7ad  test    eax, eax
0x18000e7af  jle     short loc_18000E7B9
0x18000e7b1  movzx   eax, ax
0x18000e7b4  or      eax, 80070000h
0x18000e7b9  xor     r9d, r9d; lpArguments
0x18000e7bc  xor     r8d, r8d; nNumberOfArguments
0x18000e7bf  mov     edx, 1; dwExceptionFlags
0x18000e7c4  mov     ecx, eax; dwExceptionCode
0x18000e7c6  call    cs:__imp_RaiseException
0x18000e7cc  int     3; Trap to Debugger
0x18000e7cd  xor     eax, eax
0x18000e7cf  jmp     loc_18000EB0B
0x18000e7d4  mov     ecx, r13d
0x18000e7d7  and     ecx, 0F000h
0x18000e7dd  cmp     ecx, 8000h
0x18000e7e3  jnz     short loc_18000E7FD
0x18000e7e5  mov     eax, r13d
0x18000e7e8  and     eax, 1FFF0000h
0x18000e7ed  cmp     eax, 3F0000h
0x18000e7f2  jnz     short loc_18000E81D
0x18000e7f4  test    r13d, r13d
0x18000e7f7  js      loc_18000E8A4
0x18000e7fd  cmp     ecx, 9000h
0x18000e803  jnz     short loc_18000E81D
0x18000e805  mov     eax, r13d
0x18000e808  and     eax, 1FFF0000h
0x18000e80d  cmp     eax, 3F0000h
0x18000e812  jnz     short loc_18000E81D
0x18000e814  test    r13d, r13d
0x18000e817  js      loc_18000E8A4
0x18000e81d  mov     dword ptr [rsp+258h+var_230], r13d
0x18000e822  lea     rax, aIgnoringLeaseR_0; "Ignoring lease removal request with rea"...
0x18000e829  mov     [rsp+258h+Format], rax; Format
0x18000e82e  lea     r9, aClipstorageRem; "ClipStorage::RemoveLeaseDocumentWithIdA"...
0x18000e835  mov     r8d, 1FEh; unsigned int
0x18000e83b  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e842  mov     ecx, 3; unsigned int
0x18000e847  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000e84c  nop
0x18000e84d  mov     rcx, [rsp+258h+var_210]
0x18000e852  test    rcx, rcx
0x18000e855  jz      short loc_18000E869
0x18000e857  mov     [rsp+258h+var_210], r14
0x18000e85c  mov     rax, [rcx]
0x18000e85f  mov     rax, [rax+10h]
0x18000e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e868  nop
0x18000e869  mov     rcx, [rsp+258h+var_1D0]; this
0x18000e871  test    rcx, rcx
0x18000e874  jz      short loc_18000E87C
0x18000e876  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e87b  nop
0x18000e87c  lea     rcx, [rsp+258h+var_208]; this
0x18000e881  call    ??1HClip@@QEAA@XZ; HClip::~HClip(void)
0x18000e886  nop
0x18000e887  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000e88e  mov     [rsp+258h+var_1F0], rax
0x18000e893  lea     rcx, [rsp+258h+var_1F0]
0x18000e898  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18000e89d  xor     eax, eax
0x18000e89f  jmp     loc_18000EB0B
0x18000e8a4  mov     [rsp+258h+var_228], r13d
0x18000e8a9  mov     [rsp+258h+var_230], rsi
0x18000e8ae  lea     rax, aRemovingLeaseD; "Removing lease document with file ID %s"...
0x18000e8b5  mov     [rsp+258h+Format], rax; int
0x18000e8ba  lea     r9, aClipstorageRem; "ClipStorage::RemoveLeaseDocumentWithIdA"...
0x18000e8c1  mov     r8d, 203h; unsigned int
0x18000e8c7  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e8ce  mov     ecx, 3; unsigned int
0x18000e8d3  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000e8d8  mov     rbx, [rdi+10h]
0x18000e8dc  mov     rdi, [rbx]
0x18000e8df  mov     rdx, [rsp+258h+var_200]
0x18000e8e4  test    rdx, rdx
0x18000e8e7  jnz     short loc_18000E924
0x18000e8e9  mov     rcx, [rsp+258h+var_208]
0x18000e8ee  mov     rax, [rcx]
0x18000e8f1  lea     rdx, [rsp+258h+var_200]
0x18000e8f6  mov     rax, [rax+18h]
0x18000e8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ff  mov     rcx, [rsp+258h]; this
0x18000e907  test    eax, eax
0x18000e909  jns     short loc_18000E91F
0x18000e90b  mov     r9d, eax; char *
0x18000e90e  lea     r8, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e915  mov     edx, 81h; void *
0x18000e91a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e91f  mov     rdx, [rsp+258h+var_200]
0x18000e924  lea     r8, [rsp+258h+var_58]
0x18000e92c  mov     rcx, rbx
0x18000e92f  mov     rax, [rdi+58h]
0x18000e933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e938  mov     rcx, [rsp+258h]; this
0x18000e940  test    eax, eax
0x18000e942  jns     short loc_18000E959
0x18000e944  mov     r9d, eax; char *
0x18000e947  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000e94e  mov     edx, 204h; void *
0x18000e953  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e959  mov     rcx, [rsp+258h+var_210]
0x18000e95e  test    rcx, rcx
0x18000e961  jz      short loc_18000E975
0x18000e963  mov     [rsp+258h+var_210], r14
0x18000e968  mov     rax, [rcx]
0x18000e96b  mov     rax, [rax+10h]
0x18000e96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e974  nop
0x18000e975  mov     rbx, [rsp+258h+var_1D0]
0x18000e97d  test    rbx, rbx
0x18000e980  jz      short loc_18000E9BB
  ... truncated ...
```
