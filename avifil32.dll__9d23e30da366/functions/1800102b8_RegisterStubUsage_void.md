# RegisterStubUsage(void)

- ea: `0x1800102b8`
- end: `0x18001031a`
- name: `?RegisterStubUsage@@YAXXZ`
- size: `98`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000ec20`
- `0x18000ee80`

## callees

- `0x1800102b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800102bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800102bc`

## pseudocode

```c
void RegisterStubUsage(void)
{
  HTASK *CurrentThreadId; // rdx
  __int64 v1; // rax
  __int64 v2; // rax

  CurrentThreadId = (HTASK *)(int)GetCurrentThreadId();
  v1 = 0;
  do
  {
    if ( (&ahtaskUsed)[v1] == CurrentThreadId )
    {
      ++*((_DWORD *)&aiRefCount + v1);
      return;
    }
    v1 = (unsigned int)(v1 + 1);
  }
  while ( (int)v1 < 64 );
  v2 = 0;
  while ( (&ahtaskUsed)[v2] )
  {
    v2 = (unsigned int)(v2 + 1);
    if ( (int)v2 >= 64 )
      return;
  }
  (&ahtaskUsed)[v2] = CurrentThreadId;
  *((_DWORD *)&aiRefCount + v2) = 1;
}

```

## disassembly

```asm
0x1800102b8  sub     rsp, 28h
0x1800102bc  call    cs:__imp_GetCurrentThreadId
0x1800102c2  movsxd  rdx, eax
0x1800102c5  lea     r8, cs:180000000h
0x1800102cc  xor     eax, eax
0x1800102ce  lea     r9d, [rax+1]
0x1800102d2  cmp     rva ?ahtaskUsed@@3PAPEAUHTASK__@@A[r8+rax*8], rdx; HTASK__ * near * ahtaskUsed ...
0x1800102da  jz      short loc_18001030D
0x1800102dc  add     eax, r9d
0x1800102df  cmp     eax, 40h ; '@'
0x1800102e2  jl      short loc_1800102D2
0x1800102e4  xor     eax, eax
0x1800102e6  cmp     rva ?ahtaskUsed@@3PAPEAUHTASK__@@A[r8+rax*8], 0; HTASK__ * near * ahtaskUsed ...
0x1800102ef  jz      short loc_1800102FB
0x1800102f1  add     eax, r9d
0x1800102f4  cmp     eax, 40h ; '@'
0x1800102f7  jl      short loc_1800102E6
0x1800102f9  jmp     short loc_180010315
0x1800102fb  mov     rva ?ahtaskUsed@@3PAPEAUHTASK__@@A[r8+rax*8], rdx; HTASK__ * near * ahtaskUsed ...
0x180010303  mov     rva ?aiRefCount@@3PAHA[r8+rax*4], r9d; int near * aiRefCount ...
0x18001030b  jmp     short loc_180010315
0x18001030d  add     rva ?aiRefCount@@3PAHA[r8+rax*4], r9d; int near * aiRefCount ...
0x180010315  add     rsp, 28h
0x180010319  retn
```
