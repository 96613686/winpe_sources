# __acrt_lowio_destroy_handle_array

- ea: `0x14001e358`
- end: `0x14001e3a8`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `void __fastcall(char *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b470`

## callees

- `0x140019930`
- `0x14001e358`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001e381`
- `KERNEL32!DeleteCriticalSection` at `0x14001e381`

## pseudocode

```c
void __fastcall _acrt_lowio_destroy_handle_array(char *Block)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  if ( Block )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(Block + 4608);
    v3 = (struct _RTL_CRITICAL_SECTION *)Block;
    do
    {
      DeleteCriticalSection(v3);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 72);
    }
    while ( v3 != v1 );
    free_base(Block);
  }
}

```

## disassembly

```asm
0x14001e358  test    rcx, rcx
0x14001e35b  jz      short locret_14001E3A7
0x14001e35d  mov     [rsp+arg_0], rbx
0x14001e362  mov     [rsp+arg_8], rsi
0x14001e367  push    rdi
0x14001e368  sub     rsp, 20h
0x14001e36c  lea     rsi, [rcx+1200h]
0x14001e373  mov     rbx, rcx
0x14001e376  mov     rdi, rcx
0x14001e379  cmp     rcx, rsi
0x14001e37c  jz      short loc_14001E390
0x14001e37e  mov     rcx, rdi; lpCriticalSection
0x14001e381  call    cs:__imp_DeleteCriticalSection
0x14001e387  add     rdi, 48h ; 'H'
0x14001e38b  cmp     rdi, rsi
0x14001e38e  jnz     short loc_14001E37E
0x14001e390  mov     rcx, rbx; Block
0x14001e393  call    _free_base
0x14001e398  mov     rbx, [rsp+28h+arg_0]
0x14001e39d  mov     rsi, [rsp+28h+arg_8]
0x14001e3a2  add     rsp, 20h
0x14001e3a6  pop     rdi
0x14001e3a7  retn
```
