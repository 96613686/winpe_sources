# bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)

- ea: `0x180020a28`
- end: `0x180020a52`
- name: `?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009cb0`
- `0x180009d50`
- `0x180009df0`
- `0x180009e90`
- `0x180009f30`
- `0x180018778`
- `0x180018a50`

## callees

- `0x18000f9c0`
- `0x180020a28`

## pseudocode

```c
__int64 __fastcall bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bond::InputBuffer *a1, char a2)
{
  __int64 result; // rax
  int v3; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    result = 2;
    if ( *((_WORD *)a1 + 20) == 2 )
    {
      v3 = 0;
      return bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a1, &v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020a28  sub     rsp, 28h
0x180020a2c  test    dl, dl
0x180020a2e  jnz     short loc_180020A4D
0x180020a30  mov     eax, 2
0x180020a35  cmp     ax, [rcx+28h]
0x180020a39  jnz     short loc_180020A4D
0x180020a3b  lea     rdx, [rsp+28h+arg_8]
0x180020a40  mov     [rsp+28h+arg_8], 0
0x180020a48  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180020a4d  add     rsp, 28h
0x180020a51  retn
```
