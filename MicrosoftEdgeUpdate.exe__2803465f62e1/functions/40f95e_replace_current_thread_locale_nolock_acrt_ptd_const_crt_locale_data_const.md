# replace_current_thread_locale_nolock(__acrt_ptd * const,__crt_locale_data * const)

- ea: `0x40f95e`
- end: `0x40f9a9`
- name: `?replace_current_thread_locale_nolock@@YAXQAU__acrt_ptd@@QAU__crt_locale_data@@@Z`
- size: `75`
- prototype: `void __cdecl(struct __acrt_ptd *const, struct __crt_locale_data *const)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x40f71d`
- `0x40f772`

## callees

- `0x40f95e`
- `0x411810`
- `0x41188d`
- `0x411a58`

## pseudocode

```c
void __cdecl replace_current_thread_locale_nolock(struct __acrt_ptd *const a1, struct __crt_locale_data *const a2)
{
  int v2; // eax

  if ( *((_DWORD *)a1 + 19) )
  {
    __acrt_release_locale_ref(*((_DWORD *)a1 + 19));
    v2 = *((_DWORD *)a1 + 19);
    if ( (struct __crt_locale_data *)v2 != dword_418020 && (wchar_t **)v2 != &off_417058 && !*(_DWORD *)(v2 + 12) )
      __acrt_free_locale(*((void **)a1 + 19));
  }
  *((_DWORD *)a1 + 19) = a2;
  if ( a2 )
    __acrt_add_locale_ref(a2);
}

```

## disassembly

```asm
0x40f95e  mov     edi, edi
0x40f960  push    ebp
0x40f961  mov     ebp, esp
0x40f963  push    esi
0x40f964  mov     esi, [ebp+arg_0]
0x40f967  cmp     dword ptr [esi+4Ch], 0
0x40f96b  jz      short loc_40F995
0x40f96d  push    dword ptr [esi+4Ch]
0x40f970  call    ___acrt_release_locale_ref
0x40f975  mov     eax, [esi+4Ch]
0x40f978  pop     ecx
0x40f979  cmp     eax, dword_418020
0x40f97f  jz      short loc_40F995
0x40f981  cmp     eax, offset off_417058
0x40f986  jz      short loc_40F995
0x40f988  cmp     dword ptr [eax+0Ch], 0
0x40f98c  jnz     short loc_40F995
0x40f98e  push    eax; Block
0x40f98f  call    ___acrt_free_locale
0x40f994  pop     ecx
0x40f995  mov     eax, [ebp+arg_4]
0x40f998  mov     [esi+4Ch], eax
0x40f99b  pop     esi
0x40f99c  test    eax, eax
0x40f99e  jz      short loc_40F9A7
0x40f9a0  push    eax
0x40f9a1  call    ___acrt_add_locale_ref
0x40f9a6  pop     ecx
0x40f9a7  pop     ebp
0x40f9a8  retn
```
