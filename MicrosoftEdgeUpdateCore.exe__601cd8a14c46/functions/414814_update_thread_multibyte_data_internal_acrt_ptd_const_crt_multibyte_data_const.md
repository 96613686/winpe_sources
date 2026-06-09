# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x414814`
- end: `0x4148b3`
- name: `?update_thread_multibyte_data_internal@@YAPAU__crt_multibyte_data@@QAU__acrt_ptd@@QAPAU1@@Z`
- size: `159`
- prototype: `struct __crt_multibyte_data *__cdecl(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x414700`
- `0x414908`

## callees

- `0x40dc70`
- `0x4116b0`
- `0x4136b2`
- `0x413d81`
- `0x413dd1`
- `0x414814`

## pseudocode

```c
struct __crt_multibyte_data *__cdecl update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  struct __crt_multibyte_data *v2; // esi

  if ( (dword_43D758 & *((_DWORD *)a1 + 212)) != 0 && *((_DWORD *)a1 + 19) )
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
        && v2 != (struct __crt_multibyte_data *)dword_43D068 )
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
0x414814  push    0Ch
0x414816  push    offset stru_43B6C8
0x41481b  call    __SEH_prolog4
0x414820  xor     esi, esi
0x414822  mov     [ebp+var_1C], esi
0x414825  mov     edi, [ebp+arg_0]
0x414828  mov     eax, dword_43D758
0x41482d  test    [edi+350h], eax
0x414833  jz      short loc_414843
0x414835  cmp     [edi+4Ch], esi
0x414838  jz      short loc_414843
0x41483a  mov     esi, [edi+48h]
0x41483d  test    esi, esi
0x41483f  jz      short loc_4148AE
0x414841  jmp     short loc_41489C
0x414843  push    5
0x414845  call    ___acrt_lock
0x41484a  pop     ecx
0x41484b  mov     [ebp+ms_exc.registration.TryLevel], esi
0x41484e  mov     esi, [edi+48h]
0x414851  mov     [ebp+var_1C], esi
0x414854  mov     ebx, [ebp+arg_4]
0x414857  cmp     esi, [ebx]
0x414859  jz      short loc_414882
0x41485b  test    esi, esi
0x41485d  jz      short loc_414877
0x41485f  or      eax, 0FFFFFFFFh
0x414862  lock xadd [esi], eax
0x414866  jnz     short loc_414877
0x414868  cmp     esi, offset dword_43D068
0x41486e  jz      short loc_414877
0x414870  push    esi; Block
0x414871  call    __free_base
0x414876  pop     ecx
0x414877  mov     esi, [ebx]
0x414879  mov     [edi+48h], esi
0x41487c  mov     [ebp+var_1C], esi
0x41487f  lock inc dword ptr [esi]
0x414882  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x414889  call    loc_414893
0x41488e  jmp     short loc_41483D
0x414890  mov     esi, [ebp+var_1C]
0x414893  push    5
0x414895  call    ___acrt_unlock
0x41489a  pop     ecx
0x41489b  retn
0x41489c  mov     eax, esi
0x41489e  mov     ecx, [ebp+ms_exc.registration.Next]
0x4148a1  mov     large fs:0, ecx
0x4148a8  pop     ecx
0x4148a9  pop     edi
0x4148aa  pop     esi
0x4148ab  pop     ebx
0x4148ac  leave
0x4148ad  retn
0x4148ae  call    _abort
```
