# __acrt_lowio_destroy_handle_array

- ea: `0x140015ff4`
- end: `0x140016044`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `void __fastcall(char *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012000`

## callees

- `0x1400107c4`
- `0x140015ff4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001601d`
- `KERNEL32!DeleteCriticalSection` at `0x14001601d`

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
0x140015ff4  test    rcx, rcx
0x140015ff7  jz      short locret_140016043
0x140015ff9  mov     [rsp+arg_0], rbx
0x140015ffe  mov     [rsp+arg_8], rsi
0x140016003  push    rdi
0x140016004  sub     rsp, 20h
0x140016008  lea     rsi, [rcx+1200h]
0x14001600f  mov     rbx, rcx
0x140016012  mov     rdi, rcx
0x140016015  cmp     rcx, rsi
0x140016018  jz      short loc_14001602C
0x14001601a  mov     rcx, rdi; lpCriticalSection
0x14001601d  call    cs:DeleteCriticalSection
0x140016023  add     rdi, 48h ; 'H'
0x140016027  cmp     rdi, rsi
0x14001602a  jnz     short loc_14001601A
0x14001602c  mov     rcx, rbx; Block
0x14001602f  call    _free_base
0x140016034  mov     rbx, [rsp+28h+arg_0]
0x140016039  mov     rsi, [rsp+28h+arg_8]
0x14001603e  add     rsp, 20h
0x140016042  pop     rdi
0x140016043  retn
```
