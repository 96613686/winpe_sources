# CIISSchema::CopyHere(ushort *,ushort *,IDispatch * *)

- ea: `0x180002c60`
- end: `0x180002c74`
- name: `?CopyHere@CIISSchema@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `20`
- prototype: `__int64 __fastcall(CIISSchema *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002c60`

## pseudocode

```c
__int64 __fastcall CIISSchema::CopyHere(
        CIISSchema *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  __int64 result; // rax

  result = 2147500035LL;
  if ( a2 )
  {
    if ( a4 )
      return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002c60  mov     eax, 80004003h
0x180002c65  test    rdx, rdx
0x180002c68  jz      short locret_180002C73
0x180002c6a  test    r9, r9
0x180002c6d  lea     ecx, [rax-2]
0x180002c70  cmovnz  eax, ecx
0x180002c73  retn
```
