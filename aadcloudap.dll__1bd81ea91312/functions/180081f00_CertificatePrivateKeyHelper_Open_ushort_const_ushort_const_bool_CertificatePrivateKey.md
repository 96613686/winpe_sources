# CertificatePrivateKeyHelper::Open(ushort const *,ushort const *,bool,CertificatePrivateKey &)

- ea: `0x180081f00`
- end: `0x180082129`
- name: `?Open@CertificatePrivateKeyHelper@@SAJPEBG0_NAEAVCertificatePrivateKey@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, LPCWSTR pszProviderName, bool, struct CertificatePrivateKey *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003df38`
- `0x18007b0e4`

## callees

- `0x180003c20`
- `0x18000685c`
- `0x180006908`
- `0x1800069c0`
- `0x180006ac4`
- `0x180015188`
- `0x180071e14`
- `0x180081f00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180081fcc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180081fcc`
- `ncrypt!NCryptSetProperty` at `0x18008200d`
- `ncrypt!NCryptSetProperty` at `0x18008200d`
- `ncrypt!NCryptOpenKey` at `0x180082025`
- `ncrypt!NCryptOpenKey` at `0x180082025`
- `ncrypt!NCryptFreeObject` at `0x1800820e3`
- `ncrypt!NCryptFreeObject` at `0x1800820f2`
- `ncrypt!NCryptFreeObject` at `0x1800820e3`
- `ncrypt!NCryptFreeObject` at `0x1800820f2`
- `ncrypt!NCryptOpenStorageProvider` at `0x180081f8d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180081f8d`

## string_xrefs

- `0x180081f4e`: `CertificatePrivateKeyHelper::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CertificatePrivateKeyHelper::Open(
        LPCWSTR pszKeyName,
        LPCWSTR pszProviderName,
        unsigned __int8 a3,
        struct CertificatePrivateKey *a4)
{
  int v5; // ebx
  SECURITY_STATUS v8; // eax
  DWORD v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 dwFlags; // [rsp+20h] [rbp-59h]
  int v15; // [rsp+30h] [rbp-49h]
  int v16; // [rsp+50h] [rbp-29h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-21h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-19h] BYREF
  const char *v19[6]; // [rsp+68h] [rbp-11h] BYREF
  BYTE pbInput[4]; // [rsp+98h] [rbp+1Fh] BYREF
  int v21; // [rsp+9Ch] [rbp+23h]
  int v22; // [rsp+A0h] [rbp+27h]
  int v23; // [rsp+A4h] [rbp+2Bh]

  v5 = a3;
  v16 = 0;
  phProvider = 0;
  phKey = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v19,
    (int)"certificateprivatekey.cpp",
    (int)"CertificatePrivateKeyHelper::Open",
    (int)&v16);
  if ( pszKeyName && pszProviderName )
  {
    CertificatePrivateKey::Free(a4);
    v8 = NCryptOpenStorageProvider(&phProvider, pszProviderName, 0);
    v16 = v8;
    if ( v8 >= 0 )
    {
      v9 = 32 * v5;
      if ( !(unsigned int)_o__wcsicmp(pszProviderName, L"Microsoft Platform Crypto Provider") )
      {
        *(_DWORD *)pbInput = -1429209086;
        v21 = 1180574512;
        v22 = -327497080;
        v23 = -2029071512;
        v9 |= 0x10000000u;
        NCryptSetProperty(phProvider, L"PCP_SESSIONID", pbInput, 0x10u, 0);
      }
      v8 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, v9);
      v16 = v8;
      if ( v8 >= 0 )
      {
        v10 = ATL::CSimpleStringT<unsigned short,0>::StringLength(pszKeyName);
        ATL::CSimpleStringT<unsigned short,0>::SetString(a4, pszKeyName, v10);
        v11 = ATL::CSimpleStringT<unsigned short,0>::StringLength(pszProviderName);
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)a4 + 8, pszProviderName, v11);
        *((_QWORD *)a4 + 2) = phKey;
        phKey = 0;
        goto LABEL_12;
      }
      v15 = 187;
    }
    else
    {
      v15 = 175;
    }
  }
  else
  {
    v8 = -2147024809;
    v16 = -2147024809;
    v15 = 170;
  }
  LODWORD(dwFlags) = v8;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, dwFlags, "certificateprivatekey.cpp", v15, "HRESULT", &base);
LABEL_12:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  v12 = v16;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v19);
  return v12;
}

```

## disassembly

```asm
0x180081f00  mov     [rsp-8+arg_10], rbx
0x180081f05  push    rbp
0x180081f06  push    rsi
0x180081f07  push    rdi
0x180081f08  push    r12
0x180081f0a  push    r14
0x180081f0c  lea     rbp, [rsp-37h]
0x180081f11  sub     rsp, 0B0h
0x180081f18  mov     rax, cs:__security_cookie
0x180081f1f  xor     rax, rsp
0x180081f22  mov     [rbp+57h+var_28], rax
0x180081f26  mov     rsi, r9
0x180081f29  movzx   ebx, r8b
0x180081f2d  mov     rdi, rdx
0x180081f30  mov     r14, rcx
0x180081f33  mov     [rbp+57h+var_80], 0
0x180081f3a  mov     [rbp+57h+phProvider], 0
0x180081f42  mov     [rbp+57h+phKey], 0
0x180081f4a  lea     r9, [rbp+57h+var_80]
0x180081f4e  lea     r8, aCertificatepri_4; "CertificatePrivateKeyHelper::Open"
0x180081f55  lea     r12, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x180081f5c  mov     rdx, r12
0x180081f5f  lea     rcx, [rbp+57h+var_68]
0x180081f63  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180081f68  nop
0x180081f69  test    r14, r14
0x180081f6c  jz      loc_180082093
0x180081f72  test    rdi, rdi
0x180081f75  jz      loc_180082093
0x180081f7b  mov     rcx, rsi; this
0x180081f7e  call    ?Free@CertificatePrivateKey@@QEAAXXZ; CertificatePrivateKey::Free(void)
0x180081f83  xor     r8d, r8d; dwFlags
0x180081f86  mov     rdx, rdi; pszProviderName
0x180081f89  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180081f8d  call    cs:__imp_NCryptOpenStorageProvider
0x180081f93  mov     [rbp+57h+var_80], eax
0x180081f96  test    eax, eax
0x180081f98  jns     short loc_180081FBF
0x180081f9a  lea     rcx, base
0x180081fa1  mov     [rsp+0D0h+var_90], rcx
0x180081fa6  lea     rcx, aHresult; "HRESULT"
0x180081fad  mov     [rsp+0D0h+var_98], rcx
0x180081fb2  mov     [rsp+0D0h+var_A0], 0AFh
0x180081fba  jmp     loc_1800820BB
0x180081fbf  shl     ebx, 5
0x180081fc2  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180081fc9  mov     rcx, rdi
0x180081fcc  call    cs:__imp__o__wcsicmp
0x180081fd2  test    eax, eax
0x180081fd4  jnz     short loc_180082013
0x180081fd6  mov     dword ptr [rbp+57h+pbInput], 0AAD00002h
0x180081fdd  mov     [rbp+57h+var_34], 465E2330h
0x180081fe4  mov     [rbp+57h+var_30], 0EC7ACA88h
0x180081feb  mov     [rbp+57h+var_2C], 870ED368h
0x180081ff2  bts     ebx, 1Ch
0x180081ff6  mov     dword ptr [rsp+0D0h+dwFlags], eax; dwFlags
0x180081ffa  lea     r9d, [rax+10h]; cbInput
0x180081ffe  lea     r8, [rbp+57h+pbInput]; pbInput
0x180082002  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x180082009  mov     rcx, [rbp+57h+phProvider]; hObject
0x18008200d  call    cs:__imp_NCryptSetProperty
0x180082013  mov     dword ptr [rsp+0D0h+dwFlags], ebx; dwFlags
0x180082017  xor     r9d, r9d; dwLegacyKeySpec
0x18008201a  mov     r8, r14; pszKeyName
0x18008201d  lea     rdx, [rbp+57h+phKey]; phKey
0x180082021  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180082025  call    cs:__imp_NCryptOpenKey
0x18008202b  mov     [rbp+57h+var_80], eax
0x18008202e  test    eax, eax
0x180082030  jns     short loc_180082054
0x180082032  lea     rcx, base
0x180082039  mov     [rsp+0D0h+var_90], rcx
0x18008203e  lea     rcx, aHresult; "HRESULT"
0x180082045  mov     [rsp+0D0h+var_98], rcx
0x18008204a  mov     [rsp+0D0h+var_A0], 0BBh
0x180082052  jmp     short loc_1800820BB
0x180082054  mov     rcx, r14
0x180082057  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x18008205c  mov     r8d, eax
0x18008205f  mov     rdx, r14
0x180082062  mov     rcx, rsi
0x180082065  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18008206a  mov     rcx, rdi
0x18008206d  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180082072  mov     r8d, eax
0x180082075  lea     rcx, [rsi+8]
0x180082079  mov     rdx, rdi
0x18008207c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180082081  mov     rax, [rbp+57h+phKey]
0x180082085  mov     [rsi+10h], rax
0x180082089  mov     [rbp+57h+phKey], 0
0x180082091  jmp     short loc_1800820DA
0x180082093  mov     eax, 80070057h
0x180082098  mov     [rbp+57h+var_80], eax
0x18008209b  lea     rcx, base
0x1800820a2  mov     [rsp+0D0h+var_90], rcx
0x1800820a7  lea     rcx, aHresult; "HRESULT"
0x1800820ae  mov     [rsp+0D0h+var_98], rcx
0x1800820b3  mov     [rsp+0D0h+var_A0], 0AAh
0x1800820bb  mov     [rsp+0D0h+var_A8], r12
0x1800820c0  mov     ecx, 2
0x1800820c5  mov     dword ptr [rsp+0D0h+dwFlags], eax
0x1800820c9  mov     r9d, ecx
0x1800820cc  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800820d3  xor     edx, edx
0x1800820d5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800820da  mov     rcx, [rbp+57h+phProvider]; hObject
0x1800820de  test    rcx, rcx
0x1800820e1  jz      short loc_1800820E9
0x1800820e3  call    cs:__imp_NCryptFreeObject
0x1800820e9  mov     rcx, [rbp+57h+phKey]; hObject
0x1800820ed  test    rcx, rcx
0x1800820f0  jz      short loc_1800820F8
0x1800820f2  call    cs:__imp_NCryptFreeObject
0x1800820f8  mov     ebx, [rbp+57h+var_80]
0x1800820fb  lea     rcx, [rbp+57h+var_68]
0x1800820ff  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180082104  mov     eax, ebx
0x180082106  mov     rcx, [rbp+57h+var_28]
0x18008210a  xor     rcx, rsp; StackCookie
0x18008210d  call    __security_check_cookie
0x180082112  mov     rbx, [rsp+0D0h+arg_10]
0x18008211a  add     rsp, 0B0h
0x180082121  pop     r14
0x180082123  pop     r12
0x180082125  pop     rdi
0x180082126  pop     rsi
0x180082127  pop     rbp
0x180082128  retn
```
