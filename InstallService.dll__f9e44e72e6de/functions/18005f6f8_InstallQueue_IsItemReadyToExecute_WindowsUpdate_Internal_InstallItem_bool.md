# InstallQueue::_IsItemReadyToExecute(WindowsUpdate::Internal::InstallItem *,bool *)

- ea: `0x18005f6f8`
- end: `0x18005fa93`
- name: `?_IsItemReadyToExecute@InstallQueue@@AEAAJPEAVInstallItem@Internal@WindowsUpdate@@PEA_N@Z`
- size: `923`
- prototype: `int(InstallQueue *__hidden this, struct WindowsUpdate::Internal::InstallItem *, bool *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005cf90`
- `0x180062724`

## callees

- `0x1800101f4`
- `0x18001c414`
- `0x18002ec2c`
- `0x180051f0c`
- `0x180052188`
- `0x1800522cc`
- `0x1800538d0`
- `0x180056bdc`
- `0x180056d64`
- `0x18005bccc`
- `0x18005f6f8`
- `0x180062dfc`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f74f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f74f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f9a3`

## string_xrefs

- `0x18005f737`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005f81f`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005f977`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005f9de`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005f9d1`: `InstallQueue::_IsItemReadyToExecute`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall InstallQueue::_IsItemReadyToExecute(InstallQueue *this, HSTRING *a2, bool *a3)
{
  int IsReady; // eax
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, WindowsUpdate::Internal::InstallItem **); // rbx
  int v10; // eax
  WindowsUpdate::Internal::InstallItem *v11; // rdi
  __int64 (__fastcall *v12)(WindowsUpdate::Internal::InstallItem *, HSTRING *); // rbx
  int v13; // eax
  bool v14; // r8
  HSTRING v15; // rcx
  PCWSTR StringRawBuffer; // rbx
  const char *v17; // r14
  unsigned int updated; // eax
  PCWSTR v19; // rbx
  PCWSTR v20; // rax
  const char *v21; // r9
  __int64 result; // rax
  int v23; // [rsp+20h] [rbp-88h]
  WindowsUpdate::Internal::InstallItem *v24; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-48h] BYREF
  int v27; // [rsp+68h] [rbp-40h]
  __int64 v28; // [rsp+78h] [rbp-30h] BYREF
  int v29; // [rsp+80h] [rbp-28h]
  __int64 v30; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v32; // [rsp+C0h] [rbp+18h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+20h] BYREF

  *a3 = 0;
  try
  {
    IsReady = WindowsUpdate::Internal::InstallItem::IsReady((WindowsUpdate::Internal::InstallItem *)a2, a3);
    if ( IsReady < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)IsReady,
        v23);
    WindowsDeleteString(0);
    v25 = 0;
    if ( (*(unsigned int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)a2[12] + 152LL))(a2[12], &v25) == -2147023728
      || !v25 )
    {
      WindowsDeleteString(v25);
      result = 0;
    }
    else
    {
      v32 = (*((_QWORD *)this + 25) + 16LL) & -(__int64)(*((_QWORD *)this + 25) != 0);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::begin(
        &v32,
        v26);
      v28 = 0;
      v29 = -1;
      v30 = 0;
      while ( v27 != -1 )
      {
        v7 = wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::operator*(v26);
        v24 = 0;
        v8 = *(_QWORD *)v7;
        v9 = *(__int64 (__fastcall **)(__int64, WindowsUpdate::Internal::InstallItem **))(**(_QWORD **)v7 + 56LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
        v10 = v9(v8, &v24);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x432,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v10,
            v23);
        v11 = v24;
        string = 0;
        v12 = *(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, HSTRING *))(*(_QWORD *)v24 + 112LL);
        WindowsDeleteString(0);
        string = 0;
        v13 = v12(v11, &string);
        v15 = string;
        if ( v13 != -2147023728 && string && *((HSTRING *)v11 + 11) != a2[11] )
        {
          if ( StringHelpers::Equal(string, v25, v14) )
          {
            LODWORD(v32) = 0;
            if ( (*(int (__fastcall **)(WindowsUpdate::Internal::InstallItem *, __int64 *))(*(_QWORD *)v24 + 56LL))(
                   v24,
                   &v32) >= 0
              && (_DWORD)v32 != 1 )
            {
              *a3 = 0;
              _m_prefetchw((char *)v11 + 312);
              if ( (_InterlockedOr((volatile signed __int32 *)v11 + 78, 0) & 1) == 0 )
              {
                _m_prefetchw(a2 + 39);
                if ( (_InterlockedOr((volatile signed __int32 *)a2 + 78, 0) & 1) != 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v11 + 31), 0);
                  v17 = (const char *)WindowsGetStringRawBuffer(a2[31], 0);
                  updated = WindowsUpdate::Internal::InstallItem::UpdateProperties(v11, 0, 1u, 0);
                  wil::details::in1diag3::Log_IfFailedMsg(
                    retaddr,
                    (void *)0x44F,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                    (const char *)updated,
                    (int)"Product = %ls is interactive. Marking Dependency productId = %ls as interactive too",
                    v17,
                    StringRawBuffer);
                }
              }
              v19 = WindowsGetStringRawBuffer(*((HSTRING *)v11 + 31), 0);
              v20 = WindowsGetStringRawBuffer(a2[31], 0);
              LogMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                0x451u,
                "InstallQueue::_IsItemReadyToExecute",
                -1,
                L"productId = %s is a DLC and waiting on its MainPackage productId = %s",
                0,
                0,
                v20,
                v19);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
              break;
            }
          }
          v15 = string;
        }
        WindowsDeleteString(v15);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::operator++(v26);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v28);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v26);
      WindowsDeleteString(v25);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(v32) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x458,
                     (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                     v21);
    return (unsigned int)v32;
  }
  return result;
}

```

## disassembly

```asm
0x18005f6f8  mov     [rsp+arg_0], rbx
0x18005f6fd  mov     [rsp+arg_8], rsi
0x18005f702  push    rdi
0x18005f703  push    r14
0x18005f705  push    r15
0x18005f707  sub     rsp, 90h
0x18005f70e  mov     r14, r8
0x18005f711  mov     rsi, rdx
0x18005f714  mov     rbx, rcx
0x18005f717  xor     r15d, r15d
0x18005f71a  mov     [r8], r15b
0x18005f71d  mov     rdx, r8; bool *
0x18005f720  mov     rcx, rsi; this
0x18005f723  call    ?IsReady@InstallItem@Internal@WindowsUpdate@@QEAAJPEA_N@Z; WindowsUpdate::Internal::InstallItem::IsReady(bool *)
0x18005f728  mov     rcx, [rsp+0A8h]; this
0x18005f730  test    eax, eax
0x18005f732  jns     short loc_18005F748
0x18005f734  mov     r9d, eax; char *
0x18005f737  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005f73e  mov     edx, 426h; void *
0x18005f743  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f748  mov     [rsp+0A8h+var_50], r15
0x18005f74d  xor     ecx, ecx; string
0x18005f74f  call    cs:__imp_WindowsDeleteString
0x18005f755  mov     [rsp+0A8h+var_50], r15
0x18005f75a  mov     rcx, [rsi+60h]
0x18005f75e  mov     rax, [rcx]
0x18005f761  lea     rdx, [rsp+0A8h+var_50]
0x18005f766  mov     rax, [rax+98h]
0x18005f76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f772  mov     rcx, [rsp+0A8h+var_50]; string
0x18005f777  cmp     eax, 80070490h
0x18005f77c  jz      loc_18005FA36
0x18005f782  test    rcx, rcx
0x18005f785  jz      loc_18005FA36
0x18005f78b  mov     rax, [rbx+0C8h]
0x18005f792  lea     rcx, [rax+10h]
0x18005f796  neg     rax
0x18005f799  sbb     rax, rax
0x18005f79c  and     rax, rcx
0x18005f79f  mov     [rsp+0A8h+arg_10], rax
0x18005f7a7  lea     rdx, [rsp+0A8h+var_48]
0x18005f7ac  lea     rcx, [rsp+0A8h+arg_10]
0x18005f7b4  call    ?begin@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AViterable_iterator@12@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::begin(void)
0x18005f7b9  nop
0x18005f7ba  mov     [rsp+0A8h+var_30], r15
0x18005f7bf  mov     [rsp+0A8h+var_28], 0FFFFFFFFh
0x18005f7ca  mov     [rsp+0A8h+var_20], r15
0x18005f7d2  cmp     [rsp+0A8h+var_40], 0FFFFFFFFh
0x18005f7d7  jz      loc_18005FA11
0x18005f7dd  lea     rcx, [rsp+0A8h+var_48]
0x18005f7e2  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x18005f7e7  mov     [rsp+0A8h+var_58], r15
0x18005f7ec  mov     rdi, [rax]
0x18005f7ef  mov     rax, [rdi]
0x18005f7f2  mov     rbx, [rax+38h]
0x18005f7f6  lea     rcx, [rsp+0A8h+var_58]
0x18005f7fb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005f800  lea     rdx, [rsp+0A8h+var_58]
0x18005f805  mov     rcx, rdi
0x18005f808  mov     rax, rbx
0x18005f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f810  mov     rcx, [rsp+0A8h]; this
0x18005f818  test    eax, eax
0x18005f81a  jns     short loc_18005F830
0x18005f81c  mov     r9d, eax; char *
0x18005f81f  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005f826  mov     edx, 432h; void *
0x18005f82b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005f830  mov     rdi, [rsp+0A8h+var_58]
0x18005f835  mov     [rsp+0A8h+string], r15
0x18005f83d  mov     rax, [rdi]
0x18005f840  mov     rbx, [rax+70h]
0x18005f844  xor     ecx, ecx; string
0x18005f846  call    cs:__imp_WindowsDeleteString
0x18005f84c  mov     [rsp+0A8h+string], r15
0x18005f854  lea     rdx, [rsp+0A8h+string]
0x18005f85c  mov     rcx, rdi
0x18005f85f  mov     rax, rbx
0x18005f862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f867  mov     rcx, [rsp+0A8h+string]; HSTRING
0x18005f86f  cmp     eax, 80070490h
0x18005f874  jz      loc_18005FA6A
0x18005f87a  test    rcx, rcx
0x18005f87d  jz      loc_18005FA6A
0x18005f883  mov     rax, [rsi+58h]
0x18005f887  cmp     [rdi+58h], rax
0x18005f88b  jz      loc_18005FA6A
0x18005f891  mov     rdx, [rsp+0A8h+var_50]; HSTRING
0x18005f896  call    ?Equal@StringHelpers@@SA_NPEAUHSTRING__@@0_N@Z; StringHelpers::Equal(HSTRING__ *,HSTRING__ *,bool)
0x18005f89b  test    al, al
0x18005f89d  jz      loc_18005FA60
0x18005f8a3  mov     dword ptr [rsp+0A8h+arg_10], r15d
0x18005f8ab  mov     rcx, [rsp+0A8h+var_58]
0x18005f8b0  mov     rax, [rcx]
0x18005f8b3  lea     rdx, [rsp+0A8h+arg_10]
0x18005f8bb  mov     rax, [rax+38h]
0x18005f8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f8c4  test    eax, eax
0x18005f8c6  js      loc_18005FA60
0x18005f8cc  cmp     dword ptr [rsp+0A8h+arg_10], 1
0x18005f8d4  jz      loc_18005FA60
0x18005f8da  mov     [r14], r15b
0x18005f8dd  prefetchw byte ptr [rdi+138h]
0x18005f8e4  mov     eax, [rdi+138h]
0x18005f8ea  mov     ecx, eax
0x18005f8ec  or      ecx, r15d
0x18005f8ef  lock cmpxchg [rdi+138h], ecx
0x18005f8f7  jnz     short loc_18005F8EA
0x18005f8f9  test    al, 1
0x18005f8fb  jnz     loc_18005F988
0x18005f901  prefetchw byte ptr [rsi+138h]
0x18005f908  mov     eax, [rsi+138h]
0x18005f90e  mov     ecx, eax
0x18005f910  or      ecx, r15d
0x18005f913  lock cmpxchg [rsi+138h], ecx
0x18005f91b  jnz     short loc_18005F90E
0x18005f91d  test    al, 1
0x18005f91f  jz      short loc_18005F988
0x18005f921  xor     edx, edx; length
0x18005f923  mov     rcx, [rdi+0F8h]; string
0x18005f92a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f930  mov     rbx, rax
0x18005f933  xor     edx, edx; length
0x18005f935  mov     rcx, [rsi+0F8h]; string
0x18005f93c  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f942  mov     r14, rax
0x18005f945  xor     r9d, r9d; unsigned int
0x18005f948  xor     edx, edx; HSTRING
0x18005f94a  lea     r8d, [r9+1]; unsigned int
0x18005f94e  mov     rcx, rdi; this
0x18005f951  call    ?UpdateProperties@InstallItem@Internal@WindowsUpdate@@QEAAJPEAUHSTRING__@@KK@Z; WindowsUpdate::Internal::InstallItem::UpdateProperties(HSTRING__ *,ulong,ulong)
0x18005f956  mov     rcx, [rsp+0A8h]; this
0x18005f95e  mov     [rsp+0A8h+var_78], rbx
0x18005f963  mov     [rsp+0A8h+var_80], r14; char *
0x18005f968  lea     rdx, aProductLsIsInt; "Product = %ls is interactive. Marking D"...
0x18005f96f  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x18005f974  mov     r9d, eax; char *
0x18005f977  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005f97e  mov     edx, 44Fh; void *
0x18005f983  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005f988  xor     edx, edx; length
0x18005f98a  mov     rcx, [rdi+0F8h]; string
0x18005f991  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f997  mov     rbx, rax
0x18005f99a  xor     edx, edx; length
0x18005f99c  mov     rcx, [rsi+0F8h]; string
0x18005f9a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f9a9  mov     [rsp+0A8h+var_60], rbx
0x18005f9ae  mov     [rsp+0A8h+var_68], rax
0x18005f9b3  mov     [rsp+0A8h+var_70], r15; unsigned __int16 *
0x18005f9b8  mov     [rsp+0A8h+var_78], r15; char *
0x18005f9bd  lea     rax, aProductidSIsAD; "productId = %s is a DLC and waiting on "...
0x18005f9c4  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18005f9c9  mov     [rsp+0A8h+var_88], 0FFFFFFFFh; int
0x18005f9d1  lea     r9, aInstallqueueIs; "InstallQueue::_IsItemReadyToExecute"
0x18005f9d8  mov     r8d, 451h; unsigned int
0x18005f9de  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005f9e5  mov     ecx, 3; unsigned int
0x18005f9ea  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005f9ef  nop
0x18005f9f0  mov     rcx, [rsp+0A8h+string]; string
0x18005f9f8  call    cs:__imp_WindowsDeleteString
0x18005f9fe  mov     [rsp+0A8h+string], r15
0x18005fa06  lea     rcx, [rsp+0A8h+var_58]
0x18005fa0b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005fa10  nop
0x18005fa11  lea     rcx, [rsp+0A8h+var_30]
0x18005fa16  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18005fa1b  nop
0x18005fa1c  lea     rcx, [rsp+0A8h+var_48]
0x18005fa21  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18005fa26  nop
0x18005fa27  mov     rcx, [rsp+0A8h+var_50]; string
0x18005fa2c  call    cs:__imp_WindowsDeleteString
0x18005fa32  xor     eax, eax
0x18005fa34  jmp     short loc_18005FA47
0x18005fa36  call    cs:__imp_WindowsDeleteString
0x18005fa3c  xor     eax, eax
0x18005fa3e  jmp     short loc_18005FA47
0x18005fa40  mov     eax, dword ptr [rsp+0A8h+arg_10]
0x18005fa47  lea     r11, [rsp+0A8h+var_18]
0x18005fa4f  mov     rbx, [r11+20h]
0x18005fa53  mov     rsi, [r11+28h]
0x18005fa57  mov     rsp, r11
0x18005fa5a  pop     r15
0x18005fa5c  pop     r14
0x18005fa5e  pop     rdi
0x18005fa5f  retn
0x18005fa60  mov     rcx, [rsp+0A8h+string]
0x18005fa68  jmp     short $+2
0x18005fa6a  call    cs:__imp_WindowsDeleteString
0x18005fa70  mov     [rsp+0A8h+string], r15
0x18005fa78  lea     rcx, [rsp+0A8h+var_58]
0x18005fa7d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005fa82  lea     rcx, [rsp+0A8h+var_48]
0x18005fa87  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,WindowsUpdate::Internal::IInstallItem *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x18005fa8c  jmp     loc_18005F7D2
```
