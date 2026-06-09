# __updatetlocinfoEx_nolock

- ea: `0x416b82`
- end: `0x416bd2`
- name: `__updatetlocinfoEx_nolock`
- size: `80`
- prototype: `wchar_t **__cdecl(wchar_t ***, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x4114b1`
- `0x416b01`

## callees

- `0x416838`
- `0x4168b5`
- `0x416a80`
- `0x416b82`

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
      if ( !v2[3] && v2 != &off_43D588 )
        __acrt_free_locale(v2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x416b82  mov     edi, edi
0x416b84  push    ebp
0x416b85  mov     ebp, esp
0x416b87  push    esi
0x416b88  mov     esi, [ebp+arg_4]
0x416b8b  push    edi
0x416b8c  test    esi, esi
0x416b8e  jz      short loc_416BCC
0x416b90  mov     eax, [ebp+arg_0]
0x416b93  test    eax, eax
0x416b95  jz      short loc_416BCC
0x416b97  mov     edi, [eax]
0x416b99  cmp     edi, esi
0x416b9b  jnz     short loc_416BA1
0x416b9d  mov     eax, esi
0x416b9f  jmp     short loc_416BCE
0x416ba1  push    esi
0x416ba2  mov     [eax], esi
0x416ba4  call    ___acrt_add_locale_ref
0x416ba9  pop     ecx
0x416baa  test    edi, edi
0x416bac  jz      short loc_416B9D
0x416bae  push    edi
0x416baf  call    ___acrt_release_locale_ref
0x416bb4  cmp     dword ptr [edi+0Ch], 0
0x416bb8  pop     ecx
0x416bb9  jnz     short loc_416B9D
0x416bbb  cmp     edi, offset off_43D588
0x416bc1  jz      short loc_416B9D
0x416bc3  push    edi; Block
0x416bc4  call    ___acrt_free_locale
0x416bc9  pop     ecx
0x416bca  jmp     short loc_416B9D
0x416bcc  xor     eax, eax
0x416bce  pop     edi
0x416bcf  pop     esi
0x416bd0  pop     ebp
0x416bd1  retn
```
