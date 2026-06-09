# OnDelete<void *,void * (*)(void *),&LocalFree(void *)>::~OnDelete<void *,void * (*)(void *),&LocalFree(void *)>(void)

- ea: `0x140004d14`
- end: `0x140004d27`
- name: `??1?$OnDelete@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@QEAA@XZ`
- size: `19`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14001516b`
- `0x1400151b3`
- `0x140015226`
- `0x14001524a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d1b`

## pseudocode

```c
HLOCAL __fastcall OnDelete<void *,void * (*)(void *),&void * LocalFree(void *)>::~OnDelete<void *,void * (*)(void *),&void * LocalFree(void *)>(
        HLOCAL *a1)
{
  return LocalFree(*a1);
}

```

## disassembly

```asm
0x140004d14  sub     rsp, 28h
0x140004d18  mov     rcx, [rcx]; hMem
0x140004d1b  call    cs:__imp_LocalFree
0x140004d21  nop
0x140004d22  add     rsp, 28h
0x140004d26  retn
```
