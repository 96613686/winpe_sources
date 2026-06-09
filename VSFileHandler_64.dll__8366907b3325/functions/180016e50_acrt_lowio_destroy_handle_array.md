# __acrt_lowio_destroy_handle_array

- ea: `0x180016e50`
- end: `0x180016ea0`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f70`

## callees

- `0x18000fe3c`
- `0x180016e50`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180016e79`
- `KERNEL32!DeleteCriticalSection` at `0x180016e79`

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
0x180016e50  test    rcx, rcx
0x180016e53  jz      short locret_180016E9F
0x180016e55  mov     [rsp+arg_0], rbx
0x180016e5a  mov     [rsp+arg_8], rsi
0x180016e5f  push    rdi
0x180016e60  sub     rsp, 20h
0x180016e64  lea     rsi, [rcx+1200h]
0x180016e6b  mov     rbx, rcx
0x180016e6e  mov     rdi, rcx
0x180016e71  cmp     rcx, rsi
0x180016e74  jz      short loc_180016E88
0x180016e76  mov     rcx, rdi; lpCriticalSection
0x180016e79  call    cs:__imp_DeleteCriticalSection
0x180016e7f  add     rdi, 48h ; 'H'
0x180016e83  cmp     rdi, rsi
0x180016e86  jnz     short loc_180016E76
0x180016e88  mov     rcx, rbx; Block
0x180016e8b  call    _free_base
0x180016e90  mov     rbx, [rsp+28h+arg_0]
0x180016e95  mov     rsi, [rsp+28h+arg_8]
0x180016e9a  add     rsp, 20h
0x180016e9e  pop     rdi
0x180016e9f  retn
```
