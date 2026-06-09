# WSP_Volume_Invoke_SetFileSystemLabel

- ea: `0x18014c1d0`
- end: `0x18014c821`
- name: `WSP_Volume_Invoke_SetFileSystemLabel`
- size: `1617`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001970`
- `0x1800045d0`
- `0x180004bfc`
- `0x180006290`
- `0x1800062e0`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
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
- `0x180055ec4`
- `0x18011ed28`
- `0x1801221ec`
- `0x180138120`
- `0x180143f8c`
- `0x18014c1d0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c247`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c299`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c465`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c247`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c299`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014c465`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014c272`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014c272`

## string_xrefs

- `0x18014c370`: `SetFileSystemLabel`
- `0x18014c754`: `SetFileSystemLabel`
- `0x18014c7d5`: `SetFileSystemLabel`
- `0x18014c2a5`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x18014c377`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x18014c5be`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x18014c697`: `WSP_Volume_Invoke_SetFileSystemLabel`

## pseudocode

```c
ULONG __fastcall WSP_Volume_Invoke_SetFileSystemLabel(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_Volume_SetFileSystemLabel *a7)
{
  int v9; // r13d
  int v10; // r8d
  int v11; // r9d
  struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *v12; // r14
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  char IsRemoteInstance; // al
  const MI_Char *v21; // rcx
  unsigned int SubsystemType; // edi
  int SubsystemVersion; // r15d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned __int32 v27; // eax
  int v28; // r8d
  int v29; // r9d
  unsigned __int64 v30; // r15
  enum _MI_Result v31; // edi
  int v32; // ecx
  char *v33; // rdx
  int *v34; // rax
  MI_Uint32 v35; // eax
  int v36; // r9d
  const MI_Char *v37; // rax
  MI_Uint32 *v38; // [rsp+30h] [rbp-D0h]
  MI_Uint32 v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch] BYREF
  enum _MI_Result v41; // [rsp+78h] [rbp-88h] BYREF
  int IsRemoteRequest; // [rsp+7Ch] [rbp-84h] BYREF
  int v43; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v44; // [rsp+84h] [rbp-7Ch] BYREF
  const char *v45; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *v48; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v49; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v50; // [rsp+B0h] [rbp-50h] BYREF
  const char *v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v54; // [rsp+D0h] [rbp-30h]
  MI_Value value; // [rsp+E0h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+108h] [rbp+8h] BYREF
  __int128 v57; // [rsp+118h] [rbp+18h] BYREF
  int v58; // [rsp+128h] [rbp+28h]
  GUID v59; // [rsp+130h] [rbp+30h]
  GUID v60; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+150h] [rbp+50h] BYREF
  struct _MI_ConstUint32Field v62; // [rsp+190h] [rbp+90h] BYREF

  memset(&value, 0, sizeof(value));
  v50 = a4;
  v49 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v9 = 0;
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v59 = ActivityId;
  v60 = ActivityId;
  EventActivityIdControl(4u, &v60);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v44 = 1194;
    v47 = (unsigned __int64)"WSP_Volume_Invoke_SetFileSystemLabel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Volume_Invoke_SetFileSystemLabel",
      (unsigned int)&byte_18034EE5F,
      v10,
      v11,
      (__int64)&v47,
      (__int64)&v44);
  }
  v41 = MI_RESULT_OK;
  v47 = 0;
  LODWORD(v51) = 0;
  memset_0(&instance, 0, 0x68u);
  v48 = 0;
  v12 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v52);
  CSmTimer::Start((CSmTimer *)&v52);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v9 = 1;
  v13 = (__int64)a6[4].value;
  v44 = 0;
  v14 = WspProviderEnter(a2, v13, 1u, &v44);
  v15 = v14;
  if ( v14 )
    goto LABEL_9;
  IsRemoteInstance = WspIsRemoteInstance((unsigned __int16 *)a6[4].value);
  v21 = a6[4].value;
  if ( IsRemoteInstance )
  {
    v15 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)a6[4].value, a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v15);
    goto LABEL_12;
  }
  v57 = 0;
  v58 = 0;
  v43 = 0;
  SubsystemType = WspGetSubsystemType(v21);
  SubsystemVersion = _GetSubsystemVersion(&v43);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v57);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v39 = SubsystemType;
    v40 = SubsystemVersion != v43;
    LOWORD(v43) = v58;
    v45 = (const char *)&v57;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)&byte_1803504F7,
      v25,
      v26,
      (__int64)&v45,
      (__int64)&v39,
      (__int64)&v43,
      (__int64)&v40);
  }
  v27 = WspUnpackObjectId((unsigned __int16 *)a6[4].value);
  v30 = v47;
  v31 = v27;
  if ( v27 )
  {
    v32 = dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_38;
    v39 = v27;
    v33 = &byte_180350647;
    v40 = 1225;
    goto LABEL_27;
  }
  v31 = MI_Context_ConstructParameters(a2, &WSP_Volume_SetFileSystemLabel_rtti, &instance);
  if ( v31 == MI_RESULT_OK )
  {
    WSP_Volume_Params_SetFileSystemLabel(a7, &v48, (enum SM_RETURN_CODE *)&v41);
    v12 = v48;
    if ( (_DWORD)v51 )
      v35 = PmcSetFileSystemLabel(v30, v48);
    else
      v35 = PmSetFileSystemLabel(v30, v48);
    v62.value = v35;
    v62.exists = 1;
    v31 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v31 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_38;
    v41 = v31;
    v38 = (MI_Uint32 *)&v41;
    v33 = &byte_18035129F;
    v34 = (int *)&v39;
    v39 = 1257;
    goto LABEL_28;
  }
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v39 = v31;
    v33 = (char *)&unk_18034FEE8;
    v40 = 1233;
LABEL_27:
    v38 = &v39;
    v34 = &v40;
LABEL_28:
    v45 = "WSP_Volume_Invoke_SetFileSystemLabel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v32,
      (_DWORD)v33,
      v28,
      v29,
      (__int64)&v45,
      (__int64)v34,
      (__int64)v38);
  }
LABEL_38:
  CSmTimer::Stop((CSmTimer *)&v52);
  SmLogOnMethodFailure(v50, v49, a6 + 4, &v62, v31, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v50 = 0;
    v49 = 0;
    v47 = 1000 * (v53 - v52) / v54;
    v45 = 0;
    v41 = v31;
    v40 = v9;
    v39 = v62.exists != 0 ? v62.value : 0;
    if ( a6[4].exists )
      v37 = a6[4].value;
    else
      v37 = 0;
    v46 = (unsigned __int64)v37;
    v48 = (struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *)"SetFileSystemLabel";
    v51 = "WspVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v62.exists != 0 ? v62.value : 0,
      (unsigned int)&unk_180350878,
      0,
      v36,
      (__int64)&v51,
      (__int64)&v48,
      (__int64)&v46,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v41,
      (__int64)&v47,
      (__int64)&v45,
      (__int64)&v49,
      (__int64)&v50);
  }
  WspFreeString(v30);
  MI_Instance_Destruct(&instance);
  if ( v12 )
    operator delete(v12);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v31);
LABEL_12:
  WspProviderExit(v44, v15);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v52);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v50 = (unsigned __int16 *)"SetFileSystemLabel";
        v46 = 1000 * (v53 - v52) / v54;
        v49 = (unsigned __int16 *)"WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v16,
          (unsigned int)byte_1803515E5,
          v17,
          v18,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&IsRemoteRequest,
          (__int64)&v46);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 1302;
    v46 = (unsigned __int64)"WSP_Volume_Invoke_SetFileSystemLabel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)byte_18034FB81,
      v17,
      v18,
      (__int64)&v46,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v52);
  return EventActivityIdControl(4u, &v60);
}

```

## disassembly

```asm
0x18014c1d0  mov     [rsp-8+arg_0], rbx
0x18014c1d5  push    rbp
0x18014c1d6  push    rsi
0x18014c1d7  push    rdi
0x18014c1d8  push    r12
0x18014c1da  push    r13
0x18014c1dc  push    r14
0x18014c1de  push    r15
0x18014c1e0  lea     rbp, [rsp-0D0h]
0x18014c1e8  sub     rsp, 1D0h
0x18014c1ef  mov     rax, cs:__security_cookie
0x18014c1f6  xor     rax, rsp
0x18014c1f9  mov     [rbp+100h+var_40], rax
0x18014c200  mov     r15, [rbp+100h+arg_20]
0x18014c207  xorps   xmm0, xmm0
0x18014c20a  mov     rsi, [rbp+100h+arg_28]
0x18014c211  xor     eax, eax
0x18014c213  mov     r12, [rbp+100h+arg_30]
0x18014c21a  mov     rbx, rdx
0x18014c21d  movups  xmmword ptr [rbp+100h+value], xmm0
0x18014c221  lea     rdx, [rbp+100h+ActivityId]; ActivityId
0x18014c225  mov     rdi, r9
0x18014c228  movups  xmmword ptr [rbp+100h+value+10h], xmm0
0x18014c22c  lea     ecx, [rax+1]; ControlCode
0x18014c22f  mov     [rbp+100h+var_150], r9
0x18014c233  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014c23a  mov     [rbp+100h+var_158], r15
0x18014c23e  mov     qword ptr [rbp+100h+value+20h], rax
0x18014c242  movdqu  xmmword ptr [rbp+100h+ActivityId.Data1], xmm0
0x18014c247  call    cs:__imp_EventActivityIdControl
0x18014c24d  lea     r9, [rbp+100h+value]; value
0x18014c251  xor     r8d, r8d; valueType
0x18014c254  lea     rdx, aActivityid; "ActivityId"
0x18014c25b  mov     rcx, rbx; context
0x18014c25e  call    MI_Context_GetCustomOption
0x18014c263  xor     r13d, r13d
0x18014c266  test    eax, eax
0x18014c268  jnz     short loc_18014C278
0x18014c26a  mov     rcx, qword ptr [rbp+100h+value]; lpsz
0x18014c26e  lea     rdx, [rbp+100h+ActivityId]; pclsid
0x18014c272  call    cs:__imp_CLSIDFromString
0x18014c278  mov     rcx, qword ptr [rbp+100h+ActivityId.Data1]
0x18014c27c  lea     rdx, [rbp+100h+var_C0]; ActivityId
0x18014c280  mov     rax, qword ptr [rbp+100h+ActivityId.Data4]
0x18014c284  mov     [rbp+100h+var_D0], rcx
0x18014c288  mov     qword ptr [rbp+100h+var_C0.Data1], rcx
0x18014c28c  mov     ecx, 4; ControlCode
0x18014c291  mov     [rbp+100h+var_C8], rax
0x18014c295  mov     qword ptr [rbp+100h+var_C0.Data4], rax
0x18014c299  call    cs:__imp_EventActivityIdControl
0x18014c29f  mov     eax, cs:dword_180397B68
0x18014c2a5  lea     rcx, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x18014c2ac  cmp     eax, 5
0x18014c2af  jbe     short loc_18014C2DA
0x18014c2b1  lea     rax, [rbp+100h+var_17C]
0x18014c2b5  mov     [rbp+100h+var_17C], 4AAh
0x18014c2bc  mov     [rsp+200h+var_1D8], rax
0x18014c2c1  lea     rdx, byte_18034EE5F
0x18014c2c8  lea     rax, [rbp+100h+var_168]
0x18014c2cc  mov     [rbp+100h+var_168], rcx
0x18014c2d0  mov     qword ptr [rsp+200h+var_1E0], rax
0x18014c2d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014c2da  xor     edx, edx; Val
0x18014c2dc  mov     [rsp+200h+var_188], r13d
0x18014c2e1  lea     rcx, [rbp+100h+instance]; void *
0x18014c2e5  mov     [rbp+100h+var_168], r13
0x18014c2e9  mov     dword ptr [rbp+100h+var_148], r13d
0x18014c2ed  lea     r8d, [rdx+68h]; Size
0x18014c2f1  call    memset_0
0x18014c2f6  lea     rcx, [rbp+100h+var_140]; this
0x18014c2fa  mov     [rbp+100h+var_160], r13
0x18014c2fe  mov     r14, r13
0x18014c301  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014c306  lea     rcx, [rbp+100h+var_140]; this
0x18014c30a  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014c30f  mov     rcx, rbx; context
0x18014c312  call    WspIsRemoteRequest
0x18014c317  mov     [rsp+200h+var_184], eax
0x18014c31b  cmp     [rsi+48h], r13b
0x18014c31f  jz      short loc_18014C334
0x18014c321  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014c325  call    WspIsRemoteInstance
0x18014c32a  test    al, al
0x18014c32c  jz      short loc_18014C334
0x18014c32e  mov     r13d, 1
0x18014c334  mov     rdx, [rsi+40h]
0x18014c338  lea     r9, [rbp+100h+var_17C]
0x18014c33c  mov     r8d, 1
0x18014c342  mov     [rbp+100h+var_17C], r14d
0x18014c346  mov     rcx, rbx; context
0x18014c349  call    WspProviderEnter
0x18014c34e  mov     edx, eax
0x18014c350  test    eax, eax
0x18014c352  jz      loc_18014C495
0x18014c358  test    rbx, rbx
0x18014c35b  jz      short loc_18014C370
0x18014c35d  mov     rax, [rbx]
0x18014c360  test    rax, rax
0x18014c363  jz      short loc_18014C370
0x18014c365  mov     rax, [rax]
0x18014c368  mov     rcx, rbx
0x18014c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014c370  lea     rsi, aSetfilesysteml; "SetFileSystemLabel"
0x18014c377  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x18014c37e  mov     ecx, [rbp+100h+var_17C]
0x18014c381  call    WspProviderExit
0x18014c386  cmp     [rsp+200h+var_184], 0
0x18014c38b  jz      loc_18014C41D
0x18014c391  lea     rcx, [rbp+100h+var_140]; this
0x18014c395  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014c39a  mov     eax, cs:dword_180397B68
0x18014c3a0  cmp     eax, 5
0x18014c3a3  jbe     short loc_18014C41D
0x18014c3a5  mov     rdx, 400000000000h
0x18014c3af  lea     rcx, dword_180397B68
0x18014c3b6  call    _tlgKeywordOn
0x18014c3bb  test    al, al
0x18014c3bd  jz      short loc_18014C41D
0x18014c3bf  mov     rax, [rbp+100h+var_138]
0x18014c3c3  xor     edx, edx
0x18014c3c5  sub     rax, [rbp+100h+var_140]
0x18014c3c9  imul    rax, 3E8h
0x18014c3d0  mov     [rsp+200h+var_184], r13d
0x18014c3d5  div     [rbp+100h+var_130]
0x18014c3d9  lea     rdx, byte_1803515E5
0x18014c3e0  mov     [rbp+100h+var_150], rsi
0x18014c3e4  mov     [rbp+100h+var_170], rax
0x18014c3e8  lea     rax, aWspvolume; "WspVolume"
0x18014c3ef  mov     [rbp+100h+var_158], rax
0x18014c3f3  lea     rax, [rbp+100h+var_170]
0x18014c3f7  mov     [rsp+200h+var_1C8], rax
0x18014c3fc  lea     rax, [rsp+200h+var_184]
0x18014c401  mov     [rsp+200h+var_1D0], rax
0x18014c406  lea     rax, [rbp+100h+var_150]
0x18014c40a  mov     [rsp+200h+var_1D8], rax
0x18014c40f  lea     rax, [rbp+100h+var_158]
0x18014c413  mov     qword ptr [rsp+200h+var_1E0], rax
0x18014c418  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18014c41d  mov     eax, cs:dword_180397B68
0x18014c423  cmp     eax, 5
0x18014c426  jbe     short loc_18014C453
0x18014c428  lea     rax, [rsp+200h+var_184]
0x18014c42d  mov     [rsp+200h+var_184], 516h
0x18014c435  mov     [rsp+200h+var_1D8], rax
0x18014c43a  lea     rdx, byte_18034FB81
0x18014c441  lea     rax, [rbp+100h+var_170]
0x18014c445  mov     [rbp+100h+var_170], r12
0x18014c449  mov     qword ptr [rsp+200h+var_1E0], rax
0x18014c44e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014c453  lea     rcx, [rbp+100h+var_140]; this
0x18014c457  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18014c45c  lea     rdx, [rbp+100h+var_C0]; ActivityId
0x18014c460  mov     ecx, 4; ControlCode
0x18014c465  call    cs:__imp_EventActivityIdControl
0x18014c46b  mov     rcx, [rbp+100h+var_40]
0x18014c472  xor     rcx, rsp; StackCookie
0x18014c475  call    __security_check_cookie
0x18014c47a  mov     rbx, [rsp+200h+arg_0]
0x18014c482  add     rsp, 1D0h
0x18014c489  pop     r15
0x18014c48b  pop     r14
0x18014c48d  pop     r13
0x18014c48f  pop     r12
0x18014c491  pop     rdi
0x18014c492  pop     rsi
0x18014c493  pop     rbp
0x18014c494  retn
0x18014c495  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014c499  call    WspIsRemoteInstance
0x18014c49e  mov     rcx, [rsi+40h]
0x18014c4a2  test    al, al
0x18014c4a4  jz      short loc_18014C4C3
0x18014c4a6  mov     r8, rcx; unsigned __int16 *
0x18014c4a9  mov     qword ptr [rsp+200h+var_1E0], r12; void *
0x18014c4ae  mov     rcx, rbx; struct _MI_Context *
0x18014c4b1  mov     r9, r15; unsigned __int16 *
0x18014c4b4  mov     rdx, rdi; unsigned __int16 *
0x18014c4b7  call    WspInvokeRemoteMethod
0x18014c4bc  mov     edx, eax
0x18014c4be  jmp     loc_18014C358
0x18014c4c3  xor     eax, eax
0x18014c4c5  xorps   xmm0, xmm0
0x18014c4c8  movups  [rbp+100h+var_E8], xmm0
0x18014c4cc  mov     [rbp+100h+var_D8], eax
0x18014c4cf  mov     [rbp+100h+var_180], eax
0x18014c4d2  call    WspGetSubsystemType
0x18014c4d7  lea     rcx, [rbp+100h+var_180]
0x18014c4db  mov     edi, eax
0x18014c4dd  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18014c4e2  lea     rdx, [rbp+100h+var_E8]; struct _SUBSYSTEM_INFO *
0x18014c4e6  mov     ecx, edi; unsigned int
0x18014c4e8  mov     r15d, eax
0x18014c4eb  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18014c4f0  mov     ecx, cs:dword_180397B68
0x18014c4f6  cmp     ecx, 5
0x18014c4f9  jbe     short loc_18014C568
0x18014c4fb  mov     rdx, 400000000000h
0x18014c505  lea     rcx, dword_180397B68
0x18014c50c  call    _tlgKeywordOn
0x18014c511  test    al, al
0x18014c513  jz      short loc_18014C568
0x18014c515  xor     eax, eax
0x18014c517  mov     [rsp+200h+var_190], edi
0x18014c51b  cmp     r15d, [rbp+100h+var_180]
0x18014c51f  lea     rdx, byte_1803504F7
0x18014c526  setnz   al
0x18014c529  mov     [rsp+200h+var_18C], eax
0x18014c52d  movzx   eax, word ptr [rbp+100h+var_D8]
0x18014c531  mov     word ptr [rbp+100h+var_180], ax
0x18014c535  lea     rax, [rbp+100h+var_E8]
0x18014c539  mov     [rbp+100h+var_178], rax
0x18014c53d  lea     rax, [rsp+200h+var_18C]
0x18014c542  mov     [rsp+200h+var_1C8], rax
0x18014c547  lea     rax, [rbp+100h+var_180]
0x18014c54b  mov     [rsp+200h+var_1D0], rax
0x18014c550  lea     rax, [rsp+200h+var_190]
0x18014c555  mov     [rsp+200h+var_1D8], rax
0x18014c55a  lea     rax, [rbp+100h+var_178]
0x18014c55e  mov     qword ptr [rsp+200h+var_1E0], rax
0x18014c563  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18014c568  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014c56c  lea     r9, [rbp+100h+var_168]
0x18014c570  lea     r8, [rsp+200h+var_190]
0x18014c575  lea     rdx, [rbp+100h+var_148]
0x18014c579  call    WspUnpackObjectId
0x18014c57e  mov     r15, [rbp+100h+var_168]
0x18014c582  mov     edi, eax
0x18014c584  test    eax, eax
0x18014c586  jz      short loc_18014C5DC
0x18014c588  mov     ecx, cs:dword_180397B68
0x18014c58e  cmp     ecx, 2
0x18014c591  jbe     loc_18014C697
0x18014c597  mov     [rsp+200h+var_190], eax
0x18014c59b  lea     rdx, byte_180350647
0x18014c5a2  mov     [rsp+200h+var_18C], 4C9h
0x18014c5aa  lea     rax, [rsp+200h+var_190]
0x18014c5af  mov     [rsp+200h+var_1D0], rax
0x18014c5b4  lea     rax, [rsp+200h+var_18C]
0x18014c5b9  mov     [rsp+200h+var_1D8], rax
0x18014c5be  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x18014c5c5  lea     rax, [rbp+100h+var_178]
0x18014c5c9  mov     [rbp+100h+var_178], r12
0x18014c5cd  mov     qword ptr [rsp+200h+var_1E0], rax
0x18014c5d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18014c5d7  jmp     loc_18014C69E
0x18014c5dc  lea     r8, [rbp+100h+instance]; instance
0x18014c5e0  mov     rcx, rbx; context
0x18014c5e3  lea     rdx, WSP_Volume_SetFileSystemLabel_rtti; methodDecl
0x18014c5ea  call    MI_Context_ConstructParameters
0x18014c5ef  mov     edi, eax
0x18014c5f1  test    eax, eax
0x18014c5f3  jz      short loc_18014C619
0x18014c5f5  mov     eax, cs:dword_180397B68
0x18014c5fb  cmp     eax, 2
0x18014c5fe  jbe     loc_18014C697
0x18014c604  mov     [rsp+200h+var_190], edi
0x18014c608  lea     rdx, unk_18034FEE8
0x18014c60f  mov     [rsp+200h+var_18C], 4D1h
0x18014c617  jmp     short loc_18014C5AA
0x18014c619  lea     r8, [rsp+200h+var_188]; enum SM_RETURN_CODE *
0x18014c61e  mov     rcx, r12; struct _WSP_Volume_SetFileSystemLabel *
0x18014c621  lea     rdx, [rbp+100h+var_160]; struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS **
0x18014c625  call    ?WSP_Volume_Params_SetFileSystemLabel@@YA?AW4_MI_Result@@PEBU_WSP_Volume_SetFileSystemLabel@@PEAPEAU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@PEAW4SM_RETURN_CODE@@@Z; WSP_Volume_Params_SetFileSystemLabel(_WSP_Volume_SetFileSystemLabel const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS * *,SM_RETURN_CODE *)
0x18014c62a  cmp     dword ptr [rbp+100h+var_148], r14d
0x18014c62e  mov     rcx, r15
0x18014c631  mov     r14, [rbp+100h+var_160]
0x18014c635  mov     rdx, r14
0x18014c638  jnz     short loc_18014C641
0x18014c63a  call    ?PmSetFileSystemLabel@@YA?AW4SM_RETURN_CODE@@PEBGPEBU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@@Z; PmSetFileSystemLabel(ushort const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS const *)
0x18014c63f  jmp     short loc_18014C646
0x18014c641  call    ?PmcSetFileSystemLabel@@YA?AW4SM_RETURN_CODE@@PEBGPEBU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@@Z; PmcSetFileSystemLabel(ushort const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS const *)
0x18014c646  lea     rdx, [rbp+100h+instance]
0x18014c64a  mov     [rbp+100h+var_70.value], eax
0x18014c650  mov     rcx, rbx; self
0x18014c653  mov     [rbp+100h+var_70.exists], 1
0x18014c65a  call    MI_Instance_Destruct
0x18014c65f  mov     edi, eax
0x18014c661  test    eax, eax
0x18014c663  jz      short loc_18014C697
0x18014c665  mov     eax, cs:dword_180397B68
0x18014c66b  cmp     eax, 2
0x18014c66e  jbe     short loc_18014C697
0x18014c670  lea     rax, [rsp+200h+var_188]
0x18014c675  mov     [rsp+200h+var_188], edi
0x18014c679  mov     [rsp+200h+var_1D0], rax
0x18014c67e  lea     rdx, byte_18035129F
0x18014c685  lea     rax, [rsp+200h+var_190]
0x18014c68a  mov     [rsp+200h+var_190], 4E9h
0x18014c692  jmp     loc_18014C5B9
0x18014c697  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x18014c69e  lea     rcx, [rbp+100h+var_140]; this
0x18014c6a2  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014c6a7  mov     rdx, [rbp+100h+var_158]; unsigned __int16 *
0x18014c6ab  lea     r9, [rbp+100h+var_70]; struct _MI_ConstUint32Field *
0x18014c6b2  mov     rcx, [rbp+100h+var_150]; unsigned __int16 *
0x18014c6b6  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18014c6ba  mov     [rsp+200h+var_1D8], 0; unsigned __int16 *
0x18014c6c3  mov     [rsp+200h+var_1E0], edi; enum _MI_Result
0x18014c6c7  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18014c6cc  mov     eax, cs:dword_180397B68
  ... truncated ...
```
