# ___acrt_lowio_destroy_handle_array

- ea: `0x410324`
- end: `0x410359`
- name: `___acrt_lowio_destroy_handle_array`
- size: `53`
- prototype: `void __cdecl(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x410720`

## callees

- `0x40ed53`
- `0x410324`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x410340`
- `KERNEL32!DeleteCriticalSection` at `0x410340`

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
0x410324  mov     edi, edi
0x410326  push    ebp
0x410327  mov     ebp, esp
0x410329  push    esi
0x41032a  mov     esi, [ebp+lpCriticalSection]
0x41032d  test    esi, esi
0x41032f  jz      short loc_410356
0x410331  push    ebx
0x410332  lea     ebx, [esi+0E00h]
0x410338  push    edi
0x410339  mov     edi, esi
0x41033b  cmp     esi, ebx
0x41033d  jz      short loc_41034D
0x41033f  push    edi; lpCriticalSection
0x410340  call    ds:DeleteCriticalSection
0x410346  add     edi, 38h ; '8'
0x410349  cmp     edi, ebx
0x41034b  jnz     short loc_41033F
0x41034d  push    esi; Block
0x41034e  call    __free_base
0x410353  pop     ecx
0x410354  pop     edi
0x410355  pop     ebx
0x410356  pop     esi
0x410357  pop     ebp
0x410358  retn
```
