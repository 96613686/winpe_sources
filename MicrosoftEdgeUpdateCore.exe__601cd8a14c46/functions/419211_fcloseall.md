# __fcloseall

- ea: `0x419211`
- end: `0x4192bc`
- name: `__fcloseall`
- size: `171`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x415be0`

## callees

- `0x40dc70`
- `0x4136b2`
- `0x413d81`
- `0x413dd1`
- `0x419211`
- `0x41b301`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x419274`
- `KERNEL32!DeleteCriticalSection` at `0x419274`

## pseudocode

```c
int __cdecl _fcloseall()
{
  int i; // esi
  int v1; // eax
  int v3; // [esp+14h] [ebp-1Ch]

  v3 = 0;
  __acrt_lock(8);
  for ( i = 3; i != Count; ++i )
  {
    v1 = *((_DWORD *)dword_43E7A8 + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 12) & 0x2000) != 0 && fclose(*((FILE **)dword_43E7A8 + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_DWORD *)dword_43E7A8 + i) + 32));
      _free_base(*((void **)dword_43E7A8 + i));
      *((_DWORD *)dword_43E7A8 + i) = 0;
    }
  }
  __acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x419211  push    10h
0x419213  push    offset stru_43B848
0x419218  call    __SEH_prolog4
0x41921d  and     [ebp+var_1C], 0
0x419221  push    8
0x419223  call    ___acrt_lock
0x419228  pop     ecx
0x419229  and     [ebp+ms_exc.registration.TryLevel], 0
0x41922d  push    3
0x41922f  pop     esi
0x419230  mov     [ebp+var_20], esi
0x419233  cmp     esi, Count
0x419239  jz      short loc_419294
0x41923b  mov     eax, dword_43E7A8
0x419240  mov     eax, [eax+esi*4]
0x419243  test    eax, eax
0x419245  jz      short loc_419291
0x419247  mov     eax, [eax+0Ch]
0x41924a  nop
0x41924b  shr     eax, 0Dh
0x41924e  test    al, 1
0x419250  jz      short loc_419268
0x419252  mov     eax, dword_43E7A8
0x419257  push    dword ptr [eax+esi*4]; Stream
0x41925a  call    _fclose
0x41925f  pop     ecx
0x419260  cmp     eax, 0FFFFFFFFh
0x419263  jz      short loc_419268
0x419265  inc     [ebp+var_1C]
0x419268  mov     eax, dword_43E7A8
0x41926d  mov     eax, [eax+esi*4]
0x419270  add     eax, 20h ; ' '
0x419273  push    eax; lpCriticalSection
0x419274  call    ds:DeleteCriticalSection
0x41927a  mov     eax, dword_43E7A8
0x41927f  push    dword ptr [eax+esi*4]; Block
0x419282  call    __free_base
0x419287  pop     ecx
0x419288  mov     eax, dword_43E7A8
0x41928d  and     dword ptr [eax+esi*4], 0
0x419291  inc     esi
0x419292  jmp     short loc_419230
0x419294  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x41929b  call    loc_4192B3
0x4192a0  mov     eax, [ebp+var_1C]
0x4192a3  mov     ecx, [ebp+ms_exc.registration.Next]
0x4192a6  mov     large fs:0, ecx
0x4192ad  pop     ecx
0x4192ae  pop     edi
0x4192af  pop     esi
0x4192b0  pop     ebx
0x4192b1  leave
0x4192b2  retn
0x4192b3  push    8
0x4192b5  call    ___acrt_unlock
0x4192ba  pop     ecx
0x4192bb  retn
```
