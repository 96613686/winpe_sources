# TpmCreateClaimAuthorityAndSubject

- ea: `0x180098970`
- end: `0x180099341`
- name: `TpmCreateClaimAuthorityAndSubject`
- size: `2513`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, TpmObject *this@<rdx>, __int64, rsize_t, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050bb0`

## callees

- `0x18000f240`
- `0x180015660`
- `0x1800157c0`
- `0x18001c308`
- `0x180028bb0`
- `0x180029260`
- `0x18003bbc4`
- `0x180051d88`
- `0x180051e68`
- `0x1800528d0`
- `0x180055bdc`
- `0x180059034`
- `0x18005ac48`
- `0x1800764d0`
- `0x18007704c`
- `0x18009366c`
- `0x180098970`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180099302`
- `bcrypt!BCryptDestroyKey` at `0x180099302`
- `tbs!Tbsi_GetDeviceInfo` at `0x180098f63`
- `tbs!Tbsi_GetDeviceInfo` at `0x180098f63`

## string_xrefs

- `0x1800989c4`: `TpmCreateClaimAuthorityAndSubject`

## pseudocode

```c
__int64 __fastcall TpmCreateClaimAuthorityAndSubject(
        void *a1,
        TpmObject *this,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 *a5,
        rsize_t a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned int *a9)
{
  TpmObject *v13; // rdi
  int Property; // eax
  const unsigned __int16 *v15; // rsi
  int v16; // eax
  int KeyPair; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // r14d
  rsize_t v24; // r13
  int v25; // eax
  unsigned int v26; // r14d
  int v27; // eax
  int v28; // eax
  void *v29; // rdx
  int v30; // eax
  void *v31; // rdx
  int v32; // eax
  int v33; // eax
  void *v34; // rdx
  int v35; // eax
  void *v36; // rdx
  unsigned int v37; // esi
  int v38; // eax
  int v39; // eax
  int v40; // eax
  unsigned int v41; // r15d
  int v42; // eax
  unsigned int v43; // r15d
  char v44; // al
  int v45; // r9d
  unsigned __int8 *v46; // r8
  int v47; // eax
  unsigned int v48; // r9d
  int v49; // eax
  unsigned int v50; // edx
  unsigned int v51; // r8d
  unsigned int v52; // eax
  int v53; // r14d
  unsigned int v54; // ecx
  void *v55; // r8
  __int64 v56; // rcx
  int v57; // r11d
  int v58; // r13d
  int v59; // esi
  __int64 v60; // r14
  int v61; // eax
  int v62; // eax
  int v63; // esi
  unsigned int v64; // ecx
  int v65; // esi
  unsigned int v66; // ecx
  unsigned int v67; // ebx
  rsize_t v69; // [rsp+40h] [rbp-C0h]
  rsize_t v70; // [rsp+40h] [rbp-C0h]
  int DeviceInfo; // [rsp+60h] [rbp-A0h] BYREF
  char v72[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v73; // [rsp+68h] [rbp-98h]
  unsigned int DestinationSize; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 DestinationSize_4; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v76[2]; // [rsp+74h] [rbp-8Ch] BYREF
  int v77; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v78[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v79[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v80; // [rsp+98h] [rbp-68h] BYREF
  rsize_t SourceSize; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v82; // [rsp+A8h] [rbp-58h]
  void *Source; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v84; // [rsp+B8h] [rbp-48h] BYREF
  int v85; // [rsp+C0h] [rbp-40h] BYREF
  int v86; // [rsp+C4h] [rbp-3Ch] BYREF
  TBS_HCONTEXT hContext; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v88; // [rsp+D0h] [rbp-30h]
  rsize_t v89; // [rsp+D8h] [rbp-28h]
  int *v90[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v91; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t String1[136]; // [rsp+110h] [rbp+10h] BYREF

  v82 = a5;
  v88 = a9;
  DeviceInfo = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v90, L"TpmCreateClaimAuthorityAndSubject", &DeviceInfo);
  v86 = 8;
  hContext = 0;
  SourceSize = 0;
  v13 = 0;
  Source = 0;
  v84 = 0;
  v73 = 0;
  memset(v79, 0, sizeof(v79));
  v80 = 0;
  v78[0] = 0;
  DestinationSize_4 = 1;
  v78[1] = 0;
  v72[0] = 0;
  v76[0] = 0;
  DestinationSize = 0;
  v76[1] = 0;
  v77 = 0;
  v91 = 0;
  if ( !a1 || !this || a7 && !a8 || !a9 )
  {
    DeviceInfo = -2147024809;
    v26 = 0;
    goto LABEL_78;
  }
  memset_0(String1, 0, 0x104u);
  v85 = 0;
  Property = ProviderGetProperty((__int64)this, 1u, (__int64)String1, 0x104u, (int)&v85);
  DeviceInfo = SecurityStatusFromHResult(Property);
  if ( DeviceInfo < 0 )
    goto LABEL_77;
  v15 = L"ECDSA";
  if ( wcscmp_0(String1, L"ECDH")
    && wcscmp_0(String1, L"ECDH_P256")
    && wcscmp_0(String1, L"ECDH_P384")
    && wcscmp_0(String1, L"ECDH_P521")
    && wcscmp_0(String1, L"ECDSA")
    && wcscmp_0(String1, L"ECDSA_P256")
    && wcscmp_0(String1, L"ECDSA_P384")
    && wcscmp_0(String1, L"ECDSA_P521") )
  {
    v15 = L"RSA";
  }
  v16 = ProviderGetProperty((__int64)a1, 0x41u, (__int64)&hContext, 8u, (int)&DestinationSize);
  DeviceInfo = SecurityStatusFromHResult(v16);
  if ( DeviceInfo < 0 )
  {
LABEL_77:
    v26 = 0;
    goto LABEL_78;
  }
  KeyPair = ProviderGenerateKeyPair(v15, a1, (void **)&SourceSize);
  v18 = SecurityStatusFromHResult(KeyPair);
  v13 = (TpmObject *)SourceSize;
  DeviceInfo = v18;
  if ( v18 < 0 )
    goto LABEL_62;
  v19 = ProviderSetProperty(SourceSize, 53, &v86, 4);
  DeviceInfo = SecurityStatusFromHResult(v19);
  if ( DeviceInfo < 0 )
    goto LABEL_62;
  if ( a3 )
  {
    if ( a4 )
    {
      v20 = ProviderSetProperty(v13, 80, a3, a4);
      DeviceInfo = SecurityStatusFromHResult(v20);
      if ( DeviceInfo < 0 )
        goto LABEL_62;
    }
  }
  v21 = ProviderFinalizeKeyPair(v13);
  DeviceInfo = SecurityStatusFromHResult(v21);
  if ( DeviceInfo < 0 )
    goto LABEL_62;
  v22 = ProviderGetProperty((__int64)v13, 0x50u, 0, 0, (int)&DestinationSize);
  DeviceInfo = SecurityStatusFromHResult(v22);
  if ( DeviceInfo < 0 )
    goto LABEL_62;
  v23 = DestinationSize;
  v79[1] = DestinationSize;
  v24 = DestinationSize;
  DeviceInfo = AllocateAndZero(&Source, DestinationSize);
  if ( DeviceInfo < 0 )
    goto LABEL_62;
  v25 = ProviderGetProperty((__int64)v13, 0x50u, (__int64)Source, v23, (int)&DestinationSize);
  v26 = 0;
  DeviceInfo = SecurityStatusFromHResult(v25);
  if ( DeviceInfo >= 0 )
  {
    v27 = ProviderGetProperty((__int64)v13, 0x41u, (__int64)v79, 4u, (int)&DestinationSize);
    DeviceInfo = SecurityStatusFromHResult(v27);
    if ( DeviceInfo >= 0 )
    {
      v28 = ProviderGetProperty((__int64)v13, 0xDu, (__int64)&v77, 4u, (int)&DestinationSize);
      DeviceInfo = SecurityStatusFromHResult(v28);
      if ( DeviceInfo >= 0 )
      {
        v30 = ProviderExportKey(v13, v29, L"OpaqueKeyBlob", 0, 0, &DestinationSize, 0);
        DeviceInfo = SecurityStatusFromHResult(v30);
        if ( DeviceInfo >= 0 )
        {
          v73 = DestinationSize;
          v89 = DestinationSize;
          DeviceInfo = AllocateAndZero((void **)&v84, DestinationSize);
          if ( DeviceInfo < 0 )
            goto LABEL_62;
          v26 = v73;
          v32 = ProviderExportKey(v13, v31, L"OpaqueKeyBlob", v84, v73, &DestinationSize, 0);
          DeviceInfo = SecurityStatusFromHResult(v32);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          v33 = ProviderGetProperty((__int64)this, 0x41u, (__int64)&v78[1], 4u, (int)&DestinationSize);
          DeviceInfo = SecurityStatusFromHResult(v33);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          v35 = ProviderExportKey(this, v34, L"OpaqueKeyBlob", 0, 0, &DestinationSize, 0);
          DeviceInfo = SecurityStatusFromHResult(v35);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          v78[0] = DestinationSize;
          SourceSize = DestinationSize;
          DeviceInfo = AllocateAndZero((void **)&v80, DestinationSize);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          v37 = v78[0];
          v38 = ProviderExportKey(this, v36, L"OpaqueKeyBlob", v80, v78[0], &DestinationSize, 0);
          DeviceInfo = SecurityStatusFromHResult(v38);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          DeviceInfo = KeyPolicyNeedsPinForCertify(v80, v37, &DestinationSize_4);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          if ( !DestinationSize_4 )
            goto LABEL_43;
          v39 = ProviderGetProperty((__int64)this, 0x39u, (__int64)v72, 1u, (int)&DestinationSize);
          DeviceInfo = SecurityStatusFromHResult(v39);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          if ( v72[0] )
          {
            v40 = ProviderGetProperty((__int64)this, 0x57u, 0, 0, (int)&DestinationSize);
            DeviceInfo = SecurityStatusFromHResult(v40);
            if ( DeviceInfo < 0 )
              goto LABEL_78;
            v41 = DestinationSize;
            v76[0] = DestinationSize;
            DeviceInfo = AllocateAndZero((void **)&v79[2], DestinationSize);
            if ( DeviceInfo < 0 )
              goto LABEL_78;
            v42 = ProviderGetProperty((__int64)this, 0x57u, *(__int64 *)&v79[2], v41, (int)&DestinationSize);
            DeviceInfo = SecurityStatusFromHResult(v42);
            if ( DeviceInfo < 0 )
              goto LABEL_78;
          }
          else
          {
LABEL_43:
            v41 = v76[0];
          }
          DeviceInfo = Tbsi_GetDeviceInfo(16, &v91);
          if ( DeviceInfo < 0 )
            goto LABEL_78;
          if ( DWORD1(v91) == 1 )
          {
            v43 = a6;
            if ( v82 && (_DWORD)a6 )
            {
              v44 = 1;
              v45 = a6;
            }
            else
            {
              v44 = 0;
              v45 = 20;
            }
            v46 = v82;
            if ( !v44 )
              v46 = (unsigned __int8 *)&::Source;
            LODWORD(v69) = v45;
            v47 = KeyAtt_PcpCertifyKey12(
                    hContext,
                    v79[0],
                    0,
                    0,
                    v78[1],
                    (unsigned __int8 *)(*(_QWORD *)&v79[2] & -(__int64)(v72[0] != 0)),
                    v72[0] != 0 ? v76[0] : 0,
                    v46,
                    v69,
                    0,
                    0,
                    &v76[1]);
          }
          else
          {
            if ( DWORD1(v91) != 2 )
            {
              DeviceInfo = -2144795619;
              goto LABEL_78;
            }
            v48 = v72[0] != 0 ? v41 : 0;
            v43 = a6;
            v49 = PCP20CommonpCertifyKey(
                    this,
                    v13,
                    (unsigned __int8 *)(*(_QWORD *)&v79[2] & -(__int64)(v72[0] != 0)),
                    v48,
                    v82,
                    a6,
                    0,
                    0,
                    &v76[1]);
            v47 = SecurityStatusFromHResult(v49);
          }
          DeviceInfo = v47;
          if ( v47 < 0 )
            goto LABEL_78;
          v50 = v37 + v76[1];
          v51 = v26;
          v52 = v37 + v76[1] + v26;
          v53 = v24;
          v54 = v52 + v24 + 52;
          *v88 = v54;
          if ( !a7 )
            goto LABEL_59;
          if ( a8 < v54 )
          {
            DeviceInfo = -2147024809;
LABEL_59:
            v26 = v51;
            goto LABEL_78;
          }
          *((_DWORD *)a7 + 2) = DWORD1(v91);
          *((_DWORD *)a7 + 6) = v51;
          v55 = Source;
          *((_DWORD *)a7 + 5) = v50 + 24;
          *(_DWORD *)a7 = 1414742347;
          *((_DWORD *)a7 + 1) = 1;
          *((_DWORD *)a7 + 3) = 28;
          *((_DWORD *)a7 + 4) = v24;
          if ( memcpy_s(a7 + 28, v24, v55, v24) )
            goto LABEL_61;
          v56 = (unsigned int)(v24 + 28);
          *(_DWORD *)&a7[v56] = 1396982091;
          *(_DWORD *)&a7[v56 + 4] = DWORD1(v91);
          *(_DWORD *)&a7[v56 + 8] = 24;
          v57 = v76[1] - v77;
          *(_DWORD *)&a7[v56 + 12] = v76[1] - v77;
          *(_DWORD *)&a7[v56 + 16] = v77;
          v58 = v77;
          *(_DWORD *)&a7[v56 + 20] = v37;
          v59 = v53 + 52;
          v60 = (unsigned int)(v53 + 28);
          if ( DWORD1(v91) == 1 )
          {
            LODWORD(v70) = v43;
            v61 = KeyAtt_PcpCertifyKey12(
                    hContext,
                    v79[0],
                    0,
                    0,
                    v78[1],
                    (unsigned __int8 *)(*(_QWORD *)&v79[2] & -(__int64)(v72[0] != 0)),
                    v72[0] != 0 ? v76[0] : 0,
                    v82,
                    v70,
                    &a7[v59],
                    v57 + v58,
                    &DestinationSize);
          }
          else
          {
            if ( DWORD1(v91) != 2 )
            {
              DeviceInfo = -2144795619;
              goto LABEL_62;
            }
            v62 = PCP20CommonpCertifyKey(
                    this,
                    v13,
                    (unsigned __int8 *)(*(_QWORD *)&v79[2] & -(__int64)(v72[0] != 0)),
                    v72[0] != 0 ? v76[0] : 0,
                    v82,
                    v43,
                    &a7[v59],
                    v57 + v58,
                    &DestinationSize);
            v61 = SecurityStatusFromHResult(v62);
          }
          DeviceInfo = v61;
          if ( v61 < 0 )
          {
LABEL_62:
            v26 = v73;
            goto LABEL_78;
          }
          v63 = DestinationSize + v59;
          v64 = *(_DWORD *)&a7[v60 + 20];
          if ( v64 + v63 > a8
            || memcpy_s(&a7[v63], v64, v80, SourceSize)
            || (v65 = v78[0] + v63, v66 = *((_DWORD *)a7 + 6), v66 + v65 > a8)
            || memcpy_s(&a7[v65], v66, v84, v89) )
          {
LABEL_61:
            DeviceInfo = -2147467259;
            goto LABEL_62;
          }
          v26 = v73;
          if ( v65 + v73 != *v88 )
            DeviceInfo = -2147467259;
        }
      }
    }
  }
LABEL_78:
  ZeroAndFree(&Source, v79[1]);
  ZeroAndFree((void **)&v84, v26);
  ZeroAndFree((void **)&v79[2], v76[0]);
  ZeroAndFree((void **)&v80, v78[0]);
  if ( v13 )
    BCryptDestroyKey(v13);
  v67 = DeviceInfo;
  KspFunctionLogger::~KspFunctionLogger(v90);
  return v67;
}

```

## disassembly

```asm
0x180098970  push    rbp
0x180098972  push    rbx
0x180098973  push    rsi
0x180098974  push    rdi
0x180098975  push    r12
0x180098977  push    r13
0x180098979  push    r14
0x18009897b  push    r15
0x18009897d  lea     rbp, [rsp-138h]
0x180098985  sub     rsp, 238h
0x18009898c  mov     rax, cs:__security_cookie
0x180098993  xor     rax, rsp
0x180098996  mov     [rbp+170h+var_50], rax
0x18009899d  mov     rax, [rbp+170h+arg_20]
0x1800989a4  mov     r15, r8
0x1800989a7  mov     rsi, [rbp+170h+arg_40]
0x1800989ae  lea     r8, [rsp+270h+var_210]; int *
0x1800989b3  mov     rbx, [rbp+170h+arg_30]
0x1800989ba  mov     r12, rdx
0x1800989bd  mov     r14, rcx
0x1800989c0  mov     [rbp+170h+var_1C8], rax
0x1800989c4  lea     rdx, aTpmcreateclaim_3; "TpmCreateClaimAuthorityAndSubject"
0x1800989cb  mov     [rbp+170h+var_1A0], rsi
0x1800989cf  lea     rcx, [rbp+170h+var_190]; this
0x1800989d3  mov     [rsp+270h+var_210], 0
0x1800989db  mov     r13d, r9d
0x1800989de  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x1800989e3  xor     eax, eax
0x1800989e5  mov     [rbp+170h+var_1AC], 8
0x1800989ec  mov     [rbp+170h+hContext], rax
0x1800989f0  xorps   xmm0, xmm0
0x1800989f3  mov     [rbp+170h+SourceSize], rax
0x1800989f7  mov     edi, eax
0x1800989f9  mov     [rbp+170h+Source], rax
0x1800989fd  mov     dword ptr [rbp+170h+var_1E4], eax
0x180098a00  mov     [rbp+170h+var_1B8], rax
0x180098a04  mov     [rsp+270h+var_208], eax
0x180098a08  mov     [rbp+170h+var_1E8], eax
0x180098a0b  mov     [rbp+170h+var_1D8], rax
0x180098a0f  mov     [rbp+170h+var_1F0], eax
0x180098a12  mov     byte ptr [rsp+270h+DestinationSize+4], 1
0x180098a17  mov     [rbp+170h+var_1F0+4], eax
0x180098a1a  mov     [rsp+270h+var_20C], al
0x180098a1e  mov     qword ptr [rbp+170h+var_1E4+4], rax
0x180098a22  mov     [rsp+270h+var_1FC], eax
0x180098a26  mov     dword ptr [rsp+270h+DestinationSize], eax
0x180098a2a  mov     [rsp+270h+var_1FC+4], eax
0x180098a2e  mov     [rsp+270h+var_1F4], eax
0x180098a32  movups  [rbp+170h+var_178], xmm0
0x180098a36  test    r14, r14
0x180098a39  jz      loc_1800992B9
0x180098a3f  test    r12, r12
0x180098a42  jz      loc_1800992B9
0x180098a48  test    rbx, rbx
0x180098a4b  jz      short loc_180098A59
0x180098a4d  cmp     [rbp+170h+arg_38], eax
0x180098a53  jz      loc_1800992B9
0x180098a59  test    rsi, rsi
0x180098a5c  jz      loc_1800992B9
0x180098a62  mov     esi, 104h
0x180098a67  lea     rcx, [rbp+170h+String1]; void *
0x180098a6b  mov     r8d, esi; Size
0x180098a6e  xor     edx, edx; Val
0x180098a70  call    memset_0
0x180098a75  lea     rax, [rbp+170h+var_1B0]
0x180098a79  mov     [rbp+170h+var_1B0], edi
0x180098a7c  mov     r9d, esi
0x180098a7f  mov     [rsp+270h+var_250], rax
0x180098a84  lea     r8, [rbp+170h+String1]
0x180098a88  mov     edx, 1
0x180098a8d  mov     rcx, r12
0x180098a90  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098a95  mov     ecx, eax; int
0x180098a97  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098a9c  mov     [rsp+270h+var_210], eax
0x180098aa0  test    eax, eax
0x180098aa2  js      loc_1800992C6
0x180098aa8  lea     rdx, aEcdh; "ECDH"
0x180098aaf  lea     rcx, [rbp+170h+String1]; String1
0x180098ab3  call    wcscmp_0
0x180098ab8  lea     rsi, aEcdsa; "ECDSA"
0x180098abf  test    eax, eax
0x180098ac1  jz      loc_180098B56
0x180098ac7  lea     rdx, aEcdhP256; "ECDH_P256"
0x180098ace  lea     rcx, [rbp+170h+String1]; String1
0x180098ad2  call    wcscmp_0
0x180098ad7  test    eax, eax
0x180098ad9  jz      short loc_180098B56
0x180098adb  lea     rdx, aEcdhP384; "ECDH_P384"
0x180098ae2  lea     rcx, [rbp+170h+String1]; String1
0x180098ae6  call    wcscmp_0
0x180098aeb  test    eax, eax
0x180098aed  jz      short loc_180098B56
0x180098aef  lea     rdx, aEcdhP521; "ECDH_P521"
0x180098af6  lea     rcx, [rbp+170h+String1]; String1
0x180098afa  call    wcscmp_0
0x180098aff  test    eax, eax
0x180098b01  jz      short loc_180098B56
0x180098b03  mov     rdx, rsi; String2
0x180098b06  lea     rcx, [rbp+170h+String1]; String1
0x180098b0a  call    wcscmp_0
0x180098b0f  test    eax, eax
0x180098b11  jz      short loc_180098B56
0x180098b13  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x180098b1a  lea     rcx, [rbp+170h+String1]; String1
0x180098b1e  call    wcscmp_0
0x180098b23  test    eax, eax
0x180098b25  jz      short loc_180098B56
0x180098b27  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x180098b2e  lea     rcx, [rbp+170h+String1]; String1
0x180098b32  call    wcscmp_0
0x180098b37  test    eax, eax
0x180098b39  jz      short loc_180098B56
0x180098b3b  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x180098b42  lea     rcx, [rbp+170h+String1]; String1
0x180098b46  call    wcscmp_0
0x180098b4b  test    eax, eax
0x180098b4d  jz      short loc_180098B56
0x180098b4f  lea     rsi, aRsa; "RSA"
0x180098b56  mov     r9d, 8
0x180098b5c  lea     rax, [rsp+270h+DestinationSize]
0x180098b61  lea     r8, [rbp+170h+hContext]
0x180098b65  mov     [rsp+270h+var_250], rax
0x180098b6a  mov     rcx, r14
0x180098b6d  lea     edx, [r9+39h]
0x180098b71  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098b76  mov     ecx, eax; int
0x180098b78  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098b7d  mov     [rsp+270h+var_210], eax
0x180098b81  test    eax, eax
0x180098b83  js      loc_1800992C6
0x180098b89  lea     r8, [rbp+170h+SourceSize]; void **
0x180098b8d  mov     rdx, r14; void *
0x180098b90  mov     rcx, rsi; unsigned __int16 *
0x180098b93  call    ?ProviderGenerateKeyPair@@YAJPEBGPEAXPEAPEAX@Z; ProviderGenerateKeyPair(ushort const *,void *,void * *)
0x180098b98  mov     ecx, eax; int
0x180098b9a  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098b9f  mov     rdi, [rbp+170h+SourceSize]
0x180098ba3  mov     [rsp+270h+var_210], eax
0x180098ba7  test    eax, eax
0x180098ba9  js      loc_1800990FE
0x180098baf  mov     r9d, 4
0x180098bb5  lea     r8, [rbp+170h+var_1AC]
0x180098bb9  mov     rcx, rdi
0x180098bbc  lea     edx, [r9+31h]
0x180098bc0  call    ?ProviderSetProperty@@YAJPEAXW4KspProp@@PEAEK@Z; ProviderSetProperty(void *,KspProp,uchar *,ulong)
0x180098bc5  mov     ecx, eax; int
0x180098bc7  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098bcc  mov     [rsp+270h+var_210], eax
0x180098bd0  test    eax, eax
0x180098bd2  js      loc_1800990FE
0x180098bd8  mov     esi, 50h ; 'P'
0x180098bdd  test    r15, r15
0x180098be0  jz      short loc_180098C0A
0x180098be2  test    r13d, r13d
0x180098be5  jz      short loc_180098C0A
0x180098be7  mov     r9d, r13d
0x180098bea  mov     r8, r15
0x180098bed  mov     edx, esi
0x180098bef  mov     rcx, rdi
0x180098bf2  call    ?ProviderSetProperty@@YAJPEAXW4KspProp@@PEAEK@Z; ProviderSetProperty(void *,KspProp,uchar *,ulong)
0x180098bf7  mov     ecx, eax; int
0x180098bf9  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098bfe  mov     [rsp+270h+var_210], eax
0x180098c02  test    eax, eax
0x180098c04  js      loc_1800990FE
0x180098c0a  mov     rcx, rdi; this
0x180098c0d  call    ?ProviderFinalizeKeyPair@@YAJPEAX@Z; ProviderFinalizeKeyPair(void *)
0x180098c12  mov     ecx, eax; int
0x180098c14  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098c19  mov     [rsp+270h+var_210], eax
0x180098c1d  test    eax, eax
0x180098c1f  js      loc_1800990FE
0x180098c25  lea     rax, [rsp+270h+DestinationSize]
0x180098c2a  xor     r9d, r9d
0x180098c2d  xor     r8d, r8d
0x180098c30  mov     [rsp+270h+var_250], rax
0x180098c35  mov     edx, esi
0x180098c37  mov     rcx, rdi
0x180098c3a  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098c3f  mov     ecx, eax; int
0x180098c41  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098c46  mov     [rsp+270h+var_210], eax
0x180098c4a  test    eax, eax
0x180098c4c  js      loc_1800990FE
0x180098c52  mov     r14d, dword ptr [rsp+270h+DestinationSize]
0x180098c57  lea     rcx, [rbp+170h+Source]; void **
0x180098c5b  mov     edx, r14d; unsigned __int64
0x180098c5e  mov     dword ptr [rbp+170h+var_1E4], r14d
0x180098c62  mov     r13d, r14d
0x180098c65  call    ?AllocateAndZero@@YAJPEAPEAX_K@Z; AllocateAndZero(void * *,unsigned __int64)
0x180098c6a  mov     [rsp+270h+var_210], eax
0x180098c6e  test    eax, eax
0x180098c70  js      loc_1800990FE
0x180098c76  mov     r8, [rbp+170h+Source]
0x180098c7a  lea     rax, [rsp+270h+DestinationSize]
0x180098c7f  mov     r9d, r14d
0x180098c82  mov     [rsp+270h+var_250], rax
0x180098c87  mov     edx, esi
0x180098c89  mov     rcx, rdi
0x180098c8c  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098c91  mov     ecx, eax; int
0x180098c93  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098c98  xor     r14d, r14d
0x180098c9b  mov     [rsp+270h+var_210], eax
0x180098c9f  test    eax, eax
0x180098ca1  js      loc_1800992C9
0x180098ca7  lea     esi, [r14+4]
0x180098cab  mov     rcx, rdi
0x180098cae  lea     rax, [rsp+270h+DestinationSize]
0x180098cb3  mov     r9d, esi
0x180098cb6  lea     edx, [rsi+3Dh]
0x180098cb9  mov     [rsp+270h+var_250], rax
0x180098cbe  lea     r8, [rbp+170h+var_1E8]
0x180098cc2  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098cc7  mov     ecx, eax; int
0x180098cc9  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098cce  mov     [rsp+270h+var_210], eax
0x180098cd2  test    eax, eax
0x180098cd4  js      loc_1800992C9
0x180098cda  lea     rax, [rsp+270h+DestinationSize]
0x180098cdf  mov     r9d, esi
0x180098ce2  lea     r8, [rsp+270h+var_1F4]
0x180098ce7  mov     [rsp+270h+var_250], rax
0x180098cec  lea     edx, [rsi+9]
0x180098cef  mov     rcx, rdi
0x180098cf2  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098cf7  mov     ecx, eax; int
0x180098cf9  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098cfe  mov     [rsp+270h+var_210], eax
0x180098d02  test    eax, eax
0x180098d04  js      loc_1800992C9
0x180098d0a  lea     rax, [rsp+270h+DestinationSize]
0x180098d0f  mov     dword ptr [rsp+270h+var_240], r14d; unsigned int
0x180098d14  mov     [rsp+270h+var_248], rax; unsigned int *
0x180098d19  lea     r15, aOpaquekeyblob; "OpaqueKeyBlob"
0x180098d20  mov     r8, r15; unsigned __int16 *
0x180098d23  mov     dword ptr [rsp+270h+var_250], r14d; unsigned int
0x180098d28  xor     r9d, r9d; unsigned __int8 *
0x180098d2b  mov     rcx, rdi; void *
0x180098d2e  call    ?ProviderExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; ProviderExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x180098d33  mov     ecx, eax; int
0x180098d35  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098d3a  mov     [rsp+270h+var_210], eax
0x180098d3e  test    eax, eax
0x180098d40  js      loc_1800992C9
0x180098d46  mov     eax, dword ptr [rsp+270h+DestinationSize]
0x180098d4a  lea     rcx, [rbp+170h+var_1B8]; void **
0x180098d4e  mov     edx, eax; unsigned __int64
0x180098d50  mov     [rsp+270h+var_208], eax
0x180098d54  mov     [rbp+170h+var_198], rax
0x180098d58  call    ?AllocateAndZero@@YAJPEAPEAX_K@Z; AllocateAndZero(void * *,unsigned __int64)
0x180098d5d  mov     [rsp+270h+var_210], eax
0x180098d61  test    eax, eax
0x180098d63  js      loc_1800990FE
0x180098d69  mov     r9, [rbp+170h+var_1B8]; unsigned __int8 *
0x180098d6d  lea     rax, [rsp+270h+DestinationSize]
0x180098d72  mov     dword ptr [rsp+270h+var_240], r14d; unsigned int
0x180098d77  mov     r8, r15; unsigned __int16 *
0x180098d7a  mov     r14d, [rsp+270h+var_208]
0x180098d7f  mov     rcx, rdi; void *
0x180098d82  mov     [rsp+270h+var_248], rax; unsigned int *
0x180098d87  mov     dword ptr [rsp+270h+var_250], r14d; unsigned int
0x180098d8c  call    ?ProviderExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; ProviderExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x180098d91  mov     ecx, eax; int
0x180098d93  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098d98  mov     [rsp+270h+var_210], eax
0x180098d9c  test    eax, eax
0x180098d9e  js      loc_1800992C9
0x180098da4  lea     rax, [rsp+270h+DestinationSize]
0x180098da9  mov     r9d, esi
0x180098dac  lea     r8, [rbp+170h+var_1F0+4]
0x180098db0  mov     [rsp+270h+var_250], rax
0x180098db5  lea     edx, [rsi+3Dh]
0x180098db8  mov     rcx, r12
0x180098dbb  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180098dc0  mov     ecx, eax; int
0x180098dc2  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098dc7  mov     [rsp+270h+var_210], eax
0x180098dcb  test    eax, eax
0x180098dcd  js      loc_1800992C9
0x180098dd3  lea     rax, [rsp+270h+DestinationSize]
0x180098dd8  mov     dword ptr [rsp+270h+var_240], 0; unsigned int
0x180098de0  mov     [rsp+270h+var_248], rax; unsigned int *
0x180098de5  xor     r9d, r9d; unsigned __int8 *
0x180098de8  mov     r8, r15; unsigned __int16 *
0x180098deb  mov     dword ptr [rsp+270h+var_250], 0; unsigned int
0x180098df3  mov     rcx, r12; void *
0x180098df6  call    ?ProviderExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; ProviderExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x180098dfb  mov     ecx, eax; int
0x180098dfd  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180098e02  mov     [rsp+270h+var_210], eax
0x180098e06  test    eax, eax
0x180098e08  js      loc_1800992C9
0x180098e0e  mov     eax, dword ptr [rsp+270h+DestinationSize]
0x180098e12  lea     rcx, [rbp+170h+var_1D8]; void **
0x180098e16  mov     edx, eax; unsigned __int64
0x180098e18  mov     [rbp+170h+var_1F0], eax
0x180098e1b  mov     [rbp+170h+SourceSize], rax
0x180098e1f  call    ?AllocateAndZero@@YAJPEAPEAX_K@Z; AllocateAndZero(void * *,unsigned __int64)
  ... truncated ...
```
