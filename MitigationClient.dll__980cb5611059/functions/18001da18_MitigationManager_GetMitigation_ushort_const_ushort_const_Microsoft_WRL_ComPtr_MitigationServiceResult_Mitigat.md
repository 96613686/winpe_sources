# MitigationManager::GetMitigation(ushort const *,ushort const *,Microsoft::WRL::ComPtr<MitigationServiceResult> &,MitigationContext &)

- ea: `0x18001da18`
- end: `0x18001de81`
- name: `?GetMitigation@MitigationManager@@AEAAJPEBG0AEAV?$ComPtr@VMitigationServiceResult@@@WRL@Microsoft@@AEAVMitigationContext@@@Z`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b9e0`

## callees

- `0x18000a6e0`
- `0x18001055c`
- `0x18001208c`
- `0x1800181b0`
- `0x1800182ac`
- `0x180019764`
- `0x18001a078`
- `0x18001da18`
- `0x1800212bc`
- `0x180021a94`
- `0x18002407c`
- `0x180024a6c`
- `0x18002575c`
- `0x18002b714`
- `0x18002be98`
- `0x18002ec8c`
- `0x18003045c`
- `0x180042f54`
- `0x18004ff28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de23`

## string_xrefs

- `0x18001dc76`: `LastSuccessfulServiceContactTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationManager::GetMitigation(
        __int64 a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ebx
  MitigationRestRequest *v10; // rbx
  const unsigned __int16 *v11; // rdx
  int ServiceData; // edi
  struct MitigationContext *MitigationContext; // rax
  int v14; // eax
  __int64 v15; // rdx
  int DirectoryFullPath; // eax
  __int64 v17; // rdx
  int v18; // eax
  int Mitigations; // eax
  __int64 v20; // rcx
  unsigned int v21; // esi
  char *v22; // rdi
  unsigned __int64 v23; // rbx
  unsigned __int64 j; // r14
  unsigned __int64 v25; // rsi
  char *v26; // rbx
  __int64 v27; // rcx
  unsigned int v28; // edx
  unsigned __int64 i; // rdi
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v38; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h]
  __int64 v40; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int64 v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h]
  MitigationRestRequest *v45; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h] BYREF
  GUID rguid; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v49[42]; // [rsp+D0h] [rbp-30h] BYREF
  char v50; // [rsp+220h] [rbp+120h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v49,
    "GetMitigationsActivity");
  v49[0] = &MitigationTelemetryClass::GetMitigationsActivity::`vftable';
  v50 = 0;
  MitigationTelemetryClass::GetMitigationsActivity::StartActivity(
    (MitigationTelemetryClass::GetMitigationsActivity *)v49,
    v7);
  v45 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  v8 = Microsoft::WRL::Details::MakeAndInitialize<MitigationRestRequest,MitigationRestRequest,>(&v45);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)v8,
      v31);
    goto LABEL_39;
  }
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v34 = 0;
  v10 = v45;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
  v39 = -1;
  v40 = -1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
  v36 = -1;
  v37 = -1;
  ServiceData = MitigationRestRequest::GetServiceData(v10, v11, a2, a3, &v35, &v38, &v34);
  Uuid = (UUID)xmmword_180080698;
  MitigationContext = MitigationExecutionContext::GetMitigationContext(&Uuid);
  *((_DWORD *)MitigationContext + 43) = v34;
  if ( ServiceData == -2145844844 )
  {
    Uuid = 0;
    v14 = StringUtils::StringToGuid(a2, &Uuid);
    v9 = v14;
    if ( v14 < 0 )
    {
      v15 = 883;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
        (const char *)(unsigned int)v14,
        v32);
LABEL_7:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
      goto LABEL_39;
    }
    pv = 0;
    v42 = 0;
    v43 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v42 = -1;
    v43 = -1;
    rguid = Uuid;
    DirectoryFullPath = FileUtils::GetDirectoryFullPath(&rguid, a3, (unsigned __int16 **)&pv);
    v9 = DirectoryFullPath;
    if ( DirectoryFullPath < 0 )
    {
      v17 = 886;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
        (const char *)(unsigned int)DirectoryFullPath,
        v32);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      goto LABEL_7;
    }
    DirectoryFullPath = FileUtils::DeleteDirectory((WCHAR *)pv);
    v9 = DirectoryFullPath;
    if ( DirectoryFullPath < 0 )
    {
      v17 = 888;
      goto LABEL_10;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)ServiceData,
      v32);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
    v9 = ServiceData;
    goto LABEL_39;
  }
  if ( ServiceData < 0 )
    goto LABEL_15;
  v14 = MitigationStateUtils::SetCurrentTimeStamp(L"LastSuccessfulServiceContactTimestamp");
  v9 = v14;
  if ( v14 < 0 )
  {
    v15 = 894;
    goto LABEL_6;
  }
  pv = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v18 = Microsoft::WRL::Details::MakeAndInitialize<MitigationResponsePayload,MitigationResponsePayload,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(
          &v33,
          &v35);
  v9 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)v18,
      v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    goto LABEL_7;
  }
  Mitigations = MitigationResponsePayload::GetMitigations(v33, &pv);
  v21 = Mitigations;
  if ( Mitigations >= 0 )
  {
    v25 = v42;
    if ( v42 )
    {
      if ( v42 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      v26 = (char *)pv;
      v27 = 0;
      if ( &v46 != pv )
      {
        v27 = *(_QWORD *)pv;
        *(_QWORD *)pv = 0;
      }
      v46 = *a4;
      *a4 = v27;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      MitigationTelemetryClass::GetMitigationsActivity::Stop(
        (MitigationTelemetryClass::GetMitigationsActivity *)v49,
        v28);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      if ( v26 )
      {
        for ( i = 0; i < v25; ++i )
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26[8 * i]);
        CoTaskMemFree(v26);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
      v9 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      if ( pv )
        CoTaskMemFree(pv);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
      v9 = -2135164400;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x385,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)Mitigations,
      v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    v22 = (char *)pv;
    if ( pv )
    {
      v23 = 0;
      for ( j = v42; v23 < j; ++v23 )
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22[8 * v23]);
      CoTaskMemFree(v22);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
    v9 = v21;
  }
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  MitigationTelemetryClass::GetMitigationsActivity::~GetMitigationsActivity((MitigationTelemetryClass::GetMitigationsActivity *)v49);
  return v9;
}

```

## disassembly

```asm
0x18001da18  mov     [rsp-8+arg_0], rbx
0x18001da1d  push    rbp
0x18001da1e  push    rsi
0x18001da1f  push    rdi
0x18001da20  push    r12
0x18001da22  push    r13
0x18001da24  push    r14
0x18001da26  push    r15
0x18001da28  lea     rbp, [rsp-140h]
0x18001da30  sub     rsp, 240h
0x18001da37  mov     rax, cs:__security_cookie
0x18001da3e  xor     rax, rsp
0x18001da41  mov     [rbp+170h+var_40], rax
0x18001da48  mov     r14, r9
0x18001da4b  mov     r15, r8
0x18001da4e  mov     rsi, rdx
0x18001da51  lea     rdx, aGetmitigations_0; "GetMitigationsActivity"
0x18001da58  lea     rcx, [rbp+170h+var_1A0]
0x18001da5c  call    ??0?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001da61  lea     rax, ??_7GetMitigationsActivity@MitigationTelemetryClass@@6B@; const MitigationTelemetryClass::GetMitigationsActivity::`vftable'
0x18001da68  mov     [rbp+170h+var_1A0], rax
0x18001da6c  xor     r12d, r12d
0x18001da6f  mov     [rbp+170h+var_50], r12b
0x18001da76  lea     rcx, [rbp+170h+var_1A0]; this
0x18001da7a  call    ?StartActivity@GetMitigationsActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::GetMitigationsActivity::StartActivity(ulong)
0x18001da7f  nop
0x18001da80  mov     [rbp+170h+var_1D0], r12
0x18001da84  lea     rcx, [rbp+170h+var_1D0]
0x18001da88  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001da8d  lea     rcx, [rbp+170h+var_1D0]
0x18001da91  call    ??$MakeAndInitialize@VMitigationRestRequest@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVMitigationRestRequest@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MitigationRestRequest,MitigationRestRequest,>(MitigationRestRequest * *)
0x18001da96  mov     ebx, eax
0x18001da98  test    eax, eax
0x18001da9a  jns     short loc_18001DABC
0x18001da9c  mov     rcx, [rbp+178h]; this
0x18001daa3  mov     r9d, eax; char *
0x18001daa6  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001daad  mov     edx, 362h; void *
0x18001dab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dab7  jmp     loc_18001DE42
0x18001dabc  mov     [rsp+270h+var_220], r12
0x18001dac1  mov     [rsp+270h+var_218], r12
0x18001dac6  mov     [rsp+270h+var_210], r12
0x18001dacb  mov     [rsp+270h+var_208], r12
0x18001dad0  mov     [rsp+270h+var_200], r12
0x18001dad5  mov     [rsp+270h+var_1F8], r12
0x18001dada  mov     [rsp+270h+var_228], r12d
0x18001dadf  mov     rbx, [rbp+170h+var_1D0]
0x18001dae3  lea     rcx, [rsp+270h+var_208]
0x18001dae8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001daed  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001daf1  mov     [rsp+270h+var_200], r13
0x18001daf6  mov     [rsp+270h+var_1F8], r13
0x18001dafb  lea     rcx, [rsp+270h+var_220]
0x18001db00  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001db05  mov     [rsp+270h+var_218], r13
0x18001db0a  mov     [rsp+270h+var_210], r13
0x18001db0f  lea     rax, [rsp+270h+var_228]
0x18001db14  mov     [rsp+270h+var_240], rax; int *
0x18001db19  lea     rax, [rsp+270h+var_208]
0x18001db1e  mov     [rsp+270h+var_248], rax; unsigned __int16 **
0x18001db23  lea     rax, [rsp+270h+var_220]
0x18001db28  mov     [rsp+270h+var_250], rax; int
0x18001db2d  mov     r9, r15; unsigned __int16 *
0x18001db30  mov     r8, rsi; unsigned __int16 *
0x18001db33  mov     rcx, rbx; this
0x18001db36  call    ?GetServiceData@MitigationRestRequest@@AEAAJPEBG00PEAPEAG1AEAH@Z; MitigationRestRequest::GetServiceData(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,int &)
0x18001db3b  mov     edi, eax
0x18001db3d  movups  xmm0, cs:xmmword_180080698
0x18001db44  movdqu  xmmword ptr [rbp+170h+Uuid.Data1], xmm0
0x18001db49  lea     rcx, [rbp+170h+Uuid]; rclsid
0x18001db4d  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@U_GUID@@@Z; MitigationExecutionContext::GetMitigationContext(_GUID)
0x18001db52  mov     edx, [rsp+270h+var_228]
0x18001db56  mov     [rax+0ACh], edx
0x18001db5c  cmp     edi, 80190194h
0x18001db62  jnz     loc_18001DC3A
0x18001db68  xorps   xmm0, xmm0
0x18001db6b  movups  xmmword ptr [rbp+170h+Uuid.Data1], xmm0
0x18001db6f  lea     rdx, [rbp+170h+Uuid]; Uuid
0x18001db73  mov     rcx, rsi; StringUuid
0x18001db76  call    ?StringToGuid@StringUtils@@SAJPEBGAEAU_GUID@@@Z; StringUtils::StringToGuid(ushort const *,_GUID &)
0x18001db7b  mov     ebx, eax
0x18001db7d  test    eax, eax
0x18001db7f  jns     short loc_18001DBB7
0x18001db81  mov     edx, 373h; void *
0x18001db86  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001db8d  mov     r9d, eax; char *
0x18001db90  mov     rcx, [rbp+178h]; this
0x18001db97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db9c  nop
0x18001db9d  lea     rcx, [rsp+270h+var_208]
0x18001dba2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dba7  nop
0x18001dba8  lea     rcx, [rsp+270h+var_220]
0x18001dbad  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dbb2  jmp     loc_18001DE42
0x18001dbb7  mov     [rbp+170h+pv], r12
0x18001dbbb  mov     [rbp+170h+var_1E8], r12
0x18001dbbf  mov     [rbp+170h+var_1E0], r12
0x18001dbc3  lea     rcx, [rbp+170h+pv]
0x18001dbc7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dbcc  mov     [rbp+170h+var_1E8], r13
0x18001dbd0  mov     [rbp+170h+var_1E0], r13
0x18001dbd4  movaps  xmm0, xmmword ptr [rbp+170h+Uuid.Data1]
0x18001dbd8  movdqa  xmmword ptr [rbp+170h+rguid.Data1], xmm0
0x18001dbdd  lea     r8, [rbp+170h+pv]; unsigned __int16 **
0x18001dbe1  mov     rdx, r15; unsigned __int16 *
0x18001dbe4  lea     rcx, [rbp+170h+rguid]; rguid
0x18001dbe8  call    ?GetDirectoryFullPath@FileUtils@@SAJU_GUID@@PEBGPEAPEAG@Z; FileUtils::GetDirectoryFullPath(_GUID,ushort const *,ushort * *)
0x18001dbed  mov     ebx, eax
0x18001dbef  test    eax, eax
0x18001dbf1  jns     short loc_18001DC19
0x18001dbf3  mov     edx, 376h; void *
0x18001dbf8  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001dbff  mov     r9d, eax; char *
0x18001dc02  mov     rcx, [rbp+178h]; this
0x18001dc09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc0e  lea     rcx, [rbp+170h+pv]
0x18001dc12  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dc17  jmp     short loc_18001DB9D
0x18001dc19  mov     rcx, [rbp+170h+pv]; lpFileName
0x18001dc1d  call    ?DeleteDirectory@FileUtils@@SAJPEBG@Z; FileUtils::DeleteDirectory(ushort const *)
0x18001dc22  mov     ebx, eax
0x18001dc24  test    eax, eax
0x18001dc26  jns     short loc_18001DC2F
0x18001dc28  mov     edx, 378h
0x18001dc2d  jmp     short loc_18001DBF8
0x18001dc2f  lea     rcx, [rbp+170h+pv]
0x18001dc33  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dc38  jmp     short loc_18001DC3E
0x18001dc3a  test    edi, edi
0x18001dc3c  jns     short loc_18001DC76
0x18001dc3e  mov     rcx, [rbp+178h]; this
0x18001dc45  mov     r9d, edi; char *
0x18001dc48  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001dc4f  mov     edx, 37Bh; void *
0x18001dc54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc59  nop
0x18001dc5a  lea     rcx, [rsp+270h+var_208]
0x18001dc5f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dc64  nop
0x18001dc65  lea     rcx, [rsp+270h+var_220]
0x18001dc6a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dc6f  mov     ebx, edi
0x18001dc71  jmp     loc_18001DE42
0x18001dc76  lea     rcx, aLastsuccessful; "LastSuccessfulServiceContactTimestamp"
0x18001dc7d  call    ?SetCurrentTimeStamp@MitigationStateUtils@@SAJPEBG@Z; MitigationStateUtils::SetCurrentTimeStamp(ushort const *)
0x18001dc82  mov     ebx, eax
0x18001dc84  test    eax, eax
0x18001dc86  jns     short loc_18001DC92
0x18001dc88  mov     edx, 37Eh
0x18001dc8d  jmp     loc_18001DB86
0x18001dc92  mov     [rbp+170h+pv], r12
0x18001dc96  mov     [rbp+170h+var_1E8], r12
0x18001dc9a  mov     [rbp+170h+var_1E0], r12
0x18001dc9e  mov     [rbp+170h+var_1D8], r12
0x18001dca2  mov     [rsp+270h+var_230], r12
0x18001dca7  lea     rcx, [rsp+270h+var_230]
0x18001dcac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dcb1  lea     rdx, [rsp+270h+var_220]
0x18001dcb6  lea     rcx, [rsp+270h+var_230]
0x18001dcbb  call    ??$MakeAndInitialize@VMitigationResponsePayload@@V1@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVMitigationResponsePayload@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MitigationResponsePayload,MitigationResponsePayload,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(MitigationResponsePayload * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001dcc0  mov     ebx, eax
0x18001dcc2  test    eax, eax
0x18001dcc4  jns     short loc_18001DCF2
0x18001dcc6  mov     rcx, [rbp+178h]; this
0x18001dccd  mov     r9d, eax; char *
0x18001dcd0  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001dcd7  mov     edx, 383h; void *
0x18001dcdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dce1  nop
0x18001dce2  lea     rcx, [rsp+270h+var_230]
0x18001dce7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dcec  nop
0x18001dced  jmp     loc_18001DB9D
0x18001dcf2  lea     rdx, [rbp+170h+pv]
0x18001dcf6  mov     rcx, [rsp+270h+var_230]
0x18001dcfb  call    ?GetMitigations@MitigationResponsePayload@@QEAAJAEAV?$CCoSimpleArray@V?$ComPtr@VMitigationServiceResult@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VMitigationServiceResult@@@WRL@Microsoft@@@@@@@Z; MitigationResponsePayload::GetMitigations(CCoSimpleArray<Microsoft::WRL::ComPtr<MitigationServiceResult>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationServiceResult>>> &)
0x18001dd00  mov     esi, eax
0x18001dd02  test    eax, eax
0x18001dd04  jns     short loc_18001DD79
0x18001dd06  mov     rcx, [rbp+178h]; this
0x18001dd0d  mov     r9d, eax; char *
0x18001dd10  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001dd17  mov     edx, 385h; void *
0x18001dd1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd21  nop
0x18001dd22  lea     rcx, [rsp+270h+var_230]
0x18001dd27  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dd2c  nop
0x18001dd2d  mov     rdi, [rbp+170h+pv]
0x18001dd31  test    rdi, rdi
0x18001dd34  jz      short loc_18001DD5D
0x18001dd36  mov     rbx, r12
0x18001dd39  mov     r14, [rbp+170h+var_1E8]
0x18001dd3d  test    r14, r14
0x18001dd40  jz      short loc_18001DD53
0x18001dd42  lea     rcx, [rdi+rbx*8]
0x18001dd46  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dd4b  inc     rbx
0x18001dd4e  cmp     rbx, r14
0x18001dd51  jb      short loc_18001DD42
0x18001dd53  mov     rcx, rdi; pv
0x18001dd56  call    cs:__imp_CoTaskMemFree
0x18001dd5c  nop
0x18001dd5d  lea     rcx, [rsp+270h+var_208]
0x18001dd62  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dd67  nop
0x18001dd68  lea     rcx, [rsp+270h+var_220]
0x18001dd6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dd72  mov     ebx, esi
0x18001dd74  jmp     loc_18001DE42
0x18001dd79  mov     rsi, [rbp+170h+var_1E8]
0x18001dd7d  cmp     rsi, 1
0x18001dd81  jnb     short loc_18001DDBD
0x18001dd83  lea     rcx, [rsp+270h+var_230]
0x18001dd88  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dd8d  nop
0x18001dd8e  mov     rcx, [rbp+170h+pv]; pv
0x18001dd92  test    rcx, rcx
0x18001dd95  jz      short loc_18001DD9E
0x18001dd97  call    cs:__imp_CoTaskMemFree
0x18001dd9d  nop
0x18001dd9e  lea     rcx, [rsp+270h+var_208]
0x18001dda3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001dda8  nop
0x18001dda9  lea     rcx, [rsp+270h+var_220]
0x18001ddae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ddb3  mov     ebx, 80BBFA10h
0x18001ddb8  jmp     loc_18001DE42
0x18001ddbd  jz      short loc_18001DDC4
0x18001ddbf  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "mitigationArraySize == 1")
0x18001ddc4  mov     rbx, [rbp+170h+pv]
0x18001ddc8  mov     rcx, r12
0x18001ddcb  lea     rax, [rbp+170h+var_1C8]
0x18001ddcf  cmp     rax, rbx
0x18001ddd2  jz      short loc_18001DDDA
0x18001ddd4  mov     rcx, [rbx]
0x18001ddd7  mov     [rbx], r12
0x18001ddda  mov     rax, [r14]
0x18001dddd  mov     [rbp+170h+var_1C8], rax
0x18001dde1  mov     [r14], rcx
0x18001dde4  lea     rcx, [rbp+170h+var_1C8]
0x18001dde8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001dded  lea     rcx, [rbp+170h+var_1A0]; this
0x18001ddf1  call    ?Stop@GetMitigationsActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::GetMitigationsActivity::Stop(ulong)
0x18001ddf6  nop
0x18001ddf7  lea     rcx, [rsp+270h+var_230]
0x18001ddfc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001de01  nop
0x18001de02  test    rbx, rbx
0x18001de05  jz      short loc_18001DE2A
0x18001de07  mov     rdi, r12
0x18001de0a  test    rsi, rsi
0x18001de0d  jz      short loc_18001DE20
0x18001de0f  lea     rcx, [rbx+rdi*8]
0x18001de13  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001de18  inc     rdi
0x18001de1b  cmp     rdi, rsi
0x18001de1e  jb      short loc_18001DE0F
0x18001de20  mov     rcx, rbx; pv
0x18001de23  call    cs:__imp_CoTaskMemFree
0x18001de29  nop
0x18001de2a  lea     rcx, [rsp+270h+var_208]
0x18001de2f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001de34  nop
0x18001de35  lea     rcx, [rsp+270h+var_220]
0x18001de3a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001de3f  mov     ebx, r12d
0x18001de42  lea     rcx, [rbp+170h+var_1D0]
0x18001de46  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001de4b  nop
0x18001de4c  lea     rcx, [rbp+170h+var_1A0]; this
0x18001de50  call    ??1GetMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::GetMitigationsActivity::~GetMitigationsActivity(void)
0x18001de55  mov     eax, ebx
0x18001de57  mov     rcx, [rbp+170h+var_40]
0x18001de5e  xor     rcx, rsp; StackCookie
0x18001de61  call    __security_check_cookie
0x18001de66  mov     rbx, [rsp+270h+arg_0]
0x18001de6e  add     rsp, 240h
0x18001de75  pop     r15
0x18001de77  pop     r14
0x18001de79  pop     r13
0x18001de7b  pop     r12
0x18001de7d  pop     rdi
0x18001de7e  pop     rsi
0x18001de7f  pop     rbp
0x18001de80  retn
```
