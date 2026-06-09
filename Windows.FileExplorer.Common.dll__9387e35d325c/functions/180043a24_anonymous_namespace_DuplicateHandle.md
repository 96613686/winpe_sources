# _anonymous_namespace_::_DuplicateHandle

- ea: `0x180043a24`
- end: `0x180043abe`
- name: `_anonymous_namespace_::_DuplicateHandle`
- size: `154`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, LPHANDLE lpTargetHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800437d0`

## callees

- `0x18000c668`
- `0x180043a24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043a61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043a61`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180043a8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180043a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043aad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043a48`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043a48`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::_DuplicateHandle(HANDLE hSourceHandle, LPHANDLE lpTargetHandle)
{
  DWORD CurrentProcessId; // eax
  char *v5; // rdi
  int Error; // ebx
  HANDLE CurrentProcess; // rax

  *lpTargetHandle = (HANDLE)-1LL;
  CurrentProcessId = GetCurrentProcessId();
  v5 = (char *)OpenProcess(0x40u, 0, CurrentProcessId);
  if ( v5 || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, hSourceHandle, v5, lpTargetHandle, 0, 0, 2u) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180043a24  push    rbx
0x180043a26  push    rbp
0x180043a27  push    rsi
0x180043a28  push    rdi
0x180043a29  sub     rsp, 48h
0x180043a2d  mov     rsi, rdx
0x180043a30  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180043a37  mov     rbp, rcx
0x180043a3a  call    cs:__imp_GetCurrentProcessId
0x180043a40  xor     edx, edx; bInheritHandle
0x180043a42  mov     r8d, eax; dwProcessId
0x180043a45  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180043a48  call    cs:__imp_OpenProcess
0x180043a4e  mov     rdi, rax
0x180043a51  test    rax, rax
0x180043a54  jnz     short loc_180043A61
0x180043a56  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180043a5b  mov     ebx, eax
0x180043a5d  test    eax, eax
0x180043a5f  js      short loc_180043AB3
0x180043a61  call    cs:__imp_GetCurrentProcess
0x180043a67  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180043a6f  mov     r9, rsi; lpTargetHandle
0x180043a72  mov     rcx, rax; hSourceProcessHandle
0x180043a75  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180043a7d  mov     r8, rdi; hTargetProcessHandle
0x180043a80  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180043a88  mov     rdx, rbp; hSourceHandle
0x180043a8b  call    cs:__imp_DuplicateHandle
0x180043a91  test    eax, eax
0x180043a93  jz      short loc_180043A99
0x180043a95  xor     ebx, ebx
0x180043a97  jmp     short loc_180043AA0
0x180043a99  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180043a9e  mov     ebx, eax
0x180043aa0  lea     rcx, [rdi-1]
0x180043aa4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180043aa8  ja      short loc_180043AB3
0x180043aaa  mov     rcx, rdi; hObject
0x180043aad  call    cs:__imp_CloseHandle
0x180043ab3  mov     eax, ebx
0x180043ab5  add     rsp, 48h
0x180043ab9  pop     rdi
0x180043aba  pop     rsi
0x180043abb  pop     rbp
0x180043abc  pop     rbx
0x180043abd  retn
```
