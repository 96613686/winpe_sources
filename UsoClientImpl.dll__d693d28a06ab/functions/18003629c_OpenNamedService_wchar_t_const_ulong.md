# OpenNamedService(wchar_t const *,ulong)

- ea: `0x18003629c`
- end: `0x18003634e`
- name: `?OpenNamedService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WK@Z`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180036464`

## callees

- `0x18002ff90`
- `0x18003629c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800362cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800362cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180036311`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180036311`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800362f3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800362f3`

## string_xrefs

- `0x18003632a`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x18003633c`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x1800362c3`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
SC_HANDLE *__fastcall OpenNamedService(SC_HANDLE *a1, const WCHAR *a2)
{
  SC_HANDLE v4; // rbx
  const char *v5; // r9
  SC_HANDLE v6; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  if ( !v4 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
      v5);
  *a1 = 0;
  v6 = OpenServiceW(v4, a2, 0x34u);
  *a1 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
      v7);
  CloseServiceHandle(v4);
  return a1;
}

```

## disassembly

```asm
0x18003629c  mov     rax, rsp
0x18003629f  mov     [rax+18h], rbx
0x1800362a3  mov     [rax+20h], rsi
0x1800362a7  push    rdi
0x1800362a8  sub     rsp, 40h
0x1800362ac  mov     rsi, rdx
0x1800362af  mov     rdi, rcx
0x1800362b2  mov     [rax-20h], rcx
0x1800362b6  mov     dword ptr [rax-28h], 0
0x1800362bd  mov     r8d, 1; dwDesiredAccess
0x1800362c3  lea     rdx, DatabaseName; "ServicesActive"
0x1800362ca  xor     ecx, ecx; lpMachineName
0x1800362cc  call    cs:__imp_OpenSCManagerW
0x1800362d2  mov     rbx, rax
0x1800362d5  mov     [rsp+48h+var_18], rax
0x1800362da  mov     rcx, [rsp+48h]; this
0x1800362df  test    rax, rax
0x1800362e2  jz      short loc_18003633C
0x1800362e4  xor     eax, eax
0x1800362e6  mov     [rdi], rax
0x1800362e9  lea     r8d, [rax+34h]; dwDesiredAccess
0x1800362ed  mov     rdx, rsi; lpServiceName
0x1800362f0  mov     rcx, rbx; hSCManager
0x1800362f3  call    cs:__imp_OpenServiceW
0x1800362f9  mov     [rdi], rax
0x1800362fc  mov     [rsp+48h+var_28], 1
0x180036304  mov     rcx, [rsp+48h]; this
0x180036309  test    rax, rax
0x18003630c  jz      short loc_18003632A
0x18003630e  mov     rcx, rbx; hSCObject
0x180036311  call    cs:__imp_CloseServiceHandle
0x180036317  mov     rax, rdi
0x18003631a  mov     rbx, [rsp+48h+arg_10]
0x18003631f  mov     rsi, [rsp+48h+arg_18]
0x180036324  add     rsp, 40h
0x180036328  pop     rdi
0x180036329  retn
0x18003632a  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180036331  mov     edx, 1Dh; void *
0x180036336  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003633c  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180036343  mov     edx, 1Ah; void *
0x180036348  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
