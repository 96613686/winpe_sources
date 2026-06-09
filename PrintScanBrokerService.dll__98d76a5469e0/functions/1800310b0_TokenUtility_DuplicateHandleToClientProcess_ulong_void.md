# TokenUtility::DuplicateHandleToClientProcess(ulong,void *)

- ea: `0x1800310b0`
- end: `0x1800312ed`
- name: `?DuplicateHandleToClientProcess@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KPEAX@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009a50`

## callees

- `0x18001255c`
- `0x18001cfd4`
- `0x18001d0a0`
- `0x180023264`
- `0x18002b28c`
- `0x1800310b0`
- `0x1800322f4`
- `0x1800323d4`
- `0x18003286c`
- `0x1800355f0`
- `0x1800358a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003119e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003119e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031267`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800311c9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031291`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800311c9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031291`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800310e1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180031149`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800310e1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180031149`

## string_xrefs

- `0x18003110c`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HANDLE *__fastcall TokenUtility::DuplicateHandleToClientProcess(void *a1, HANDLE *a2, DWORD a3, void *a4)
{
  char *v6; // rdi
  PrintScanBrokerUtilities *v7; // rcx
  DWORD CallerProcessId; // eax
  HANDLE v9; // rax
  HANDLE v10; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v12; // eax
  TokenUtility *v13; // rcx
  enum HandleType v14; // r8d
  unsigned int v15; // esi
  bool IsValidHandleType; // al
  HANDLE v17; // rbx
  HANDLE v18; // rax
  unsigned int v19; // eax
  const char *bInheritHandle; // [rsp+28h] [rbp-38h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-38h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-38h]
  const char *bInheritHandlec; // [rsp+28h] [rbp-38h]
  const char *dwOptions; // [rsp+30h] [rbp-30h]
  HANDLE hSourceProcessHandle; // [rsp+48h] [rbp-18h] BYREF
  void *v27; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HANDLE TargetHandle; // [rsp+90h] [rbp+30h] BYREF
  HANDLE *v30; // [rsp+98h] [rbp+38h]

  v30 = a2;
  TargetHandle = a1;
  v6 = (char *)OpenProcess(0x40u, 0, a3);
  v27 = v6;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x6B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)((unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Invalid client process information!",
    bInheritHandle);
  hSourceProcessHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    CallerProcessId = PrintScanBrokerUtilities::GetCallerProcessId(v7);
  else
    CallerProcessId = TokenUtility::_GetCallerProcessId(v7);
  v9 = OpenProcess(0x40u, 0, CallerProcessId);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hSourceProcessHandle,
    v9);
  v10 = hSourceProcessHandle;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x76,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)((char *)hSourceProcessHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL),
    (bool)"Invalid spooler process information!",
    bInheritHandlea);
  TargetHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v12 = DuplicateHandle(v10, a4, CurrentProcess, &TargetHandle, 0, 0, 2u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v12,
    (int)"DuplicateHandle failed!",
    bInheritHandleb);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    v15 = 126;
    IsValidHandleType = PrintScanBrokerUtilities::IsValidHandleType(TargetHandle, 0, v14);
  }
  else
  {
    v15 = 130;
    IsValidHandleType = TokenUtility::_IsValidHandleType(v13, TargetHandle, (enum HandleType)0);
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)v15,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)0x80070006LL,
    !IsValidHandleType,
    (bool)"Invalid handle type!",
    dwOptions);
  *a2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  v17 = TargetHandle;
  v18 = GetCurrentProcess();
  v19 = DuplicateHandle(v18, v17, v6, a2, 0, 0, 2u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x86,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v19,
    (int)"DuplicateHandle failed!",
    bInheritHandlec);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSourceProcessHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
  return a2;
}

```

## disassembly

```asm
0x1800310b0  mov     [rsp-28h+arg_10], rbx
0x1800310b5  mov     [rsp-28h+arg_8], rdx
0x1800310ba  mov     [rsp-28h+TargetHandle], rcx
0x1800310bf  push    rbp
0x1800310c0  push    rsi
0x1800310c1  push    rdi
0x1800310c2  push    r12
0x1800310c4  push    r14
0x1800310c6  mov     rbp, rsp
0x1800310c9  sub     rsp, 60h
0x1800310cd  mov     rsi, r9
0x1800310d0  mov     r14, rdx
0x1800310d3  mov     [rbp+var_20], 0
0x1800310da  xor     edx, edx; bInheritHandle
0x1800310dc  lea     ebx, [rdx+40h]
0x1800310df  mov     ecx, ebx; dwDesiredAccess
0x1800310e1  call    cs:__imp_OpenProcess
0x1800310e7  mov     rdi, rax
0x1800310ea  mov     [rbp+var_10], rax
0x1800310ee  dec     rax
0x1800310f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800310f5  setnbe  al
0x1800310f8  mov     rcx, [rbp+28h]; this
0x1800310fc  lea     rdx, aInvalidClientP; "Invalid client process information!"
0x180031103  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; bool
0x180031108  movzx   r9d, al; char *
0x18003110c  lea     r12, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180031113  mov     r8, r12; unsigned int
0x180031116  lea     edx, [rbx+2Bh]; void *
0x180031119  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18003111e  mov     [rbp+hSourceProcessHandle], 0
0x180031126  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x18003112d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180031132  test    al, al
0x180031134  jz      short loc_18003113D
0x180031136  call    ?GetCallerProcessId@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerProcessId(void)
0x18003113b  jmp     short loc_180031142
0x18003113d  call    ?_GetCallerProcessId@TokenUtility@@AEAAKXZ; TokenUtility::_GetCallerProcessId(void)
0x180031142  mov     r8d, eax; dwProcessId
0x180031145  xor     edx, edx; bInheritHandle
0x180031147  mov     ecx, ebx; dwDesiredAccess
0x180031149  call    cs:__imp_OpenProcess
0x18003114f  mov     rdx, rax
0x180031152  lea     rcx, [rbp+hSourceProcessHandle]
0x180031156  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003115b  mov     rbx, [rbp+hSourceProcessHandle]
0x18003115f  lea     rax, [rbx-1]
0x180031163  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031167  setnbe  al
0x18003116a  mov     rcx, [rbp+28h]; this
0x18003116e  lea     rdx, aInvalidSpooler; "Invalid spooler process information!"
0x180031175  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; bool
0x18003117a  movzx   r9d, al; char *
0x18003117e  mov     r8, r12; unsigned int
0x180031181  mov     edx, 76h ; 'v'; void *
0x180031186  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18003118b  mov     [rbp+TargetHandle], 0
0x180031193  xor     edx, edx
0x180031195  lea     rcx, [rbp+TargetHandle]
0x180031199  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003119e  call    cs:__imp_GetCurrentProcess
0x1800311a4  mov     [rsp+60h+dwOptions], 2; char *
0x1800311ac  mov     [rsp+60h+bInheritHandle], 0; char *
0x1800311b4  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x1800311bc  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1800311c0  mov     r8, rax; hTargetProcessHandle
0x1800311c3  mov     rdx, rsi; hSourceHandle
0x1800311c6  mov     rcx, rbx; hSourceProcessHandle
0x1800311c9  call    cs:__imp_DuplicateHandle
0x1800311cf  mov     rcx, [rbp+28h]; this
0x1800311d3  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x1800311da  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; int
0x1800311df  mov     r9d, eax; char *
0x1800311e2  mov     r8, r12; unsigned int
0x1800311e5  mov     edx, 7Bh ; '{'; void *
0x1800311ea  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800311ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800311f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800311fb  mov     rbx, [rbp+28h]
0x1800311ff  test    al, al
0x180031201  jz      short loc_180031215
0x180031203  mov     esi, 7Eh ; '~'
0x180031208  xor     edx, edx; void *
0x18003120a  mov     rcx, [rbp+TargetHandle]; hFile
0x18003120e  call    ?IsValidHandleType@PrintScanBrokerUtilities@@YA_NPEAXW4HandleType@1@@Z; PrintScanBrokerUtilities::IsValidHandleType(void *,PrintScanBrokerUtilities::HandleType)
0x180031213  jmp     short loc_180031226
0x180031215  mov     esi, 82h
0x18003121a  xor     r8d, r8d; enum HandleType
0x18003121d  mov     rdx, [rbp+TargetHandle]; void *
0x180031221  call    ?_IsValidHandleType@TokenUtility@@AEAA_NPEAXW4HandleType@@@Z; TokenUtility::_IsValidHandleType(void *,HandleType)
0x180031226  xor     al, 1
0x180031228  lea     rcx, aInvalidHandleT; "Invalid handle type!"
0x18003122f  mov     qword ptr [rsp+60h+bInheritHandle], rcx; bool
0x180031234  mov     byte ptr [rsp+60h+dwDesiredAccess], al; char
0x180031238  mov     r9d, 80070006h; char *
0x18003123e  mov     r8, r12; unsigned int
0x180031241  mov     edx, esi; void *
0x180031243  mov     rcx, rbx; this
0x180031246  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003124b  mov     qword ptr [r14], 0
0x180031252  mov     [rbp+var_20], 1
0x180031259  xor     edx, edx
0x18003125b  mov     rcx, r14
0x18003125e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180031263  mov     rbx, [rbp+TargetHandle]
0x180031267  call    cs:__imp_GetCurrentProcess
0x18003126d  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180031275  mov     [rsp+60h+bInheritHandle], 0; char *
0x18003127d  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180031285  mov     r9, r14; lpTargetHandle
0x180031288  mov     r8, rdi; hTargetProcessHandle
0x18003128b  mov     rdx, rbx; hSourceHandle
0x18003128e  mov     rcx, rax; hSourceProcessHandle
0x180031291  call    cs:__imp_DuplicateHandle
0x180031297  mov     rcx, [rbp+28h]; this
0x18003129b  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x1800312a2  mov     qword ptr [rsp+60h+dwDesiredAccess], rdx; int
0x1800312a7  mov     r9d, eax; char *
0x1800312aa  mov     r8, r12; unsigned int
0x1800312ad  mov     edx, 86h; void *
0x1800312b2  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800312b7  nop
0x1800312b8  lea     rcx, [rbp+TargetHandle]
0x1800312bc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800312c1  nop
0x1800312c2  lea     rcx, [rbp+hSourceProcessHandle]
0x1800312c6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800312cb  nop
0x1800312cc  lea     rcx, [rbp+var_10]
0x1800312d0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800312d5  mov     rax, r14
0x1800312d8  mov     rbx, [rsp+60h+arg_10]
0x1800312e0  add     rsp, 60h
0x1800312e4  pop     r14
0x1800312e6  pop     r12
0x1800312e8  pop     rdi
0x1800312e9  pop     rsi
0x1800312ea  pop     rbp
0x1800312eb  retn
```
