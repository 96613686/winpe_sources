# TokenUtility::_GetCallerProcessId(void)

- ea: `0x1800322f4`
- end: `0x1800323cb`
- name: `?_GetCallerProcessId@TokenUtility@@AEAAKXZ`
- size: `215`
- prototype: `unsigned int __fastcall(TokenUtility *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030df0`
- `0x1800310b0`
- `0x1800320a4`

## callees

- `0x18001255c`
- `0x18001d058`
- `0x180023264`
- `0x180030a08`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003231f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003231f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800323a1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800323a1`

## string_xrefs

- `0x180032339`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x18003238b`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x18003237c`: `OpenCallerProcessHandle failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TokenUtility::_GetCallerProcessId(TokenUtility *this)
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
    (void *)0x181,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
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
    (void *)0x182,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v4,
    (int)"OpenCallerProcessHandle failed!",
    v7);
  LODWORD(v3) = GetProcessId(Process);
  wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>((__int64 *)&v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800322f4  mov     rax, rsp
0x1800322f7  mov     [rax+18h], rbx
0x1800322fb  mov     [rax+8], rcx
0x1800322ff  push    rdi
0x180032300  sub     rsp, 30h
0x180032304  mov     qword ptr [rax+8], 0
0x18003230c  mov     qword ptr [rax+10h], 0
0x180032314  lea     rdx, [rax+10h]; ppInterface
0x180032318  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18003231f  call    cs:__imp_CoGetCallContext
0x180032325  mov     rcx, [rsp+38h]; this
0x18003232a  lea     rdx, aCogetcallconte; "CoGetCallContext failed!"
0x180032331  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180032336  mov     r9d, eax; char *
0x180032339  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032340  mov     edx, 181h; void *
0x180032345  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003234a  mov     rdi, [rsp+38h+arg_8]
0x18003234f  mov     rax, [rdi]
0x180032352  mov     rbx, [rax+18h]
0x180032356  xor     edx, edx
0x180032358  lea     rcx, [rsp+38h+Process]
0x18003235d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032362  lea     r8, [rsp+38h+Process]
0x180032367  mov     edx, 1000h
0x18003236c  mov     rcx, rdi
0x18003236f  mov     rax, rbx
0x180032372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032377  mov     rcx, [rsp+38h]; this
0x18003237c  lea     rdx, aOpencallerproc; "OpenCallerProcessHandle failed!"
0x180032383  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180032388  mov     r9d, eax; char *
0x18003238b  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032392  mov     edx, 182h; void *
0x180032397  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003239c  mov     rcx, [rsp+38h+Process]; Process
0x1800323a1  call    cs:__imp_GetProcessId
0x1800323a7  mov     ebx, eax
0x1800323a9  lea     rcx, [rsp+38h+arg_8]
0x1800323ae  call    ??1?$com_ptr_t@UIClassFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>(void)
0x1800323b3  nop
0x1800323b4  lea     rcx, [rsp+38h+Process]
0x1800323b9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800323be  mov     eax, ebx
0x1800323c0  mov     rbx, [rsp+38h+arg_10]
0x1800323c5  add     rsp, 30h
0x1800323c9  pop     rdi
0x1800323ca  retn
```
