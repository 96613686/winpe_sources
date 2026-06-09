# IoShutdown(void)

- ea: `0x18001a234`
- end: `0x18001a2b4`
- name: `?IoShutdown@@YAXXZ`
- size: `128`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016068`

## callees

- `0x18001a234`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a298`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a298`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a248`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a267`

## pseudocode

```c
void IoShutdown(void)
{
  if ( dword_180024AB8 == 1 )
  {
    EnterCriticalSection(&g_csIoInitialize);
    if ( g_hIoDevice )
    {
      CloseHandle(g_hIoDevice);
      g_hIoDevice = 0;
    }
    LeaveCriticalSection(&g_csIoInitialize);
    DeleteCriticalSection(&g_csIoInitialize);
    dword_180024AB8 = 0;
  }
}

```

## disassembly

```asm
0x18001a234  sub     rsp, 28h
0x18001a238  cmp     cs:dword_180024AB8, 1
0x18001a23f  jnz     short loc_18001A2AE
0x18001a241  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a248  call    cs:__imp_EnterCriticalSection
0x18001a24f  nop     dword ptr [rax+rax+00h]
0x18001a254  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x18001a25b  test    rax, rax
0x18001a25e  jz      short loc_18001A27E
0x18001a260  mov     rcx, cs:?g_hIoDevice@@3REAXEA; hObject
0x18001a267  call    cs:__imp_CloseHandle
0x18001a26e  nop     dword ptr [rax+rax+00h]
0x18001a273  mov     cs:?g_hIoDevice@@3REAXEA, 0; void * g_hIoDevice
0x18001a27e  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a285  call    cs:__imp_LeaveCriticalSection
0x18001a28c  nop     dword ptr [rax+rax+00h]
0x18001a291  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a298  call    cs:__imp_DeleteCriticalSection
0x18001a29f  nop     dword ptr [rax+rax+00h]
0x18001a2a4  mov     cs:dword_180024AB8, 0
0x18001a2ae  add     rsp, 28h
0x18001a2b2  retn
```
