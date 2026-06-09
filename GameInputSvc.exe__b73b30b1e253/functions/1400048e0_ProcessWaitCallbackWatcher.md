# ProcessWaitCallbackWatcher

- ea: `0x1400048e0`
- end: `0x140004948`
- name: `ProcessWaitCallbackWatcher`
- size: `104`
- prototype: `ULONG __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400048e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400048f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400048fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400048f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400048fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004939`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004929`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004929`

## pseudocode

```c
ULONG __fastcall ProcessWaitCallbackWatcher(HANDLE *Parameter)
{
  WaitForSingleObject(Parameter[15], 0xFFFFFFFF);
  if ( WaitForSingleObject(Parameter[13], 0) != 258
    || CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ProcessWaitCallback, (LPVOID)*((unsigned int *)Parameter + 4), 0, 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x1400048e0  push    rbx
0x1400048e2  sub     rsp, 30h
0x1400048e6  mov     rbx, rcx
0x1400048e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400048ec  mov     rcx, [rcx+78h]; hHandle
0x1400048f0  call    cs:__imp_WaitForSingleObject
0x1400048f6  mov     rcx, [rbx+68h]; hHandle
0x1400048fa  xor     edx, edx; dwMilliseconds
0x1400048fc  call    cs:__imp_WaitForSingleObject
0x140004902  cmp     eax, 102h
0x140004907  jnz     short loc_140004940
0x140004909  mov     r9d, [rbx+10h]; lpParameter
0x14000490d  lea     r8, ProcessWaitCallback; lpStartAddress
0x140004914  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14000491d  xor     edx, edx; dwStackSize
0x14000491f  xor     ecx, ecx; lpThreadAttributes
0x140004921  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140004929  call    cs:__imp_CreateThread
0x14000492f  test    rax, rax
0x140004932  jnz     short loc_140004940
0x140004934  add     rsp, 30h
0x140004938  pop     rbx
0x140004939  jmp     cs:__imp_GetLastError
0x140004940  xor     eax, eax
0x140004942  add     rsp, 30h
0x140004946  pop     rbx
0x140004947  retn
```
