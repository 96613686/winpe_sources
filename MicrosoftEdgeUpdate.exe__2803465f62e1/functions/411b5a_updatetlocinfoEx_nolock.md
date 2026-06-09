# __updatetlocinfoEx_nolock

- ea: `0x411b5a`
- end: `0x411baa`
- name: `__updatetlocinfoEx_nolock`
- size: `80`
- prototype: `wchar_t **__cdecl(wchar_t ***, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x40ede6`
- `0x411ad9`

## callees

- `0x411810`
- `0x41188d`
- `0x411a58`
- `0x411b5a`

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
      if ( !v2[3] && v2 != &off_417058 )
        __acrt_free_locale(v2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x411b5a  mov     edi, edi
0x411b5c  push    ebp
0x411b5d  mov     ebp, esp
0x411b5f  push    esi
0x411b60  mov     esi, [ebp+arg_4]
0x411b63  push    edi
0x411b64  test    esi, esi
0x411b66  jz      short loc_411BA4
0x411b68  mov     eax, [ebp+arg_0]
0x411b6b  test    eax, eax
0x411b6d  jz      short loc_411BA4
0x411b6f  mov     edi, [eax]
0x411b71  cmp     edi, esi
0x411b73  jnz     short loc_411B79
0x411b75  mov     eax, esi
0x411b77  jmp     short loc_411BA6
0x411b79  push    esi
0x411b7a  mov     [eax], esi
0x411b7c  call    ___acrt_add_locale_ref
0x411b81  pop     ecx
0x411b82  test    edi, edi
0x411b84  jz      short loc_411B75
0x411b86  push    edi
0x411b87  call    ___acrt_release_locale_ref
0x411b8c  cmp     dword ptr [edi+0Ch], 0
0x411b90  pop     ecx
0x411b91  jnz     short loc_411B75
0x411b93  cmp     edi, offset off_417058
0x411b99  jz      short loc_411B75
0x411b9b  push    edi; Block
0x411b9c  call    ___acrt_free_locale
0x411ba1  pop     ecx
0x411ba2  jmp     short loc_411B75
0x411ba4  xor     eax, eax
0x411ba6  pop     edi
0x411ba7  pop     esi
0x411ba8  pop     ebp
0x411ba9  retn
```
