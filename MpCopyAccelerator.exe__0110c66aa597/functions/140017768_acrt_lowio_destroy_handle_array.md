# __acrt_lowio_destroy_handle_array

- ea: `0x140017768`
- end: `0x1400177b8`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014610`

## callees

- `0x140013e10`
- `0x140017768`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140017791`
- `KERNEL32!DeleteCriticalSection` at `0x140017791`

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
0x140017768  test    rcx, rcx
0x14001776b  jz      short locret_1400177B7
0x14001776d  mov     [rsp+arg_0], rbx
0x140017772  mov     [rsp+arg_8], rsi
0x140017777  push    rdi
0x140017778  sub     rsp, 20h
0x14001777c  lea     rsi, [rcx+1200h]
0x140017783  mov     rbx, rcx
0x140017786  mov     rdi, rcx
0x140017789  cmp     rcx, rsi
0x14001778c  jz      short loc_1400177A0
0x14001778e  mov     rcx, rdi; lpCriticalSection
0x140017791  call    cs:__imp_DeleteCriticalSection
0x140017797  add     rdi, 48h ; 'H'
0x14001779b  cmp     rdi, rsi
0x14001779e  jnz     short loc_14001778E
0x1400177a0  mov     rcx, rbx; Block
0x1400177a3  call    _free_base
0x1400177a8  mov     rbx, [rsp+28h+arg_0]
0x1400177ad  mov     rsi, [rsp+28h+arg_8]
0x1400177b2  add     rsp, 20h
0x1400177b6  pop     rdi
0x1400177b7  retn
```
