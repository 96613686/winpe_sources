# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x10019b54`
- end: `0x10019bea`
- name: `?update_thread_multibyte_data_internal@@YAPAU__crt_multibyte_data@@QAU__acrt_ptd@@QAPAU1@@Z`
- size: `150`
- prototype: `struct __crt_multibyte_data *__cdecl(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x10019a39`
- `0x10019c32`

## callees

- `0x10011180`
- `0x100111c6`
- `0x10016ce8`
- `0x1001770e`
- `0x10018c0a`
- `0x10018c52`
- `0x10019b54`

## pseudocode

```c
struct __crt_multibyte_data *__cdecl update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  struct __crt_multibyte_data *v2; // esi

  if ( (dword_10033740 & *((_DWORD *)a1 + 212)) != 0 && *((_DWORD *)a1 + 19) )
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
        && v2 != (struct __crt_multibyte_data *)dword_10033220 )
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
0x10019b54  push    0Ch
0x10019b56  push    offset stru_10031120
0x10019b5b  call    __SEH_prolog4
0x10019b60  xor     esi, esi
0x10019b62  mov     [ebp+var_1C], esi
0x10019b65  mov     edi, [ebp+arg_0]
0x10019b68  mov     eax, dword_10033740
0x10019b6d  test    [edi+350h], eax
0x10019b73  jz      short loc_10019B83
0x10019b75  cmp     [edi+4Ch], esi
0x10019b78  jz      short loc_10019B83
0x10019b7a  mov     esi, [edi+48h]
0x10019b7d  test    esi, esi
0x10019b7f  jz      short loc_10019BE4
0x10019b81  jmp     short loc_10019BDC
0x10019b83  push    5
0x10019b85  call    ___acrt_lock
0x10019b8a  pop     ecx
0x10019b8b  mov     [ebp+ms_exc.registration.TryLevel], esi
0x10019b8e  mov     esi, [edi+48h]
0x10019b91  mov     [ebp+var_1C], esi
0x10019b94  mov     ebx, [ebp+arg_4]
0x10019b97  cmp     esi, [ebx]
0x10019b99  jz      short loc_10019BC2
0x10019b9b  test    esi, esi
0x10019b9d  jz      short loc_10019BB7
0x10019b9f  or      eax, 0FFFFFFFFh
0x10019ba2  lock xadd [esi], eax
0x10019ba6  jnz     short loc_10019BB7
0x10019ba8  cmp     esi, offset dword_10033220
0x10019bae  jz      short loc_10019BB7
0x10019bb0  push    esi; Block
0x10019bb1  call    __free_base
0x10019bb6  pop     ecx
0x10019bb7  mov     esi, [ebx]
0x10019bb9  mov     [edi+48h], esi
0x10019bbc  mov     [ebp+var_1C], esi
0x10019bbf  lock inc dword ptr [esi]
0x10019bc2  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10019bc9  call    loc_10019BD3
0x10019bce  jmp     short loc_10019B7D
0x10019bd0  mov     esi, [ebp+var_1C]
0x10019bd3  push    5
0x10019bd5  call    ___acrt_unlock
0x10019bda  pop     ecx
0x10019bdb  retn
0x10019bdc  mov     eax, esi
0x10019bde  call    __SEH_epilog4
0x10019be3  retn
0x10019be4  call    _abort
```
