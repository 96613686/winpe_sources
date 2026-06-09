# ___acrt_getptd_noexit

- ea: `0x40fb00`
- end: `0x40fbb5`
- name: `___acrt_getptd_noexit`
- size: `181`
- prototype: `void *()`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x40ddf0`
- `0x40e29f`
- `0x40fbc0`
- `0x40ff96`
- `0x40ffa9`
- `0x4121f6`

## callees

- `0x40f7cc`
- `0x40fb00`
- `0x40ffbd`
- `0x41001a`
- `0x411de6`
- `0x411e25`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40fb05`
- `KERNEL32!GetLastError` at `0x40fb05`
- `KERNEL32!SetLastError` at `0x40fba3`
- `KERNEL32!SetLastError` at `0x40fba3`

## pseudocode

```c
void *__acrt_getptd_noexit()
{
  DWORD LastError; // esi
  int v1; // eax
  void *Value; // eax
  void *v3; // edi
  void *v4; // ebx
  void *v5; // eax

  LastError = GetLastError();
  v1 = dword_417050;
  if ( dword_417050 == -1 )
    goto LABEL_7;
  Value = (void *)__acrt_FlsGetValue(dword_417050);
  v3 = Value;
  if ( !Value )
  {
    v1 = dword_417050;
LABEL_7:
    if ( !__acrt_FlsSetValue(v1, -1) )
      goto LABEL_4;
    v5 = _calloc_base(1u, 0x364u);
    v3 = v5;
    if ( !v5 )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_417050, 0);
      _free_base(0);
      goto LABEL_5;
    }
    if ( !__acrt_FlsSetValue(dword_417050, v5) )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_417050, 0);
      _free_base(v3);
      goto LABEL_5;
    }
    construct_ptd((struct __acrt_ptd *const)v3, &dword_418020);
    _free_base(0);
LABEL_13:
    v4 = v3;
    goto LABEL_14;
  }
  if ( Value != (void *)-1 )
    goto LABEL_13;
LABEL_4:
  v4 = 0;
LABEL_5:
  v3 = 0;
LABEL_14:
  SetLastError(LastError);
  return v3 != 0 ? v4 : 0;
}

```

## disassembly

```asm
0x40fb00  mov     edi, edi
0x40fb02  push    ebx
0x40fb03  push    esi
0x40fb04  push    edi
0x40fb05  call    ds:GetLastError
0x40fb0b  mov     esi, eax
0x40fb0d  mov     eax, dword_417050
0x40fb12  cmp     eax, 0FFFFFFFFh
0x40fb15  jz      short loc_40FB33
0x40fb17  push    eax
0x40fb18  call    ___acrt_FlsGetValue@4
0x40fb1d  mov     edi, eax
0x40fb1f  test    edi, edi
0x40fb21  jz      short loc_40FB2E
0x40fb23  cmp     edi, 0FFFFFFFFh
0x40fb26  jnz     short loc_40FBA0
0x40fb28  xor     ebx, ebx
0x40fb2a  mov     edi, ebx
0x40fb2c  jmp     short loc_40FBA2
0x40fb2e  mov     eax, dword_417050
0x40fb33  push    0FFFFFFFFh
0x40fb35  push    eax
0x40fb36  call    ___acrt_FlsSetValue@8
0x40fb3b  test    eax, eax
0x40fb3d  jz      short loc_40FB28
0x40fb3f  push    364h; Size
0x40fb44  push    1; Count
0x40fb46  call    __calloc_base
0x40fb4b  mov     edi, eax
0x40fb4d  pop     ecx
0x40fb4e  pop     ecx
0x40fb4f  test    edi, edi
0x40fb51  jnz     short loc_40FB6A
0x40fb53  xor     ebx, ebx
0x40fb55  push    ebx
0x40fb56  push    dword_417050
0x40fb5c  call    ___acrt_FlsSetValue@8
0x40fb61  push    ebx; Block
0x40fb62  call    __free_base
0x40fb67  pop     ecx
0x40fb68  jmp     short loc_40FB2A
0x40fb6a  push    edi
0x40fb6b  push    dword_417050
0x40fb71  call    ___acrt_FlsSetValue@8
0x40fb76  test    eax, eax
0x40fb78  jnz     short loc_40FB8B
0x40fb7a  xor     ebx, ebx
0x40fb7c  push    ebx
0x40fb7d  push    dword_417050
0x40fb83  call    ___acrt_FlsSetValue@8
0x40fb88  push    edi
0x40fb89  jmp     short loc_40FB62
0x40fb8b  push    offset dword_418020; struct __crt_locale_data **
0x40fb90  push    edi; struct __acrt_ptd *
0x40fb91  call    ?construct_ptd@@YAXQAU__acrt_ptd@@QAPAU__crt_locale_data@@@Z
0x40fb96  push    0; Block
0x40fb98  call    __free_base
0x40fb9d  add     esp, 0Ch
0x40fba0  mov     ebx, edi
0x40fba2  push    esi; dwErrCode
0x40fba3  call    ds:SetLastError
0x40fba9  neg     edi
0x40fbab  sbb     edi, edi
0x40fbad  and     edi, ebx
0x40fbaf  mov     eax, edi
0x40fbb1  pop     edi
0x40fbb2  pop     esi
0x40fbb3  pop     ebx
0x40fbb4  retn
```
