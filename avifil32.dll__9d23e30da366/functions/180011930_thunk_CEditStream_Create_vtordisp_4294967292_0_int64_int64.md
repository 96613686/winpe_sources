# [thunk]:CEditStream::Create`vtordisp{4294967292,0}' (__int64,__int64)

- ea: `0x180011930`
- end: `0x18001193c`
- name: `?Create@CEditStream@@$4PPPPPPPM@A@EAAJ_J0@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011944`

## pseudocode

```c
__int64 __fastcall CEditStream::Create(__int64 a1, __int64 a2)
{
  return CEditStream::Create((CEditStream *)(a1 - *(int *)(a1 - 4)), a2);
}

```

## disassembly

```asm
0x180011930  movsxd  rax, dword ptr [rcx-4]
0x180011934  sub     rcx, rax; this
0x180011937  jmp     ?Create@CEditStream@@UEAAJ_J0@Z; CEditStream::Create(__int64,__int64)
```
