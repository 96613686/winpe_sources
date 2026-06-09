# WSP_Partition_Invoke_DeleteObject

- ea: `0x180164ce0`
- end: `0x180165320`
- name: `WSP_Partition_Invoke_DeleteObject`
- size: `1600`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001970`
- `0x1800045d0`
- `0x180004bfc`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd18`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180014000`
- `0x180014720`
- `0x180015500`
- `0x1800156c0`
- `0x1800158d0`
- `0x180015b40`
- `0x180015c60`
- `0x180016480`
- `0x1800165f0`
- `0x180016c80`
- `0x18001afd0`
- `0x1800234e4`
- `0x180115e70`
- `0x180126860`
- `0x1801287b8`
- `0x180128cb8`
- `0x180137a24`
- `0x180138120`
- `0x180164ce0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164d53`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164daa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164f7b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164d53`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164daa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164f7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180164d74`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180164d74`

## string_xrefs

- `0x180164e8a`: `DeletePartition`
- `0x180165250`: `DeletePartition`
- `0x1801652d8`: `DeletePartition`
- `0x180164db6`: `WSP_Partition_Invoke_DeleteObject`
- `0x180164f34`: `WSP_Partition_Invoke_DeleteObject`
- `0x18016517c`: `WSP_Partition_Invoke_DeleteObject`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_DeleteObject(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        void *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r15d
  int v12; // r8d
  int v13; // r9d
  unsigned __int16 **v14; // rsi
  unsigned __int16 *v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  char IsRemoteInstance; // al
  unsigned __int16 *v23; // rcx
  unsigned int SubsystemType; // edi
  int SubsystemVersion; // r14d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  enum _MI_Result v29; // eax
  int v30; // r8d
  int v31; // r9d
  unsigned __int16 *v32; // r14
  enum _MI_Result v33; // edi
  int v34; // ecx
  int *v35; // rdx
  MI_Uint32 v36; // edi
  int v37; // r9d
  unsigned __int16 *v38; // rax
  unsigned __int32 v39; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v40; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-80h] BYREF
  const char *v44; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v46; // [rsp+98h] [rbp-68h] BYREF
  const char *v47; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v48; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v49; // [rsp+B0h] [rbp-50h] BYREF
  const char *v50; // [rsp+B8h] [rbp-48h] BYREF
  const char *v51; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v54; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+150h] [rbp+50h] BYREF
  GUID ActivityId; // [rsp+170h] [rbp+70h] BYREF
  __int128 v59; // [rsp+180h] [rbp+80h] BYREF
  int v60; // [rsp+190h] [rbp+90h]
  GUID v61; // [rsp+198h] [rbp+98h]
  GUID v62; // [rsp+1A8h] [rbp+A8h] BYREF

  memset(&value, 0, sizeof(value));
  v49 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v61 = ActivityId;
  v62 = ActivityId;
  EventActivityIdControl(4u, &v62);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v43 = 624;
    v46 = (unsigned __int16 *)"WSP_Partition_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_DeleteObject",
      (unsigned int)byte_180359F83,
      v12,
      v13,
      (__int64)&v46,
      (__int64)&v43);
  }
  v46 = 0;
  v48 = 0;
  v42 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x50u);
  CSmTimer::CSmTimer((CSmTimer *)&v52);
  CSmTimer::Start((CSmTimer *)&v52);
  v14 = (unsigned __int16 **)&a6[4];
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance(*v14) )
    v11 = 1;
  v15 = *v14;
  v43 = 0;
  v16 = WspProviderEnter(a2, (__int64)v15, 1u, &v43);
  v17 = v16;
  if ( v16 )
    goto LABEL_9;
  IsRemoteInstance = WspIsRemoteInstance(*v14);
  v23 = *v14;
  if ( IsRemoteInstance )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *v14, a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v17);
    goto LABEL_12;
  }
  v59 = 0;
  v60 = 0;
  LODWORD(v45) = 0;
  SubsystemType = WspGetSubsystemType(v23);
  SubsystemVersion = _GetSubsystemVersion(&v45);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v59);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v39 = SubsystemType;
    v40 = SubsystemVersion != v45;
    LOWORD(v45) = v60;
    v44 = (const char *)&v59;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v26,
      (unsigned int)word_18035A7A2,
      v27,
      v28,
      (__int64)&v44,
      (__int64)&v39,
      (__int64)&v45,
      (__int64)&v40);
  }
  v29 = (unsigned int)WspUnpackObjectId(*v14);
  v32 = v46;
  v33 = v29;
  if ( v29 )
  {
    v34 = dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_40;
    v39 = v29;
    v35 = &dword_18035A8A4;
    v40 = 654;
  }
  else
  {
    v33 = MI_Context_ConstructParameters(a2, &WSP_Partition_DeleteObject_rtti, &instance);
    if ( v33 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_40;
      v40 = 662;
      v35 = (int *)&unk_18035A298;
    }
    else
    {
      if ( v42 )
      {
        v36 = PmcDeletePartition(v32);
        if ( !v36 && (unsigned int)PmUnpackPartitionKey(v32, &v48, 0) )
          PmcRefreshDisk(v48);
      }
      else
      {
        v36 = PmDeletePartition(v32);
      }
      v57.value = v36;
      v57.exists = 1;
      v33 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v33 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_40;
      v40 = 698;
      v35 = (int *)byte_180359E89;
    }
    v39 = v33;
  }
  v44 = "WSP_Partition_Invoke_DeleteObject";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v34,
    (_DWORD)v35,
    v30,
    v31,
    (__int64)&v44,
    (__int64)&v40,
    (__int64)&v39);
LABEL_40:
  SmLogOnMethodFailure(a4, v49, a6 + 4, &v57, v33, 0);
  CSmTimer::Stop((CSmTimer *)&v52);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v49 = 0;
    v44 = 0;
    v45 = 1000 * (v53 - v52) / v54;
    v46 = 0;
    v39 = v33;
    v42 = v11;
    v40 = v57.exists != 0 ? v57.value : 0;
    if ( a6[4].exists )
      v38 = *v14;
    else
      v38 = 0;
    v50 = (const char *)v38;
    v51 = "DeletePartition";
    v47 = "WspPartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v57.exists != 0 ? v57.value : 0,
      (unsigned int)byte_18035B001,
      0,
      v37,
      (__int64)&v47,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v42,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v49);
  }
  WspFreeString(v32);
  SmFreeString(&v48);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v33);
LABEL_12:
  WspProviderExit(v43, v17);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v52);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v51 = "DeletePartition";
        v47 = (const char *)(1000 * (v53 - v52) / v54);
        v50 = "WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v18,
          (unsigned int)&unk_18035AE40,
          v19,
          v20,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&IsRemoteRequest,
          (__int64)&v47);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 746;
    v47 = "WSP_Partition_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&dword_18035AAC4,
      v19,
      v20,
      (__int64)&v47,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v52);
  return EventActivityIdControl(4u, &v62);
}

```

## disassembly

```asm
0x180164ce0  mov     [rsp-8+arg_0], rbx
0x180164ce5  push    rbp
0x180164ce6  push    rsi
0x180164ce7  push    rdi
0x180164ce8  push    r12
0x180164cea  push    r13
0x180164cec  push    r14
0x180164cee  push    r15
0x180164cf0  lea     rbp, [rsp-0C0h]
0x180164cf8  sub     rsp, 1C0h
0x180164cff  mov     rax, cs:__security_cookie
0x180164d06  xor     rax, rsp
0x180164d09  mov     [rbp+0F0h+var_38], rax
0x180164d10  mov     r14, [rbp+0F0h+arg_20]
0x180164d17  xorps   xmm0, xmm0
0x180164d1a  mov     r13, [rbp+0F0h+arg_28]
0x180164d21  xor     eax, eax
0x180164d23  mov     rdi, [rbp+0F0h+arg_30]
0x180164d2a  mov     rbx, rdx
0x180164d2d  movups  xmmword ptr [rbp+0F0h+value], xmm0
0x180164d31  lea     rdx, [rbp+0F0h+ActivityId]; ActivityId
0x180164d35  mov     r12, r9
0x180164d38  movups  xmmword ptr [rbp+0F0h+value+10h], xmm0
0x180164d3c  lea     ecx, [rax+1]; ControlCode
0x180164d3f  mov     [rbp+0F0h+var_140], r14
0x180164d43  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180164d4a  mov     qword ptr [rbp+0F0h+value+20h], rax
0x180164d4e  movdqu  xmmword ptr [rbp+0F0h+ActivityId.Data1], xmm0
0x180164d53  call    cs:__imp_EventActivityIdControl
0x180164d59  lea     r9, [rbp+0F0h+value]; value
0x180164d5d  mov     rcx, rbx; context
0x180164d60  call    MI_Context_GetCustomOption_1
0x180164d65  xor     r15d, r15d
0x180164d68  test    eax, eax
0x180164d6a  jnz     short loc_180164D7A
0x180164d6c  mov     rcx, qword ptr [rbp+0F0h+value]; lpsz
0x180164d70  lea     rdx, [rbp+0F0h+ActivityId]; pclsid
0x180164d74  call    cs:__imp_CLSIDFromString
0x180164d7a  mov     rcx, qword ptr [rbp+0F0h+ActivityId.Data1]
0x180164d7e  lea     rdx, [rbp+0F0h+var_48]; ActivityId
0x180164d85  mov     rax, qword ptr [rbp+0F0h+ActivityId.Data4]
0x180164d89  mov     [rbp+0F0h+var_58], rcx
0x180164d90  mov     qword ptr [rbp+0F0h+var_48.Data1], rcx
0x180164d97  mov     ecx, 4; ControlCode
0x180164d9c  mov     [rbp+0F0h+var_50], rax
0x180164da3  mov     qword ptr [rbp+0F0h+var_48.Data4], rax
0x180164daa  call    cs:__imp_EventActivityIdControl
0x180164db0  mov     eax, cs:dword_180397B68
0x180164db6  lea     rcx, aWspPartitionIn_2; "WSP_Partition_Invoke_DeleteObject"
0x180164dbd  cmp     eax, 5
0x180164dc0  jbe     short loc_180164DEB
0x180164dc2  lea     rax, [rbp+0F0h+var_170]
0x180164dc6  mov     [rbp+0F0h+var_170], 270h
0x180164dcd  mov     [rsp+1F0h+var_1C8], rax
0x180164dd2  lea     rdx, byte_180359F83
0x180164dd9  lea     rax, [rbp+0F0h+var_158]
0x180164ddd  mov     [rbp+0F0h+var_158], rcx
0x180164de1  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180164de6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180164deb  xor     edx, edx; Val
0x180164ded  mov     [rbp+0F0h+var_158], r15
0x180164df1  lea     rcx, [rbp+0F0h+instance.classDecl]; void *
0x180164df5  mov     [rbp+0F0h+var_148], r15
0x180164df9  mov     [rsp+1F0h+var_174], r15d
0x180164dfe  mov     [rbp+0F0h+instance.ft], r15
0x180164e02  lea     r8d, [rdx+50h]; Size
0x180164e06  call    memset_0
0x180164e0b  lea     rcx, [rbp+0F0h+var_128]; this
0x180164e0f  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180164e14  lea     rcx, [rbp+0F0h+var_128]; this
0x180164e18  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180164e1d  mov     rcx, rbx; context
0x180164e20  call    WspIsRemoteRequest
0x180164e25  lea     rsi, [r13+40h]
0x180164e29  mov     [rsp+1F0h+var_178], eax
0x180164e2d  cmp     [rsi+8], r15b
0x180164e31  jz      short loc_180164E45
0x180164e33  mov     rcx, [rsi]; unsigned __int16 *
0x180164e36  call    WspIsRemoteInstance
0x180164e3b  test    al, al
0x180164e3d  jz      short loc_180164E45
0x180164e3f  mov     r15d, 1
0x180164e45  mov     rdx, [rsi]
0x180164e48  lea     r9, [rbp+0F0h+var_170]
0x180164e4c  mov     r8d, 1
0x180164e52  mov     [rbp+0F0h+var_170], 0
0x180164e59  mov     rcx, rbx; context
0x180164e5c  call    WspProviderEnter
0x180164e61  mov     edx, eax
0x180164e63  test    eax, eax
0x180164e65  jz      loc_180164FAB
0x180164e6b  test    rbx, rbx
0x180164e6e  jz      short loc_180164E83
0x180164e70  mov     rax, [rbx]
0x180164e73  test    rax, rax
0x180164e76  jz      short loc_180164E83
0x180164e78  mov     rax, [rax]
0x180164e7b  mov     rcx, rbx
0x180164e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164e83  lea     r12, aWsppartition; "WspPartition"
0x180164e8a  lea     rsi, aDeletepartitio; "DeletePartition"
0x180164e91  mov     ecx, [rbp+0F0h+var_170]
0x180164e94  call    WspProviderExit
0x180164e99  cmp     [rsp+1F0h+var_178], 0
0x180164e9e  jz      loc_180164F29
0x180164ea4  lea     rcx, [rbp+0F0h+var_128]; this
0x180164ea8  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180164ead  mov     eax, cs:dword_180397B68
0x180164eb3  cmp     eax, 5
0x180164eb6  jbe     short loc_180164F29
0x180164eb8  mov     rdx, 400000000000h
0x180164ec2  lea     rcx, dword_180397B68
0x180164ec9  call    _tlgKeywordOn
0x180164ece  test    al, al
0x180164ed0  jz      short loc_180164F29
0x180164ed2  mov     rax, [rbp+0F0h+var_120]
0x180164ed6  xor     edx, edx
0x180164ed8  sub     rax, [rbp+0F0h+var_128]
0x180164edc  imul    rax, 3E8h
0x180164ee3  mov     [rsp+1F0h+var_178], r15d
0x180164ee8  div     [rbp+0F0h+var_118]
0x180164eec  lea     rdx, unk_18035AE40
0x180164ef3  mov     [rbp+0F0h+var_130], rsi
0x180164ef7  mov     [rbp+0F0h+var_150], rax
0x180164efb  lea     rax, [rbp+0F0h+var_150]
0x180164eff  mov     [rsp+1F0h+var_1B8], rax
0x180164f04  lea     rax, [rsp+1F0h+var_178]
0x180164f09  mov     [rsp+1F0h+var_1C0], rax
0x180164f0e  lea     rax, [rbp+0F0h+var_130]
0x180164f12  mov     [rsp+1F0h+var_1C8], rax
0x180164f17  lea     rax, [rbp+0F0h+var_138]
0x180164f1b  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180164f20  mov     [rbp+0F0h+var_138], r12
0x180164f24  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180164f29  mov     eax, cs:dword_180397B68
0x180164f2f  cmp     eax, 5
0x180164f32  jbe     short loc_180164F66
0x180164f34  lea     rax, aWspPartitionIn_2; "WSP_Partition_Invoke_DeleteObject"
0x180164f3b  mov     [rsp+1F0h+var_178], 2EAh
0x180164f43  mov     [rbp+0F0h+var_150], rax
0x180164f47  lea     rdx, dword_18035AAC4
0x180164f4e  lea     rax, [rsp+1F0h+var_178]
0x180164f53  mov     [rsp+1F0h+var_1C8], rax
0x180164f58  lea     rax, [rbp+0F0h+var_150]
0x180164f5c  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180164f61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180164f66  lea     rcx, [rbp+0F0h+var_128]; this
0x180164f6a  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180164f6f  lea     rdx, [rbp+0F0h+var_48]; ActivityId
0x180164f76  mov     ecx, 4; ControlCode
0x180164f7b  call    cs:__imp_EventActivityIdControl
0x180164f81  mov     rcx, [rbp+0F0h+var_38]
0x180164f88  xor     rcx, rsp; StackCookie
0x180164f8b  call    __security_check_cookie
0x180164f90  mov     rbx, [rsp+1F0h+arg_0]
0x180164f98  add     rsp, 1C0h
0x180164f9f  pop     r15
0x180164fa1  pop     r14
0x180164fa3  pop     r13
0x180164fa5  pop     r12
0x180164fa7  pop     rdi
0x180164fa8  pop     rsi
0x180164fa9  pop     rbp
0x180164faa  retn
0x180164fab  mov     rcx, [rsi]; unsigned __int16 *
0x180164fae  call    WspIsRemoteInstance
0x180164fb3  mov     rcx, [rsi]
0x180164fb6  test    al, al
0x180164fb8  jz      short loc_180164FD7
0x180164fba  mov     r8, rcx; unsigned __int16 *
0x180164fbd  mov     qword ptr [rsp+1F0h+var_1D0], rdi; void *
0x180164fc2  mov     rcx, rbx; struct _MI_Context *
0x180164fc5  mov     r9, r14; unsigned __int16 *
0x180164fc8  mov     rdx, r12; unsigned __int16 *
0x180164fcb  call    WspInvokeRemoteMethod
0x180164fd0  mov     edx, eax
0x180164fd2  jmp     loc_180164E6B
0x180164fd7  xor     eax, eax
0x180164fd9  xorps   xmm0, xmm0
0x180164fdc  movups  [rbp+0F0h+var_70], xmm0
0x180164fe3  mov     [rbp+0F0h+var_60], eax
0x180164fe9  mov     dword ptr [rbp+0F0h+var_160], eax
0x180164fec  call    WspGetSubsystemType
0x180164ff1  lea     rcx, [rbp+0F0h+var_160]
0x180164ff5  mov     edi, eax
0x180164ff7  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180164ffc  lea     rdx, [rbp+0F0h+var_70]; struct _SUBSYSTEM_INFO *
0x180165003  mov     ecx, edi; unsigned int
0x180165005  mov     r14d, eax
0x180165008  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18016500d  mov     ecx, cs:dword_180397B68
0x180165013  cmp     ecx, 5
0x180165016  jbe     short loc_18016508B
0x180165018  mov     rdx, 400000000000h
0x180165022  lea     rcx, dword_180397B68
0x180165029  call    _tlgKeywordOn
0x18016502e  test    al, al
0x180165030  jz      short loc_18016508B
0x180165032  xor     eax, eax
0x180165034  mov     [rsp+1F0h+var_180], edi
0x180165038  cmp     r14d, dword ptr [rbp+0F0h+var_160]
0x18016503c  lea     rdx, word_18035A7A2
0x180165043  setnz   al
0x180165046  mov     [rsp+1F0h+var_17C], eax
0x18016504a  movzx   eax, word ptr [rbp+0F0h+var_60]
0x180165051  mov     word ptr [rbp+0F0h+var_160], ax
0x180165055  lea     rax, [rbp+0F0h+var_70]
0x18016505c  mov     [rbp+0F0h+var_168], rax
0x180165060  lea     rax, [rsp+1F0h+var_17C]
0x180165065  mov     [rsp+1F0h+var_1B8], rax
0x18016506a  lea     rax, [rbp+0F0h+var_160]
0x18016506e  mov     [rsp+1F0h+var_1C0], rax
0x180165073  lea     rax, [rsp+1F0h+var_180]
0x180165078  mov     [rsp+1F0h+var_1C8], rax
0x18016507d  lea     rax, [rbp+0F0h+var_168]
0x180165081  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180165086  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18016508b  mov     rcx, [rsi]; unsigned __int16 *
0x18016508e  lea     r9, [rbp+0F0h+var_158]
0x180165092  lea     r8, [rsp+1F0h+var_180]
0x180165097  lea     rdx, [rsp+1F0h+var_174]
0x18016509c  call    WspUnpackObjectId
0x1801650a1  mov     r14, [rbp+0F0h+var_158]
0x1801650a5  mov     edi, eax
0x1801650a7  test    eax, eax
0x1801650a9  jz      short loc_1801650D2
0x1801650ab  mov     ecx, cs:dword_180397B68
0x1801650b1  cmp     ecx, 2
0x1801650b4  jbe     loc_1801651A9
0x1801650ba  mov     [rsp+1F0h+var_180], eax
0x1801650be  lea     rdx, dword_18035A8A4
0x1801650c5  mov     [rsp+1F0h+var_17C], 28Eh
0x1801650cd  jmp     loc_18016517C
0x1801650d2  lea     r8, [rbp+0F0h+instance]; instance
0x1801650d6  mov     rcx, rbx; context
0x1801650d9  lea     rdx, WSP_Partition_DeleteObject_rtti; methodDecl
0x1801650e0  call    MI_Context_ConstructParameters
0x1801650e5  mov     edi, eax
0x1801650e7  test    eax, eax
0x1801650e9  jz      short loc_18016510B
0x1801650eb  mov     eax, cs:dword_180397B68
0x1801650f1  cmp     eax, 2
0x1801650f4  jbe     loc_1801651A9
0x1801650fa  mov     [rsp+1F0h+var_17C], 296h
0x180165102  lea     rdx, unk_18035A298
0x180165109  jmp     short loc_180165178
0x18016510b  cmp     [rsp+1F0h+var_174], 0
0x180165110  mov     rcx, r14
0x180165113  jnz     short loc_18016511E
0x180165115  call    ?PmDeletePartition@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmDeletePartition(ushort const *)
0x18016511a  mov     edi, eax
0x18016511c  jmp     short loc_180165145
0x18016511e  call    ?PmcDeletePartition@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcDeletePartition(ushort const *)
0x180165123  mov     edi, eax
0x180165125  test    eax, eax
0x180165127  jnz     short loc_180165145
0x180165129  xor     r8d, r8d; unsigned __int64 *
0x18016512c  lea     rdx, [rbp+0F0h+var_148]; unsigned __int16 **
0x180165130  mov     rcx, r14; unsigned __int16 *
0x180165133  call    ?PmUnpackPartitionKey@@YAHPEBGPEAPEAGPEA_K@Z; PmUnpackPartitionKey(ushort const *,ushort * *,unsigned __int64 *)
0x180165138  test    eax, eax
0x18016513a  jz      short loc_180165145
0x18016513c  mov     rcx, [rbp+0F0h+var_148]
0x180165140  call    ?PmcRefreshDisk@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcRefreshDisk(ushort const *)
0x180165145  lea     rdx, [rbp+0F0h+instance]
0x180165149  mov     [rbp+0F0h+var_A0.value], edi
0x18016514c  mov     rcx, rbx; self
0x18016514f  mov     [rbp+0F0h+var_A0.exists], 1
0x180165153  call    MI_Instance_Destruct
0x180165158  mov     edi, eax
0x18016515a  test    eax, eax
0x18016515c  jz      short loc_1801651A9
0x18016515e  mov     eax, cs:dword_180397B68
0x180165164  cmp     eax, 2
0x180165167  jbe     short loc_1801651A9
0x180165169  mov     [rsp+1F0h+var_17C], 2BAh
0x180165171  lea     rdx, byte_180359E89
0x180165178  mov     [rsp+1F0h+var_180], edi
0x18016517c  lea     rax, aWspPartitionIn_2; "WSP_Partition_Invoke_DeleteObject"
0x180165183  mov     [rbp+0F0h+var_168], rax
0x180165187  lea     rax, [rsp+1F0h+var_180]
0x18016518c  mov     [rsp+1F0h+var_1C0], rax
0x180165191  lea     rax, [rsp+1F0h+var_17C]
0x180165196  mov     [rsp+1F0h+var_1C8], rax
0x18016519b  lea     rax, [rbp+0F0h+var_168]
0x18016519f  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1801651a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801651a9  mov     rdx, [rbp+0F0h+var_140]; unsigned __int16 *
0x1801651ad  lea     r9, [rbp+0F0h+var_A0]; struct _MI_ConstUint32Field *
0x1801651b1  mov     [rsp+1F0h+var_1C8], 0; unsigned __int16 *
0x1801651ba  mov     r8, rsi; struct _MI_ConstStringField *
0x1801651bd  mov     rcx, r12; unsigned __int16 *
0x1801651c0  mov     [rsp+1F0h+var_1D0], edi; enum _MI_Result
0x1801651c4  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801651c9  lea     rcx, [rbp+0F0h+var_128]; this
0x1801651cd  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801651d2  mov     eax, cs:dword_180397B68
0x1801651d8  cmp     eax, 5
0x1801651db  jbe     loc_1801652D1
0x1801651e1  mov     rdx, 400000000000h
  ... truncated ...
```
