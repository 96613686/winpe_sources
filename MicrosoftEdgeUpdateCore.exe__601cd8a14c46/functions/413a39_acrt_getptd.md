# ___acrt_getptd

- ea: `0x413a39`
- end: `0x413af5`
- name: `___acrt_getptd`
- size: `188`
- prototype: `void *()`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x411577`
- `0x411615`
- `0x411eed`
- `0x414908`
- `0x415680`
- `0x41625b`
- `0x416b01`
- `0x418bde`

## callees

- `0x4116b0`
- `0x4136b2`
- `0x413858`
- `0x413a39`
- `0x413e19`
- `0x415004`
- `0x415043`

## import_xrefs

- `KERNEL32!SetLastError` at `0x413adc`
- `KERNEL32!SetLastError` at `0x413adc`
- `KERNEL32!GetLastError` at `0x413a3e`
- `KERNEL32!GetLastError` at `0x413a3e`

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
  v1 = dword_43D060;
  if ( dword_43D060 == -1 )
    goto LABEL_7;
  Value = (void *)__acrt_FlsGetValue(dword_43D060);
  v3 = Value;
  if ( !Value )
  {
    v1 = dword_43D060;
LABEL_7:
    if ( !__acrt_FlsSetValue(v1, -1) )
      goto LABEL_4;
    v5 = _calloc_base(1u, 0x364u);
    v3 = v5;
    if ( !v5 )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_43D060, 0);
      _free_base(0);
      goto LABEL_5;
    }
    if ( !__acrt_FlsSetValue(dword_43D060, v5) )
    {
      v4 = 0;
      __acrt_FlsSetValue(dword_43D060, 0);
      _free_base(v3);
      goto LABEL_5;
    }
    construct_ptd((struct __acrt_ptd *const)v3, &dword_43E7A0);
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
0x413a39  mov     edi, edi
0x413a3b  push    ebx
0x413a3c  push    esi
0x413a3d  push    edi
0x413a3e  call    ds:GetLastError
0x413a44  mov     esi, eax
0x413a46  mov     eax, dword_43D060
0x413a4b  cmp     eax, 0FFFFFFFFh
0x413a4e  jz      short loc_413A6C
0x413a50  push    eax
0x413a51  call    ___acrt_FlsGetValue@4
0x413a56  mov     edi, eax
0x413a58  test    edi, edi
0x413a5a  jz      short loc_413A67
0x413a5c  cmp     edi, 0FFFFFFFFh
0x413a5f  jnz     short loc_413AD9
0x413a61  xor     ebx, ebx
0x413a63  mov     edi, ebx
0x413a65  jmp     short loc_413ADB
0x413a67  mov     eax, dword_43D060
0x413a6c  push    0FFFFFFFFh
0x413a6e  push    eax
0x413a6f  call    ___acrt_FlsSetValue@8
0x413a74  test    eax, eax
0x413a76  jz      short loc_413A61
0x413a78  push    364h; Size
0x413a7d  push    1; Count
0x413a7f  call    __calloc_base
0x413a84  mov     edi, eax
0x413a86  pop     ecx
0x413a87  pop     ecx
0x413a88  test    edi, edi
0x413a8a  jnz     short loc_413AA3
0x413a8c  xor     ebx, ebx
0x413a8e  push    ebx
0x413a8f  push    dword_43D060
0x413a95  call    ___acrt_FlsSetValue@8
0x413a9a  push    ebx; Block
0x413a9b  call    __free_base
0x413aa0  pop     ecx
0x413aa1  jmp     short loc_413A63
0x413aa3  push    edi
0x413aa4  push    dword_43D060
0x413aaa  call    ___acrt_FlsSetValue@8
0x413aaf  test    eax, eax
0x413ab1  jnz     short loc_413AC4
0x413ab3  xor     ebx, ebx
0x413ab5  push    ebx
0x413ab6  push    dword_43D060
0x413abc  call    ___acrt_FlsSetValue@8
0x413ac1  push    edi
0x413ac2  jmp     short loc_413A9B
0x413ac4  push    offset dword_43E7A0; struct __crt_locale_data **
0x413ac9  push    edi; struct __acrt_ptd *
0x413aca  call    ?construct_ptd@@YAXQAU__acrt_ptd@@QAPAU__crt_locale_data@@@Z
0x413acf  push    0; Block
0x413ad1  call    __free_base
0x413ad6  add     esp, 0Ch
0x413ad9  mov     ebx, edi
0x413adb  push    esi; dwErrCode
0x413adc  call    ds:SetLastError
0x413ae2  neg     edi
0x413ae4  sbb     edi, edi
0x413ae6  and     edi, ebx
0x413ae8  jz      short loc_413AF0
0x413aea  mov     eax, edi
0x413aec  pop     edi
0x413aed  pop     esi
0x413aee  pop     ebx
0x413aef  retn
0x413af0  call    _abort
```
