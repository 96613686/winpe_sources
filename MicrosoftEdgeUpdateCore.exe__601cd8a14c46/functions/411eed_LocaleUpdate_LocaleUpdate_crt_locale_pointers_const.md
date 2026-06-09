# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x411eed`
- end: `0x411f70`
- name: `??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z`
- size: `131`
- prototype: `_LocaleUpdate *__thiscall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `12`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x411867`
- `0x4119ee`
- `0x412fc9`
- `0x4144aa`
- `0x416715`
- `0x41713b`
- `0x4173f6`
- `0x4177ad`
- `0x417986`
- `0x4185ca`
- `0x4187ca`
- `0x4194c5`

## callees

- `0x411eed`
- `0x413a39`
- `0x417297`
- `0x4172c4`

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
  if ( !dword_43E318 )
  {
    *v3 = (struct __crt_locale_data *)off_43D640;
    mbcinfo = (struct __crt_multibyte_data *)off_43D644;
    goto LABEL_5;
  }
  v5 = __acrt_getptd();
  *(_DWORD *)this = v5;
  *v3 = *(struct __crt_locale_data **)(v5 + 76);
  *((_DWORD *)this + 2) = *(_DWORD *)(v5 + 72);
  sub_417297(v5, (char *)this + 4);
  sub_4172C4(*(_DWORD *)this, (char *)this + 8);
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
0x411eed  mov     edi, edi
0x411eef  push    ebp
0x411ef0  mov     ebp, esp
0x411ef2  push    ebx
0x411ef3  push    edi
0x411ef4  mov     edi, ecx
0x411ef6  mov     ecx, [ebp+arg_0]
0x411ef9  mov     byte ptr [edi+0Ch], 0
0x411efd  lea     ebx, [edi+4]
0x411f00  test    ecx, ecx
0x411f02  jz      short loc_411F0D
0x411f04  mov     eax, [ecx]
0x411f06  mov     [ebx], eax
0x411f08  mov     eax, [ecx+4]
0x411f0b  jmp     short loc_411F22
0x411f0d  cmp     dword_43E318, 0
0x411f14  jnz     short loc_411F27
0x411f16  mov     eax, off_43D640
0x411f1b  mov     [ebx], eax
0x411f1d  mov     eax, off_43D644
0x411f22  mov     [ebx+4], eax
0x411f25  jmp     short loc_411F68
0x411f27  push    esi
0x411f28  call    ___acrt_getptd
0x411f2d  mov     [edi], eax
0x411f2f  lea     esi, [edi+8]
0x411f32  push    ebx
0x411f33  push    eax
0x411f34  mov     ecx, [eax+4Ch]
0x411f37  mov     [ebx], ecx
0x411f39  mov     ecx, [eax+48h]
0x411f3c  mov     [esi], ecx
0x411f3e  call    sub_417297
0x411f43  push    esi
0x411f44  push    dword ptr [edi]
0x411f46  call    sub_4172C4
0x411f4b  mov     ecx, [edi]
0x411f4d  add     esp, 10h
0x411f50  mov     eax, [ecx+350h]
0x411f56  pop     esi
0x411f57  test    al, 2
0x411f59  jnz     short loc_411F68
0x411f5b  or      eax, 2
0x411f5e  mov     [ecx+350h], eax
0x411f64  mov     byte ptr [edi+0Ch], 1
0x411f68  mov     eax, edi
0x411f6a  pop     edi
0x411f6b  pop     ebx
0x411f6c  pop     ebp
0x411f6d  retn    4
```
