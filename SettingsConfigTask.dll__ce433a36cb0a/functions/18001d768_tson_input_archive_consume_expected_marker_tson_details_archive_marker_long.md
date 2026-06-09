# tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)

- ea: `0x18001d768`
- end: `0x18001d79a`
- name: `?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z`
- size: `50`
- prototype: `char __fastcall(tson::read_buffer **)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c5ec`
- `0x18000c660`
- `0x18000c714`
- `0x18000c77c`
- `0x18000c7e0`
- `0x18000c8bc`
- `0x18000c9d0`
- `0x18000ca38`
- `0x180010510`
- `0x1800105cc`
- `0x180010688`
- `0x18001099c`
- `0x180010a50`
- `0x180010d0c`
- `0x180010dd0`
- `0x180010eb4`
- `0x180010f58`
- `0x1800120fc`
- `0x18001dbe0`
- `0x18001dcf4`
- `0x18001eb78`
- `0x1800210fc`

## callees

- `0x18001d114`
- `0x18001d768`

## pseudocode

```c
char __fastcall tson::input_archive::consume_expected_marker(tson::read_buffer **a1)
{
  unsigned __int8 *v1; // rax
  int v2; // r8d
  __int64 v3; // r9
  char v4; // r10

  v1 = tson::read_buffer::advance(*a1);
  if ( v1 )
  {
    if ( v4 == *v1 )
      return 1;
    if ( *(int *)(v3 + 8) >= 0 )
      *(_DWORD *)(v3 + 8) = v2;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d768  sub     rsp, 28h
0x18001d76c  mov     r9, rcx
0x18001d76f  mov     r10b, dl
0x18001d772  mov     rcx, [rcx]; this
0x18001d775  call    ?advance@read_buffer@tson@@QEAAPEAEXZ; tson::read_buffer::advance(void)
0x18001d77a  test    rax, rax
0x18001d77d  jz      short loc_18001D793
0x18001d77f  cmp     r10b, [rax]
0x18001d782  jnz     short loc_18001D788
0x18001d784  mov     al, 1
0x18001d786  jmp     short loc_18001D795
0x18001d788  cmp     dword ptr [r9+8], 0
0x18001d78d  jl      short loc_18001D793
0x18001d78f  mov     [r9+8], r8d
0x18001d793  xor     al, al
0x18001d795  add     rsp, 28h
0x18001d799  retn
```
