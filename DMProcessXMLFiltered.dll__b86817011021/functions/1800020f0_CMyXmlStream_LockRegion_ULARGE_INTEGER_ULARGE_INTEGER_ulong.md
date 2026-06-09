# CMyXmlStream::LockRegion(_ULARGE_INTEGER,_ULARGE_INTEGER,ulong)

- ea: `0x1800020f0`
- end: `0x1800020f6`
- name: `?LockRegion@CMyXmlStream@@UEAAJT_ULARGE_INTEGER@@0K@Z`
- size: `6`
- prototype: `__int64 __fastcall(CMyXmlStream *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CMyXmlStream::LockRegion(CMyXmlStream *this, union _ULARGE_INTEGER a2, union _ULARGE_INTEGER a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800020f0  mov     eax, 80004001h
0x1800020f5  retn
```
