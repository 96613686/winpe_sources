# ___acrt_getptd_noexit

- ea: `0x40e970`
- end: `0x40ea25`
- name: `___acrt_getptd_noexit`
- size: `181`
- prototype: `void *()`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x40b0d0`
- `0x40ea30`
- `0x40ebc2`
- `0x40ecd0`
- `0x40ece3`
- `0x4118fe`

## callees

- `0x40e63e`
- `0x40e970`
- `0x40ecf6`
- `0x40ed53`
- `0x41144b`
- `0x41148a`

## import_xrefs

- `KERNEL32!SetLastError` at `0x40ea13`
- `KERNEL32!SetLastError` at `0x40ea13`
- `KERNEL32!GetLastError` at `0x40e975`
- `KERNEL32!GetLastError` at `0x40e975`

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
0x40e970  mov     edi, edi
0x40e972  push    ebx
0x40e973  push    esi
0x40e974  push    edi
0x40e975  call    ds:GetLastError
0x40e97b  mov     esi, eax
0x40e97d  mov     eax, dword_426050
0x40e982  cmp     eax, 0FFFFFFFFh
0x40e985  jz      short loc_40E9A3
0x40e987  push    eax
0x40e988  call    ___acrt_FlsGetValue@4
0x40e98d  mov     edi, eax
0x40e98f  test    edi, edi
0x40e991  jz      short loc_40E99E
0x40e993  cmp     edi, 0FFFFFFFFh
0x40e996  jnz     short loc_40EA10
0x40e998  xor     ebx, ebx
0x40e99a  mov     edi, ebx
0x40e99c  jmp     short loc_40EA12
0x40e99e  mov     eax, dword_426050
0x40e9a3  push    0FFFFFFFFh
0x40e9a5  push    eax
0x40e9a6  call    ___acrt_FlsSetValue@8
0x40e9ab  test    eax, eax
0x40e9ad  jz      short loc_40E998
0x40e9af  push    364h; Size
0x40e9b4  push    1; Count
0x40e9b6  call    __calloc_base
0x40e9bb  mov     edi, eax
0x40e9bd  pop     ecx
0x40e9be  pop     ecx
0x40e9bf  test    edi, edi
0x40e9c1  jnz     short loc_40E9DA
0x40e9c3  xor     ebx, ebx
0x40e9c5  push    ebx
0x40e9c6  push    dword_426050
0x40e9cc  call    ___acrt_FlsSetValue@8
0x40e9d1  push    ebx; Block
0x40e9d2  call    __free_base
0x40e9d7  pop     ecx
0x40e9d8  jmp     short loc_40E99A
0x40e9da  push    edi
0x40e9db  push    dword_426050
0x40e9e1  call    ___acrt_FlsSetValue@8
0x40e9e6  test    eax, eax
0x40e9e8  jnz     short loc_40E9FB
0x40e9ea  xor     ebx, ebx
0x40e9ec  push    ebx
0x40e9ed  push    dword_426050
0x40e9f3  call    ___acrt_FlsSetValue@8
0x40e9f8  push    edi
0x40e9f9  jmp     short loc_40E9D2
0x40e9fb  push    offset dword_42721C; struct __crt_locale_data **
0x40ea00  push    edi; struct __acrt_ptd *
0x40ea01  call    ?construct_ptd@@YAXQAU__acrt_ptd@@QAPAU__crt_locale_data@@@Z
0x40ea06  push    0; Block
0x40ea08  call    __free_base
0x40ea0d  add     esp, 0Ch
0x40ea10  mov     ebx, edi
0x40ea12  push    esi; dwErrCode
0x40ea13  call    ds:SetLastError
0x40ea19  neg     edi
0x40ea1b  sbb     edi, edi
0x40ea1d  and     edi, ebx
0x40ea1f  mov     eax, edi
0x40ea21  pop     edi
0x40ea22  pop     esi
0x40ea23  pop     ebx
0x40ea24  retn
```
