# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)

- ea: `0x180005828`
- end: `0x180005849`
- name: `??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180014851`
- `0x180014863`
- `0x1800148fe`
- `0x180014910`

## callees

- `0x180002178`
- `0x180005828`

## pseudocode

```c
void __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
        void **a1)
{
  if ( *a1 != a1 + 2 )
    operator delete(*a1, (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x180005828  sub     rsp, 28h
0x18000582c  lea     rax, [rcx+10h]
0x180005830  cmp     [rcx], rax
0x180005833  jz      short loc_180005844
0x180005835  mov     rcx, [rcx]; void *
0x180005838  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000583f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005844  add     rsp, 28h
0x180005848  retn
```
