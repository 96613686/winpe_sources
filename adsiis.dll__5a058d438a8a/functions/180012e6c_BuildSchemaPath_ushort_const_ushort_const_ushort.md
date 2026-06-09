# BuildSchemaPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180012e6c`
- end: `0x180012fc2`
- name: `?BuildSchemaPath@@YAJPEBG0PEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *Source, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800148a0`

## callees

- `0x180012e6c`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001beb8`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180012f2f`
- `msvcrt!swprintf_s` at `0x180012f2f`
- `msvcrt!wcscat_s` at `0x180012f44`
- `msvcrt!wcscat_s` at `0x180012f5b`
- `msvcrt!wcscat_s` at `0x180012f6e`
- `msvcrt!wcscat_s` at `0x180012f44`
- `msvcrt!wcscat_s` at `0x180012f5b`
- `msvcrt!wcscat_s` at `0x180012f6e`
- `msvcrt!wcscpy_s` at `0x180012ee9`
- `msvcrt!wcscpy_s` at `0x180012ee9`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180012f94`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180012f94`

## pseudocode

```c
__int64 __fastcall BuildSchemaPath(const unsigned __int16 *a1, wchar_t *Source, unsigned __int16 **a3)
{
  int v6; // ebx
  _BYTE v8[8]; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR pStr; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Sourcea; // [rsp+48h] [rbp-B8h]
  wchar_t Destination[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(&v10, 0, 0x230u);
  CLexer::CLexer((CLexer *)v8, a1);
  memset_0(&v10, 0, 0x230u);
  wcscpy_s(Destination, 0x104u, &psz);
  if ( !Source || !*Source )
  {
LABEL_6:
    v6 = ADsAllocString(Destination, a3);
    goto LABEL_7;
  }
  v6 = ADsObject((struct CLexer *)v8, (struct _objectinfo *)&v10);
  if ( v6 >= 0 )
  {
    if ( Sourcea )
    {
      swprintf_s(Destination, 0x104u, L"%s://", v10);
      wcscat_s(Destination, 0x104u, Sourcea);
      wcscat_s(Destination, 0x104u, L"/schema/");
      wcscat_s(Destination, 0x104u, Source);
    }
    goto LABEL_6;
  }
LABEL_7:
  FreeObjectInfo((struct _objectinfo *)&v10);
  FreeADsStr(pStr);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012e6c  mov     [rsp-8+arg_18], rbx
0x180012e71  push    rbp
0x180012e72  push    rsi
0x180012e73  push    rdi
0x180012e74  push    r14
0x180012e76  push    r15
0x180012e78  lea     rbp, [rsp-390h]
0x180012e80  sub     rsp, 490h
0x180012e87  mov     rax, cs:__security_cookie
0x180012e8e  xor     rax, rsp
0x180012e91  mov     [rbp+3B0h+var_30], rax
0x180012e98  mov     rsi, r8
0x180012e9b  mov     rdi, rdx
0x180012e9e  mov     rbx, rcx
0x180012ea1  mov     r14d, 230h
0x180012ea7  mov     r8d, r14d; Size
0x180012eaa  lea     rcx, [rsp+4B0h+var_470]; void *
0x180012eaf  xor     edx, edx; Val
0x180012eb1  call    memset_0
0x180012eb6  mov     rdx, rbx; unsigned __int16 *
0x180012eb9  lea     rcx, [rsp+4B0h+var_490]; this
0x180012ebe  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180012ec3  mov     r8d, r14d; Size
0x180012ec6  lea     rcx, [rsp+4B0h+var_470]; void *
0x180012ecb  xor     edx, edx; Val
0x180012ecd  call    memset_0
0x180012ed2  mov     r15d, 104h
0x180012ed8  lea     r8, psz; Source
0x180012edf  mov     edx, r15d; SizeInWords
0x180012ee2  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180012ee9  call    cs:__imp_wcscpy_s
0x180012eef  xor     r14d, r14d
0x180012ef2  test    rdi, rdi
0x180012ef5  jz      short loc_180012F74
0x180012ef7  cmp     [rdi], r14w
0x180012efb  jz      short loc_180012F74
0x180012efd  lea     rdx, [rsp+4B0h+var_470]; struct _objectinfo *
0x180012f02  lea     rcx, [rsp+4B0h+var_490]; struct CLexer *
0x180012f07  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180012f0c  mov     ebx, eax
0x180012f0e  test    eax, eax
0x180012f10  js      short loc_180012F85
0x180012f12  cmp     [rsp+4B0h+Source], r14
0x180012f17  jz      short loc_180012F74
0x180012f19  mov     r9, [rsp+4B0h+var_470]
0x180012f1e  lea     r8, aS; "%s://"
0x180012f25  mov     edx, r15d; BufferCount
0x180012f28  lea     rcx, [rbp+3B0h+Destination]; Buffer
0x180012f2f  call    cs:__imp_swprintf_s
0x180012f35  mov     r8, [rsp+4B0h+Source]; Source
0x180012f3a  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180012f41  mov     edx, r15d; SizeInWords
0x180012f44  call    cs:__imp_wcscat_s
0x180012f4a  lea     r8, aSchema; "/schema/"
0x180012f51  mov     edx, r15d; SizeInWords
0x180012f54  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180012f5b  call    cs:__imp_wcscat_s
0x180012f61  mov     r8, rdi; Source
0x180012f64  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180012f6b  mov     edx, r15d; SizeInWords
0x180012f6e  call    cs:__imp_wcscat_s
0x180012f74  mov     rdx, rsi
0x180012f77  lea     rcx, [rbp+3B0h+Destination]
0x180012f7e  call    ADsAllocString
0x180012f83  mov     ebx, eax
0x180012f85  lea     rcx, [rsp+4B0h+var_470]; struct _objectinfo *
0x180012f8a  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180012f8f  mov     rcx, [rsp+4B0h+pStr]; pStr
0x180012f94  call    cs:__imp_FreeADsStr
0x180012f9a  mov     eax, ebx
0x180012f9c  mov     rcx, [rbp+3B0h+var_30]
0x180012fa3  xor     rcx, rsp; StackCookie
0x180012fa6  call    __security_check_cookie
0x180012fab  mov     rbx, [rsp+4B0h+arg_18]
0x180012fb3  add     rsp, 490h
0x180012fba  pop     r15
0x180012fbc  pop     r14
0x180012fbe  pop     rdi
0x180012fbf  pop     rsi
0x180012fc0  pop     rbp
0x180012fc1  retn
```
