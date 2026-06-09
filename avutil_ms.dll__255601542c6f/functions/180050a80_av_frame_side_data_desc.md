# av_frame_side_data_desc

- ea: `0x180050a80`
- end: `0x180050aa2`
- name: `av_frame_side_data_desc`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180050760`
- `0x180050880`
- `0x180050b30`
- `0x180050b50`
- `0x180050cb0`

## callees

- `0x180050a80`

## pseudocode

```c
char **__fastcall av_frame_side_data_desc(unsigned int a1)
{
  char **result; // rax

  if ( a1 >= 0x1F )
    return 0;
  result = &(&off_180093950)[2 * a1];
  if ( !*result )
    return 0;
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x180050a80  cmp     ecx, 1Fh
0x180050a83  jnb     short loc_180050A9F
0x180050a85  mov     eax, ecx
0x180050a87  lea     rcx, off_180093950; "AVPanScan"
0x180050a8e  shl     rax, 4
0x180050a92  add     rax, rcx
0x180050a95  cmp     qword ptr [rax], 0
0x180050a99  jz      short loc_180050A9F
0x180050a9b  lfence
0x180050a9e  retn
0x180050a9f  xor     eax, eax
0x180050aa1  retn
```
