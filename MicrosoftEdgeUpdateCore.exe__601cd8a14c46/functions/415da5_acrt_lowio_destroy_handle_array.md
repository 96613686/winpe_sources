# ___acrt_lowio_destroy_handle_array

- ea: `0x415da5`
- end: `0x415dda`
- name: `___acrt_lowio_destroy_handle_array`
- size: `53`
- prototype: `void __cdecl(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x415410`

## callees

- `0x4136b2`
- `0x415da5`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x415dc1`
- `KERNEL32!DeleteCriticalSection` at `0x415dc1`

## pseudocode

```c
void __cdecl __acrt_lowio_destroy_handle_array(LPCRITICAL_SECTION lpCriticalSection)
{
  struct _RTL_CRITICAL_SECTION *v1; // edi

  if ( lpCriticalSection )
  {
    v1 = lpCriticalSection;
    do
    {
      DeleteCriticalSection(v1);
      v1 = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 56);
    }
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&lpCriticalSection[149].RecursionCount );
    _free_base(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x415da5  mov     edi, edi
0x415da7  push    ebp
0x415da8  mov     ebp, esp
0x415daa  push    esi
0x415dab  mov     esi, [ebp+lpCriticalSection]
0x415dae  test    esi, esi
0x415db0  jz      short loc_415DD7
0x415db2  push    ebx
0x415db3  lea     ebx, [esi+0E00h]
0x415db9  push    edi
0x415dba  mov     edi, esi
0x415dbc  cmp     esi, ebx
0x415dbe  jz      short loc_415DCE
0x415dc0  push    edi; lpCriticalSection
0x415dc1  call    ds:DeleteCriticalSection
0x415dc7  add     edi, 38h ; '8'
0x415dca  cmp     edi, ebx
0x415dcc  jnz     short loc_415DC0
0x415dce  push    esi; Block
0x415dcf  call    __free_base
0x415dd4  pop     ecx
0x415dd5  pop     edi
0x415dd6  pop     ebx
0x415dd7  pop     esi
0x415dd8  pop     ebp
0x415dd9  retn
```
