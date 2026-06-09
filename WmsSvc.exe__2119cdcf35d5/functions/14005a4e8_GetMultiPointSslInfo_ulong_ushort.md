# GetMultiPointSslInfo(ulong *,ushort * *)

- ea: `0x14005a4e8`
- end: `0x14005a884`
- name: `?GetMultiPointSslInfo@@YAJPEAKPEAPEAG@Z`
- size: `924`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000308c`
- `0x140023030`
- `0x140026298`
- `0x140048fa8`
- `0x140059214`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005a4e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14005a540`
- `ADVAPI32!RegOpenKeyExW` at `0x14005a540`
- `ADVAPI32!RegGetValueW` at `0x14005a62b`
- `ADVAPI32!RegGetValueW` at `0x14005a6c7`
- `ADVAPI32!RegGetValueW` at `0x14005a82c`
- `ADVAPI32!RegGetValueW` at `0x14005a62b`
- `ADVAPI32!RegGetValueW` at `0x14005a6c7`
- `ADVAPI32!RegGetValueW` at `0x14005a82c`
- `ADVAPI32!RegCloseKey` at `0x14005a863`
- `ADVAPI32!RegCloseKey` at `0x14005a863`
- `KERNEL32!IsDebuggerPresent` at `0x14005a593`
- `KERNEL32!IsDebuggerPresent` at `0x14005a67a`
- `KERNEL32!IsDebuggerPresent` at `0x14005a727`
- `KERNEL32!IsDebuggerPresent` at `0x14005a7ba`
- `KERNEL32!IsDebuggerPresent` at `0x14005a593`
- `KERNEL32!IsDebuggerPresent` at `0x14005a67a`
- `KERNEL32!IsDebuggerPresent` at `0x14005a727`
- `KERNEL32!IsDebuggerPresent` at `0x14005a7ba`

## string_xrefs

- `0x14005a570`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a657`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a710`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a79e`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c
__int64 __fastcall GetMultiPointSslInfo(unsigned int *a1, unsigned __int16 **a2)
{
  void *v4; // r15
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS ValueW; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  unsigned int v12; // eax
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *pvDataa; // [rsp+28h] [rbp-28h]
  LPDWORD pcbData; // [rsp+30h] [rbp-20h]
  const unsigned __int16 *pcbDataa; // [rsp+30h] [rbp-20h]
  int v18; // [rsp+38h] [rbp-18h]
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  DWORD v20; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+48h] BYREF

  hkey = 0;
  v21 = 0;
  v20 = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
         0,
         0x20019u,
         &hkey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x1B7u,
      L"GetMultiPointSslInfo",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v7 = 439;
LABEL_6:
      v18 = v6;
      pcbDataa = L"lr == 0L";
      pvData = L"CBRAEx";
LABEL_7:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        v7,
        L"GetMultiPointSslInfo",
        pvData,
        pcbDataa,
        v18);
      goto LABEL_32;
    }
    v8 = 439;
LABEL_9:
    LODWORD(pcbData) = v6;
    pvDataa = L"lr == 0L";
LABEL_10:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      v8,
      L"GetMultiPointSslInfo",
      L"CBRAEx",
      pvDataa,
      pcbData);
    goto LABEL_32;
  }
  v20 = 4;
  ValueW = RegGetValueW(hkey, 0, L"SslPort", 0x10u, 0, &v21, &v20);
  v6 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v6 = (unsigned __int16)ValueW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x1BCu,
      L"GetMultiPointSslInfo",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v7 = 444;
      goto LABEL_6;
    }
    v8 = 444;
    goto LABEL_9;
  }
  v20 = 0;
  v10 = RegGetValueW(hkey, 0, L"SslCertificateThumbprint", 2u, 0, 0, &v20);
  v6 = v10;
  if ( v10 && v10 != 234 )
  {
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x1C1u,
      L"GetMultiPointSslInfo",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 234L)",
      v6);
    if ( IsDebuggerPresent() )
    {
      v18 = v6;
      v7 = 449;
      pcbDataa = L"(lr == 0L) || (lr == 234L)";
      pvData = L"CBRAEx";
      goto LABEL_7;
    }
    LODWORD(pcbData) = v6;
    v8 = 449;
    pvDataa = L"(lr == 0L) || (lr == 234L)";
    goto LABEL_10;
  }
  v4 = operator new(v20);
  if ( v4 )
  {
    v11 = RegGetValueW(hkey, 0, L"SslCertificateThumbprint", 2u, 0, v4, &v20);
    v6 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v12 = v21;
      v6 = 0;
      *a2 = (unsigned __int16 *)v4;
      v4 = 0;
      *a1 = v12;
    }
  }
  else
  {
    v6 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x1C7u,
      L"GetMultiPointSslInfo",
      L"CPR",
      L"pszSslCertificateThumbprint",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      v18 = -2147024882;
      v7 = 455;
      pcbDataa = L"pszSslCertificateThumbprint";
      pvData = L"CPR";
      goto LABEL_7;
    }
    LODWORD(pcbData) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      455,
      L"GetMultiPointSslInfo",
      L"CPR",
      L"pszSslCertificateThumbprint",
      pcbData);
  }
LABEL_32:
  operator delete(v4);
  if ( hkey )
    RegCloseKey(hkey);
  return v6;
}

```

## disassembly

```asm
0x14005a4e8  mov     [rsp-28h+arg_0], rbx
0x14005a4ed  mov     [rsp-28h+arg_8], rsi
0x14005a4f2  push    rbp
0x14005a4f3  push    rdi
0x14005a4f4  push    r12
0x14005a4f6  push    r14
0x14005a4f8  push    r15
0x14005a4fa  mov     rbp, rsp
0x14005a4fd  sub     rsp, 50h
0x14005a501  mov     rdi, rdx
0x14005a504  mov     [rbp+hkey], 0
0x14005a50c  mov     rsi, rcx
0x14005a50f  mov     [rbp+arg_18], 0
0x14005a516  lea     rax, [rbp+hkey]
0x14005a51a  mov     [rbp+arg_10], 0
0x14005a521  lea     rdx, aSoftwareMicros_32; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14005a528  mov     [rsp+50h+phkResult], rax; phkResult
0x14005a52d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005a534  mov     r9d, 20019h; samDesired
0x14005a53a  xor     r8d, r8d; ulOptions
0x14005a53d  xor     r15d, r15d
0x14005a540  call    cs:__imp_RegOpenKeyExW
0x14005a546  mov     ebx, eax
0x14005a548  test    eax, eax
0x14005a54a  jz      loc_14005A5FA
0x14005a550  jle     short loc_14005A55B
0x14005a552  movzx   ebx, ax
0x14005a555  or      ebx, 80070000h
0x14005a55b  lea     r14, aCbraex; "CBRAEx"
0x14005a562  mov     dword ptr [rsp+50h+pvData], ebx; int
0x14005a566  lea     rsi, aGetmultipoints; "GetMultiPointSslInfo"
0x14005a56d  mov     r9, r14; unsigned __int16 *
0x14005a570  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005a577  mov     r8, rsi; unsigned __int16 *
0x14005a57a  lea     r12, aLr0l; "lr == 0L"
0x14005a581  mov     rcx, rdi; unsigned __int16 *
0x14005a584  mov     edx, 1B7h; unsigned int
0x14005a589  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x14005a58e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005a593  call    cs:__imp_IsDebuggerPresent
0x14005a599  test    eax, eax
0x14005a59b  jz      short loc_14005A5CF
0x14005a59d  mov     r9d, 1B7h
0x14005a5a3  mov     [rsp+50h+var_18], ebx
0x14005a5a7  mov     ecx, 2; unsigned __int8
0x14005a5ac  mov     [rsp+50h+pcbData], r12
0x14005a5b1  mov     [rsp+50h+pvData], r14
0x14005a5b6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005a5bd  mov     [rsp+50h+phkResult], rsi
0x14005a5c2  mov     r8, rdi
0x14005a5c5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005a5ca  jmp     loc_14005A852
0x14005a5cf  mov     r8d, 1B7h
0x14005a5d5  mov     dword ptr [rsp+50h+pcbData], ebx
0x14005a5d9  mov     [rsp+50h+pvData], r12
0x14005a5de  mov     [rsp+50h+phkResult], r14
0x14005a5e3  mov     r9, rsi
0x14005a5e6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005a5ed  mov     rdx, rdi
0x14005a5f0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005a5f5  jmp     loc_14005A852
0x14005a5fa  mov     rcx, [rbp+hkey]; hkey
0x14005a5fe  lea     rax, [rbp+arg_10]
0x14005a602  mov     [rsp+50h+pcbData], rax; pcbData
0x14005a607  lea     r8, aSslport_2; "SslPort"
0x14005a60e  lea     rax, [rbp+arg_18]
0x14005a612  mov     [rbp+arg_10], 4
0x14005a619  mov     [rsp+50h+pvData], rax; pvData
0x14005a61e  mov     r9d, 10h; dwFlags
0x14005a624  xor     edx, edx; lpSubKey
0x14005a626  mov     [rsp+50h+phkResult], r15; pdwType
0x14005a62b  call    cs:__imp_RegGetValueW
0x14005a631  mov     ebx, eax
0x14005a633  test    eax, eax
0x14005a635  jz      short loc_14005A69A
0x14005a637  jle     short loc_14005A642
0x14005a639  movzx   ebx, ax
0x14005a63c  or      ebx, 80070000h
0x14005a642  lea     r14, aCbraex; "CBRAEx"
0x14005a649  mov     dword ptr [rsp+50h+pvData], ebx; int
0x14005a64d  lea     rsi, aGetmultipoints; "GetMultiPointSslInfo"
0x14005a654  mov     r9, r14; unsigned __int16 *
0x14005a657  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005a65e  mov     r8, rsi; unsigned __int16 *
0x14005a661  lea     r12, aLr0l; "lr == 0L"
0x14005a668  mov     rcx, rdi; unsigned __int16 *
0x14005a66b  mov     edx, 1BCh; unsigned int
0x14005a670  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x14005a675  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005a67a  call    cs:__imp_IsDebuggerPresent
0x14005a680  test    eax, eax
0x14005a682  jz      short loc_14005A68F
0x14005a684  mov     r9d, 1BCh
0x14005a68a  jmp     loc_14005A5A3
0x14005a68f  mov     r8d, 1BCh
0x14005a695  jmp     loc_14005A5D5
0x14005a69a  mov     rcx, [rbp+hkey]; hkey
0x14005a69e  lea     rax, [rbp+arg_10]
0x14005a6a2  mov     [rsp+50h+pcbData], rax; pcbData
0x14005a6a7  lea     r8, aSslcertificate_5; "SslCertificateThumbprint"
0x14005a6ae  mov     r12d, 2
0x14005a6b4  mov     [rsp+50h+pvData], r15; pvData
0x14005a6b9  mov     r9d, r12d; dwFlags
0x14005a6bc  mov     [rsp+50h+phkResult], r15; pdwType
0x14005a6c1  xor     edx, edx; lpSubKey
0x14005a6c3  mov     [rbp+arg_10], r15d
0x14005a6c7  call    cs:__imp_RegGetValueW
0x14005a6cd  mov     ebx, eax
0x14005a6cf  test    eax, eax
0x14005a6d1  jz      loc_14005A768
0x14005a6d7  cmp     eax, 0EAh
0x14005a6dc  jz      loc_14005A768
0x14005a6e2  test    eax, eax
0x14005a6e4  jle     short loc_14005A6EF
0x14005a6e6  movzx   ebx, ax
0x14005a6e9  or      ebx, 80070000h
0x14005a6ef  lea     rax, aLr0lLr234l; "(lr == 0L) || (lr == 234L)"
0x14005a6f6  mov     dword ptr [rsp+50h+pvData], ebx; int
0x14005a6fa  lea     r14, aCbraex; "CBRAEx"
0x14005a701  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14005a706  lea     rsi, aGetmultipoints; "GetMultiPointSslInfo"
0x14005a70d  mov     r9, r14; unsigned __int16 *
0x14005a710  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005a717  mov     r8, rsi; unsigned __int16 *
0x14005a71a  mov     rcx, rdi; unsigned __int16 *
0x14005a71d  mov     edx, 1C1h; unsigned int
0x14005a722  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005a727  call    cs:__imp_IsDebuggerPresent
0x14005a72d  test    eax, eax
0x14005a72f  lea     rax, aLr0lLr234l; "(lr == 0L) || (lr == 234L)"
0x14005a736  jz      short loc_14005A754
0x14005a738  mov     [rsp+50h+var_18], ebx
0x14005a73c  mov     r9d, 1C1h
0x14005a742  mov     [rsp+50h+pcbData], rax
0x14005a747  mov     [rsp+50h+pvData], r14
0x14005a74c  mov     ecx, r12d
0x14005a74f  jmp     loc_14005A5B6
0x14005a754  mov     dword ptr [rsp+50h+pcbData], ebx
0x14005a758  mov     r8d, 1C1h
0x14005a75e  mov     [rsp+50h+pvData], rax
0x14005a763  jmp     loc_14005A5DE
0x14005a768  mov     ecx, [rbp+arg_10]; Size
0x14005a76b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005a770  mov     r15, rax
0x14005a773  test    rax, rax
0x14005a776  jnz     loc_14005A805
0x14005a77c  lea     rax, aPszsslcertific; "pszSslCertificateThumbprint"
0x14005a783  mov     ebx, 8007000Eh
0x14005a788  lea     rsi, aGetmultipoints; "GetMultiPointSslInfo"
0x14005a78f  mov     dword ptr [rsp+50h+pvData], ebx; int
0x14005a793  mov     r14d, 1C7h
0x14005a799  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14005a79e  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005a7a5  mov     r8, rsi; unsigned __int16 *
0x14005a7a8  mov     edx, r14d; unsigned int
0x14005a7ab  lea     r9, aCpr; "CPR"
0x14005a7b2  mov     rcx, rdi; unsigned __int16 *
0x14005a7b5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005a7ba  call    cs:__imp_IsDebuggerPresent
0x14005a7c0  test    eax, eax
0x14005a7c2  lea     rax, aPszsslcertific; "pszSslCertificateThumbprint"
0x14005a7c9  jz      short loc_14005A7E8
0x14005a7cb  mov     [rsp+50h+var_18], ebx
0x14005a7cf  mov     r9d, r14d
0x14005a7d2  mov     [rsp+50h+pcbData], rax
0x14005a7d7  lea     rax, aCpr; "CPR"
0x14005a7de  mov     [rsp+50h+pvData], rax
0x14005a7e3  jmp     loc_14005A74C
0x14005a7e8  mov     dword ptr [rsp+50h+pcbData], ebx
0x14005a7ec  mov     r8d, r14d
0x14005a7ef  mov     [rsp+50h+pvData], rax
0x14005a7f4  lea     rax, aCpr; "CPR"
0x14005a7fb  mov     [rsp+50h+phkResult], rax
0x14005a800  jmp     loc_14005A5E3
0x14005a805  mov     rcx, [rbp+hkey]; hkey
0x14005a809  lea     rax, [rbp+arg_10]
0x14005a80d  mov     [rsp+50h+pcbData], rax; pcbData
0x14005a812  lea     r8, aSslcertificate_5; "SslCertificateThumbprint"
0x14005a819  mov     [rsp+50h+pvData], r15; pvData
0x14005a81e  mov     r9d, r12d; dwFlags
0x14005a821  xor     edx, edx; lpSubKey
0x14005a823  mov     [rsp+50h+phkResult], 0; pdwType
0x14005a82c  call    cs:__imp_RegGetValueW
0x14005a832  mov     ebx, eax
0x14005a834  test    eax, eax
0x14005a836  jz      short loc_14005A845
0x14005a838  jle     short loc_14005A852
0x14005a83a  movzx   ebx, ax
0x14005a83d  or      ebx, 80070000h
0x14005a843  jmp     short loc_14005A852
0x14005a845  mov     eax, [rbp+arg_18]
0x14005a848  xor     ebx, ebx
0x14005a84a  mov     [rdi], r15
0x14005a84d  xor     r15d, r15d
0x14005a850  mov     [rsi], eax
0x14005a852  mov     rcx, r15; Block
0x14005a855  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005a85a  mov     rcx, [rbp+hkey]; hKey
0x14005a85e  test    rcx, rcx
0x14005a861  jz      short loc_14005A869
0x14005a863  call    cs:__imp_RegCloseKey
0x14005a869  lea     r11, [rsp+50h+var_s0]
0x14005a86e  mov     eax, ebx
0x14005a870  mov     rbx, [r11+30h]
0x14005a874  mov     rsi, [r11+38h]
0x14005a878  mov     rsp, r11
0x14005a87b  pop     r15
0x14005a87d  pop     r14
0x14005a87f  pop     r12
0x14005a881  pop     rdi
0x14005a882  pop     rbp
0x14005a883  retn
```
