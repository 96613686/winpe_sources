# memcpy_s

- ea: `0x18000af04`
- end: `0x18000af8d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002b5c`
- `0x1800068a4`
- `0x18000691c`
- `0x180008148`

## callees

- `0x180004572`
- `0x1800045ba`
- `0x18000af04`
- `0x18000b180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af2a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af2a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af6b`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v8; // rax
  errno_t v9; // ebx

  if ( !SourceSize )
    return 0;
  if ( !Destination )
    goto LABEL_4;
  if ( Source && DestinationSize >= SourceSize )
  {
    memcpy_0(Destination, Source, SourceSize);
    return 0;
  }
  memset_0(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = (errno_t *)_o__errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x18000af04  mov     [rsp+arg_0], rbx
0x18000af09  mov     [rsp+arg_8], rsi
0x18000af0e  push    rdi
0x18000af0f  sub     rsp, 20h
0x18000af13  mov     rbx, r9
0x18000af16  mov     rsi, r8
0x18000af19  mov     rdi, rdx
0x18000af1c  test    r9, r9
0x18000af1f  jnz     short loc_18000AF25
0x18000af21  xor     eax, eax
0x18000af23  jmp     short loc_18000AF7D
0x18000af25  test    rcx, rcx
0x18000af28  jnz     short loc_18000AF40
0x18000af2a  call    cs:__imp__o__errno
0x18000af30  mov     ebx, 16h
0x18000af35  mov     [rax], ebx
0x18000af37  call    _invalid_parameter_noinfo
0x18000af3c  mov     eax, ebx
0x18000af3e  jmp     short loc_18000AF7D
0x18000af40  test    rsi, rsi
0x18000af43  jz      short loc_18000AF57
0x18000af45  cmp     rdi, rbx
0x18000af48  jb      short loc_18000AF57
0x18000af4a  mov     r8, rbx; Size
0x18000af4d  mov     rdx, rsi; Src
0x18000af50  call    memcpy_0
0x18000af55  jmp     short loc_18000AF21
0x18000af57  mov     r8, rdi; Size
0x18000af5a  xor     edx, edx; Val
0x18000af5c  call    memset_0
0x18000af61  test    rsi, rsi
0x18000af64  jz      short loc_18000AF2A
0x18000af66  cmp     rdi, rbx
0x18000af69  jnb     short loc_18000AF78
0x18000af6b  call    cs:__imp__o__errno
0x18000af71  mov     ebx, 22h ; '"'
0x18000af76  jmp     short loc_18000AF35
0x18000af78  mov     eax, 16h
0x18000af7d  mov     rbx, [rsp+28h+arg_0]
0x18000af82  mov     rsi, [rsp+28h+arg_8]
0x18000af87  add     rsp, 20h
0x18000af8b  pop     rdi
0x18000af8c  retn
```
