# SPACES_StoragePool_Invoke_CreateStorageTier3

- ea: `0x180155ca0`
- end: `0x1801562ba`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier3`
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
- `0x180155ca0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155d1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155d7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015628a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155d1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155d7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015628a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155d40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155d40`

## string_xrefs

- `0x180156192`: `CreateStorageTier`
- `0x180155d88`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x180155ec3`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x180155ffb`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x18015602a`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x18015603f`: `SPACES_StoragePool_Invoke_CreateStorageTier3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateStorageTier3(
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
  struct _MI_Instance *v55; // [rsp+260h] [rbp+160h]
  char v56; // [rsp+268h] [rbp+168h]
  struct _MI_Instance *v57; // [rsp+270h] [rbp+170h]
  char v58; // [rsp+278h] [rbp+178h]
  GUID ActivityId; // [rsp+290h] [rbp+190h] BYREF
  GUID v60; // [rsp+2A0h] [rbp+1A0h]
  GUID v61; // [rsp+2B0h] [rbp+1B0h] BYREF

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
    v36 = 948;
    v35 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateStorageTier3",
      (unsigned int)&dword_180356C8C,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x108u);
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
        v41 = 980;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = &byte_180355EAF;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
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
      if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) < 3 )
      {
        v15 = MI_RESULT_NOT_SUPPORTED;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        LODWORD(v42) = 7;
        LODWORD(v43) = 991;
        v34 = &v42;
        v20 = &v43;
        v21 = byte_180354A05;
        goto LABEL_13;
      }
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier3_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        LODWORD(v44) = v15;
        LODWORD(v45) = 999;
        v34 = (const char **)&v44;
        v20 = (const char **)&v45;
        v21 = (char *)&dword_1803566E4;
        goto LABEL_13;
      }
      v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
              v38,
              720920,
              a2,
              a7,
              &instance);
      if ( v15 == MI_RESULT_OK )
      {
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_180397B68 > 2 )
        {
          v37 = v15;
          LODWORD(v35) = 1018;
          v39 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&word_180356EDE,
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
        LODWORD(v39) = 1010;
        v34 = &v46;
        v20 = &v39;
        v21 = byte_180354C61;
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
        v46 = "StorageTier";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateStorageTier";
        v42 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)&word_180355736,
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
    LODWORD(v35) = 1051;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&dword_180356FAC,
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
0x180155ca0  mov     [rsp-8+arg_10], rbx
0x180155ca5  push    rbp
0x180155ca6  push    rsi
0x180155ca7  push    rdi
0x180155ca8  push    r12
0x180155caa  push    r13
0x180155cac  push    r14
0x180155cae  push    r15
0x180155cb0  lea     rbp, [rsp-1D0h]
0x180155cb8  sub     rsp, 2D0h
0x180155cbf  mov     rax, cs:__security_cookie
0x180155cc6  xor     rax, rsp
0x180155cc9  mov     [rbp+200h+var_40], rax
0x180155cd0  mov     [rbp+200h+var_270], r9
0x180155cd4  mov     rdi, rdx
0x180155cd7  mov     r14, rcx
0x180155cda  mov     rax, [rbp+200h+arg_20]
0x180155ce1  mov     [rbp+200h+var_238], rax
0x180155ce5  mov     rsi, [rbp+200h+arg_28]
0x180155cec  mov     r13, [rbp+200h+arg_30]
0x180155cf3  xorps   xmm0, xmm0
0x180155cf6  xor     eax, eax
0x180155cf8  movups  xmmword ptr [rbp+200h+value], xmm0
0x180155cfc  movups  xmmword ptr [rbp+200h+value+10h], xmm0
0x180155d00  mov     qword ptr [rbp+200h+value+20h], rax
0x180155d04  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180155d0b  movdqu  xmmword ptr [rbp+200h+ActivityId.Data1], xmm0
0x180155d13  lea     rdx, [rbp+200h+ActivityId]; ActivityId
0x180155d1a  lea     ecx, [rax+1]; ControlCode
0x180155d1d  call    cs:__imp_EventActivityIdControl
0x180155d23  lea     r9, [rbp+200h+value]; value
0x180155d27  mov     rcx, rdi; context
0x180155d2a  call    MI_Context_GetCustomOption_1
0x180155d2f  xor     ebx, ebx
0x180155d31  test    eax, eax
0x180155d33  jnz     short loc_180155D46
0x180155d35  lea     rdx, [rbp+200h+ActivityId]; pclsid
0x180155d3c  mov     rcx, qword ptr [rbp+200h+value]; lpsz
0x180155d40  call    cs:__imp_CLSIDFromString
0x180155d46  mov     rcx, qword ptr [rbp+200h+ActivityId.Data1]
0x180155d4d  mov     [rbp+200h+var_60], rcx
0x180155d54  mov     rax, qword ptr [rbp+200h+ActivityId.Data4]
0x180155d5b  mov     [rbp+200h+var_58], rax
0x180155d62  mov     qword ptr [rbp+200h+var_50.Data1], rcx
0x180155d69  mov     qword ptr [rbp+200h+var_50.Data4], rax
0x180155d70  lea     rdx, [rbp+200h+var_50]; ActivityId
0x180155d77  mov     ecx, 4; ControlCode
0x180155d7c  call    cs:__imp_EventActivityIdControl
0x180155d82  mov     eax, cs:dword_180397B68
0x180155d88  lea     rcx, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180155d8f  cmp     eax, 5
0x180155d92  jbe     short loc_180155DC1
0x180155d94  mov     [rsp+300h+var_288], 3B4h
0x180155d9c  mov     [rsp+300h+var_290], rcx
0x180155da1  lea     rax, [rsp+300h+var_288]
0x180155da6  mov     [rsp+300h+var_2D8], rax
0x180155dab  lea     rax, [rsp+300h+var_290]
0x180155db0  mov     qword ptr [rsp+300h+var_2E0], rax
0x180155db5  lea     rdx, dword_180356C8C
0x180155dbc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180155dc1  mov     [rbp+200h+instance.ft], rbx
0x180155dc8  xor     edx, edx; Val
0x180155dca  mov     r8d, 108h; Size
0x180155dd0  lea     rcx, [rbp+200h+instance.classDecl]; void *
0x180155dd7  call    memset_0
0x180155ddc  xorps   xmm0, xmm0
0x180155ddf  xor     eax, eax
0x180155de1  movups  [rbp+200h+var_210], xmm0
0x180155de5  mov     [rbp+200h+var_200], rax
0x180155de9  mov     [rbp+200h+var_280], rbx
0x180155ded  lea     rcx, [rbp+200h+var_280]
0x180155df1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180155df6  mov     [rbp+200h+var_280], rbx
0x180155dfa  mov     r15d, ebx
0x180155dfd  lea     rcx, [rbp+200h+var_230]; this
0x180155e01  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180155e06  mov     rcx, rdi; context
0x180155e09  call    WspIsRemoteRequest
0x180155e0e  mov     r12d, eax
0x180155e11  test    eax, eax
0x180155e13  jnz     short loc_180155E38
0x180155e15  lea     rcx, [rbp+200h+var_230]; this
0x180155e19  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180155e1e  cmp     [rsi+48h], bl
0x180155e21  jz      short loc_180155E35
0x180155e23  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180155e27  call    WspIsRemoteInstance
0x180155e2c  test    al, al
0x180155e2e  lea     r15d, [r12+1]
0x180155e33  jnz     short loc_180155E38
0x180155e35  mov     r15d, ebx
0x180155e38  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180155e3f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180155e44  mov     ebx, eax
0x180155e46  test    eax, eax
0x180155e48  jnz     loc_18015603F
0x180155e4e  mov     dword ptr [rbp+200h+var_210], 0Bh
0x180155e55  mov     rax, [rsi+40h]
0x180155e59  mov     qword ptr [rbp+200h+var_210+8], rax
0x180155e5d  mov     rbx, [r14]
0x180155e60  lea     rcx, [rbp+200h+var_280]
0x180155e64  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180155e69  mov     [rsp+300h+var_2E0], 1; int
0x180155e71  lea     r9, [rbp+200h+var_280]; struct ISpWmiObject **
0x180155e75  lea     r8, [rbp+200h+var_210]; struct _SP_OBJECT_ID *
0x180155e79  mov     rdx, rdi; context
0x180155e7c  mov     rcx, rbx; this
0x180155e7f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180155e84  mov     ebx, eax
0x180155e86  test    eax, eax
0x180155e88  jz      short loc_180155EDE
0x180155e8a  mov     eax, cs:dword_180397B68
0x180155e90  cmp     eax, 2
0x180155e93  jbe     loc_18015602A
0x180155e99  mov     [rsp+300h+var_288], ebx
0x180155e9d  mov     [rbp+200h+var_268], 3D4h
0x180155ea4  lea     rax, [rsp+300h+var_288]
0x180155ea9  mov     [rsp+300h+var_2D0], rax
0x180155eae  lea     rax, [rbp+200h+var_268]
0x180155eb2  lea     rdx, byte_180355EAF
0x180155eb9  mov     [rsp+300h+var_2D8], rax
0x180155ebe  lea     rax, [rsp+300h+var_290]
0x180155ec3  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180155eca  mov     [rsp+300h+var_290], r13
0x180155ecf  mov     qword ptr [rsp+300h+var_2E0], rax
0x180155ed4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180155ed9  jmp     loc_180156031
0x180155ede  mov     r8, [rsi+40h]
0x180155ee2  mov     rdx, rdi
0x180155ee5  mov     rcx, [r14]
0x180155ee8  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180155eed  cmp     eax, 3
0x180155ef0  jnb     short loc_180155F26
0x180155ef2  mov     ebx, 7
0x180155ef7  mov     eax, cs:dword_180397B68
0x180155efd  cmp     eax, 2
0x180155f00  jbe     loc_18015602A
0x180155f06  mov     dword ptr [rbp+200h+var_260], ebx
0x180155f09  mov     dword ptr [rbp+200h+var_258], 3DFh
0x180155f10  lea     rax, [rbp+200h+var_260]
0x180155f14  mov     [rsp+300h+var_2D0], rax
0x180155f19  lea     rax, [rbp+200h+var_258]
0x180155f1d  lea     rdx, byte_180354A05
0x180155f24  jmp     short loc_180155EB9
0x180155f26  lea     r8, [rbp+200h+instance]; instance
0x180155f2d  lea     rdx, SPACES_StoragePool_CreateStorageTier3_rtti; methodDecl
0x180155f34  mov     rcx, rdi; context
0x180155f37  call    MI_Context_ConstructParameters
0x180155f3c  mov     ebx, eax
0x180155f3e  test    eax, eax
0x180155f40  jz      short loc_180155F74
0x180155f42  mov     eax, cs:dword_180397B68
0x180155f48  cmp     eax, 2
0x180155f4b  jbe     loc_18015602A
0x180155f51  mov     dword ptr [rbp+200h+var_250], ebx
0x180155f54  mov     dword ptr [rbp+200h+var_248], 3E7h
0x180155f5b  lea     rax, [rbp+200h+var_250]
0x180155f5f  mov     [rsp+300h+var_2D0], rax
0x180155f64  lea     rax, [rbp+200h+var_248]
0x180155f68  lea     rdx, dword_1803566E4
0x180155f6f  jmp     loc_180155EB9
0x180155f74  mov     rcx, [rbp+200h+var_280]
0x180155f78  mov     rax, [rcx]
0x180155f7b  lea     rdx, [rbp+200h+instance]
0x180155f82  mov     qword ptr [rsp+300h+var_2E0], rdx
0x180155f87  mov     r9, r13
0x180155f8a  mov     r8, rdi
0x180155f8d  mov     edx, 0B0018h
0x180155f92  mov     rax, [rax+30h]
0x180155f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155f9b  mov     ebx, eax
0x180155f9d  test    eax, eax
0x180155f9f  jz      short loc_180155FCF
0x180155fa1  mov     eax, cs:dword_180397B68
0x180155fa7  cmp     eax, 2
0x180155faa  jbe     short loc_18015602A
0x180155fac  mov     dword ptr [rbp+200h+var_240], ebx
0x180155faf  mov     dword ptr [rbp+200h+var_278], 3F2h
0x180155fb6  lea     rax, [rbp+200h+var_240]
0x180155fba  mov     [rsp+300h+var_2D0], rax
0x180155fbf  lea     rax, [rbp+200h+var_278]
0x180155fc3  lea     rdx, byte_180354C61
0x180155fca  jmp     loc_180155EB9
0x180155fcf  lea     rdx, [rbp+200h+instance]
0x180155fd6  mov     rcx, rdi; self
0x180155fd9  call    MI_Instance_Destruct
0x180155fde  mov     ebx, eax
0x180155fe0  test    eax, eax
0x180155fe2  jz      short loc_18015602A
0x180155fe4  mov     eax, cs:dword_180397B68
0x180155fea  cmp     eax, 2
0x180155fed  jbe     short loc_18015602A
0x180155fef  mov     [rsp+300h+var_284], ebx
0x180155ff3  mov     dword ptr [rsp+300h+var_290], 3FAh
0x180155ffb  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180156002  mov     [rbp+200h+var_278], r13
0x180156006  lea     rax, [rsp+300h+var_284]
0x18015600b  mov     [rsp+300h+var_2D0], rax
0x180156010  lea     rax, [rsp+300h+var_290]
0x180156015  mov     [rsp+300h+var_2D8], rax
0x18015601a  lea     rax, [rbp+200h+var_278]
0x18015601e  lea     rdx, word_180356EDE
0x180156025  jmp     loc_180155ECF
0x18015602a  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180156031  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180156038  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015603d  jmp     short loc_180156046
0x18015603f  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180156046  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18015604a  xor     r14d, r14d
0x18015604d  mov     [rsp+300h+var_2D8], r14; unsigned __int16 *
0x180156052  mov     [rsp+300h+var_2E0], ebx; enum _MI_Result
0x180156056  lea     r9, [rbp+200h+var_140]; struct _MI_ConstUint32Field *
0x18015605d  mov     rdx, [rbp+200h+var_238]; unsigned __int16 *
0x180156061  mov     rcx, [rbp+200h+var_270]; unsigned __int16 *
0x180156065  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015606a  test    r12d, r12d
0x18015606d  jnz     loc_180156210
0x180156073  lea     rcx, [rbp+200h+var_230]; this
0x180156077  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015607c  mov     eax, cs:dword_180397B68
0x180156082  cmp     eax, 5
0x180156085  jbe     loc_180156210
0x18015608b  mov     rdx, 400000000000h
0x180156095  lea     rcx, dword_180397B68
0x18015609c  call    _tlgKeywordOn
0x1801560a1  test    al, al
0x1801560a3  jz      loc_180156210
0x1801560a9  cmp     [rbp+200h+var_88], r14b
0x1801560b0  jz      short loc_1801560ED
0x1801560b2  mov     rax, [rbp+200h+var_90]
0x1801560b9  movups  xmm0, xmmword ptr [rax]
0x1801560bc  movaps  xmmword ptr [rbp+200h+var_1F0.ft], xmm0
0x1801560c0  movups  xmm1, xmmword ptr [rax+10h]
0x1801560c4  movaps  xmmword ptr [rbp+200h+var_1F0.serverName], xmm1
0x1801560c8  movups  xmm0, xmmword ptr [rax+20h]
0x1801560cc  movaps  xmmword ptr [rbp+200h+var_1F0.reserved], xmm0
0x1801560d0  movups  xmm1, xmmword ptr [rax+30h]
0x1801560d4  movaps  xmmword ptr [rbp+200h+var_1F0.reserved+10h], xmm1
0x1801560d8  xor     r8d, r8d; unsigned __int16 *
0x1801560db  lea     rdx, [rbp+200h+var_1F0]; struct _MI_Instance
0x1801560df  lea     rcx, name; "ObjectId"
0x1801560e6  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801560eb  jmp     short loc_1801560F0
0x1801560ed  mov     rax, r14
0x1801560f0  mov     [rbp+200h+var_270], rax
0x1801560f4  cmp     [rbp+200h+var_98], r14b
0x1801560fb  jz      short loc_180156138
0x1801560fd  mov     rax, [rbp+200h+var_A0]
0x180156104  movups  xmm0, xmmword ptr [rax]
0x180156107  movaps  xmmword ptr [rbp+200h+var_1F0.ft], xmm0
0x18015610b  movups  xmm1, xmmword ptr [rax+10h]
0x18015610f  movaps  xmmword ptr [rbp+200h+var_1F0.serverName], xmm1
0x180156113  movups  xmm0, xmmword ptr [rax+20h]
0x180156117  movaps  xmmword ptr [rbp+200h+var_1F0.reserved], xmm0
0x18015611b  movups  xmm1, xmmword ptr [rax+30h]
0x18015611f  movaps  xmmword ptr [rbp+200h+var_1F0.reserved+10h], xmm1
0x180156123  xor     r8d, r8d; unsigned __int16 *
0x180156126  lea     rdx, [rbp+200h+var_1F0]; struct _MI_Instance
0x18015612a  lea     rcx, name; "ObjectId"
0x180156131  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180156136  jmp     short loc_18015613B
0x180156138  mov     rax, r14
0x18015613b  mov     [rbp+200h+var_238], rax
0x18015613f  lea     rax, aStoragetier; "StorageTier"
0x180156146  mov     [rbp+200h+var_240], rax
0x18015614a  mov     rax, [rbp+200h+var_228]
0x18015614e  sub     rax, [rbp+200h+var_230]
0x180156152  imul    rax, 3E8h
0x180156159  xor     edx, edx
0x18015615b  div     [rbp+200h+var_220]
0x18015615f  mov     [rbp+200h+var_248], rax
0x180156163  mov     dword ptr [rsp+300h+var_290], ebx
0x180156167  mov     al, [rbp+200h+var_140.exists]
0x18015616d  neg     al
0x18015616f  sbb     ecx, ecx
0x180156171  and     ecx, [rbp+200h+var_140.value]
0x180156177  mov     [rsp+300h+var_284], ecx
0x18015617b  mov     dword ptr [rbp+200h+var_278], r15d
0x18015617f  cmp     [rsi+48h], r14b
0x180156183  jz      short loc_18015618B
0x180156185  mov     rax, [rsi+40h]
0x180156189  jmp     short loc_18015618E
0x18015618b  mov     rax, r14
0x18015618e  mov     [rbp+200h+var_250], rax
0x180156192  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x180156199  mov     [rbp+200h+var_258], rax
0x18015619d  lea     rax, aStoragepool_0; "StoragePool"
0x1801561a4  mov     [rbp+200h+var_260], rax
0x1801561a8  lea     rax, [rbp+200h+var_270]
0x1801561ac  mov     [rsp+300h+var_298], rax
0x1801561b1  lea     rax, [rbp+200h+var_238]
0x1801561b5  mov     [rsp+300h+var_2A0], rax
0x1801561ba  lea     rax, [rbp+200h+var_240]
0x1801561be  mov     [rsp+300h+var_2A8], rax
0x1801561c3  lea     rax, [rbp+200h+var_248]
0x1801561c7  mov     [rsp+300h+var_2B0], rax
0x1801561cc  lea     rax, [rsp+300h+var_290]
0x1801561d1  mov     [rsp+300h+var_2B8], rax
0x1801561d6  lea     rax, [rsp+300h+var_284]
  ... truncated ...
```
