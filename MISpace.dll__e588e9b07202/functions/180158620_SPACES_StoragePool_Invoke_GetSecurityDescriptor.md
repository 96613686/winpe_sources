# SPACES_StoragePool_Invoke_GetSecurityDescriptor

- ea: `0x180158620`
- end: `0x180158b5c`
- name: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- size: `1340`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
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
- `0x180137a24`
- `0x180138120`
- `0x180158620`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015869d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801586fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180158b2c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015869d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801586fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180158b2c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801586c0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801586c0`

## string_xrefs

- `0x180158a30`: `GetSecurityDescriptor`
- `0x180158708`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015881a`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015887b`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x1801588ed`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x180158942`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x180158aca`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_GetSecurityDescriptor(
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
  const MI_Char *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const char *v36; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v37; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v43; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v47[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h]
  MI_Value value; // [rsp+100h] [rbp+0h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v54; // [rsp+1B0h] [rbp+B0h]
  GUID v55; // [rsp+1C0h] [rbp+C0h] BYREF

  v41 = a4;
  v46 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v54 = ActivityId;
  v55 = ActivityId;
  EventActivityIdControl(4u, &v55);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v39) = 2100;
    v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_GetSecurityDescriptor",
      (unsigned int)byte_18035467D,
      v11,
      v12,
      (__int64)&v36,
      (__int64)&v39);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v48 = 0;
  v49 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v47);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v47);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v48) = 11;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v39) = v15;
        LODWORD(v42) = 2131;
        v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_180355944,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_GetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 2139;
          v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_180355199,
            v21,
            v22,
            (__int64)&v36,
            (__int64)&v44,
            (__int64)&v43);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720902,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 2150;
            v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&unk_180354C28,
              v24,
              v25,
              (__int64)&v36,
              (__int64)&v40,
              (__int64)&v45);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_180397B68 > 2 )
          {
            v37 = v15;
            LODWORD(v36) = 2158;
            v40 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_180354965,
              v27,
              v28,
              (__int64)&v40,
              (__int64)&v36,
              (__int64)&v37);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v41, v46, a6 + 4, &v52, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v47);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        v41 = 0;
        v46 = 0;
        v45 = 0;
        v44 = (unsigned __int64)(1000LL * (v47[1] - v47[0])) / v47[2];
        LODWORD(v36) = v15;
        v37 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v40) = v13;
        if ( a6[4].exists )
          v31 = a6[4].value;
        else
          v31 = 0;
        v43 = v31;
        v42 = "GetSecurityDescriptor";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&byte_1803559EF,
          v29,
          v30,
          (__int64)&v39,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v41);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v36) = 2191;
    v41 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)qword_1803562D0,
      v33,
      v34,
      (__int64)&v41,
      (__int64)&v36);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v47);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v55);
}

```

## disassembly

```asm
0x180158620  mov     [rsp-8+arg_10], rbx
0x180158625  push    rbp
0x180158626  push    rsi
0x180158627  push    rdi
0x180158628  push    r12
0x18015862a  push    r13
0x18015862c  push    r14
0x18015862e  push    r15
0x180158630  lea     rbp, [rsp-0E0h]
0x180158638  sub     rsp, 1E0h
0x18015863f  mov     rax, cs:__security_cookie
0x180158646  xor     rax, rsp
0x180158649  mov     [rbp+110h+var_40], rax
0x180158650  mov     [rbp+110h+var_178], r9
0x180158654  mov     rdi, rdx
0x180158657  mov     rsi, rcx
0x18015865a  mov     rax, [rbp+110h+arg_20]
0x180158661  mov     [rbp+110h+var_150], rax
0x180158665  mov     r14, [rbp+110h+arg_28]
0x18015866c  mov     r13, [rbp+110h+arg_30]
0x180158673  xorps   xmm0, xmm0
0x180158676  xor     eax, eax
0x180158678  movups  xmmword ptr [rbp+110h+value], xmm0
0x18015867c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x180158680  mov     qword ptr [rbp+110h+value+20h], rax
0x180158684  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015868b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x180158693  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18015869a  lea     ecx, [rax+1]; ControlCode
0x18015869d  call    cs:__imp_EventActivityIdControl
0x1801586a3  lea     r9, [rbp+110h+value]; value
0x1801586a7  mov     rcx, rdi; context
0x1801586aa  call    MI_Context_GetCustomOption_1
0x1801586af  xor     ebx, ebx
0x1801586b1  test    eax, eax
0x1801586b3  jnz     short loc_1801586C6
0x1801586b5  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x1801586bc  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x1801586c0  call    cs:__imp_CLSIDFromString
0x1801586c6  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x1801586cd  mov     [rbp+110h+var_60], rcx
0x1801586d4  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x1801586db  mov     [rbp+110h+var_58], rax
0x1801586e2  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x1801586e9  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x1801586f0  lea     rdx, [rbp+110h+var_50]; ActivityId
0x1801586f7  mov     ecx, 4; ControlCode
0x1801586fc  call    cs:__imp_EventActivityIdControl
0x180158702  mov     eax, cs:dword_180397B68
0x180158708  lea     rcx, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015870f  cmp     eax, 5
0x180158712  jbe     short loc_18015873F
0x180158714  mov     dword ptr [rbp+110h+var_188], 834h
0x18015871b  mov     [rsp+210h+var_1A0], rcx
0x180158720  lea     rax, [rbp+110h+var_188]
0x180158724  mov     [rsp+210h+var_1E8], rax
0x180158729  lea     rax, [rsp+210h+var_1A0]
0x18015872e  mov     qword ptr [rsp+210h+var_1F0], rax
0x180158733  lea     rdx, byte_18035467D
0x18015873a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015873f  mov     [rbp+110h+instance.ft], rbx
0x180158743  xor     edx, edx; Val
0x180158745  lea     r8d, [rdx+60h]; Size
0x180158749  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18015874d  call    memset_0
0x180158752  xorps   xmm0, xmm0
0x180158755  xor     eax, eax
0x180158757  movups  [rbp+110h+var_128], xmm0
0x18015875b  mov     [rbp+110h+var_118], rax
0x18015875f  mov     [rbp+110h+var_190], rbx
0x180158763  lea     rcx, [rbp+110h+var_190]
0x180158767  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015876c  mov     [rbp+110h+var_190], rbx
0x180158770  mov     r15d, ebx
0x180158773  lea     rcx, [rbp+110h+var_148]; this
0x180158777  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015877c  mov     rcx, rdi; context
0x18015877f  call    WspIsRemoteRequest
0x180158784  mov     r12d, eax
0x180158787  test    eax, eax
0x180158789  jnz     short loc_1801587AF
0x18015878b  lea     rcx, [rbp+110h+var_148]; this
0x18015878f  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180158794  cmp     [r14+48h], bl
0x180158798  jz      short loc_1801587AC
0x18015879a  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015879e  call    WspIsRemoteInstance
0x1801587a3  test    al, al
0x1801587a5  lea     r15d, [r12+1]
0x1801587aa  jnz     short loc_1801587AF
0x1801587ac  mov     r15d, ebx
0x1801587af  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801587b6  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801587bb  mov     ebx, eax
0x1801587bd  test    eax, eax
0x1801587bf  jnz     loc_180158982
0x1801587c5  mov     dword ptr [rbp+110h+var_128], 0Bh
0x1801587cc  mov     rax, [r14+40h]
0x1801587d0  mov     qword ptr [rbp+110h+var_128+8], rax
0x1801587d4  mov     rbx, [rsi]
0x1801587d7  lea     rcx, [rbp+110h+var_190]
0x1801587db  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801587e0  mov     [rsp+210h+var_1F0], 1; int
0x1801587e8  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x1801587ec  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x1801587f0  mov     rdx, rdi; context
0x1801587f3  mov     rcx, rbx; this
0x1801587f6  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x1801587fb  mov     ebx, eax
0x1801587fd  test    eax, eax
0x1801587ff  jz      short loc_180158849
0x180158801  mov     eax, cs:dword_180397B68
0x180158807  cmp     eax, 2
0x18015880a  jbe     loc_180158976
0x180158810  mov     dword ptr [rbp+110h+var_188], ebx
0x180158813  mov     dword ptr [rbp+110h+var_170], 853h
0x18015881a  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x180158821  mov     [rsp+210h+var_1A0], rax
0x180158826  lea     rax, [rbp+110h+var_188]
0x18015882a  mov     [rsp+210h+var_1E0], rax
0x18015882f  lea     rax, [rbp+110h+var_170]
0x180158833  mov     [rsp+210h+var_1E8], rax
0x180158838  lea     rax, [rsp+210h+var_1A0]
0x18015883d  lea     rdx, dword_180355944
0x180158844  jmp     loc_18015896C
0x180158849  lea     r8, [rbp+110h+instance]; instance
0x18015884d  lea     rdx, SPACES_StoragePool_GetSecurityDescriptor_rtti; methodDecl
0x180158854  mov     rcx, rdi; context
0x180158857  call    MI_Context_ConstructParameters
0x18015885c  mov     ebx, eax
0x18015885e  test    eax, eax
0x180158860  jz      short loc_1801588AA
0x180158862  mov     eax, cs:dword_180397B68
0x180158868  cmp     eax, 2
0x18015886b  jbe     loc_180158976
0x180158871  mov     dword ptr [rbp+110h+var_168], ebx
0x180158874  mov     dword ptr [rbp+110h+var_160], 85Bh
0x18015887b  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x180158882  mov     [rsp+210h+var_1A0], rax
0x180158887  lea     rax, [rbp+110h+var_168]
0x18015888b  mov     [rsp+210h+var_1E0], rax
0x180158890  lea     rax, [rbp+110h+var_160]
0x180158894  mov     [rsp+210h+var_1E8], rax
0x180158899  lea     rax, [rsp+210h+var_1A0]
0x18015889e  lea     rdx, byte_180355199
0x1801588a5  jmp     loc_18015896C
0x1801588aa  mov     rcx, [rbp+110h+var_190]
0x1801588ae  mov     rax, [rcx]
0x1801588b1  lea     rdx, [rbp+110h+instance]
0x1801588b5  mov     qword ptr [rsp+210h+var_1F0], rdx
0x1801588ba  mov     r9, r13
0x1801588bd  mov     r8, rdi
0x1801588c0  mov     edx, 0B0006h
0x1801588c5  mov     rax, [rax+30h]
0x1801588c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801588ce  mov     ebx, eax
0x1801588d0  test    eax, eax
0x1801588d2  jz      short loc_180158919
0x1801588d4  mov     eax, cs:dword_180397B68
0x1801588da  cmp     eax, 2
0x1801588dd  jbe     loc_180158976
0x1801588e3  mov     dword ptr [rbp+110h+var_158], ebx
0x1801588e6  mov     dword ptr [rbp+110h+var_180], 866h
0x1801588ed  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x1801588f4  mov     [rsp+210h+var_1A0], rax
0x1801588f9  lea     rax, [rbp+110h+var_158]
0x1801588fd  mov     [rsp+210h+var_1E0], rax
0x180158902  lea     rax, [rbp+110h+var_180]
0x180158906  mov     [rsp+210h+var_1E8], rax
0x18015890b  lea     rax, [rsp+210h+var_1A0]
0x180158910  lea     rdx, unk_180354C28
0x180158917  jmp     short loc_18015896C
0x180158919  lea     rdx, [rbp+110h+instance]
0x18015891d  mov     rcx, rdi; self
0x180158920  call    MI_Instance_Destruct
0x180158925  mov     ebx, eax
0x180158927  test    eax, eax
0x180158929  jz      short loc_180158976
0x18015892b  mov     eax, cs:dword_180397B68
0x180158931  cmp     eax, 2
0x180158934  jbe     short loc_180158976
0x180158936  mov     [rsp+210h+var_198], ebx
0x18015893a  mov     dword ptr [rsp+210h+var_1A0], 86Eh
0x180158942  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x180158949  mov     [rbp+110h+var_180], rax
0x18015894d  lea     rax, [rsp+210h+var_198]
0x180158952  mov     [rsp+210h+var_1E0], rax
0x180158957  lea     rax, [rsp+210h+var_1A0]
0x18015895c  mov     [rsp+210h+var_1E8], rax
0x180158961  lea     rax, [rbp+110h+var_180]
0x180158965  lea     rdx, byte_180354965
0x18015896c  mov     qword ptr [rsp+210h+var_1F0], rax
0x180158971  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180158976  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015897d  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180158982  xor     r13d, r13d
0x180158985  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18015898a  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18015898e  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x180158992  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x180158996  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18015899a  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18015899e  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801589a3  test    r12d, r12d
0x1801589a6  jnz     loc_180158AAE
0x1801589ac  lea     rcx, [rbp+110h+var_148]; this
0x1801589b0  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801589b5  mov     eax, cs:dword_180397B68
0x1801589bb  cmp     eax, 5
0x1801589be  jbe     loc_180158AAE
0x1801589c4  mov     rdx, 400000000000h
0x1801589ce  lea     rcx, dword_180397B68
0x1801589d5  call    _tlgKeywordOn
0x1801589da  test    al, al
0x1801589dc  jz      loc_180158AAE
0x1801589e2  mov     [rbp+110h+var_178], r13
0x1801589e6  mov     [rbp+110h+var_150], r13
0x1801589ea  mov     [rbp+110h+var_158], r13
0x1801589ee  mov     rax, [rbp+110h+var_140]
0x1801589f2  sub     rax, [rbp+110h+var_148]
0x1801589f6  imul    rax, 3E8h
0x1801589fd  xor     edx, edx
0x1801589ff  div     [rbp+110h+var_138]
0x180158a03  mov     [rbp+110h+var_160], rax
0x180158a07  mov     dword ptr [rsp+210h+var_1A0], ebx
0x180158a0b  mov     al, [rbp+110h+var_A0.exists]
0x180158a0e  neg     al
0x180158a10  sbb     ecx, ecx
0x180158a12  and     ecx, [rbp+110h+var_A0.value]
0x180158a15  mov     [rsp+210h+var_198], ecx
0x180158a19  mov     dword ptr [rbp+110h+var_180], r15d
0x180158a1d  cmp     [r14+48h], r13b
0x180158a21  jz      short loc_180158A29
0x180158a23  mov     rax, [r14+40h]
0x180158a27  jmp     short loc_180158A2C
0x180158a29  mov     rax, r13
0x180158a2c  mov     [rbp+110h+var_168], rax
0x180158a30  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptor"
0x180158a37  mov     [rbp+110h+var_170], rax
0x180158a3b  lea     rax, aStoragepool_0; "StoragePool"
0x180158a42  mov     [rbp+110h+var_188], rax
0x180158a46  lea     rax, [rbp+110h+var_178]
0x180158a4a  mov     [rsp+210h+var_1A8], rax
0x180158a4f  lea     rax, [rbp+110h+var_150]
0x180158a53  mov     [rsp+210h+var_1B0], rax
0x180158a58  lea     rax, [rbp+110h+var_158]
0x180158a5c  mov     [rsp+210h+var_1B8], rax
0x180158a61  lea     rax, [rbp+110h+var_160]
0x180158a65  mov     [rsp+210h+var_1C0], rax
0x180158a6a  lea     rax, [rsp+210h+var_1A0]
0x180158a6f  mov     [rsp+210h+var_1C8], rax
0x180158a74  lea     rax, [rsp+210h+var_198]
0x180158a79  mov     [rsp+210h+var_1D0], rax
0x180158a7e  lea     rax, [rbp+110h+var_180]
0x180158a82  mov     [rsp+210h+var_1D8], rax
0x180158a87  lea     rax, [rbp+110h+var_168]
0x180158a8b  mov     [rsp+210h+var_1E0], rax
0x180158a90  lea     rax, [rbp+110h+var_170]
0x180158a94  mov     [rsp+210h+var_1E8], rax
0x180158a99  lea     rax, [rbp+110h+var_188]
0x180158a9d  mov     qword ptr [rsp+210h+var_1F0], rax
0x180158aa2  lea     rdx, byte_1803559EF
0x180158aa9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180158aae  lea     rcx, [rbp+110h+instance]; self
0x180158ab2  call    MI_Instance_Destruct
0x180158ab7  mov     eax, cs:dword_180397B68
0x180158abd  cmp     eax, 5
0x180158ac0  jbe     short loc_180158AF4
0x180158ac2  mov     dword ptr [rsp+210h+var_1A0], 88Fh
0x180158aca  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x180158ad1  mov     [rbp+110h+var_178], rax
0x180158ad5  lea     rax, [rsp+210h+var_1A0]
0x180158ada  mov     [rsp+210h+var_1E8], rax
0x180158adf  lea     rax, [rbp+110h+var_178]
0x180158ae3  mov     qword ptr [rsp+210h+var_1F0], rax
0x180158ae8  lea     rdx, qword_1803562D0
0x180158aef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180158af4  test    rdi, rdi
0x180158af7  jz      short loc_180158B0E
0x180158af9  mov     rax, [rdi]
0x180158afc  test    rax, rax
0x180158aff  jz      short loc_180158B0E
0x180158b01  mov     edx, ebx
0x180158b03  mov     rcx, rdi
0x180158b06  mov     rax, [rax]
0x180158b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158b0e  lea     rcx, [rbp+110h+var_148]; this
0x180158b12  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180158b17  lea     rcx, [rbp+110h+var_190]
0x180158b1b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180158b20  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180158b27  mov     ecx, 4; ControlCode
0x180158b2c  call    cs:__imp_EventActivityIdControl
0x180158b32  mov     rcx, [rbp+110h+var_40]
0x180158b39  xor     rcx, rsp; StackCookie
0x180158b3c  call    __security_check_cookie
0x180158b41  mov     rbx, [rsp+210h+arg_10]
0x180158b49  add     rsp, 1E0h
0x180158b50  pop     r15
0x180158b52  pop     r14
  ... truncated ...
```
