# SPACES_StoragePool_Invoke_CreateVirtualDisk2

- ea: `0x180156880`
- end: `0x180156e9a`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- size: `1562`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x180156880`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801568fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015695c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156e6a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801568fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015695c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156e6a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156920`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156920`

## string_xrefs

- `0x180156d72`: `CreateVirtualDisk`
- `0x180156968`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x180156aa3`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x180156bdb`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x180156c0a`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x180156c1f`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVirtualDisk2(
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
  struct _MI_Instance *v55; // [rsp+2D0h] [rbp+1D0h]
  char v56; // [rsp+2D8h] [rbp+1D8h]
  struct _MI_Instance *v57; // [rsp+2E0h] [rbp+1E0h]
  char v58; // [rsp+2E8h] [rbp+1E8h]
  GUID ActivityId; // [rsp+300h] [rbp+200h] BYREF
  GUID v60; // [rsp+310h] [rbp+210h]
  GUID v61; // [rsp+320h] [rbp+220h] BYREF

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
    v36 = 256;
    v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVirtualDisk2",
      (unsigned int)word_180354492,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x178u);
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
    LODWORD(v49) = 11;
    *((_QWORD *)&v49 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v49, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v36 = v15;
        v41 = 288;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = (char *)&dword_180356DCC;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
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
        LODWORD(v43) = 299;
        v34 = &v42;
        v20 = &v43;
        v21 = byte_180356EA5;
        goto LABEL_13;
      }
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        LODWORD(v44) = v15;
        LODWORD(v45) = 307;
        v34 = (const char **)&v44;
        v20 = (const char **)&v45;
        v21 = byte_180355E3D;
        goto LABEL_13;
      }
      v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
              v38,
              720916,
              a2,
              a7,
              &instance);
      if ( v15 == MI_RESULT_OK )
      {
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_180397B68 > 2 )
        {
          v37 = v15;
          LODWORD(v35) = 326;
          v39 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&byte_180355BA7,
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
        LODWORD(v39) = 318;
        v34 = &v46;
        v20 = &v39;
        v21 = (char *)&word_180356616;
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
        v46 = "VirtualDisk";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateVirtualDisk";
        v42 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)&byte_180355FAF,
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
    LODWORD(v35) = 359;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&dword_18035483C,
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
0x180156880  mov     [rsp-8+arg_10], rbx
0x180156885  push    rbp
0x180156886  push    rsi
0x180156887  push    rdi
0x180156888  push    r12
0x18015688a  push    r13
0x18015688c  push    r14
0x18015688e  push    r15
0x180156890  lea     rbp, [rsp-240h]
0x180156898  sub     rsp, 340h
0x18015689f  mov     rax, cs:__security_cookie
0x1801568a6  xor     rax, rsp
0x1801568a9  mov     [rbp+270h+var_40], rax
0x1801568b0  mov     [rbp+270h+var_2E0], r9
0x1801568b4  mov     rdi, rdx
0x1801568b7  mov     r14, rcx
0x1801568ba  mov     rax, [rbp+270h+arg_20]
0x1801568c1  mov     [rbp+270h+var_2A8], rax
0x1801568c5  mov     rsi, [rbp+270h+arg_28]
0x1801568cc  mov     r13, [rbp+270h+arg_30]
0x1801568d3  xorps   xmm0, xmm0
0x1801568d6  xor     eax, eax
0x1801568d8  movups  xmmword ptr [rbp+270h+value], xmm0
0x1801568dc  movups  xmmword ptr [rbp+270h+value+10h], xmm0
0x1801568e0  mov     qword ptr [rbp+270h+value+20h], rax
0x1801568e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801568eb  movdqu  xmmword ptr [rbp+270h+ActivityId.Data1], xmm0
0x1801568f3  lea     rdx, [rbp+270h+ActivityId]; ActivityId
0x1801568fa  lea     ecx, [rax+1]; ControlCode
0x1801568fd  call    cs:__imp_EventActivityIdControl
0x180156903  lea     r9, [rbp+270h+value]; value
0x180156907  mov     rcx, rdi; context
0x18015690a  call    MI_Context_GetCustomOption_1
0x18015690f  xor     ebx, ebx
0x180156911  test    eax, eax
0x180156913  jnz     short loc_180156926
0x180156915  lea     rdx, [rbp+270h+ActivityId]; pclsid
0x18015691c  mov     rcx, qword ptr [rbp+270h+value]; lpsz
0x180156920  call    cs:__imp_CLSIDFromString
0x180156926  mov     rcx, qword ptr [rbp+270h+ActivityId.Data1]
0x18015692d  mov     [rbp+270h+var_60], rcx
0x180156934  mov     rax, qword ptr [rbp+270h+ActivityId.Data4]
0x18015693b  mov     [rbp+270h+var_58], rax
0x180156942  mov     qword ptr [rbp+270h+var_50.Data1], rcx
0x180156949  mov     qword ptr [rbp+270h+var_50.Data4], rax
0x180156950  lea     rdx, [rbp+270h+var_50]; ActivityId
0x180156957  mov     ecx, 4; ControlCode
0x18015695c  call    cs:__imp_EventActivityIdControl
0x180156962  mov     eax, cs:dword_180397B68
0x180156968  lea     rcx, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015696f  cmp     eax, 5
0x180156972  jbe     short loc_1801569A1
0x180156974  mov     [rsp+370h+var_2F8], 100h
0x18015697c  mov     [rsp+370h+var_300], rcx
0x180156981  lea     rax, [rsp+370h+var_2F8]
0x180156986  mov     [rsp+370h+var_348], rax
0x18015698b  lea     rax, [rsp+370h+var_300]
0x180156990  mov     qword ptr [rsp+370h+var_350], rax
0x180156995  lea     rdx, word_180354492
0x18015699c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801569a1  mov     [rbp+270h+instance.ft], rbx
0x1801569a8  xor     edx, edx; Val
0x1801569aa  mov     r8d, 178h; Size
0x1801569b0  lea     rcx, [rbp+270h+instance.classDecl]; void *
0x1801569b7  call    memset_0
0x1801569bc  xorps   xmm0, xmm0
0x1801569bf  xor     eax, eax
0x1801569c1  movups  [rbp+270h+var_280], xmm0
0x1801569c5  mov     [rbp+270h+var_270], rax
0x1801569c9  mov     [rbp+270h+var_2F0], rbx
0x1801569cd  lea     rcx, [rbp+270h+var_2F0]
0x1801569d1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801569d6  mov     [rbp+270h+var_2F0], rbx
0x1801569da  mov     r15d, ebx
0x1801569dd  lea     rcx, [rbp+270h+var_2A0]; this
0x1801569e1  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801569e6  mov     rcx, rdi; context
0x1801569e9  call    WspIsRemoteRequest
0x1801569ee  mov     r12d, eax
0x1801569f1  test    eax, eax
0x1801569f3  jnz     short loc_180156A18
0x1801569f5  lea     rcx, [rbp+270h+var_2A0]; this
0x1801569f9  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801569fe  cmp     [rsi+48h], bl
0x180156a01  jz      short loc_180156A15
0x180156a03  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180156a07  call    WspIsRemoteInstance
0x180156a0c  test    al, al
0x180156a0e  lea     r15d, [r12+1]
0x180156a13  jnz     short loc_180156A18
0x180156a15  mov     r15d, ebx
0x180156a18  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180156a1f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180156a24  mov     ebx, eax
0x180156a26  test    eax, eax
0x180156a28  jnz     loc_180156C1F
0x180156a2e  mov     dword ptr [rbp+270h+var_280], 0Bh
0x180156a35  mov     rax, [rsi+40h]
0x180156a39  mov     qword ptr [rbp+270h+var_280+8], rax
0x180156a3d  mov     rbx, [r14]
0x180156a40  lea     rcx, [rbp+270h+var_2F0]
0x180156a44  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180156a49  mov     [rsp+370h+var_350], 1; int
0x180156a51  lea     r9, [rbp+270h+var_2F0]; struct ISpWmiObject **
0x180156a55  lea     r8, [rbp+270h+var_280]; struct _SP_OBJECT_ID *
0x180156a59  mov     rdx, rdi; context
0x180156a5c  mov     rcx, rbx; this
0x180156a5f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180156a64  mov     ebx, eax
0x180156a66  test    eax, eax
0x180156a68  jz      short loc_180156ABE
0x180156a6a  mov     eax, cs:dword_180397B68
0x180156a70  cmp     eax, 2
0x180156a73  jbe     loc_180156C0A
0x180156a79  mov     [rsp+370h+var_2F8], ebx
0x180156a7d  mov     [rbp+270h+var_2D8], 120h
0x180156a84  lea     rax, [rsp+370h+var_2F8]
0x180156a89  mov     [rsp+370h+var_340], rax
0x180156a8e  lea     rax, [rbp+270h+var_2D8]
0x180156a92  lea     rdx, dword_180356DCC
0x180156a99  mov     [rsp+370h+var_348], rax
0x180156a9e  lea     rax, [rsp+370h+var_300]
0x180156aa3  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156aaa  mov     [rsp+370h+var_300], r13
0x180156aaf  mov     qword ptr [rsp+370h+var_350], rax
0x180156ab4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180156ab9  jmp     loc_180156C11
0x180156abe  mov     r8, [rsi+40h]
0x180156ac2  mov     rdx, rdi
0x180156ac5  mov     rcx, [r14]
0x180156ac8  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180156acd  cmp     eax, 1
0x180156ad0  jnb     short loc_180156B06
0x180156ad2  mov     ebx, 7
0x180156ad7  mov     eax, cs:dword_180397B68
0x180156add  cmp     eax, 2
0x180156ae0  jbe     loc_180156C0A
0x180156ae6  mov     dword ptr [rbp+270h+var_2D0], ebx
0x180156ae9  mov     dword ptr [rbp+270h+var_2C8], 12Bh
0x180156af0  lea     rax, [rbp+270h+var_2D0]
0x180156af4  mov     [rsp+370h+var_340], rax
0x180156af9  lea     rax, [rbp+270h+var_2C8]
0x180156afd  lea     rdx, byte_180356EA5
0x180156b04  jmp     short loc_180156A99
0x180156b06  lea     r8, [rbp+270h+instance]; instance
0x180156b0d  lea     rdx, SPACES_StoragePool_CreateVirtualDisk2_rtti; methodDecl
0x180156b14  mov     rcx, rdi; context
0x180156b17  call    MI_Context_ConstructParameters
0x180156b1c  mov     ebx, eax
0x180156b1e  test    eax, eax
0x180156b20  jz      short loc_180156B54
0x180156b22  mov     eax, cs:dword_180397B68
0x180156b28  cmp     eax, 2
0x180156b2b  jbe     loc_180156C0A
0x180156b31  mov     dword ptr [rbp+270h+var_2C0], ebx
0x180156b34  mov     dword ptr [rbp+270h+var_2B8], 133h
0x180156b3b  lea     rax, [rbp+270h+var_2C0]
0x180156b3f  mov     [rsp+370h+var_340], rax
0x180156b44  lea     rax, [rbp+270h+var_2B8]
0x180156b48  lea     rdx, byte_180355E3D
0x180156b4f  jmp     loc_180156A99
0x180156b54  mov     rcx, [rbp+270h+var_2F0]
0x180156b58  mov     rax, [rcx]
0x180156b5b  lea     rdx, [rbp+270h+instance]
0x180156b62  mov     qword ptr [rsp+370h+var_350], rdx
0x180156b67  mov     r9, r13
0x180156b6a  mov     r8, rdi
0x180156b6d  mov     edx, 0B0014h
0x180156b72  mov     rax, [rax+30h]
0x180156b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156b7b  mov     ebx, eax
0x180156b7d  test    eax, eax
0x180156b7f  jz      short loc_180156BAF
0x180156b81  mov     eax, cs:dword_180397B68
0x180156b87  cmp     eax, 2
0x180156b8a  jbe     short loc_180156C0A
0x180156b8c  mov     dword ptr [rbp+270h+var_2B0], ebx
0x180156b8f  mov     dword ptr [rbp+270h+var_2E8], 13Eh
0x180156b96  lea     rax, [rbp+270h+var_2B0]
0x180156b9a  mov     [rsp+370h+var_340], rax
0x180156b9f  lea     rax, [rbp+270h+var_2E8]
0x180156ba3  lea     rdx, word_180356616
0x180156baa  jmp     loc_180156A99
0x180156baf  lea     rdx, [rbp+270h+instance]
0x180156bb6  mov     rcx, rdi; self
0x180156bb9  call    MI_Instance_Destruct
0x180156bbe  mov     ebx, eax
0x180156bc0  test    eax, eax
0x180156bc2  jz      short loc_180156C0A
0x180156bc4  mov     eax, cs:dword_180397B68
0x180156bca  cmp     eax, 2
0x180156bcd  jbe     short loc_180156C0A
0x180156bcf  mov     [rsp+370h+var_2F4], ebx
0x180156bd3  mov     dword ptr [rsp+370h+var_300], 146h
0x180156bdb  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156be2  mov     [rbp+270h+var_2E8], r13
0x180156be6  lea     rax, [rsp+370h+var_2F4]
0x180156beb  mov     [rsp+370h+var_340], rax
0x180156bf0  lea     rax, [rsp+370h+var_300]
0x180156bf5  mov     [rsp+370h+var_348], rax
0x180156bfa  lea     rax, [rbp+270h+var_2E8]
0x180156bfe  lea     rdx, byte_180355BA7
0x180156c05  jmp     loc_180156AAF
0x180156c0a  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156c11  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180156c18  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180156c1d  jmp     short loc_180156C26
0x180156c1f  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156c26  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x180156c2a  xor     r14d, r14d
0x180156c2d  mov     [rsp+370h+var_348], r14; unsigned __int16 *
0x180156c32  mov     [rsp+370h+var_350], ebx; enum _MI_Result
0x180156c36  lea     r9, [rbp+270h+var_1B0]; struct _MI_ConstUint32Field *
0x180156c3d  mov     rdx, [rbp+270h+var_2A8]; unsigned __int16 *
0x180156c41  mov     rcx, [rbp+270h+var_2E0]; unsigned __int16 *
0x180156c45  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180156c4a  test    r12d, r12d
0x180156c4d  jnz     loc_180156DF0
0x180156c53  lea     rcx, [rbp+270h+var_2A0]; this
0x180156c57  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180156c5c  mov     eax, cs:dword_180397B68
0x180156c62  cmp     eax, 5
0x180156c65  jbe     loc_180156DF0
0x180156c6b  mov     rdx, 400000000000h
0x180156c75  lea     rcx, dword_180397B68
0x180156c7c  call    _tlgKeywordOn
0x180156c81  test    al, al
0x180156c83  jz      loc_180156DF0
0x180156c89  cmp     [rbp+270h+var_88], r14b
0x180156c90  jz      short loc_180156CCD
0x180156c92  mov     rax, [rbp+270h+var_90]
0x180156c99  movups  xmm0, xmmword ptr [rax]
0x180156c9c  movaps  xmmword ptr [rbp+270h+var_260.ft], xmm0
0x180156ca0  movups  xmm1, xmmword ptr [rax+10h]
0x180156ca4  movaps  xmmword ptr [rbp+270h+var_260.serverName], xmm1
0x180156ca8  movups  xmm0, xmmword ptr [rax+20h]
0x180156cac  movaps  xmmword ptr [rbp+270h+var_260.reserved], xmm0
0x180156cb0  movups  xmm1, xmmword ptr [rax+30h]
0x180156cb4  movaps  xmmword ptr [rbp+270h+var_260.reserved+10h], xmm1
0x180156cb8  xor     r8d, r8d; unsigned __int16 *
0x180156cbb  lea     rdx, [rbp+270h+var_260]; struct _MI_Instance
0x180156cbf  lea     rcx, name; "ObjectId"
0x180156cc6  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180156ccb  jmp     short loc_180156CD0
0x180156ccd  mov     rax, r14
0x180156cd0  mov     [rbp+270h+var_2E0], rax
0x180156cd4  cmp     [rbp+270h+var_98], r14b
0x180156cdb  jz      short loc_180156D18
0x180156cdd  mov     rax, [rbp+270h+var_A0]
0x180156ce4  movups  xmm0, xmmword ptr [rax]
0x180156ce7  movaps  xmmword ptr [rbp+270h+var_260.ft], xmm0
0x180156ceb  movups  xmm1, xmmword ptr [rax+10h]
0x180156cef  movaps  xmmword ptr [rbp+270h+var_260.serverName], xmm1
0x180156cf3  movups  xmm0, xmmword ptr [rax+20h]
0x180156cf7  movaps  xmmword ptr [rbp+270h+var_260.reserved], xmm0
0x180156cfb  movups  xmm1, xmmword ptr [rax+30h]
0x180156cff  movaps  xmmword ptr [rbp+270h+var_260.reserved+10h], xmm1
0x180156d03  xor     r8d, r8d; unsigned __int16 *
0x180156d06  lea     rdx, [rbp+270h+var_260]; struct _MI_Instance
0x180156d0a  lea     rcx, name; "ObjectId"
0x180156d11  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180156d16  jmp     short loc_180156D1B
0x180156d18  mov     rax, r14
0x180156d1b  mov     [rbp+270h+var_2A8], rax
0x180156d1f  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x180156d26  mov     [rbp+270h+var_2B0], rax
0x180156d2a  mov     rax, [rbp+270h+var_298]
0x180156d2e  sub     rax, [rbp+270h+var_2A0]
0x180156d32  imul    rax, 3E8h
0x180156d39  xor     edx, edx
0x180156d3b  div     [rbp+270h+var_290]
0x180156d3f  mov     [rbp+270h+var_2B8], rax
0x180156d43  mov     dword ptr [rsp+370h+var_300], ebx
0x180156d47  mov     al, [rbp+270h+var_1B0.exists]
0x180156d4d  neg     al
0x180156d4f  sbb     ecx, ecx
0x180156d51  and     ecx, [rbp+270h+var_1B0.value]
0x180156d57  mov     [rsp+370h+var_2F4], ecx
0x180156d5b  mov     dword ptr [rbp+270h+var_2E8], r15d
0x180156d5f  cmp     [rsi+48h], r14b
0x180156d63  jz      short loc_180156D6B
0x180156d65  mov     rax, [rsi+40h]
0x180156d69  jmp     short loc_180156D6E
0x180156d6b  mov     rax, r14
0x180156d6e  mov     [rbp+270h+var_2C0], rax
0x180156d72  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x180156d79  mov     [rbp+270h+var_2C8], rax
0x180156d7d  lea     rax, aStoragepool_0; "StoragePool"
0x180156d84  mov     [rbp+270h+var_2D0], rax
0x180156d88  lea     rax, [rbp+270h+var_2E0]
0x180156d8c  mov     [rsp+370h+var_308], rax
0x180156d91  lea     rax, [rbp+270h+var_2A8]
0x180156d95  mov     [rsp+370h+var_310], rax
0x180156d9a  lea     rax, [rbp+270h+var_2B0]
0x180156d9e  mov     [rsp+370h+var_318], rax
0x180156da3  lea     rax, [rbp+270h+var_2B8]
0x180156da7  mov     [rsp+370h+var_320], rax
0x180156dac  lea     rax, [rsp+370h+var_300]
0x180156db1  mov     [rsp+370h+var_328], rax
0x180156db6  lea     rax, [rsp+370h+var_2F4]
  ... truncated ...
```
