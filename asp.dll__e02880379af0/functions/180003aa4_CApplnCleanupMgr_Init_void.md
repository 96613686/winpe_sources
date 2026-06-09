# CApplnCleanupMgr::Init(void)

- ea: `0x180003aa4`
- end: `0x180003b66`
- name: `?Init@CApplnCleanupMgr@@QEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CApplnCleanupMgr *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800053cc`

## callees

- `0x180003aa4`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x180003b4b`
- `KERNEL32!ResumeThread` at `0x180003b4b`
- `KERNEL32!CreateThread` at `0x180003b2b`
- `KERNEL32!CreateThread` at `0x180003b2b`
- `KERNEL32!CreateEventA` at `0x180003ab4`
- `KERNEL32!CreateEventA` at `0x180003ab4`
- `KERNEL32!GetLastError` at `0x180003add`
- `KERNEL32!GetLastError` at `0x180025618`
- `KERNEL32!GetLastError` at `0x180003add`
- `KERNEL32!GetLastError` at `0x180025618`
- `iisutil!IISInitializeCriticalSection` at `0x180003ad3`
- `iisutil!IISInitializeCriticalSection` at `0x180003ad3`

## pseudocode

```c
signed int __fastcall CApplnCleanupMgr::Init(CApplnCleanupMgr *this)
{
  signed int v1; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int result; // eax

  qword_180079CB0 = CreateEventA(0, 0, 0, 0);
  if ( !qword_180079CB0 )
    return -2147467259;
  v1 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_180079B80) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v1 < 0 )
    return v1;
  g_ApplnCleanupMgr |= 2u;
  Thread = CreateThread(0, 0, CApplnCleanupMgr::ApplnCleanupThread, 0, 4u, 0);
  qword_180079B78 = (__int64)Thread;
  if ( Thread )
  {
    g_ApplnCleanupMgr |= 1u;
    if ( ResumeThread(Thread) != -1 )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003aa4  push    rbx
0x180003aa6  sub     rsp, 40h
0x180003aaa  xor     r9d, r9d; lpName
0x180003aad  xor     r8d, r8d; bInitialState
0x180003ab0  xor     edx, edx; bManualReset
0x180003ab2  xor     ecx, ecx; lpEventAttributes
0x180003ab4  call    cs:__imp_CreateEventA
0x180003aba  mov     cs:qword_180079CB0, rax
0x180003ac1  test    rax, rax
0x180003ac4  jz      loc_18002560E
0x180003aca  xor     ebx, ebx
0x180003acc  lea     rcx, stru_180079B80
0x180003ad3  call    cs:__imp_IISInitializeCriticalSection
0x180003ad9  test    eax, eax
0x180003adb  jnz     short loc_180003AF6
0x180003add  call    cs:__imp_GetLastError
0x180003ae3  mov     ebx, eax
0x180003ae5  test    eax, eax
0x180003ae7  jle     short loc_180003AF2
0x180003ae9  movzx   ebx, ax
0x180003aec  or      ebx, 80070000h
0x180003af2  mov     [rsp+48h+var_18], ebx
0x180003af6  jmp     short loc_180003B01
0x180003af8  mov     ebx, 8000FFFFh
0x180003afd  mov     [rsp+48h+var_18], ebx
0x180003b01  test    ebx, ebx
0x180003b03  js      short loc_180003B62
0x180003b05  or      cs:?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A, 2; CApplnCleanupMgr g_ApplnCleanupMgr
0x180003b0c  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180003b15  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x180003b1d  xor     r9d, r9d; lpParameter
0x180003b20  lea     r8, ?ApplnCleanupThread@CApplnCleanupMgr@@CAKPEAX@Z; lpStartAddress
0x180003b27  xor     edx, edx; dwStackSize
0x180003b29  xor     ecx, ecx; lpThreadAttributes
0x180003b2b  call    cs:__imp_CreateThread
0x180003b31  mov     cs:qword_180079B78, rax
0x180003b38  test    rax, rax
0x180003b3b  jz      loc_180025618
0x180003b41  or      cs:?g_ApplnCleanupMgr@@3VCApplnCleanupMgr@@A, 1; CApplnCleanupMgr g_ApplnCleanupMgr
0x180003b48  mov     rcx, rax; hThread
0x180003b4b  call    cs:__imp_ResumeThread
0x180003b51  cmp     eax, 0FFFFFFFFh
0x180003b54  jz      loc_180025618
0x180003b5a  xor     eax, eax
0x180003b5c  add     rsp, 40h
0x180003b60  pop     rbx
0x180003b61  retn
0x180003b62  mov     eax, ebx
0x180003b64  jmp     short loc_180003B5C
0x18002560e  mov     eax, 80004005h
0x180025613  jmp     loc_180003B5C
0x180025618  call    cs:__imp_GetLastError
0x18002561e  test    eax, eax
0x180025620  jle     loc_180003B5C
0x180025626  movzx   eax, ax
0x180025629  or      eax, 80070000h
0x18002562e  jmp     loc_180003B5C
```
