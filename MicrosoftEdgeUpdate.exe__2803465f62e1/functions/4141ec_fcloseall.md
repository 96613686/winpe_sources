# __fcloseall

- ea: `0x4141ec`
- end: `0x414297`
- name: `__fcloseall`
- size: `171`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x412750`

## callees

- `0x40bfc0`
- `0x40fd41`
- `0x40fd91`
- `0x41001a`
- `0x4141ec`
- `0x414733`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x41424f`
- `KERNEL32!DeleteCriticalSection` at `0x41424f`

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
    v1 = *((_DWORD *)dword_4184B0 + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 12) & 0x2000) != 0 && fclose(*((FILE **)dword_4184B0 + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_DWORD *)dword_4184B0 + i) + 32));
      _free_base(*((void **)dword_4184B0 + i));
      *((_DWORD *)dword_4184B0 + i) = 0;
    }
  }
  __acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x4141ec  push    10h
0x4141ee  push    offset stru_416C28
0x4141f3  call    __SEH_prolog4
0x4141f8  and     [ebp+var_1C], 0
0x4141fc  push    8
0x4141fe  call    ___acrt_lock
0x414203  pop     ecx
0x414204  and     [ebp+ms_exc.registration.TryLevel], 0
0x414208  push    3
0x41420a  pop     esi
0x41420b  mov     [ebp+var_20], esi
0x41420e  cmp     esi, Count
0x414214  jz      short loc_41426F
0x414216  mov     eax, dword_4184B0
0x41421b  mov     eax, [eax+esi*4]
0x41421e  test    eax, eax
0x414220  jz      short loc_41426C
0x414222  mov     eax, [eax+0Ch]
0x414225  nop
0x414226  shr     eax, 0Dh
0x414229  test    al, 1
0x41422b  jz      short loc_414243
0x41422d  mov     eax, dword_4184B0
0x414232  push    dword ptr [eax+esi*4]; Stream
0x414235  call    _fclose
0x41423a  pop     ecx
0x41423b  cmp     eax, 0FFFFFFFFh
0x41423e  jz      short loc_414243
0x414240  inc     [ebp+var_1C]
0x414243  mov     eax, dword_4184B0
0x414248  mov     eax, [eax+esi*4]
0x41424b  add     eax, 20h ; ' '
0x41424e  push    eax; lpCriticalSection
0x41424f  call    ds:DeleteCriticalSection
0x414255  mov     eax, dword_4184B0
0x41425a  push    dword ptr [eax+esi*4]; Block
0x41425d  call    __free_base
0x414262  pop     ecx
0x414263  mov     eax, dword_4184B0
0x414268  and     dword ptr [eax+esi*4], 0
0x41426c  inc     esi
0x41426d  jmp     short loc_41420B
0x41426f  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x414276  call    loc_41428E
0x41427b  mov     eax, [ebp+var_1C]
0x41427e  mov     ecx, [ebp+ms_exc.registration.Next]
0x414281  mov     large fs:0, ecx
0x414288  pop     ecx
0x414289  pop     edi
0x41428a  pop     esi
0x41428b  pop     ebx
0x41428c  leave
0x41428d  retn
0x41428e  push    8
0x414290  call    ___acrt_unlock
0x414295  pop     ecx
0x414296  retn
```
