# CIMRequestRAEvent::ExtractSalemTicket(ushort *)

- ea: `0x140013c10`
- end: `0x140013ef0`
- name: `?ExtractSalemTicket@CIMRequestRAEvent@@QEAAJPEAG@Z`
- size: `736`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x140004f74`
- `0x14000e6a0`
- `0x140011a4c`
- `0x140013c10`
- `0x140014f10`
- `0x140015240`
- `0x1400156c8`

## import_xrefs

- `ADVAPI32!CryptDestroyKey` at `0x140013e9a`
- `ADVAPI32!CryptDestroyKey` at `0x140013e9a`
- `ADVAPI32!CryptImportKey` at `0x140013d8d`
- `ADVAPI32!CryptImportKey` at `0x140013d8d`
- `ADVAPI32!CryptDecrypt` at `0x140013e29`
- `ADVAPI32!CryptDecrypt` at `0x140013e29`
- `KERNEL32!GetProcessHeap` at `0x140013ea5`
- `KERNEL32!GetProcessHeap` at `0x140013ec0`
- `KERNEL32!GetProcessHeap` at `0x140013ea5`
- `KERNEL32!GetProcessHeap` at `0x140013ec0`
- `KERNEL32!HeapFree` at `0x140013eb3`
- `KERNEL32!HeapFree` at `0x140013ecf`
- `KERNEL32!HeapFree` at `0x140013eb3`
- `KERNEL32!HeapFree` at `0x140013ecf`
- `msvcrt!free` at `0x140013dca`
- `msvcrt!free` at `0x140013e5e`
- `msvcrt!free` at `0x140013dca`
- `msvcrt!free` at `0x140013e5e`
- `OLEAUT32!__imp_SysStringLen` at `0x140013c78`
- `OLEAUT32!__imp_SysStringLen` at `0x140013cba`
- `OLEAUT32!__imp_SysStringLen` at `0x140013cd3`
- `OLEAUT32!__imp_SysStringLen` at `0x140013ddb`
- `OLEAUT32!__imp_SysStringLen` at `0x140013c78`
- `OLEAUT32!__imp_SysStringLen` at `0x140013cba`
- `OLEAUT32!__imp_SysStringLen` at `0x140013cd3`
- `OLEAUT32!__imp_SysStringLen` at `0x140013ddb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140013e44`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140013e44`

## string_xrefs

- `0x140013d48`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140013dac`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140013e80`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::ExtractSalemTicket(CIMRequestRAEvent *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  void *v5; // r15
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  unsigned __int16 **v8; // r14
  unsigned int v9; // r9d
  BSTR *v10; // rdi
  int PropertyValueFromBlob; // eax
  UINT v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  signed int v15; // eax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  unsigned int v18; // r9d
  BYTE *v19; // rdi
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  unsigned int v22; // r9d
  OLECHAR *v23; // rcx
  UINT v24; // eax
  unsigned __int16 *v25; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  BYTE *pbData; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-18h] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwDataLen; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwDataLen; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  dwDataLen = 0;
  pdwDataLen = 0;
  hKey = 0;
  pbData = 0;
  v5 = 0;
  lpMem = 0;
  v30 = 0;
  if ( !(unsigned int)GetPropertyValueFromBlob(a2, (wchar_t *)L"U", &v30) )
  {
    v9 = 640;
    goto LABEL_26;
  }
  v8 = (unsigned __int16 **)((char *)this + 104);
  ATL::CComBSTR::operator=((BSTR *)this + 13, v30);
  if ( !SysStringLen(*((BSTR *)this + 13)) )
  {
    v9 = 631;
LABEL_26:
    v2 = -2147024809;
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v9,
      L"CIMRequestRAEvent::ExtractSalemTicket",
      0x80070057);
    goto LABEL_27;
  }
  v10 = (BSTR *)((char *)this + 112);
  PropertyValueFromBlob = GetPropertyValueFromBlob(a2, (wchar_t *)L"S", (unsigned __int16 **)&lpMem);
  v5 = lpMem;
  if ( !PropertyValueFromBlob
    || (ATL::CComBSTR::operator=((BSTR *)this + 14, (const OLECHAR *)lpMem), !SysStringLen(*v10)) )
  {
    ATL::CComBSTR::operator=((OLECHAR **)this + 15, (CIMRequestRAEvent *)((char *)this + 104));
  }
  v12 = SysStringLen(*v10);
  dwDataLen = v12;
  if ( v12 )
  {
    if ( !*((_QWORD *)this + 7) )
    {
      v2 = -2147467261;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x2A5u,
        L"CIMRequestRAEvent::ExtractSalemTicket",
        0x80004003);
      goto LABEL_27;
    }
    if ( !*((_QWORD *)this + 8) )
    {
      v2 = -2147467261;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x2A6u,
        L"CIMRequestRAEvent::ExtractSalemTicket",
        0x80004003);
      goto LABEL_27;
    }
    v15 = CIMRequestRAEvent::StringToBinary((CIMRequestRAEvent *)&dwDataLen, *v10, v12, &pbData, &dwDataLen);
    v2 = v15;
    if ( v15 < 0 )
    {
      v18 = 684;
LABEL_14:
      CEventLogger::LogError(
        v17,
        v16,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        v18,
        L"CIMRequestRAEvent::ExtractSalemTicket",
        v15);
      v19 = pbData;
      goto LABEL_23;
    }
    v19 = pbData;
    if ( CryptImportKey(*((_QWORD *)this + 7), pbData, dwDataLen, *((_QWORD *)this + 8), 0, &hKey) )
    {
      free(v19);
      v23 = *v8;
      pbData = 0;
      v24 = SysStringLen(v23);
      v15 = CIMRequestRAEvent::StringToBinary((CIMRequestRAEvent *)&pdwDataLen, *v8, v24, &pbData, &pdwDataLen);
      v2 = v15;
      if ( v15 < 0 )
      {
        v18 = 704;
        goto LABEL_14;
      }
      v19 = pbData;
      if ( CryptDecrypt(hKey, 0, 1, 0, pbData, &pdwDataLen) )
      {
        v25 = SysAllocStringByteLen((LPCSTR)v19, pdwDataLen);
        ATL::CComBSTR::Attach((BSTR *)this + 15, v25);
LABEL_23:
        if ( v19 )
          free(v19);
        goto LABEL_27;
      }
      v22 = 712;
    }
    else
    {
      v22 = 692;
    }
    CEventLogger::LogError(
      v21,
      v20,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v22,
      L"CIMRequestRAEvent::ExtractSalemTicket",
      0);
    v2 = -2147467259;
    goto LABEL_23;
  }
LABEL_27:
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( v30 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v30);
  }
  return v2;
}

```

## disassembly

```asm
0x140013c10  mov     [rsp-28h+arg_0], rbx
0x140013c15  mov     [rsp-28h+arg_8], rsi
0x140013c1a  push    rbp
0x140013c1b  push    rdi
0x140013c1c  push    r12
0x140013c1e  push    r14
0x140013c20  push    r15
0x140013c22  mov     rbp, rsp
0x140013c25  sub     rsp, 50h
0x140013c29  xor     ebx, ebx
0x140013c2b  lea     r8, [rbp+var_18]; unsigned __int16 **
0x140013c2f  mov     r12, rdx
0x140013c32  mov     [rbp+dwDataLen], ebx
0x140013c35  mov     rsi, rcx
0x140013c38  mov     [rbp+pdwDataLen], ebx
0x140013c3b  mov     rcx, r12; String
0x140013c3e  mov     [rbp+hKey], rbx
0x140013c42  lea     rdx, aU; "U"
0x140013c49  mov     [rbp+pbData], rbx
0x140013c4d  mov     r15d, ebx
0x140013c50  mov     [rbp+lpMem], rbx
0x140013c54  mov     [rbp+var_18], rbx
0x140013c58  call    ?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z; GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)
0x140013c5d  test    eax, eax
0x140013c5f  jz      loc_140013E66
0x140013c65  mov     rdx, [rbp+var_18]
0x140013c69  lea     r14, [rsi+68h]
0x140013c6d  mov     rcx, r14
0x140013c70  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140013c75  mov     rcx, [r14]; pbstr
0x140013c78  call    cs:__imp_SysStringLen
0x140013c7e  test    eax, eax
0x140013c80  jnz     short loc_140013C8D
0x140013c82  mov     r9d, 277h
0x140013c88  jmp     loc_140013E6C
0x140013c8d  lea     r8, [rbp+lpMem]; unsigned __int16 **
0x140013c91  mov     rcx, r12; String
0x140013c94  lea     rdx, aS; "S"
0x140013c9b  lea     rdi, [rsi+70h]
0x140013c9f  call    ?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z; GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)
0x140013ca4  mov     r15, [rbp+lpMem]
0x140013ca8  test    eax, eax
0x140013caa  jz      short loc_140013CC4
0x140013cac  mov     rdx, r15
0x140013caf  mov     rcx, rdi
0x140013cb2  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140013cb7  mov     rcx, [rdi]; pbstr
0x140013cba  call    cs:__imp_SysStringLen
0x140013cc0  test    eax, eax
0x140013cc2  jnz     short loc_140013CD0
0x140013cc4  mov     rdx, r14
0x140013cc7  lea     rcx, [rsi+78h]
0x140013ccb  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x140013cd0  mov     rcx, [rdi]; pbstr
0x140013cd3  call    cs:__imp_SysStringLen
0x140013cd9  mov     [rbp+dwDataLen], eax
0x140013cdc  test    eax, eax
0x140013cde  jz      loc_140013E91
0x140013ce4  cmp     [rsi+38h], rbx
0x140013ce8  jnz     short loc_140013D02
0x140013cea  mov     ebx, 80004003h
0x140013cef  mov     dword ptr [rsp+50h+phKey], 80004003h
0x140013cf7  mov     r9d, 2A5h
0x140013cfd  jmp     loc_140013E79
0x140013d02  cmp     [rsi+40h], rbx
0x140013d06  jnz     short loc_140013D20
0x140013d08  mov     ebx, 80004003h
0x140013d0d  mov     dword ptr [rsp+50h+phKey], 80004003h
0x140013d15  mov     r9d, 2A6h
0x140013d1b  jmp     loc_140013E79
0x140013d20  mov     rdx, [rdi]; unsigned __int16 *
0x140013d23  lea     rcx, [rbp+dwDataLen]; this
0x140013d27  lea     r9, [rbp+pbData]; unsigned __int8 **
0x140013d2b  mov     qword ptr [rsp+50h+dwFlags], rcx; unsigned int *
0x140013d30  mov     r8d, eax; unsigned int
0x140013d33  call    ?StringToBinary@CIMRequestRAEvent@@QEAAJPEAGKPEAPEAEPEAK@Z; CIMRequestRAEvent::StringToBinary(ushort *,ulong,uchar * *,ulong *)
0x140013d38  mov     ebx, eax
0x140013d3a  test    eax, eax
0x140013d3c  jns     short loc_140013D69
0x140013d3e  mov     r9d, 2ACh; unsigned int
0x140013d44  mov     dword ptr [rsp+50h+phKey], eax; unsigned int
0x140013d48  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013d4f  lea     rax, aCimrequestraev_7; "CIMRequestRAEvent::ExtractSalemTicket"
0x140013d56  mov     qword ptr [rsp+50h+dwFlags], rax; unsigned __int16 *
0x140013d5b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013d60  mov     rdi, [rbp+pbData]
0x140013d64  jmp     loc_140013E56
0x140013d69  mov     rdi, [rbp+pbData]
0x140013d6d  lea     rax, [rbp+hKey]
0x140013d71  mov     r9, [rsi+40h]; hPubKey
0x140013d75  mov     rdx, rdi; pbData
0x140013d78  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x140013d7c  mov     rcx, [rsi+38h]; hProv
0x140013d80  mov     [rsp+50h+phKey], rax; phKey
0x140013d85  mov     [rsp+50h+dwFlags], 0; dwFlags
0x140013d8d  call    cs:__imp_CryptImportKey
0x140013d93  test    eax, eax
0x140013d95  jnz     short loc_140013DC7
0x140013d97  mov     r9d, 2B4h; unsigned int
0x140013d9d  lea     rax, aCimrequestraev_7; "CIMRequestRAEvent::ExtractSalemTicket"
0x140013da4  mov     dword ptr [rsp+50h+phKey], 0; unsigned int
0x140013dac  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013db3  mov     qword ptr [rsp+50h+dwFlags], rax; unsigned __int16 *
0x140013db8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013dbd  mov     ebx, 80004005h
0x140013dc2  jmp     loc_140013E56
0x140013dc7  mov     rcx, rdi; Block
0x140013dca  call    cs:__imp_free
0x140013dd0  mov     rcx, [r14]; pbstr
0x140013dd3  mov     [rbp+pbData], 0
0x140013ddb  call    cs:__imp_SysStringLen
0x140013de1  mov     rdx, [r14]; unsigned __int16 *
0x140013de4  lea     rcx, [rbp+pdwDataLen]; this
0x140013de8  mov     r8d, eax; unsigned int
0x140013deb  mov     qword ptr [rsp+50h+dwFlags], rcx; unsigned int *
0x140013df0  lea     r9, [rbp+pbData]; unsigned __int8 **
0x140013df4  call    ?StringToBinary@CIMRequestRAEvent@@QEAAJPEAGKPEAPEAEPEAK@Z; CIMRequestRAEvent::StringToBinary(ushort *,ulong,uchar * *,ulong *)
0x140013df9  mov     ebx, eax
0x140013dfb  test    eax, eax
0x140013dfd  jns     short loc_140013E0A
0x140013dff  mov     r9d, 2C0h
0x140013e05  jmp     loc_140013D44
0x140013e0a  mov     rdi, [rbp+pbData]
0x140013e0e  lea     rax, [rbp+pdwDataLen]
0x140013e12  mov     rcx, [rbp+hKey]; hKey
0x140013e16  xor     r9d, r9d; dwFlags
0x140013e19  mov     [rsp+50h+phKey], rax; pdwDataLen
0x140013e1e  xor     edx, edx; hHash
0x140013e20  mov     qword ptr [rsp+50h+dwFlags], rdi; pbData
0x140013e25  lea     r8d, [r9+1]; Final
0x140013e29  call    cs:__imp_CryptDecrypt
0x140013e2f  test    eax, eax
0x140013e31  jnz     short loc_140013E3E
0x140013e33  mov     r9d, 2C8h
0x140013e39  jmp     loc_140013D9D
0x140013e3e  mov     edx, [rbp+pdwDataLen]; len
0x140013e41  mov     rcx, rdi; psz
0x140013e44  call    cs:__imp_SysAllocStringByteLen
0x140013e4a  mov     rdx, rax; unsigned __int16 *
0x140013e4d  lea     rcx, [rsi+78h]; this
0x140013e51  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x140013e56  test    rdi, rdi
0x140013e59  jz      short loc_140013E91
0x140013e5b  mov     rcx, rdi; Block
0x140013e5e  call    cs:__imp_free
0x140013e64  jmp     short loc_140013E91
0x140013e66  mov     r9d, 280h; unsigned int
0x140013e6c  mov     dword ptr [rsp+50h+phKey], 80070057h; unsigned int
0x140013e74  mov     ebx, 80070057h
0x140013e79  lea     rax, aCimrequestraev_7; "CIMRequestRAEvent::ExtractSalemTicket"
0x140013e80  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013e87  mov     qword ptr [rsp+50h+dwFlags], rax; unsigned __int16 *
0x140013e8c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013e91  mov     rcx, [rbp+hKey]; hKey
0x140013e95  test    rcx, rcx
0x140013e98  jz      short loc_140013EA0
0x140013e9a  call    cs:__imp_CryptDestroyKey
0x140013ea0  test    r15, r15
0x140013ea3  jz      short loc_140013EB9
0x140013ea5  call    cs:__imp_GetProcessHeap
0x140013eab  mov     r8, r15; lpMem
0x140013eae  xor     edx, edx; dwFlags
0x140013eb0  mov     rcx, rax; hHeap
0x140013eb3  call    cs:__imp_HeapFree
0x140013eb9  cmp     [rbp+var_18], 0
0x140013ebe  jz      short loc_140013ED5
0x140013ec0  call    cs:__imp_GetProcessHeap
0x140013ec6  mov     r8, [rbp+var_18]; lpMem
0x140013eca  xor     edx, edx; dwFlags
0x140013ecc  mov     rcx, rax; hHeap
0x140013ecf  call    cs:__imp_HeapFree
0x140013ed5  lea     r11, [rsp+50h+var_s0]
0x140013eda  mov     eax, ebx
0x140013edc  mov     rbx, [r11+30h]
0x140013ee0  mov     rsi, [r11+38h]
0x140013ee4  mov     rsp, r11
0x140013ee7  pop     r15
0x140013ee9  pop     r14
0x140013eeb  pop     r12
0x140013eed  pop     rdi
0x140013eee  pop     rbp
0x140013eef  retn
```
