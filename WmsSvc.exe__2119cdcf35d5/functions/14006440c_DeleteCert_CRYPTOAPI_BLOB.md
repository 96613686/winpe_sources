# DeleteCert(_CRYPTOAPI_BLOB *)

- ea: `0x14006440c`
- end: `0x14006463e`
- name: `?DeleteCert@@YAJPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *pvFindPara)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140023030`
- `0x14004823c`
- `0x14004a590`
- `0x14004c738`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006440c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140064449`
- `KERNEL32!GetLastError` at `0x140064533`
- `KERNEL32!GetLastError` at `0x14006456a`
- `KERNEL32!GetLastError` at `0x140064449`
- `KERNEL32!GetLastError` at `0x140064533`
- `KERNEL32!GetLastError` at `0x14006456a`
- `KERNEL32!IsDebuggerPresent` at `0x1400644a1`
- `KERNEL32!IsDebuggerPresent` at `0x1400645c2`
- `KERNEL32!IsDebuggerPresent` at `0x1400644a1`
- `KERNEL32!IsDebuggerPresent` at `0x1400645c2`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x14006455c`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x14006455c`
- `CRYPT32!CertFindCertificateInStore` at `0x140064528`
- `CRYPT32!CertFindCertificateInStore` at `0x140064528`
- `CRYPT32!CertCloseStore` at `0x140064628`
- `CRYPT32!CertCloseStore` at `0x140064628`
- `CRYPT32!CertOpenStore` at `0x140064437`
- `CRYPT32!CertOpenStore` at `0x140064437`

## string_xrefs

- `0x140064483`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x1400644af`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x1400644e2`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x1400645a4`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x1400645d0`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x140064600`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x14006446c`: `DeleteCert`
- `0x14006459a`: `DeleteCert`
- `0x14006441c`: `MultiPoint Services Certificates`

## pseudocode

```c
__int64 __fastcall DeleteCert(struct _CRYPTOAPI_BLOB *pvFindPara)
{
  HCERTSTORE v2; // rax
  void *v3; // r14
  signed int v4; // eax
  signed int v5; // ebx
  const CERT_CONTEXT *CertificateInStore; // rax
  signed int v7; // eax
  const unsigned __int16 *v8; // r12
  unsigned int v9; // r15d
  signed int LastError; // eax

  v2 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"MultiPoint Services Certificates");
  v3 = v2;
  if ( v2 )
  {
    CertificateInStore = CertFindCertificateInStore(v2, 1u, 0, 0x10000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      v5 = 0;
      if ( CertDeleteCertificateFromStore(CertificateInStore) )
      {
LABEL_22:
        CertCloseStore(v3, 0);
        return (unsigned int)v5;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v8 = L"fSuccess";
      v9 = 572;
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      v8 = L"pCertContext";
      v9 = 566;
    }
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp", v9, L"DeleteCert", L"CBRAEx", v8, v5);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
        v9,
        L"DeleteCert",
        L"CBRAEx",
        v8,
        v5);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
        v9,
        L"DeleteCert",
        L"CBRAEx",
        v8,
        v5);
    goto LABEL_22;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
    v5 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
    0x232u,
    L"DeleteCert",
    L"CBRAEx",
    L"hCertStore != 0",
    v5);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
      562,
      L"DeleteCert",
      L"CBRAEx",
      L"hCertStore != 0",
      v5);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\wsutils.cpp",
      562,
      L"DeleteCert",
      L"CBRAEx",
      L"hCertStore != 0",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14006440c  push    rbx
0x14006440e  push    rbp
0x14006440f  push    rsi
0x140064410  push    r12
0x140064412  push    r14
0x140064414  push    r15
0x140064416  sub     rsp, 48h
0x14006441a  xor     edx, edx; dwEncodingType
0x14006441c  lea     rax, aMultipointServ; "MultiPoint Services Certificates"
0x140064423  mov     rbx, rcx
0x140064426  mov     [rsp+78h+pvPara], rax; pvPara
0x14006442b  mov     r9d, 20000h; dwFlags
0x140064431  xor     r8d, r8d; hCryptProv
0x140064434  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x140064437  call    cs:__imp_CertOpenStore
0x14006443d  mov     r14, rax
0x140064440  test    rax, rax
0x140064443  jnz     loc_14006450A
0x140064449  call    cs:__imp_GetLastError
0x14006444f  mov     ebx, eax
0x140064451  test    eax, eax
0x140064453  jle     short loc_14006445E
0x140064455  movzx   ebx, ax
0x140064458  or      ebx, 80070000h
0x14006445e  mov     eax, 80004005h
0x140064463  lea     rbp, aCbraex; "CBRAEx"
0x14006446a  test    ebx, ebx
0x14006446c  lea     rsi, aDeletecert; "DeleteCert"
0x140064473  mov     r14d, 232h
0x140064479  lea     r15, aHcertstore0; "hCertStore != 0"
0x140064480  cmovns  ebx, eax
0x140064483  lea     rcx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x14006448a  mov     dword ptr [rsp+78h+pPrevCertContext], ebx; int
0x14006448e  mov     r9, rbp; unsigned __int16 *
0x140064491  mov     r8, rsi; unsigned __int16 *
0x140064494  mov     [rsp+78h+pvPara], r15; unsigned __int16 *
0x140064499  mov     edx, r14d; unsigned int
0x14006449c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400644a1  call    cs:__imp_IsDebuggerPresent
0x1400644a7  test    eax, eax
0x1400644a9  jz      short loc_1400644DE
0x1400644ab  mov     [rsp+78h+var_40], ebx
0x1400644af  lea     r8, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400644b6  mov     [rsp+78h+var_48], r15
0x1400644bb  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400644c2  mov     [rsp+78h+pPrevCertContext], rbp
0x1400644c7  mov     r9d, r14d
0x1400644ca  mov     ecx, 2; unsigned __int8
0x1400644cf  mov     [rsp+78h+pvPara], rsi
0x1400644d4  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400644d9  jmp     loc_14006462E
0x1400644de  mov     dword ptr [rsp+78h+var_48], ebx
0x1400644e2  lea     rdx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400644e9  mov     [rsp+78h+pPrevCertContext], r15
0x1400644ee  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400644f5  mov     r9, rsi
0x1400644f8  mov     [rsp+78h+pvPara], rbp
0x1400644fd  mov     r8d, r14d
0x140064500  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140064505  jmp     loc_14006462E
0x14006450a  xor     r8d, r8d; dwFindFlags
0x14006450d  mov     [rsp+78h+pPrevCertContext], 0; pPrevCertContext
0x140064516  mov     r9d, 10000h; dwFindType
0x14006451c  mov     [rsp+78h+pvPara], rbx; pvFindPara
0x140064521  mov     rcx, r14; hCertStore
0x140064524  lea     edx, [r8+1]; dwCertEncodingType
0x140064528  call    cs:__imp_CertFindCertificateInStore
0x14006452e  test    rax, rax
0x140064531  jnz     short loc_140064557
0x140064533  call    cs:__imp_GetLastError
0x140064539  mov     ebx, eax
0x14006453b  test    eax, eax
0x14006453d  jle     short loc_140064548
0x14006453f  movzx   ebx, ax
0x140064542  or      ebx, 80070000h
0x140064548  lea     r12, aPcertcontext; "pCertContext"
0x14006454f  mov     r15d, 236h
0x140064555  jmp     short loc_14006458C
0x140064557  mov     rcx, rax; pCertContext
0x14006455a  xor     ebx, ebx
0x14006455c  call    cs:__imp_CertDeleteCertificateFromStore
0x140064562  test    eax, eax
0x140064564  jnz     loc_140064623
0x14006456a  call    cs:__imp_GetLastError
0x140064570  mov     ebx, eax
0x140064572  test    eax, eax
0x140064574  jle     short loc_14006457F
0x140064576  movzx   ebx, ax
0x140064579  or      ebx, 80070000h
0x14006457f  lea     r12, aFsuccess; "fSuccess"
0x140064586  mov     r15d, 23Ch
0x14006458c  mov     eax, 80004005h
0x140064591  lea     rbp, aCbraex; "CBRAEx"
0x140064598  test    ebx, ebx
0x14006459a  lea     rsi, aDeletecert; "DeleteCert"
0x1400645a1  mov     r9, rbp; unsigned __int16 *
0x1400645a4  lea     rcx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400645ab  cmovns  ebx, eax
0x1400645ae  mov     r8, rsi; unsigned __int16 *
0x1400645b1  mov     dword ptr [rsp+78h+pPrevCertContext], ebx; int
0x1400645b5  mov     edx, r15d; unsigned int
0x1400645b8  mov     [rsp+78h+pvPara], r12; unsigned __int16 *
0x1400645bd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400645c2  call    cs:__imp_IsDebuggerPresent
0x1400645c8  test    eax, eax
0x1400645ca  jz      short loc_1400645FC
0x1400645cc  mov     [rsp+78h+var_40], ebx
0x1400645d0  lea     r8, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x1400645d7  mov     [rsp+78h+var_48], r12
0x1400645dc  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400645e3  mov     [rsp+78h+pPrevCertContext], rbp
0x1400645e8  mov     r9d, r15d
0x1400645eb  mov     ecx, 2; unsigned __int8
0x1400645f0  mov     [rsp+78h+pvPara], rsi
0x1400645f5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400645fa  jmp     short loc_140064623
0x1400645fc  mov     dword ptr [rsp+78h+var_48], ebx
0x140064600  lea     rdx, aTermsrvWmsSrcC_6; "termsrv\\wms\\src\\common\\srcutils\\ws"...
0x140064607  mov     [rsp+78h+pPrevCertContext], r12
0x14006460c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140064613  mov     r9, rsi
0x140064616  mov     [rsp+78h+pvPara], rbp
0x14006461b  mov     r8d, r15d
0x14006461e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140064623  xor     edx, edx; dwFlags
0x140064625  mov     rcx, r14; hCertStore
0x140064628  call    cs:__imp_CertCloseStore
0x14006462e  mov     eax, ebx
0x140064630  add     rsp, 48h
0x140064634  pop     r15
0x140064636  pop     r14
0x140064638  pop     r12
0x14006463a  pop     rsi
0x14006463b  pop     rbp
0x14006463c  pop     rbx
0x14006463d  retn
```
