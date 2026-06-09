# PrintScanBrokerUtilities::GetCallerProcessId(void)

- ea: `0x1800355f0`
- end: `0x1800356c3`
- name: `?GetCallerProcessId@PrintScanBrokerUtilities@@YAKXZ`
- size: `211`
- prototype: `__int64 __fastcall(PrintScanBrokerUtilities *this)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030df0`
- `0x1800310b0`
- `0x1800320a4`
- `0x180033254`

## callees

- `0x18001255c`
- `0x18001d058`
- `0x180023264`
- `0x180030a08`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180035617`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180035617`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180035699`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180035699`

## string_xrefs

- `0x180035674`: `OpenCallerProcessHandle failed!`
- `0x180035631`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x180035683`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintScanBrokerUtilities::GetCallerProcessId(PrintScanBrokerUtilities *this)
{
  unsigned int v1; // eax
  void *v2; // rdi
  __int64 (__fastcall *v3)(void *, __int64, HANDLE *); // rbx
  unsigned int v4; // eax
  const char *v6; // [rsp+28h] [rbp-10h]
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE Process; // [rsp+40h] [rbp+8h] BYREF
  void *v10; // [rsp+48h] [rbp+10h] BYREF

  Process = 0;
  v10 = 0;
  v1 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &v10);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2D,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
    (const char *)v1,
    (int)"CoGetCallContext failed!",
    v6);
  v2 = v10;
  v3 = *(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)v10 + 24LL);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &Process,
    0);
  v4 = v3(v2, 4096, &Process);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
    (const char *)v4,
    (int)"OpenCallerProcessHandle failed!",
    v7);
  LODWORD(v3) = GetProcessId(Process);
  wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>(&v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800355f0  mov     rax, rsp
0x1800355f3  mov     [rax+18h], rbx
0x1800355f7  push    rdi
0x1800355f8  sub     rsp, 30h
0x1800355fc  mov     qword ptr [rax+8], 0
0x180035604  mov     qword ptr [rax+10h], 0
0x18003560c  lea     rdx, [rax+10h]; ppInterface
0x180035610  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180035617  call    cs:__imp_CoGetCallContext
0x18003561d  mov     rcx, [rsp+38h]; this
0x180035622  lea     rdx, aCogetcallconte; "CoGetCallContext failed!"
0x180035629  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18003562e  mov     r9d, eax; char *
0x180035631  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x180035638  mov     edx, 2Dh ; '-'; void *
0x18003563d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180035642  mov     rdi, [rsp+38h+arg_8]
0x180035647  mov     rax, [rdi]
0x18003564a  mov     rbx, [rax+18h]
0x18003564e  xor     edx, edx
0x180035650  lea     rcx, [rsp+38h+Process]
0x180035655  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003565a  lea     r8, [rsp+38h+Process]
0x18003565f  mov     edx, 1000h
0x180035664  mov     rcx, rdi
0x180035667  mov     rax, rbx
0x18003566a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003566f  mov     rcx, [rsp+38h]; this
0x180035674  lea     rdx, aOpencallerproc; "OpenCallerProcessHandle failed!"
0x18003567b  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180035680  mov     r9d, eax; char *
0x180035683  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x18003568a  mov     edx, 2Eh ; '.'; void *
0x18003568f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180035694  mov     rcx, [rsp+38h+Process]; Process
0x180035699  call    cs:__imp_GetProcessId
0x18003569f  mov     ebx, eax
0x1800356a1  lea     rcx, [rsp+38h+arg_8]
0x1800356a6  call    ??1?$com_ptr_t@UIClassFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>(void)
0x1800356ab  nop
0x1800356ac  lea     rcx, [rsp+38h+Process]
0x1800356b1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800356b6  mov     eax, ebx
0x1800356b8  mov     rbx, [rsp+38h+arg_10]
0x1800356bd  add     rsp, 30h
0x1800356c1  pop     rdi
0x1800356c2  retn
```
