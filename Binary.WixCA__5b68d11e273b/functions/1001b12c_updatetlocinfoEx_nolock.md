# __updatetlocinfoEx_nolock

- ea: `0x1001b12c`
- end: `0x1001b17c`
- name: `__updatetlocinfoEx_nolock`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x100174c9`
- `0x1001b0b5`

## callees

- `0x1001adea`
- `0x1001ae67`
- `0x1001b034`
- `0x1001b12c`

## pseudocode

```c
unsigned __int16 **__cdecl _updatetlocinfoEx_nolock(unsigned __int16 ***a1, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // edi

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
      if ( !v2[3] && v2 != &Locale_pctype_array )
        __acrt_free_locale(v2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1001b12c  mov     edi, edi
0x1001b12e  push    ebp
0x1001b12f  mov     ebp, esp
0x1001b131  push    esi
0x1001b132  mov     esi, [ebp+arg_4]
0x1001b135  push    edi
0x1001b136  test    esi, esi
0x1001b138  jz      short loc_1001B176
0x1001b13a  mov     eax, [ebp+arg_0]
0x1001b13d  test    eax, eax
0x1001b13f  jz      short loc_1001B176
0x1001b141  mov     edi, [eax]
0x1001b143  cmp     edi, esi
0x1001b145  jnz     short loc_1001B14B
0x1001b147  mov     eax, esi
0x1001b149  jmp     short loc_1001B178
0x1001b14b  push    esi
0x1001b14c  mov     [eax], esi
0x1001b14e  call    ___acrt_add_locale_ref
0x1001b153  pop     ecx
0x1001b154  test    edi, edi
0x1001b156  jz      short loc_1001B147
0x1001b158  push    edi
0x1001b159  call    ___acrt_release_locale_ref
0x1001b15e  cmp     dword ptr [edi+0Ch], 0
0x1001b162  pop     ecx
0x1001b163  jnz     short loc_1001B147
0x1001b165  cmp     edi, offset Locale_pctype_array
0x1001b16b  jz      short loc_1001B147
0x1001b16d  push    edi; Block
0x1001b16e  call    ___acrt_free_locale
0x1001b173  pop     ecx
0x1001b174  jmp     short loc_1001B147
0x1001b176  xor     eax, eax
0x1001b178  pop     edi
0x1001b179  pop     esi
0x1001b17a  pop     ebp
0x1001b17b  retn
```
