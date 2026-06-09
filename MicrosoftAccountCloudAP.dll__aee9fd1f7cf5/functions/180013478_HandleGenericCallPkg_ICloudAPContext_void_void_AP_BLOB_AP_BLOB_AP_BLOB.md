# HandleGenericCallPkg(ICloudAPContext *,void *,void *,_AP_BLOB *,_AP_BLOB *,_AP_BLOB *)

- ea: `0x180013478`
- end: `0x180013c06`
- name: `?HandleGenericCallPkg@@YAJPEAVICloudAPContext@@PEAX1PEAU_AP_BLOB@@22@Z`
- size: `1934`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, int *, void *, struct _AP_BLOB *, struct _AP_BLOB *, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009c00`

## callees

- `0x1800011fc`
- `0x180001630`
- `0x1800016ac`
- `0x180008440`
- `0x18000baac`
- `0x18000d770`
- `0x18000d824`
- `0x18000d904`
- `0x18000d91c`
- `0x18000d9e4`
- `0x18000deac`
- `0x18000e5c0`
- `0x18000e75c`
- `0x18000eaec`
- `0x18000fcf4`
- `0x180010064`
- `0x180010830`
- `0x180010db0`
- `0x1800110e0`
- `0x18001164c`
- `0x180011754`
- `0x180011b44`
- `0x180011fe8`
- `0x18001200c`
- `0x180012024`
- `0x180012178`
- `0x1800121b4`
- `0x1800124a4`
- `0x180013478`
- `0x180015338`
- `0x1800267c0`
- `0x180032010`

## string_xrefs

- `0x1800135c8`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013b11`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013b04`: `User token missing for connected account.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HandleGenericCallPkg(
        struct ICloudAPContext *a1,
        int *a2,
        void *a3,
        struct _AP_BLOB *a4,
        struct _AP_BLOB *a5,
        struct _AP_BLOB *a6)
{
  BOOL v7; // r15d
  __int64 v8; // r13
  __int64 v9; // r14
  __int64 v10; // rsi
  struct _AP_BLOB *v11; // rbx
  struct _AP_BLOB *v12; // r12
  int HmacEncapsulateProofOfPossessionTokenPayload; // edi
  __int64 v14; // rax
  int v15; // ebx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rbx
  int v20; // esi
  __int64 v21; // r8
  int v22; // edi
  int *v23; // rbx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // r8
  int v28; // ebx
  __int64 v29; // rcx
  int v30; // r15d
  __int64 v31; // rsi
  _DWORD *v32; // rbx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  unsigned int v41; // ebx
  const unsigned __int16 *v43; // [rsp+28h] [rbp-E0h]
  __int64 v44; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+70h] [rbp-98h] BYREF
  __int64 v47; // [rsp+78h] [rbp-90h] BYREF
  int v48; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v49[2]; // [rsp+88h] [rbp-80h] BYREF
  ATL::CStringData *v50; // [rsp+98h] [rbp-70h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-68h]
  __int64 v52; // [rsp+A8h] [rbp-60h]
  __int64 v53; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-50h]
  __int64 v55; // [rsp+C0h] [rbp-48h]
  __int64 v56; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-38h]
  __int64 v58; // [rsp+D8h] [rbp-30h]
  __int128 pObject; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v60[3]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v61; // [rsp+108h] [rbp+0h] BYREF
  __int64 v62; // [rsp+110h] [rbp+8h] BYREF
  __int64 v63; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v64[2]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v65[3]; // [rsp+130h] [rbp+28h] BYREF
  _QWORD v66[3]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v67[3]; // [rsp+160h] [rbp+58h] BYREF
  _QWORD v68[3]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v69[3]; // [rsp+190h] [rbp+88h] BYREF
  _QWORD v70[3]; // [rsp+1A8h] [rbp+A0h] BYREF
  _QWORD v71[13]; // [rsp+1C0h] [rbp+B8h] BYREF
  struct ICloudAPContext *v72; // [rsp+238h] [rbp+130h] BYREF
  int *v73; // [rsp+240h] [rbp+138h] BYREF
  void *v74; // [rsp+248h] [rbp+140h] BYREF
  struct _AP_BLOB *v75; // [rsp+250h] [rbp+148h] BYREF

  v75 = a4;
  v74 = a3;
  v73 = a2;
  v72 = a1;
  v7 = 0;
  v44 = 0;
  v8 = 0;
  memset(v70, 0, sizeof(v70));
  v54 = 0;
  memset(v69, 0, sizeof(v69));
  v55 = 0;
  v9 = 0;
  memset(v68, 0, sizeof(v68));
  memset(v67, 0, sizeof(v67));
  v45 = 0;
  memset(v66, 0, sizeof(v66));
  v56 = 0;
  v58 = 0;
  v57 = 0;
  LODWORD(v46) = 0;
  LOBYTE(v75) = 0;
  LOBYTE(v73) = 0;
  v49[0] = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v49[0] + 48LL))(v49[0]);
  v61 = v49[0];
  v53 = v49[0];
  pObject = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v63,
    &qword_18003AB48,
    0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v62,
    &qword_18003AB48,
    0);
  v71[0] = "HandleGenericCallPkg";
  v71[1] = &v44;
  v71[2] = 0;
  v71[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleGenericCallPkg",
    (const char *)0x801,
    0,
    v43);
  if ( !a3 )
    goto LABEL_47;
  v11 = a5;
  if ( !a5 )
    goto LABEL_47;
  v12 = a6;
  if ( !a6 )
    goto LABEL_47;
  LODWORD(v44) = GetAppContainerInfo(a3, (unsigned __int8 *)&v75, (unsigned __int8 *)&v73);
  if ( (int)v44 < 0 )
    goto LABEL_48;
  if ( (_BYTE)v75 == 1 && !(_BYTE)v73 )
  {
    LODWORD(v44) = -1073741790;
    goto LABEL_48;
  }
  if ( (int)DeserializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(
              (WlidPropertyBagSerializer *)&v53,
              *((void **)v11 + 1),
              *(unsigned int *)v11,
              &pObject) < 0 )
  {
LABEL_47:
    LODWORD(v44) = -1073741811;
    goto LABEL_48;
  }
  v64[0] = &v53;
  v64[1] = &pObject;
  LODWORD(v44) = ValidateSerializedProtocolBuffer((struct _WlidPropertyBag *)&pObject);
  if ( (int)v44 < 0 )
  {
    AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>::~AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>(v64);
    goto LABEL_48;
  }
  HmacEncapsulateProofOfPossessionTokenPayload = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v73);
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v73, L"MicrosoftAccount:target=SSO_POP_User:user=", 42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  memset(v60, 0, sizeof(v60));
  memset(v65, 0, sizeof(v65));
  v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v49[0] + 24LL))(v49[0]);
  v50 = (ATL::CStringData *)&AutoImpersonateClient::`vftable';
  LODWORD(v51) = 0;
  v52 = v14;
  v15 = AutoImpersonateClient::Impersonate((AutoImpersonateClient *)&v50, v74);
  if ( v15 >= 0 )
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 32LL))(v10, v60);
  AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v50);
  if ( v15 >= 0 && v60[0] )
    (*(void (__fastcall **)(__int64, _QWORD, char *, _QWORD *))(*(_QWORD *)v10 + 16LL))(
      v10,
      v60[0],
      (char *)&v44 + 4,
      v65);
  if ( *(_DWORD *)(*((_QWORD *)&pObject + 1) + 16LL) > 2u )
  {
    v16 = *(_QWORD *)(*((_QWORD *)&pObject + 1) + 24LL);
    goto LABEL_20;
  }
  if ( HIDWORD(v44) )
  {
    v16 = v65[0];
LABEL_20:
    v17 = ATL::CSimpleStringT<unsigned short,0>::StringLength(v16);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v18, v17);
  }
  v19 = v47;
  v50 = (ATL::CStringData *)(v47 - 24);
  if ( *(int *)(v47 - 24 + 8) <= 0 )
  {
    v23 = v73;
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(&v73, v47);
    LODWORD(v75) = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct _AP_BLOB **))(*(_QWORD *)v10 + 40LL))(
            v10,
            v60[0],
            v19,
            &v75);
    v22 = (int)v75;
    v23 = v73;
    if ( *(v73 - 2) > 1 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Fork(&v73, (unsigned int)*(v73 - 4));
      v23 = v73;
    }
    HmacEncapsulateProofOfPossessionTokenPayload = GenerateHmacEncapsulateProofOfPossessionTokenPayload(
                                                     v72,
                                                     v74,
                                                     v21,
                                                     v23,
                                                     v22);
    v7 = HmacEncapsulateProofOfPossessionTokenPayload >= 0;
    if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
    {
      LODWORD(v73) = (_DWORD)v75;
      v48 = HmacEncapsulateProofOfPossessionTokenPayload;
      LODWORD(v47) = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v24,
        (unsigned int)&byte_180044067,
        v25,
        v26,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v73);
    }
    v8 = v70[0];
    v9 = v68[0];
  }
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v65);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v60);
  ATL::CStringData::Release(v50);
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 6));
  AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>::~AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>(v64);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v75,
    &qword_18003AB48);
  v28 = GenerateHmacEncapsulateProofOfPossessionTokenPayload(
          v72,
          v74,
          v27,
          L"MicrosoftAccount:target=SSO_POP_Device",
          0);
  LODWORD(v74) = v28;
  ATL::CStringData::Release((struct _AP_BLOB *)((char *)v75 - 24));
  v29 = (unsigned int)(v7 + 1);
  if ( v28 < 0 )
    v29 = v7;
  v30 = v29;
  v72 = (struct ICloudAPContext *)v49[0];
  v49[0] = &v72;
  v49[1] = v9;
  v50 = (ATL::CStringData *)&v72;
  v31 = v67[0];
  v51 = v67[0];
  v32 = LiveAllocate(40 * v29);
  Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v66);
  v66[0] = v32;
  if ( !v32 )
  {
    LODWORD(v44) = -1073741670;
LABEL_33:
    AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(&v50);
    AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(v49);
    goto LABEL_48;
  }
  LODWORD(v45) = v30;
  *((_QWORD *)&v45 + 1) = v32;
  v33 = 0;
  if ( v8 && v54 )
  {
    v32[9] = 0;
    **((_QWORD **)&v45 + 1) = *(_QWORD *)v9;
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 8LL) = *(_QWORD *)(v9 + 8);
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 16LL) = *(_QWORD *)(v9 + 16);
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 24LL) = v8;
    *(_DWORD *)(*((_QWORD *)&v45 + 1) + 32LL) = *(_DWORD *)(v9 + 32);
    v33 = 1;
    v32 = (_DWORD *)*((_QWORD *)&v45 + 1);
  }
  v34 = v69[0];
  if ( v69[0] && v55 )
  {
    v35 = 5 * v33;
    v32[2 * v35 + 9] = 1;
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 8 * v35) = *(_QWORD *)v31;
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 8 * v35 + 8) = *(_QWORD *)(v31 + 8);
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 8 * v35 + 16) = *(_QWORD *)(v31 + 16);
    *(_QWORD *)(*((_QWORD *)&v45 + 1) + 8 * v35 + 24) = v34;
    *(_DWORD *)(*((_QWORD *)&v45 + 1) + 8 * v35 + 32) = *(_DWORD *)(v31 + 32);
  }
  v36 = SerializeObject<ProofOfPossessionTokenBagSerializer,_ProofOfPossessionTokenBag>(&v61, &v45, &v56, &v46);
  LODWORD(v44) = LiveMapHResultToNtStatus(v36);
  if ( (int)v44 < 0 )
    goto LABEL_33;
  v37 = v56;
  v56 = 0;
  v57 = 0;
  *((_QWORD *)v12 + 1) = v37;
  *(_DWORD *)v12 = v46;
  AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(&v50);
  AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>::~AutoSerializationObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(v49);
  if ( (int)v74 >= 0 && HmacEncapsulateProofOfPossessionTokenPayload < 0 )
  {
    if ( HIDWORD(v44) )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        0x8F4u,
        L"User token missing for connected account.");
      if ( (unsigned int)dword_18004D048 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
        {
          LODWORD(v72) = HmacEncapsulateProofOfPossessionTokenPayload;
          LOBYTE(v74) = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v38,
            (unsigned int)byte_18004400D,
            v39,
            v40,
            (__int64)&v74,
            (__int64)&v72);
        }
      }
    }
  }
LABEL_48:
  v41 = v44;
  CTraceFuncW<long>::~CTraceFuncW<long>(v71);
  ATL::CStringData::Release((ATL::CStringData *)(v62 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
  Auto<unsigned char *,LocalMIDLPointerFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LocalMIDLPointerFunctor<unsigned char *>,DummyContext>(&v56);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(v66);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(v67);
  Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,LiveMemoryFunctor<unsigned char *>,DummyContext>(v68);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>(v69);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>(v70);
  return v41;
}

```

## disassembly

```asm
0x180013478  mov     rax, rsp
0x18001347b  mov     [rax+20h], r9
0x18001347f  mov     [rax+18h], r8
0x180013483  mov     [rax+10h], rdx
0x180013487  mov     [rax+8], rcx
0x18001348b  push    rbp
0x18001348c  push    rbx
0x18001348d  push    rsi
0x18001348e  push    rdi
0x18001348f  push    r12
0x180013491  push    r13
0x180013493  push    r14
0x180013495  push    r15
0x180013497  lea     rbp, [rax-128h]
0x18001349e  sub     rsp, 1E8h
0x1800134a5  mov     rdi, r8
0x1800134a8  xor     r15d, r15d
0x1800134ab  mov     dword ptr [rsp+220h+var_1D0], r15d
0x1800134b0  mov     r13d, r15d
0x1800134b3  mov     [rbp+120h+var_80], r15
0x1800134ba  mov     [rbp+120h+var_70], r15
0x1800134c1  mov     [rbp+120h+var_78], r15
0x1800134c8  mov     [rbp+120h+var_170], r15
0x1800134cc  mov     [rbp+120h+var_98], r15
0x1800134d3  mov     [rbp+120h+var_88], r15
0x1800134da  mov     [rbp+120h+var_90], r15
0x1800134e1  mov     [rbp+120h+var_168], r15
0x1800134e5  mov     r14d, r15d
0x1800134e8  mov     [rbp+120h+var_B0], r15
0x1800134ec  mov     [rbp+120h+var_A0], r15
0x1800134f3  mov     [rbp+120h+var_A8], r15
0x1800134f7  mov     [rbp+120h+var_C8], r15
0x1800134fb  mov     [rbp+120h+var_B8], r15
0x1800134ff  mov     [rbp+120h+var_C0], r15
0x180013503  xorps   xmm0, xmm0
0x180013506  movups  [rsp+220h+var_1D0+8], xmm0
0x18001350b  mov     [rbp+120h+var_E0], r15
0x18001350f  mov     [rbp+120h+var_D0], r15
0x180013513  mov     [rbp+120h+var_D8], r15
0x180013517  mov     [rbp+120h+var_160], r15
0x18001351b  mov     [rbp+120h+var_150], r15
0x18001351f  mov     [rbp+120h+var_158], r15
0x180013523  mov     dword ptr [rsp+220h+var_1B8], r15d
0x180013528  mov     byte ptr [rbp+120h+arg_18], r15b
0x18001352f  mov     byte ptr [rbp+120h+arg_8], r15b
0x180013536  mov     rax, [rcx]
0x180013539  mov     rax, [rax+8]
0x18001353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013542  mov     rbx, rax
0x180013545  mov     [rbp+120h+var_1A0], rax
0x180013549  mov     rcx, [rax]
0x18001354c  mov     rax, [rcx+30h]
0x180013550  mov     rcx, rbx
0x180013553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013558  mov     rsi, rax
0x18001355b  mov     dword ptr [rsp+220h+var_1D0+4], r15d
0x180013560  mov     [rbp+120h+var_120], rbx
0x180013564  mov     [rbp+120h+var_178], rbx
0x180013568  xorps   xmm0, xmm0
0x18001356b  movups  [rbp+120h+pObject], xmm0
0x18001356f  xor     r8d, r8d
0x180013572  lea     rdx, qword_18003AB48
0x180013579  lea     rcx, [rbp+120h+var_110]
0x18001357d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x180013582  nop
0x180013583  xor     r8d, r8d
0x180013586  lea     rdx, qword_18003AB48
0x18001358d  lea     rcx, [rbp+120h+var_118]
0x180013591  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x180013596  nop
0x180013597  lea     rdx, aHandlegenericc; "HandleGenericCallPkg"
0x18001359e  mov     [rbp+120h+var_68], rdx
0x1800135a5  lea     rax, [rsp+220h+var_1D0]
0x1800135aa  mov     [rbp+120h+var_60], rax
0x1800135b1  mov     [rbp+120h+var_58], r15
0x1800135b8  mov     [rbp+120h+var_50], r15
0x1800135bf  xor     r9d, r9d; unsigned int
0x1800135c2  mov     r8d, 801h; char *
0x1800135c8  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800135cf  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800135d4  nop
0x1800135d5  test    rdi, rdi
0x1800135d8  jz      loc_180013B7A
0x1800135de  mov     rbx, [rbp+120h+arg_20]
0x1800135e5  test    rbx, rbx
0x1800135e8  jz      loc_180013B7A
0x1800135ee  mov     r12, [rbp+120h+arg_28]
0x1800135f5  test    r12, r12
0x1800135f8  jz      loc_180013B7A
0x1800135fe  lea     r8, [rbp+120h+arg_8]; unsigned __int8 *
0x180013605  lea     rdx, [rbp+120h+arg_18]; unsigned __int8 *
0x18001360c  mov     rcx, rdi; TokenHandle
0x18001360f  call    ?GetAppContainerInfo@@YAJPEAXPEAE1@Z; GetAppContainerInfo(void *,uchar *,uchar *)
0x180013614  mov     dword ptr [rsp+220h+var_1D0], eax
0x180013618  test    eax, eax
0x18001361a  js      loc_180013B82
0x180013620  cmp     byte ptr [rbp+120h+arg_18], 1
0x180013627  jnz     short loc_18001363F
0x180013629  cmp     byte ptr [rbp+120h+arg_8], r15b
0x180013630  jnz     short loc_18001363F
0x180013632  mov     dword ptr [rsp+220h+var_1D0], 0C0000022h
0x18001363a  jmp     loc_180013B82
0x18001363f  lea     r9, [rbp+120h+pObject]; pObject
0x180013643  mov     r8d, [rbx]; DestinationSize
0x180013646  mov     rdx, [rbx+8]; Source
0x18001364a  lea     rcx, [rbp+120h+var_178]; this
0x18001364e  call    ??$DeserializeObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@YAJAEAVWlidPropertyBagSerializer@@PEAEKPEAU_WlidPropertyBag@@@Z; DeserializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(WlidPropertyBagSerializer &,uchar *,ulong,_WlidPropertyBag *)
0x180013653  test    eax, eax
0x180013655  js      loc_180013B7A
0x18001365b  lea     rax, [rbp+120h+var_178]
0x18001365f  mov     [rbp+120h+var_108], rax
0x180013663  lea     rax, [rbp+120h+pObject]
0x180013667  mov     [rbp+120h+var_100], rax
0x18001366b  lea     rcx, [rbp+120h+pObject]; struct _WlidPropertyBag *
0x18001366f  call    ?ValidateSerializedProtocolBuffer@@YAJPEAU_WlidPropertyBag@@@Z; ValidateSerializedProtocolBuffer(_WlidPropertyBag *)
0x180013674  mov     dword ptr [rsp+220h+var_1D0], eax
0x180013678  test    eax, eax
0x18001367a  jns     short loc_18001368A
0x18001367c  lea     rcx, [rbp+120h+var_108]
0x180013680  call    ??1?$AutoSerializationObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@QEAA@XZ; AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>::~AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>(void)
0x180013685  jmp     loc_180013B82
0x18001368a  mov     edi, r15d
0x18001368d  lea     rcx, [rbp+120h+arg_8]
0x180013694  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180013699  nop
0x18001369a  mov     r8d, 2Ah ; '*'
0x1800136a0  lea     rdx, aMicrosoftaccou_2; "MicrosoftAccount:target=SSO_POP_User:us"...
0x1800136a7  lea     rcx, [rbp+120h+arg_8]
0x1800136ae  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800136b3  lea     rcx, [rsp+220h+var_1B0]
0x1800136b8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800136bd  nop
0x1800136be  xor     ebx, ebx
0x1800136c0  mov     [rbp+120h+var_138], rbx
0x1800136c4  mov     [rbp+120h+var_128], rbx
0x1800136c8  mov     [rbp+120h+var_130], rbx
0x1800136cc  mov     [rbp+120h+var_F8], rbx
0x1800136d0  mov     [rbp+120h+var_E8], rbx
0x1800136d4  mov     [rbp+120h+var_F0], rbx
0x1800136d8  mov     rcx, [rbp+120h+var_1A0]
0x1800136dc  mov     rax, [rcx]
0x1800136df  mov     rax, [rax+18h]
0x1800136e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136e8  lea     rcx, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x1800136ef  mov     [rbp+120h+var_190], rcx
0x1800136f3  mov     dword ptr [rbp+120h+var_188], ebx
0x1800136f6  mov     [rbp+120h+var_180], rax
0x1800136fa  mov     rdx, [rbp+120h+arg_10]; void *
0x180013701  lea     rcx, [rbp+120h+var_190]; this
0x180013705  call    ?Impersonate@AutoImpersonateClient@@QEAAJPEAX@Z; AutoImpersonateClient::Impersonate(void *)
0x18001370a  mov     ebx, eax
0x18001370c  test    eax, eax
0x18001370e  js      short loc_180013725
0x180013710  mov     rax, [rsi]
0x180013713  lea     rdx, [rbp+120h+var_138]
0x180013717  mov     rcx, rsi
0x18001371a  mov     rax, [rax+20h]
0x18001371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013723  mov     ebx, eax
0x180013725  lea     rcx, [rbp+120h+var_190]; this
0x180013729  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x18001372e  test    ebx, ebx
0x180013730  js      short loc_180013753
0x180013732  mov     rdx, [rbp+120h+var_138]
0x180013736  test    rdx, rdx
0x180013739  jz      short loc_180013753
0x18001373b  mov     rax, [rsi]
0x18001373e  lea     r9, [rbp+120h+var_F8]
0x180013742  lea     r8, [rsp+220h+var_1D0+4]
0x180013747  mov     rcx, rsi
0x18001374a  mov     rax, [rax+10h]
0x18001374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013753  mov     rcx, qword ptr [rbp+120h+pObject+8]
0x180013757  cmp     dword ptr [rcx+10h], 2
0x18001375b  ja      short loc_18001376A
0x18001375d  cmp     dword ptr [rsp+220h+var_1D0+4], 0
0x180013762  jz      short loc_180013783
0x180013764  mov     rcx, [rbp+120h+var_F8]
0x180013768  jmp     short loc_18001376E
0x18001376a  mov     rcx, [rcx+18h]
0x18001376e  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180013773  mov     rdx, rcx
0x180013776  mov     r8d, eax
0x180013779  lea     rcx, [rsp+220h+var_1B0]
0x18001377e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180013783  mov     rbx, [rsp+220h+var_1B0]
0x180013788  lea     rax, [rbx-18h]
0x18001378c  mov     [rbp+120h+var_190], rax
0x180013790  mov     r8d, [rax+8]
0x180013794  test    r8d, r8d
0x180013797  jle     loc_1800138B4
0x18001379d  mov     rdx, rbx
0x1800137a0  lea     rcx, [rbp+120h+arg_8]
0x1800137a7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800137ac  mov     dword ptr [rbp+120h+arg_18], 0
0x1800137b6  mov     rax, [rsi]
0x1800137b9  lea     r9, [rbp+120h+arg_18]
0x1800137c0  mov     r8, rbx
0x1800137c3  mov     rdx, [rbp+120h+var_138]
0x1800137c7  mov     rcx, rsi
0x1800137ca  mov     rax, [rax+28h]
0x1800137ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137d3  mov     esi, eax
0x1800137d5  mov     edi, dword ptr [rbp+120h+arg_18]
0x1800137db  mov     rbx, [rbp+120h+arg_8]
0x1800137e2  cmp     dword ptr [rbx-8], 1
0x1800137e6  jle     short loc_1800137FE
0x1800137e8  mov     edx, [rbx-10h]
0x1800137eb  lea     rcx, [rbp+120h+arg_8]
0x1800137f2  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800137f7  mov     rbx, [rbp+120h+arg_8]
0x1800137fe  lea     rax, [rbp+120h+var_170]
0x180013802  mov     [rsp+40h], rax
0x180013807  lea     rax, [rbp+120h+var_80]
0x18001380e  mov     [rsp+220h+var_1E8], rax
0x180013813  lea     rax, [rbp+120h+var_B0]
0x180013817  mov     [rsp+220h+var_1F0], rax
0x18001381c  mov     dword ptr [rsp+220h+var_200], edi
0x180013820  mov     r9, rbx
0x180013823  mov     rdx, [rbp+120h+arg_10]
0x18001382a  mov     rcx, [rbp+120h+arg_0]
0x180013831  call    ?GenerateHmacEncapsulateProofOfPossessionTokenPayload@@YAJPEAVICloudAPContext@@PEAXPEBGPEAGW4ReportingAccountType@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAU_UnsignedProofOfPossessionTokenParameter@@PEAPEADPEA_K@Z; GenerateHmacEncapsulateProofOfPossessionTokenPayload(ICloudAPContext *,void *,ushort const *,ushort *,ReportingAccountType,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_UnsignedProofOfPossessionTokenParameter * *,char * *,unsigned __int64 *)
0x180013836  mov     edi, eax
0x180013838  mov     r15d, eax
0x18001383b  not     r15d
0x18001383e  shr     r15d, 1Fh
0x180013842  mov     ecx, cs:dword_18004D048
0x180013848  cmp     ecx, 5
0x18001384b  jbe     short loc_1800138A7
0x18001384d  mov     rdx, 400000000000h
0x180013857  lea     rcx, dword_18004D048
0x18001385e  call    _tlgKeywordOn
0x180013863  test    al, al
0x180013865  jz      short loc_1800138A7
0x180013867  mov     eax, dword ptr [rbp+120h+arg_18]
0x18001386d  mov     dword ptr [rbp+120h+arg_8], eax
0x180013873  mov     [rsp+220h+var_1A8], edi
0x180013877  mov     dword ptr [rsp+220h+var_1B0], esi
0x18001387b  lea     rax, [rbp+120h+arg_8]
0x180013882  mov     [rsp+220h+var_1F0], rax
0x180013887  lea     rax, [rsp+220h+var_1A8]
0x18001388c  mov     [rsp+220h+var_1F8], rax
0x180013891  lea     rax, [rsp+220h+var_1B0]
0x180013896  mov     [rsp+220h+var_200], rax
0x18001389b  lea     rdx, byte_180044067
0x1800138a2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800138a7  mov     r13, [rbp+120h+var_80]
0x1800138ae  mov     r14, [rbp+120h+var_B0]
0x1800138b2  jmp     short loc_1800138BB
0x1800138b4  mov     rbx, [rbp+120h+arg_8]
0x1800138bb  lea     rcx, [rbp+120h+var_F8]
0x1800138bf  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800138c4  nop
0x1800138c5  lea     rcx, [rbp+120h+var_138]
0x1800138c9  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800138ce  nop
0x1800138cf  mov     rcx, [rbp+120h+var_190]; this
0x1800138d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800138d8  nop
0x1800138d9  lea     rcx, [rbx-18h]; this
0x1800138dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800138e2  nop
0x1800138e3  lea     rcx, [rbp+120h+var_108]
0x1800138e7  call    ??1?$AutoSerializationObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@QEAA@XZ; AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>::~AutoSerializationObject<WlidPropertyBagSerializer,_WlidPropertyBag>(void)
0x1800138ec  lea     rdx, qword_18003AB48
0x1800138f3  lea     rcx, [rbp+120h+arg_18]
0x1800138fa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800138ff  nop
0x180013900  lea     rax, [rbp+120h+var_168]
0x180013904  mov     [rsp+40h], rax
0x180013909  lea     rax, [rbp+120h+var_98]
0x180013910  mov     [rsp+220h+var_1E8], rax
0x180013915  lea     rax, [rbp+120h+var_C8]
0x180013919  mov     [rsp+220h+var_1F0], rax
0x18001391e  mov     dword ptr [rsp+220h+var_200], 0
0x180013926  lea     r9, aMicrosoftaccou_0; "MicrosoftAccount:target=SSO_POP_Device"
0x18001392d  mov     rdx, [rbp+120h+arg_10]
0x180013934  mov     rcx, [rbp+120h+arg_0]
0x18001393b  call    ?GenerateHmacEncapsulateProofOfPossessionTokenPayload@@YAJPEAVICloudAPContext@@PEAXPEBGPEAGW4ReportingAccountType@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAU_UnsignedProofOfPossessionTokenParameter@@PEAPEADPEA_K@Z; GenerateHmacEncapsulateProofOfPossessionTokenPayload(ICloudAPContext *,void *,ushort const *,ushort *,ReportingAccountType,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_UnsignedProofOfPossessionTokenParameter * *,char * *,unsigned __int64 *)
0x180013940  mov     ebx, eax
0x180013942  mov     dword ptr [rbp+120h+arg_10], eax
0x180013948  mov     rcx, [rbp+120h+arg_18]
0x18001394f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180013953  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013958  lea     ecx, [r15+1]
0x18001395c  test    ebx, ebx
0x18001395e  cmovs   ecx, r15d
0x180013962  mov     r15d, ecx
0x180013965  mov     rax, [rbp+120h+var_1A0]
0x180013969  mov     [rbp+120h+arg_0], rax
0x180013970  lea     rax, [rbp+120h+arg_0]
0x180013977  mov     [rbp+120h+var_1A0], rax
0x18001397b  mov     [rbp+120h+var_198], r14
0x18001397f  lea     rax, [rbp+120h+arg_0]
0x180013986  mov     [rbp+120h+var_190], rax
0x18001398a  mov     rsi, [rbp+120h+var_C8]
0x18001398e  mov     [rbp+120h+var_188], rsi
0x180013992  lea     rcx, [rcx+rcx*4]
0x180013996  shl     rcx, 3; unsigned __int64
0x18001399a  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
  ... truncated ...
```
