# SPACES_VirtualDisk_Invoke_SetSecurityDescriptor

- ea: `0x18013dfc0`
- end: `0x18013e4fc`
- name: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
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
- `0x18013dfc0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e03d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e09c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e4cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e03d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e09c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e4cc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013e060`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013e060`

## string_xrefs

- `0x18013e0a8`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e1ba`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e21b`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e28d`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e2e2`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e46a`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18013e3d0`: `SetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_SetSecurityDescriptor(
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
    LODWORD(v39) = 576;
    v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_SetSecurityDescriptor",
      (unsigned int)byte_18034A851,
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
  CSmTimer::CSmTimer((CSmTimer *)v47);
  v13 = 0;
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
    LODWORD(v48) = 16;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v39) = v15;
        LODWORD(v42) = 607;
        v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_18034CC91,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_SetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 615;
          v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&unk_18034B678,
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
                1048581,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 626;
            v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_18034BD9A,
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
            LODWORD(v36) = 634;
            v40 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18034B32D,
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
        v39 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&word_18034C8E6,
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
    LODWORD(v36) = 667;
    v41 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)&dword_18034B434,
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
0x18013dfc0  mov     [rsp-8+arg_10], rbx
0x18013dfc5  push    rbp
0x18013dfc6  push    rsi
0x18013dfc7  push    rdi
0x18013dfc8  push    r12
0x18013dfca  push    r13
0x18013dfcc  push    r14
0x18013dfce  push    r15
0x18013dfd0  lea     rbp, [rsp-0E0h]
0x18013dfd8  sub     rsp, 1E0h
0x18013dfdf  mov     rax, cs:__security_cookie
0x18013dfe6  xor     rax, rsp
0x18013dfe9  mov     [rbp+110h+var_40], rax
0x18013dff0  mov     [rbp+110h+var_178], r9
0x18013dff4  mov     rdi, rdx
0x18013dff7  mov     rsi, rcx
0x18013dffa  mov     rax, [rbp+110h+arg_20]
0x18013e001  mov     [rbp+110h+var_150], rax
0x18013e005  mov     r14, [rbp+110h+arg_28]
0x18013e00c  mov     r13, [rbp+110h+arg_30]
0x18013e013  xorps   xmm0, xmm0
0x18013e016  xor     eax, eax
0x18013e018  movups  xmmword ptr [rbp+110h+value], xmm0
0x18013e01c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18013e020  mov     qword ptr [rbp+110h+value+20h], rax
0x18013e024  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013e02b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18013e033  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18013e03a  lea     ecx, [rax+1]; ControlCode
0x18013e03d  call    cs:__imp_EventActivityIdControl
0x18013e043  lea     r9, [rbp+110h+value]; value
0x18013e047  mov     rcx, rdi; context
0x18013e04a  call    MI_Context_GetCustomOption_1
0x18013e04f  xor     ebx, ebx
0x18013e051  test    eax, eax
0x18013e053  jnz     short loc_18013E066
0x18013e055  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18013e05c  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18013e060  call    cs:__imp_CLSIDFromString
0x18013e066  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18013e06d  mov     [rbp+110h+var_60], rcx
0x18013e074  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18013e07b  mov     [rbp+110h+var_58], rax
0x18013e082  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18013e089  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18013e090  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013e097  mov     ecx, 4; ControlCode
0x18013e09c  call    cs:__imp_EventActivityIdControl
0x18013e0a2  mov     eax, cs:dword_180397B68
0x18013e0a8  lea     rcx, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e0af  cmp     eax, 5
0x18013e0b2  jbe     short loc_18013E0DF
0x18013e0b4  mov     dword ptr [rbp+110h+var_188], 240h
0x18013e0bb  mov     [rsp+210h+var_1A0], rcx
0x18013e0c0  lea     rax, [rbp+110h+var_188]
0x18013e0c4  mov     [rsp+210h+var_1E8], rax
0x18013e0c9  lea     rax, [rsp+210h+var_1A0]
0x18013e0ce  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013e0d3  lea     rdx, byte_18034A851
0x18013e0da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013e0df  mov     [rbp+110h+instance.ft], rbx
0x18013e0e3  xor     edx, edx; Val
0x18013e0e5  lea     r8d, [rdx+60h]; Size
0x18013e0e9  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18013e0ed  call    memset_0
0x18013e0f2  xorps   xmm0, xmm0
0x18013e0f5  xor     eax, eax
0x18013e0f7  movups  [rbp+110h+var_128], xmm0
0x18013e0fb  mov     [rbp+110h+var_118], rax
0x18013e0ff  mov     [rbp+110h+var_190], rbx
0x18013e103  lea     rcx, [rbp+110h+var_190]
0x18013e107  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013e10c  mov     [rbp+110h+var_190], rbx
0x18013e110  lea     rcx, [rbp+110h+var_148]; this
0x18013e114  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013e119  mov     r15d, ebx
0x18013e11c  mov     rcx, rdi; context
0x18013e11f  call    WspIsRemoteRequest
0x18013e124  mov     r12d, eax
0x18013e127  test    eax, eax
0x18013e129  jnz     short loc_18013E14F
0x18013e12b  lea     rcx, [rbp+110h+var_148]; this
0x18013e12f  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013e134  cmp     [r14+48h], bl
0x18013e138  jz      short loc_18013E14C
0x18013e13a  mov     rcx, [r14+40h]; unsigned __int16 *
0x18013e13e  call    WspIsRemoteInstance
0x18013e143  test    al, al
0x18013e145  lea     r15d, [r12+1]
0x18013e14a  jnz     short loc_18013E14F
0x18013e14c  mov     r15d, ebx
0x18013e14f  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013e156  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013e15b  mov     ebx, eax
0x18013e15d  test    eax, eax
0x18013e15f  jnz     loc_18013E322
0x18013e165  mov     dword ptr [rbp+110h+var_128], 10h
0x18013e16c  mov     rax, [r14+40h]
0x18013e170  mov     qword ptr [rbp+110h+var_128+8], rax
0x18013e174  mov     rbx, [rsi]
0x18013e177  lea     rcx, [rbp+110h+var_190]
0x18013e17b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013e180  mov     [rsp+210h+var_1F0], 1; int
0x18013e188  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18013e18c  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x18013e190  mov     rdx, rdi; context
0x18013e193  mov     rcx, rbx; this
0x18013e196  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013e19b  mov     ebx, eax
0x18013e19d  test    eax, eax
0x18013e19f  jz      short loc_18013E1E9
0x18013e1a1  mov     eax, cs:dword_180397B68
0x18013e1a7  cmp     eax, 2
0x18013e1aa  jbe     loc_18013E316
0x18013e1b0  mov     dword ptr [rbp+110h+var_188], ebx
0x18013e1b3  mov     dword ptr [rbp+110h+var_170], 25Fh
0x18013e1ba  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e1c1  mov     [rsp+210h+var_1A0], rax
0x18013e1c6  lea     rax, [rbp+110h+var_188]
0x18013e1ca  mov     [rsp+210h+var_1E0], rax
0x18013e1cf  lea     rax, [rbp+110h+var_170]
0x18013e1d3  mov     [rsp+210h+var_1E8], rax
0x18013e1d8  lea     rax, [rsp+210h+var_1A0]
0x18013e1dd  lea     rdx, byte_18034CC91
0x18013e1e4  jmp     loc_18013E30C
0x18013e1e9  lea     r8, [rbp+110h+instance]; instance
0x18013e1ed  lea     rdx, SPACES_VirtualDisk_SetSecurityDescriptor_rtti; methodDecl
0x18013e1f4  mov     rcx, rdi; context
0x18013e1f7  call    MI_Context_ConstructParameters
0x18013e1fc  mov     ebx, eax
0x18013e1fe  test    eax, eax
0x18013e200  jz      short loc_18013E24A
0x18013e202  mov     eax, cs:dword_180397B68
0x18013e208  cmp     eax, 2
0x18013e20b  jbe     loc_18013E316
0x18013e211  mov     dword ptr [rbp+110h+var_168], ebx
0x18013e214  mov     dword ptr [rbp+110h+var_160], 267h
0x18013e21b  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e222  mov     [rsp+210h+var_1A0], rax
0x18013e227  lea     rax, [rbp+110h+var_168]
0x18013e22b  mov     [rsp+210h+var_1E0], rax
0x18013e230  lea     rax, [rbp+110h+var_160]
0x18013e234  mov     [rsp+210h+var_1E8], rax
0x18013e239  lea     rax, [rsp+210h+var_1A0]
0x18013e23e  lea     rdx, unk_18034B678
0x18013e245  jmp     loc_18013E30C
0x18013e24a  mov     rcx, [rbp+110h+var_190]
0x18013e24e  mov     rax, [rcx]
0x18013e251  lea     rdx, [rbp+110h+instance]
0x18013e255  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18013e25a  mov     r9, r13
0x18013e25d  mov     r8, rdi
0x18013e260  mov     edx, 100005h
0x18013e265  mov     rax, [rax+30h]
0x18013e269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e26e  mov     ebx, eax
0x18013e270  test    eax, eax
0x18013e272  jz      short loc_18013E2B9
0x18013e274  mov     eax, cs:dword_180397B68
0x18013e27a  cmp     eax, 2
0x18013e27d  jbe     loc_18013E316
0x18013e283  mov     dword ptr [rbp+110h+var_158], ebx
0x18013e286  mov     dword ptr [rbp+110h+var_180], 272h
0x18013e28d  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e294  mov     [rsp+210h+var_1A0], rax
0x18013e299  lea     rax, [rbp+110h+var_158]
0x18013e29d  mov     [rsp+210h+var_1E0], rax
0x18013e2a2  lea     rax, [rbp+110h+var_180]
0x18013e2a6  mov     [rsp+210h+var_1E8], rax
0x18013e2ab  lea     rax, [rsp+210h+var_1A0]
0x18013e2b0  lea     rdx, word_18034BD9A
0x18013e2b7  jmp     short loc_18013E30C
0x18013e2b9  lea     rdx, [rbp+110h+instance]
0x18013e2bd  mov     rcx, rdi; self
0x18013e2c0  call    MI_Instance_Destruct
0x18013e2c5  mov     ebx, eax
0x18013e2c7  test    eax, eax
0x18013e2c9  jz      short loc_18013E316
0x18013e2cb  mov     eax, cs:dword_180397B68
0x18013e2d1  cmp     eax, 2
0x18013e2d4  jbe     short loc_18013E316
0x18013e2d6  mov     [rsp+210h+var_198], ebx
0x18013e2da  mov     dword ptr [rsp+210h+var_1A0], 27Ah
0x18013e2e2  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e2e9  mov     [rbp+110h+var_180], rax
0x18013e2ed  lea     rax, [rsp+210h+var_198]
0x18013e2f2  mov     [rsp+210h+var_1E0], rax
0x18013e2f7  lea     rax, [rsp+210h+var_1A0]
0x18013e2fc  mov     [rsp+210h+var_1E8], rax
0x18013e301  lea     rax, [rbp+110h+var_180]
0x18013e305  lea     rdx, byte_18034B32D
0x18013e30c  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013e311  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013e316  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013e31d  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013e322  xor     r13d, r13d
0x18013e325  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18013e32a  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18013e32e  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18013e332  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18013e336  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18013e33a  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18013e33e  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013e343  test    r12d, r12d
0x18013e346  jnz     loc_18013E44E
0x18013e34c  lea     rcx, [rbp+110h+var_148]; this
0x18013e350  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013e355  mov     eax, cs:dword_180397B68
0x18013e35b  cmp     eax, 5
0x18013e35e  jbe     loc_18013E44E
0x18013e364  mov     rdx, 400000000000h
0x18013e36e  lea     rcx, dword_180397B68
0x18013e375  call    _tlgKeywordOn
0x18013e37a  test    al, al
0x18013e37c  jz      loc_18013E44E
0x18013e382  mov     [rbp+110h+var_178], r13
0x18013e386  mov     [rbp+110h+var_150], r13
0x18013e38a  mov     [rbp+110h+var_158], r13
0x18013e38e  mov     rax, [rbp+110h+var_140]
0x18013e392  sub     rax, [rbp+110h+var_148]
0x18013e396  imul    rax, 3E8h
0x18013e39d  xor     edx, edx
0x18013e39f  div     [rbp+110h+var_138]
0x18013e3a3  mov     [rbp+110h+var_160], rax
0x18013e3a7  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18013e3ab  mov     al, [rbp+110h+var_A0.exists]
0x18013e3ae  neg     al
0x18013e3b0  sbb     ecx, ecx
0x18013e3b2  and     ecx, [rbp+110h+var_A0.value]
0x18013e3b5  mov     [rsp+210h+var_198], ecx
0x18013e3b9  mov     dword ptr [rbp+110h+var_180], r15d
0x18013e3bd  cmp     [r14+48h], r13b
0x18013e3c1  jz      short loc_18013E3C9
0x18013e3c3  mov     rax, [r14+40h]
0x18013e3c7  jmp     short loc_18013E3CC
0x18013e3c9  mov     rax, r13
0x18013e3cc  mov     [rbp+110h+var_168], rax
0x18013e3d0  lea     rax, aSetsecuritydes_0; "SetSecurityDescriptor"
0x18013e3d7  mov     [rbp+110h+var_170], rax
0x18013e3db  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013e3e2  mov     [rbp+110h+var_188], rax
0x18013e3e6  lea     rax, [rbp+110h+var_178]
0x18013e3ea  mov     [rsp+210h+var_1A8], rax
0x18013e3ef  lea     rax, [rbp+110h+var_150]
0x18013e3f3  mov     [rsp+210h+var_1B0], rax
0x18013e3f8  lea     rax, [rbp+110h+var_158]
0x18013e3fc  mov     [rsp+210h+var_1B8], rax
0x18013e401  lea     rax, [rbp+110h+var_160]
0x18013e405  mov     [rsp+210h+var_1C0], rax
0x18013e40a  lea     rax, [rsp+210h+var_1A0]
0x18013e40f  mov     [rsp+210h+var_1C8], rax
0x18013e414  lea     rax, [rsp+210h+var_198]
0x18013e419  mov     [rsp+210h+var_1D0], rax
0x18013e41e  lea     rax, [rbp+110h+var_180]
0x18013e422  mov     [rsp+210h+var_1D8], rax
0x18013e427  lea     rax, [rbp+110h+var_168]
0x18013e42b  mov     [rsp+210h+var_1E0], rax
0x18013e430  lea     rax, [rbp+110h+var_170]
0x18013e434  mov     [rsp+210h+var_1E8], rax
0x18013e439  lea     rax, [rbp+110h+var_188]
0x18013e43d  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013e442  lea     rdx, word_18034C8E6
0x18013e449  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18013e44e  lea     rcx, [rbp+110h+instance]; self
0x18013e452  call    MI_Instance_Destruct
0x18013e457  mov     eax, cs:dword_180397B68
0x18013e45d  cmp     eax, 5
0x18013e460  jbe     short loc_18013E494
0x18013e462  mov     dword ptr [rsp+210h+var_1A0], 29Bh
0x18013e46a  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18013e471  mov     [rbp+110h+var_178], rax
0x18013e475  lea     rax, [rsp+210h+var_1A0]
0x18013e47a  mov     [rsp+210h+var_1E8], rax
0x18013e47f  lea     rax, [rbp+110h+var_178]
0x18013e483  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013e488  lea     rdx, dword_18034B434
0x18013e48f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013e494  test    rdi, rdi
0x18013e497  jz      short loc_18013E4AE
0x18013e499  mov     rax, [rdi]
0x18013e49c  test    rax, rax
0x18013e49f  jz      short loc_18013E4AE
0x18013e4a1  mov     edx, ebx
0x18013e4a3  mov     rcx, rdi
0x18013e4a6  mov     rax, [rax]
0x18013e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e4ae  lea     rcx, [rbp+110h+var_148]; this
0x18013e4b2  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18013e4b7  lea     rcx, [rbp+110h+var_190]
0x18013e4bb  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013e4c0  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013e4c7  mov     ecx, 4; ControlCode
0x18013e4cc  call    cs:__imp_EventActivityIdControl
0x18013e4d2  mov     rcx, [rbp+110h+var_40]
0x18013e4d9  xor     rcx, rsp; StackCookie
0x18013e4dc  call    __security_check_cookie
0x18013e4e1  mov     rbx, [rsp+210h+arg_10]
0x18013e4e9  add     rsp, 1E0h
0x18013e4f0  pop     r15
0x18013e4f2  pop     r14
  ... truncated ...
```
