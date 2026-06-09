# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x40ca5a`
- end: `0x40cadd`
- name: `??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z`
- size: `131`
- prototype: `_LocaleUpdate *__thiscall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `18`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x40c35a`
- `0x40c4e1`
- `0x40db46`
- `0x40dd69`
- `0x40f43d`
- `0x40f873`
- `0x40ff4f`
- `0x410d19`
- `0x412467`
- `0x412722`
- `0x412ad9`
- `0x412cb2`
- `0x4131d1`
- `0x4138a7`
- `0x413b1e`
- `0x413e05`
- `0x414ab1`
- `0x41b29e`

## callees

- `0x40ca5a`
- `0x40e819`
- `0x4125c3`
- `0x4125f0`

## pseudocode

```c
_LocaleUpdate *__thiscall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  struct __crt_locale_data **v3; // ebx
  struct __crt_multibyte_data *mbcinfo; // eax
  int v5; // eax
  int v6; // eax

  *((_BYTE *)this + 12) = 0;
  v3 = (struct __crt_locale_data **)((char *)this + 4);
  if ( a2 )
  {
    *v3 = a2->locinfo;
    mbcinfo = a2->mbcinfo;
LABEL_5:
    *((_DWORD *)this + 2) = mbcinfo;
    return this;
  }
  if ( !dword_426E68 )
  {
    *v3 = (struct __crt_locale_data *)off_426638;
    mbcinfo = (struct __crt_multibyte_data *)off_42663C;
    goto LABEL_5;
  }
  v5 = __acrt_getptd();
  *(_DWORD *)this = v5;
  *v3 = *(struct __crt_locale_data **)(v5 + 76);
  *((_DWORD *)this + 2) = *(_DWORD *)(v5 + 72);
  sub_4125C3(v5, (char *)this + 4);
  sub_4125F0(*(_DWORD *)this, (char *)this + 8);
  v6 = *(_DWORD *)(*(_DWORD *)this + 848);
  if ( (v6 & 2) == 0 )
  {
    *(_DWORD *)(*(_DWORD *)this + 848) = v6 | 2;
    *((_BYTE *)this + 12) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x40ca5a  mov     edi, edi
0x40ca5c  push    ebp
0x40ca5d  mov     ebp, esp
0x40ca5f  push    ebx
0x40ca60  push    edi
0x40ca61  mov     edi, ecx
0x40ca63  mov     ecx, [ebp+arg_0]
0x40ca66  mov     byte ptr [edi+0Ch], 0
0x40ca6a  lea     ebx, [edi+4]
0x40ca6d  test    ecx, ecx
0x40ca6f  jz      short loc_40CA7A
0x40ca71  mov     eax, [ecx]
0x40ca73  mov     [ebx], eax
0x40ca75  mov     eax, [ecx+4]
0x40ca78  jmp     short loc_40CA8F
0x40ca7a  cmp     dword_426E68, 0
0x40ca81  jnz     short loc_40CA94
0x40ca83  mov     eax, off_426638
0x40ca88  mov     [ebx], eax
0x40ca8a  mov     eax, off_42663C
0x40ca8f  mov     [ebx+4], eax
0x40ca92  jmp     short loc_40CAD5
0x40ca94  push    esi
0x40ca95  call    ___acrt_getptd
0x40ca9a  mov     [edi], eax
0x40ca9c  lea     esi, [edi+8]
0x40ca9f  push    ebx
0x40caa0  push    eax
0x40caa1  mov     ecx, [eax+4Ch]
0x40caa4  mov     [ebx], ecx
0x40caa6  mov     ecx, [eax+48h]
0x40caa9  mov     [esi], ecx
0x40caab  call    sub_4125C3
0x40cab0  push    esi
0x40cab1  push    dword ptr [edi]
0x40cab3  call    sub_4125F0
0x40cab8  mov     ecx, [edi]
0x40caba  add     esp, 10h
0x40cabd  mov     eax, [ecx+350h]
0x40cac3  pop     esi
0x40cac4  test    al, 2
0x40cac6  jnz     short loc_40CAD5
0x40cac8  or      eax, 2
0x40cacb  mov     [ecx+350h], eax
0x40cad1  mov     byte ptr [edi+0Ch], 1
0x40cad5  mov     eax, edi
0x40cad7  pop     edi
0x40cad8  pop     ebx
0x40cad9  pop     ebp
0x40cada  retn    4
```
