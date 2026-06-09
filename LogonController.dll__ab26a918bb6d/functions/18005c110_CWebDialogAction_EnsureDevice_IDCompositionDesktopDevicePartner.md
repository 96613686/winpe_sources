# CWebDialogAction::_EnsureDevice(IDCompositionDesktopDevicePartner * *)

- ea: `0x18005c110`
- end: `0x18005c3ad`
- name: `?_EnsureDevice@CWebDialogAction@@AEAAJPEAPEAUIDCompositionDesktopDevicePartner@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(CWebDialogAction *__hidden this, struct IDCompositionDesktopDevicePartner **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005c5f4`

## callees

- `0x180017dec`
- `0x18001db70`
- `0x18001f3a0`
- `0x18001fde8`
- `0x180026e70`
- `0x18002f554`
- `0x1800440d0`
- `0x18005a9a0`
- `0x18005b3e4`
- `0x18005c110`
- `0x18005c3b4`
- `0x18005d488`
- `0x18006c000`
- `0x18008b654`
- `0x18008b894`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18005c1dc`
- `KERNEL32!LoadLibraryExW` at `0x18005c1dc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c1fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c271`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c372`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c1fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c271`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c372`

## string_xrefs

- `0x18005c1cf`: `dcomp.dll`

## pseudocode

```c
__int64 __fastcall CWebDialogAction::_EnsureDevice(
        CWebDialogAction *this,
        struct IDCompositionDesktopDevicePartner **a2)
{
  HINSTANCE *v4; // rdi
  HMODULE Library; // rax
  unsigned int v6; // ebx
  CWebDialogAction *v7; // rcx
  int v8; // eax
  HINSTANCE v9; // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  struct IDCompositionDevice *v15; // [rsp+20h] [rbp-E0h] BYREF
  struct IDXGIDevice1 *v16; // [rsp+28h] [rbp-D8h] BYREF
  struct _GUID Buf1; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "CWebDialogAction__EnsureDevice_Activity");
  v18[0] = &LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v18,
      &Buf1);
  LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::StartActivity((LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity *)v18);
  *a2 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&Buf1, (char *)this + 296);
  v4 = (HINSTANCE *)((char *)this + 352);
  if ( !*((_QWORD *)this + 44) )
  {
    Library = LoadLibraryExW(L"dcomp.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 352,
      Library);
    if ( !*v4 )
    {
      if ( *(_QWORD *)&Buf1.Data1 )
        ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
      v6 = -2147467263;
      goto LABEL_28;
    }
  }
  if ( !*((_QWORD *)this + 38) )
  {
    v16 = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v16);
    v8 = CWebDialogAction::_InitializeDCompDeviceSupport(v7, &v16);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v8,
        (int)v15);
LABEL_11:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v16);
      goto LABEL_12;
    }
    v9 = *v4;
    v15 = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
    v10 = OS_DCompositionCreateDevice2((struct IDXGIDevice *)v16, &v15, v9);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 547;
LABEL_16:
      v12 = (unsigned int)v10;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)v12,
        (int)v15);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
      goto LABEL_11;
    }
    if ( !v15 )
    {
      v6 = -2147024882;
      v11 = 548;
      v12 = 2147942414LL;
      goto LABEL_17;
    }
    v10 = Microsoft::WRL::ComPtr<IDCompositionDevice>::As<IDCompositionDesktopDevicePartner>(&v15, (char *)this + 304);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 550;
      goto LABEL_16;
    }
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v16);
  }
  v13 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IDCompositionDesktopDevicePartner **))this + 38))(
          *((_QWORD *)this + 38),
          &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0,
          a2);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
      (const char *)(unsigned int)v13,
      (int)v15);
LABEL_12:
    if ( *(_QWORD *)&Buf1.Data1 )
      ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
    goto LABEL_28;
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, 0);
  if ( *(_QWORD *)&Buf1.Data1 )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
  v6 = 0;
LABEL_28:
  LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::~CWebDialogAction__EnsureDevice_Activity((LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity *)v18);
  return v6;
}

```

## disassembly

```asm
0x18005c110  mov     [rsp-8+arg_10], rbx
0x18005c115  mov     [rsp-8+arg_18], rsi
0x18005c11a  push    rbp
0x18005c11b  push    rdi
0x18005c11c  push    r14
0x18005c11e  lea     rbp, [rsp-0A0h]
0x18005c126  sub     rsp, 1A0h
0x18005c12d  mov     rax, cs:__security_cookie
0x18005c134  xor     rax, rsp
0x18005c137  mov     [rbp+0B0h+var_20], rax
0x18005c13e  mov     r14, rdx
0x18005c141  mov     rsi, rcx
0x18005c144  lea     rdx, aCwebdialogacti_3; "CWebDialogAction__EnsureDevice_Activity"
0x18005c14b  lea     rcx, [rsp+1B0h+var_170]
0x18005c150  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005c155  lea     rax, ??_7CWebDialogAction__EnsureDevice_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::`vftable'
0x18005c15c  lea     rcx, [rsp+1B0h+Buf1]; retstr
0x18005c161  mov     [rsp+1B0h+var_170], rax
0x18005c166  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18005c16b  mov     r8d, 10h; Size
0x18005c171  lea     rdx, GUID_NULL; Buf2
0x18005c178  lea     rcx, [rsp+1B0h+Buf1]; Buf1
0x18005c17d  movups  xmm0, xmmword ptr [rax]
0x18005c180  movdqu  [rsp+1B0h+Buf1], xmm0
0x18005c186  call    memcmp_0
0x18005c18b  test    eax, eax
0x18005c18d  jz      short loc_18005C19E
0x18005c18f  lea     rdx, [rsp+1B0h+Buf1]
0x18005c194  lea     rcx, [rsp+1B0h+var_170]
0x18005c199  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18005c19e  lea     rcx, [rsp+1B0h+var_170]; this
0x18005c1a3  call    ?StartActivity@CWebDialogAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::StartActivity(void)
0x18005c1a8  lea     rdx, [rsi+128h]
0x18005c1af  mov     qword ptr [r14], 0
0x18005c1b6  lea     rcx, [rsp+1B0h+Buf1]
0x18005c1bb  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005c1c0  lea     rdi, [rsi+160h]
0x18005c1c7  cmp     qword ptr [rdi], 0
0x18005c1cb  jnz     short loc_18005C20D
0x18005c1cd  xor     edx, edx; hFile
0x18005c1cf  lea     rcx, aDcompDll; "dcomp.dll"
0x18005c1d6  mov     r8d, 800h; dwFlags
0x18005c1dc  call    cs:__imp_LoadLibraryExW
0x18005c1e2  mov     rdx, rax
0x18005c1e5  mov     rcx, rdi
0x18005c1e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18005c1ed  cmp     qword ptr [rdi], 0
0x18005c1f1  jnz     short loc_18005C20D
0x18005c1f3  mov     rcx, qword ptr [rsp+1B0h+Buf1]; SRWLock
0x18005c1f8  test    rcx, rcx
0x18005c1fb  jz      short loc_18005C203
0x18005c1fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c203  mov     ebx, 80004001h
0x18005c208  jmp     loc_18005C37A
0x18005c20d  cmp     qword ptr [rsi+130h], 0
0x18005c215  jnz     loc_18005C31A
0x18005c21b  lea     rcx, [rsp+1B0h+var_188]
0x18005c220  mov     [rsp+1B0h+var_188], 0
0x18005c229  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c22e  lea     rdx, [rsp+1B0h+var_188]; struct IDXGIDevice1 **
0x18005c233  call    ?_InitializeDCompDeviceSupport@CWebDialogAction@@AEAAJPEAPEAUIDXGIDevice1@@@Z; CWebDialogAction::_InitializeDCompDeviceSupport(IDXGIDevice1 * *)
0x18005c238  mov     ebx, eax
0x18005c23a  test    eax, eax
0x18005c23c  jns     short loc_18005C27C
0x18005c23e  mov     rcx, [rbp+0B8h]; this
0x18005c245  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c24c  mov     r9d, eax; char *
0x18005c24f  mov     edx, 21Fh; void *
0x18005c254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c259  lea     rcx, [rsp+1B0h+var_188]
0x18005c25e  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c263  mov     rcx, qword ptr [rsp+1B0h+Buf1]; SRWLock
0x18005c268  test    rcx, rcx
0x18005c26b  jz      loc_18005C37A
0x18005c271  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c277  jmp     loc_18005C37A
0x18005c27c  mov     rbx, [rdi]
0x18005c27f  lea     rcx, [rsp+1B0h+var_190]
0x18005c284  mov     [rsp+1B0h+var_190], 0; int
0x18005c28d  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c292  mov     rcx, [rsp+1B0h+var_188]; struct IDXGIDevice *
0x18005c297  lea     rdx, [rsp+1B0h+var_190]; struct IDCompositionDevice **
0x18005c29c  mov     r8, rbx; HINSTANCE
0x18005c29f  call    ?OS_DCompositionCreateDevice2@@YAJPEAUIDXGIDevice@@PEAPEAUIDCompositionDevice@@PEAUHINSTANCE__@@@Z; OS_DCompositionCreateDevice2(IDXGIDevice *,IDCompositionDevice * *,HINSTANCE__ *)
0x18005c2a4  mov     ebx, eax
0x18005c2a6  test    eax, eax
0x18005c2a8  jns     short loc_18005C2D1
0x18005c2aa  mov     edx, 223h; void *
0x18005c2af  mov     r9d, eax; char *
0x18005c2b2  mov     rcx, [rbp+0B8h]; this
0x18005c2b9  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c2c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c2c5  lea     rcx, [rsp+1B0h+var_190]
0x18005c2ca  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c2cf  jmp     short loc_18005C259
0x18005c2d1  cmp     [rsp+1B0h+var_190], 0
0x18005c2d7  jnz     short loc_18005C2E8
0x18005c2d9  mov     ebx, 8007000Eh
0x18005c2de  mov     edx, 224h
0x18005c2e3  mov     r9d, ebx
0x18005c2e6  jmp     short loc_18005C2B2
0x18005c2e8  lea     rdx, [rsi+130h]
0x18005c2ef  lea     rcx, [rsp+1B0h+var_190]
0x18005c2f4  call    ??$As@UIDCompositionDesktopDevicePartner@@@?$ComPtr@UIDCompositionDevice@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionDesktopDevicePartner@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IDCompositionDevice>::As<IDCompositionDesktopDevicePartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionDesktopDevicePartner>>)
0x18005c2f9  mov     ebx, eax
0x18005c2fb  test    eax, eax
0x18005c2fd  jns     short loc_18005C306
0x18005c2ff  mov     edx, 226h
0x18005c304  jmp     short loc_18005C2AF
0x18005c306  lea     rcx, [rsp+1B0h+var_190]
0x18005c30b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c310  lea     rcx, [rsp+1B0h+var_188]
0x18005c315  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c31a  mov     rcx, [rsi+130h]
0x18005c321  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x18005c328  mov     r8, r14
0x18005c32b  mov     rax, [rcx]
0x18005c32e  mov     rax, [rax]
0x18005c331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c336  mov     ebx, eax
0x18005c338  test    eax, eax
0x18005c33a  jns     short loc_18005C35C
0x18005c33c  mov     rcx, [rbp+0B8h]; this
0x18005c343  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c34a  mov     r9d, eax; char *
0x18005c34d  mov     edx, 229h; void *
0x18005c352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c357  jmp     loc_18005C263
0x18005c35c  xor     edx, edx
0x18005c35e  lea     rcx, [rsp+1B0h+var_170]
0x18005c363  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005c368  mov     rcx, qword ptr [rsp+1B0h+Buf1]; SRWLock
0x18005c36d  test    rcx, rcx
0x18005c370  jz      short loc_18005C378
0x18005c372  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c378  xor     ebx, ebx
0x18005c37a  lea     rcx, [rsp+1B0h+var_170]; this
0x18005c37f  call    ??1CWebDialogAction__EnsureDevice_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CWebDialogAction__EnsureDevice_Activity::~CWebDialogAction__EnsureDevice_Activity(void)
0x18005c384  mov     eax, ebx
0x18005c386  mov     rcx, [rbp+0B0h+var_20]
0x18005c38d  xor     rcx, rsp; StackCookie
0x18005c390  call    __security_check_cookie
0x18005c395  lea     r11, [rsp+1B0h+var_10]
0x18005c39d  mov     rbx, [r11+30h]
0x18005c3a1  mov     rsi, [r11+38h]
0x18005c3a5  mov     rsp, r11
0x18005c3a8  pop     r14
0x18005c3aa  pop     rdi
0x18005c3ab  pop     rbp
0x18005c3ac  retn
```
