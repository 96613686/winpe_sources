# CPrxAVIFile::CreateStream(IAVIStream * *,_AVISTREAMINFOW *)

- ea: `0x1800049c0`
- end: `0x1800049c6`
- name: `?CreateStream@CPrxAVIFile@@UEAAJPEAPEAUIAVIStream@@PEAU_AVISTREAMINFOW@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CPrxAVIFile *__hidden this, struct IAVIStream **, struct _AVISTREAMINFOW *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CPrxAVIFile::CreateStream(CPrxAVIFile *this, struct IAVIStream **a2, struct _AVISTREAMINFOW *a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800049c0  mov     eax, 80004001h
0x1800049c5  retn
```
