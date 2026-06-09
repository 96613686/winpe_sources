# I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE

- ea: `0x18000f100`
- end: `0x18000f1ef`
- name: `I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE`
- size: `239`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000f100`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f16c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f16c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f183`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f183`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f122`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f122`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f10d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1de`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE(HANDLE *lpMem)
{
  HANDLE v2; // rcx
  HANDLE v3; // rcx
  HANDLE v4; // rcx
  HANDLE v5; // rcx
  HANDLE v6; // rcx
  void (__fastcall *v7)(HANDLE); // rax
  HANDLE ProcessHeap; // rax

  SetEvent(lpMem[9]);
  WaitForSingleObject(lpMem[5], 0xFFFFFFFF);
  v2 = lpMem[5];
  if ( v2 )
    CloseHandle(v2);
  v3 = lpMem[9];
  if ( v3 )
    CloseHandle(v3);
  v4 = lpMem[7];
  if ( v4 )
    CloseHandle(v4);
  v5 = lpMem[8];
  if ( v5 )
    CloseHandle(v5);
  v6 = lpMem[6];
  if ( v6 )
    CloseHandle(v6);
  v7 = (void (__fastcall *)(HANDLE))lpMem[4];
  if ( v7 )
    v7(lpMem[1]);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 8u, lpMem);
  return 0;
}

```

## disassembly

```asm
0x18000f100  push    rbx
0x18000f102  sub     rsp, 20h
0x18000f106  mov     rbx, rcx
0x18000f109  mov     rcx, [rcx+48h]; hEvent
0x18000f10d  call    cs:__imp_SetEvent
0x18000f114  nop     dword ptr [rax+rax+00h]
0x18000f119  mov     rcx, [rbx+28h]; hHandle
0x18000f11d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f122  call    cs:__imp_WaitForSingleObject
0x18000f129  nop     dword ptr [rax+rax+00h]
0x18000f12e  mov     rcx, [rbx+28h]; hObject
0x18000f132  test    rcx, rcx
0x18000f135  jnz     short loc_18000F1A6
0x18000f137  mov     rcx, [rbx+48h]; hObject
0x18000f13b  test    rcx, rcx
0x18000f13e  jnz     short loc_18000F198
0x18000f140  mov     rcx, [rbx+38h]; hObject
0x18000f144  test    rcx, rcx
0x18000f147  jnz     loc_18000F1CD
0x18000f14d  mov     rcx, [rbx+40h]; hObject
0x18000f151  test    rcx, rcx
0x18000f154  jnz     loc_18000F1DE
0x18000f15a  mov     rcx, [rbx+30h]; hObject
0x18000f15e  test    rcx, rcx
0x18000f161  jnz     short loc_18000F1BF
0x18000f163  mov     rax, [rbx+20h]
0x18000f167  test    rax, rax
0x18000f16a  jnz     short loc_18000F1B4
0x18000f16c  call    cs:__imp_GetProcessHeap
0x18000f173  nop     dword ptr [rax+rax+00h]
0x18000f178  mov     r8, rbx; lpMem
0x18000f17b  mov     edx, 8; dwFlags
0x18000f180  mov     rcx, rax; hHeap
0x18000f183  call    cs:__imp_HeapFree
0x18000f18a  nop     dword ptr [rax+rax+00h]
0x18000f18f  xor     eax, eax
0x18000f191  add     rsp, 20h
0x18000f195  pop     rbx
0x18000f196  retn
0x18000f198  call    cs:__imp_CloseHandle
0x18000f19f  nop     dword ptr [rax+rax+00h]
0x18000f1a4  jmp     short loc_18000F140
0x18000f1a6  call    cs:__imp_CloseHandle
0x18000f1ad  nop     dword ptr [rax+rax+00h]
0x18000f1b2  jmp     short loc_18000F137
0x18000f1b4  mov     rcx, [rbx+8]
0x18000f1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1bd  jmp     short loc_18000F16C
0x18000f1bf  call    cs:__imp_CloseHandle
0x18000f1c6  nop     dword ptr [rax+rax+00h]
0x18000f1cb  jmp     short loc_18000F163
0x18000f1cd  call    cs:__imp_CloseHandle
0x18000f1d4  nop     dword ptr [rax+rax+00h]
0x18000f1d9  jmp     loc_18000F14D
0x18000f1de  call    cs:__imp_CloseHandle
0x18000f1e5  nop     dword ptr [rax+rax+00h]
0x18000f1ea  jmp     loc_18000F15A
```
