# ___acrt_update_thread_locale_data

- ea: `0x411105`
- end: `0x411186`
- name: `___acrt_update_thread_locale_data`
- size: `129`
- prototype: `int()`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x4125c3`

## callees

- `0x4089e0`
- `0x40c30b`
- `0x40e819`
- `0x410211`
- `0x410261`
- `0x411105`
- `0x411186`

## pseudocode

```c
int __acrt_update_thread_locale_data()
{
  _DWORD *v0; // eax
  int *v1; // edi
  int v2; // esi

  v0 = __acrt_getptd();
  v1 = v0 + 19;
  if ( (dword_4266A0 & v0[212]) == 0 || (v2 = *v1) == 0 )
  {
    __acrt_lock(4);
    v2 = _updatetlocinfoEx_nolock(v1, dword_42721C);
    __acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x411105  push    0Ch
0x411107  push    offset stru_424280
0x41110c  call    __SEH_prolog4
0x411111  and     [ebp+var_1C], 0
0x411115  call    ___acrt_getptd
0x41111a  lea     edi, [eax+4Ch]
0x41111d  mov     ecx, dword_4266A0
0x411123  test    [eax+350h], ecx
0x411129  jz      short loc_411131
0x41112b  mov     esi, [edi]
0x41112d  test    esi, esi
0x41112f  jnz     short loc_41116E
0x411131  push    4
0x411133  call    ___acrt_lock
0x411138  pop     ecx
0x411139  and     [ebp+ms_exc.registration.TryLevel], 0
0x41113d  push    dword_42721C
0x411143  push    edi
0x411144  call    __updatetlocinfoEx_nolock
0x411149  pop     ecx
0x41114a  pop     ecx
0x41114b  mov     esi, eax
0x41114d  mov     [ebp+var_1C], esi
0x411150  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x411157  call    loc_411165
0x41115c  test    esi, esi
0x41115e  jz      short loc_411180
0x411160  jmp     short loc_41116E
0x411162  mov     esi, [ebp+var_1C]
0x411165  push    4
0x411167  call    ___acrt_unlock
0x41116c  pop     ecx
0x41116d  retn
0x41116e  mov     eax, esi
0x411170  mov     ecx, [ebp+ms_exc.registration.Next]
0x411173  mov     large fs:0, ecx
0x41117a  pop     ecx
0x41117b  pop     edi
0x41117c  pop     esi
0x41117d  pop     ebx
0x41117e  leave
0x41117f  retn
0x411180  call    _abort
```
