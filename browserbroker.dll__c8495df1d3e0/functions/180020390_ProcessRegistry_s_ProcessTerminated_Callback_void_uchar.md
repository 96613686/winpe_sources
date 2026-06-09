# ProcessRegistry::s_ProcessTerminated_Callback(void *,uchar)

- ea: `0x180020390`
- end: `0x1800203cc`
- name: `?s_ProcessTerminated_Callback@ProcessRegistry@@CAXPEAXE@Z`
- size: `60`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180020390`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800203b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800203b3`

## pseudocode

```c
void __fastcall ProcessRegistry::s_ProcessTerminated_Callback(PVOID a1)
{
  HANDLE Thread; // rax

  Thread = CreateThread(0, 0, ProcessRegistry::s_ProcessTerminated_Callback_ThreadProc, a1, 0, 0);
  if ( Thread )
    CloseHandle(Thread);
}

```

## disassembly

```asm
0x180020390  sub     rsp, 38h
0x180020394  mov     r9, rcx; lpParameter
0x180020397  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800203a0  xor     ecx, ecx; lpThreadAttributes
0x1800203a2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800203aa  lea     r8, ?s_ProcessTerminated_Callback_ThreadProc@ProcessRegistry@@CAKPEAX@Z; lpStartAddress
0x1800203b1  xor     edx, edx; dwStackSize
0x1800203b3  call    cs:__imp_CreateThread
0x1800203b9  test    rax, rax
0x1800203bc  jz      short loc_1800203C7
0x1800203be  mov     rcx, rax; hObject
0x1800203c1  call    cs:__imp_CloseHandle
0x1800203c7  add     rsp, 38h
0x1800203cb  retn
```
