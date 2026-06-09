# memcpy_s

- ea: `0x18000c93c`
- end: `0x18000c9c5`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180001830`
- `0x1800080c8`
- `0x180015428`
- `0x180015740`
- `0x180015b84`

## callees

- `0x18000a832`
- `0x18000a856`
- `0x18000c93c`
- `0x180018b49`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c962`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c9a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c962`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c9a3`

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
0x18000c93c  mov     [rsp+arg_0], rbx
0x18000c941  mov     [rsp+arg_8], rsi
0x18000c946  push    rdi
0x18000c947  sub     rsp, 20h
0x18000c94b  mov     rbx, r9
0x18000c94e  mov     rsi, r8
0x18000c951  mov     rdi, rdx
0x18000c954  test    r9, r9
0x18000c957  jnz     short loc_18000C95D
0x18000c959  xor     eax, eax
0x18000c95b  jmp     short loc_18000C9B5
0x18000c95d  test    rcx, rcx
0x18000c960  jnz     short loc_18000C978
0x18000c962  call    cs:__imp__o__errno
0x18000c968  mov     ebx, 16h
0x18000c96d  mov     [rax], ebx
0x18000c96f  call    _invalid_parameter_noinfo
0x18000c974  mov     eax, ebx
0x18000c976  jmp     short loc_18000C9B5
0x18000c978  test    rsi, rsi
0x18000c97b  jz      short loc_18000C98F
0x18000c97d  cmp     rdi, rbx
0x18000c980  jb      short loc_18000C98F
0x18000c982  mov     r8, rbx; Size
0x18000c985  mov     rdx, rsi; Src
0x18000c988  call    memcpy_0
0x18000c98d  jmp     short loc_18000C959
0x18000c98f  mov     r8, rdi; Size
0x18000c992  xor     edx, edx; Val
0x18000c994  call    memset_0
0x18000c999  test    rsi, rsi
0x18000c99c  jz      short loc_18000C962
0x18000c99e  cmp     rdi, rbx
0x18000c9a1  jnb     short loc_18000C9B0
0x18000c9a3  call    cs:__imp__o__errno
0x18000c9a9  mov     ebx, 22h ; '"'
0x18000c9ae  jmp     short loc_18000C96D
0x18000c9b0  mov     eax, 16h
0x18000c9b5  mov     rbx, [rsp+28h+arg_0]
0x18000c9ba  mov     rsi, [rsp+28h+arg_8]
0x18000c9bf  add     rsp, 20h
0x18000c9c3  pop     rdi
0x18000c9c4  retn
```
