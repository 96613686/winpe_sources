# ___acrt_lowio_destroy_handle_array

- ea: `0x410fef`
- end: `0x411024`
- name: `___acrt_lowio_destroy_handle_array`
- size: `53`
- prototype: `void __cdecl(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x4113f0`

## callees

- `0x41001a`
- `0x410fef`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x41100b`
- `KERNEL32!DeleteCriticalSection` at `0x41100b`

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
0x410fef  mov     edi, edi
0x410ff1  push    ebp
0x410ff2  mov     ebp, esp
0x410ff4  push    esi
0x410ff5  mov     esi, [ebp+lpCriticalSection]
0x410ff8  test    esi, esi
0x410ffa  jz      short loc_411021
0x410ffc  push    ebx
0x410ffd  lea     ebx, [esi+0E00h]
0x411003  push    edi
0x411004  mov     edi, esi
0x411006  cmp     esi, ebx
0x411008  jz      short loc_411018
0x41100a  push    edi; lpCriticalSection
0x41100b  call    ds:DeleteCriticalSection
0x411011  add     edi, 38h ; '8'
0x411014  cmp     edi, ebx
0x411016  jnz     short loc_41100A
0x411018  push    esi; Block
0x411019  call    __free_base
0x41101e  pop     ecx
0x41101f  pop     edi
0x411020  pop     ebx
0x411021  pop     esi
0x411022  pop     ebp
0x411023  retn
```
