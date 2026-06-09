# SPACES_StoragePool_Invoke_SetSecurityDescriptor

- ea: `0x18015bda0`
- end: `0x18015c2dc`
- name: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
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
- `0x18015bda0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015be1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015be7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c2ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015be1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015be7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c2ac`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015be40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015be40`

## string_xrefs

- `0x18015c1b0`: `SetSecurityDescriptor`
- `0x18015be88`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18015bf9a`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18015bffb`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18015c06d`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18015c0c2`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18015c24a`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_SetSecurityDescriptor(
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
    LODWORD(v39) = 2207;
    v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_SetSecurityDescriptor",
      (unsigned int)&word_18035480E,
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
        LODWORD(v42) = 2238;
        v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&byte_180356297,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_SetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 2246;
          v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&dword_18035458C,
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
                720903,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 2257;
            v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&unk_1803567C8,
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
            LODWORD(v36) = 2265;
            v40 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_180354D39,
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
        v42 = "SetSecurityDescriptor";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&dword_1803543AC,
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
    LODWORD(v36) = 2298;
    v41 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)word_180354EEA,
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
0x18015bda0  mov     [rsp-8+arg_10], rbx
0x18015bda5  push    rbp
0x18015bda6  push    rsi
0x18015bda7  push    rdi
0x18015bda8  push    r12
0x18015bdaa  push    r13
0x18015bdac  push    r14
0x18015bdae  push    r15
0x18015bdb0  lea     rbp, [rsp-0E0h]
0x18015bdb8  sub     rsp, 1E0h
0x18015bdbf  mov     rax, cs:__security_cookie
0x18015bdc6  xor     rax, rsp
0x18015bdc9  mov     [rbp+110h+var_40], rax
0x18015bdd0  mov     [rbp+110h+var_178], r9
0x18015bdd4  mov     rdi, rdx
0x18015bdd7  mov     rsi, rcx
0x18015bdda  mov     rax, [rbp+110h+arg_20]
0x18015bde1  mov     [rbp+110h+var_150], rax
0x18015bde5  mov     r14, [rbp+110h+arg_28]
0x18015bdec  mov     r13, [rbp+110h+arg_30]
0x18015bdf3  xorps   xmm0, xmm0
0x18015bdf6  xor     eax, eax
0x18015bdf8  movups  xmmword ptr [rbp+110h+value], xmm0
0x18015bdfc  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18015be00  mov     qword ptr [rbp+110h+value+20h], rax
0x18015be04  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015be0b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18015be13  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18015be1a  lea     ecx, [rax+1]; ControlCode
0x18015be1d  call    cs:__imp_EventActivityIdControl
0x18015be23  lea     r9, [rbp+110h+value]; value
0x18015be27  mov     rcx, rdi; context
0x18015be2a  call    MI_Context_GetCustomOption_1
0x18015be2f  xor     ebx, ebx
0x18015be31  test    eax, eax
0x18015be33  jnz     short loc_18015BE46
0x18015be35  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18015be3c  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18015be40  call    cs:__imp_CLSIDFromString
0x18015be46  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18015be4d  mov     [rbp+110h+var_60], rcx
0x18015be54  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18015be5b  mov     [rbp+110h+var_58], rax
0x18015be62  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18015be69  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18015be70  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18015be77  mov     ecx, 4; ControlCode
0x18015be7c  call    cs:__imp_EventActivityIdControl
0x18015be82  mov     eax, cs:dword_180397B68
0x18015be88  lea     rcx, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015be8f  cmp     eax, 5
0x18015be92  jbe     short loc_18015BEBF
0x18015be94  mov     dword ptr [rbp+110h+var_188], 89Fh
0x18015be9b  mov     [rsp+210h+var_1A0], rcx
0x18015bea0  lea     rax, [rbp+110h+var_188]
0x18015bea4  mov     [rsp+210h+var_1E8], rax
0x18015bea9  lea     rax, [rsp+210h+var_1A0]
0x18015beae  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015beb3  lea     rdx, word_18035480E
0x18015beba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015bebf  mov     [rbp+110h+instance.ft], rbx
0x18015bec3  xor     edx, edx; Val
0x18015bec5  lea     r8d, [rdx+60h]; Size
0x18015bec9  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18015becd  call    memset_0
0x18015bed2  xorps   xmm0, xmm0
0x18015bed5  xor     eax, eax
0x18015bed7  movups  [rbp+110h+var_128], xmm0
0x18015bedb  mov     [rbp+110h+var_118], rax
0x18015bedf  mov     [rbp+110h+var_190], rbx
0x18015bee3  lea     rcx, [rbp+110h+var_190]
0x18015bee7  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015beec  mov     [rbp+110h+var_190], rbx
0x18015bef0  mov     r15d, ebx
0x18015bef3  lea     rcx, [rbp+110h+var_148]; this
0x18015bef7  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015befc  mov     rcx, rdi; context
0x18015beff  call    WspIsRemoteRequest
0x18015bf04  mov     r12d, eax
0x18015bf07  test    eax, eax
0x18015bf09  jnz     short loc_18015BF2F
0x18015bf0b  lea     rcx, [rbp+110h+var_148]; this
0x18015bf0f  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015bf14  cmp     [r14+48h], bl
0x18015bf18  jz      short loc_18015BF2C
0x18015bf1a  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015bf1e  call    WspIsRemoteInstance
0x18015bf23  test    al, al
0x18015bf25  lea     r15d, [r12+1]
0x18015bf2a  jnz     short loc_18015BF2F
0x18015bf2c  mov     r15d, ebx
0x18015bf2f  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015bf36  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015bf3b  mov     ebx, eax
0x18015bf3d  test    eax, eax
0x18015bf3f  jnz     loc_18015C102
0x18015bf45  mov     dword ptr [rbp+110h+var_128], 0Bh
0x18015bf4c  mov     rax, [r14+40h]
0x18015bf50  mov     qword ptr [rbp+110h+var_128+8], rax
0x18015bf54  mov     rbx, [rsi]
0x18015bf57  lea     rcx, [rbp+110h+var_190]
0x18015bf5b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015bf60  mov     [rsp+210h+var_1F0], 1; int
0x18015bf68  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18015bf6c  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x18015bf70  mov     rdx, rdi; context
0x18015bf73  mov     rcx, rbx; this
0x18015bf76  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015bf7b  mov     ebx, eax
0x18015bf7d  test    eax, eax
0x18015bf7f  jz      short loc_18015BFC9
0x18015bf81  mov     eax, cs:dword_180397B68
0x18015bf87  cmp     eax, 2
0x18015bf8a  jbe     loc_18015C0F6
0x18015bf90  mov     dword ptr [rbp+110h+var_188], ebx
0x18015bf93  mov     dword ptr [rbp+110h+var_170], 8BEh
0x18015bf9a  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015bfa1  mov     [rsp+210h+var_1A0], rax
0x18015bfa6  lea     rax, [rbp+110h+var_188]
0x18015bfaa  mov     [rsp+210h+var_1E0], rax
0x18015bfaf  lea     rax, [rbp+110h+var_170]
0x18015bfb3  mov     [rsp+210h+var_1E8], rax
0x18015bfb8  lea     rax, [rsp+210h+var_1A0]
0x18015bfbd  lea     rdx, byte_180356297
0x18015bfc4  jmp     loc_18015C0EC
0x18015bfc9  lea     r8, [rbp+110h+instance]; instance
0x18015bfcd  lea     rdx, SPACES_StoragePool_SetSecurityDescriptor_rtti; methodDecl
0x18015bfd4  mov     rcx, rdi; context
0x18015bfd7  call    MI_Context_ConstructParameters
0x18015bfdc  mov     ebx, eax
0x18015bfde  test    eax, eax
0x18015bfe0  jz      short loc_18015C02A
0x18015bfe2  mov     eax, cs:dword_180397B68
0x18015bfe8  cmp     eax, 2
0x18015bfeb  jbe     loc_18015C0F6
0x18015bff1  mov     dword ptr [rbp+110h+var_168], ebx
0x18015bff4  mov     dword ptr [rbp+110h+var_160], 8C6h
0x18015bffb  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015c002  mov     [rsp+210h+var_1A0], rax
0x18015c007  lea     rax, [rbp+110h+var_168]
0x18015c00b  mov     [rsp+210h+var_1E0], rax
0x18015c010  lea     rax, [rbp+110h+var_160]
0x18015c014  mov     [rsp+210h+var_1E8], rax
0x18015c019  lea     rax, [rsp+210h+var_1A0]
0x18015c01e  lea     rdx, dword_18035458C
0x18015c025  jmp     loc_18015C0EC
0x18015c02a  mov     rcx, [rbp+110h+var_190]
0x18015c02e  mov     rax, [rcx]
0x18015c031  lea     rdx, [rbp+110h+instance]
0x18015c035  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18015c03a  mov     r9, r13
0x18015c03d  mov     r8, rdi
0x18015c040  mov     edx, 0B0007h
0x18015c045  mov     rax, [rax+30h]
0x18015c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c04e  mov     ebx, eax
0x18015c050  test    eax, eax
0x18015c052  jz      short loc_18015C099
0x18015c054  mov     eax, cs:dword_180397B68
0x18015c05a  cmp     eax, 2
0x18015c05d  jbe     loc_18015C0F6
0x18015c063  mov     dword ptr [rbp+110h+var_158], ebx
0x18015c066  mov     dword ptr [rbp+110h+var_180], 8D1h
0x18015c06d  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015c074  mov     [rsp+210h+var_1A0], rax
0x18015c079  lea     rax, [rbp+110h+var_158]
0x18015c07d  mov     [rsp+210h+var_1E0], rax
0x18015c082  lea     rax, [rbp+110h+var_180]
0x18015c086  mov     [rsp+210h+var_1E8], rax
0x18015c08b  lea     rax, [rsp+210h+var_1A0]
0x18015c090  lea     rdx, unk_1803567C8
0x18015c097  jmp     short loc_18015C0EC
0x18015c099  lea     rdx, [rbp+110h+instance]
0x18015c09d  mov     rcx, rdi; self
0x18015c0a0  call    MI_Instance_Destruct
0x18015c0a5  mov     ebx, eax
0x18015c0a7  test    eax, eax
0x18015c0a9  jz      short loc_18015C0F6
0x18015c0ab  mov     eax, cs:dword_180397B68
0x18015c0b1  cmp     eax, 2
0x18015c0b4  jbe     short loc_18015C0F6
0x18015c0b6  mov     [rsp+210h+var_198], ebx
0x18015c0ba  mov     dword ptr [rsp+210h+var_1A0], 8D9h
0x18015c0c2  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015c0c9  mov     [rbp+110h+var_180], rax
0x18015c0cd  lea     rax, [rsp+210h+var_198]
0x18015c0d2  mov     [rsp+210h+var_1E0], rax
0x18015c0d7  lea     rax, [rsp+210h+var_1A0]
0x18015c0dc  mov     [rsp+210h+var_1E8], rax
0x18015c0e1  lea     rax, [rbp+110h+var_180]
0x18015c0e5  lea     rdx, byte_180354D39
0x18015c0ec  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015c0f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015c0f6  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015c0fd  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015c102  xor     r13d, r13d
0x18015c105  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18015c10a  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18015c10e  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18015c112  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18015c116  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18015c11a  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18015c11e  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015c123  test    r12d, r12d
0x18015c126  jnz     loc_18015C22E
0x18015c12c  lea     rcx, [rbp+110h+var_148]; this
0x18015c130  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015c135  mov     eax, cs:dword_180397B68
0x18015c13b  cmp     eax, 5
0x18015c13e  jbe     loc_18015C22E
0x18015c144  mov     rdx, 400000000000h
0x18015c14e  lea     rcx, dword_180397B68
0x18015c155  call    _tlgKeywordOn
0x18015c15a  test    al, al
0x18015c15c  jz      loc_18015C22E
0x18015c162  mov     [rbp+110h+var_178], r13
0x18015c166  mov     [rbp+110h+var_150], r13
0x18015c16a  mov     [rbp+110h+var_158], r13
0x18015c16e  mov     rax, [rbp+110h+var_140]
0x18015c172  sub     rax, [rbp+110h+var_148]
0x18015c176  imul    rax, 3E8h
0x18015c17d  xor     edx, edx
0x18015c17f  div     [rbp+110h+var_138]
0x18015c183  mov     [rbp+110h+var_160], rax
0x18015c187  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18015c18b  mov     al, [rbp+110h+var_A0.exists]
0x18015c18e  neg     al
0x18015c190  sbb     ecx, ecx
0x18015c192  and     ecx, [rbp+110h+var_A0.value]
0x18015c195  mov     [rsp+210h+var_198], ecx
0x18015c199  mov     dword ptr [rbp+110h+var_180], r15d
0x18015c19d  cmp     [r14+48h], r13b
0x18015c1a1  jz      short loc_18015C1A9
0x18015c1a3  mov     rax, [r14+40h]
0x18015c1a7  jmp     short loc_18015C1AC
0x18015c1a9  mov     rax, r13
0x18015c1ac  mov     [rbp+110h+var_168], rax
0x18015c1b0  lea     rax, aSetsecuritydes_0; "SetSecurityDescriptor"
0x18015c1b7  mov     [rbp+110h+var_170], rax
0x18015c1bb  lea     rax, aStoragepool_0; "StoragePool"
0x18015c1c2  mov     [rbp+110h+var_188], rax
0x18015c1c6  lea     rax, [rbp+110h+var_178]
0x18015c1ca  mov     [rsp+210h+var_1A8], rax
0x18015c1cf  lea     rax, [rbp+110h+var_150]
0x18015c1d3  mov     [rsp+210h+var_1B0], rax
0x18015c1d8  lea     rax, [rbp+110h+var_158]
0x18015c1dc  mov     [rsp+210h+var_1B8], rax
0x18015c1e1  lea     rax, [rbp+110h+var_160]
0x18015c1e5  mov     [rsp+210h+var_1C0], rax
0x18015c1ea  lea     rax, [rsp+210h+var_1A0]
0x18015c1ef  mov     [rsp+210h+var_1C8], rax
0x18015c1f4  lea     rax, [rsp+210h+var_198]
0x18015c1f9  mov     [rsp+210h+var_1D0], rax
0x18015c1fe  lea     rax, [rbp+110h+var_180]
0x18015c202  mov     [rsp+210h+var_1D8], rax
0x18015c207  lea     rax, [rbp+110h+var_168]
0x18015c20b  mov     [rsp+210h+var_1E0], rax
0x18015c210  lea     rax, [rbp+110h+var_170]
0x18015c214  mov     [rsp+210h+var_1E8], rax
0x18015c219  lea     rax, [rbp+110h+var_188]
0x18015c21d  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015c222  lea     rdx, dword_1803543AC
0x18015c229  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18015c22e  lea     rcx, [rbp+110h+instance]; self
0x18015c232  call    MI_Instance_Destruct
0x18015c237  mov     eax, cs:dword_180397B68
0x18015c23d  cmp     eax, 5
0x18015c240  jbe     short loc_18015C274
0x18015c242  mov     dword ptr [rsp+210h+var_1A0], 8FAh
0x18015c24a  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18015c251  mov     [rbp+110h+var_178], rax
0x18015c255  lea     rax, [rsp+210h+var_1A0]
0x18015c25a  mov     [rsp+210h+var_1E8], rax
0x18015c25f  lea     rax, [rbp+110h+var_178]
0x18015c263  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015c268  lea     rdx, word_180354EEA
0x18015c26f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015c274  test    rdi, rdi
0x18015c277  jz      short loc_18015C28E
0x18015c279  mov     rax, [rdi]
0x18015c27c  test    rax, rax
0x18015c27f  jz      short loc_18015C28E
0x18015c281  mov     edx, ebx
0x18015c283  mov     rcx, rdi
0x18015c286  mov     rax, [rax]
0x18015c289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c28e  lea     rcx, [rbp+110h+var_148]; this
0x18015c292  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18015c297  lea     rcx, [rbp+110h+var_190]
0x18015c29b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015c2a0  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18015c2a7  mov     ecx, 4; ControlCode
0x18015c2ac  call    cs:__imp_EventActivityIdControl
0x18015c2b2  mov     rcx, [rbp+110h+var_40]
0x18015c2b9  xor     rcx, rsp; StackCookie
0x18015c2bc  call    __security_check_cookie
0x18015c2c1  mov     rbx, [rsp+210h+arg_10]
0x18015c2c9  add     rsp, 1E0h
0x18015c2d0  pop     r15
0x18015c2d2  pop     r14
  ... truncated ...
```
