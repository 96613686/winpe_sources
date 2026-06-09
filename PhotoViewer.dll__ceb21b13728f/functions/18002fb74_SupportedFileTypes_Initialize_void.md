# SupportedFileTypes::Initialize(void)

- ea: `0x18002fb74`
- end: `0x18002fc06`
- name: `?Initialize@SupportedFileTypes@@QEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(SupportedFileTypes *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180011a00`
- `0x180029c14`
- `0x180047d34`
- `0x18004c2a0`
- `0x18005cd90`

## callees

- `0x18002fb74`
- `0x18002fc0c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002fbba`
- `KERNEL32!WaitForSingleObject` at `0x18002fbba`
- `KERNEL32!CloseHandle` at `0x18002fbea`
- `KERNEL32!CloseHandle` at `0x18002fbea`
- `KERNEL32!CreateThread` at `0x18002fba6`
- `KERNEL32!CreateThread` at `0x18002fba6`
- `KERNEL32!GetExitCodeThread` at `0x18002fbd0`
- `KERNEL32!GetExitCodeThread` at `0x18002fbd0`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::Initialize(SupportedFileTypes *this)
{
  HANDLE v1; // rax
  void *v2; // rdi
  DWORD ResultFromKnownLastError; // ebx
  DWORD ExitCode; // [rsp+48h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  ThreadId = 0;
  v1 = CreateThread(0, 0, SupportedFileTypes::InitializeThreadProc, this, 0, &ThreadId);
  v2 = v1;
  if ( v1 )
  {
    ExitCode = WaitForSingleObject(v1, 0xFFFFFFFF);
    if ( ExitCode || !GetExitCodeThread(v2, &ExitCode) )
      ResultFromKnownLastError = GetResultFromKnownLastError();
    else
      ResultFromKnownLastError = ExitCode;
    CloseHandle(v2);
  }
  else
  {
    return (unsigned int)GetResultFromKnownLastError();
  }
  return ResultFromKnownLastError;
}

```

## disassembly

```asm
0x18002fb74  mov     [rsp+arg_0], rbx
0x18002fb79  push    rdi
0x18002fb7a  sub     rsp, 30h
0x18002fb7e  lea     rax, [rsp+38h+ThreadId]
0x18002fb83  mov     [rsp+38h+ThreadId], 0
0x18002fb8b  mov     r9, rcx; lpParameter
0x18002fb8e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18002fb93  lea     r8, ?InitializeThreadProc@SupportedFileTypes@@CAKPEAX@Z; lpStartAddress
0x18002fb9a  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002fba2  xor     edx, edx; dwStackSize
0x18002fba4  xor     ecx, ecx; lpThreadAttributes
0x18002fba6  call    cs:__imp_CreateThread
0x18002fbac  mov     rdi, rax
0x18002fbaf  test    rax, rax
0x18002fbb2  jz      short loc_18002FBF2
0x18002fbb4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002fbb7  mov     rcx, rax; hHandle
0x18002fbba  call    cs:__imp_WaitForSingleObject
0x18002fbc0  mov     [rsp+38h+ExitCode], eax
0x18002fbc4  test    eax, eax
0x18002fbc6  jnz     short loc_18002FBE0
0x18002fbc8  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x18002fbcd  mov     rcx, rdi; hThread
0x18002fbd0  call    cs:__imp_GetExitCodeThread
0x18002fbd6  test    eax, eax
0x18002fbd8  jz      short loc_18002FBE0
0x18002fbda  mov     ebx, [rsp+38h+ExitCode]
0x18002fbde  jmp     short loc_18002FBE7
0x18002fbe0  call    GetResultFromKnownLastError
0x18002fbe5  mov     ebx, eax
0x18002fbe7  mov     rcx, rdi; hObject
0x18002fbea  call    cs:__imp_CloseHandle
0x18002fbf0  jmp     short loc_18002FBF9
0x18002fbf2  call    GetResultFromKnownLastError
0x18002fbf7  mov     ebx, eax
0x18002fbf9  mov     eax, ebx
0x18002fbfb  mov     rbx, [rsp+38h+arg_0]
0x18002fc00  add     rsp, 30h
0x18002fc04  pop     rdi
0x18002fc05  retn
```
