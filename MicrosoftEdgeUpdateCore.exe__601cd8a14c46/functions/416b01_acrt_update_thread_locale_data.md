# ___acrt_update_thread_locale_data

- ea: `0x416b01`
- end: `0x416b82`
- name: `___acrt_update_thread_locale_data`
- size: `129`
- prototype: `int()`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x417297`

## callees

- `0x40dc70`
- `0x4116b0`
- `0x413a39`
- `0x413d81`
- `0x413dd1`
- `0x416b01`
- `0x416b82`

## pseudocode

```c
int __acrt_update_thread_locale_data()
{
  _DWORD *v0; // eax
  int *v1; // edi
  int v2; // esi

  v0 = __acrt_getptd();
  v1 = v0 + 19;
  if ( (dword_43D758 & v0[212]) == 0 || (v2 = *v1) == 0 )
  {
    __acrt_lock(4);
    v2 = _updatetlocinfoEx_nolock(v1, dword_43E7A0);
    __acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x416b01  push    0Ch
0x416b03  push    offset stru_43B7E8
0x416b08  call    __SEH_prolog4
0x416b0d  and     [ebp+var_1C], 0
0x416b11  call    ___acrt_getptd
0x416b16  lea     edi, [eax+4Ch]
0x416b19  mov     ecx, dword_43D758
0x416b1f  test    [eax+350h], ecx
0x416b25  jz      short loc_416B2D
0x416b27  mov     esi, [edi]
0x416b29  test    esi, esi
0x416b2b  jnz     short loc_416B6A
0x416b2d  push    4
0x416b2f  call    ___acrt_lock
0x416b34  pop     ecx
0x416b35  and     [ebp+ms_exc.registration.TryLevel], 0
0x416b39  push    dword_43E7A0
0x416b3f  push    edi
0x416b40  call    __updatetlocinfoEx_nolock
0x416b45  pop     ecx
0x416b46  pop     ecx
0x416b47  mov     esi, eax
0x416b49  mov     [ebp+var_1C], esi
0x416b4c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x416b53  call    loc_416B61
0x416b58  test    esi, esi
0x416b5a  jz      short loc_416B7C
0x416b5c  jmp     short loc_416B6A
0x416b5e  mov     esi, [ebp+var_1C]
0x416b61  push    4
0x416b63  call    ___acrt_unlock
0x416b68  pop     ecx
0x416b69  retn
0x416b6a  mov     eax, esi
0x416b6c  mov     ecx, [ebp+ms_exc.registration.Next]
0x416b6f  mov     large fs:0, ecx
0x416b76  pop     ecx
0x416b77  pop     edi
0x416b78  pop     esi
0x416b79  pop     ebx
0x416b7a  leave
0x416b7b  retn
0x416b7c  call    _abort
```
