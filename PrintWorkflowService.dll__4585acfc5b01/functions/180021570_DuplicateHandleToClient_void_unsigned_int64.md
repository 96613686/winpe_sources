# DuplicateHandleToClient(void *,unsigned __int64 *)

- ea: `0x180021570`
- end: `0x18002179d`
- name: `?DuplicateHandleToClient@@YAJPEAXPEA_K@Z`
- size: `557`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, unsigned __int64 *)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019a30`
- `0x180019b00`
- `0x180023f0c`
- `0x180023f40`
- `0x180023f50`
- `0x180023f60`
- `0x180034e38`
- `0x1800453ac`
- `0x1800455c8`

## callees

- `0x1800014e8`
- `0x180003ca0`
- `0x1800127a4`
- `0x1800166a8`
- `0x18001a7c0`
- `0x180021570`
- `0x180021eac`
- `0x1800235a0`
- `0x180023664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021620`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002164c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002164c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800215e3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800215e3`

## string_xrefs

- `0x180021752`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021766`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021778`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002178a`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall DuplicateHandleToClient(HANDLE hSourceHandle, unsigned __int64 *a2)
{
  int CallerProcessId; // eax
  DWORD v5; // r14d
  char *v6; // rbx
  const char *v7; // r9
  HANDLE CurrentProcess; // rax
  const char *v9; // r9
  HANDLE v10; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-C8h]
  DWORD dwOptions; // [rsp+30h] [rbp-B8h]
  DWORD dwProcessId; // [rsp+40h] [rbp-A8h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-98h] BYREF
  HANDLE v17; // [rsp+58h] [rbp-90h] BYREF
  char *v18; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v19[32]; // [rsp+70h] [rbp-78h] BYREF
  DWORD *p_dwProcessId; // [rsp+90h] [rbp-58h]
  __int64 v21; // [rsp+98h] [rbp-50h]
  HANDLE *v22; // [rsp+A0h] [rbp-48h]
  __int64 v23; // [rsp+A8h] [rbp-40h]
  __int64 *v24; // [rsp+B0h] [rbp-38h]
  __int64 v25; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  *a2 = -1;
  if ( IsPseudoHandle(hSourceHandle) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)0x80070006LL,
      dwDesiredAccess);
  dwProcessId = 0;
  CallerProcessId = GetCallerProcessId(&dwProcessId);
  if ( CallerProcessId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)(unsigned int)CallerProcessId,
      dwDesiredAccess);
  v5 = dwProcessId;
  v6 = (char *)OpenProcess(0x40u, 0, dwProcessId);
  v18 = v6;
  if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v7);
  TargetHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, hSourceHandle, v6, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v9);
  v10 = TargetHandle;
  TargetHandle = 0;
  *a2 = (unsigned __int64)v10;
  if ( (unsigned int)dword_180083038 > 5 )
  {
    v16 = *a2;
    v17 = hSourceHandle;
    dwProcessId = v5;
    v24 = &v16;
    v25 = 8;
    v22 = &v17;
    v23 = 8;
    p_dwProcessId = &dwProcessId;
    v21 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180083038, word_180072872, 0, 0, 5, v19, dwOptions);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  return 0;
}

```

## disassembly

```asm
0x180021570  mov     [rsp+arg_10], rbx
0x180021575  push    rsi
0x180021576  push    rdi
0x180021577  push    r14
0x180021579  sub     rsp, 0D0h
0x180021580  mov     rax, cs:__security_cookie
0x180021587  xor     rax, rsp
0x18002158a  mov     [rsp+0E8h+var_28], rax
0x180021592  mov     rdi, rdx
0x180021595  mov     rsi, rcx
0x180021598  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18002159f  call    ?IsPseudoHandle@@YA_NPEAX@Z; IsPseudoHandle(void *)
0x1800215a4  mov     rcx, [rsp+0E8h]; this
0x1800215ac  test    al, al
0x1800215ae  jnz     loc_18002174C
0x1800215b4  mov     [rsp+0E8h+dwProcessId], 0
0x1800215bc  lea     rcx, [rsp+0E8h+dwProcessId]; unsigned int *
0x1800215c1  call    ?GetCallerProcessId@@YAJPEAK@Z; GetCallerProcessId(ulong *)
0x1800215c6  mov     rcx, [rsp+0E8h]; this
0x1800215ce  test    eax, eax
0x1800215d0  js      loc_180021763
0x1800215d6  mov     r14d, [rsp+0E8h+dwProcessId]
0x1800215db  mov     r8d, r14d; dwProcessId
0x1800215de  xor     edx, edx; bInheritHandle
0x1800215e0  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800215e3  call    cs:__imp_OpenProcess
0x1800215e9  mov     rbx, rax
0x1800215ec  mov     [rsp+0E8h+var_88], rax
0x1800215f1  dec     rax
0x1800215f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800215f8  setnbe  al
0x1800215fb  mov     rcx, [rsp+0E8h]; this
0x180021603  test    al, al
0x180021605  jnz     loc_180021778
0x18002160b  mov     [rsp+0E8h+TargetHandle], 0
0x180021614  xor     edx, edx
0x180021616  lea     rcx, [rsp+0E8h+TargetHandle]
0x18002161b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021620  call    cs:__imp_GetCurrentProcess
0x180021626  mov     [rsp+0E8h+dwOptions], 2; dwOptions
0x18002162e  mov     [rsp+0E8h+bInheritHandle], 0; bInheritHandle
0x180021636  mov     [rsp+0E8h+dwDesiredAccess], 0; dwDesiredAccess
0x18002163e  lea     r9, [rsp+0E8h+TargetHandle]; lpTargetHandle
0x180021643  mov     r8, rbx; hTargetProcessHandle
0x180021646  mov     rdx, rsi; hSourceHandle
0x180021649  mov     rcx, rax; hSourceProcessHandle
0x18002164c  call    cs:__imp_DuplicateHandle
0x180021652  mov     rcx, [rsp+0E8h]; this
0x18002165a  test    eax, eax
0x18002165c  jz      loc_18002178A
0x180021662  mov     rax, [rsp+0E8h+TargetHandle]
0x180021667  mov     [rsp+0E8h+TargetHandle], 0
0x180021670  mov     [rdi], rax
0x180021673  mov     eax, cs:dword_180083038
0x180021679  cmp     eax, 5
0x18002167c  jbe     loc_18002170B
0x180021682  mov     rax, [rdi]
0x180021685  mov     [rsp+0E8h+var_98], rax
0x18002168a  mov     [rsp+0E8h+var_90], rsi
0x18002168f  mov     [rsp+0E8h+dwProcessId], r14d
0x180021694  lea     rax, [rsp+0E8h+var_98]
0x180021699  mov     [rsp+0E8h+var_38], rax
0x1800216a1  mov     [rsp+0E8h+var_30], 8
0x1800216ad  lea     rax, [rsp+0E8h+var_90]
0x1800216b2  mov     [rsp+0E8h+var_48], rax
0x1800216ba  mov     [rsp+0E8h+var_40], 8
0x1800216c6  lea     rax, [rsp+0E8h+dwProcessId]
0x1800216cb  mov     [rsp+0E8h+var_58], rax
0x1800216d3  mov     [rsp+0E8h+var_50], 4
0x1800216df  lea     rax, [rsp+0E8h+var_78]
0x1800216e4  mov     qword ptr [rsp+0E8h+bInheritHandle], rax
0x1800216e9  mov     [rsp+0E8h+dwDesiredAccess], 5
0x1800216f1  xor     r9d, r9d
0x1800216f4  xor     r8d, r8d
0x1800216f7  lea     rdx, word_180072872
0x1800216fe  lea     rcx, dword_180083038
0x180021705  call    _tlgWriteTransfer_EventWriteTransfer
0x18002170a  nop
0x18002170b  lea     rcx, [rsp+0E8h+TargetHandle]
0x180021710  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021715  nop
0x180021716  lea     rcx, [rsp+0E8h+var_88]
0x18002171b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021720  xor     eax, eax
0x180021722  jmp     short loc_180021728
0x180021724  mov     eax, [rsp+0E8h+dwProcessId]
0x180021728  mov     rcx, [rsp+0E8h+var_28]
0x180021730  xor     rcx, rsp; StackCookie
0x180021733  call    __security_check_cookie
0x180021738  mov     rbx, [rsp+0E8h+arg_10]
0x180021740  add     rsp, 0D0h
0x180021747  pop     r14
0x180021749  pop     rdi
0x18002174a  pop     rsi
0x18002174b  retn
0x18002174c  mov     r9d, 80070006h; char *
0x180021752  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021759  mov     edx, 1FAh; void *
0x18002175e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021763  mov     r9d, eax; char *
0x180021766  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002176d  mov     edx, 1FEh; void *
0x180021772  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021778  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002177f  mov     edx, 202h; void *
0x180021784  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002178a  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021791  mov     edx, 206h; void *
0x180021796  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
