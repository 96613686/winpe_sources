# GenerateHmacEncapsulateProofOfPossessionTokenPayload(ICloudAPContext *,void *,ushort const *,ushort *,ReportingAccountType,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_UnsignedProofOfPossessionTokenParameter * *,char * *,unsigned __int64 *)

- ea: `0x18000e75c`
- end: `0x18000eae6`
- name: `?GenerateHmacEncapsulateProofOfPossessionTokenPayload@@YAJPEAVICloudAPContext@@PEAXPEBGPEAGW4ReportingAccountType@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAU_UnsignedProofOfPossessionTokenParameter@@PEAPEADPEA_K@Z`
- size: `906`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64, __int64, __int64, _QWORD *, char **, rsize_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013478`

## callees

- `0x180003160`
- `0x180008440`
- `0x18000baac`
- `0x18000d330`
- `0x18000d904`
- `0x18000d998`
- `0x18000d9e4`
- `0x18000deac`
- `0x18000e08c`
- `0x18000e75c`
- `0x18000fcf4`
- `0x180010064`
- `0x180011080`
- `0x180011118`
- `0x180023ea8`
- `0x180028a10`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e8ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e8ac`

## string_xrefs

- `0x18000e863`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000e83e`: `GenerateHmacEncapsulateProofOfPossessionTokenPayload`

## pseudocode

```c
__int64 __fastcall GenerateHmacEncapsulateProofOfPossessionTokenPayload(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        char **a8,
        rsize_t *a9)
{
  __int64 v11; // rbx
  struct IWinApiLite *v12; // r13
  signed int LastError; // eax
  unsigned int *v14; // rbx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // rdx
  int v19; // eax
  char *v20; // rax
  unsigned int v21; // ebx
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  rsize_t DestinationSize; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  char *v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  unsigned int *v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 *v35; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v36; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v37[3]; // [rsp+A8h] [rbp-58h] BYREF
  void **v38; // [rsp+C0h] [rbp-40h] BYREF
  struct _CREDENTIALW *v39[3]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v40[3]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v41[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v42[4]; // [rsp+110h] [rbp+10h] BYREF
  int TokenInformation; // [rsp+130h] [rbp+30h] BYREF
  __int128 v44; // [rsp+134h] [rbp+34h]
  __int128 v45; // [rsp+144h] [rbp+44h]
  __int128 v46; // [rsp+154h] [rbp+54h]
  int v47; // [rsp+164h] [rbp+64h]

  v24 = 0;
  memset(v37, 0, sizeof(v37));
  LODWORD(DestinationSize) = 0;
  memset(v41, 0, sizeof(v41));
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v12 = (struct IWinApiLite *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
  v28 = v11;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  memset(v39, 0, sizeof(v39));
  memset(v40, 0, sizeof(v40));
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v27 = 0;
  TokenInformation = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v26 = 0;
  v42[0] = "GenerateHmacEncapsulateProofOfPossessionTokenPayload";
  v42[1] = &v24;
  v42[2] = 0;
  v42[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "GenerateHmacEncapsulateProofOfPossessionTokenPayload",
    (const char *)0x698,
    0,
    ReturnLength);
  if ( a8 && a9 && a7 )
  {
    *a8 = 0;
    *a9 = 0;
    *a7 = 0;
    if ( GetTokenInformation(a2, TokenStatistics, &TokenInformation, 0x38u, &v26)
      || ((int)GetLastError() > 0
        ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
        : (LastError = GetLastError()),
          v24 = LastError,
          LastError >= 0) )
    {
      v27 = *(_QWORD *)((char *)&v44 + 4);
      v24 = (*((__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, _DWORD, struct _CREDENTIALW **))g_MSACloudAPPluginLsaFunctions
             + 8))(
              &v27,
              1,
              a4,
              1,
              0,
              v39);
      if ( v24 >= 0 )
      {
        v24 = UnChunkProofOfPossessionCacheEntry(v39[0], v37, (unsigned int *)&DestinationSize);
        if ( v24 >= 0 )
        {
          v14 = (unsigned int *)LiveAllocate(0x40u);
          Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(&v32);
          v32 = v14;
          if ( v14 )
          {
            v15 = CredSerializationHelper::DecryptBufferInPlaceForSameLogon(
                    v12,
                    v37[0],
                    (unsigned int *)&DestinationSize);
            v24 = LiveMapHResultToNtStatus(v15);
            if ( v24 >= 0 )
            {
              v16 = DeserializeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(
                      (WlidPropertyBagSerializer *)&v28,
                      v37[0],
                      (unsigned int)DestinationSize,
                      v14);
              v24 = LiveMapHResultToNtStatus(v16);
              if ( v24 >= 0 )
              {
                v38 = &NgcFunctions::`vftable';
                v35 = &v28;
                v36 = v14;
                v17 = LiteCryptUtilities::HmacEncapsulateString(
                        &v38,
                        v14[10],
                        *((_QWORD *)v14 + 7),
                        v14[11],
                        v14[12],
                        *((_QWORD *)v14 + 3),
                        &v29);
                v24 = LiveMapHResultToNtStatus(v17);
                if ( v24 >= 0 )
                {
                  DestinationSize = 0;
                  v19 = StringCchLengthA(v29, v18, &DestinationSize);
                  v24 = LiveMapHResultToNtStatus(v19);
                  if ( v24 >= 0 )
                  {
                    v32 = 0;
                    v33 = 0;
                    *a7 = v14;
                    v20 = v29;
                    v29 = 0;
                    v30 = 0;
                    *a8 = v20;
                    *a9 = DestinationSize;
                    v36 = 0;
                  }
                }
                AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(&v35);
              }
            }
          }
          else
          {
            v24 = -1073741670;
          }
        }
      }
    }
  }
  else
  {
    v24 = -1073741811;
  }
  v21 = v24;
  CTraceFuncW<long>::~CTraceFuncW<long>(v42);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v29);
  Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>::~Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>(v40);
  Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>::~Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>(v39);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(&v32);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(v41);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(v37);
  return v21;
}

```

## disassembly

```asm
0x18000e75c  mov     [rsp-8+arg_10], rbx
0x18000e761  push    rbp
0x18000e762  push    rsi
0x18000e763  push    rdi
0x18000e764  push    r12
0x18000e766  push    r13
0x18000e768  push    r14
0x18000e76a  push    r15
0x18000e76c  lea     rbp, [rsp-70h]
0x18000e771  sub     rsp, 170h
0x18000e778  mov     rax, cs:__security_cookie
0x18000e77f  xor     rax, rsp
0x18000e782  mov     [rbp+0A0h+var_38], rax
0x18000e786  mov     r12, r9
0x18000e789  mov     r15, rdx
0x18000e78c  mov     rdi, [rbp+0A0h+arg_30]
0x18000e793  mov     r14, [rbp+0A0h+arg_38]
0x18000e79a  mov     rsi, [rbp+0A0h+arg_40]
0x18000e7a1  xor     eax, eax
0x18000e7a3  mov     [rsp+1A0h+var_160], eax
0x18000e7a7  mov     [rbp+0A0h+var_F8], rax
0x18000e7ab  mov     [rbp+0A0h+var_E8], rax
0x18000e7af  mov     [rbp+0A0h+var_F0], rax
0x18000e7b3  mov     dword ptr [rsp+1A0h+DestinationSize], eax
0x18000e7b7  mov     [rbp+0A0h+var_A8], rax
0x18000e7bb  mov     [rbp+0A0h+var_98], rax
0x18000e7bf  mov     [rbp+0A0h+var_A0], rax
0x18000e7c3  mov     rax, [rcx]
0x18000e7c6  mov     rax, [rax+8]
0x18000e7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7cf  mov     rbx, rax
0x18000e7d2  mov     rcx, [rax]
0x18000e7d5  mov     rax, [rcx+18h]
0x18000e7d9  mov     rcx, rbx
0x18000e7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e1  mov     r13, rax
0x18000e7e4  mov     [rsp+1A0h+var_140], rbx
0x18000e7e9  xor     ebx, ebx
0x18000e7eb  mov     [rbp+0A0h+var_120], rbx
0x18000e7ef  mov     [rbp+0A0h+var_110], rbx
0x18000e7f3  mov     [rbp+0A0h+var_118], rbx
0x18000e7f7  mov     [rbp+0A0h+var_D8], rbx
0x18000e7fb  mov     [rbp+0A0h+var_C8], rbx
0x18000e7ff  mov     [rbp+0A0h+var_D0], rbx
0x18000e803  mov     [rbp+0A0h+var_C0], rbx
0x18000e807  mov     [rbp+0A0h+var_B0], rbx
0x18000e80b  mov     [rbp+0A0h+var_B8], rbx
0x18000e80f  mov     [rsp+1A0h+var_138], rbx
0x18000e814  mov     [rsp+1A0h+var_128], rbx
0x18000e819  mov     [rsp+1A0h+var_130], rbx
0x18000e81e  mov     [rsp+1A0h+var_148], rbx
0x18000e823  mov     [rbp+0A0h+TokenInformation], ebx
0x18000e826  xorps   xmm0, xmm0
0x18000e829  xor     eax, eax
0x18000e82b  movups  [rbp+0A0h+var_6C], xmm0
0x18000e82f  movups  [rbp+0A0h+var_5C], xmm0
0x18000e833  movups  [rbp+0A0h+var_4C], xmm0
0x18000e837  mov     [rbp+0A0h+var_3C], eax
0x18000e83a  mov     [rsp+1A0h+var_150], ebx
0x18000e83e  lea     rdx, aGeneratehmacen; "GenerateHmacEncapsulateProofOfPossessio"...
0x18000e845  mov     [rbp+0A0h+var_90], rdx
0x18000e849  lea     rax, [rsp+1A0h+var_160]
0x18000e84e  mov     [rbp+0A0h+var_88], rax
0x18000e852  mov     [rbp+0A0h+var_80], rbx
0x18000e856  mov     [rbp+0A0h+var_78], rbx
0x18000e85a  xor     r9d, r9d; unsigned int
0x18000e85d  mov     r8d, 698h; char *
0x18000e863  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000e86a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000e86f  nop
0x18000e870  test    r14, r14
0x18000e873  jz      loc_18000EA6B
0x18000e879  test    rsi, rsi
0x18000e87c  jz      loc_18000EA6B
0x18000e882  test    rdi, rdi
0x18000e885  jz      loc_18000EA6B
0x18000e88b  mov     [r14], rbx
0x18000e88e  mov     [rsi], rbx
0x18000e891  mov     [rdi], rbx
0x18000e894  lea     rax, [rsp+1A0h+var_150]
0x18000e899  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18000e89e  lea     r9d, [rbx+38h]; TokenInformationLength
0x18000e8a2  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x18000e8a6  lea     edx, [rbx+0Ah]; TokenInformationClass
0x18000e8a9  mov     rcx, r15; TokenHandle
0x18000e8ac  call    cs:__imp_GetTokenInformation
0x18000e8b2  test    eax, eax
0x18000e8b4  jnz     short loc_18000E8E2
0x18000e8b6  call    cs:__imp_GetLastError
0x18000e8bc  test    eax, eax
0x18000e8be  jg      short loc_18000E8C8
0x18000e8c0  call    cs:__imp_GetLastError
0x18000e8c6  jmp     short loc_18000E8D6
0x18000e8c8  call    cs:__imp_GetLastError
0x18000e8ce  movzx   eax, ax
0x18000e8d1  or      eax, 0C0070000h
0x18000e8d6  mov     [rsp+1A0h+var_160], eax
0x18000e8da  test    eax, eax
0x18000e8dc  js      loc_18000EA73
0x18000e8e2  mov     rax, qword ptr [rbp+0A0h+var_6C+4]
0x18000e8e6  mov     [rsp+1A0h+var_148], rax
0x18000e8eb  mov     rax, cs:?g_MSACloudAPPluginLsaFunctions@@3PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@EA; _CLOUDAP_SECPKG_FUNCTION_TABLE * g_MSACloudAPPluginLsaFunctions
0x18000e8f2  lea     rcx, [rbp+0A0h+var_D8]
0x18000e8f6  mov     [rsp+1A0h+var_178], rcx
0x18000e8fb  mov     dword ptr [rsp+1A0h+ReturnLength], ebx
0x18000e8ff  mov     edx, 1
0x18000e904  mov     r9d, edx
0x18000e907  mov     r8, r12
0x18000e90a  lea     rcx, [rsp+1A0h+var_148]
0x18000e90f  mov     rax, [rax+40h]
0x18000e913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e918  mov     [rsp+1A0h+var_160], eax
0x18000e91c  test    eax, eax
0x18000e91e  js      loc_18000EA73
0x18000e924  lea     r8, [rsp+1A0h+DestinationSize]; unsigned int *
0x18000e929  lea     rdx, [rbp+0A0h+var_F8]; unsigned __int8 **
0x18000e92d  mov     rcx, [rbp+0A0h+var_D8]; struct _CREDENTIALW *
0x18000e931  call    ?UnChunkProofOfPossessionCacheEntry@@YAJPEAU_CREDENTIALW@@PEAPEAEPEAK@Z; UnChunkProofOfPossessionCacheEntry(_CREDENTIALW *,uchar * *,ulong *)
0x18000e936  mov     [rsp+1A0h+var_160], eax
0x18000e93a  test    eax, eax
0x18000e93c  js      loc_18000EA73
0x18000e942  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e947  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e94c  mov     rbx, rax
0x18000e94f  lea     rcx, [rbp+0A0h+var_120]
0x18000e953  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e958  mov     [rbp+0A0h+var_120], rbx
0x18000e95c  xor     r15d, r15d
0x18000e95f  test    rbx, rbx
0x18000e962  jnz     short loc_18000E971
0x18000e964  mov     [rsp+1A0h+var_160], 0C000009Ah
0x18000e96c  jmp     loc_18000EA73
0x18000e971  lea     r8, [rsp+1A0h+DestinationSize]; unsigned int *
0x18000e976  mov     rdx, [rbp+0A0h+var_F8]; unsigned __int8 *
0x18000e97a  mov     rcx, r13; struct IWinApiLite *
0x18000e97d  call    ?DecryptBufferInPlaceForSameLogon@CredSerializationHelper@@SAJPEAVIWinApiLite@@PEAEPEAK@Z; CredSerializationHelper::DecryptBufferInPlaceForSameLogon(IWinApiLite *,uchar *,ulong *)
0x18000e982  mov     ecx, eax; int
0x18000e984  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e989  mov     [rsp+1A0h+var_160], eax
0x18000e98d  test    eax, eax
0x18000e98f  js      loc_18000EA73
0x18000e995  mov     r9, rbx; pObject
0x18000e998  mov     r8d, dword ptr [rsp+1A0h+DestinationSize]; DestinationSize
0x18000e99d  mov     rdx, [rbp+0A0h+var_F8]; Source
0x18000e9a1  lea     rcx, [rsp+1A0h+var_140]; this
0x18000e9a6  call    ??$DeserializeObject@VUnsignedProofOfPossessionTokenParameterSerializer@@U_UnsignedProofOfPossessionTokenParameter@@@@YAJAEAVUnsignedProofOfPossessionTokenParameterSerializer@@PEAEKPEAU_UnsignedProofOfPossessionTokenParameter@@@Z; DeserializeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(UnsignedProofOfPossessionTokenParameterSerializer &,uchar *,ulong,_UnsignedProofOfPossessionTokenParameter *)
0x18000e9ab  mov     ecx, eax; int
0x18000e9ad  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e9b2  mov     [rsp+1A0h+var_160], eax
0x18000e9b6  test    eax, eax
0x18000e9b8  js      loc_18000EA73
0x18000e9be  lea     rax, ??_7NgcFunctions@@6B@; const NgcFunctions::`vftable'
0x18000e9c5  mov     [rbp+0A0h+var_E0], rax
0x18000e9c9  lea     rax, [rsp+1A0h+var_140]
0x18000e9ce  mov     [rbp+0A0h+var_108], rax
0x18000e9d2  mov     [rbp+0A0h+var_100], rbx
0x18000e9d6  lea     rax, [rsp+1A0h+var_138]
0x18000e9db  mov     [rsp+1A0h+var_170], rax
0x18000e9e0  mov     rax, [rbx+18h]
0x18000e9e4  mov     [rsp+1A0h+var_178], rax
0x18000e9e9  mov     eax, [rbx+30h]
0x18000e9ec  mov     dword ptr [rsp+1A0h+ReturnLength], eax
0x18000e9f0  mov     r9d, [rbx+2Ch]
0x18000e9f4  mov     r8, [rbx+38h]
0x18000e9f8  mov     edx, [rbx+28h]
0x18000e9fb  lea     rcx, [rbp+0A0h+var_E0]
0x18000e9ff  call    ?HmacEncapsulateString@LiteCryptUtilities@@YAJPEAVINgcFunctions@@W4Type@SessionKeyTypes@@PEAEKJPEBDPEAPEAD@Z; LiteCryptUtilities::HmacEncapsulateString(INgcFunctions *,SessionKeyTypes::Type,uchar *,ulong,long,char const *,char * *)
0x18000ea04  mov     ecx, eax; int
0x18000ea06  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000ea0b  mov     [rsp+1A0h+var_160], eax
0x18000ea0f  test    eax, eax
0x18000ea11  js      short loc_18000EA5F
0x18000ea13  mov     [rsp+1A0h+DestinationSize], r15
0x18000ea18  lea     r8, [rsp+1A0h+DestinationSize]; unsigned __int64 *
0x18000ea1d  mov     rcx, [rsp+1A0h+var_138]; char *
0x18000ea22  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000ea27  mov     ecx, eax; int
0x18000ea29  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000ea2e  mov     [rsp+1A0h+var_160], eax
0x18000ea32  test    eax, eax
0x18000ea34  js      short loc_18000EA5F
0x18000ea36  mov     [rbp+0A0h+var_120], r15
0x18000ea3a  mov     [rbp+0A0h+var_118], r15
0x18000ea3e  mov     [rdi], rbx
0x18000ea41  mov     rax, [rsp+1A0h+var_138]
0x18000ea46  mov     [rsp+1A0h+var_138], r15
0x18000ea4b  mov     [rsp+1A0h+var_130], r15
0x18000ea50  mov     [r14], rax
0x18000ea53  mov     rax, [rsp+1A0h+DestinationSize]
0x18000ea58  mov     [rsi], rax
0x18000ea5b  mov     [rbp+0A0h+var_100], r15
0x18000ea5f  lea     rcx, [rbp+0A0h+var_108]
0x18000ea63  call    ??1?$AutoSerializationObject@VUnsignedProofOfPossessionTokenParameterSerializer@@U_UnsignedProofOfPossessionTokenParameter@@@@QEAA@XZ; AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(void)
0x18000ea68  nop
0x18000ea69  jmp     short loc_18000EA73
0x18000ea6b  mov     [rsp+1A0h+var_160], 0C000000Dh
0x18000ea73  mov     ebx, [rsp+1A0h+var_160]
0x18000ea77  lea     rcx, [rbp+0A0h+var_90]
0x18000ea7b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000ea80  nop
0x18000ea81  lea     rcx, [rsp+1A0h+var_138]
0x18000ea86  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x18000ea8b  nop
0x18000ea8c  lea     rcx, [rbp+0A0h+var_C0]
0x18000ea90  call    ??1?$Auto@PEAU_ENCRYPTED_CREDENTIALW@@VEncryptedCredentialFunctor@@VDummyContext@@@@QEAA@XZ; Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>::~Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>(void)
0x18000ea95  nop
0x18000ea96  lea     rcx, [rbp+0A0h+var_D8]
0x18000ea9a  call    ??1?$Auto@PEAU_ENCRYPTED_CREDENTIALW@@VEncryptedCredentialFunctor@@VDummyContext@@@@QEAA@XZ; Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>::~Auto<_ENCRYPTED_CREDENTIALW *,EncryptedCredentialFunctor,DummyContext>(void)
0x18000ea9f  nop
0x18000eaa0  lea     rcx, [rbp+0A0h+var_120]
0x18000eaa4  call    ??1?$Auto@PEAEV?$LiveMemoryFunctor@PEAE@@VDummyContext@@@@QEAA@XZ; Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>::~Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>(void)
0x18000eaa9  nop
0x18000eaaa  lea     rcx, [rbp+0A0h+var_A8]
0x18000eaae  call    ??1?$Auto@PEAEV?$LiveMemoryFunctor@PEAE@@VDummyContext@@@@QEAA@XZ; Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>::~Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>(void)
0x18000eab3  nop
0x18000eab4  lea     rcx, [rbp+0A0h+var_F8]
0x18000eab8  call    ??1?$Auto@PEAEV?$LiveMemoryFunctor@PEAE@@VDummyContext@@@@QEAA@XZ; Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>::~Auto<uchar *,LiveMemoryFunctor<uchar *>,DummyContext>(void)
0x18000eabd  mov     eax, ebx
0x18000eabf  mov     rcx, [rbp+0A0h+var_38]
0x18000eac3  xor     rcx, rsp; StackCookie
0x18000eac6  call    __security_check_cookie
0x18000eacb  mov     rbx, [rsp+1A0h+arg_10]
0x18000ead3  add     rsp, 170h
0x18000eada  pop     r15
0x18000eadc  pop     r14
0x18000eade  pop     r13
0x18000eae0  pop     r12
0x18000eae2  pop     rdi
0x18000eae3  pop     rsi
0x18000eae4  pop     rbp
0x18000eae5  retn
```
