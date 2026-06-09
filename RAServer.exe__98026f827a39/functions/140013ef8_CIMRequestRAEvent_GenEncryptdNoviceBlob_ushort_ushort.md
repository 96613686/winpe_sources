# CIMRequestRAEvent::GenEncryptdNoviceBlob(ushort *,ushort * *)

- ea: `0x140013ef8`
- end: `0x14001437f`
- name: `?GenEncryptdNoviceBlob@CIMRequestRAEvent@@QEAAJPEAGPEAPEAG@Z`
- size: `1159`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140014a90`

## callees

- `0x140001fd6`
- `0x1400022d3`
- `0x14000aafc`
- `0x14000e6a0`
- `0x140011b74`
- `0x14001398c`
- `0x140013a88`
- `0x140013ef8`
- `0x140014388`
- `0x140014508`
- `0x140014f10`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x140014337`
- `ADVAPI32!CryptDestroyKey` at `0x140014346`
- `ADVAPI32!CryptDestroyKey` at `0x140014337`
- `ADVAPI32!CryptDestroyKey` at `0x140014346`
- `ADVAPI32!CryptGenKey` at `0x140014025`
- `ADVAPI32!CryptGenKey` at `0x140014025`
- `ADVAPI32!CryptImportKey` at `0x140013fe1`
- `ADVAPI32!CryptImportKey` at `0x140013fe1`
- `ADVAPI32!CryptEncrypt` at `0x1400140d3`
- `ADVAPI32!CryptEncrypt` at `0x140014178`
- `ADVAPI32!CryptEncrypt` at `0x1400140d3`
- `ADVAPI32!CryptEncrypt` at `0x140014178`
- `KERNEL32!GetLastError` at `0x140013feb`
- `KERNEL32!GetLastError` at `0x14001402f`
- `KERNEL32!GetLastError` at `0x1400140dd`
- `KERNEL32!GetLastError` at `0x140014185`
- `KERNEL32!GetLastError` at `0x140013feb`
- `KERNEL32!GetLastError` at `0x14001402f`
- `KERNEL32!GetLastError` at `0x1400140dd`
- `KERNEL32!GetLastError` at `0x140014185`
- `msvcrt!malloc` at `0x140014114`
- `msvcrt!malloc` at `0x140014114`
- `msvcrt!free` at `0x140014109`
- `msvcrt!free` at `0x14001430b`
- `msvcrt!free` at `0x140014109`
- `msvcrt!free` at `0x14001430b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001431a`
- `OLEAUT32!__imp_SysFreeString` at `0x140014328`
- `OLEAUT32!__imp_SysFreeString` at `0x140014350`
- `OLEAUT32!__imp_SysFreeString` at `0x14001431a`
- `OLEAUT32!__imp_SysFreeString` at `0x140014328`
- `OLEAUT32!__imp_SysFreeString` at `0x140014350`
- `OLEAUT32!__imp_SysStringLen` at `0x140013f6e`
- `OLEAUT32!__imp_SysStringLen` at `0x140013f6e`

## string_xrefs

- `0x140013fac`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x1400141de`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x1400142a4`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x1400142f7`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::GenEncryptdNoviceBlob(
        CIMRequestRAEvent *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v5; // r14
  OLECHAR *v6; // rbx
  int inited; // edi
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  BYTE *v11; // rsi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  unsigned __int64 *v15; // r12
  CIMRequestRAEvent *v16; // rcx
  signed int v17; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  signed int KeyExportString; // eax
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  CEventLogger *v22; // rcx
  __int64 v23; // rax
  unsigned __int64 dwBufLen; // rax
  signed int v25; // eax
  const struct _EVENT_DESCRIPTOR *v26; // rdx
  CEventLogger *v27; // rcx
  size_t v28; // rdi
  BYTE *v29; // rax
  const struct _EVENT_DESCRIPTOR *v30; // rdx
  CEventLogger *v31; // rcx
  CIMRequestRAEvent *v32; // rcx
  signed int v33; // eax
  const struct _EVENT_DESCRIPTOR *v34; // rdx
  CEventLogger *v35; // rcx
  signed int v36; // eax
  const struct _EVENT_DESCRIPTOR *v37; // rdx
  CEventLogger *v38; // rcx
  unsigned int v39; // r9d
  signed int v40; // eax
  const struct _EVENT_DESCRIPTOR *v41; // rdx
  CEventLogger *v42; // rcx
  signed int v43; // eax
  const struct _EVENT_DESCRIPTOR *v44; // rdx
  CEventLogger *v45; // rcx
  unsigned __int16 *v46; // rax
  HCRYPTKEY v47; // rcx
  HCRYPTKEY v48; // rcx
  DWORD pdwDataLen; // [rsp+40h] [rbp-79h] BYREF
  size_t Size; // [rsp+44h] [rbp-75h] BYREF
  BSTR v52; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v53; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v54; // [rsp+5Ch] [rbp-5Dh] BYREF
  unsigned __int16 *v55; // [rsp+60h] [rbp-59h] BYREF
  BYTE *pbData; // [rsp+68h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 **v58; // [rsp+78h] [rbp-41h]
  unsigned __int16 v59[40]; // [rsp+80h] [rbp-39h] BYREF

  v58 = a3;
  Size = 0;
  pdwDataLen = 0;
  v53 = 0;
  v54 = 0;
  pbData = 0;
  bstrString = 0;
  v5 = 0;
  v55 = 0;
  v6 = 0;
  v52 = 0;
  inited = CIMRequestRAEvent::InitCSP(this, 0);
  if ( inited < 0 )
    goto LABEL_50;
  HIDWORD(Size) = SysStringLen(*((BSTR *)this + 12));
  v8 = CIMRequestRAEvent::StringToBinary(
         (CIMRequestRAEvent *)((char *)&Size + 4),
         *((unsigned __int16 **)this + 12),
         HIDWORD(Size),
         &pbData,
         (unsigned int *)&Size + 1);
  inited = v8;
  if ( v8 >= 0 )
  {
    v11 = pbData;
    if ( !CryptImportKey(*((_QWORD *)this + 7), pbData, HIDWORD(Size), 0, 0, (HCRYPTKEY *)this + 8) )
    {
      LastError = GetLastError();
      inited = LastError;
      if ( LastError > 0 )
        inited = (unsigned __int16)LastError | 0x80070000;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x321u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        inited);
      goto LABEL_44;
    }
    v15 = (unsigned __int64 *)((char *)this + 72);
    if ( !CryptGenKey(*((_QWORD *)this + 7), 0x6602u, 1u, (HCRYPTKEY *)this + 9) )
    {
      v17 = GetLastError();
      inited = v17;
      if ( v17 > 0 )
        inited = (unsigned __int16)v17 | 0x80070000;
      CEventLogger::LogError(
        v19,
        v18,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x32Eu,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        inited);
      goto LABEL_44;
    }
    KeyExportString = CIMRequestRAEvent::GetKeyExportString(v16, *v15, *((_QWORD *)this + 8), 1u, &bstrString, &v53);
    inited = KeyExportString;
    if ( KeyExportString < 0 )
    {
      CEventLogger::LogError(
        v22,
        v21,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x338u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        KeyExportString);
      goto LABEL_44;
    }
    v23 = -1;
    do
      ++v23;
    while ( a2[v23] );
    dwBufLen = 2 * v23;
    if ( dwBufLen > 0xFFFFFFFF )
    {
      LODWORD(Size) = -1;
      inited = -2147024362;
      CEventLogger::LogError(
        (CEventLogger *)0xFFFFFFFFLL,
        v21,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x342u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        0x80070216);
      goto LABEL_44;
    }
    LODWORD(Size) = dwBufLen;
    pdwDataLen = dwBufLen;
    if ( !CryptEncrypt(*v15, 0, 1, 0, 0, &pdwDataLen, dwBufLen) )
    {
      v25 = GetLastError();
      inited = v25;
      if ( v25 > 0 )
        inited = (unsigned __int16)v25 | 0x80070000;
      CEventLogger::LogError(
        v27,
        v26,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x350u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        inited);
      goto LABEL_44;
    }
    if ( v11 )
      free(v11);
    v28 = pdwDataLen;
    v29 = (BYTE *)malloc(pdwDataLen);
    v11 = v29;
    if ( !v29 )
    {
      inited = -2147024882;
      CEventLogger::LogError(
        v31,
        v30,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x359u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        0x8007000E);
      goto LABEL_44;
    }
    memset_0(v29, 0, v28);
    memcpy_0(v11, a2, (unsigned int)Size);
    if ( !CryptEncrypt(*v15, 0, 1, 0, v11, (DWORD *)&Size, pdwDataLen) )
    {
      v33 = GetLastError();
      inited = v33;
      if ( v33 > 0 )
        inited = (unsigned __int16)v33 | 0x80070000;
      CEventLogger::LogError(
        v35,
        v34,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x368u,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        inited);
      goto LABEL_44;
    }
    v36 = CIMRequestRAEvent::BinaryToString(v32, v11, pdwDataLen, &v55, &v54);
    inited = v36;
    if ( v36 < 0 )
    {
      v39 = 879;
LABEL_31:
      CEventLogger::LogError(
        v38,
        v37,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        v39,
        L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
        v36);
      v5 = v55;
      goto LABEL_44;
    }
    if ( v53 )
    {
      v36 = StringCchPrintfW(v59, 0x28u, L"%d;S=", v53 + 2);
      inited = v36;
      if ( v36 < 0 )
      {
        v39 = 890;
        goto LABEL_31;
      }
      ATL::CComBSTR::operator=(&v52, v59);
      ATL::CComBSTR::AppendBSTR(&v52, bstrString);
      v6 = v52;
    }
    v5 = v55;
    if ( v54 )
    {
      v40 = StringCchPrintfW(v59, 0x28u, L"%d;U=", v54 + 2);
      inited = v40;
      if ( v40 < 0 )
      {
        CEventLogger::LogError(
          v42,
          v41,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0x38Cu,
          L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
          v40);
        goto LABEL_44;
      }
      v43 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v52, v59);
      inited = v43;
      if ( v43 < 0 )
      {
        CEventLogger::LogError(
          v45,
          v44,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0x392u,
          L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
          v43);
        v6 = v52;
        goto LABEL_44;
      }
      ATL::CComBSTR::AppendBSTR(&v52, v5);
      v6 = v52;
    }
    v46 = v6;
    v6 = 0;
    *v58 = v46;
    goto LABEL_44;
  }
  CEventLogger::LogError(
    v10,
    v9,
    L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
    0x316u,
    L"CIMRequestRAEvent::GenEncryptdNoviceBlob",
    v8);
  v11 = pbData;
LABEL_44:
  if ( v11 )
    free(v11);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v5 )
    SysFreeString(v5);
LABEL_50:
  v47 = *((_QWORD *)this + 8);
  if ( v47 )
    CryptDestroyKey(v47);
  v48 = *((_QWORD *)this + 9);
  if ( v48 )
    CryptDestroyKey(v48);
  SysFreeString(v6);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140013ef8  mov     [rsp-8+arg_18], rbx
0x140013efd  push    rbp
0x140013efe  push    rsi
0x140013eff  push    rdi
0x140013f00  push    r12
0x140013f02  push    r13
0x140013f04  push    r14
0x140013f06  push    r15
0x140013f08  lea     rbp, [rsp-27h]
0x140013f0d  sub     rsp, 0E0h
0x140013f14  mov     rax, cs:__security_cookie
0x140013f1b  xor     rax, rsp
0x140013f1e  mov     [rbp+57h+var_40], rax
0x140013f22  mov     [rbp+57h+var_98], r8
0x140013f26  mov     r13, rdx
0x140013f29  mov     r15, rcx
0x140013f2c  xor     r12d, r12d
0x140013f2f  mov     dword ptr [rbp+57h+Size], r12d
0x140013f33  mov     [rbp+57h+pdwDataLen], r12d
0x140013f37  mov     [rbp+57h+var_B8], r12d
0x140013f3b  mov     [rbp+57h+var_B4], r12d
0x140013f3f  mov     [rbp+57h+pbData], r12
0x140013f43  mov     [rbp+57h+bstrString], r12
0x140013f47  mov     r14d, r12d
0x140013f4a  mov     [rbp+57h+var_B0], r12
0x140013f4e  mov     ebx, r12d
0x140013f51  mov     [rbp+57h+var_C0], rbx
0x140013f55  mov     dword ptr [rbp+57h+Size+4], r12d
0x140013f59  xor     edx, edx; int
0x140013f5b  call    ?InitCSP@CIMRequestRAEvent@@QEAAJH@Z; CIMRequestRAEvent::InitCSP(int)
0x140013f60  mov     edi, eax
0x140013f62  test    eax, eax
0x140013f64  js      loc_14001432E
0x140013f6a  mov     rcx, [r15+60h]; pbstr
0x140013f6e  call    cs:__imp_SysStringLen
0x140013f74  mov     dword ptr [rbp+57h+Size+4], eax
0x140013f77  lea     rcx, [rbp+57h+Size+4]; this
0x140013f7b  mov     qword ptr [rsp+110h+dwFlags], rcx; unsigned int *
0x140013f80  lea     r9, [rbp+57h+pbData]; unsigned __int8 **
0x140013f84  mov     r8d, eax; unsigned int
0x140013f87  mov     rdx, [r15+60h]; unsigned __int16 *
0x140013f8b  call    ?StringToBinary@CIMRequestRAEvent@@QEAAJPEAGKPEAPEAEPEAK@Z; CIMRequestRAEvent::StringToBinary(ushort *,ulong,uchar * *,ulong *)
0x140013f90  mov     edi, eax
0x140013f92  test    eax, eax
0x140013f94  jns     short loc_140013FC1
0x140013f96  mov     dword ptr [rsp+110h+phKey], eax; unsigned int
0x140013f9a  lea     rax, aCimrequestraev_4; "CIMRequestRAEvent::GenEncryptdNoviceBlo"...
0x140013fa1  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned __int16 *
0x140013fa6  mov     r9d, 316h; unsigned int
0x140013fac  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013fb3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013fb8  mov     rsi, [rbp+57h+pbData]
0x140013fbc  jmp     loc_140014303
0x140013fc1  lea     rdi, [r15+40h]
0x140013fc5  mov     [rsp+110h+phKey], rdi; phKey
0x140013fca  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x140013fcf  xor     r9d, r9d; hPubKey
0x140013fd2  mov     r8d, dword ptr [rbp+57h+Size+4]; dwDataLen
0x140013fd6  mov     rsi, [rbp+57h+pbData]
0x140013fda  mov     rdx, rsi; pbData
0x140013fdd  mov     rcx, [r15+38h]; hProv
0x140013fe1  call    cs:__imp_CryptImportKey
0x140013fe7  test    eax, eax
0x140013fe9  jnz     short loc_14001400F
0x140013feb  call    cs:__imp_GetLastError
0x140013ff1  mov     edi, eax
0x140013ff3  test    eax, eax
0x140013ff5  jle     short loc_140014000
0x140013ff7  movzx   edi, ax
0x140013ffa  or      edi, 80070000h
0x140014000  mov     dword ptr [rsp+110h+phKey], edi
0x140014004  mov     r9d, 321h
0x14001400a  jmp     loc_1400142EB
0x14001400f  lea     r12, [r15+48h]
0x140014013  mov     r9, r12; phKey
0x140014016  mov     edx, 6602h; Algid
0x14001401b  mov     r8d, 1; dwFlags
0x140014021  mov     rcx, [r15+38h]; hProv
0x140014025  call    cs:__imp_CryptGenKey
0x14001402b  test    eax, eax
0x14001402d  jnz     short loc_140014053
0x14001402f  call    cs:__imp_GetLastError
0x140014035  mov     edi, eax
0x140014037  test    eax, eax
0x140014039  jle     short loc_140014044
0x14001403b  movzx   edi, ax
0x14001403e  or      edi, 80070000h
0x140014044  mov     dword ptr [rsp+110h+phKey], edi
0x140014048  mov     r9d, 32Eh
0x14001404e  jmp     loc_1400142EB
0x140014053  lea     rax, [rbp+57h+var_B8]
0x140014057  mov     [rsp+110h+phKey], rax; unsigned int *
0x14001405c  lea     rax, [rbp+57h+bstrString]
0x140014060  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned __int16 **
0x140014065  mov     r9d, 1; unsigned int
0x14001406b  mov     r8, [rdi]; unsigned __int64
0x14001406e  mov     rdx, [r12]; unsigned __int64
0x140014072  call    ?GetKeyExportString@CIMRequestRAEvent@@QEAAJ_K0KPEAPEAGPEAK@Z; CIMRequestRAEvent::GetKeyExportString(unsigned __int64,unsigned __int64,ulong,ushort * *,ulong *)
0x140014077  mov     edi, eax
0x140014079  test    eax, eax
0x14001407b  jns     short loc_14001408C
0x14001407d  mov     dword ptr [rsp+110h+phKey], eax
0x140014081  mov     r9d, 338h
0x140014087  jmp     loc_1400142EB
0x14001408c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014090  xor     edi, edi
0x140014092  inc     rax
0x140014095  cmp     [r13+rax*2+0], di
0x14001409b  jnz     short loc_140014092
0x14001409d  add     rax, rax
0x1400140a0  mov     ecx, 0FFFFFFFFh; this
0x1400140a5  cmp     rax, rcx
0x1400140a8  ja      loc_1400142D5
0x1400140ae  mov     dword ptr [rbp+57h+Size], eax
0x1400140b1  mov     [rbp+57h+pdwDataLen], eax
0x1400140b4  mov     [rsp+110h+dwBufLen], eax; dwBufLen
0x1400140b8  lea     rax, [rbp+57h+pdwDataLen]
0x1400140bc  mov     [rsp+110h+phKey], rax; pdwDataLen
0x1400140c1  mov     qword ptr [rsp+110h+dwFlags], rdi; pbData
0x1400140c6  xor     r9d, r9d; dwFlags
0x1400140c9  xor     edx, edx; hHash
0x1400140cb  lea     r8d, [r9+1]; Final
0x1400140cf  mov     rcx, [r12]; hKey
0x1400140d3  call    cs:__imp_CryptEncrypt
0x1400140d9  test    eax, eax
0x1400140db  jnz     short loc_140014101
0x1400140dd  call    cs:__imp_GetLastError
0x1400140e3  mov     edi, eax
0x1400140e5  test    eax, eax
0x1400140e7  jle     short loc_1400140F2
0x1400140e9  movzx   edi, ax
0x1400140ec  or      edi, 80070000h
0x1400140f2  mov     dword ptr [rsp+110h+phKey], edi
0x1400140f6  mov     r9d, 350h
0x1400140fc  jmp     loc_1400142EB
0x140014101  test    rsi, rsi
0x140014104  jz      short loc_14001410F
0x140014106  mov     rcx, rsi; Block
0x140014109  call    cs:__imp_free
0x14001410f  mov     edi, [rbp+57h+pdwDataLen]
0x140014112  mov     ecx, edi; Size
0x140014114  call    cs:__imp_malloc
0x14001411a  mov     rsi, rax
0x14001411d  test    rax, rax
0x140014120  jnz     short loc_14001413A
0x140014122  mov     edi, 8007000Eh
0x140014127  mov     dword ptr [rsp+110h+phKey], 8007000Eh
0x14001412f  mov     r9d, 359h
0x140014135  jmp     loc_1400142EB
0x14001413a  mov     r8, rdi; Size
0x14001413d  xor     edx, edx; Val
0x14001413f  mov     rcx, rsi; void *
0x140014142  call    memset_0
0x140014147  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x14001414b  mov     rdx, r13; Src
0x14001414e  mov     rcx, rsi; void *
0x140014151  call    memcpy_0
0x140014156  mov     eax, [rbp+57h+pdwDataLen]
0x140014159  mov     [rsp+110h+dwBufLen], eax; dwBufLen
0x14001415d  lea     rax, [rbp+57h+Size]
0x140014161  mov     [rsp+110h+phKey], rax; pdwDataLen
0x140014166  mov     qword ptr [rsp+110h+dwFlags], rsi; pbData
0x14001416b  xor     r9d, r9d; dwFlags
0x14001416e  xor     edx, edx; hHash
0x140014170  lea     r8d, [r9+1]; Final
0x140014174  mov     rcx, [r12]; hKey
0x140014178  call    cs:__imp_CryptEncrypt
0x14001417e  xor     r12d, r12d
0x140014181  test    eax, eax
0x140014183  jnz     short loc_1400141A9
0x140014185  call    cs:__imp_GetLastError
0x14001418b  mov     edi, eax
0x14001418d  test    eax, eax
0x14001418f  jle     short loc_14001419A
0x140014191  movzx   edi, ax
0x140014194  or      edi, 80070000h
0x14001419a  mov     dword ptr [rsp+110h+phKey], edi
0x14001419e  mov     r9d, 368h
0x1400141a4  jmp     loc_1400142EB
0x1400141a9  lea     rax, [rbp+57h+var_B4]
0x1400141ad  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned int *
0x1400141b2  lea     r9, [rbp+57h+var_B0]; unsigned __int16 **
0x1400141b6  mov     r8d, [rbp+57h+pdwDataLen]; unsigned int
0x1400141ba  mov     rdx, rsi; unsigned __int8 *
0x1400141bd  call    ?BinaryToString@CIMRequestRAEvent@@QEAAJPEAEKPEAPEAGPEAK@Z; CIMRequestRAEvent::BinaryToString(uchar *,ulong,ushort * *,ulong *)
0x1400141c2  mov     edi, eax
0x1400141c4  test    eax, eax
0x1400141c6  jns     short loc_1400141F3
0x1400141c8  mov     r9d, 36Fh; unsigned int
0x1400141ce  mov     dword ptr [rsp+110h+phKey], eax; unsigned int
0x1400141d2  lea     rax, aCimrequestraev_4; "CIMRequestRAEvent::GenEncryptdNoviceBlo"...
0x1400141d9  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned __int16 *
0x1400141de  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400141e5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400141ea  mov     r14, [rbp+57h+var_B0]
0x1400141ee  jmp     loc_140014303
0x1400141f3  mov     r13d, 28h ; '('
0x1400141f9  mov     r9d, [rbp+57h+var_B8]
0x1400141fd  test    r9d, r9d
0x140014200  jz      short loc_140014245
0x140014202  add     r9d, 2
0x140014206  lea     r8, aDS; "%d;S="
0x14001420d  mov     edx, r13d; unsigned __int64
0x140014210  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x140014214  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014219  mov     edi, eax
0x14001421b  test    eax, eax
0x14001421d  jns     short loc_140014227
0x14001421f  mov     r9d, 37Ah
0x140014225  jmp     short loc_1400141CE
0x140014227  lea     rdx, [rbp+57h+var_90]
0x14001422b  lea     rcx, [rbp+57h+var_C0]
0x14001422f  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140014234  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x140014238  lea     rcx, [rbp+57h+var_C0]; this
0x14001423c  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x140014241  mov     rbx, [rbp+57h+var_C0]
0x140014245  mov     r14, [rbp+57h+var_B0]
0x140014249  mov     r9d, [rbp+57h+var_B4]
0x14001424d  test    r9d, r9d
0x140014250  jz      short loc_1400142C6
0x140014252  add     r9d, 2
0x140014256  lea     r8, aDU; "%d;U="
0x14001425d  mov     rdx, r13; unsigned __int64
0x140014260  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x140014264  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014269  mov     edi, eax
0x14001426b  test    eax, eax
0x14001426d  jns     short loc_14001427B
0x14001426f  mov     dword ptr [rsp+110h+phKey], eax
0x140014273  mov     r9d, 38Ch
0x140014279  jmp     short loc_1400142EB
0x14001427b  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001427f  lea     rcx, [rbp+57h+var_C0]; this
0x140014283  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140014288  mov     edi, eax
0x14001428a  test    eax, eax
0x14001428c  jns     short loc_1400142B6
0x14001428e  mov     dword ptr [rsp+110h+phKey], eax; unsigned int
0x140014292  lea     rax, aCimrequestraev_4; "CIMRequestRAEvent::GenEncryptdNoviceBlo"...
0x140014299  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned __int16 *
0x14001429e  mov     r9d, 392h; unsigned int
0x1400142a4  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400142ab  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400142b0  mov     rbx, [rbp+57h+var_C0]
0x1400142b4  jmp     short loc_140014303
0x1400142b6  mov     rdx, r14; unsigned __int16 *
0x1400142b9  lea     rcx, [rbp+57h+var_C0]; this
0x1400142bd  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x1400142c2  mov     rbx, [rbp+57h+var_C0]
0x1400142c6  mov     rax, rbx
0x1400142c9  mov     rbx, r12
0x1400142cc  mov     rcx, [rbp+57h+var_98]
0x1400142d0  mov     [rcx], rax
0x1400142d3  jmp     short loc_140014303
0x1400142d5  mov     dword ptr [rbp+57h+Size], ecx
0x1400142d8  mov     edi, 80070216h
0x1400142dd  mov     dword ptr [rsp+110h+phKey], 80070216h; unsigned int
0x1400142e5  mov     r9d, 342h; unsigned int
0x1400142eb  lea     rax, aCimrequestraev_4; "CIMRequestRAEvent::GenEncryptdNoviceBlo"...
0x1400142f2  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned __int16 *
0x1400142f7  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400142fe  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014303  test    rsi, rsi
0x140014306  jz      short loc_140014311
0x140014308  mov     rcx, rsi; Block
0x14001430b  call    cs:__imp_free
0x140014311  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140014315  test    rcx, rcx
0x140014318  jz      short loc_140014320
0x14001431a  call    cs:__imp_SysFreeString
0x140014320  test    r14, r14
0x140014323  jz      short loc_14001432E
0x140014325  mov     rcx, r14; bstrString
0x140014328  call    cs:__imp_SysFreeString
0x14001432e  mov     rcx, [r15+40h]; hKey
0x140014332  test    rcx, rcx
0x140014335  jz      short loc_14001433D
0x140014337  call    cs:__imp_CryptDestroyKey
0x14001433d  mov     rcx, [r15+48h]; hKey
0x140014341  test    rcx, rcx
0x140014344  jz      short loc_14001434D
0x140014346  call    cs:__imp_CryptDestroyKey
0x14001434c  nop
0x14001434d  mov     rcx, rbx; bstrString
0x140014350  call    cs:__imp_SysFreeString
0x140014356  mov     eax, edi
0x140014358  mov     rcx, [rbp+57h+var_40]
0x14001435c  xor     rcx, rsp; StackCookie
0x14001435f  call    __security_check_cookie
0x140014364  mov     rbx, [rsp+110h+arg_18]
0x14001436c  add     rsp, 0E0h
0x140014373  pop     r15
0x140014375  pop     r14
0x140014377  pop     r13
0x140014379  pop     r12
0x14001437b  pop     rdi
0x14001437c  pop     rsi
0x14001437d  pop     rbp
0x14001437e  retn
  ... truncated ...
```
