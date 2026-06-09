# SPACES_StoragePool_Invoke_CreateVirtualDisk

- ea: `0x1801562c0`
- end: `0x180156877`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- size: `1463`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x1801562c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015633d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015639c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156847`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015633d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015639c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156847`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156360`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156360`

## string_xrefs

- `0x1801563a8`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x1801564d4`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x1801565bd`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x1801565ec`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x180156601`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x180156752`: `CreateVirtualDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVirtualDisk(
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
  int v13; // r14d
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
  MI_Uint32 v36; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v37; // [rsp+80h] [rbp-80h] BYREF
  const char *v38; // [rsp+88h] [rbp-78h] BYREF
  const char *v39; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v40; // [rsp+98h] [rbp-68h] BYREF
  const char *v41; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v42; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v43; // [rsp+B0h] [rbp-50h] BYREF
  const char *v44; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v45; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v46[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v47; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v49; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v53; // [rsp+290h] [rbp+190h]
  char v54; // [rsp+298h] [rbp+198h]
  struct _MI_Instance *v55; // [rsp+2A0h] [rbp+1A0h]
  char v56; // [rsp+2A8h] [rbp+1A8h]
  GUID ActivityId; // [rsp+2C0h] [rbp+1C0h] BYREF
  GUID v58; // [rsp+2D0h] [rbp+1D0h]
  GUID v59; // [rsp+2E0h] [rbp+1E0h] BYREF

  v40 = a4;
  v45 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v58 = ActivityId;
  v59 = ActivityId;
  EventActivityIdControl(4u, &v59);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v38) = 149;
    v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVirtualDisk",
      (unsigned int)word_180356CBA,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v38);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x148u);
  v47 = 0;
  v48 = 0;
  v37 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  v37 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v46);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v46);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v47) = 11;
    *((_QWORD *)&v47 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v47, &v37, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v38) = v15;
        LODWORD(v41) = 180;
        v34 = &v38;
        v20 = &v41;
        v21 = (char *)word_180354D72;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_23;
        LODWORD(v42) = v15;
        LODWORD(v43) = 188;
        v34 = (const char **)&v42;
        v20 = (const char **)&v43;
        v21 = byte_1803566AB;
        goto LABEL_13;
      }
      v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v37 + 48LL))(
              v37,
              720897,
              a2,
              a7,
              &instance);
      if ( v15 == MI_RESULT_OK )
      {
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_180397B68 > 2 )
        {
          v36 = v15;
          LODWORD(v35) = 207;
          v39 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&byte_1803561F7,
            v23,
            v24,
            (__int64)&v39,
            (__int64)&v35,
            (__int64)&v36);
        }
        goto LABEL_23;
      }
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v44) = v15;
        LODWORD(v39) = 199;
        v34 = &v44;
        v20 = &v39;
        v21 = byte_180355041;
        goto LABEL_13;
      }
    }
LABEL_23:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v45, a6 + 4, &v52, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v46);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v56 )
        {
          v49 = *v55;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v49, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v54 )
        {
          v49 = *v53;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v49, 0);
        }
        else
        {
          v28 = 0;
        }
        v45 = v28;
        v44 = "VirtualDisk";
        v43 = (unsigned __int64)(1000LL * (v46[1] - v46[0])) / v46[2];
        LODWORD(v35) = v15;
        v36 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v42 = v29;
        v41 = "CreateVirtualDisk";
        v38 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&unk_1803560A0,
          v25,
          v26,
          (__int64)&v38,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v39,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v35) = 240;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&dword_18035767C,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v46);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  return EventActivityIdControl(4u, &v59);
}

```

## disassembly

```asm
0x1801562c0  mov     [rsp-8+arg_10], rbx
0x1801562c5  push    rbp
0x1801562c6  push    rsi
0x1801562c7  push    rdi
0x1801562c8  push    r12
0x1801562ca  push    r13
0x1801562cc  push    r14
0x1801562ce  push    r15
0x1801562d0  lea     rbp, [rsp-200h]
0x1801562d8  sub     rsp, 300h
0x1801562df  mov     rax, cs:__security_cookie
0x1801562e6  xor     rax, rsp
0x1801562e9  mov     [rbp+230h+var_40], rax
0x1801562f0  mov     [rbp+230h+var_298], r9
0x1801562f4  mov     rdi, rdx
0x1801562f7  mov     r15, rcx
0x1801562fa  mov     rax, [rbp+230h+arg_20]
0x180156301  mov     [rbp+230h+var_270], rax
0x180156305  mov     rsi, [rbp+230h+arg_28]
0x18015630c  mov     r13, [rbp+230h+arg_30]
0x180156313  xorps   xmm0, xmm0
0x180156316  xor     eax, eax
0x180156318  movups  xmmword ptr [rbp+230h+value], xmm0
0x18015631c  movups  xmmword ptr [rbp+230h+value+10h], xmm0
0x180156320  mov     qword ptr [rbp+230h+value+20h], rax
0x180156324  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015632b  movdqu  xmmword ptr [rbp+230h+ActivityId.Data1], xmm0
0x180156333  lea     rdx, [rbp+230h+ActivityId]; ActivityId
0x18015633a  lea     ecx, [rax+1]; ControlCode
0x18015633d  call    cs:__imp_EventActivityIdControl
0x180156343  lea     r9, [rbp+230h+value]; value
0x180156347  mov     rcx, rdi; context
0x18015634a  call    MI_Context_GetCustomOption_1
0x18015634f  xor     ebx, ebx
0x180156351  test    eax, eax
0x180156353  jnz     short loc_180156366
0x180156355  lea     rdx, [rbp+230h+ActivityId]; pclsid
0x18015635c  mov     rcx, qword ptr [rbp+230h+value]; lpsz
0x180156360  call    cs:__imp_CLSIDFromString
0x180156366  mov     rcx, qword ptr [rbp+230h+ActivityId.Data1]
0x18015636d  mov     [rbp+230h+var_60], rcx
0x180156374  mov     rax, qword ptr [rbp+230h+ActivityId.Data4]
0x18015637b  mov     [rbp+230h+var_58], rax
0x180156382  mov     qword ptr [rbp+230h+var_50.Data1], rcx
0x180156389  mov     qword ptr [rbp+230h+var_50.Data4], rax
0x180156390  lea     rdx, [rbp+230h+var_50]; ActivityId
0x180156397  mov     ecx, 4; ControlCode
0x18015639c  call    cs:__imp_EventActivityIdControl
0x1801563a2  mov     eax, cs:dword_180397B68
0x1801563a8  lea     rcx, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x1801563af  cmp     eax, 5
0x1801563b2  jbe     short loc_1801563DF
0x1801563b4  mov     dword ptr [rbp+230h+var_2A8], 95h
0x1801563bb  mov     [rsp+330h+var_2C0], rcx
0x1801563c0  lea     rax, [rbp+230h+var_2A8]
0x1801563c4  mov     [rsp+330h+var_308], rax
0x1801563c9  lea     rax, [rsp+330h+var_2C0]
0x1801563ce  mov     qword ptr [rsp+330h+var_310], rax
0x1801563d3  lea     rdx, word_180356CBA
0x1801563da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801563df  mov     [rbp+230h+instance.ft], rbx
0x1801563e3  xor     edx, edx; Val
0x1801563e5  mov     r8d, 148h; Size
0x1801563eb  lea     rcx, [rbp+230h+instance.classDecl]; void *
0x1801563ef  call    memset_0
0x1801563f4  xorps   xmm0, xmm0
0x1801563f7  xor     eax, eax
0x1801563f9  movups  [rbp+230h+var_248], xmm0
0x1801563fd  mov     [rbp+230h+var_238], rax
0x180156401  mov     [rbp+230h+var_2B0], rbx
0x180156405  lea     rcx, [rbp+230h+var_2B0]
0x180156409  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015640e  mov     [rbp+230h+var_2B0], rbx
0x180156412  mov     r14d, ebx
0x180156415  lea     rcx, [rbp+230h+var_268]; this
0x180156419  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015641e  mov     rcx, rdi; context
0x180156421  call    WspIsRemoteRequest
0x180156426  mov     r12d, eax
0x180156429  test    eax, eax
0x18015642b  jnz     short loc_180156450
0x18015642d  lea     rcx, [rbp+230h+var_268]; this
0x180156431  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180156436  cmp     [rsi+48h], bl
0x180156439  jz      short loc_18015644D
0x18015643b  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18015643f  call    WspIsRemoteInstance
0x180156444  test    al, al
0x180156446  lea     r14d, [r12+1]
0x18015644b  jnz     short loc_180156450
0x18015644d  mov     r14d, ebx
0x180156450  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180156457  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015645c  mov     ebx, eax
0x18015645e  test    eax, eax
0x180156460  jnz     loc_180156601
0x180156466  mov     dword ptr [rbp+230h+var_248], 0Bh
0x18015646d  mov     rax, [rsi+40h]
0x180156471  mov     qword ptr [rbp+230h+var_248+8], rax
0x180156475  mov     rbx, [r15]
0x180156478  lea     rcx, [rbp+230h+var_2B0]
0x18015647c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180156481  mov     [rsp+330h+var_310], 1; int
0x180156489  lea     r9, [rbp+230h+var_2B0]; struct ISpWmiObject **
0x18015648d  lea     r8, [rbp+230h+var_248]; struct _SP_OBJECT_ID *
0x180156491  mov     rdx, rdi; context
0x180156494  mov     rcx, rbx; this
0x180156497  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015649c  mov     ebx, eax
0x18015649e  test    eax, eax
0x1801564a0  jz      short loc_1801564F4
0x1801564a2  mov     eax, cs:dword_180397B68
0x1801564a8  cmp     eax, 2
0x1801564ab  jbe     loc_1801565EC
0x1801564b1  mov     dword ptr [rbp+230h+var_2A8], ebx
0x1801564b4  mov     dword ptr [rbp+230h+var_290], 0B4h
0x1801564bb  lea     rax, [rbp+230h+var_2A8]
0x1801564bf  mov     [rsp+330h+var_300], rax
0x1801564c4  lea     rax, [rbp+230h+var_290]
0x1801564c8  lea     rdx, word_180354D72
0x1801564cf  mov     [rsp+330h+var_308], rax
0x1801564d4  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x1801564db  lea     rax, [rsp+330h+var_2C0]
0x1801564e0  mov     [rsp+330h+var_2C0], r15
0x1801564e5  mov     qword ptr [rsp+330h+var_310], rax
0x1801564ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801564ef  jmp     loc_1801565F3
0x1801564f4  lea     r8, [rbp+230h+instance]; instance
0x1801564f8  lea     rdx, SPACES_StoragePool_CreateVirtualDisk_rtti; methodDecl
0x1801564ff  mov     rcx, rdi; context
0x180156502  call    MI_Context_ConstructParameters
0x180156507  mov     ebx, eax
0x180156509  test    eax, eax
0x18015650b  jz      short loc_18015653C
0x18015650d  mov     eax, cs:dword_180397B68
0x180156513  cmp     eax, 2
0x180156516  jbe     loc_1801565EC
0x18015651c  mov     dword ptr [rbp+230h+var_288], ebx
0x18015651f  mov     dword ptr [rbp+230h+var_280], 0BCh
0x180156526  lea     rax, [rbp+230h+var_288]
0x18015652a  mov     [rsp+330h+var_300], rax
0x18015652f  lea     rax, [rbp+230h+var_280]
0x180156533  lea     rdx, byte_1803566AB
0x18015653a  jmp     short loc_1801564CF
0x18015653c  mov     rcx, [rbp+230h+var_2B0]
0x180156540  mov     rax, [rcx]
0x180156543  lea     rdx, [rbp+230h+instance]
0x180156547  mov     qword ptr [rsp+330h+var_310], rdx
0x18015654c  mov     r9, r13
0x18015654f  mov     r8, rdi
0x180156552  mov     edx, 0B0001h
0x180156557  mov     rax, [rax+30h]
0x18015655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156560  mov     ebx, eax
0x180156562  test    eax, eax
0x180156564  jz      short loc_180156594
0x180156566  mov     eax, cs:dword_180397B68
0x18015656c  cmp     eax, 2
0x18015656f  jbe     short loc_1801565EC
0x180156571  mov     dword ptr [rbp+230h+var_278], ebx
0x180156574  mov     dword ptr [rbp+230h+var_2A0], 0C7h
0x18015657b  lea     rax, [rbp+230h+var_278]
0x18015657f  mov     [rsp+330h+var_300], rax
0x180156584  lea     rax, [rbp+230h+var_2A0]
0x180156588  lea     rdx, byte_180355041
0x18015658f  jmp     loc_1801564CF
0x180156594  lea     rdx, [rbp+230h+instance]
0x180156598  mov     rcx, rdi; self
0x18015659b  call    MI_Instance_Destruct
0x1801565a0  mov     ebx, eax
0x1801565a2  test    eax, eax
0x1801565a4  jz      short loc_1801565EC
0x1801565a6  mov     eax, cs:dword_180397B68
0x1801565ac  cmp     eax, 2
0x1801565af  jbe     short loc_1801565EC
0x1801565b1  mov     [rsp+330h+var_2B8], ebx
0x1801565b5  mov     dword ptr [rsp+330h+var_2C0], 0CFh
0x1801565bd  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x1801565c4  mov     [rbp+230h+var_2A0], r15
0x1801565c8  lea     rax, [rsp+330h+var_2B8]
0x1801565cd  mov     [rsp+330h+var_300], rax
0x1801565d2  lea     rax, [rsp+330h+var_2C0]
0x1801565d7  mov     [rsp+330h+var_308], rax
0x1801565dc  lea     rax, [rbp+230h+var_2A0]
0x1801565e0  lea     rdx, byte_1803561F7
0x1801565e7  jmp     loc_1801564E5
0x1801565ec  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x1801565f3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801565fa  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801565ff  jmp     short loc_180156608
0x180156601  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156608  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18015660c  mov     [rsp+330h+var_308], 0; unsigned __int16 *
0x180156615  mov     [rsp+330h+var_310], ebx; enum _MI_Result
0x180156619  lea     r9, [rbp+230h+var_180]; struct _MI_ConstUint32Field *
0x180156620  mov     rdx, [rbp+230h+var_270]; unsigned __int16 *
0x180156624  mov     rcx, [rbp+230h+var_298]; unsigned __int16 *
0x180156628  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015662d  test    r12d, r12d
0x180156630  jnz     loc_1801567D0
0x180156636  lea     rcx, [rbp+230h+var_268]; this
0x18015663a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015663f  mov     eax, cs:dword_180397B68
0x180156645  cmp     eax, 5
0x180156648  jbe     loc_1801567D0
0x18015664e  mov     rdx, 400000000000h
0x180156658  lea     rcx, dword_180397B68
0x18015665f  call    _tlgKeywordOn
0x180156664  test    al, al
0x180156666  jz      loc_1801567D0
0x18015666c  cmp     [rbp+230h+var_88], r12b
0x180156673  jz      short loc_1801566B0
0x180156675  mov     rax, [rbp+230h+var_90]
0x18015667c  movups  xmm0, xmmword ptr [rax]
0x18015667f  movaps  xmmword ptr [rbp+230h+var_230.ft], xmm0
0x180156683  movups  xmm1, xmmword ptr [rax+10h]
0x180156687  movaps  xmmword ptr [rbp+230h+var_230.serverName], xmm1
0x18015668b  movups  xmm0, xmmword ptr [rax+20h]
0x18015668f  movaps  xmmword ptr [rbp+230h+var_230.reserved], xmm0
0x180156693  movups  xmm1, xmmword ptr [rax+30h]
0x180156697  movaps  xmmword ptr [rbp+230h+var_230.reserved+10h], xmm1
0x18015669b  xor     r8d, r8d; unsigned __int16 *
0x18015669e  lea     rdx, [rbp+230h+var_230]; struct _MI_Instance
0x1801566a2  lea     rcx, name; "ObjectId"
0x1801566a9  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801566ae  jmp     short loc_1801566B2
0x1801566b0  xor     eax, eax
0x1801566b2  mov     [rbp+230h+var_298], rax
0x1801566b6  cmp     [rbp+230h+var_98], 0
0x1801566bd  jz      short loc_1801566FA
0x1801566bf  mov     rax, [rbp+230h+var_A0]
0x1801566c6  movups  xmm0, xmmword ptr [rax]
0x1801566c9  movaps  xmmword ptr [rbp+230h+var_230.ft], xmm0
0x1801566cd  movups  xmm1, xmmword ptr [rax+10h]
0x1801566d1  movaps  xmmword ptr [rbp+230h+var_230.serverName], xmm1
0x1801566d5  movups  xmm0, xmmword ptr [rax+20h]
0x1801566d9  movaps  xmmword ptr [rbp+230h+var_230.reserved], xmm0
0x1801566dd  movups  xmm1, xmmword ptr [rax+30h]
0x1801566e1  movaps  xmmword ptr [rbp+230h+var_230.reserved+10h], xmm1
0x1801566e5  xor     r8d, r8d; unsigned __int16 *
0x1801566e8  lea     rdx, [rbp+230h+var_230]; struct _MI_Instance
0x1801566ec  lea     rcx, name; "ObjectId"
0x1801566f3  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801566f8  jmp     short loc_1801566FC
0x1801566fa  xor     eax, eax
0x1801566fc  mov     [rbp+230h+var_270], rax
0x180156700  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x180156707  mov     [rbp+230h+var_278], rax
0x18015670b  mov     rax, [rbp+230h+var_260]
0x18015670f  sub     rax, [rbp+230h+var_268]
0x180156713  imul    rax, 3E8h
0x18015671a  xor     edx, edx
0x18015671c  div     [rbp+230h+var_258]
0x180156720  mov     [rbp+230h+var_280], rax
0x180156724  mov     dword ptr [rsp+330h+var_2C0], ebx
0x180156728  mov     al, [rbp+230h+var_180.exists]
0x18015672e  neg     al
0x180156730  sbb     ecx, ecx
0x180156732  and     ecx, [rbp+230h+var_180.value]
0x180156738  mov     [rsp+330h+var_2B8], ecx
0x18015673c  mov     dword ptr [rbp+230h+var_2A0], r14d
0x180156740  cmp     byte ptr [rsi+48h], 0
0x180156744  jz      short loc_18015674C
0x180156746  mov     rax, [rsi+40h]
0x18015674a  jmp     short loc_18015674E
0x18015674c  xor     eax, eax
0x18015674e  mov     [rbp+230h+var_288], rax
0x180156752  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x180156759  mov     [rbp+230h+var_290], rax
0x18015675d  lea     rax, aStoragepool_0; "StoragePool"
0x180156764  mov     [rbp+230h+var_2A8], rax
0x180156768  lea     rax, [rbp+230h+var_298]
0x18015676c  mov     [rsp+330h+var_2C8], rax
0x180156771  lea     rax, [rbp+230h+var_270]
0x180156775  mov     [rsp+330h+var_2D0], rax
0x18015677a  lea     rax, [rbp+230h+var_278]
0x18015677e  mov     [rsp+330h+var_2D8], rax
0x180156783  lea     rax, [rbp+230h+var_280]
0x180156787  mov     [rsp+330h+var_2E0], rax
0x18015678c  lea     rax, [rsp+330h+var_2C0]
0x180156791  mov     [rsp+330h+var_2E8], rax
0x180156796  lea     rax, [rsp+330h+var_2B8]
0x18015679b  mov     [rsp+330h+var_2F0], rax
0x1801567a0  lea     rax, [rbp+230h+var_2A0]
0x1801567a4  mov     [rsp+330h+var_2F8], rax
0x1801567a9  lea     rax, [rbp+230h+var_288]
0x1801567ad  mov     [rsp+330h+var_300], rax
0x1801567b2  lea     rax, [rbp+230h+var_290]
0x1801567b6  mov     [rsp+330h+var_308], rax
0x1801567bb  lea     rax, [rbp+230h+var_2A8]
0x1801567bf  mov     qword ptr [rsp+330h+var_310], rax
0x1801567c4  lea     rdx, unk_1803560A0
0x1801567cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801567d0  lea     rcx, [rbp+230h+instance]; self
0x1801567d4  call    MI_Instance_Destruct
0x1801567d9  mov     eax, cs:dword_180397B68
0x1801567df  cmp     eax, 5
0x1801567e2  jbe     short loc_18015680F
0x1801567e4  mov     dword ptr [rsp+330h+var_2C0], 0F0h
0x1801567ec  mov     [rbp+230h+var_298], r15
  ... truncated ...
```
