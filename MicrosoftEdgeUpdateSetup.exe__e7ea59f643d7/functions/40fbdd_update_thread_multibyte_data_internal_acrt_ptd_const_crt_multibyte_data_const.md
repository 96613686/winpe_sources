# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x40fbdd`
- end: `0x40fc7c`
- name: `?update_thread_multibyte_data_internal@@YAPAU__crt_multibyte_data@@QAU__acrt_ptd@@QAPAU1@@Z`
- size: `159`
- prototype: `struct __crt_multibyte_data *__cdecl(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x40fac9`
- `0x40fcc8`

## callees

- `0x4089e0`
- `0x40c30b`
- `0x40ed53`
- `0x40fbdd`
- `0x410211`
- `0x410261`

## pseudocode

```c
struct __crt_multibyte_data *__cdecl update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  struct __crt_multibyte_data *v2; // esi

  if ( (dword_4266A0 & *((_DWORD *)a1 + 212)) != 0 && *((_DWORD *)a1 + 19) )
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
        && v2 != (struct __crt_multibyte_data *)dword_426060 )
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
0x40fbdd  push    0Ch
0x40fbdf  push    offset stru_424200
0x40fbe4  call    __SEH_prolog4
0x40fbe9  xor     esi, esi
0x40fbeb  mov     [ebp+var_1C], esi
0x40fbee  mov     edi, [ebp+arg_0]
0x40fbf1  mov     eax, dword_4266A0
0x40fbf6  test    [edi+350h], eax
0x40fbfc  jz      short loc_40FC0C
0x40fbfe  cmp     [edi+4Ch], esi
0x40fc01  jz      short loc_40FC0C
0x40fc03  mov     esi, [edi+48h]
0x40fc06  test    esi, esi
0x40fc08  jz      short loc_40FC77
0x40fc0a  jmp     short loc_40FC65
0x40fc0c  push    5
0x40fc0e  call    ___acrt_lock
0x40fc13  pop     ecx
0x40fc14  mov     [ebp+ms_exc.registration.TryLevel], esi
0x40fc17  mov     esi, [edi+48h]
0x40fc1a  mov     [ebp+var_1C], esi
0x40fc1d  mov     ebx, [ebp+arg_4]
0x40fc20  cmp     esi, [ebx]
0x40fc22  jz      short loc_40FC4B
0x40fc24  test    esi, esi
0x40fc26  jz      short loc_40FC40
0x40fc28  or      eax, 0FFFFFFFFh
0x40fc2b  lock xadd [esi], eax
0x40fc2f  jnz     short loc_40FC40
0x40fc31  cmp     esi, offset dword_426060
0x40fc37  jz      short loc_40FC40
0x40fc39  push    esi; Block
0x40fc3a  call    __free_base
0x40fc3f  pop     ecx
0x40fc40  mov     esi, [ebx]
0x40fc42  mov     [edi+48h], esi
0x40fc45  mov     [ebp+var_1C], esi
0x40fc48  lock inc dword ptr [esi]
0x40fc4b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x40fc52  call    loc_40FC5C
0x40fc57  jmp     short loc_40FC06
0x40fc59  mov     esi, [ebp+var_1C]
0x40fc5c  push    5
0x40fc5e  call    ___acrt_unlock
0x40fc63  pop     ecx
0x40fc64  retn
0x40fc65  mov     eax, esi
0x40fc67  mov     ecx, [ebp+ms_exc.registration.Next]
0x40fc6a  mov     large fs:0, ecx
0x40fc71  pop     ecx
0x40fc72  pop     edi
0x40fc73  pop     esi
0x40fc74  pop     ebx
0x40fc75  leave
0x40fc76  retn
0x40fc77  call    _abort
```
