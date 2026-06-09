# TokenUtility::DuplicateHandleFromBrokerProcess(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,void *)

- ea: `0x180030df0`
- end: `0x1800310aa`
- name: `?DuplicateHandleFromBrokerProcess@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAX@Z`
- size: `698`
- prototype: `HANDLE *__fastcall(void *, HANDLE *, __int64, DWORD, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012770`

## callees

- `0x18001255c`
- `0x18001cfd4`
- `0x18001d058`
- `0x18001d0a0`
- `0x180023264`
- `0x1800291d0`
- `0x18002b28c`
- `0x180030df0`
- `0x1800322f4`
- `0x1800323d4`
- `0x18003286c`
- `0x1800355f0`
- `0x1800358a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031023`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180030f53`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003104d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180030f53`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003104d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030ea1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030ea1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030e60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030ed2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030e60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030ed2`

## string_xrefs

- `0x180030e2f`: `ImpersonateUser failed!`
- `0x180030e3e`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030e85`: `Invalid broker process information!`

## pseudocode

```c
HANDLE *__fastcall TokenUtility::DuplicateHandleFromBrokerProcess(
        void *a1,
        HANDLE *a2,
        __int64 a3,
        DWORD a4,
        HANDLE hSourceHandle)
{
  unsigned int v7; // eax
  HANDLE v8; // rax
  HANDLE v9; // rbx
  PrintScanBrokerUtilities *v10; // rcx
  DWORD CallerProcessId; // eax
  HANDLE v12; // rax
  HANDLE v13; // rdi
  HANDLE CurrentProcess; // rax
  unsigned int v15; // eax
  TokenUtility *v16; // rcx
  enum HandleType v17; // r8d
  enum HandleType v18; // r8d
  char v19; // al
  __int64 v20; // rdx
  TokenUtility *v21; // rcx
  HANDLE v22; // rbx
  HANDLE v23; // rax
  unsigned int v24; // eax
  const char *bInheritHandle; // [rsp+28h] [rbp-38h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-38h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-38h]
  const char *bInheritHandlec; // [rsp+28h] [rbp-38h]
  const char *bInheritHandled; // [rsp+28h] [rbp-38h]
  const char *dwOptions; // [rsp+30h] [rbp-30h]
  HANDLE TargetHandle; // [rsp+48h] [rbp-18h] BYREF
  HANDLE hSourceProcessHandle[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE hTargetProcessHandle; // [rsp+80h] [rbp+20h] BYREF
  HANDLE *v36; // [rsp+88h] [rbp+28h]

  v36 = a2;
  hTargetProcessHandle = a1;
  hSourceProcessHandle[0] = 0;
  v7 = PrintCore::UserImpersonationHelpers::ImpersonateUser(a3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x91,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v7,
    (int)"ImpersonateUser failed!",
    bInheritHandle);
  BYTE1(hTargetProcessHandle) = 1;
  v8 = OpenProcess(0x40u, 0, a4);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    hSourceProcessHandle,
    v8);
  v9 = hSourceProcessHandle[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x98,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)((unsigned __int64)hSourceProcessHandle[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Invalid broker process information!",
    bInheritHandleb);
  RevertToSelf();
  hTargetProcessHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    CallerProcessId = PrintScanBrokerUtilities::GetCallerProcessId(v10);
  else
    CallerProcessId = TokenUtility::_GetCallerProcessId(v10);
  v12 = OpenProcess(0x40u, 0, CallerProcessId);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hTargetProcessHandle,
    v12);
  v13 = hTargetProcessHandle;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xA4,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)((char *)hTargetProcessHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL),
    (bool)"Invalid client process information!",
    bInheritHandlea);
  TargetHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v15 = DuplicateHandle(v9, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v15,
    (int)"DuplicateHandle failed!",
    bInheritHandlec);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    v19 = !PrintScanBrokerUtilities::IsValidHandleType(TargetHandle, 0, v17)
       && !PrintScanBrokerUtilities::IsValidHandleType(TargetHandle, (void *)1, v18);
    v20 = 173;
  }
  else
  {
    v19 = !TokenUtility::_IsValidHandleType(v16, TargetHandle, (enum HandleType)0)
       && !TokenUtility::_IsValidHandleType(v21, TargetHandle, Asymmetric);
    v20 = 177;
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)0x80070006LL,
    v19,
    (bool)"Invalid handle type!",
    dwOptions);
  *a2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  v22 = TargetHandle;
  v23 = GetCurrentProcess();
  v24 = DuplicateHandle(v23, v22, v13, a2, 0, 0, 2u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0xB5,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v24,
    (int)"DuplicateHandle failed!",
    bInheritHandled);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hTargetProcessHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hSourceProcessHandle);
  return a2;
}

```

## disassembly

```asm
0x180030df0  mov     rax, rsp
0x180030df3  mov     [rax+18h], rbx
0x180030df7  mov     [rax+20h], rsi
0x180030dfb  mov     [rax+10h], rdx
0x180030dff  mov     [rax+8], rcx
0x180030e03  push    rbp
0x180030e04  push    rdi
0x180030e05  push    r12
0x180030e07  mov     rbp, rsp
0x180030e0a  sub     rsp, 60h
0x180030e0e  mov     ebx, r9d
0x180030e11  mov     rsi, rdx
0x180030e14  mov     [rbp+var_20], 0
0x180030e1b  mov     [rbp+hSourceProcessHandle], 0
0x180030e23  mov     rcx, r8
0x180030e26  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180030e2b  mov     rcx, [rbp+18h]; this
0x180030e2f  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180030e36  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; int
0x180030e3b  mov     r9d, eax; char *
0x180030e3e  lea     r12, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030e45  mov     r8, r12; unsigned int
0x180030e48  mov     edx, 91h; void *
0x180030e4d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030e52  mov     byte ptr [rbp+hTargetProcessHandle+1], 1
0x180030e56  mov     r8d, ebx; dwProcessId
0x180030e59  xor     edx, edx; bInheritHandle
0x180030e5b  lea     edi, [rdx+40h]
0x180030e5e  mov     ecx, edi; dwDesiredAccess
0x180030e60  call    cs:__imp_OpenProcess
0x180030e66  mov     rdx, rax
0x180030e69  lea     rcx, [rbp+hSourceProcessHandle]
0x180030e6d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030e72  mov     rbx, [rbp+hSourceProcessHandle]
0x180030e76  lea     rax, [rbx-1]
0x180030e7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030e7e  setnbe  al
0x180030e81  mov     rcx, [rbp+18h]; this
0x180030e85  lea     rdx, aInvalidBrokerP; "Invalid broker process information!"
0x180030e8c  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; bool
0x180030e91  movzx   r9d, al; char *
0x180030e95  mov     r8, r12; unsigned int
0x180030e98  lea     edx, [rdi+58h]; void *
0x180030e9b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180030ea0  nop
0x180030ea1  call    cs:__imp_RevertToSelf
0x180030ea7  mov     [rbp+hTargetProcessHandle], 0
0x180030eaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180030eb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180030ebb  test    al, al
0x180030ebd  jz      short loc_180030EC6
0x180030ebf  call    ?GetCallerProcessId@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerProcessId(void)
0x180030ec4  jmp     short loc_180030ECB
0x180030ec6  call    ?_GetCallerProcessId@TokenUtility@@AEAAKXZ; TokenUtility::_GetCallerProcessId(void)
0x180030ecb  mov     r8d, eax; dwProcessId
0x180030ece  xor     edx, edx; bInheritHandle
0x180030ed0  mov     ecx, edi; dwDesiredAccess
0x180030ed2  call    cs:__imp_OpenProcess
0x180030ed8  mov     rdx, rax
0x180030edb  lea     rcx, [rbp+hTargetProcessHandle]
0x180030edf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030ee4  mov     rdi, [rbp+hTargetProcessHandle]
0x180030ee8  lea     rax, [rdi-1]
0x180030eec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030ef0  setnbe  al
0x180030ef3  mov     rcx, [rbp+18h]; this
0x180030ef7  lea     rdx, aInvalidClientP; "Invalid client process information!"
0x180030efe  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; bool
0x180030f03  movzx   r9d, al; char *
0x180030f07  mov     r8, r12; unsigned int
0x180030f0a  mov     edx, 0A4h; void *
0x180030f0f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180030f14  mov     [rbp+TargetHandle], 0
0x180030f1c  xor     edx, edx
0x180030f1e  lea     rcx, [rbp+TargetHandle]
0x180030f22  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030f27  call    cs:__imp_GetCurrentProcess
0x180030f2d  mov     [rsp+60h+dwOptions], 2; char *
0x180030f35  mov     [rsp+60h+bInheritHandle], 0; char *
0x180030f3d  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180030f45  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180030f49  mov     r8, rax; hTargetProcessHandle
0x180030f4c  mov     rdx, [rbp+hSourceHandle]; hSourceHandle
0x180030f50  mov     rcx, rbx; hSourceProcessHandle
0x180030f53  call    cs:__imp_DuplicateHandle
0x180030f59  mov     rcx, [rbp+18h]; this
0x180030f5d  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x180030f64  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; int
0x180030f69  mov     r9d, eax; char *
0x180030f6c  mov     r8, r12; unsigned int
0x180030f6f  mov     edx, 0A9h; void *
0x180030f74  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180030f79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180030f80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180030f85  test    al, al
0x180030f87  jz      short loc_180030FB7
0x180030f89  xor     edx, edx; void *
0x180030f8b  mov     rcx, [rbp+TargetHandle]; hFile
0x180030f8f  call    ?IsValidHandleType@PrintScanBrokerUtilities@@YA_NPEAXW4HandleType@1@@Z; PrintScanBrokerUtilities::IsValidHandleType(void *,PrintScanBrokerUtilities::HandleType)
0x180030f94  test    al, al
0x180030f96  jnz     short loc_180030FAE
0x180030f98  mov     edx, 1; void *
0x180030f9d  mov     rcx, [rbp+TargetHandle]; hFile
0x180030fa1  call    ?IsValidHandleType@PrintScanBrokerUtilities@@YA_NPEAXW4HandleType@1@@Z; PrintScanBrokerUtilities::IsValidHandleType(void *,PrintScanBrokerUtilities::HandleType)
0x180030fa6  test    al, al
0x180030fa8  jnz     short loc_180030FAE
0x180030faa  mov     al, 1
0x180030fac  jmp     short loc_180030FB0
0x180030fae  xor     al, al
0x180030fb0  mov     edx, 0ADh
0x180030fb5  jmp     short loc_180030FE5
0x180030fb7  xor     r8d, r8d; enum HandleType
0x180030fba  mov     rdx, [rbp+TargetHandle]; void *
0x180030fbe  call    ?_IsValidHandleType@TokenUtility@@AEAA_NPEAXW4HandleType@@@Z; TokenUtility::_IsValidHandleType(void *,HandleType)
0x180030fc3  test    al, al
0x180030fc5  jnz     short loc_180030FDE
0x180030fc7  mov     r8d, 1; enum HandleType
0x180030fcd  mov     rdx, [rbp+TargetHandle]; void *
0x180030fd1  call    ?_IsValidHandleType@TokenUtility@@AEAA_NPEAXW4HandleType@@@Z; TokenUtility::_IsValidHandleType(void *,HandleType)
0x180030fd6  test    al, al
0x180030fd8  jnz     short loc_180030FDE
0x180030fda  mov     al, 1
0x180030fdc  jmp     short loc_180030FE0
0x180030fde  xor     al, al
0x180030fe0  mov     edx, 0B1h; void *
0x180030fe5  mov     rcx, [rbp+18h]; this
0x180030fe9  lea     r8, aInvalidHandleT; "Invalid handle type!"
0x180030ff0  mov     qword ptr [rsp+60h+bInheritHandle], r8; bool
0x180030ff5  mov     byte ptr [rsp+60h+dwDesiredAccess], al; char
0x180030ff9  mov     r9d, 80070006h; char *
0x180030fff  mov     r8, r12; unsigned int
0x180031002  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180031007  mov     qword ptr [rsi], 0
0x18003100e  mov     [rbp+var_20], 1
0x180031015  xor     edx, edx
0x180031017  mov     rcx, rsi
0x18003101a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003101f  mov     rbx, [rbp+TargetHandle]
0x180031023  call    cs:__imp_GetCurrentProcess
0x180031029  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180031031  mov     [rsp+60h+bInheritHandle], 0; char *
0x180031039  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180031041  mov     r9, rsi; lpTargetHandle
0x180031044  mov     r8, rdi; hTargetProcessHandle
0x180031047  mov     rdx, rbx; hSourceHandle
0x18003104a  mov     rcx, rax; hSourceProcessHandle
0x18003104d  call    cs:__imp_DuplicateHandle
0x180031053  mov     rcx, [rbp+18h]; this
0x180031057  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x18003105e  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; int
0x180031063  mov     r9d, eax; char *
0x180031066  mov     r8, r12; unsigned int
0x180031069  mov     edx, 0B5h; void *
0x18003106e  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180031073  nop
0x180031074  lea     rcx, [rbp+TargetHandle]
0x180031078  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003107d  nop
0x18003107e  lea     rcx, [rbp+hTargetProcessHandle]
0x180031082  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031087  nop
0x180031088  lea     rcx, [rbp+hSourceProcessHandle]
0x18003108c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031091  mov     rax, rsi
0x180031094  lea     r11, [rsp+60h+var_s0]
0x180031099  mov     rbx, [r11+30h]
0x18003109d  mov     rsi, [r11+38h]
0x1800310a1  mov     rsp, r11
0x1800310a4  pop     r12
0x1800310a6  pop     rdi
0x1800310a7  pop     rbp
0x1800310a8  retn
```
