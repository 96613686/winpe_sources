# __fcloseall

- ea: `0x41484c`
- end: `0x4148f7`
- name: `__fcloseall`
- size: `171`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x411e60`

## callees

- `0x4089e0`
- `0x40ed53`
- `0x410211`
- `0x410261`
- `0x41484c`
- `0x4169a1`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x4148af`
- `KERNEL32!DeleteCriticalSection` at `0x4148af`

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
    v1 = *((_DWORD *)dword_42731C + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 12) & 0x2000) != 0 && fclose(*((FILE **)dword_42731C + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_DWORD *)dword_42731C + i) + 32));
      _free_base(*((void **)dword_42731C + i));
      *((_DWORD *)dword_42731C + i) = 0;
    }
  }
  __acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x41484c  push    10h
0x41484e  push    offset stru_424380
0x414853  call    __SEH_prolog4
0x414858  and     [ebp+var_1C], 0
0x41485c  push    8
0x41485e  call    ___acrt_lock
0x414863  pop     ecx
0x414864  and     [ebp+ms_exc.registration.TryLevel], 0
0x414868  push    3
0x41486a  pop     esi
0x41486b  mov     [ebp+var_20], esi
0x41486e  cmp     esi, Count
0x414874  jz      short loc_4148CF
0x414876  mov     eax, dword_42731C
0x41487b  mov     eax, [eax+esi*4]
0x41487e  test    eax, eax
0x414880  jz      short loc_4148CC
0x414882  mov     eax, [eax+0Ch]
0x414885  nop
0x414886  shr     eax, 0Dh
0x414889  test    al, 1
0x41488b  jz      short loc_4148A3
0x41488d  mov     eax, dword_42731C
0x414892  push    dword ptr [eax+esi*4]; Stream
0x414895  call    _fclose
0x41489a  pop     ecx
0x41489b  cmp     eax, 0FFFFFFFFh
0x41489e  jz      short loc_4148A3
0x4148a0  inc     [ebp+var_1C]
0x4148a3  mov     eax, dword_42731C
0x4148a8  mov     eax, [eax+esi*4]
0x4148ab  add     eax, 20h ; ' '
0x4148ae  push    eax; lpCriticalSection
0x4148af  call    ds:DeleteCriticalSection
0x4148b5  mov     eax, dword_42731C
0x4148ba  push    dword ptr [eax+esi*4]; Block
0x4148bd  call    __free_base
0x4148c2  pop     ecx
0x4148c3  mov     eax, dword_42731C
0x4148c8  and     dword ptr [eax+esi*4], 0
0x4148cc  inc     esi
0x4148cd  jmp     short loc_41486B
0x4148cf  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x4148d6  call    loc_4148EE
0x4148db  mov     eax, [ebp+var_1C]
0x4148de  mov     ecx, [ebp+ms_exc.registration.Next]
0x4148e1  mov     large fs:0, ecx
0x4148e8  pop     ecx
0x4148e9  pop     edi
0x4148ea  pop     esi
0x4148eb  pop     ebx
0x4148ec  leave
0x4148ed  retn
0x4148ee  push    8
0x4148f0  call    ___acrt_unlock
0x4148f5  pop     ecx
0x4148f6  retn
```
