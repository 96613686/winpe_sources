# __acrt_lowio_destroy_handle_array

- ea: `0x180014974`
- end: `0x1800149c4`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e920`

## callees

- `0x180008040`
- `0x180014974`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001499d`
- `KERNEL32!DeleteCriticalSection` at `0x18001499d`

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
0x180014974  test    rcx, rcx
0x180014977  jz      short locret_1800149C3
0x180014979  mov     [rsp+arg_0], rbx
0x18001497e  mov     [rsp+arg_8], rsi
0x180014983  push    rdi
0x180014984  sub     rsp, 20h
0x180014988  lea     rsi, [rcx+1200h]
0x18001498f  mov     rbx, rcx
0x180014992  mov     rdi, rcx
0x180014995  cmp     rcx, rsi
0x180014998  jz      short loc_1800149AC
0x18001499a  mov     rcx, rdi; lpCriticalSection
0x18001499d  call    cs:__imp_DeleteCriticalSection
0x1800149a3  add     rdi, 48h ; 'H'
0x1800149a7  cmp     rdi, rsi
0x1800149aa  jnz     short loc_18001499A
0x1800149ac  mov     rcx, rbx; Block
0x1800149af  call    _free_base
0x1800149b4  mov     rbx, [rsp+28h+arg_0]
0x1800149b9  mov     rsi, [rsp+28h+arg_8]
0x1800149be  add     rsp, 20h
0x1800149c2  pop     rdi
0x1800149c3  retn
```
