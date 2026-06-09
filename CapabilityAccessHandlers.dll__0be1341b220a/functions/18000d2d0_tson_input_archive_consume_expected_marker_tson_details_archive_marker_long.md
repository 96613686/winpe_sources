# tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)

- ea: `0x18000d2d0`
- end: `0x18000d302`
- name: `?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z`
- size: `50`
- prototype: `char __fastcall(tson::read_buffer **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa6c`
- `0x18000ad0c`
- `0x18000debc`
- `0x18000eed0`

## callees

- `0x18000d0f4`
- `0x18000d2d0`

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
0x18000d2d0  sub     rsp, 28h
0x18000d2d4  mov     r9, rcx
0x18000d2d7  mov     r10b, dl
0x18000d2da  mov     rcx, [rcx]; this
0x18000d2dd  call    ?advance@read_buffer@tson@@QEAAPEAEXZ; tson::read_buffer::advance(void)
0x18000d2e2  test    rax, rax
0x18000d2e5  jz      short loc_18000D2FB
0x18000d2e7  cmp     r10b, [rax]
0x18000d2ea  jnz     short loc_18000D2F0
0x18000d2ec  mov     al, 1
0x18000d2ee  jmp     short loc_18000D2FD
0x18000d2f0  cmp     dword ptr [r9+8], 0
0x18000d2f5  jl      short loc_18000D2FB
0x18000d2f7  mov     [r9+8], r8d
0x18000d2fb  xor     al, al
0x18000d2fd  add     rsp, 28h
0x18000d301  retn
```
