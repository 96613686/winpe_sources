# ___acrt_update_thread_locale_data

- ea: `0x411ad9`
- end: `0x411b5a`
- name: `___acrt_update_thread_locale_data`
- size: `129`
- prototype: `int()`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x40fc0a`

## callees

- `0x40bfc0`
- `0x40f51a`
- `0x40f9a9`
- `0x40fd41`
- `0x40fd91`
- `0x411ad9`
- `0x411b5a`

## pseudocode

```c
int __acrt_update_thread_locale_data()
{
  _DWORD *v0; // eax
  int *v1; // edi
  int v2; // esi

  v0 = __acrt_getptd();
  v1 = v0 + 19;
  if ( (dword_4176A0 & v0[212]) == 0 || (v2 = *v1) == 0 )
  {
    __acrt_lock(4);
    v2 = _updatetlocinfoEx_nolock(v1, dword_418020);
    __acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x411ad9  push    0Ch
0x411adb  push    offset stru_416B48
0x411ae0  call    __SEH_prolog4
0x411ae5  and     [ebp+var_1C], 0
0x411ae9  call    ___acrt_getptd
0x411aee  lea     edi, [eax+4Ch]
0x411af1  mov     ecx, dword_4176A0
0x411af7  test    [eax+350h], ecx
0x411afd  jz      short loc_411B05
0x411aff  mov     esi, [edi]
0x411b01  test    esi, esi
0x411b03  jnz     short loc_411B42
0x411b05  push    4
0x411b07  call    ___acrt_lock
0x411b0c  pop     ecx
0x411b0d  and     [ebp+ms_exc.registration.TryLevel], 0
0x411b11  push    dword_418020
0x411b17  push    edi
0x411b18  call    __updatetlocinfoEx_nolock
0x411b1d  pop     ecx
0x411b1e  pop     ecx
0x411b1f  mov     esi, eax
0x411b21  mov     [ebp+var_1C], esi
0x411b24  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x411b2b  call    loc_411B39
0x411b30  test    esi, esi
0x411b32  jz      short loc_411B54
0x411b34  jmp     short loc_411B42
0x411b36  mov     esi, [ebp+var_1C]
0x411b39  push    4
0x411b3b  call    ___acrt_unlock
0x411b40  pop     ecx
0x411b41  retn
0x411b42  mov     eax, esi
0x411b44  mov     ecx, [ebp+ms_exc.registration.Next]
0x411b47  mov     large fs:0, ecx
0x411b4e  pop     ecx
0x411b4f  pop     edi
0x411b50  pop     esi
0x411b51  pop     ebx
0x411b52  leave
0x411b53  retn
0x411b54  call    _abort
```
