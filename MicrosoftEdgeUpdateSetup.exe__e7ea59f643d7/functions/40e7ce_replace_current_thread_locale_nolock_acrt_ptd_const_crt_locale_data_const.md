# replace_current_thread_locale_nolock(__acrt_ptd * const,__crt_locale_data * const)

- ea: `0x40e7ce`
- end: `0x40e819`
- name: `?replace_current_thread_locale_nolock@@YAXQAU__acrt_ptd@@QAU__crt_locale_data@@@Z`
- size: `75`
- prototype: `void __cdecl(struct __acrt_ptd *const, struct __crt_locale_data *const)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x40e58f`
- `0x40e5e4`

## callees

- `0x40e7ce`
- `0x410e3c`
- `0x410eb9`
- `0x411084`

## pseudocode

```c
void __cdecl replace_current_thread_locale_nolock(struct __acrt_ptd *const a1, struct __crt_locale_data *const a2)
{
  int v2; // eax

  if ( *((_DWORD *)a1 + 19) )
  {
    __acrt_release_locale_ref(*((_DWORD *)a1 + 19));
    v2 = *((_DWORD *)a1 + 19);
    if ( (struct __crt_locale_data *)v2 != dword_42721C && (wchar_t **)v2 != &off_426580 && !*(_DWORD *)(v2 + 12) )
      __acrt_free_locale(*((void **)a1 + 19));
  }
  *((_DWORD *)a1 + 19) = a2;
  if ( a2 )
    __acrt_add_locale_ref(a2);
}

```

## disassembly

```asm
0x40e7ce  mov     edi, edi
0x40e7d0  push    ebp
0x40e7d1  mov     ebp, esp
0x40e7d3  push    esi
0x40e7d4  mov     esi, [ebp+arg_0]
0x40e7d7  cmp     dword ptr [esi+4Ch], 0
0x40e7db  jz      short loc_40E805
0x40e7dd  push    dword ptr [esi+4Ch]
0x40e7e0  call    ___acrt_release_locale_ref
0x40e7e5  mov     eax, [esi+4Ch]
0x40e7e8  pop     ecx
0x40e7e9  cmp     eax, dword_42721C
0x40e7ef  jz      short loc_40E805
0x40e7f1  cmp     eax, offset off_426580
0x40e7f6  jz      short loc_40E805
0x40e7f8  cmp     dword ptr [eax+0Ch], 0
0x40e7fc  jnz     short loc_40E805
0x40e7fe  push    eax; Block
0x40e7ff  call    ___acrt_free_locale
0x40e804  pop     ecx
0x40e805  mov     eax, [ebp+arg_4]
0x40e808  mov     [esi+4Ch], eax
0x40e80b  pop     esi
0x40e80c  test    eax, eax
0x40e80e  jz      short loc_40E817
0x40e810  push    eax
0x40e811  call    ___acrt_add_locale_ref
0x40e816  pop     ecx
0x40e817  pop     ebp
0x40e818  retn
```
