# _GenerateXAddrsList

- ea: `0x140079d40`
- end: `0x14007a123`
- name: `_GenerateXAddrsList`
- size: `995`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140079428`

## callees

- `0x1400016b8`
- `0x1400033e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140079d40`
- `0x14007c3c4`
- `0x14007c7c0`
- `0x14007cbaa`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140079db7`
- `KERNEL32!IsDebuggerPresent` at `0x140079e90`
- `KERNEL32!IsDebuggerPresent` at `0x14007a054`
- `KERNEL32!IsDebuggerPresent` at `0x140079db7`
- `KERNEL32!IsDebuggerPresent` at `0x140079e90`
- `KERNEL32!IsDebuggerPresent` at `0x14007a054`
- `wsdapi!WSDAllocateLinkedMemory` at `0x140079e3e`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007a000`
- `wsdapi!WSDAllocateLinkedMemory` at `0x140079e3e`
- `wsdapi!WSDAllocateLinkedMemory` at `0x14007a000`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007a0ed`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007a0fb`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007a0ed`
- `wsdapi!WSDFreeLinkedMemory` at `0x14007a0fb`

## string_xrefs

- `0x140079d9f`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x140079e6a`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x14007a037`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x140079e71`: `pTempXAddrsList`
- `0x14007a018`: `pszTempXAddrs`
- `0x14007a05c`: `pszTempXAddrs`

## pseudocode

```c
__int64 __fastcall GenerateXAddrsList(wchar_t *String1, _QWORD *a2)
{
  wchar_t *v2; // r15
  unsigned __int16 *v5; // r13
  void *v6; // rsi
  int v7; // ebx
  const unsigned __int16 *v8; // r12
  unsigned int v9; // r14d
  _QWORD *v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  int WideStringHostName; // eax
  size_t v17; // rbp
  unsigned __int16 *v18; // rax
  unsigned __int16 *v20; // [rsp+80h] [rbp+8h] BYREF
  void *pVoid; // [rsp+90h] [rbp+18h] BYREF

  v2 = 0;
  v20 = 0;
  pVoid = 0;
  v5 = 0;
  v6 = 0;
  if ( !String1 )
  {
    v7 = -2147024809;
    v8 = L"pszEpr";
    v9 = 684;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147467261;
    v8 = L"ppXAddrsList";
    v9 = 685;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      v9,
      L"_GenerateXAddrsList",
      L"CBRAEx",
      v8,
      v7);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        v9,
        L"_GenerateXAddrsList",
        L"CBRAEx",
        v8,
        v7);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        v9,
        L"_GenerateXAddrsList",
        L"CBRAEx",
        v8,
        v7);
    goto LABEL_40;
  }
  *a2 = 0;
  v10 = WSDAllocateLinkedMemory(0, 0x10u);
  v11 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      0x2B2u,
      L"_GenerateXAddrsList",
      L"CPR",
      L"pTempXAddrsList",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        690,
        L"_GenerateXAddrsList",
        L"CPR",
        L"pTempXAddrsList",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        690,
        L"_GenerateXAddrsList",
        L"CPR",
        L"pTempXAddrsList",
        -2147024882);
    goto LABEL_40;
  }
  v10[1] = 0;
  *v10 = 0;
  v12 = -1;
  if ( !wcsncmp_0(String1, L"http://", 7u) || !wcsncmp_0(String1, L"https://", 8u) || !wcsncmp_0(String1, L"uri:", 4u) )
  {
    v15 = s_DeepCopyStringHelper(1, String1, v11, &pVoid);
    v6 = pVoid;
    v7 = v15;
    if ( v15 < 0 )
      goto LABEL_36;
  }
  else
  {
    v7 = 0;
    if ( !wcsncmp_0(String1, L"urn:uuid:", 9u) )
    {
      v13 = -1;
      do
        ++v13;
      while ( String1[v13] );
      if ( v13 != 45 )
      {
LABEL_19:
        v7 = -2147024809;
LABEL_39:
        WSDFreeLinkedMemory(v11);
        goto LABEL_40;
      }
      v2 = String1 + 9;
    }
    else
    {
      if ( wcsncmp_0(String1, L"uuid:", 5u) )
        goto LABEL_19;
      v14 = -1;
      do
        ++v14;
      while ( String1[v14] );
      if ( v14 != 41 )
        goto LABEL_19;
      v2 = String1 + 5;
    }
  }
  if ( !v2 )
  {
LABEL_35:
    v11[1] = v6;
    v6 = 0;
    *a2 = v11;
    v11 = 0;
    goto LABEL_36;
  }
  WideStringHostName = GetWideStringHostName(&v20);
  v5 = v20;
  v7 = WideStringHostName;
  if ( WideStringHostName < 0 )
    goto LABEL_36;
  do
    ++v12;
  while ( v20[v12] );
  v17 = 2 * v12 + 2;
  v18 = (unsigned __int16 *)WSDAllocateLinkedMemory(v11, v17);
  v6 = v18;
  if ( v18 )
  {
    v7 = StringCchPrintfW(v18, v17, L"%s", v5);
    if ( v7 < 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  v7 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
    0x309u,
    L"_GenerateXAddrsList",
    L"CPR",
    L"pszTempXAddrs",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      777,
      L"_GenerateXAddrsList",
      L"CPR",
      L"pszTempXAddrs",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      777,
      L"_GenerateXAddrsList",
      L"CPR",
      L"pszTempXAddrs",
      -2147024882);
LABEL_36:
  if ( v6 )
    WSDFreeLinkedMemory(v6);
  if ( v11 )
    goto LABEL_39;
LABEL_40:
  operator delete(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140079d40  mov     rax, rsp
0x140079d43  mov     [rax+10h], rbx
0x140079d47  push    rbp
0x140079d48  push    rsi
0x140079d49  push    rdi
0x140079d4a  push    r12
0x140079d4c  push    r13
0x140079d4e  push    r14
0x140079d50  push    r15
0x140079d52  sub     rsp, 40h
0x140079d56  xor     r15d, r15d
0x140079d59  mov     r12, rdx
0x140079d5c  mov     [rax+8], r15
0x140079d60  mov     rdi, rcx
0x140079d63  mov     [rax+18h], r15
0x140079d67  mov     r13d, r15d
0x140079d6a  mov     esi, r15d
0x140079d6d  test    rcx, rcx
0x140079d70  jnz     loc_140079E18
0x140079d76  mov     ebx, 80070057h
0x140079d7b  lea     r12, aPszepr; "pszEpr"
0x140079d82  mov     r14d, 2ACh
0x140079d88  lea     rsi, aCbraex; "CBRAEx"
0x140079d8f  mov     [rsp+78h+var_50], ebx; int
0x140079d93  lea     rbp, aGeneratexaddrs; "_GenerateXAddrsList"
0x140079d9a  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x140079d9f  lea     rdi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079da6  mov     r9, rsi; unsigned __int16 *
0x140079da9  mov     r8, rbp; unsigned __int16 *
0x140079dac  mov     rcx, rdi; unsigned __int16 *
0x140079daf  mov     edx, r14d; unsigned int
0x140079db2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140079db7  call    cs:__imp_IsDebuggerPresent
0x140079dbd  test    eax, eax
0x140079dbf  jz      short loc_140079DF0
0x140079dc1  mov     [rsp+78h+var_40], ebx
0x140079dc5  mov     r9d, r14d
0x140079dc8  mov     [rsp+78h+var_48], r12
0x140079dcd  mov     qword ptr [rsp+78h+var_50], rsi
0x140079dd2  mov     r8, rdi
0x140079dd5  mov     [rsp+78h+var_58], rbp
0x140079dda  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140079de1  mov     ecx, 2; unsigned __int8
0x140079de6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140079deb  jmp     loc_14007A101
0x140079df0  mov     dword ptr [rsp+78h+var_48], ebx
0x140079df4  mov     r8d, r14d
0x140079df7  mov     qword ptr [rsp+78h+var_50], r12
0x140079dfc  mov     [rsp+78h+var_58], rsi
0x140079e01  mov     r9, rbp
0x140079e04  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140079e0b  mov     rdx, rdi
0x140079e0e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140079e13  jmp     loc_14007A101
0x140079e18  test    r12, r12
0x140079e1b  jnz     short loc_140079E34
0x140079e1d  mov     ebx, 80004003h
0x140079e22  lea     r12, aPpxaddrslist; "ppXAddrsList"
0x140079e29  mov     r14d, 2ADh
0x140079e2f  jmp     loc_140079D88
0x140079e34  mov     [rdx], r15
0x140079e37  xor     ecx, ecx; pParent
0x140079e39  mov     edx, 10h; cbSize
0x140079e3e  call    cs:__imp_WSDAllocateLinkedMemory
0x140079e44  mov     r14, rax
0x140079e47  test    rax, rax
0x140079e4a  jnz     short loc_140079EC8
0x140079e4c  mov     r15d, 8007000Eh
0x140079e52  lea     r12, aCpr; "CPR"
0x140079e59  lea     rbp, aGeneratexaddrs; "_GenerateXAddrsList"
0x140079e60  mov     [rsp+78h+var_50], r15d; int
0x140079e65  mov     esi, 2B2h
0x140079e6a  lea     rdi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079e71  lea     r14, aPtempxaddrslis; "pTempXAddrsList"
0x140079e78  mov     r9, r12; unsigned __int16 *
0x140079e7b  mov     r8, rbp; unsigned __int16 *
0x140079e7e  mov     [rsp+78h+var_58], r14; unsigned __int16 *
0x140079e83  mov     edx, esi; unsigned int
0x140079e85  mov     rcx, rdi; unsigned __int16 *
0x140079e88  mov     ebx, r15d
0x140079e8b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140079e90  call    cs:__imp_IsDebuggerPresent
0x140079e96  test    eax, eax
0x140079e98  jz      short loc_140079EB1
0x140079e9a  mov     [rsp+78h+var_40], r15d
0x140079e9f  mov     r9d, esi
0x140079ea2  mov     [rsp+78h+var_48], r14
0x140079ea7  mov     qword ptr [rsp+78h+var_50], r12
0x140079eac  jmp     loc_140079DD2
0x140079eb1  mov     dword ptr [rsp+78h+var_48], r15d
0x140079eb6  mov     r8d, esi
0x140079eb9  mov     qword ptr [rsp+78h+var_50], r14
0x140079ebe  mov     [rsp+78h+var_58], r12
0x140079ec3  jmp     loc_140079E01
0x140079ec8  mov     r8d, 7; MaxCount
0x140079ece  mov     [rax+8], r15
0x140079ed2  lea     rdx, aHttp; "http://"
0x140079ed9  mov     [rax], r15
0x140079edc  mov     rcx, rdi; String1
0x140079edf  call    wcsncmp_0
0x140079ee4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140079ee8  test    eax, eax
0x140079eea  jz      loc_140079F93
0x140079ef0  lea     r8d, [rbp+9]; MaxCount
0x140079ef4  mov     rcx, rdi; String1
0x140079ef7  lea     rdx, aHttps; "https://"
0x140079efe  call    wcsncmp_0
0x140079f03  test    eax, eax
0x140079f05  jz      loc_140079F93
0x140079f0b  lea     r8d, [rbp+5]; MaxCount
0x140079f0f  mov     rcx, rdi; String1
0x140079f12  lea     rdx, aUri; "uri:"
0x140079f19  call    wcsncmp_0
0x140079f1e  test    eax, eax
0x140079f20  jz      short loc_140079F93
0x140079f22  lea     r8d, [rbp+0Ah]; MaxCount
0x140079f26  mov     rcx, rdi; String1
0x140079f29  lea     rdx, aUrnUuid; "urn:uuid:"
0x140079f30  mov     ebx, r15d
0x140079f33  call    wcsncmp_0
0x140079f38  test    eax, eax
0x140079f3a  jnz     short loc_140079F5F
0x140079f3c  mov     rax, rbp
0x140079f3f  inc     rax
0x140079f42  cmp     [rdi+rax*2], r15w
0x140079f47  jnz     short loc_140079F3F
0x140079f49  cmp     rax, 2Dh ; '-'
0x140079f4d  jz      short loc_140079F59
0x140079f4f  mov     ebx, 80070057h
0x140079f54  jmp     loc_14007A0F8
0x140079f59  lea     r15, [rdi+12h]
0x140079f5d  jmp     short loc_140079F8F
0x140079f5f  mov     r8d, 5; MaxCount
0x140079f65  lea     rdx, aUuid; "uuid:"
0x140079f6c  mov     rcx, rdi; String1
0x140079f6f  call    wcsncmp_0
0x140079f74  test    eax, eax
0x140079f76  jnz     short loc_140079F4F
0x140079f78  mov     rax, rbp
0x140079f7b  inc     rax
0x140079f7e  cmp     [rdi+rax*2], r15w
0x140079f83  jnz     short loc_140079F7B
0x140079f85  cmp     rax, 29h ; ')'
0x140079f89  jnz     short loc_140079F4F
0x140079f8b  lea     r15, [rdi+0Ah]
0x140079f8f  xor     edi, edi
0x140079f91  jmp     short loc_140079FBF
0x140079f93  lea     r9, [rsp+78h+pVoid]
0x140079f9b  mov     r8, r14
0x140079f9e  mov     rdx, rdi
0x140079fa1  mov     ecx, 1
0x140079fa6  call    s_DeepCopyStringHelper
0x140079fab  mov     rsi, [rsp+78h+pVoid]
0x140079fb3  xor     edi, edi
0x140079fb5  mov     ebx, eax
0x140079fb7  test    eax, eax
0x140079fb9  js      loc_14007A0E5
0x140079fbf  test    r15, r15
0x140079fc2  jz      loc_14007A0D7
0x140079fc8  lea     rcx, [rsp+78h+arg_0]; unsigned __int16 **
0x140079fd0  call    ?GetWideStringHostName@@YAJPEAPEAG@Z; GetWideStringHostName(ushort * *)
0x140079fd5  mov     r13, [rsp+78h+arg_0]
0x140079fdd  mov     ebx, eax
0x140079fdf  test    eax, eax
0x140079fe1  js      loc_14007A0E5
0x140079fe7  inc     rbp
0x140079fea  cmp     [r13+rbp*2+0], di
0x140079ff0  jnz     short loc_140079FE7
0x140079ff2  lea     rbp, ds:2[rbp*2]
0x140079ffa  mov     rcx, r14; pParent
0x140079ffd  mov     rdx, rbp; cbSize
0x14007a000  call    cs:__imp_WSDAllocateLinkedMemory
0x14007a006  mov     rsi, rax
0x14007a009  test    rax, rax
0x14007a00c  jnz     loc_14007A0BC
0x14007a012  mov     r15d, 8007000Eh
0x14007a018  lea     rax, aPsztempxaddrs; "pszTempXAddrs"
0x14007a01f  lea     r12, aCpr; "CPR"
0x14007a026  mov     [rsp+78h+var_50], r15d; int
0x14007a02b  lea     rbp, aGeneratexaddrs; "_GenerateXAddrsList"
0x14007a032  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x14007a037  lea     rdi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x14007a03e  mov     r9, r12; unsigned __int16 *
0x14007a041  mov     r8, rbp; unsigned __int16 *
0x14007a044  mov     rcx, rdi; unsigned __int16 *
0x14007a047  mov     edx, 309h; unsigned int
0x14007a04c  mov     ebx, r15d
0x14007a04f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007a054  call    cs:__imp_IsDebuggerPresent
0x14007a05a  test    eax, eax
0x14007a05c  lea     rax, aPsztempxaddrs; "pszTempXAddrs"
0x14007a063  jz      short loc_14007A093
0x14007a065  mov     [rsp+78h+var_40], r15d
0x14007a06a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007a071  mov     [rsp+78h+var_48], rax
0x14007a076  lea     ecx, [rsi+2]; unsigned __int8
0x14007a079  mov     qword ptr [rsp+78h+var_50], r12
0x14007a07e  mov     r9d, 309h
0x14007a084  mov     r8, rdi
0x14007a087  mov     [rsp+78h+var_58], rbp
0x14007a08c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007a091  jmp     short loc_14007A0E5
0x14007a093  mov     dword ptr [rsp+78h+var_48], r15d
0x14007a098  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007a09f  mov     qword ptr [rsp+78h+var_50], rax
0x14007a0a4  mov     r9, rbp
0x14007a0a7  mov     r8d, 309h
0x14007a0ad  mov     [rsp+78h+var_58], r12
0x14007a0b2  mov     rdx, rdi
0x14007a0b5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007a0ba  jmp     short loc_14007A0E5
0x14007a0bc  mov     r9, r13
0x14007a0bf  lea     r8, aS; "%s"
0x14007a0c6  mov     rdx, rbp; unsigned __int64
0x14007a0c9  mov     rcx, rax; unsigned __int16 *
0x14007a0cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007a0d1  mov     ebx, eax
0x14007a0d3  test    eax, eax
0x14007a0d5  js      short loc_14007A0E5
0x14007a0d7  mov     [r14+8], rsi
0x14007a0db  mov     rsi, rdi
0x14007a0de  mov     [r12], r14
0x14007a0e2  mov     r14, rdi
0x14007a0e5  test    rsi, rsi
0x14007a0e8  jz      short loc_14007A0F3
0x14007a0ea  mov     rcx, rsi; pVoid
0x14007a0ed  call    cs:__imp_WSDFreeLinkedMemory
0x14007a0f3  test    r14, r14
0x14007a0f6  jz      short loc_14007A101
0x14007a0f8  mov     rcx, r14; pVoid
0x14007a0fb  call    cs:__imp_WSDFreeLinkedMemory
0x14007a101  mov     rcx, r13; Block
0x14007a104  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007a109  mov     eax, ebx
0x14007a10b  mov     rbx, [rsp+78h+arg_8]
0x14007a113  add     rsp, 40h
0x14007a117  pop     r15
0x14007a119  pop     r14
0x14007a11b  pop     r13
0x14007a11d  pop     r12
0x14007a11f  pop     rdi
0x14007a120  pop     rsi
0x14007a121  pop     rbp
0x14007a122  retn
```
