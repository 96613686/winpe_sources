# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x10013673`
- end: `0x100136f6`
- name: `??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z`
- size: `131`
- prototype: `_LocaleUpdate *__thiscall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `22`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10012e0a`
- `0x10013031`
- `0x1001380a`
- `0x1001398a`
- `0x10015dff`
- `0x10015e37`
- `0x10015e72`
- `0x10016e02`
- `0x10017561`
- `0x10017796`
- `0x100178f4`
- `0x10017da2`
- `0x10018161`
- `0x10018338`
- `0x10018b58`
- `0x100193ae`
- `0x100197de`
- `0x1001ac89`
- `0x1001acc5`
- `0x1001b5eb`
- `0x1001d9e7`
- `0x1001dd18`

## callees

- `0x10013673`
- `0x1001721d`
- `0x1001746f`
- `0x1001749c`

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
  if ( !dword_10034F08 )
  {
    *v3 = (struct __crt_locale_data *)off_10033168;
    mbcinfo = (struct __crt_multibyte_data *)off_1003316C;
    goto LABEL_5;
  }
  v5 = __acrt_getptd();
  *(_DWORD *)this = v5;
  *v3 = *(struct __crt_locale_data **)(v5 + 76);
  *((_DWORD *)this + 2) = *(_DWORD *)(v5 + 72);
  sub_1001746F(v5, (char *)this + 4);
  sub_1001749C(*(_DWORD *)this, (char *)this + 8);
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
0x10013673  mov     edi, edi
0x10013675  push    ebp
0x10013676  mov     ebp, esp
0x10013678  push    ebx
0x10013679  push    edi
0x1001367a  mov     edi, ecx
0x1001367c  mov     ecx, [ebp+arg_0]
0x1001367f  mov     byte ptr [edi+0Ch], 0
0x10013683  lea     ebx, [edi+4]
0x10013686  test    ecx, ecx
0x10013688  jz      short loc_10013693
0x1001368a  mov     eax, [ecx]
0x1001368c  mov     [ebx], eax
0x1001368e  mov     eax, [ecx+4]
0x10013691  jmp     short loc_100136A8
0x10013693  cmp     dword_10034F08, 0
0x1001369a  jnz     short loc_100136AD
0x1001369c  mov     eax, off_10033168
0x100136a1  mov     [ebx], eax
0x100136a3  mov     eax, off_1003316C
0x100136a8  mov     [ebx+4], eax
0x100136ab  jmp     short loc_100136EE
0x100136ad  push    esi
0x100136ae  call    ___acrt_getptd
0x100136b3  mov     [edi], eax
0x100136b5  lea     esi, [edi+8]
0x100136b8  push    ebx
0x100136b9  push    eax
0x100136ba  mov     ecx, [eax+4Ch]
0x100136bd  mov     [ebx], ecx
0x100136bf  mov     ecx, [eax+48h]
0x100136c2  mov     [esi], ecx
0x100136c4  call    sub_1001746F
0x100136c9  push    esi
0x100136ca  push    dword ptr [edi]
0x100136cc  call    sub_1001749C
0x100136d1  mov     ecx, [edi]
0x100136d3  add     esp, 10h
0x100136d6  mov     eax, [ecx+350h]
0x100136dc  pop     esi
0x100136dd  test    al, 2
0x100136df  jnz     short loc_100136EE
0x100136e1  or      eax, 2
0x100136e4  mov     [ecx+350h], eax
0x100136ea  mov     byte ptr [edi+0Ch], 1
0x100136ee  mov     eax, edi
0x100136f0  pop     edi
0x100136f1  pop     ebx
0x100136f2  pop     ebp
0x100136f3  retn    4
```
