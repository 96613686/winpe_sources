# __acrt_lowio_destroy_handle_array

- ea: `0x140008370`
- end: `0x1400083c0`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008850`

## callees

- `0x140006940`
- `0x140008370`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140008399`
- `KERNEL32!DeleteCriticalSection` at `0x140008399`

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
0x140008370  test    rcx, rcx
0x140008373  jz      short locret_1400083BF
0x140008375  mov     [rsp+arg_0], rbx
0x14000837a  mov     [rsp+arg_8], rsi
0x14000837f  push    rdi
0x140008380  sub     rsp, 20h
0x140008384  lea     rsi, [rcx+1200h]
0x14000838b  mov     rbx, rcx
0x14000838e  mov     rdi, rcx
0x140008391  cmp     rcx, rsi
0x140008394  jz      short loc_1400083A8
0x140008396  mov     rcx, rdi; lpCriticalSection
0x140008399  call    cs:DeleteCriticalSection
0x14000839f  add     rdi, 48h ; 'H'
0x1400083a3  cmp     rdi, rsi
0x1400083a6  jnz     short loc_140008396
0x1400083a8  mov     rcx, rbx; Block
0x1400083ab  call    _free_base
0x1400083b0  mov     rbx, [rsp+28h+arg_0]
0x1400083b5  mov     rsi, [rsp+28h+arg_8]
0x1400083ba  add     rsp, 20h
0x1400083be  pop     rdi
0x1400083bf  retn
```
