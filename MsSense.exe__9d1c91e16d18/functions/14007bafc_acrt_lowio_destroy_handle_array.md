# __acrt_lowio_destroy_handle_array

- ea: `0x14007bafc`
- end: `0x14007bb4c`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `void __fastcall(char *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140073c60`

## callees

- `0x140072280`
- `0x14007bafc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14007bb25`
- `KERNEL32!DeleteCriticalSection` at `0x14007bb25`

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
0x14007bafc  test    rcx, rcx
0x14007baff  jz      short locret_14007BB4B
0x14007bb01  mov     [rsp+arg_0], rbx
0x14007bb06  mov     [rsp+arg_8], rsi
0x14007bb0b  push    rdi
0x14007bb0c  sub     rsp, 20h
0x14007bb10  lea     rsi, [rcx+1200h]
0x14007bb17  mov     rbx, rcx
0x14007bb1a  mov     rdi, rcx
0x14007bb1d  cmp     rcx, rsi
0x14007bb20  jz      short loc_14007BB34
0x14007bb22  mov     rcx, rdi; lpCriticalSection
0x14007bb25  call    cs:__imp_DeleteCriticalSection
0x14007bb2b  add     rdi, 48h ; 'H'
0x14007bb2f  cmp     rdi, rsi
0x14007bb32  jnz     short loc_14007BB22
0x14007bb34  mov     rcx, rbx; Block
0x14007bb37  call    _free_base
0x14007bb3c  mov     rbx, [rsp+28h+arg_0]
0x14007bb41  mov     rsi, [rsp+28h+arg_8]
0x14007bb46  add     rsp, 20h
0x14007bb4a  pop     rdi
0x14007bb4b  retn
```
