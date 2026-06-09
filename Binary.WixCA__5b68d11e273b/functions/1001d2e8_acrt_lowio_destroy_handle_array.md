# ___acrt_lowio_destroy_handle_array

- ea: `0x1001d2e8`
- end: `0x1001d31d`
- name: `___acrt_lowio_destroy_handle_array`
- size: `53`
- prototype: `int __cdecl(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10018a6e`

## callees

- `0x1001770e`
- `0x1001d2e8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1001d304`
- `KERNEL32!DeleteCriticalSection` at `0x1001d304`

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
0x1001d2e8  mov     edi, edi
0x1001d2ea  push    ebp
0x1001d2eb  mov     ebp, esp
0x1001d2ed  push    esi
0x1001d2ee  mov     esi, [ebp+lpCriticalSection]
0x1001d2f1  test    esi, esi
0x1001d2f3  jz      short loc_1001D31A
0x1001d2f5  push    ebx
0x1001d2f6  lea     ebx, [esi+0E00h]
0x1001d2fc  push    edi
0x1001d2fd  mov     edi, esi
0x1001d2ff  cmp     esi, ebx
0x1001d301  jz      short loc_1001D311
0x1001d303  push    edi; lpCriticalSection
0x1001d304  call    ds:DeleteCriticalSection
0x1001d30a  add     edi, 38h ; '8'
0x1001d30d  cmp     edi, ebx
0x1001d30f  jnz     short loc_1001D303
0x1001d311  push    esi; Block
0x1001d312  call    __free_base
0x1001d317  pop     ecx
0x1001d318  pop     edi
0x1001d319  pop     ebx
0x1001d31a  pop     esi
0x1001d31b  pop     ebp
0x1001d31c  retn
```
