# DWORDMap::Compare(void const *,void const *)

- ea: `0x180019ec0`
- end: `0x180019ec5`
- name: `?Compare@DWORDMap@@KAHPEBX0@Z`
- size: `5`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall DWORDMap::Compare(_DWORD *a1, _DWORD *a2)
{
  return (unsigned int)(*a1 - *a2);
}

```

## disassembly

```asm
0x180019ec0  mov     eax, [rcx]
0x180019ec2  sub     eax, [rdx]
0x180019ec4  retn
```
