# __acrt_lowio_destroy_handle_array

- ea: `0x1802251e4`
- end: `0x180225234`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18021b060`

## callees

- `0x180219680`
- `0x1802251e4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18022520d`
- `KERNEL32!DeleteCriticalSection` at `0x18022520d`

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
0x1802251e4  test    rcx, rcx
0x1802251e7  jz      short locret_180225233
0x1802251e9  mov     [rsp+arg_0], rbx
0x1802251ee  mov     [rsp+arg_8], rsi
0x1802251f3  push    rdi
0x1802251f4  sub     rsp, 20h
0x1802251f8  lea     rsi, [rcx+1200h]
0x1802251ff  mov     rbx, rcx
0x180225202  mov     rdi, rcx
0x180225205  cmp     rcx, rsi
0x180225208  jz      short loc_18022521C
0x18022520a  mov     rcx, rdi; lpCriticalSection
0x18022520d  call    cs:__imp_DeleteCriticalSection
0x180225213  add     rdi, 48h ; 'H'
0x180225217  cmp     rdi, rsi
0x18022521a  jnz     short loc_18022520A
0x18022521c  mov     rcx, rbx; Block
0x18022521f  call    _free_base
0x180225224  mov     rbx, [rsp+28h+arg_0]
0x180225229  mov     rsi, [rsp+28h+arg_8]
0x18022522e  add     rsp, 20h
0x180225232  pop     rdi
0x180225233  retn
```
