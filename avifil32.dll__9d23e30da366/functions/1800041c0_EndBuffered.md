# EndBuffered

- ea: `0x1800041c0`
- end: `0x180004203`
- name: `EndBuffered`
- size: `67`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000420c`
- `0x18000b5c0`
- `0x18000b760`

## callees

- `0x1800041c0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800041db`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800041db`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800041d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800041e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800041d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800041e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041fc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800041ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800041ee`

## pseudocode

```c
HLOCAL __fastcall EndBuffered(LPCVOID *a1)
{
  LPCVOID v2; // rcx
  HGLOBAL v3; // rax
  HGLOBAL v4; // rax

  v2 = a1[1];
  if ( v2 )
  {
    v3 = GlobalHandle(v2);
    GlobalUnlock(v3);
    v4 = GlobalHandle(a1[1]);
    GlobalFree(v4);
  }
  return LocalFree(a1);
}

```

## disassembly

```asm
0x1800041c0  push    rbx
0x1800041c2  sub     rsp, 20h
0x1800041c6  mov     rbx, rcx
0x1800041c9  mov     rcx, [rcx+8]; pMem
0x1800041cd  test    rcx, rcx
0x1800041d0  jz      short loc_1800041F4
0x1800041d2  call    cs:__imp_GlobalHandle
0x1800041d8  mov     rcx, rax; hMem
0x1800041db  call    cs:__imp_GlobalUnlock
0x1800041e1  mov     rcx, [rbx+8]; pMem
0x1800041e5  call    cs:__imp_GlobalHandle
0x1800041eb  mov     rcx, rax; hMem
0x1800041ee  call    cs:__imp_GlobalFree
0x1800041f4  mov     rcx, rbx
0x1800041f7  add     rsp, 20h
0x1800041fb  pop     rbx
0x1800041fc  jmp     cs:__imp_LocalFree
```
