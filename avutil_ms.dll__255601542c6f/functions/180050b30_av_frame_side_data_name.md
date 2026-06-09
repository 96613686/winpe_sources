# av_frame_side_data_name

- ea: `0x180050b30`
- end: `0x180050b4b`
- name: `av_frame_side_data_name`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180050a80`
- `0x180050b30`

## pseudocode

```c
char *__fastcall av_frame_side_data_name(unsigned int a1)
{
  char **v1; // rcx
  char *result; // rax

  v1 = av_frame_side_data_desc(a1);
  result = 0;
  if ( v1 )
    return *v1;
  return result;
}

```

## disassembly

```asm
0x180050b30  sub     rsp, 28h
0x180050b34  call    av_frame_side_data_desc
0x180050b39  mov     rcx, rax
0x180050b3c  xor     eax, eax
0x180050b3e  test    rcx, rcx
0x180050b41  jz      short loc_180050B46
0x180050b43  mov     rax, [rcx]
0x180050b46  add     rsp, 28h
0x180050b4a  retn
```
