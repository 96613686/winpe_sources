# Microsoft::CoreUI::Dispatch::BaseUserData::Initialize(Microsoft::CoreUI::Dispatch::UserAdapter *,HWND__ *,Microsoft::CoreUI::Support::Win32Event)

- ea: `0x18005c460`
- end: `0x18005c4c2`
- name: `?Initialize@BaseUserData@Dispatch@CoreUI@Microsoft@@QEAAXPEAVUserAdapter@234@PEAUHWND__@@UWin32Event@Support@34@@Z`
- size: `98`
- prototype: `void __high(struct Microsoft::CoreUI::Dispatch::UserAdapter *, HWND, struct Microsoft::CoreUI::Support::Win32Event)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c084`

## callees

- `0x18005c460`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c47c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005c47c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005c4a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005c4a7`

## pseudocode

```c
BOOL __fastcall Microsoft::CoreUI::Dispatch::BaseUserData::Initialize(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  HANDLE CurrentProcess; // rax
  BOOL result; // eax

  *(_QWORD *)a1 = a3;
  *(_DWORD *)(a1 + 8) = GetCurrentThreadId();
  CurrentProcess = GetCurrentProcess();
  result = DuplicateHandle(CurrentProcess, a4, CurrentProcess, (LPHANDLE)(a1 + 16), 0, 0, 2u);
  if ( !result )
    Cn::FailFast::ForWin32();
  return result;
}

```

## disassembly

```asm
0x18005c460  mov     [rsp+arg_0], rbx
0x18005c465  push    rdi
0x18005c466  sub     rsp, 40h
0x18005c46a  mov     rbx, r9
0x18005c46d  mov     [rcx], r8
0x18005c470  mov     rdi, rcx
0x18005c473  call    cs:__imp_GetCurrentThreadId
0x18005c479  mov     [rdi+8], eax
0x18005c47c  call    cs:__imp_GetCurrentProcess
0x18005c482  mov     [rsp+48h+dwOptions], 2; dwOptions
0x18005c48a  lea     r9, [rdi+10h]; lpTargetHandle
0x18005c48e  mov     r8, rax; hTargetProcessHandle
0x18005c491  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18005c499  mov     rcx, rax; hSourceProcessHandle
0x18005c49c  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18005c4a4  mov     rdx, rbx; hSourceHandle
0x18005c4a7  call    cs:__imp_DuplicateHandle
0x18005c4ad  test    eax, eax
0x18005c4af  jz      short loc_18005C4BC
0x18005c4b1  mov     rbx, [rsp+48h+arg_0]
0x18005c4b6  add     rsp, 40h
0x18005c4ba  pop     rdi
0x18005c4bb  retn
0x18005c4bc  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
```
