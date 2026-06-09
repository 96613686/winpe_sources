# __acrt_lowio_destroy_handle_array

- ea: `0x18033b650`
- end: `0x18033b6a0`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18034c9f0`

## callees

- `0x18033b650`
- `0x18034962c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18033b679`
- `KERNEL32!DeleteCriticalSection` at `0x18033b679`

## pseudocode

```c
void __fastcall _acrt_lowio_destroy_handle_array(char *Block)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  if ( Block )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(Block + 4096);
    v3 = (struct _RTL_CRITICAL_SECTION *)Block;
    do
    {
      DeleteCriticalSection(v3);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 64);
    }
    while ( v3 != v1 );
    free_base(Block);
  }
}

```

## disassembly

```asm
0x18033b650  test    rcx, rcx
0x18033b653  jz      short locret_18033B69F
0x18033b655  mov     [rsp+arg_0], rbx
0x18033b65a  mov     [rsp+arg_8], rsi
0x18033b65f  push    rdi
0x18033b660  sub     rsp, 20h
0x18033b664  lea     rsi, [rcx+1000h]
0x18033b66b  mov     rbx, rcx
0x18033b66e  mov     rdi, rcx
0x18033b671  cmp     rcx, rsi
0x18033b674  jz      short loc_18033B688
0x18033b676  mov     rcx, rdi; lpCriticalSection
0x18033b679  call    cs:__imp_DeleteCriticalSection
0x18033b67f  add     rdi, 40h ; '@'
0x18033b683  cmp     rdi, rsi
0x18033b686  jnz     short loc_18033B676
0x18033b688  mov     rcx, rbx; Block
0x18033b68b  call    _free_base
0x18033b690  mov     rbx, [rsp+28h+arg_0]
0x18033b695  mov     rsi, [rsp+28h+arg_8]
0x18033b69a  add     rsp, 20h
0x18033b69e  pop     rdi
0x18033b69f  retn
```
