# _ResourceStringAllocCopyExLocalAlloc

- ea: `0x180009900`
- end: `0x180009928`
- name: `_ResourceStringAllocCopyExLocalAlloc`
- size: `40`
- prototype: `__int64 __fastcall(__int64, SIZE_T, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009800`

## callees

- `0x180009900`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000990b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000990b`

## pseudocode

```c
__int64 __fastcall ResourceStringAllocCopyExLocalAlloc(__int64 a1, SIZE_T a2, _QWORD *a3)
{
  HLOCAL v4; // rax

  v4 = LocalAlloc(0, a2);
  if ( !v4 )
    return 2147942414LL;
  *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x180009900  push    rbx
0x180009902  sub     rsp, 20h
0x180009906  xor     ecx, ecx; uFlags
0x180009908  mov     rbx, r8
0x18000990b  call    cs:__imp_LocalAlloc
0x180009911  test    rax, rax
0x180009914  jz      short loc_18000991D
0x180009916  mov     [rbx], rax
0x180009919  xor     eax, eax
0x18000991b  jmp     short loc_180009922
0x18000991d  mov     eax, 8007000Eh
0x180009922  add     rsp, 20h
0x180009926  pop     rbx
0x180009927  retn
```
