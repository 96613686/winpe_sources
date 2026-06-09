# ___acrt_getptd

- ea: `0x40e819`
- end: `0x40e8d5`
- name: `___acrt_getptd`
- size: `188`
- prototype: `void *()`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x40bc97`
- `0x40c24f`
- `0x40ca5a`
- `0x40fcc8`
- `0x4109cf`
- `0x411105`
- `0x4118fe`
- `0x414219`

## callees

- `0x40c30b`
- `0x40e63e`
- `0x40e819`
- `0x40ecf6`
- `0x40ed53`
- `0x41144b`
- `0x41148a`

## import_xrefs

- `KERNEL32!SetLastError` at `0x40e8bc`
- `KERNEL32!SetLastError` at `0x40e8bc`
- `KERNEL32!GetLastError` at `0x40e81e`
- `KERNEL32!GetLastError` at `0x40e81e`

## pseudocode

```c
void *__acrt_getptd()
{
  DWORD LastError; // esi
  int v1; // eax
  void *Value; // eax
  void *v3; // edi
  void *v4; // ebx
  void *v5; // eax
  void *v6; // edi

  LastError = GetLastError();
  v1 = dword_426050;
  if ( dword_426050 == -1 )
    goto LABEL_7;
  Value = (void *)__acrt_FlsGetValue(dword_426050);
  v3 = Value;
  if ( !Value )
  {
    v1 = dword_426050;
LABEL_7:
    if ( !__acrt_FlsSetValue(v1, -1) )
      goto LABEL_4;
    v5 = _calloc_base(1u, 0x364u);
    v3 = v5;
    if ( !v5 )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_426050, 0);
      _free_base(0);
      goto LABEL_5;
    }
    if ( !__acrt_FlsSetValue(dword_426050, v5) )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_426050, 0);
      _free_base(v3);
      goto LABEL_5;
    }
    construct_ptd((struct __acrt_ptd *const)v3, &dword_42721C);
    _free_base(0);
    goto LABEL_13;
  }
  if ( Value == (void *)-1 )
  {
LABEL_4:
    v4 = 0;
LABEL_5:
    v3 = 0;
    goto LABEL_14;
  }
LABEL_13:
  v4 = v3;
LABEL_14:
  SetLastError(LastError);
  v6 = v3 != 0 ? v4 : 0;
  if ( !v6 )
    abort();
  return v6;
}

```

## disassembly

```asm
0x40e819  mov     edi, edi
0x40e81b  push    ebx
0x40e81c  push    esi
0x40e81d  push    edi
0x40e81e  call    ds:GetLastError
0x40e824  mov     esi, eax
0x40e826  mov     eax, dword_426050
0x40e82b  cmp     eax, 0FFFFFFFFh
0x40e82e  jz      short loc_40E84C
0x40e830  push    eax
0x40e831  call    ___acrt_FlsGetValue@4
0x40e836  mov     edi, eax
0x40e838  test    edi, edi
0x40e83a  jz      short loc_40E847
0x40e83c  cmp     edi, 0FFFFFFFFh
0x40e83f  jnz     short loc_40E8B9
0x40e841  xor     ebx, ebx
0x40e843  mov     edi, ebx
0x40e845  jmp     short loc_40E8BB
0x40e847  mov     eax, dword_426050
0x40e84c  push    0FFFFFFFFh
0x40e84e  push    eax
0x40e84f  call    ___acrt_FlsSetValue@8
0x40e854  test    eax, eax
0x40e856  jz      short loc_40E841
0x40e858  push    364h; Size
0x40e85d  push    1; Count
0x40e85f  call    __calloc_base
0x40e864  mov     edi, eax
0x40e866  pop     ecx
0x40e867  pop     ecx
0x40e868  test    edi, edi
0x40e86a  jnz     short loc_40E883
0x40e86c  xor     ebx, ebx
0x40e86e  push    ebx
0x40e86f  push    dword_426050
0x40e875  call    ___acrt_FlsSetValue@8
0x40e87a  push    ebx; Block
0x40e87b  call    __free_base
0x40e880  pop     ecx
0x40e881  jmp     short loc_40E843
0x40e883  push    edi
0x40e884  push    dword_426050
0x40e88a  call    ___acrt_FlsSetValue@8
0x40e88f  test    eax, eax
0x40e891  jnz     short loc_40E8A4
0x40e893  xor     ebx, ebx
0x40e895  push    ebx
0x40e896  push    dword_426050
0x40e89c  call    ___acrt_FlsSetValue@8
0x40e8a1  push    edi
0x40e8a2  jmp     short loc_40E87B
0x40e8a4  push    offset dword_42721C; struct __crt_locale_data **
0x40e8a9  push    edi; struct __acrt_ptd *
0x40e8aa  call    ?construct_ptd@@YAXQAU__acrt_ptd@@QAPAU__crt_locale_data@@@Z
0x40e8af  push    0; Block
0x40e8b1  call    __free_base
0x40e8b6  add     esp, 0Ch
0x40e8b9  mov     ebx, edi
0x40e8bb  push    esi; dwErrCode
0x40e8bc  call    ds:SetLastError
0x40e8c2  neg     edi
0x40e8c4  sbb     edi, edi
0x40e8c6  and     edi, ebx
0x40e8c8  jz      short loc_40E8D0
0x40e8ca  mov     eax, edi
0x40e8cc  pop     edi
0x40e8cd  pop     esi
0x40e8ce  pop     ebx
0x40e8cf  retn
0x40e8d0  call    _abort
```
