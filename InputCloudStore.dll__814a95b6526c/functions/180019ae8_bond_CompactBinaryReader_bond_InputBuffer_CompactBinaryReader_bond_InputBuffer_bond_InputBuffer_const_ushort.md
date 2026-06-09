# bond::CompactBinaryReader<bond::InputBuffer>::CompactBinaryReader<bond::InputBuffer>(bond::InputBuffer const &,ushort)

- ea: `0x180019ae8`
- end: `0x180019b05`
- name: `??0?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAA@AEBVInputBuffer@1@G@Z`
- size: `29`
- prototype: `__int64 __fastcall(bond::blob *, const struct bond::blob *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`

## callees

- `0x18001a4a4`

## pseudocode

```c
__int64 __fastcall bond::CompactBinaryReader<bond::InputBuffer>::CompactBinaryReader<bond::InputBuffer>(
        bond::blob *a1,
        const struct bond::blob *a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 result; // rax

  bond::blob::blob(a1, a2);
  result = v3;
  *(_DWORD *)(v3 + 32) = *(_DWORD *)(v2 + 32);
  *(_WORD *)(v3 + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x180019ae8  sub     rsp, 28h
0x180019aec  call    ??0blob@bond@@QEAA@AEBV01@@Z; bond::blob::blob(bond::blob const &)
0x180019af1  mov     edx, [rdx+20h]
0x180019af4  mov     rax, rcx
0x180019af7  mov     [rcx+20h], edx
0x180019afa  mov     word ptr [rcx+28h], 1
0x180019b00  add     rsp, 28h
0x180019b04  retn
```
