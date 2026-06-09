# ___acrt_getptd

- ea: `0x40f9a9`
- end: `0x40fa65`
- name: `___acrt_getptd`
- size: `188`
- prototype: `void *()`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x40db70`
- `0x40ee87`
- `0x40f45f`
- `0x40f49b`
- `0x40fc64`
- `0x410ae8`
- `0x411ad9`
- `0x4121f6`
- `0x413bb9`

## callees

- `0x40f51a`
- `0x40f7cc`
- `0x40f9a9`
- `0x40ffbd`
- `0x41001a`
- `0x411de6`
- `0x411e25`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40f9ae`
- `KERNEL32!GetLastError` at `0x40f9ae`
- `KERNEL32!SetLastError` at `0x40fa4c`
- `KERNEL32!SetLastError` at `0x40fa4c`

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
0x40f9a9  mov     edi, edi
0x40f9ab  push    ebx
0x40f9ac  push    esi
0x40f9ad  push    edi
0x40f9ae  call    ds:GetLastError
0x40f9b4  mov     esi, eax
0x40f9b6  mov     eax, dword_417050
0x40f9bb  cmp     eax, 0FFFFFFFFh
0x40f9be  jz      short loc_40F9DC
0x40f9c0  push    eax
0x40f9c1  call    ___acrt_FlsGetValue@4
0x40f9c6  mov     edi, eax
0x40f9c8  test    edi, edi
0x40f9ca  jz      short loc_40F9D7
0x40f9cc  cmp     edi, 0FFFFFFFFh
0x40f9cf  jnz     short loc_40FA49
0x40f9d1  xor     ebx, ebx
0x40f9d3  mov     edi, ebx
0x40f9d5  jmp     short loc_40FA4B
0x40f9d7  mov     eax, dword_417050
0x40f9dc  push    0FFFFFFFFh
0x40f9de  push    eax
0x40f9df  call    ___acrt_FlsSetValue@8
0x40f9e4  test    eax, eax
0x40f9e6  jz      short loc_40F9D1
0x40f9e8  push    364h; Size
0x40f9ed  push    1; Count
0x40f9ef  call    __calloc_base
0x40f9f4  mov     edi, eax
0x40f9f6  pop     ecx
0x40f9f7  pop     ecx
0x40f9f8  test    edi, edi
0x40f9fa  jnz     short loc_40FA13
0x40f9fc  xor     ebx, ebx
0x40f9fe  push    ebx
0x40f9ff  push    dword_417050
0x40fa05  call    ___acrt_FlsSetValue@8
0x40fa0a  push    ebx; Block
0x40fa0b  call    __free_base
0x40fa10  pop     ecx
0x40fa11  jmp     short loc_40F9D3
0x40fa13  push    edi
0x40fa14  push    dword_417050
0x40fa1a  call    ___acrt_FlsSetValue@8
0x40fa1f  test    eax, eax
0x40fa21  jnz     short loc_40FA34
0x40fa23  xor     ebx, ebx
0x40fa25  push    ebx
0x40fa26  push    dword_417050
0x40fa2c  call    ___acrt_FlsSetValue@8
0x40fa31  push    edi
0x40fa32  jmp     short loc_40FA0B
0x40fa34  push    offset dword_418020; struct __crt_locale_data **
0x40fa39  push    edi; struct __acrt_ptd *
0x40fa3a  call    ?construct_ptd@@YAXQAU__acrt_ptd@@QAPAU__crt_locale_data@@@Z
0x40fa3f  push    0; Block
0x40fa41  call    __free_base
0x40fa46  add     esp, 0Ch
0x40fa49  mov     ebx, edi
0x40fa4b  push    esi; dwErrCode
0x40fa4c  call    ds:SetLastError
0x40fa52  neg     edi
0x40fa54  sbb     edi, edi
0x40fa56  and     edi, ebx
0x40fa58  jz      short loc_40FA60
0x40fa5a  mov     eax, edi
0x40fa5c  pop     edi
0x40fa5d  pop     esi
0x40fa5e  pop     ebx
0x40fa5f  retn
0x40fa60  call    _abort
```
