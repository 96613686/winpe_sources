# ___acrt_update_thread_locale_data

- ea: `0x1001b0b5`
- end: `0x1001b12c`
- name: `___acrt_update_thread_locale_data`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1001746f`

## callees

- `0x10011180`
- `0x100111c6`
- `0x10016ce8`
- `0x1001721d`
- `0x10018c0a`
- `0x10018c52`
- `0x1001b0b5`
- `0x1001b12c`

## pseudocode

```c
int __acrt_update_thread_locale_data()
{
  int v0; // eax
  int *v1; // edi
  int v2; // esi

  v0 = __acrt_getptd();
  v1 = (int *)(v0 + 76);
  if ( (dword_10033740 & *(_DWORD *)(v0 + 848)) == 0 || (v2 = *v1) == 0 )
  {
    __acrt_lock(4);
    v2 = _updatetlocinfoEx_nolock(v1, dword_10034F0C);
    __acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x1001b0b5  push    0Ch
0x1001b0b7  push    offset stru_10031200
0x1001b0bc  call    __SEH_prolog4
0x1001b0c1  and     [ebp+var_1C], 0
0x1001b0c5  call    ___acrt_getptd
0x1001b0ca  lea     edi, [eax+4Ch]
0x1001b0cd  mov     ecx, dword_10033740
0x1001b0d3  test    [eax+350h], ecx
0x1001b0d9  jz      short loc_1001B0E1
0x1001b0db  mov     esi, [edi]
0x1001b0dd  test    esi, esi
0x1001b0df  jnz     short loc_1001B11E
0x1001b0e1  push    4
0x1001b0e3  call    ___acrt_lock
0x1001b0e8  pop     ecx
0x1001b0e9  and     [ebp+ms_exc.registration.TryLevel], 0
0x1001b0ed  push    dword_10034F0C
0x1001b0f3  push    edi
0x1001b0f4  call    __updatetlocinfoEx_nolock
0x1001b0f9  pop     ecx
0x1001b0fa  pop     ecx
0x1001b0fb  mov     esi, eax
0x1001b0fd  mov     [ebp+var_1C], esi
0x1001b100  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1001b107  call    loc_1001B115
0x1001b10c  test    esi, esi
0x1001b10e  jz      short loc_1001B126
0x1001b110  jmp     short loc_1001B11E
0x1001b112  mov     esi, [ebp+var_1C]
0x1001b115  push    4
0x1001b117  call    ___acrt_unlock
0x1001b11c  pop     ecx
0x1001b11d  retn
0x1001b11e  mov     eax, esi
0x1001b120  call    __SEH_epilog4
0x1001b125  retn
0x1001b126  call    _abort
```
