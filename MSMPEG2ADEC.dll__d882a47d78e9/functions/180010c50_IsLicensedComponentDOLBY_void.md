# IsLicensedComponentDOLBY(void)

- ea: `0x180010c50`
- end: `0x180010cdf`
- name: `?IsLicensedComponentDOLBY@@YAHXZ`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010cf0`

## callees

- `0x180010c50`
- `0x180067160`

## import_xrefs

- `CompPkgSup!AreDvdCodecsEnabled` at `0x180010c5c`
- `CompPkgSup!AreDvdCodecsEnabled` at `0x180010c5c`

## pseudocode

```c
_BOOL8 IsLicensedComponentDOLBY(void)
{
  _BOOL8 result; // rax
  DWORD pdwValue; // [rsp+30h] [rbp+8h] BYREF

  pdwValue = 0;
  result = 1;
  if ( (int)AreDvdCodecsEnabled() < 0
    && (SLGetWindowsInformationDWORD(L"msmpeg2adec-DolbyDigitalDecoderV3InSKU", &pdwValue) || !pdwValue) )
  {
    pdwValue = 0;
    if ( SLGetWindowsInformationDWORD(L"msmpeg2adec-DolbyDigitalDecoderV3AddInEnable", &pdwValue) )
      return 0;
    if ( !pdwValue )
      return 0;
    pdwValue = 0;
    if ( SLGetWindowsInformationDWORD(L"msmpeg2adec-DolbyDigitalDecoderV3AddIn", &pdwValue) || !pdwValue )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010c50  sub     rsp, 28h
0x180010c54  mov     [rsp+28h+pdwValue], 0
0x180010c5c  call    cs:__imp_AreDvdCodecsEnabled
0x180010c63  nop     dword ptr [rax+rax+00h]
0x180010c68  test    eax, eax
0x180010c6a  js      short loc_180010C77
0x180010c6c  mov     eax, 1
0x180010c71  add     rsp, 28h
0x180010c75  retn
0x180010c77  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010c7c  lea     rcx, aMsmpeg2adecDol; "msmpeg2adec-DolbyDigitalDecoderV3InSKU"
0x180010c83  call    SLGetWindowsInformationDWORD
0x180010c88  test    eax, eax
0x180010c8a  jnz     short loc_180010C93
0x180010c8c  cmp     [rsp+28h+pdwValue], 1
0x180010c91  jnb     short loc_180010C6C
0x180010c93  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010c98  mov     [rsp+28h+pdwValue], 0
0x180010ca0  lea     rcx, aMsmpeg2adecDol_0; "msmpeg2adec-DolbyDigitalDecoderV3AddInE"...
0x180010ca7  call    SLGetWindowsInformationDWORD
0x180010cac  test    eax, eax
0x180010cae  jnz     short loc_180010CD7
0x180010cb0  cmp     [rsp+28h+pdwValue], 1
0x180010cb5  jb      short loc_180010CD7
0x180010cb7  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010cbc  mov     [rsp+28h+pdwValue], eax
0x180010cc0  lea     rcx, aMsmpeg2adecDol_1; "msmpeg2adec-DolbyDigitalDecoderV3AddIn"
0x180010cc7  call    SLGetWindowsInformationDWORD
0x180010ccc  test    eax, eax
0x180010cce  jnz     short loc_180010CD7
0x180010cd0  cmp     [rsp+28h+pdwValue], 1
0x180010cd5  jnb     short loc_180010C6C
0x180010cd7  xor     eax, eax
0x180010cd9  add     rsp, 28h
0x180010cdd  retn
```
