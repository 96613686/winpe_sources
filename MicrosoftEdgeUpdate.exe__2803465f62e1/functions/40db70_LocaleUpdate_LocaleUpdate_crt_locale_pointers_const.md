# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x40db70`
- end: `0x40dbf3`
- name: `??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z`
- size: `131`
- prototype: `_LocaleUpdate *__thiscall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x40dbf3`
- `0x40ded7`
- `0x41068a`
- `0x4116ed`
- `0x412df4`
- `0x412e3d`
- `0x4137a5`

## callees

- `0x40db70`
- `0x40f9a9`
- `0x40fc0a`
- `0x40fc37`

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
  if ( !dword_417FFC )
  {
    *v3 = (struct __crt_locale_data *)off_417110;
    mbcinfo = (struct __crt_multibyte_data *)off_417114;
    goto LABEL_5;
  }
  v5 = __acrt_getptd();
  *(_DWORD *)this = v5;
  *v3 = *(struct __crt_locale_data **)(v5 + 76);
  *((_DWORD *)this + 2) = *(_DWORD *)(v5 + 72);
  sub_40FC0A(v5, (char *)this + 4);
  sub_40FC37(*(_DWORD *)this, (char *)this + 8);
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
0x40db70  mov     edi, edi
0x40db72  push    ebp
0x40db73  mov     ebp, esp
0x40db75  push    ebx
0x40db76  push    edi
0x40db77  mov     edi, ecx
0x40db79  mov     ecx, [ebp+arg_0]
0x40db7c  mov     byte ptr [edi+0Ch], 0
0x40db80  lea     ebx, [edi+4]
0x40db83  test    ecx, ecx
0x40db85  jz      short loc_40DB90
0x40db87  mov     eax, [ecx]
0x40db89  mov     [ebx], eax
0x40db8b  mov     eax, [ecx+4]
0x40db8e  jmp     short loc_40DBA5
0x40db90  cmp     dword_417FFC, 0
0x40db97  jnz     short loc_40DBAA
0x40db99  mov     eax, off_417110
0x40db9e  mov     [ebx], eax
0x40dba0  mov     eax, off_417114
0x40dba5  mov     [ebx+4], eax
0x40dba8  jmp     short loc_40DBEB
0x40dbaa  push    esi
0x40dbab  call    ___acrt_getptd
0x40dbb0  mov     [edi], eax
0x40dbb2  lea     esi, [edi+8]
0x40dbb5  push    ebx
0x40dbb6  push    eax
0x40dbb7  mov     ecx, [eax+4Ch]
0x40dbba  mov     [ebx], ecx
0x40dbbc  mov     ecx, [eax+48h]
0x40dbbf  mov     [esi], ecx
0x40dbc1  call    sub_40FC0A
0x40dbc6  push    esi
0x40dbc7  push    dword ptr [edi]
0x40dbc9  call    sub_40FC37
0x40dbce  mov     ecx, [edi]
0x40dbd0  add     esp, 10h
0x40dbd3  mov     eax, [ecx+350h]
0x40dbd9  pop     esi
0x40dbda  test    al, 2
0x40dbdc  jnz     short loc_40DBEB
0x40dbde  or      eax, 2
0x40dbe1  mov     [ecx+350h], eax
0x40dbe7  mov     byte ptr [edi+0Ch], 1
0x40dbeb  mov     eax, edi
0x40dbed  pop     edi
0x40dbee  pop     ebx
0x40dbef  pop     ebp
0x40dbf0  retn    4
```
