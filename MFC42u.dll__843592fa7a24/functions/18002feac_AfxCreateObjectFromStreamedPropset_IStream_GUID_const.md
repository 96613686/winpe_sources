# _AfxCreateObjectFromStreamedPropset(IStream *,_GUID const &)

- ea: `0x18002feac`
- end: `0x18002fff6`
- name: `?_AfxCreateObjectFromStreamedPropset@@YAPEAUIUnknown@@PEAUIStream@@AEBU_GUID@@@Z`
- size: `330`
- prototype: `struct IUnknown *__fastcall(struct IStream *, IID *riid)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c2df0`
- `0x1800c2f00`

## callees

- `0x18000a150`
- `0x18002feac`
- `0x1800c3b0c`
- `0x1800c3d68`
- `0x1800d1f6e`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ff71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ff71`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x18002ff8b`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x18002ff8b`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18002ffc6`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18002ffc6`

## pseudocode

```c
struct IUnknown *__fastcall _AfxCreateObjectFromStreamedPropset(struct IStream *a1, IID *riid)
{
  struct IUnknown *result; // rax
  HRESULT v5; // eax
  LPVOID lpvObj; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID Buf1; // [rsp+38h] [rbp-18h] BYREF

  lpvObj = 0;
  Buf1 = 0;
  if ( !(unsigned int)_AfxGetClassIDFromStreamedPropset(&Buf1, a1) )
    return (struct IUnknown *)lpvObj;
  if ( !memcmp_0(&Buf1, &CLSID_StdFont, 0x10u) || !memcmp_0(&Buf1, &_afx_CLSID_StdFont_V1, 0x10u) )
  {
    v5 = OleCreateFontIndirect((LPFONTDESC)&_afxFontDescHelv, riid, &lpvObj);
  }
  else
  {
    if ( memcmp_0(&Buf1, &CLSID_StdPicture, 0x10u) && memcmp_0(&Buf1, &_afx_CLSID_StdPicture_V1, 0x10u) )
    {
      if ( CoCreateInstance(&Buf1, 0, 1u, riid, &lpvObj) < 0 )
        return 0;
      goto LABEL_10;
    }
    v5 = OleCreatePictureIndirect(0, riid, 0, &lpvObj);
  }
  if ( v5 < 0 )
  {
    result = 0;
    lpvObj = 0;
    goto LABEL_11;
  }
LABEL_10:
  result = (struct IUnknown *)lpvObj;
LABEL_11:
  if ( !result )
    return result;
  if ( !(unsigned int)_AfxLoadObjectFromStreamedPropset(result, a1) )
  {
    _AfxRelease((struct IUnknown **)&lpvObj);
    return 0;
  }
  return (struct IUnknown *)lpvObj;
}

```

## disassembly

```asm
0x18002feac  mov     [rsp-18h+arg_10], rbx
0x18002feb1  push    rbp
0x18002feb2  push    rsi
0x18002feb3  push    rdi
0x18002feb4  mov     rbp, rsp
0x18002feb7  sub     rsp, 50h
0x18002febb  mov     rax, cs:__security_cookie
0x18002fec2  xor     rax, rsp
0x18002fec5  mov     [rbp+var_8], rax
0x18002fec9  mov     rbx, rdx
0x18002fecc  mov     [rbp+lpvObj], 0
0x18002fed4  mov     rdx, rcx; struct IStream *
0x18002fed7  mov     rdi, rcx
0x18002feda  xorps   xmm0, xmm0
0x18002fedd  lea     rcx, [rbp+Buf1]; struct _GUID *
0x18002fee1  movups  [rbp+Buf1], xmm0
0x18002fee5  call    ?_AfxGetClassIDFromStreamedPropset@@YAHPEAU_GUID@@PEAUIStream@@@Z; _AfxGetClassIDFromStreamedPropset(_GUID *,IStream *)
0x18002feea  test    eax, eax
0x18002feec  jz      loc_18002FFD6
0x18002fef2  mov     esi, 10h
0x18002fef7  lea     rdx, CLSID_StdFont; Buf2
0x18002fefe  mov     r8d, esi; Size
0x18002ff01  lea     rcx, [rbp+Buf1]; Buf1
0x18002ff05  call    memcmp_0
0x18002ff0a  test    eax, eax
0x18002ff0c  jz      loc_18002FFB8
0x18002ff12  mov     r8d, esi; Size
0x18002ff15  lea     rdx, ?_afx_CLSID_StdFont_V1@@3U_GUID@@B; Buf2
0x18002ff1c  lea     rcx, [rbp+Buf1]; Buf1
0x18002ff20  call    memcmp_0
0x18002ff25  test    eax, eax
0x18002ff27  jz      loc_18002FFB8
0x18002ff2d  mov     r8d, esi; Size
0x18002ff30  lea     rdx, CLSID_StdPicture; Buf2
0x18002ff37  lea     rcx, [rbp+Buf1]; Buf1
0x18002ff3b  call    memcmp_0
0x18002ff40  test    eax, eax
0x18002ff42  jz      short loc_18002FF7F
0x18002ff44  mov     r8d, esi; Size
0x18002ff47  lea     rdx, ?_afx_CLSID_StdPicture_V1@@3U_GUID@@B; Buf2
0x18002ff4e  lea     rcx, [rbp+Buf1]; Buf1
0x18002ff52  call    memcmp_0
0x18002ff57  test    eax, eax
0x18002ff59  jz      short loc_18002FF7F
0x18002ff5b  lea     rax, [rbp+lpvObj]
0x18002ff5f  mov     r9, rbx; riid
0x18002ff62  xor     edx, edx; pUnkOuter
0x18002ff64  mov     [rsp+50h+ppv], rax; ppv
0x18002ff69  lea     r8d, [rsi-0Fh]; dwClsContext
0x18002ff6d  lea     rcx, [rbp+Buf1]; rclsid
0x18002ff71  call    cs:__imp_CoCreateInstance
0x18002ff77  test    eax, eax
0x18002ff79  jns     short loc_18002FF95
0x18002ff7b  xor     eax, eax
0x18002ff7d  jmp     short loc_18002FFDA
0x18002ff7f  lea     r9, [rbp+lpvObj]; lplpvObj
0x18002ff83  xor     r8d, r8d; fOwn
0x18002ff86  mov     rdx, rbx; riid
0x18002ff89  xor     ecx, ecx; lpPictDesc
0x18002ff8b  call    cs:__imp_OleCreatePictureIndirect
0x18002ff91  test    eax, eax
0x18002ff93  js      short loc_18002FFCE
0x18002ff95  mov     rax, [rbp+lpvObj]
0x18002ff99  test    rax, rax
0x18002ff9c  jz      short loc_18002FFDA
0x18002ff9e  mov     rdx, rdi; struct IStream *
0x18002ffa1  mov     rcx, rax; struct IUnknown *
0x18002ffa4  call    ?_AfxLoadObjectFromStreamedPropset@@YAHPEAUIUnknown@@PEAUIStream@@@Z; _AfxLoadObjectFromStreamedPropset(IUnknown *,IStream *)
0x18002ffa9  test    eax, eax
0x18002ffab  jnz     short loc_18002FFD6
0x18002ffad  lea     rcx, [rbp+lpvObj]; struct IUnknown **
0x18002ffb1  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18002ffb6  jmp     short loc_18002FF7B
0x18002ffb8  lea     r8, [rbp+lpvObj]; lplpvObj
0x18002ffbc  mov     rdx, rbx; riid
0x18002ffbf  lea     rcx, ?_afxFontDescHelv@@3UtagFONTDESC@@B; lpFontDesc
0x18002ffc6  call    cs:__imp_OleCreateFontIndirect
0x18002ffcc  jmp     short loc_18002FF91
0x18002ffce  xor     eax, eax
0x18002ffd0  mov     [rbp+lpvObj], rax
0x18002ffd4  jmp     short loc_18002FF99
0x18002ffd6  mov     rax, [rbp+lpvObj]
0x18002ffda  mov     rcx, [rbp+var_8]
0x18002ffde  xor     rcx, rsp; StackCookie
0x18002ffe1  call    __security_check_cookie
0x18002ffe6  mov     rbx, [rsp+50h+arg_10]
0x18002ffee  add     rsp, 50h
0x18002fff2  pop     rdi
0x18002fff3  pop     rsi
0x18002fff4  pop     rbp
0x18002fff5  retn
```
