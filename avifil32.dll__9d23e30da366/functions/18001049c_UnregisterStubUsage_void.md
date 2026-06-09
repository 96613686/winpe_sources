# UnregisterStubUsage(void)

- ea: `0x18001049c`
- end: `0x1800104f2`
- name: `?UnregisterStubUsage@@YAXXZ`
- size: `86`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000eaa0`
- `0x18000eacc`

## callees

- `0x18001049c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104a0`

## pseudocode

```c
void UnregisterStubUsage(void)
{
  HTASK *CurrentThreadId; // rdx
  unsigned int v1; // ecx

  CurrentThreadId = (HTASK *)(int)GetCurrentThreadId();
  v1 = 0;
  while ( (&ahtaskUsed)[v1] != CurrentThreadId )
  {
    if ( (int)++v1 >= 64 )
      return;
  }
  if ( (int)--*((_DWORD *)&aiRefCount + v1) <= 0 )
  {
    (&ahtaskUsed)[v1] = 0;
    *((_DWORD *)&aiRefCount + v1) = 0;
  }
}

```

## disassembly

```asm
0x18001049c  sub     rsp, 28h
0x1800104a0  call    cs:__imp_GetCurrentThreadId
0x1800104a6  xor     r9d, r9d
0x1800104a9  movsxd  rdx, eax
0x1800104ac  mov     ecx, r9d
0x1800104af  lea     r8, cs:180000000h
0x1800104b6  mov     eax, ecx
0x1800104b8  cmp     rva ?ahtaskUsed@@3PAPEAUHTASK__@@A[r8+rax*8], rdx; HTASK__ * near * ahtaskUsed ...
0x1800104c0  jz      short loc_1800104CB
0x1800104c2  inc     ecx
0x1800104c4  cmp     ecx, 40h ; '@'
0x1800104c7  jl      short loc_1800104B6
0x1800104c9  jmp     short loc_1800104ED
0x1800104cb  dec     rva ?aiRefCount@@3PAHA[r8+rax*4]; int near * aiRefCount ...
0x1800104d3  cmp     rva ?aiRefCount@@3PAHA[r8+rax*4], r9d; int near * aiRefCount ...
0x1800104db  jg      short loc_1800104ED
0x1800104dd  mov     rva ?ahtaskUsed@@3PAPEAUHTASK__@@A[r8+rax*8], r9; HTASK__ * near * ahtaskUsed ...
0x1800104e5  mov     rva ?aiRefCount@@3PAHA[r8+rax*4], r9d; int near * aiRefCount ...
0x1800104ed  add     rsp, 28h
0x1800104f1  retn
```
