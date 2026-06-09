# OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&LocalFree(void *)>(void)

- ea: `0x140004d30`
- end: `0x140004d49`
- name: `??1?$OnDeleteIf@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@QEAA@XZ`
- size: `25`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005140`
- `0x1400151a1`

## callees

- `0x140004d30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d3d`

## pseudocode

```c
HLOCAL __fastcall OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>::~OnDeleteIf<void *,void * (*)(void *),&void * LocalFree(void *)>(
        __int64 a1)
{
  HLOCAL result; // rax

  if ( !*(_BYTE *)(a1 + 8) )
    return LocalFree(*(HLOCAL *)a1);
  return result;
}

```

## disassembly

```asm
0x140004d30  sub     rsp, 28h
0x140004d34  cmp     byte ptr [rcx+8], 0
0x140004d38  jnz     short loc_140004D44
0x140004d3a  mov     rcx, [rcx]; hMem
0x140004d3d  call    cs:__imp_LocalFree
0x140004d43  nop
0x140004d44  add     rsp, 28h
0x140004d48  retn
```
