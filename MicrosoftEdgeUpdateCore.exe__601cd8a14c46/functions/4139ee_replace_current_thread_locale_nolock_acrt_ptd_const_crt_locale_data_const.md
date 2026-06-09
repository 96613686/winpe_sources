# replace_current_thread_locale_nolock(__acrt_ptd * const,__crt_locale_data * const)

- ea: `0x4139ee`
- end: `0x413a39`
- name: `?replace_current_thread_locale_nolock@@YAXQAU__acrt_ptd@@QAU__crt_locale_data@@@Z`
- size: `75`
- prototype: `void __cdecl(struct __acrt_ptd *const, struct __crt_locale_data *const)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x4137a9`
- `0x4137fe`

## callees

- `0x4139ee`
- `0x416838`
- `0x4168b5`
- `0x416a80`

## pseudocode

```c
void __cdecl replace_current_thread_locale_nolock(struct __acrt_ptd *const a1, struct __crt_locale_data *const a2)
{
  int v2; // eax

  if ( *((_DWORD *)a1 + 19) )
  {
    __acrt_release_locale_ref(*((_DWORD *)a1 + 19));
    v2 = *((_DWORD *)a1 + 19);
    if ( (struct __crt_locale_data *)v2 != dword_43E7A0 && (wchar_t **)v2 != &off_43D588 && !*(_DWORD *)(v2 + 12) )
      __acrt_free_locale(*((void **)a1 + 19));
  }
  *((_DWORD *)a1 + 19) = a2;
  if ( a2 )
    __acrt_add_locale_ref(a2);
}

```

## disassembly

```asm
0x4139ee  mov     edi, edi
0x4139f0  push    ebp
0x4139f1  mov     ebp, esp
0x4139f3  push    esi
0x4139f4  mov     esi, [ebp+arg_0]
0x4139f7  cmp     dword ptr [esi+4Ch], 0
0x4139fb  jz      short loc_413A25
0x4139fd  push    dword ptr [esi+4Ch]
0x413a00  call    ___acrt_release_locale_ref
0x413a05  mov     eax, [esi+4Ch]
0x413a08  pop     ecx
0x413a09  cmp     eax, dword_43E7A0
0x413a0f  jz      short loc_413A25
0x413a11  cmp     eax, offset off_43D588
0x413a16  jz      short loc_413A25
0x413a18  cmp     dword ptr [eax+0Ch], 0
0x413a1c  jnz     short loc_413A25
0x413a1e  push    eax; Block
0x413a1f  call    ___acrt_free_locale
0x413a24  pop     ecx
0x413a25  mov     eax, [ebp+arg_4]
0x413a28  mov     [esi+4Ch], eax
0x413a2b  pop     esi
0x413a2c  test    eax, eax
0x413a2e  jz      short loc_413A37
0x413a30  push    eax
0x413a31  call    ___acrt_add_locale_ref
0x413a36  pop     ecx
0x413a37  pop     ebp
0x413a38  retn
```
