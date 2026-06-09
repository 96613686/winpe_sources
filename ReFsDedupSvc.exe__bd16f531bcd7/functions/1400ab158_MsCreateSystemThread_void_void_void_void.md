# MsCreateSystemThread(void (*)(void *),void *,void * *)

- ea: `0x1400ab158`
- end: `0x1400ab1f5`
- name: `?MsCreateSystemThread@@YAJP6AXPEAX@Z0PEAPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(void (*)(void *), void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140127d78`

## callees

- `0x1400ab158`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400ab1c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400ab1c3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400ab163`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400ab163`
- `ntdll!RtlGetLastNtStatus` at `0x1400ab1cf`
- `ntdll!RtlGetLastNtStatus` at `0x1400ab1cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400ab1af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400ab1af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ab1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ab1e0`

## pseudocode

```c
NTSTATUS __fastcall MsCreateSystemThread(void (*a1)(void *), void *a2, void **a3)
{
  _QWORD *v3; // rbx
  HANDLE Thread; // rax

  v3 = malloc(0x10u);
  if ( !v3 )
    return -1073741670;
  *v3 = MspDeferredIoThread;
  v3[1] = 0;
  Thread = CreateThread(0, 0, MsThunkThreadStart, v3, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    return 0;
  }
  else
  {
    free(v3);
    return RtlGetLastNtStatus();
  }
}

```

## disassembly

```asm
0x1400ab158  push    rbx
0x1400ab15a  sub     rsp, 30h
0x1400ab15e  mov     ecx, 10h; Size
0x1400ab163  call    cs:__imp_malloc
0x1400ab16a  nop     dword ptr [rax+rax+00h]
0x1400ab16f  mov     rbx, rax
0x1400ab172  test    rax, rax
0x1400ab175  jnz     short loc_1400AB17E
0x1400ab177  mov     eax, 0C000009Ah
0x1400ab17c  jmp     short loc_1400AB1EE
0x1400ab17e  lea     rax, ?MspDeferredIoThread@@YAXPEAX@Z; MspDeferredIoThread(void *)
0x1400ab185  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1400ab18e  mov     r9, rbx; lpParameter
0x1400ab191  mov     [rbx], rax
0x1400ab194  lea     r8, ?MsThunkThreadStart@@YAKPEAX@Z; lpStartAddress
0x1400ab19b  mov     qword ptr [rbx+8], 0
0x1400ab1a3  xor     edx, edx; dwStackSize
0x1400ab1a5  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1400ab1ad  xor     ecx, ecx; lpThreadAttributes
0x1400ab1af  call    cs:__imp_CreateThread
0x1400ab1b6  nop     dword ptr [rax+rax+00h]
0x1400ab1bb  test    rax, rax
0x1400ab1be  jnz     short loc_1400AB1DD
0x1400ab1c0  mov     rcx, rbx; Block
0x1400ab1c3  call    cs:__imp_free
0x1400ab1ca  nop     dword ptr [rax+rax+00h]
0x1400ab1cf  call    cs:__imp_RtlGetLastNtStatus
0x1400ab1d6  nop     dword ptr [rax+rax+00h]
0x1400ab1db  jmp     short loc_1400AB1EE
0x1400ab1dd  mov     rcx, rax; hObject
0x1400ab1e0  call    cs:__imp_CloseHandle
0x1400ab1e7  nop     dword ptr [rax+rax+00h]
0x1400ab1ec  xor     eax, eax
0x1400ab1ee  add     rsp, 30h
0x1400ab1f2  pop     rbx
0x1400ab1f3  retn
```
