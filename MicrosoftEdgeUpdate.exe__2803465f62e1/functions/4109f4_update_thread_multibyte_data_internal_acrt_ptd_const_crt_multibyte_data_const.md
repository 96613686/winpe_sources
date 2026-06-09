# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x4109f4`
- end: `0x410a93`
- name: `?update_thread_multibyte_data_internal@@YAPAU__crt_multibyte_data@@QAU__acrt_ptd@@QAPAU1@@Z`
- size: `159`
- prototype: `struct __crt_multibyte_data *__cdecl(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x4108e0`
- `0x410ae8`

## callees

- `0x40bfc0`
- `0x40f51a`
- `0x40fd41`
- `0x40fd91`
- `0x41001a`
- `0x4109f4`

## pseudocode

```c
struct __crt_multibyte_data *__cdecl update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  struct __crt_multibyte_data *v2; // esi

  if ( (dword_4176A0 & *((_DWORD *)a1 + 212)) != 0 && *((_DWORD *)a1 + 19) )
  {
    v2 = (struct __crt_multibyte_data *)*((_DWORD *)a1 + 18);
  }
  else
  {
    __acrt_lock(5);
    v2 = (struct __crt_multibyte_data *)*((_DWORD *)a1 + 18);
    if ( v2 != *a2 )
    {
      if ( v2
        && !_InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF)
        && v2 != (struct __crt_multibyte_data *)dword_417128 )
      {
        _free_base(v2);
      }
      v2 = *a2;
      *((_DWORD *)a1 + 18) = *a2;
      _InterlockedIncrement((volatile signed __int32 *)v2);
    }
    __acrt_unlock(5);
  }
  if ( !v2 )
    abort();
  return v2;
}

```

## disassembly

```asm
0x4109f4  push    0Ch
0x4109f6  push    offset stru_416AC8
0x4109fb  call    __SEH_prolog4
0x410a00  xor     esi, esi
0x410a02  mov     [ebp+var_1C], esi
0x410a05  mov     edi, [ebp+arg_0]
0x410a08  mov     eax, dword_4176A0
0x410a0d  test    [edi+350h], eax
0x410a13  jz      short loc_410A23
0x410a15  cmp     [edi+4Ch], esi
0x410a18  jz      short loc_410A23
0x410a1a  mov     esi, [edi+48h]
0x410a1d  test    esi, esi
0x410a1f  jz      short loc_410A8E
0x410a21  jmp     short loc_410A7C
0x410a23  push    5
0x410a25  call    ___acrt_lock
0x410a2a  pop     ecx
0x410a2b  mov     [ebp+ms_exc.registration.TryLevel], esi
0x410a2e  mov     esi, [edi+48h]
0x410a31  mov     [ebp+var_1C], esi
0x410a34  mov     ebx, [ebp+arg_4]
0x410a37  cmp     esi, [ebx]
0x410a39  jz      short loc_410A62
0x410a3b  test    esi, esi
0x410a3d  jz      short loc_410A57
0x410a3f  or      eax, 0FFFFFFFFh
0x410a42  lock xadd [esi], eax
0x410a46  jnz     short loc_410A57
0x410a48  cmp     esi, offset dword_417128
0x410a4e  jz      short loc_410A57
0x410a50  push    esi; Block
0x410a51  call    __free_base
0x410a56  pop     ecx
0x410a57  mov     esi, [ebx]
0x410a59  mov     [edi+48h], esi
0x410a5c  mov     [ebp+var_1C], esi
0x410a5f  lock inc dword ptr [esi]
0x410a62  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x410a69  call    loc_410A73
0x410a6e  jmp     short loc_410A1D
0x410a70  mov     esi, [ebp+var_1C]
0x410a73  push    5
0x410a75  call    ___acrt_unlock
0x410a7a  pop     ecx
0x410a7b  retn
0x410a7c  mov     eax, esi
0x410a7e  mov     ecx, [ebp+ms_exc.registration.Next]
0x410a81  mov     large fs:0, ecx
0x410a88  pop     ecx
0x410a89  pop     edi
0x410a8a  pop     esi
0x410a8b  pop     ebx
0x410a8c  leave
0x410a8d  retn
0x410a8e  call    _abort
```
