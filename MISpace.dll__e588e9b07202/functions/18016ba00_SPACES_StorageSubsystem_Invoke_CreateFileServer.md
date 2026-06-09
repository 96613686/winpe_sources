# SPACES_StorageSubsystem_Invoke_CreateFileServer

- ea: `0x18016ba00`
- end: `0x18016c017`
- name: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- size: `1559`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800045d0`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000c704`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180015b40`
- `0x180015c60`
- `0x1800175f0`
- `0x18001a5e4`
- `0x18001afd0`
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x18016ba00`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016ba7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016badc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bfe7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016ba7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016badc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bfe7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016baa0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016baa0`

## string_xrefs

- `0x18016beef`: `CreateFileServer`
- `0x18016bae8`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016bc23`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016bd58`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016bd87`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016bd9c`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateFileServer(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r8d
  int v12; // r9d
  int v13; // r15d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const char **v20; // rax
  char *v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  const MI_Char *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char **v34; // [rsp+30h] [rbp-D0h]
  const char *v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v37; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const char *v43; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  const char *v46; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v51; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v54; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v55; // [rsp+208h] [rbp+108h]
  char v56; // [rsp+210h] [rbp+110h]
  struct _MI_Instance *v57; // [rsp+218h] [rbp+118h]
  char v58; // [rsp+220h] [rbp+120h]
  GUID ActivityId; // [rsp+240h] [rbp+140h] BYREF
  GUID v60; // [rsp+250h] [rbp+150h]
  GUID v61; // [rsp+260h] [rbp+160h] BYREF

  v40 = a4;
  v47 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v60 = ActivityId;
  v61 = ActivityId;
  EventActivityIdControl(4u, &v61);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v36 = 1139;
    v35 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageSubsystem_Invoke_CreateFileServer",
      (unsigned int)&byte_18035C53F,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xB0u);
  v49 = 0;
  v50 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v48);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v48);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v49) = 13;
    *((_QWORD *)&v49 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v49, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v36 = v15;
        v41 = 1170;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = (char *)&dword_18035CEEC;
LABEL_13:
        v35 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (_DWORD)v21,
          v18,
          v19,
          (__int64)&v35,
          (__int64)v20,
          (__int64)v34);
      }
    }
    else
    {
      if ( !(unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
      {
        v15 = MI_RESULT_NOT_SUPPORTED;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        LODWORD(v42) = 7;
        LODWORD(v43) = 1181;
        v34 = &v42;
        v20 = &v43;
        v21 = byte_18035D90B;
        goto LABEL_13;
      }
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateFileServer_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        LODWORD(v44) = v15;
        LODWORD(v45) = 1188;
        v34 = (const char **)&v44;
        v20 = (const char **)&v45;
        v21 = (char *)word_18035DB6A;
        goto LABEL_13;
      }
      v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
              v38,
              851976,
              a2,
              a7,
              &instance);
      if ( v15 == MI_RESULT_OK )
      {
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_180397B68 > 2 )
        {
          v37 = v15;
          LODWORD(v35) = 1205;
          v39 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_18035D799,
            v23,
            v24,
            (__int64)&v39,
            (__int64)&v35,
            (__int64)&v37);
        }
        goto LABEL_26;
      }
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v46) = v15;
        LODWORD(v39) = 1198;
        v34 = &v46;
        v20 = &v39;
        v21 = byte_18035D9AB;
        goto LABEL_13;
      }
    }
LABEL_26:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v47, a6 + 4, &v54, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v48);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v58 )
        {
          v51 = *v57;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v56 )
        {
          v51 = *v55;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v28 = 0;
        }
        v47 = v28;
        v46 = "FileServer";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateFileServer";
        v42 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)word_18035D0CA,
          v25,
          v26,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v35) = 1238;
    v40 = (unsigned __int16 *)"SPACES_StorageSubsystem_Invoke_CreateFileServer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&byte_18035CF97,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v48);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x18016ba00  mov     [rsp-8+arg_10], rbx
0x18016ba05  push    rbp
0x18016ba06  push    rsi
0x18016ba07  push    rdi
0x18016ba08  push    r12
0x18016ba0a  push    r13
0x18016ba0c  push    r14
0x18016ba0e  push    r15
0x18016ba10  lea     rbp, [rsp-180h]
0x18016ba18  sub     rsp, 280h
0x18016ba1f  mov     rax, cs:__security_cookie
0x18016ba26  xor     rax, rsp
0x18016ba29  mov     [rbp+1B0h+var_40], rax
0x18016ba30  mov     [rbp+1B0h+var_220], r9
0x18016ba34  mov     rdi, rdx
0x18016ba37  mov     r14, rcx
0x18016ba3a  mov     rax, [rbp+1B0h+arg_20]
0x18016ba41  mov     [rbp+1B0h+var_1E8], rax
0x18016ba45  mov     rsi, [rbp+1B0h+arg_28]
0x18016ba4c  mov     r13, [rbp+1B0h+arg_30]
0x18016ba53  xorps   xmm0, xmm0
0x18016ba56  xor     eax, eax
0x18016ba58  movups  xmmword ptr [rbp+1B0h+value], xmm0
0x18016ba5c  movups  xmmword ptr [rbp+1B0h+value+10h], xmm0
0x18016ba60  mov     qword ptr [rbp+1B0h+value+20h], rax
0x18016ba64  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016ba6b  movdqu  xmmword ptr [rbp+1B0h+ActivityId.Data1], xmm0
0x18016ba73  lea     rdx, [rbp+1B0h+ActivityId]; ActivityId
0x18016ba7a  lea     ecx, [rax+1]; ControlCode
0x18016ba7d  call    cs:__imp_EventActivityIdControl
0x18016ba83  lea     r9, [rbp+1B0h+value]; value
0x18016ba87  mov     rcx, rdi; context
0x18016ba8a  call    MI_Context_GetCustomOption_1
0x18016ba8f  xor     ebx, ebx
0x18016ba91  test    eax, eax
0x18016ba93  jnz     short loc_18016BAA6
0x18016ba95  lea     rdx, [rbp+1B0h+ActivityId]; pclsid
0x18016ba9c  mov     rcx, qword ptr [rbp+1B0h+value]; lpsz
0x18016baa0  call    cs:__imp_CLSIDFromString
0x18016baa6  mov     rcx, qword ptr [rbp+1B0h+ActivityId.Data1]
0x18016baad  mov     [rbp+1B0h+var_60], rcx
0x18016bab4  mov     rax, qword ptr [rbp+1B0h+ActivityId.Data4]
0x18016babb  mov     [rbp+1B0h+var_58], rax
0x18016bac2  mov     qword ptr [rbp+1B0h+var_50.Data1], rcx
0x18016bac9  mov     qword ptr [rbp+1B0h+var_50.Data4], rax
0x18016bad0  lea     rdx, [rbp+1B0h+var_50]; ActivityId
0x18016bad7  mov     ecx, 4; ControlCode
0x18016badc  call    cs:__imp_EventActivityIdControl
0x18016bae2  mov     eax, cs:dword_180397B68
0x18016bae8  lea     rcx, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016baef  cmp     eax, 5
0x18016baf2  jbe     short loc_18016BB21
0x18016baf4  mov     [rsp+2B0h+var_238], 473h
0x18016bafc  mov     [rsp+2B0h+var_240], rcx
0x18016bb01  lea     rax, [rsp+2B0h+var_238]
0x18016bb06  mov     [rsp+2B0h+var_288], rax
0x18016bb0b  lea     rax, [rsp+2B0h+var_240]
0x18016bb10  mov     qword ptr [rsp+2B0h+var_290], rax
0x18016bb15  lea     rdx, byte_18035C53F
0x18016bb1c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016bb21  mov     [rbp+1B0h+instance.ft], rbx
0x18016bb28  xor     edx, edx; Val
0x18016bb2a  mov     r8d, 0B0h; Size
0x18016bb30  lea     rcx, [rbp+1B0h+instance.classDecl]; void *
0x18016bb37  call    memset_0
0x18016bb3c  xorps   xmm0, xmm0
0x18016bb3f  xor     eax, eax
0x18016bb41  movups  [rbp+1B0h+var_1C0], xmm0
0x18016bb45  mov     [rbp+1B0h+var_1B0], rax
0x18016bb49  mov     [rbp+1B0h+var_230], rbx
0x18016bb4d  lea     rcx, [rbp+1B0h+var_230]
0x18016bb51  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016bb56  mov     [rbp+1B0h+var_230], rbx
0x18016bb5a  mov     r15d, ebx
0x18016bb5d  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016bb61  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016bb66  mov     rcx, rdi; context
0x18016bb69  call    WspIsRemoteRequest
0x18016bb6e  mov     r12d, eax
0x18016bb71  test    eax, eax
0x18016bb73  jnz     short loc_18016BB98
0x18016bb75  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016bb79  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016bb7e  cmp     [rsi+48h], bl
0x18016bb81  jz      short loc_18016BB95
0x18016bb83  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18016bb87  call    WspIsRemoteInstance
0x18016bb8c  test    al, al
0x18016bb8e  lea     r15d, [r12+1]
0x18016bb93  jnz     short loc_18016BB98
0x18016bb95  mov     r15d, ebx
0x18016bb98  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18016bb9f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18016bba4  mov     ebx, eax
0x18016bba6  test    eax, eax
0x18016bba8  jnz     loc_18016BD9C
0x18016bbae  mov     dword ptr [rbp+1B0h+var_1C0], 0Dh
0x18016bbb5  mov     rax, [rsi+40h]
0x18016bbb9  mov     qword ptr [rbp+1B0h+var_1C0+8], rax
0x18016bbbd  mov     rbx, [r14]
0x18016bbc0  lea     rcx, [rbp+1B0h+var_230]
0x18016bbc4  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016bbc9  mov     [rsp+2B0h+var_290], 1; int
0x18016bbd1  lea     r9, [rbp+1B0h+var_230]; struct ISpWmiObject **
0x18016bbd5  lea     r8, [rbp+1B0h+var_1C0]; struct _SP_OBJECT_ID *
0x18016bbd9  mov     rdx, rdi; context
0x18016bbdc  mov     rcx, rbx; this
0x18016bbdf  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18016bbe4  mov     ebx, eax
0x18016bbe6  test    eax, eax
0x18016bbe8  jz      short loc_18016BC3E
0x18016bbea  mov     eax, cs:dword_180397B68
0x18016bbf0  cmp     eax, 2
0x18016bbf3  jbe     loc_18016BD87
0x18016bbf9  mov     [rsp+2B0h+var_238], ebx
0x18016bbfd  mov     [rbp+1B0h+var_218], 492h
0x18016bc04  lea     rax, [rsp+2B0h+var_238]
0x18016bc09  mov     [rsp+2B0h+var_280], rax
0x18016bc0e  lea     rax, [rbp+1B0h+var_218]
0x18016bc12  lea     rdx, dword_18035CEEC
0x18016bc19  mov     [rsp+2B0h+var_288], rax
0x18016bc1e  lea     rax, [rsp+2B0h+var_240]
0x18016bc23  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016bc2a  mov     [rsp+2B0h+var_240], r13
0x18016bc2f  mov     qword ptr [rsp+2B0h+var_290], rax
0x18016bc34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016bc39  jmp     loc_18016BD8E
0x18016bc3e  mov     r8, [rsi+40h]
0x18016bc42  mov     rdx, rdi
0x18016bc45  mov     rcx, [r14]
0x18016bc48  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18016bc4d  test    eax, eax
0x18016bc4f  jnz     short loc_18016BC83
0x18016bc51  lea     ebx, [rax+7]
0x18016bc54  mov     eax, cs:dword_180397B68
0x18016bc5a  cmp     eax, 2
0x18016bc5d  jbe     loc_18016BD87
0x18016bc63  mov     dword ptr [rbp+1B0h+var_210], ebx
0x18016bc66  mov     dword ptr [rbp+1B0h+var_208], 49Dh
0x18016bc6d  lea     rax, [rbp+1B0h+var_210]
0x18016bc71  mov     [rsp+2B0h+var_280], rax
0x18016bc76  lea     rax, [rbp+1B0h+var_208]
0x18016bc7a  lea     rdx, byte_18035D90B
0x18016bc81  jmp     short loc_18016BC19
0x18016bc83  lea     r8, [rbp+1B0h+instance]; instance
0x18016bc8a  lea     rdx, SPACES_StorageSubsystem_CreateFileServer_rtti; methodDecl
0x18016bc91  mov     rcx, rdi; context
0x18016bc94  call    MI_Context_ConstructParameters
0x18016bc99  mov     ebx, eax
0x18016bc9b  test    eax, eax
0x18016bc9d  jz      short loc_18016BCD1
0x18016bc9f  mov     eax, cs:dword_180397B68
0x18016bca5  cmp     eax, 2
0x18016bca8  jbe     loc_18016BD87
0x18016bcae  mov     dword ptr [rbp+1B0h+var_200], ebx
0x18016bcb1  mov     dword ptr [rbp+1B0h+var_1F8], 4A4h
0x18016bcb8  lea     rax, [rbp+1B0h+var_200]
0x18016bcbc  mov     [rsp+2B0h+var_280], rax
0x18016bcc1  lea     rax, [rbp+1B0h+var_1F8]
0x18016bcc5  lea     rdx, word_18035DB6A
0x18016bccc  jmp     loc_18016BC19
0x18016bcd1  mov     rcx, [rbp+1B0h+var_230]
0x18016bcd5  mov     rax, [rcx]
0x18016bcd8  lea     rdx, [rbp+1B0h+instance]
0x18016bcdf  mov     qword ptr [rsp+2B0h+var_290], rdx
0x18016bce4  mov     r9, r13
0x18016bce7  mov     r8, rdi
0x18016bcea  mov     edx, 0D0008h
0x18016bcef  mov     rax, [rax+30h]
0x18016bcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016bcf8  mov     ebx, eax
0x18016bcfa  test    eax, eax
0x18016bcfc  jz      short loc_18016BD2C
0x18016bcfe  mov     eax, cs:dword_180397B68
0x18016bd04  cmp     eax, 2
0x18016bd07  jbe     short loc_18016BD87
0x18016bd09  mov     dword ptr [rbp+1B0h+var_1F0], ebx
0x18016bd0c  mov     dword ptr [rbp+1B0h+var_228], 4AEh
0x18016bd13  lea     rax, [rbp+1B0h+var_1F0]
0x18016bd17  mov     [rsp+2B0h+var_280], rax
0x18016bd1c  lea     rax, [rbp+1B0h+var_228]
0x18016bd20  lea     rdx, byte_18035D9AB
0x18016bd27  jmp     loc_18016BC19
0x18016bd2c  lea     rdx, [rbp+1B0h+instance]
0x18016bd33  mov     rcx, rdi; self
0x18016bd36  call    MI_Instance_Destruct
0x18016bd3b  mov     ebx, eax
0x18016bd3d  test    eax, eax
0x18016bd3f  jz      short loc_18016BD87
0x18016bd41  mov     eax, cs:dword_180397B68
0x18016bd47  cmp     eax, 2
0x18016bd4a  jbe     short loc_18016BD87
0x18016bd4c  mov     [rsp+2B0h+var_234], ebx
0x18016bd50  mov     dword ptr [rsp+2B0h+var_240], 4B5h
0x18016bd58  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016bd5f  mov     [rbp+1B0h+var_228], r13
0x18016bd63  lea     rax, [rsp+2B0h+var_234]
0x18016bd68  mov     [rsp+2B0h+var_280], rax
0x18016bd6d  lea     rax, [rsp+2B0h+var_240]
0x18016bd72  mov     [rsp+2B0h+var_288], rax
0x18016bd77  lea     rax, [rbp+1B0h+var_228]
0x18016bd7b  lea     rdx, byte_18035D799
0x18016bd82  jmp     loc_18016BC2F
0x18016bd87  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016bd8e  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18016bd95  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18016bd9a  jmp     short loc_18016BDA3
0x18016bd9c  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016bda3  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18016bda7  xor     r14d, r14d
0x18016bdaa  mov     [rsp+2B0h+var_288], r14; unsigned __int16 *
0x18016bdaf  mov     [rsp+2B0h+var_290], ebx; enum _MI_Result
0x18016bdb3  lea     r9, [rbp+1B0h+var_F0]; struct _MI_ConstUint32Field *
0x18016bdba  mov     rdx, [rbp+1B0h+var_1E8]; unsigned __int16 *
0x18016bdbe  mov     rcx, [rbp+1B0h+var_220]; unsigned __int16 *
0x18016bdc2  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016bdc7  test    r12d, r12d
0x18016bdca  jnz     loc_18016BF6D
0x18016bdd0  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016bdd4  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016bdd9  mov     eax, cs:dword_180397B68
0x18016bddf  cmp     eax, 5
0x18016bde2  jbe     loc_18016BF6D
0x18016bde8  mov     rdx, 400000000000h
0x18016bdf2  lea     rcx, dword_180397B68
0x18016bdf9  call    _tlgKeywordOn
0x18016bdfe  test    al, al
0x18016be00  jz      loc_18016BF6D
0x18016be06  cmp     [rbp+1B0h+var_90], r14b
0x18016be0d  jz      short loc_18016BE4A
0x18016be0f  mov     rax, [rbp+1B0h+var_98]
0x18016be16  movups  xmm0, xmmword ptr [rax]
0x18016be19  movaps  xmmword ptr [rbp+1B0h+var_1A0.ft], xmm0
0x18016be1d  movups  xmm1, xmmword ptr [rax+10h]
0x18016be21  movaps  xmmword ptr [rbp+1B0h+var_1A0.serverName], xmm1
0x18016be25  movups  xmm0, xmmword ptr [rax+20h]
0x18016be29  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved], xmm0
0x18016be2d  movups  xmm1, xmmword ptr [rax+30h]
0x18016be31  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved+10h], xmm1
0x18016be35  xor     r8d, r8d; unsigned __int16 *
0x18016be38  lea     rdx, [rbp+1B0h+var_1A0]; struct _MI_Instance
0x18016be3c  lea     rcx, name; "ObjectId"
0x18016be43  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016be48  jmp     short loc_18016BE4D
0x18016be4a  mov     rax, r14
0x18016be4d  mov     [rbp+1B0h+var_220], rax
0x18016be51  cmp     [rbp+1B0h+var_A0], r14b
0x18016be58  jz      short loc_18016BE95
0x18016be5a  mov     rax, [rbp+1B0h+var_A8]
0x18016be61  movups  xmm0, xmmword ptr [rax]
0x18016be64  movaps  xmmword ptr [rbp+1B0h+var_1A0.ft], xmm0
0x18016be68  movups  xmm1, xmmword ptr [rax+10h]
0x18016be6c  movaps  xmmword ptr [rbp+1B0h+var_1A0.serverName], xmm1
0x18016be70  movups  xmm0, xmmword ptr [rax+20h]
0x18016be74  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved], xmm0
0x18016be78  movups  xmm1, xmmword ptr [rax+30h]
0x18016be7c  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved+10h], xmm1
0x18016be80  xor     r8d, r8d; unsigned __int16 *
0x18016be83  lea     rdx, [rbp+1B0h+var_1A0]; struct _MI_Instance
0x18016be87  lea     rcx, name; "ObjectId"
0x18016be8e  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016be93  jmp     short loc_18016BE98
0x18016be95  mov     rax, r14
0x18016be98  mov     [rbp+1B0h+var_1E8], rax
0x18016be9c  lea     rax, aFileserver; "FileServer"
0x18016bea3  mov     [rbp+1B0h+var_1F0], rax
0x18016bea7  mov     rax, [rbp+1B0h+var_1D8]
0x18016beab  sub     rax, [rbp+1B0h+var_1E0]
0x18016beaf  imul    rax, 3E8h
0x18016beb6  xor     edx, edx
0x18016beb8  div     [rbp+1B0h+var_1D0]
0x18016bebc  mov     [rbp+1B0h+var_1F8], rax
0x18016bec0  mov     dword ptr [rsp+2B0h+var_240], ebx
0x18016bec4  mov     al, [rbp+1B0h+var_F0.exists]
0x18016beca  neg     al
0x18016becc  sbb     ecx, ecx
0x18016bece  and     ecx, [rbp+1B0h+var_F0.value]
0x18016bed4  mov     [rsp+2B0h+var_234], ecx
0x18016bed8  mov     dword ptr [rbp+1B0h+var_228], r15d
0x18016bedc  cmp     [rsi+48h], r14b
0x18016bee0  jz      short loc_18016BEE8
0x18016bee2  mov     rax, [rsi+40h]
0x18016bee6  jmp     short loc_18016BEEB
0x18016bee8  mov     rax, r14
0x18016beeb  mov     [rbp+1B0h+var_200], rax
0x18016beef  lea     rax, aCreatefileserv_0; "CreateFileServer"
0x18016bef6  mov     [rbp+1B0h+var_208], rax
0x18016befa  lea     rax, aStoragesubsyst_3; "StorageSubsystem"
0x18016bf01  mov     [rbp+1B0h+var_210], rax
0x18016bf05  lea     rax, [rbp+1B0h+var_220]
0x18016bf09  mov     [rsp+2B0h+var_248], rax
0x18016bf0e  lea     rax, [rbp+1B0h+var_1E8]
0x18016bf12  mov     [rsp+2B0h+var_250], rax
0x18016bf17  lea     rax, [rbp+1B0h+var_1F0]
0x18016bf1b  mov     [rsp+2B0h+var_258], rax
0x18016bf20  lea     rax, [rbp+1B0h+var_1F8]
0x18016bf24  mov     [rsp+2B0h+var_260], rax
0x18016bf29  lea     rax, [rsp+2B0h+var_240]
0x18016bf2e  mov     [rsp+2B0h+var_268], rax
0x18016bf33  lea     rax, [rsp+2B0h+var_234]
  ... truncated ...
```
