# WaveFileDeleteStream

- ea: `0x180005e30`
- end: `0x180005e95`
- name: `WaveFileDeleteStream`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005e30`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005e5f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005e5f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e6c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e6c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005e75`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005e75`

## pseudocode

```c
__int64 __fastcall WaveFileDeleteStream(__int64 a1, int a2, int a3)
{
  const void *v4; // rcx
  HGLOBAL v5; // rax
  HGLOBAL v6; // rax
  __int64 result; // rax

  v4 = *(const void **)(a1 + 272);
  if ( !v4 || a3 || a2 && a2 != 1935963489 )
    return 2147762282LL;
  v5 = GlobalHandle(v4);
  GlobalUnlock(v5);
  v6 = GlobalHandle(*(LPCVOID *)(a1 + 272));
  GlobalFree(v6);
  result = 0;
  *(_QWORD *)(a1 + 272) = 0;
  return result;
}

```

## disassembly

```asm
0x180005e30  push    rbx
0x180005e32  sub     rsp, 20h
0x180005e36  mov     rbx, rcx
0x180005e39  mov     rcx, [rcx+110h]; pMem
0x180005e40  test    rcx, rcx
0x180005e43  jz      short loc_180005E8A
0x180005e45  test    r8d, r8d
0x180005e48  jnz     short loc_180005E8A
0x180005e4a  test    edx, edx
0x180005e4c  jz      short loc_180005E56
0x180005e4e  cmp     edx, 73647561h
0x180005e54  jnz     short loc_180005E8A
0x180005e56  call    cs:__imp_GlobalHandle
0x180005e5c  mov     rcx, rax; hMem
0x180005e5f  call    cs:__imp_GlobalUnlock
0x180005e65  mov     rcx, [rbx+110h]; pMem
0x180005e6c  call    cs:__imp_GlobalHandle
0x180005e72  mov     rcx, rax; hMem
0x180005e75  call    cs:__imp_GlobalFree
0x180005e7b  xor     eax, eax
0x180005e7d  mov     qword ptr [rbx+110h], 0
0x180005e88  jmp     short loc_180005E8F
0x180005e8a  mov     eax, 8004406Ah
0x180005e8f  add     rsp, 20h
0x180005e93  pop     rbx
0x180005e94  retn
```
