# SPACES_StoragePool_Invoke_RemovePhysicalDisk

- ea: `0x180159c00`
- end: `0x18015a1ab`
- name: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800047c0`
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
- `0x180159c00`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159c7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159cdc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a17b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159c7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159cdc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a17b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159ca0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159ca0`

## string_xrefs

- `0x18015a077`: `RemovePhysicalDisk`
- `0x180159ce8`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x180159e00`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x180159e62`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x180159ed5`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x180159f29`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015a11a`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_RemovePhysicalDisk(
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
  enum _MI_Result v13; // r14d
  int IsRemoteRequest; // r13d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  unsigned __int16 *v32; // rax
  const MI_Char *v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  const char *v38; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v39; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v40; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v41; // [rsp+90h] [rbp-70h] BYREF
  const char *v42; // [rsp+98h] [rbp-68h] BYREF
  const char *v43; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v44; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v47; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v48; // [rsp+C8h] [rbp-38h] BYREF
  const char *v49; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v50[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v53; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v56; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v57; // [rsp+1E0h] [rbp+E0h]
  char v58; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v60; // [rsp+210h] [rbp+110h]
  GUID v61; // [rsp+220h] [rbp+120h] BYREF

  v48 = a4;
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
    LODWORD(v42) = 1502;
    v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_RemovePhysicalDisk",
      (unsigned int)&word_180355D1E,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v42);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v51 = 0;
  v52 = 0;
  v41 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  v41 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v50);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v50);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v51) = 11;
    *((_QWORD *)&v51 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v51, &v41, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v42) = v15;
        LODWORD(v44) = 1533;
        v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_180356A74,
          v18,
          v19,
          (__int64)&v38,
          (__int64)&v44,
          (__int64)&v42);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_RemovePhysicalDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v45) = v15;
          LODWORD(v46) = 1541;
          v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_180354EB1,
            v21,
            v22,
            (__int64)&v38,
            (__int64)&v46,
            (__int64)&v45);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v41 + 48LL))(
                v41,
                720900,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            v39 = v15;
            LODWORD(v43) = 1552;
            v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&byte_180355827,
              v24,
              v25,
              (__int64)&v38,
              (__int64)&v43,
              (__int64)&v39);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_180397B68 > 2 )
          {
            v40 = v15;
            LODWORD(v38) = 1560;
            v43 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&word_1803561BE,
              v27,
              v28,
              (__int64)&v43,
              (__int64)&v38,
              (__int64)&v40);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v48, v47, a6 + 4, &v56, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v50);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v31 = *(_DWORD *)(a7 + 80);
        else
          v31 = 0;
        LODWORD(v38) = v31;
        if ( v58 )
        {
          v53 = *v57;
          v32 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v53, 0);
        }
        else
        {
          v32 = 0;
        }
        v48 = v32;
        v47 = 0;
        v46 = 0;
        v45 = (unsigned __int64)(1000LL * (v50[1] - v50[0])) / v50[2];
        v40 = v15;
        LODWORD(v43) = v56.exists != 0 ? v56.value : 0;
        v39 = v13;
        if ( a6[4].exists )
          v33 = a6[4].value;
        else
          v33 = 0;
        v44 = v33;
        v42 = "RemovePhysicalDisk";
        v49 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v56.exists != 0 ? v56.value : 0,
          (unsigned int)&unk_180355EE8,
          v29,
          v30,
          (__int64)&v49,
          (__int64)&v42,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v38);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v38) = 1594;
    v49 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v34,
      (unsigned int)byte_180355669,
      v35,
      v36,
      (__int64)&v49,
      (__int64)&v38);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v50);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x180159c00  mov     [rsp-8+arg_10], rbx
0x180159c05  push    rbp
0x180159c06  push    rsi
0x180159c07  push    rdi
0x180159c08  push    r12
0x180159c0a  push    r13
0x180159c0c  push    r14
0x180159c0e  push    r15
0x180159c10  lea     rbp, [rsp-140h]
0x180159c18  sub     rsp, 240h
0x180159c1f  mov     rax, cs:__security_cookie
0x180159c26  xor     rax, rsp
0x180159c29  mov     [rbp+170h+var_40], rax
0x180159c30  mov     [rbp+170h+var_1A8], r9
0x180159c34  mov     rdi, rdx
0x180159c37  mov     r12, rcx
0x180159c3a  mov     rax, [rbp+170h+arg_20]
0x180159c41  mov     [rbp+170h+var_1B0], rax
0x180159c45  mov     rsi, [rbp+170h+arg_28]
0x180159c4c  mov     r15, [rbp+170h+arg_30]
0x180159c53  xorps   xmm0, xmm0
0x180159c56  xor     eax, eax
0x180159c58  movups  xmmword ptr [rbp+170h+value], xmm0
0x180159c5c  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x180159c60  mov     qword ptr [rbp+170h+value+20h], rax
0x180159c64  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180159c6b  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x180159c73  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x180159c7a  lea     ecx, [rax+1]; ControlCode
0x180159c7d  call    cs:__imp_EventActivityIdControl
0x180159c83  lea     r9, [rbp+170h+value]; value
0x180159c87  mov     rcx, rdi; context
0x180159c8a  call    MI_Context_GetCustomOption_1
0x180159c8f  xor     ebx, ebx
0x180159c91  test    eax, eax
0x180159c93  jnz     short loc_180159CA6
0x180159c95  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x180159c9c  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x180159ca0  call    cs:__imp_CLSIDFromString
0x180159ca6  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x180159cad  mov     [rbp+170h+var_60], rcx
0x180159cb4  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x180159cbb  mov     [rbp+170h+var_58], rax
0x180159cc2  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x180159cc9  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x180159cd0  lea     rdx, [rbp+170h+var_50]; ActivityId
0x180159cd7  mov     ecx, 4; ControlCode
0x180159cdc  call    cs:__imp_EventActivityIdControl
0x180159ce2  mov     eax, cs:dword_180397B68
0x180159ce8  lea     rcx, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x180159cef  cmp     eax, 5
0x180159cf2  jbe     short loc_180159D1D
0x180159cf4  mov     dword ptr [rbp+170h+var_1D8], 5DEh
0x180159cfb  mov     [rbp+170h+var_1F0], rcx
0x180159cff  lea     rax, [rbp+170h+var_1D8]
0x180159d03  mov     [rsp+270h+var_248], rax
0x180159d08  lea     rax, [rbp+170h+var_1F0]
0x180159d0c  mov     qword ptr [rsp+270h+var_250], rax
0x180159d11  lea     rdx, word_180355D1E
0x180159d18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180159d1d  mov     [rbp+170h+instance.ft], rbx
0x180159d24  xor     edx, edx; Val
0x180159d26  lea     r8d, [rdx+78h]; Size
0x180159d2a  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x180159d31  call    memset_0
0x180159d36  xorps   xmm0, xmm0
0x180159d39  xor     eax, eax
0x180159d3b  movups  [rbp+170h+var_178], xmm0
0x180159d3f  mov     [rbp+170h+var_168], rax
0x180159d43  mov     [rbp+170h+var_1E0], rbx
0x180159d47  lea     rcx, [rbp+170h+var_1E0]
0x180159d4b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159d50  mov     [rbp+170h+var_1E0], rbx
0x180159d54  mov     r14d, ebx
0x180159d57  lea     rcx, [rbp+170h+var_198]; this
0x180159d5b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180159d60  mov     rcx, rdi; context
0x180159d63  call    WspIsRemoteRequest
0x180159d68  mov     r13d, eax
0x180159d6b  test    eax, eax
0x180159d6d  jnz     short loc_180159D91
0x180159d6f  lea     rcx, [rbp+170h+var_198]; this
0x180159d73  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180159d78  cmp     [rsi+48h], bl
0x180159d7b  jz      short loc_180159D8E
0x180159d7d  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180159d81  call    WspIsRemoteInstance
0x180159d86  test    al, al
0x180159d88  lea     r14d, [r13+1]
0x180159d8c  jnz     short loc_180159D91
0x180159d8e  mov     r14d, ebx
0x180159d91  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180159d98  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180159d9d  mov     ebx, eax
0x180159d9f  test    eax, eax
0x180159da1  jnz     loc_180159F69
0x180159da7  mov     dword ptr [rbp+170h+var_178], 0Bh
0x180159dae  mov     rax, [rsi+40h]
0x180159db2  mov     qword ptr [rbp+170h+var_178+8], rax
0x180159db6  mov     rbx, [r12]
0x180159dba  lea     rcx, [rbp+170h+var_1E0]
0x180159dbe  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159dc3  mov     [rsp+270h+var_250], 1; int
0x180159dcb  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x180159dcf  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x180159dd3  mov     rdx, rdi; context
0x180159dd6  mov     rcx, rbx; this
0x180159dd9  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180159dde  mov     ebx, eax
0x180159de0  xor     r12d, r12d
0x180159de3  test    eax, eax
0x180159de5  jz      short loc_180159E2D
0x180159de7  mov     eax, cs:dword_180397B68
0x180159ded  cmp     eax, 2
0x180159df0  jbe     loc_180159F5B
0x180159df6  mov     dword ptr [rbp+170h+var_1D8], ebx
0x180159df9  mov     dword ptr [rbp+170h+var_1C8], 5FDh
0x180159e00  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x180159e07  mov     [rbp+170h+var_1F0], rax
0x180159e0b  lea     rax, [rbp+170h+var_1D8]
0x180159e0f  mov     [rsp+270h+var_240], rax
0x180159e14  lea     rax, [rbp+170h+var_1C8]
0x180159e18  mov     [rsp+270h+var_248], rax
0x180159e1d  lea     rax, [rbp+170h+var_1F0]
0x180159e21  lea     rdx, dword_180356A74
0x180159e28  jmp     loc_180159F51
0x180159e2d  lea     r8, [rbp+170h+instance]; instance
0x180159e34  lea     rdx, SPACES_StoragePool_RemovePhysicalDisk_rtti; methodDecl
0x180159e3b  mov     rcx, rdi; context
0x180159e3e  call    MI_Context_ConstructParameters
0x180159e43  mov     ebx, eax
0x180159e45  test    eax, eax
0x180159e47  jz      short loc_180159E8F
0x180159e49  mov     eax, cs:dword_180397B68
0x180159e4f  cmp     eax, 2
0x180159e52  jbe     loc_180159F5B
0x180159e58  mov     dword ptr [rbp+170h+var_1C0], ebx
0x180159e5b  mov     dword ptr [rbp+170h+var_1B8], 605h
0x180159e62  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x180159e69  mov     [rbp+170h+var_1F0], rax
0x180159e6d  lea     rax, [rbp+170h+var_1C0]
0x180159e71  mov     [rsp+270h+var_240], rax
0x180159e76  lea     rax, [rbp+170h+var_1B8]
0x180159e7a  mov     [rsp+270h+var_248], rax
0x180159e7f  lea     rax, [rbp+170h+var_1F0]
0x180159e83  lea     rdx, byte_180354EB1
0x180159e8a  jmp     loc_180159F51
0x180159e8f  mov     rcx, [rbp+170h+var_1E0]
0x180159e93  mov     rax, [rcx]
0x180159e96  lea     rdx, [rbp+170h+instance]
0x180159e9d  mov     qword ptr [rsp+270h+var_250], rdx
0x180159ea2  mov     r9, r15
0x180159ea5  mov     r8, rdi
0x180159ea8  mov     edx, 0B0004h
0x180159ead  mov     rax, [rax+30h]
0x180159eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159eb6  mov     ebx, eax
0x180159eb8  test    eax, eax
0x180159eba  jz      short loc_180159EFF
0x180159ebc  mov     eax, cs:dword_180397B68
0x180159ec2  cmp     eax, 2
0x180159ec5  jbe     loc_180159F5B
0x180159ecb  mov     [rbp+170h+var_1E8], ebx
0x180159ece  mov     dword ptr [rbp+170h+var_1D0], 610h
0x180159ed5  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x180159edc  mov     [rbp+170h+var_1F0], rax
0x180159ee0  lea     rax, [rbp+170h+var_1E8]
0x180159ee4  mov     [rsp+270h+var_240], rax
0x180159ee9  lea     rax, [rbp+170h+var_1D0]
0x180159eed  mov     [rsp+270h+var_248], rax
0x180159ef2  lea     rax, [rbp+170h+var_1F0]
0x180159ef6  lea     rdx, byte_180355827
0x180159efd  jmp     short loc_180159F51
0x180159eff  lea     rdx, [rbp+170h+instance]
0x180159f06  mov     rcx, rdi; self
0x180159f09  call    MI_Instance_Destruct
0x180159f0e  mov     ebx, eax
0x180159f10  test    eax, eax
0x180159f12  jz      short loc_180159F5B
0x180159f14  mov     eax, cs:dword_180397B68
0x180159f1a  cmp     eax, 2
0x180159f1d  jbe     short loc_180159F5B
0x180159f1f  mov     [rbp+170h+var_1E4], ebx
0x180159f22  mov     dword ptr [rbp+170h+var_1F0], 618h
0x180159f29  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x180159f30  mov     [rbp+170h+var_1D0], rax
0x180159f34  lea     rax, [rbp+170h+var_1E4]
0x180159f38  mov     [rsp+270h+var_240], rax
0x180159f3d  lea     rax, [rbp+170h+var_1F0]
0x180159f41  mov     [rsp+270h+var_248], rax
0x180159f46  lea     rax, [rbp+170h+var_1D0]
0x180159f4a  lea     rdx, word_1803561BE
0x180159f51  mov     qword ptr [rsp+270h+var_250], rax
0x180159f56  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180159f5b  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180159f62  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180159f67  jmp     short loc_180159F6C
0x180159f69  xor     r12d, r12d
0x180159f6c  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x180159f70  mov     [rsp+270h+var_248], r12; unsigned __int16 *
0x180159f75  mov     [rsp+270h+var_250], ebx; enum _MI_Result
0x180159f79  lea     r9, [rbp+170h+var_B0]; struct _MI_ConstUint32Field *
0x180159f80  mov     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x180159f84  mov     rcx, [rbp+170h+var_1A8]; unsigned __int16 *
0x180159f88  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180159f8d  test    r13d, r13d
0x180159f90  jnz     loc_18015A0FC
0x180159f96  lea     rcx, [rbp+170h+var_198]; this
0x180159f9a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180159f9f  mov     eax, cs:dword_180397B68
0x180159fa5  cmp     eax, 5
0x180159fa8  jbe     loc_18015A0FC
0x180159fae  mov     rdx, 400000000000h
0x180159fb8  lea     rcx, dword_180397B68
0x180159fbf  call    _tlgKeywordOn
0x180159fc4  test    al, al
0x180159fc6  jz      loc_18015A0FC
0x180159fcc  cmp     [r15+58h], r12b
0x180159fd0  jz      short loc_180159FD8
0x180159fd2  mov     eax, [r15+50h]
0x180159fd6  jmp     short loc_180159FDB
0x180159fd8  mov     eax, r12d
0x180159fdb  mov     dword ptr [rbp+170h+var_1F0], eax
0x180159fde  cmp     [rbp+170h+var_88], r12b
0x180159fe5  jz      short loc_18015A022
0x180159fe7  mov     rax, [rbp+170h+var_90]
0x180159fee  movups  xmm0, xmmword ptr [rax]
0x180159ff1  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x180159ff5  movups  xmm1, xmmword ptr [rax+10h]
0x180159ff9  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x180159ffd  movups  xmm0, xmmword ptr [rax+20h]
0x18015a001  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18015a005  movups  xmm1, xmmword ptr [rax+30h]
0x18015a009  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18015a00d  xor     r8d, r8d; unsigned __int16 *
0x18015a010  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18015a014  lea     rcx, name; "ObjectId"
0x18015a01b  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a020  jmp     short loc_18015A025
0x18015a022  mov     rax, r12
0x18015a025  mov     [rbp+170h+var_1A8], rax
0x18015a029  mov     [rbp+170h+var_1B0], r12
0x18015a02d  mov     [rbp+170h+var_1B8], r12
0x18015a031  mov     rax, [rbp+170h+var_190]
0x18015a035  sub     rax, [rbp+170h+var_198]
0x18015a039  imul    rax, 3E8h
0x18015a040  xor     edx, edx
0x18015a042  div     [rbp+170h+var_188]
0x18015a046  mov     [rbp+170h+var_1C0], rax
0x18015a04a  mov     [rbp+170h+var_1E4], ebx
0x18015a04d  mov     al, [rbp+170h+var_B0.exists]
0x18015a053  neg     al
0x18015a055  sbb     ecx, ecx
0x18015a057  and     ecx, [rbp+170h+var_B0.value]
0x18015a05d  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18015a060  mov     [rbp+170h+var_1E8], r14d
0x18015a064  cmp     [rsi+48h], r12b
0x18015a068  jz      short loc_18015A070
0x18015a06a  mov     rax, [rsi+40h]
0x18015a06e  jmp     short loc_18015A073
0x18015a070  mov     rax, r12
0x18015a073  mov     [rbp+170h+var_1C8], rax
0x18015a077  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18015a07e  mov     [rbp+170h+var_1D8], rax
0x18015a082  lea     rax, aStoragepool_0; "StoragePool"
0x18015a089  mov     [rbp+170h+var_1A0], rax
0x18015a08d  lea     rax, [rbp+170h+var_1F0]
0x18015a091  mov     [rsp+270h+var_200], rax
0x18015a096  lea     rax, [rbp+170h+var_1A8]
0x18015a09a  mov     [rsp+270h+var_208], rax
0x18015a09f  lea     rax, [rbp+170h+var_1B0]
0x18015a0a3  mov     [rsp+270h+var_210], rax
0x18015a0a8  lea     rax, [rbp+170h+var_1B8]
0x18015a0ac  mov     [rsp+270h+var_218], rax
0x18015a0b1  lea     rax, [rbp+170h+var_1C0]
0x18015a0b5  mov     [rsp+270h+var_220], rax
0x18015a0ba  lea     rax, [rbp+170h+var_1E4]
0x18015a0be  mov     [rsp+270h+var_228], rax
0x18015a0c3  lea     rax, [rbp+170h+var_1D0]
0x18015a0c7  mov     [rsp+270h+var_230], rax
0x18015a0cc  lea     rax, [rbp+170h+var_1E8]
0x18015a0d0  mov     [rsp+270h+var_238], rax
0x18015a0d5  lea     rax, [rbp+170h+var_1C8]
0x18015a0d9  mov     [rsp+270h+var_240], rax
0x18015a0de  lea     rax, [rbp+170h+var_1D8]
0x18015a0e2  mov     [rsp+270h+var_248], rax
0x18015a0e7  lea     rax, [rbp+170h+var_1A0]
0x18015a0eb  mov     qword ptr [rsp+270h+var_250], rax
0x18015a0f0  lea     rdx, unk_180355EE8
0x18015a0f7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@3445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18015a0fc  lea     rcx, [rbp+170h+instance]; self
0x18015a103  call    MI_Instance_Destruct
0x18015a108  mov     eax, cs:dword_180397B68
0x18015a10e  cmp     eax, 5
0x18015a111  jbe     short loc_18015A143
0x18015a113  mov     dword ptr [rbp+170h+var_1F0], 63Ah
0x18015a11a  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a121  mov     [rbp+170h+var_1A0], rax
0x18015a125  lea     rax, [rbp+170h+var_1F0]
0x18015a129  mov     [rsp+270h+var_248], rax
  ... truncated ...
```
