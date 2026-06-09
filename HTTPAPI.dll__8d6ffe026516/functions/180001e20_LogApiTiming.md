# LogApiTiming

- ea: `0x180001e20`
- end: `0x180001e62`
- name: `LogApiTiming`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001330`
- `0x180001d20`
- `0x180008480`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001e5b`

## pseudocode

```c
void __fastcall LogApiTiming(int a1, int a2)
{
  __int64 v2; // rax

  v2 = 3 * (32LL * a1 + (((unsigned __int8)_InterlockedExchangeAdd(&g_ApiCallInfoIndex[a1], 1u) + 1) & 0x1F));
  g_ApiCallInfos[v2] = a2;
  GetSystemTimeAsFileTime((LPFILETIME)&algn_180012884[4 * v2]);
}

```

## disassembly

```asm
0x180001e20  movsxd  r8, ecx
0x180001e23  mov     eax, 1
0x180001e28  lea     rcx, __ImageBase
0x180001e2f  lock xadd rva g_ApiCallInfoIndex[rcx+r8*4], eax
0x180001e39  inc     eax
0x180001e3b  shl     r8, 5
0x180001e3f  and     eax, 1Fh
0x180001e42  add     rax, r8
0x180001e45  lea     rax, [rax+rax*2]
0x180001e49  mov     rva g_ApiCallInfos[rcx+rax*4], edx
0x180001e50  lea     rcx, [rcx+rax*4]
0x180001e54  lea     rcx, [rcx+12884h]
0x180001e5b  jmp     cs:__imp_GetSystemTimeAsFileTime
```
