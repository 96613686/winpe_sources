# AppInstallBroker::IsAppInInstallQueue(HSTRING__ *,uchar,uchar *)

- ea: `0x1802161b0`
- end: `0x180216490`
- name: `?IsAppInInstallQueue@AppInstallBroker@@UEAAJPEAUHSTRING__@@EPEAE@Z`
- size: `736`
- prototype: `int(AppInstallBroker *__hidden this, HSTRING, unsigned __int8, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180035a98`
- `0x1800f0eb4`
- `0x18020e5bc`
- `0x180211a48`
- `0x1802161b0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18021635a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18021635a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802162f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802163b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802163d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216484`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802162f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802163b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802163d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180216484`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021632b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021633f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021632b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021633f`

## string_xrefs

- `0x180216202`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180216236`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802163ef`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021643e`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021646f`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`

## pseudocode

```c
__int64 __fastcall AppInstallBroker::IsAppInInstallQueue(
        AppInstallBroker *this,
        HSTRING a2,
        char a3,
        unsigned __int8 *a4)
{
  AppInstallBroker *v7; // rcx
  int AppInstallManager; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  int v17; // esi
  int v18; // r13d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v23; // rax
  int v24; // eax
  HSTRING v25; // rcx
  bool v26; // zf
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  HSTRING v30; // r8
  int v31; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-31h] BYREF
  __int64 v36; // [rsp+40h] [rbp-29h] BYREF
  __int64 v37; // [rsp+48h] [rbp-21h] BYREF
  char *v38; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal *v39; // [rsp+58h] [rbp-11h] BYREF
  __int64 v40; // [rsp+60h] [rbp-9h] BYREF
  int v41; // [rsp+68h] [rbp-1h] BYREF
  char **v42; // [rsp+70h] [rbp+7h]
  int v43; // [rsp+78h] [rbp+Fh]
  _QWORD v44[8]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  AppInstallBroker *v46; // [rsp+D0h] [rbp+67h] BYREF
  UINT32 length; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = this;
  *a4 = 0;
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  AppInstallManager = AppInstallBroker::GetAppInstallManager(v7, &v39);
  v9 = AppInstallManager;
  if ( AppInstallManager < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
      (const char *)(unsigned int)AppInstallManager,
      bIgnoreCase);
    goto LABEL_23;
  }
  v37 = 0;
  v10 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal>::As<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(
          &v39,
          &v37);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    goto LABEL_22;
  }
  v36 = 0;
  v11 = v37;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  v13 = v12(v11, &v36);
  v9 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
    v15 = 258;
    goto LABEL_20;
  }
  LODWORD(v38) = 0;
  v40 = v36;
  v42 = &v38;
  v43 = 0;
  v44[0] = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 56LL))(v36, &v41);
  *(_DWORD *)v42 = v16;
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
    &v40,
    0);
  v17 = 0;
  v18 = v41;
  while ( 1 )
  {
    if ( *(int *)v42 < 0 || v17 == v18 )
      goto LABEL_18;
    if ( a3 )
    {
      string = 0;
      v19 = v44[0];
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44[0] + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v21 = v20(v19, &string);
      v9 = v21;
      if ( v21 >= 0 )
      {
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
        LODWORD(v46) = 0;
        v23 = WindowsGetStringRawBuffer(string, (UINT32 *)&v46);
        v24 = CompareStringOrdinal(StringRawBuffer, length, v23, (int)v46, 1);
        v25 = string;
        v26 = v24 == 2;
        goto LABEL_15;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      WindowsDeleteString(string);
      string = 0;
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
      goto LABEL_21;
    }
    v35 = 0;
    v27 = v44[0];
    v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44[0] + 56LL);
    WindowsDeleteString(0);
    v35 = 0;
    v29 = v28(v27, &v35);
    v9 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)v29,
        bIgnoreCase);
      WindowsDeleteString(v35);
      v35 = 0;
      goto LABEL_25;
    }
    v31 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal((Microsoft::WRL::Wrappers::Details *)v35, a2, v30);
    v25 = v35;
    v26 = v31 == 0;
LABEL_15:
    if ( v26 )
      break;
    WindowsDeleteString(v25);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
      &v40,
      (unsigned int)++v17);
  }
  *a4 = 1;
  WindowsDeleteString(v25);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
  v9 = (unsigned int)v38;
  if ( (int)v38 >= 0 )
    goto LABEL_21;
  v14 = (unsigned int)v38;
  v15 = 294;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
    (const char *)v14,
    bIgnoreCase);
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
LABEL_22:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_23:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  return v9;
}

```

## disassembly

```asm
0x1802161b0  mov     [rsp-8+arg_8], rbx
0x1802161b5  mov     [rsp-8+arg_0], rcx
0x1802161ba  push    rbp
0x1802161bb  push    rsi
0x1802161bc  push    rdi
0x1802161bd  push    r12
0x1802161bf  push    r13
0x1802161c1  push    r14
0x1802161c3  push    r15
0x1802161c5  lea     rbp, [rsp-27h]
0x1802161ca  sub     rsp, 90h
0x1802161d1  mov     r14, r9
0x1802161d4  mov     r12b, r8b
0x1802161d7  mov     r15, rdx
0x1802161da  xor     edi, edi
0x1802161dc  mov     [r9], dil
0x1802161df  mov     [rbp+57h+var_68], rdi
0x1802161e3  lea     rcx, [rbp+57h+var_68]
0x1802161e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802161ec  lea     rdx, [rbp+57h+var_68]; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal **
0x1802161f0  call    ?GetAppInstallManager@AppInstallBroker@@AEAAJPEAPEAUIAppInstallManagerInternal@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; AppInstallBroker::GetAppInstallManager(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal * *)
0x1802161f5  mov     ebx, eax
0x1802161f7  test    eax, eax
0x1802161f9  jns     short loc_180216218
0x1802161fb  mov     rcx, [rbp+5Fh]; this
0x1802161ff  mov     r9d, eax; char *
0x180216202  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216209  mov     edx, 0FCh; void *
0x18021620e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216213  jmp     loc_180216411
0x180216218  mov     [rbp+57h+var_78], rdi
0x18021621c  lea     rdx, [rbp+57h+var_78]
0x180216220  lea     rcx, [rbp+57h+var_68]
0x180216224  call    ??$As@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@?$ComPtr@UIAppInstallManagerInternal@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal>::As<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x180216229  mov     ebx, eax
0x18021622b  test    eax, eax
0x18021622d  jns     short loc_18021624C
0x18021622f  mov     rcx, [rbp+5Fh]; this
0x180216233  mov     r9d, eax; char *
0x180216236  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021623d  mov     edx, 0FFh; void *
0x180216242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216247  jmp     loc_180216408
0x18021624c  mov     [rbp+57h+var_80], rdi
0x180216250  mov     rdi, [rbp+57h+var_78]
0x180216254  mov     rax, [rdi]
0x180216257  mov     rbx, [rax+30h]
0x18021625b  lea     rcx, [rbp+57h+var_80]
0x18021625f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216264  lea     rdx, [rbp+57h+var_80]
0x180216268  mov     rcx, rdi
0x18021626b  mov     rax, rbx
0x18021626e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216273  mov     ebx, eax
0x180216275  xor     edi, edi
0x180216277  test    eax, eax
0x180216279  jns     short loc_180216288
0x18021627b  mov     r9d, eax
0x18021627e  mov     edx, 102h
0x180216283  jmp     loc_1802163EF
0x180216288  mov     dword ptr [rbp+57h+var_70], edi
0x18021628b  mov     rcx, [rbp+57h+var_80]
0x18021628f  mov     [rbp+57h+var_60], rcx
0x180216293  lea     rax, [rbp+57h+var_70]
0x180216297  mov     [rbp+57h+var_50], rax
0x18021629b  mov     [rbp+57h+var_48], edi
0x18021629e  mov     [rbp+57h+var_40], rdi
0x1802162a2  mov     rax, [rcx]
0x1802162a5  lea     rdx, [rbp+57h+var_58]
0x1802162a9  mov     rax, [rax+38h]
0x1802162ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802162b2  mov     rcx, [rbp+57h+var_50]
0x1802162b6  mov     [rcx], eax
0x1802162b8  xor     edx, edx
0x1802162ba  lea     rcx, [rbp+57h+var_60]
0x1802162be  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x1802162c3  mov     esi, edi
0x1802162c5  mov     r13d, [rbp+57h+var_58]
0x1802162c9  mov     rax, [rbp+57h+var_50]
0x1802162cd  cmp     [rax], edi
0x1802162cf  jl      loc_1802163D7
0x1802162d5  cmp     esi, r13d
0x1802162d8  jz      loc_1802163D7
0x1802162de  xor     ecx, ecx; string
0x1802162e0  test    r12b, r12b
0x1802162e3  jz      loc_180216369
0x1802162e9  mov     [rbp+57h+string], rdi
0x1802162ed  mov     rdi, [rbp+57h+var_40]
0x1802162f1  mov     rax, [rdi]
0x1802162f4  mov     rbx, [rax+30h]
0x1802162f8  call    cs:__imp_WindowsDeleteString
0x1802162fe  mov     [rbp+57h+string], 0
0x180216306  lea     rdx, [rbp+57h+string]
0x18021630a  mov     rcx, rdi
0x18021630d  mov     rax, rbx
0x180216310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216315  mov     ebx, eax
0x180216317  xor     edi, edi
0x180216319  test    eax, eax
0x18021631b  js      loc_180216437
0x180216321  mov     [rbp+57h+length], edi
0x180216324  lea     rdx, [rbp+57h+length]; length
0x180216328  mov     rcx, r15; string
0x18021632b  call    cs:__imp_WindowsGetStringRawBuffer
0x180216331  mov     rbx, rax
0x180216334  mov     dword ptr [rbp+57h+arg_0], edi
0x180216337  lea     rdx, [rbp+57h+arg_0]; length
0x18021633b  mov     rcx, [rbp+57h+string]; string
0x18021633f  call    cs:__imp_WindowsGetStringRawBuffer
0x180216345  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18021634d  mov     r9d, dword ptr [rbp+57h+arg_0]; cchCount2
0x180216351  mov     r8, rax; lpString2
0x180216354  mov     edx, [rbp+57h+length]; cchCount1
0x180216357  mov     rcx, rbx; lpString1
0x18021635a  call    cs:__imp_CompareStringOrdinal
0x180216360  mov     rcx, [rbp+57h+string]
0x180216364  cmp     eax, 2
0x180216367  jmp     short loc_1802163B3
0x180216369  mov     [rbp+57h+var_88], rdi
0x18021636d  mov     rdi, [rbp+57h+var_40]
0x180216371  mov     rax, [rdi]
0x180216374  mov     rbx, [rax+38h]
0x180216378  call    cs:__imp_WindowsDeleteString
0x18021637e  mov     [rbp+57h+var_88], 0
0x180216386  lea     rdx, [rbp+57h+var_88]
0x18021638a  mov     rcx, rdi
0x18021638d  mov     rax, rbx
0x180216390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216395  mov     ebx, eax
0x180216397  xor     edi, edi
0x180216399  test    eax, eax
0x18021639b  js      loc_180216468
0x1802163a1  mov     rdx, r15; HSTRING
0x1802163a4  mov     rcx, [rbp+57h+var_88]; this
0x1802163a8  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802163ad  mov     rcx, [rbp+57h+var_88]; string
0x1802163b1  test    eax, eax
0x1802163b3  jz      short loc_1802163CD
0x1802163b5  call    cs:__imp_WindowsDeleteString
0x1802163bb  inc     esi
0x1802163bd  mov     edx, esi
0x1802163bf  lea     rcx, [rbp+57h+var_60]
0x1802163c3  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVStoreAvailability@Store@Services@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(uint)
0x1802163c8  jmp     loc_1802162C9
0x1802163cd  mov     byte ptr [r14], 1
0x1802163d1  call    cs:__imp_WindowsDeleteString
0x1802163d7  lea     rcx, [rbp+57h+var_40]
0x1802163db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802163e0  mov     ebx, dword ptr [rbp+57h+var_70]
0x1802163e3  test    ebx, ebx
0x1802163e5  jns     short loc_1802163FF
0x1802163e7  mov     r9d, ebx; char *
0x1802163ea  mov     edx, 126h; void *
0x1802163ef  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802163f6  mov     rcx, [rbp+5Fh]; this
0x1802163fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802163ff  lea     rcx, [rbp+57h+var_80]
0x180216403  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216408  lea     rcx, [rbp+57h+var_78]
0x18021640c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216411  lea     rcx, [rbp+57h+var_68]
0x180216415  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021641a  mov     eax, ebx
0x18021641c  mov     rbx, [rsp+0C0h+arg_8]
0x180216424  add     rsp, 90h
0x18021642b  pop     r15
0x18021642d  pop     r14
0x18021642f  pop     r13
0x180216431  pop     r12
0x180216433  pop     rdi
0x180216434  pop     rsi
0x180216435  pop     rbp
0x180216436  retn
0x180216437  mov     rcx, [rbp+5Fh]; this
0x18021643b  mov     r9d, eax; char *
0x18021643e  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216445  mov     edx, 10Ch; void *
0x18021644a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021644f  mov     rcx, [rbp+57h+string]; string
0x180216453  call    cs:__imp_WindowsDeleteString
0x180216459  mov     [rbp+57h+string], rdi
0x18021645d  lea     rcx, [rbp+57h+var_40]
0x180216461  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216466  jmp     short loc_1802163FF
0x180216468  mov     rcx, [rbp+5Fh]; this
0x18021646c  mov     r9d, eax; char *
0x18021646f  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180216476  mov     edx, 11Dh; void *
0x18021647b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180216480  mov     rcx, [rbp+57h+var_88]; string
0x180216484  call    cs:__imp_WindowsDeleteString
0x18021648a  mov     [rbp+57h+var_88], rdi
0x18021648e  jmp     short loc_18021645D
```
