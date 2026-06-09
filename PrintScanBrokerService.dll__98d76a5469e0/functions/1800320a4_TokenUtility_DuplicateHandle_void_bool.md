# TokenUtility::_DuplicateHandle(void *,bool)

- ea: `0x1800320a4`
- end: `0x1800321f0`
- name: `?_DuplicateHandle@TokenUtility@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N@Z`
- size: `332`
- prototype: `HANDLE *__fastcall(__int64, HANDLE *, void *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030a60`
- `0x180031a9c`

## callees

- `0x18001255c`
- `0x18001d0a0`
- `0x180023264`
- `0x18002b28c`
- `0x1800320a4`
- `0x1800322f4`
- `0x18003286c`
- `0x1800355f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032158`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032158`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180032187`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800321a6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180032187`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800321a6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800320f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800320f6`

## string_xrefs

- `0x18003212e`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800321c0`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`

## pseudocode

```c
HANDLE *__fastcall TokenUtility::_DuplicateHandle(__int64 a1, HANDLE *a2, void *a3, char a4)
{
  PrintScanBrokerUtilities *v7; // rcx
  DWORD CallerProcessId; // eax
  HANDLE v9; // rax
  HANDLE v10; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  const char *bInheritHandle; // [rsp+28h] [rbp-40h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-40h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE hSourceProcessHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE *v20; // [rsp+78h] [rbp+10h]

  v20 = a2;
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
    (void *)0x16B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)((char *)hSourceProcessHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL),
    (bool)"Invalid client process information!",
    bInheritHandle);
  *a2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( a4 )
  {
    v12 = DuplicateHandle(v10, a3, CurrentProcess, a2, 0, 0, 2u);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
      (const char *)v12,
      (int)"DuplicateHandle failed!",
      bInheritHandlea);
  }
  else
  {
    v13 = DuplicateHandle(CurrentProcess, a3, v10, a2, 0, 0, 2u);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
      (const char *)v13,
      (int)"DuplicateHandle failed!",
      bInheritHandleb);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hSourceProcessHandle);
  return a2;
}

```

## disassembly

```asm
0x1800320a4  mov     rax, rsp
0x1800320a7  mov     [rax+18h], rbx
0x1800320ab  mov     [rax+10h], rdx
0x1800320af  mov     [rax+8], rcx
0x1800320b3  push    rbp
0x1800320b4  push    rsi
0x1800320b5  push    rdi
0x1800320b6  sub     rsp, 50h
0x1800320ba  mov     sil, r9b
0x1800320bd  mov     rbp, r8
0x1800320c0  mov     rdi, rdx
0x1800320c3  mov     dword ptr [rax-28h], 0
0x1800320ca  mov     qword ptr [rax+8], 0
0x1800320d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800320d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800320de  test    al, al
0x1800320e0  jz      short loc_1800320E9
0x1800320e2  call    ?GetCallerProcessId@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerProcessId(void)
0x1800320e7  jmp     short loc_1800320EE
0x1800320e9  call    ?_GetCallerProcessId@TokenUtility@@AEAAKXZ; TokenUtility::_GetCallerProcessId(void)
0x1800320ee  mov     r8d, eax; dwProcessId
0x1800320f1  xor     edx, edx; bInheritHandle
0x1800320f3  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800320f6  call    cs:__imp_OpenProcess
0x1800320fc  mov     rdx, rax
0x1800320ff  lea     rcx, [rsp+68h+hSourceProcessHandle]
0x180032104  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032109  mov     rbx, [rsp+68h+hSourceProcessHandle]
0x18003210e  lea     rax, [rbx-1]
0x180032112  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180032116  setnbe  al
0x180032119  mov     rcx, [rsp+68h]; this
0x18003211e  lea     rdx, aInvalidClientP; "Invalid client process information!"
0x180032125  mov     qword ptr [rsp+68h+dwDesiredAccess], rdx; bool
0x18003212a  movzx   r9d, al; char *
0x18003212e  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032135  mov     edx, 16Bh; void *
0x18003213a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18003213f  mov     qword ptr [rdi], 0
0x180032146  mov     [rsp+68h+var_28], 1
0x18003214e  xor     edx, edx
0x180032150  mov     rcx, rdi
0x180032153  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032158  call    cs:__imp_GetCurrentProcess
0x18003215e  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180032166  mov     r9, rdi; lpTargetHandle
0x180032169  mov     rdx, rbp; hSourceHandle
0x18003216c  mov     dword ptr [rsp+68h+bInheritHandle], 0; char *
0x180032174  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18003217c  test    sil, sil
0x18003217f  jz      short loc_1800321A0
0x180032181  mov     r8, rax; hTargetProcessHandle
0x180032184  mov     rcx, rbx; hSourceProcessHandle
0x180032187  call    cs:__imp_DuplicateHandle
0x18003218d  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x180032194  mov     qword ptr [rsp+68h+dwDesiredAccess], rdx
0x180032199  mov     edx, 171h
0x18003219e  jmp     short loc_1800321BD
0x1800321a0  mov     r8, rbx; hTargetProcessHandle
0x1800321a3  mov     rcx, rax; hSourceProcessHandle
0x1800321a6  call    cs:__imp_DuplicateHandle
0x1800321ac  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x1800321b3  mov     qword ptr [rsp+68h+dwDesiredAccess], rdx; int
0x1800321b8  mov     edx, 176h; void *
0x1800321bd  mov     r9d, eax; char *
0x1800321c0  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x1800321c7  mov     rcx, [rsp+68h]; this
0x1800321cc  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800321d1  nop
0x1800321d2  lea     rcx, [rsp+68h+hSourceProcessHandle]
0x1800321d7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800321dc  mov     rax, rdi
0x1800321df  mov     rbx, [rsp+68h+arg_10]
0x1800321e7  add     rsp, 50h
0x1800321eb  pop     rdi
0x1800321ec  pop     rsi
0x1800321ed  pop     rbp
0x1800321ee  retn
```
