# __acrt_lowio_destroy_handle_array

- ea: `0x180014214`
- end: `0x180014264`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e1c0`

## callees

- `0x1800078e0`
- `0x180014214`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001423d`
- `KERNEL32!DeleteCriticalSection` at `0x18001423d`

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
0x180014214  test    rcx, rcx
0x180014217  jz      short locret_180014263
0x180014219  mov     [rsp+arg_0], rbx
0x18001421e  mov     [rsp+arg_8], rsi
0x180014223  push    rdi
0x180014224  sub     rsp, 20h
0x180014228  lea     rsi, [rcx+1200h]
0x18001422f  mov     rbx, rcx
0x180014232  mov     rdi, rcx
0x180014235  cmp     rcx, rsi
0x180014238  jz      short loc_18001424C
0x18001423a  mov     rcx, rdi; lpCriticalSection
0x18001423d  call    cs:__imp_DeleteCriticalSection
0x180014243  add     rdi, 48h ; 'H'
0x180014247  cmp     rdi, rsi
0x18001424a  jnz     short loc_18001423A
0x18001424c  mov     rcx, rbx; Block
0x18001424f  call    _free_base
0x180014254  mov     rbx, [rsp+28h+arg_0]
0x180014259  mov     rsi, [rsp+28h+arg_8]
0x18001425e  add     rsp, 20h
0x180014262  pop     rdi
0x180014263  retn
```
