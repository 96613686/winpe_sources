# CertificatePrivateKeyHelper::CreateNew(AadContextFunctions *,CertificatePrivateKeyHelper::PrivateKeyUIPolicy const &,bool,CertificatePrivateKey &,_GUID *)

- ea: `0x180081208`
- end: `0x180081620`
- name: `?CreateNew@CertificatePrivateKeyHelper@@SAJPEAVAadContextFunctions@@AEBUPrivateKeyUIPolicy@1@_NAEAVCertificatePrivateKey@@PEAU_GUID@@@Z`
- size: `1048`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, const struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *@<rdx>, bool@<r8b>, struct CertificatePrivateKey *@<r9>, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080ccc`

## callees

- `0x180003c20`
- `0x1800065e8`
- `0x18000685c`
- `0x180006908`
- `0x1800069c0`
- `0x180006ac4`
- `0x180015188`
- `0x180071e14`
- `0x180072934`
- `0x180080e34`
- `0x180081208`
- `0x1800927b4`
- `0x1800a3520`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180081325`
- `tbs!Tbsi_GetDeviceInfo` at `0x180081325`
- `ncrypt!NCryptSetProperty` at `0x1800814e1`
- `ncrypt!NCryptSetProperty` at `0x1800814e1`
- `ncrypt!NCryptFreeObject` at `0x1800813bb`
- `ncrypt!NCryptFreeObject` at `0x1800813cd`
- `ncrypt!NCryptFreeObject` at `0x1800815d7`
- `ncrypt!NCryptFreeObject` at `0x1800815e5`
- `ncrypt!NCryptFreeObject` at `0x1800813bb`
- `ncrypt!NCryptFreeObject` at `0x1800813cd`
- `ncrypt!NCryptFreeObject` at `0x1800815d7`
- `ncrypt!NCryptFreeObject` at `0x1800815e5`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800813ec`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800813ec`

## string_xrefs

- `0x180081530`: `CreateKey failed`
- `0x180081281`: `CertificatePrivateKeyHelper::CreateNew`
- `0x180081408`: `NCryptOpenStorageProvider failed for crypt provider`
- `0x180081586`: `CreateKey succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CertificatePrivateKeyHelper::CreateNew(
        struct AadContextFunctions *a1,
        const struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *a2,
        unsigned __int8 a3,
        struct CertificatePrivateKey *a4,
        struct _GUID *a5)
{
  int v6; // esi
  NCRYPT_HANDLE v8; // rbx
  int DeviceInfo; // eax
  __int64 v10; // r8
  int AadKeyStorageProviders; // r11d
  unsigned int v12; // r12d
  int v13; // r14d
  const wchar_t **v14; // rsi
  const WCHAR *v15; // r15
  SECURITY_STATUS v16; // eax
  const WCHAR *v17; // rcx
  unsigned int v18; // eax
  const WCHAR *v19; // rax
  BYTE *v20; // r15
  unsigned int v21; // ebx
  LPCWSTR *dwFlags; // [rsp+20h] [rbp-A1h]
  DWORD dwFlagsa[2]; // [rsp+20h] [rbp-A1h]
  unsigned __int64 *v25; // [rsp+30h] [rbp-91h]
  unsigned __int64 *v26; // [rsp+30h] [rbp-91h]
  int v27; // [rsp+50h] [rbp-71h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-6Dh] BYREF
  unsigned int v29; // [rsp+58h] [rbp-69h] BYREF
  int v30; // [rsp+5Ch] [rbp-65h]
  NCRYPT_HANDLE hObject; // [rsp+60h] [rbp-61h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-59h] BYREF
  PBYTE pbInput; // [rsp+70h] [rbp-51h]
  struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *v34; // [rsp+78h] [rbp-49h]
  const char *v35[6]; // [rsp+80h] [rbp-41h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-11h] BYREF
  LPCWSTR pszProviderName[2]; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v38; // [rsp+D0h] [rbp+Fh]

  v6 = a3;
  v34 = a2;
  pbInput = (PBYTE)a5;
  v27 = 0;
  hObject = 0;
  v8 = 0;
  v32 = 0;
  v29 = 0;
  v28 = 0;
  v36 = 0;
  *(_OWORD *)pszProviderName = 0;
  v38 = 0;
  v30 = 3;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v35,
    (int)"certificateprivatekey.cpp",
    (int)"CertificatePrivateKeyHelper::CreateNew",
    (int)&v27);
  CertificatePrivateKey::Free(a4);
  if ( a1 )
  {
    RegistryHelper::GetKeyPolicies(a1, &v29, &v28);
    if ( !v29 )
      v29 = 1;
    if ( !v28 )
      v28 = 1;
    DeviceInfo = Tbsi_GetDeviceInfo(16, &v36);
    v10 = 0;
    if ( !DeviceInfo )
      v10 = DWORD1(v36);
    dwFlags = pszProviderName;
    AadKeyStorageProviders = GetAadKeyStorageProviders(v29, v28, v10);
    v27 = AadKeyStorageProviders;
    if ( AadKeyStorageProviders < 0 )
    {
      LODWORD(dwFlags) = AadKeyStorageProviders;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, dwFlags, "certificateprivatekey.cpp", 91, "HRESULT", &base);
      goto LABEL_32;
    }
    v12 = 32 * v6;
    v13 = 0;
    if ( v30 > 0 )
    {
      v14 = (const wchar_t **)((char *)a4 + 8);
      do
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty((char *)a4 + 8);
        if ( hObject )
        {
          NCryptFreeObject(hObject);
          hObject = 0;
        }
        if ( v8 )
        {
          NCryptFreeObject(v8);
          v8 = 0;
          v32 = 0;
        }
        v15 = pszProviderName[v13];
        v16 = NCryptOpenStorageProvider(&hObject, v15, 0);
        v27 = v16;
        if ( v16 >= 0 )
        {
          v18 = ATL::CSimpleStringT<unsigned short,0>::StringLength(v15);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)a4 + 8, v15, v18);
          v19 = &base;
          if ( *v14 )
            v19 = *v14;
          LODWORD(v25) = 118;
          WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "certificateprivatekey.cpp", v25, "Crypt Provider", v19);
          v20 = pbInput;
          if ( pbInput && !wcscmp_0(*v14, L"Microsoft Platform Crypto Provider") )
            NCryptSetProperty(hObject, L"PCP_SESSIONID", v20, 0x10u, 0);
          v27 = CertificatePrivateKeyHelper::CreateKey(
                  hObject,
                  *v14,
                  (const unsigned __int16 *)(*(_QWORD *)a4 & -(__int64)(*(_DWORD *)(*(_QWORD *)a4 - 16LL) != 0)),
                  v34,
                  v12,
                  0,
                  &v32);
          if ( v27 >= 0 )
          {
            LODWORD(v26) = 135;
            WPPTraceLogA(
              4,
              0,
              "%x 0x%08x %s:%u : %s:%ws",
              4,
              0,
              "certificateprivatekey.cpp",
              v26,
              "CreateKey succeeded",
              &base);
            *((_QWORD *)a4 + 2) = v32;
            v8 = 0;
            break;
          }
          ATL::CSimpleStringT<unsigned short,0>::Empty((char *)a4 + 8);
          LODWORD(v26) = 131;
          dwFlagsa[0] = v27;
          WPPTraceLogA(
            3,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            3,
            *(_QWORD *)dwFlagsa,
            "certificateprivatekey.cpp",
            v26,
            "CreateKey failed",
            &base);
          v8 = v32;
        }
        else
        {
          v17 = &base;
          if ( v15 )
            v17 = v15;
          LODWORD(v25) = 113;
          LODWORD(dwFlags) = v16;
          WPPTraceLogA(
            3,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            3,
            dwFlags,
            "certificateprivatekey.cpp",
            v25,
            "NCryptOpenStorageProvider failed for crypt provider",
            v17);
        }
        ++v13;
      }
      while ( v13 < v30 );
    }
  }
  else
  {
    v27 = -2147024809;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -2147024809, "certificateprivatekey.cpp", 71, "HRESULT", &base);
  }
LABEL_32:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( v8 )
    NCryptFreeObject(v8);
  v21 = v27;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v35);
  return v21;
}

```

## disassembly

```asm
0x180081208  mov     [rsp-8+arg_10], rbx
0x18008120d  push    rbp
0x18008120e  push    rsi
0x18008120f  push    rdi
0x180081210  push    r12
0x180081212  push    r13
0x180081214  push    r14
0x180081216  push    r15
0x180081218  lea     rbp, [rsp-1Fh]
0x18008121d  sub     rsp, 0E0h
0x180081224  mov     rax, cs:__security_cookie
0x18008122b  xor     rax, rsp
0x18008122e  mov     [rbp+4Fh+var_38], rax
0x180081232  mov     r13, r9
0x180081235  movzx   esi, r8b
0x180081239  mov     [rbp+4Fh+var_98], rdx
0x18008123d  mov     rdi, rcx
0x180081240  mov     r15, [rbp+4Fh+arg_20]
0x180081244  mov     [rbp+4Fh+pbInput], r15
0x180081248  xor     r15d, r15d
0x18008124b  mov     [rbp+4Fh+var_C0], r15d
0x18008124f  mov     [rbp+4Fh+hObject], r15
0x180081253  mov     ebx, r15d
0x180081256  mov     [rbp+4Fh+var_A8], rbx
0x18008125a  mov     [rbp+4Fh+var_B8], r15d
0x18008125e  mov     [rbp+4Fh+var_BC], r15d
0x180081262  xorps   xmm0, xmm0
0x180081265  movups  [rbp+4Fh+var_60], xmm0
0x180081269  xorps   xmm1, xmm1
0x18008126c  xor     eax, eax
0x18008126e  movups  xmmword ptr [rbp+4Fh+pszProviderName], xmm1
0x180081272  mov     [rbp+4Fh+var_40], rax
0x180081276  mov     [rbp+4Fh+var_B4], 3
0x18008127d  lea     r9, [rbp+4Fh+var_C0]
0x180081281  lea     r8, aCertificatepri_3; "CertificatePrivateKeyHelper::CreateNew"
0x180081288  lea     r14, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x18008128f  mov     rdx, r14
0x180081292  lea     rcx, [rbp+4Fh+var_90]
0x180081296  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18008129b  nop
0x18008129c  mov     rcx, r13; this
0x18008129f  call    ?Free@CertificatePrivateKey@@QEAAXXZ; CertificatePrivateKey::Free(void)
0x1800812a4  test    rdi, rdi
0x1800812a7  jnz     short loc_1800812F5
0x1800812a9  mov     ecx, 80070057h
0x1800812ae  mov     [rbp+4Fh+var_C0], ecx
0x1800812b1  lea     rdi, base
0x1800812b8  mov     [rsp+110h+var_D0], rdi
0x1800812bd  lea     rax, aHresult; "HRESULT"
0x1800812c4  mov     [rsp+110h+var_D8], rax
0x1800812c9  mov     dword ptr [rsp+110h+var_E0], 47h ; 'G'
0x1800812d1  mov     qword ptr [rsp+110h+var_E8], r14
0x1800812d6  mov     [rsp+110h+dwFlags], ecx
0x1800812da  mov     ecx, 2
0x1800812df  mov     r9d, ecx
0x1800812e2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800812e9  xor     edx, edx
0x1800812eb  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800812f0  jmp     loc_1800815CE
0x1800812f5  lea     r8, [rbp+4Fh+var_BC]; unsigned int *
0x1800812f9  lea     rdx, [rbp+4Fh+var_B8]; unsigned int *
0x1800812fd  mov     rcx, rdi; struct AadContextFunctions *
0x180081300  call    ?GetKeyPolicies@RegistryHelper@@SAJPEAVAadContextFunctions@@PEAK1@Z; RegistryHelper::GetKeyPolicies(AadContextFunctions *,ulong *,ulong *)
0x180081305  mov     eax, 1
0x18008130a  cmp     [rbp+4Fh+var_B8], r15d
0x18008130e  jnz     short loc_180081313
0x180081310  mov     [rbp+4Fh+var_B8], eax
0x180081313  cmp     [rbp+4Fh+var_BC], r15d
0x180081317  jnz     short loc_18008131C
0x180081319  mov     [rbp+4Fh+var_BC], eax
0x18008131c  lea     rdx, [rbp+4Fh+var_60]
0x180081320  mov     ecx, 10h
0x180081325  call    cs:__imp_Tbsi_GetDeviceInfo
0x18008132b  mov     r8d, r15d
0x18008132e  test    eax, eax
0x180081330  cmovz   r8d, dword ptr [rbp+4Fh+var_60+4]
0x180081335  lea     rax, [rbp+4Fh+var_B4]
0x180081339  mov     qword ptr [rsp+110h+var_E8], rax
0x18008133e  lea     rax, [rbp+4Fh+pszProviderName]
0x180081342  mov     qword ptr [rsp+110h+dwFlags], rax
0x180081347  mov     edx, [rbp+4Fh+var_BC]
0x18008134a  mov     ecx, [rbp+4Fh+var_B8]
0x18008134d  call    ?GetAadKeyStorageProviders@@YAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@IHQEAPEBGAEAH@Z; GetAadKeyStorageProviders(_KEY_POLICY,_HARDWARE_POLICY,uint,int,ushort const * * const,int &)
0x180081352  mov     r11d, eax
0x180081355  mov     [rbp+4Fh+var_C0], eax
0x180081358  test    eax, eax
0x18008135a  jns     short loc_18008138B
0x18008135c  lea     rdi, base
0x180081363  mov     [rsp+110h+var_D0], rdi
0x180081368  lea     rax, aHresult; "HRESULT"
0x18008136f  mov     [rsp+110h+var_D8], rax
0x180081374  mov     dword ptr [rsp+110h+var_E0], 5Bh ; '['
0x18008137c  mov     qword ptr [rsp+110h+var_E8], r14
0x180081381  mov     [rsp+110h+dwFlags], r11d
0x180081386  jmp     loc_1800812DA
0x18008138b  mov     r12d, esi
0x18008138e  shl     r12d, 5
0x180081392  mov     r14d, r15d
0x180081395  cmp     [rbp+4Fh+var_B4], r15d
0x180081399  jle     loc_1800815CE
0x18008139f  lea     rsi, [r13+8]
0x1800813a3  lea     rdi, base
0x1800813aa  mov     rcx, rsi
0x1800813ad  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800813b2  mov     rcx, [rbp+4Fh+hObject]; hObject
0x1800813b6  test    rcx, rcx
0x1800813b9  jz      short loc_1800813C5
0x1800813bb  call    cs:__imp_NCryptFreeObject
0x1800813c1  mov     [rbp+4Fh+hObject], r15
0x1800813c5  test    rbx, rbx
0x1800813c8  jz      short loc_1800813DA
0x1800813ca  mov     rcx, rbx; hObject
0x1800813cd  call    cs:__imp_NCryptFreeObject
0x1800813d3  mov     rbx, r15
0x1800813d6  mov     [rbp+4Fh+var_A8], rbx
0x1800813da  movsxd  rax, r14d
0x1800813dd  mov     r15, [rbp+rax*8+4Fh+pszProviderName]
0x1800813e2  xor     r8d, r8d; dwFlags
0x1800813e5  mov     rdx, r15; pszProviderName
0x1800813e8  lea     rcx, [rbp+4Fh+hObject]; phProvider
0x1800813ec  call    cs:__imp_NCryptOpenStorageProvider
0x1800813f2  mov     [rbp+4Fh+var_C0], eax
0x1800813f5  test    eax, eax
0x1800813f7  jns     short loc_18008144C
0x1800813f9  mov     rcx, rdi
0x1800813fc  test    r15, r15
0x1800813ff  cmovnz  rcx, r15
0x180081403  mov     [rsp+110h+var_D0], rcx
0x180081408  lea     rcx, aNcryptopenstor_0; "NCryptOpenStorageProvider failed for cr"...
0x18008140f  mov     [rsp+110h+var_D8], rcx
0x180081414  mov     dword ptr [rsp+110h+var_E0], 71h ; 'q'
0x18008141c  lea     rcx, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x180081423  mov     qword ptr [rsp+110h+var_E8], rcx
0x180081428  mov     [rsp+110h+dwFlags], eax
0x18008142c  mov     eax, 3
0x180081431  mov     r9d, eax
0x180081434  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18008143b  xor     edx, edx
0x18008143d  mov     ecx, eax
0x18008143f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180081444  xor     r15d, r15d
0x180081447  jmp     loc_180081572
0x18008144c  mov     rcx, r15
0x18008144f  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180081454  mov     r8d, eax
0x180081457  mov     rdx, r15
0x18008145a  mov     rcx, rsi
0x18008145d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180081462  mov     rax, rdi
0x180081465  xor     ebx, ebx
0x180081467  cmp     [rsi], rbx
0x18008146a  cmovnz  rax, [rsi]
0x18008146e  mov     [rsp+110h+var_D0], rax
0x180081473  lea     rax, aCryptProvider; "Crypt Provider"
0x18008147a  mov     [rsp+110h+var_D8], rax
0x18008147f  mov     dword ptr [rsp+110h+var_E0], 76h ; 'v'
0x180081487  lea     rax, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x18008148e  mov     qword ptr [rsp+110h+var_E8], rax
0x180081493  mov     qword ptr [rsp+110h+dwFlags], rbx
0x180081498  lea     eax, [rbx+4]
0x18008149b  mov     r9d, eax
0x18008149e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800814a5  xor     edx, edx
0x1800814a7  mov     ecx, eax
0x1800814a9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800814ae  mov     r15, [rbp+4Fh+pbInput]
0x1800814b2  test    r15, r15
0x1800814b5  jz      short loc_1800814E7
0x1800814b7  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x1800814be  mov     rcx, [rsi]; String1
0x1800814c1  call    wcscmp_0
0x1800814c6  nop
0x1800814c7  test    eax, eax
0x1800814c9  jnz     short loc_1800814E7
0x1800814cb  mov     [rsp+110h+dwFlags], ebx; dwFlags
0x1800814cf  lea     r9d, [rbx+10h]; cbInput
0x1800814d3  mov     r8, r15; pbInput
0x1800814d6  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x1800814dd  mov     rcx, [rbp+4Fh+hObject]; hObject
0x1800814e1  call    cs:__imp_NCryptSetProperty
0x1800814e7  mov     rcx, [r13+0]
0x1800814eb  mov     eax, [rcx-10h]
0x1800814ee  neg     eax
0x1800814f0  sbb     r8, r8
0x1800814f3  and     r8, rcx; unsigned __int16 *
0x1800814f6  lea     rax, [rbp+4Fh+var_A8]
0x1800814fa  mov     [rsp+110h+var_E0], rax; unsigned __int64 *
0x1800814ff  xor     r15d, r15d
0x180081502  mov     [rsp+110h+var_E8], r15b; bool
0x180081507  mov     [rsp+110h+dwFlags], r12d; unsigned int
0x18008150c  mov     r9, [rbp+4Fh+var_98]; struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *
0x180081510  mov     rdx, [rsi]; unsigned __int16 *
0x180081513  mov     rcx, [rbp+4Fh+hObject]; hProvider
0x180081517  call    ?CreateKey@CertificatePrivateKeyHelper@@SAJ_KPEBG1AEBUPrivateKeyUIPolicy@1@K_NAEA_K@Z; CertificatePrivateKeyHelper::CreateKey(unsigned __int64,ushort const *,ushort const *,CertificatePrivateKeyHelper::PrivateKeyUIPolicy const &,ulong,bool,unsigned __int64 &)
0x18008151c  mov     [rbp+4Fh+var_C0], eax
0x18008151f  test    eax, eax
0x180081521  jns     short loc_180081581
0x180081523  mov     rcx, rsi
0x180081526  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18008152b  mov     [rsp+110h+var_D0], rdi
0x180081530  lea     rax, aCreatekeyFaile; "CreateKey failed"
0x180081537  mov     [rsp+110h+var_D8], rax
0x18008153c  mov     dword ptr [rsp+110h+var_E0], 83h
0x180081544  lea     rax, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x18008154b  mov     qword ptr [rsp+110h+var_E8], rax
0x180081550  mov     eax, [rbp+4Fh+var_C0]
0x180081553  mov     [rsp+110h+dwFlags], eax
0x180081557  lea     eax, [r15+3]
0x18008155b  mov     r9d, eax
0x18008155e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180081565  xor     edx, edx
0x180081567  mov     ecx, eax
0x180081569  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18008156e  mov     rbx, [rbp+4Fh+var_A8]
0x180081572  inc     r14d
0x180081575  cmp     r14d, [rbp+4Fh+var_B4]
0x180081579  jl      loc_1800813AA
0x18008157f  jmp     short loc_1800815CE
0x180081581  mov     [rsp+110h+var_D0], rdi
0x180081586  lea     rax, aCreatekeySucce; "CreateKey succeeded"
0x18008158d  mov     [rsp+110h+var_D8], rax
0x180081592  mov     dword ptr [rsp+110h+var_E0], 87h
0x18008159a  lea     rax, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x1800815a1  mov     qword ptr [rsp+110h+var_E8], rax
0x1800815a6  mov     qword ptr [rsp+110h+dwFlags], r15
0x1800815ab  mov     eax, 4
0x1800815b0  mov     r9d, eax
0x1800815b3  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800815ba  xor     edx, edx
0x1800815bc  mov     ecx, eax
0x1800815be  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800815c3  mov     rax, [rbp+4Fh+var_A8]
0x1800815c7  mov     [r13+10h], rax
0x1800815cb  mov     rbx, r15
0x1800815ce  mov     rcx, [rbp+4Fh+hObject]; hObject
0x1800815d2  test    rcx, rcx
0x1800815d5  jz      short loc_1800815DD
0x1800815d7  call    cs:__imp_NCryptFreeObject
0x1800815dd  test    rbx, rbx
0x1800815e0  jz      short loc_1800815EB
0x1800815e2  mov     rcx, rbx; hObject
0x1800815e5  call    cs:__imp_NCryptFreeObject
0x1800815eb  mov     ebx, [rbp+4Fh+var_C0]
0x1800815ee  lea     rcx, [rbp+4Fh+var_90]
0x1800815f2  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800815f7  mov     eax, ebx
0x1800815f9  mov     rcx, [rbp+4Fh+var_38]
0x1800815fd  xor     rcx, rsp; StackCookie
0x180081600  call    __security_check_cookie
0x180081605  mov     rbx, [rsp+110h+arg_10]
0x18008160d  add     rsp, 0E0h
0x180081614  pop     r15
0x180081616  pop     r14
0x180081618  pop     r13
0x18008161a  pop     r12
0x18008161c  pop     rdi
0x18008161d  pop     rsi
0x18008161e  pop     rbp
0x18008161f  retn
```
