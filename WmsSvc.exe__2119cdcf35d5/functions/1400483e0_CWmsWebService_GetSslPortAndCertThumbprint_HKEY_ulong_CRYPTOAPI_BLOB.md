# CWmsWebService::GetSslPortAndCertThumbprint(HKEY__ *,ulong *,_CRYPTOAPI_BLOB *)

- ea: `0x1400483e0`
- end: `0x1400486fd`
- name: `?GetSslPortAndCertThumbprint@CWmsWebService@@AEAAJPEAUHKEY__@@PEAKPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this, HKEY, unsigned int *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x140048d20`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140046c2c`
- `0x1400483e0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064148`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140048434`
- `ADVAPI32!RegGetValueW` at `0x140048550`
- `ADVAPI32!RegGetValueW` at `0x1400486be`
- `ADVAPI32!RegGetValueW` at `0x140048434`
- `ADVAPI32!RegGetValueW` at `0x140048550`
- `ADVAPI32!RegGetValueW` at `0x1400486be`
- `ADVAPI32!RegSetValueExW` at `0x140048522`
- `ADVAPI32!RegSetValueExW` at `0x140048522`
- `KERNEL32!IsDebuggerPresent` at `0x14004849a`
- `KERNEL32!IsDebuggerPresent` at `0x1400485b9`
- `KERNEL32!IsDebuggerPresent` at `0x14004865a`
- `KERNEL32!IsDebuggerPresent` at `0x14004849a`
- `KERNEL32!IsDebuggerPresent` at `0x1400485b9`
- `KERNEL32!IsDebuggerPresent` at `0x14004865a`

## string_xrefs

- `0x140048482`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400485a1`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140048633`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140048475`: `CWmsWebService::GetSslPortAndCertThumbprint`
- `0x140048594`: `CWmsWebService::GetSslPortAndCertThumbprint`
- `0x140048623`: `CWmsWebService::GetSslPortAndCertThumbprint`
- `0x1400486e1`: `CWmsWebService::GetSslPortAndCertThumbprint - cert thumbprint %s found in registry.\n`
- `0x1400485cd`: `CWmsWebService::GetSslPortAndCertThumbprint - cert thumprint not found in registry, creating new cert.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::GetSslPortAndCertThumbprint(
        CWmsWebService *this,
        HKEY a2,
        unsigned int *a3,
        struct _CRYPTOAPI_BLOB *a4)
{
  void *v5; // r14
  LSTATUS ValueW; // eax
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  LSTATUS v14; // eax
  int MultiPointSslCert; // eax
  LSTATUS v17; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-58h]
  DWORD v19; // [rsp+40h] [rbp-48h] BYREF
  BYTE Data[68]; // [rsp+44h] [rbp-44h] BYREF

  *(_DWORD *)Data = 8443;
  v5 = 0;
  v19 = 4;
  ValueW = RegGetValueW(a2, 0, L"SslPort", 0x10u, 0, Data, &v19);
  v10 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
      v11 = 1088;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x440u,
        L"CWmsWebService::GetSslPortAndCertThumbprint",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v10);
      v12 = !IsDebuggerPresent();
      v13 = L"(lr == 0L) || (lr == 2L)";
LABEL_6:
      if ( v12 )
      {
        LODWORD(pcbData) = v10;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          v11,
          L"CWmsWebService::GetSslPortAndCertThumbprint",
          L"CBRAEx",
          v13,
          pcbData);
      }
      else
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          v11,
          L"CWmsWebService::GetSslPortAndCertThumbprint",
          L"CBRAEx",
          v13,
          v10);
      }
      goto LABEL_21;
    }
    RegSetValueExW(a2, L"SslPort", 0, 4u, Data, 4u);
  }
  v19 = 0;
  v14 = RegGetValueW(a2, 0, L"SslCertificateThumbprint", 2u, 0, 0, &v19);
  v10 = v14;
  if ( v14 )
  {
    if ( v14 == 2 )
    {
      DEBUGMSG(L"CWmsWebService::GetSslPortAndCertThumbprint - cert thumprint not found in registry, creating new cert.\n");
      MultiPointSslCert = CWmsWebService::CreateMultiPointSslCert(this, a2, a4);
      goto LABEL_19;
    }
    if ( v14 != 234 )
    {
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      v11 = 1098;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x44Au,
        L"CWmsWebService::GetSslPortAndCertThumbprint",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L) || (lr == 234L)",
        v10);
      v12 = !IsDebuggerPresent();
      v13 = L"(lr == 0L) || (lr == 2L) || (lr == 234L)";
      goto LABEL_6;
    }
  }
  v5 = operator new(v19);
  if ( !v5 )
  {
    v10 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x450u,
      L"CWmsWebService::GetSslPortAndCertThumbprint",
      L"CPR",
      L"pszSslCertificateThumbprint",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        1104,
        L"CWmsWebService::GetSslPortAndCertThumbprint",
        L"CPR",
        L"pszSslCertificateThumbprint",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        1104,
        L"CWmsWebService::GetSslPortAndCertThumbprint",
        L"CPR",
        L"pszSslCertificateThumbprint",
        pcbData);
    }
    goto LABEL_21;
  }
  v17 = RegGetValueW(a2, 0, L"SslCertificateThumbprint", 2u, 0, v5, &v19);
  v10 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_21;
  }
  DEBUGMSG(L"CWmsWebService::GetSslPortAndCertThumbprint - cert thumbprint %s found in registry.\n", v5);
  MultiPointSslCert = ConvertThumbprintStringToBlob((const unsigned __int16 *)v5, a4);
LABEL_19:
  v10 = MultiPointSslCert;
  if ( MultiPointSslCert >= 0 )
    *a3 = *(_DWORD *)Data;
LABEL_21:
  operator delete(v5);
  return v10;
}

```

## disassembly

```asm
0x1400483e0  mov     r11, rsp
0x1400483e3  push    rbx
0x1400483e4  push    rbp
0x1400483e5  push    rsi
0x1400483e6  push    rdi
0x1400483e7  push    r13
0x1400483e9  push    r14
0x1400483eb  push    r15
0x1400483ed  sub     rsp, 50h
0x1400483f1  lea     rax, [r11-48h]
0x1400483f5  mov     dword ptr [rsp+88h+Data], 20FBh
0x1400483fd  mov     [r11-58h], rax
0x140048401  mov     rdi, rdx
0x140048404  xor     r14d, r14d
0x140048407  mov     [rsp+88h+var_48], 4
0x14004840f  lea     rax, [r11-44h]
0x140048413  mov     rsi, r9
0x140048416  mov     r15, r8
0x140048419  mov     [r11-60h], rax
0x14004841d  mov     rbp, rcx
0x140048420  mov     [r11-68h], r14
0x140048424  lea     r9d, [r14+10h]; dwFlags
0x140048428  xor     edx, edx; lpSubKey
0x14004842a  lea     r8, aSslport_1; "SslPort"
0x140048431  mov     rcx, rdi; hkey
0x140048434  call    cs:__imp_RegGetValueW
0x14004843a  lea     r13d, [r14+2]
0x14004843e  mov     ebx, eax
0x140048440  test    eax, eax
0x140048442  jz      loc_140048528
0x140048448  cmp     eax, r13d
0x14004844b  jz      loc_140048500
0x140048451  test    eax, eax
0x140048453  jle     short loc_14004845E
0x140048455  movzx   ebx, ax
0x140048458  or      ebx, 80070000h
0x14004845e  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140048465  mov     [rsp+88h+cbData], ebx; int
0x140048469  lea     rbp, aCbraex; "CBRAEx"
0x140048470  mov     [rsp+88h+lpData], rax; unsigned __int16 *
0x140048475  lea     rsi, aCwmswebservice_83; "CWmsWebService::GetSslPortAndCertThumbp"...
0x14004847c  mov     r15d, 440h
0x140048482  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140048489  mov     r9, rbp; unsigned __int16 *
0x14004848c  mov     r8, rsi; unsigned __int16 *
0x14004848f  mov     edx, r15d; unsigned int
0x140048492  mov     rcx, rdi; unsigned __int16 *
0x140048495  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004849a  call    cs:__imp_IsDebuggerPresent
0x1400484a0  test    eax, eax
0x1400484a2  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x1400484a9  jz      short loc_1400484D8
0x1400484ab  mov     [rsp+88h+var_50], ebx
0x1400484af  mov     r9d, r15d
0x1400484b2  mov     [rsp+88h+pcbData], rax
0x1400484b7  mov     qword ptr [rsp+88h+cbData], rbp
0x1400484bc  mov     r8, rdi
0x1400484bf  mov     [rsp+88h+lpData], rsi
0x1400484c4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400484cb  mov     ecx, r13d; unsigned __int8
0x1400484ce  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400484d3  jmp     loc_1400485F4
0x1400484d8  mov     dword ptr [rsp+88h+pcbData], ebx
0x1400484dc  mov     r8d, r15d
0x1400484df  mov     qword ptr [rsp+88h+cbData], rax
0x1400484e4  mov     [rsp+88h+lpData], rbp
0x1400484e9  mov     r9, rsi
0x1400484ec  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400484f3  mov     rdx, rdi
0x1400484f6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400484fb  jmp     loc_1400485F4
0x140048500  mov     r9d, 4; dwType
0x140048506  lea     rax, [rsp+88h+Data]
0x14004850b  mov     [rsp+88h+cbData], r9d; cbData
0x140048510  lea     rdx, aSslport_1; "SslPort"
0x140048517  xor     r8d, r8d; Reserved
0x14004851a  mov     [rsp+88h+lpData], rax; lpData
0x14004851f  mov     rcx, rdi; hKey
0x140048522  call    cs:__imp_RegSetValueExW
0x140048528  lea     rax, [rsp+88h+var_48]
0x14004852d  mov     [rsp+88h+var_48], r14d
0x140048532  mov     [rsp+88h+pcbData], rax; pcbData
0x140048537  lea     r8, aSslcertificate_1; "SslCertificateThumbprint"
0x14004853e  mov     qword ptr [rsp+88h+cbData], r14; pvData
0x140048543  mov     r9d, r13d; dwFlags
0x140048546  xor     edx, edx; lpSubKey
0x140048548  mov     [rsp+88h+lpData], r14; pdwType
0x14004854d  mov     rcx, rdi; hkey
0x140048550  call    cs:__imp_RegGetValueW
0x140048556  mov     ebx, eax
0x140048558  test    eax, eax
0x14004855a  jz      loc_14004860D
0x140048560  cmp     eax, r13d
0x140048563  jz      short loc_1400485CD
0x140048565  cmp     eax, 0EAh
0x14004856a  jz      loc_14004860D
0x140048570  test    eax, eax
0x140048572  jle     short loc_14004857D
0x140048574  movzx   ebx, ax
0x140048577  or      ebx, 80070000h
0x14004857d  lea     rax, aLr0lLr2lLr234l; "(lr == 0L) || (lr == 2L) || (lr == 234L"...
0x140048584  mov     [rsp+88h+cbData], ebx; int
0x140048588  lea     rbp, aCbraex; "CBRAEx"
0x14004858f  mov     [rsp+88h+lpData], rax; unsigned __int16 *
0x140048594  lea     rsi, aCwmswebservice_83; "CWmsWebService::GetSslPortAndCertThumbp"...
0x14004859b  mov     r15d, 44Ah
0x1400485a1  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400485a8  mov     r9, rbp; unsigned __int16 *
0x1400485ab  mov     r8, rsi; unsigned __int16 *
0x1400485ae  mov     edx, r15d; unsigned int
0x1400485b1  mov     rcx, rdi; unsigned __int16 *
0x1400485b4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400485b9  call    cs:__imp_IsDebuggerPresent
0x1400485bf  test    eax, eax
0x1400485c1  lea     rax, aLr0lLr2lLr234l; "(lr == 0L) || (lr == 2L) || (lr == 234L"...
0x1400485c8  jmp     loc_1400484A9
0x1400485cd  lea     rcx, aCwmswebservice_110; "CWmsWebService::GetSslPortAndCertThumbp"...
0x1400485d4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400485d9  mov     r8, rsi; struct _CRYPTOAPI_BLOB *
0x1400485dc  mov     rdx, rdi; HKEY
0x1400485df  mov     rcx, rbp; this
0x1400485e2  call    ?CreateMultiPointSslCert@CWmsWebService@@AEAAJPEAUHKEY__@@PEAU_CRYPTOAPI_BLOB@@@Z; CWmsWebService::CreateMultiPointSslCert(HKEY__ *,_CRYPTOAPI_BLOB *)
0x1400485e7  mov     ebx, eax
0x1400485e9  test    eax, eax
0x1400485eb  js      short loc_1400485F4
0x1400485ed  mov     eax, dword ptr [rsp+88h+Data]
0x1400485f1  mov     [r15], eax
0x1400485f4  mov     rcx, r14; Block
0x1400485f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400485fc  mov     eax, ebx
0x1400485fe  add     rsp, 50h
0x140048602  pop     r15
0x140048604  pop     r14
0x140048606  pop     r13
0x140048608  pop     rdi
0x140048609  pop     rsi
0x14004860a  pop     rbp
0x14004860b  pop     rbx
0x14004860c  retn
0x14004860d  mov     ecx, [rsp+88h+var_48]; Size
0x140048611  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140048616  mov     r14, rax
0x140048619  test    rax, rax
0x14004861c  jnz     short loc_140048697
0x14004861e  mov     ebx, 8007000Eh
0x140048623  lea     rsi, aCwmswebservice_83; "CWmsWebService::GetSslPortAndCertThumbp"...
0x14004862a  mov     ebp, 450h
0x14004862f  mov     [rsp+88h+cbData], ebx; int
0x140048633  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004863a  mov     r8, rsi; unsigned __int16 *
0x14004863d  lea     r15, aPszsslcertific; "pszSslCertificateThumbprint"
0x140048644  mov     edx, ebp; unsigned int
0x140048646  mov     rcx, rdi; unsigned __int16 *
0x140048649  mov     [rsp+88h+lpData], r15; unsigned __int16 *
0x14004864e  lea     r9, aCpr; "CPR"
0x140048655  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004865a  call    cs:__imp_IsDebuggerPresent
0x140048660  test    eax, eax
0x140048662  lea     rax, aCpr; "CPR"
0x140048669  jz      short loc_140048681
0x14004866b  mov     [rsp+88h+var_50], ebx
0x14004866f  mov     r9d, ebp
0x140048672  mov     [rsp+88h+pcbData], r15
0x140048677  mov     qword ptr [rsp+88h+cbData], rax
0x14004867c  jmp     loc_1400484BC
0x140048681  mov     dword ptr [rsp+88h+pcbData], ebx
0x140048685  mov     r8d, ebp
0x140048688  mov     qword ptr [rsp+88h+cbData], r15
0x14004868d  mov     [rsp+88h+lpData], rax
0x140048692  jmp     loc_1400484E9
0x140048697  lea     rax, [rsp+88h+var_48]
0x14004869c  mov     r9d, r13d; dwFlags
0x14004869f  mov     [rsp+88h+pcbData], rax; pcbData
0x1400486a4  lea     r8, aSslcertificate_1; "SslCertificateThumbprint"
0x1400486ab  mov     qword ptr [rsp+88h+cbData], r14; pvData
0x1400486b0  xor     edx, edx; lpSubKey
0x1400486b2  mov     rcx, rdi; hkey
0x1400486b5  mov     [rsp+88h+lpData], 0; pdwType
0x1400486be  call    cs:__imp_RegGetValueW
0x1400486c4  mov     ebx, eax
0x1400486c6  test    eax, eax
0x1400486c8  jz      short loc_1400486DE
0x1400486ca  jle     loc_1400485F4
0x1400486d0  movzx   ebx, ax
0x1400486d3  or      ebx, 80070000h
0x1400486d9  jmp     loc_1400485F4
0x1400486de  mov     rdx, r14
0x1400486e1  lea     rcx, aCwmswebservice_24; "CWmsWebService::GetSslPortAndCertThumbp"...
0x1400486e8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400486ed  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x1400486f0  mov     rcx, r14; unsigned __int16 *
0x1400486f3  call    ?ConvertThumbprintStringToBlob@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; ConvertThumbprintStringToBlob(ushort const *,_CRYPTOAPI_BLOB *)
0x1400486f8  jmp     loc_1400485E7
```
