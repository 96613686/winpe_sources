# _errno

- ea: `0x18000bfbc`
- end: `0x18000bfdc`
- name: `_errno`
- size: `32`
- prototype: `int *__cdecl()`
- caller_count: `95`
- callee_count: `2`
- tags: ``

## callers

- `0x180003be8`
- `0x18000572c`
- `0x1800060c0`
- `0x180006918`
- `0x1800069b4`
- `0x180006b5c`
- `0x180006e34`
- `0x1800070d4`
- `0x18000baa0`
- `0x18000bb1c`
- `0x18000bb9c`
- `0x18000bfe4`
- `0x18000c07c`
- `0x18000c250`
- `0x18000c2f8`
- `0x18000c758`
- `0x18000c7fc`
- `0x18000ca68`
- `0x18000d23c`
- `0x18000d3c4`
- `0x18000dda0`
- `0x18000e820`
- `0x18000e8b8`
- `0x18000ebbc`
- `0x18000f264`
- `0x18000f554`
- `0x18000fe3c`
- `0x18000fe7c`
- `0x180010554`
- `0x180010590`
- `0x180010690`
- `0x180010818`
- `0x180010d58`
- `0x1800111c8`
- `0x180011764`
- `0x180011a9c`
- `0x1800120b0`
- `0x180012144`
- `0x1800122bc`
- `0x180012448`
- `0x180012af4`
- `0x180012d28`
- `0x1800131d8`
- `0x180014190`
- `0x180014d4c`
- `0x180014ec4`
- `0x180014f78`
- `0x18001550c`
- `0x180016750`
- `0x1800168e0`

## callees

- `0x18000bfbc`
- `0x180010420`

## pseudocode

```c
int *__cdecl errno()
{
  __int64 v0; // rax

  v0 = _acrt_getptd_noexit();
  if ( v0 )
    return (int *)(v0 + 32);
  else
    return (int *)&unk_18003D0C0;
}

```

## disassembly

```asm
0x18000bfbc  sub     rsp, 28h
0x18000bfc0  call    __acrt_getptd_noexit
0x18000bfc5  test    rax, rax
0x18000bfc8  jnz     short loc_18000BFD3
0x18000bfca  lea     rax, unk_18003D0C0
0x18000bfd1  jmp     short loc_18000BFD7
0x18000bfd3  add     rax, 20h ; ' '
0x18000bfd7  add     rsp, 28h
0x18000bfdb  retn
```
