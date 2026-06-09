# CEditStream::AddRef(void)

- ea: `0x180010ed8`
- end: `0x180010ee5`
- name: `?AddRef@CEditStream@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CEditStream *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180010e80`
- `0x180010ea0`
- `0x180010ec0`

## pseudocode

```c
__int64 __fastcall CEditStream::AddRef(CEditStream *this)
{
  return (unsigned int)++*((_DWORD *)this - 66);
}

```

## disassembly

```asm
0x180010ed8  inc     dword ptr [rcx-108h]
0x180010ede  mov     eax, [rcx-108h]
0x180010ee4  retn
```
