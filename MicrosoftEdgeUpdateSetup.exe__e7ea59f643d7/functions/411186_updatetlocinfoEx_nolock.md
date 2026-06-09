# __updatetlocinfoEx_nolock

- ea: `0x411186`
- end: `0x4111d6`
- name: `__updatetlocinfoEx_nolock`
- size: `80`
- prototype: `wchar_t **__cdecl(wchar_t ***, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x40bbcf`
- `0x411105`

## callees

- `0x410e3c`
- `0x410eb9`
- `0x411084`
- `0x411186`

## pseudocode

```c
wchar_t **__cdecl _updatetlocinfoEx_nolock(wchar_t ***a1, wchar_t **a2)
{
  wchar_t **v2; // edi

  if ( !a2 || !a1 )
    return 0;
  v2 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    __acrt_add_locale_ref(a2);
    if ( v2 )
    {
      __acrt_release_locale_ref(v2);
      if ( !v2[3] && v2 != &off_426580 )
        __acrt_free_locale(v2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x411186  mov     edi, edi
0x411188  push    ebp
0x411189  mov     ebp, esp
0x41118b  push    esi
0x41118c  mov     esi, [ebp+arg_4]
0x41118f  push    edi
0x411190  test    esi, esi
0x411192  jz      short loc_4111D0
0x411194  mov     eax, [ebp+arg_0]
0x411197  test    eax, eax
0x411199  jz      short loc_4111D0
0x41119b  mov     edi, [eax]
0x41119d  cmp     edi, esi
0x41119f  jnz     short loc_4111A5
0x4111a1  mov     eax, esi
0x4111a3  jmp     short loc_4111D2
0x4111a5  push    esi
0x4111a6  mov     [eax], esi
0x4111a8  call    ___acrt_add_locale_ref
0x4111ad  pop     ecx
0x4111ae  test    edi, edi
0x4111b0  jz      short loc_4111A1
0x4111b2  push    edi
0x4111b3  call    ___acrt_release_locale_ref
0x4111b8  cmp     dword ptr [edi+0Ch], 0
0x4111bc  pop     ecx
0x4111bd  jnz     short loc_4111A1
0x4111bf  cmp     edi, offset off_426580
0x4111c5  jz      short loc_4111A1
0x4111c7  push    edi; Block
0x4111c8  call    ___acrt_free_locale
0x4111cd  pop     ecx
0x4111ce  jmp     short loc_4111A1
0x4111d0  xor     eax, eax
0x4111d2  pop     edi
0x4111d3  pop     esi
0x4111d4  pop     ebp
0x4111d5  retn
```
