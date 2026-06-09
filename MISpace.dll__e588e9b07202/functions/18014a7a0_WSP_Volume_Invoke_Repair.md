# WSP_Volume_Invoke_Repair

- ea: `0x18014a7a0`
- end: `0x18014af40`
- name: `WSP_Volume_Invoke_Repair`
- size: `1952`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

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
- `0x1800167e0`
- `0x180016c80`
- `0x18001afd0`
- `0x1800234e4`
- `0x180025444`
- `0x180055ec4`
- `0x180138120`
- `0x180144088`
- `0x18014a7a0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014a81d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014a887`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014aa58`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014a81d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014a887`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014aa58`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014a84b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014a84b`

## string_xrefs

- `0x18014a965`: `Repair`
- `0x18014ae6d`: `Repair`
- `0x18014aeee`: `Repair`
- `0x18014a893`: `WSP_Volume_Invoke_Repair`
- `0x18014a96c`: `WSP_Volume_Invoke_Repair`
- `0x18014abb6`: `WSP_Volume_Invoke_Repair`
- `0x18014ad2d`: `WSP_Volume_Invoke_Repair`
- `0x18014ad63`: `WSP_Volume_Invoke_Repair`
- `0x18014ad70`: `WSP_Volume_Invoke_Repair`
- `0x18014ac69`: `Repair Volume`

## pseudocode

```c
ULONG __fastcall WSP_Volume_Invoke_Repair(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_Volume_Repair *a7)
{
  int v9; // r13d
  int v10; // r8d
  int v11; // r9d
  struct _PM_REPAIR_VOLUME_PARAMETERS_EX *v12; // r14
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  char IsRemoteInstance; // al
  const MI_Char *v21; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  enum _MI_Result v27; // eax
  int v28; // r8d
  int v29; // r9d
  enum _MI_Result v30; // ebx
  int v31; // ecx
  char *v32; // rdx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  int v36; // r8d
  int v37; // r9d
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  unsigned __int16 *v41; // rax
  const MI_Char *v42; // rax
  MI_Uint32 v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int32 v44; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v45; // [rsp+78h] [rbp-88h] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v49; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h] BYREF
  struct _PM_REPAIR_VOLUME_PARAMETERS_EX *v52; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v53; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v54; // [rsp+B0h] [rbp-50h] BYREF
  int v55[2]; // [rsp+B8h] [rbp-48h] BYREF
  const char *v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v59; // [rsp+D8h] [rbp-28h]
  struct _MI_Instance v60; // [rsp+F0h] [rbp-10h] BYREF
  MI_Value value; // [rsp+130h] [rbp+30h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v63; // [rsp+1A0h] [rbp+A0h] BYREF
  int v64; // [rsp+230h] [rbp+130h]
  char v65; // [rsp+234h] [rbp+134h]
  _OWORD *v66; // [rsp+238h] [rbp+138h]
  char v67; // [rsp+240h] [rbp+140h]
  GUID ActivityId; // [rsp+260h] [rbp+160h] BYREF
  __int128 v69; // [rsp+270h] [rbp+170h] BYREF
  int v70; // [rsp+280h] [rbp+180h]
  GUID v71; // [rsp+288h] [rbp+188h]
  GUID v72; // [rsp+298h] [rbp+198h] BYREF

  memset(&value, 0, sizeof(value));
  v54 = a4;
  v53 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v9 = 0;
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v71 = ActivityId;
  v72 = ActivityId;
  EventActivityIdControl(4u, &v72);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v49 = 774;
    v56 = "WSP_Volume_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Volume_Invoke_Repair",
      (unsigned int)&dword_18034EAC4,
      v10,
      v11,
      (__int64)&v56,
      (__int64)&v49);
  }
  LODWORD(v51) = 0;
  v56 = 0;
  v48 = 0;
  v55[0] = 0;
  memset_0(&instance, 0, 0xF8u);
  v52 = 0;
  v12 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v57);
  CSmTimer::Start((CSmTimer *)&v57);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v9 = 1;
  v13 = (__int64)a6[4].value;
  v49 = 0;
  v14 = WspProviderEnter(a2, v13, 1u, &v49);
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
      ((void (__fastcall *)(struct _MI_Context *, __int64))a2->ft->PostResult)(a2, v15);
    goto LABEL_12;
  }
  v69 = 0;
  v70 = 0;
  v47 = 0;
  SubsystemType = WspGetSubsystemType(v21);
  SubsystemVersion = _GetSubsystemVersion(&v47);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v69);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v44 = SubsystemType;
    v43 = SubsystemVersion != v47;
    LOWORD(v47) = v70;
    v45 = (const char *)&v69;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)byte_18034EE8D,
      v25,
      v26,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v47,
      (__int64)&v43);
  }
  v27 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)a6[4].value);
  v30 = v27;
  if ( v27 )
  {
    v31 = dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_44;
    v44 = v27;
    v32 = byte_18034F855;
    v43 = 806;
    goto LABEL_27;
  }
  v30 = MI_Context_ConstructParameters(a2, &WSP_Volume_Repair_rtti, &instance);
  if ( v30 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v44 = v30;
      v32 = (char *)&unk_180351750;
      v43 = 814;
LABEL_27:
      v45 = "WSP_Volume_Invoke_Repair";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        (_DWORD)v32,
        v28,
        v29,
        (__int64)&v45,
        (__int64)&v43,
        (__int64)&v44);
    }
  }
  else
  {
    v30 = WSP_Volume_Params_Repair(a7, &v52, (enum SM_RETURN_CODE *)&v51);
    if ( v30 || (_DWORD)v51 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v44 = v30;
        v43 = 822;
        v45 = "WSP_Volume_Invoke_Repair";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)&dword_18034F204,
          v34,
          v35,
          (__int64)&v45,
          (__int64)&v43,
          (__int64)&v44);
      }
      v12 = v52;
      goto LABEL_44;
    }
    v12 = v52;
    v30 = (unsigned int)WspRunMethodAsJob(
                          a2,
                          (__int64)L"Repair Volume",
                          2u,
                          (__int64)WSP_Volume_Invoke_Repair_Async,
                          (__int64)v52,
                          v48,
                          v55[0],
                          (__int64)a6[4].value,
                          &instance,
                          &v51);
    if ( v30 == MI_RESULT_OK )
    {
      v12 = 0;
      if ( !(_DWORD)v51 )
      {
        v64 = 0;
        v65 = 1;
      }
      v63.value = v51;
      v63.exists = 1;
      v30 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v30 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_44;
      v44 = v30;
      v32 = (char *)&dword_18035044C;
      v43 = 871;
      goto LABEL_27;
    }
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v44 = v30;
      v32 = byte_18034EBFB;
      v43 = 841;
      goto LABEL_27;
    }
  }
LABEL_44:
  CSmTimer::Stop((CSmTimer *)&v57);
  SmLogOnMethodFailure(v54, v53, a6 + 4, &v63, v30, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    if ( v67 )
    {
      v38 = v66[1];
      *(_OWORD *)&v60.ft = *v66;
      v39 = v66[2];
      *(_OWORD *)&v60.serverName = v38;
      v40 = v66[3];
      *(_OWORD *)v60.reserved = v39;
      *(_OWORD *)&v60.reserved[2] = v40;
      v41 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v60, 0);
    }
    else
    {
      v41 = 0;
    }
    v54 = v41;
    v53 = 0;
    v45 = 0;
    v52 = (struct _PM_REPAIR_VOLUME_PARAMETERS_EX *)(1000 * (v58 - v57) / v59);
    v44 = v30;
    v48 = v9;
    v43 = v63.exists != 0 ? v63.value : 0;
    if ( a6[4].exists )
      v42 = a6[4].value;
    else
      v42 = 0;
    v50 = (unsigned __int64)v42;
    *(_QWORD *)v55 = "Repair";
    v51 = (__int64)"WspVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v63.exists != 0 ? v63.value : 0,
      (unsigned int)&unk_180350680,
      v36,
      v37,
      (__int64)&v51,
      (__int64)v55,
      (__int64)&v50,
      (__int64)&v48,
      (__int64)&v43,
      (__int64)&v44,
      (__int64)&v52,
      (__int64)&v45,
      (__int64)&v53,
      (__int64)&v54);
  }
  WspFreeString(v56);
  MI_Instance_Destruct(&instance);
  if ( v12 )
    operator delete(v12);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v30);
LABEL_12:
  WspProviderExit(v49, v15);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v57);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v54 = (unsigned __int16 *)"Repair";
        v50 = 1000 * (v58 - v57) / v59;
        v53 = (unsigned __int16 *)"WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v16,
          (unsigned int)&unk_180350208,
          v17,
          v18,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&IsRemoteRequest,
          (__int64)&v50);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 916;
    v50 = (unsigned __int64)"WSP_Volume_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)byte_18034F3B1,
      v17,
      v18,
      (__int64)&v50,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v57);
  return EventActivityIdControl(4u, &v72);
}

```

## disassembly

```asm
0x18014a7a0  mov     [rsp-8+arg_0], rbx
0x18014a7a5  push    rbp
0x18014a7a6  push    rsi
0x18014a7a7  push    rdi
0x18014a7a8  push    r12
0x18014a7aa  push    r13
0x18014a7ac  push    r14
0x18014a7ae  push    r15
0x18014a7b0  lea     rbp, [rsp-1B0h]
0x18014a7b8  sub     rsp, 2B0h
0x18014a7bf  mov     rax, cs:__security_cookie
0x18014a7c6  xor     rax, rsp
0x18014a7c9  mov     [rbp+1E0h+var_38], rax
0x18014a7d0  mov     r15, [rbp+1E0h+arg_20]
0x18014a7d7  xorps   xmm0, xmm0
0x18014a7da  mov     rsi, [rbp+1E0h+arg_28]
0x18014a7e1  xor     eax, eax
0x18014a7e3  mov     r12, [rbp+1E0h+arg_30]
0x18014a7ea  mov     rbx, r9
0x18014a7ed  movups  xmmword ptr [rbp+1E0h+value], xmm0
0x18014a7f1  mov     rdi, rdx
0x18014a7f4  lea     rdx, [rbp+1E0h+ActivityId]; ActivityId
0x18014a7fb  movups  xmmword ptr [rbp+1E0h+value+10h], xmm0
0x18014a7ff  lea     ecx, [rax+1]; ControlCode
0x18014a802  mov     [rbp+1E0h+var_230], rbx
0x18014a806  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014a80d  mov     [rbp+1E0h+var_238], r15
0x18014a811  mov     qword ptr [rbp+1E0h+value+20h], rax
0x18014a815  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x18014a81d  call    cs:__imp_EventActivityIdControl
0x18014a823  lea     r9, [rbp+1E0h+value]; value
0x18014a827  xor     r8d, r8d; valueType
0x18014a82a  lea     rdx, aActivityid; "ActivityId"
0x18014a831  mov     rcx, rdi; context
0x18014a834  call    MI_Context_GetCustomOption
0x18014a839  xor     r13d, r13d
0x18014a83c  test    eax, eax
0x18014a83e  jnz     short loc_18014A851
0x18014a840  mov     rcx, qword ptr [rbp+1E0h+value]; lpsz
0x18014a844  lea     rdx, [rbp+1E0h+ActivityId]; pclsid
0x18014a84b  call    cs:__imp_CLSIDFromString
0x18014a851  mov     rcx, qword ptr [rbp+1E0h+ActivityId.Data1]
0x18014a858  lea     rdx, [rbp+1E0h+var_48]; ActivityId
0x18014a85f  mov     rax, qword ptr [rbp+1E0h+ActivityId.Data4]
0x18014a866  mov     [rbp+1E0h+var_58], rcx
0x18014a86d  mov     qword ptr [rbp+1E0h+var_48.Data1], rcx
0x18014a874  mov     ecx, 4; ControlCode
0x18014a879  mov     [rbp+1E0h+var_50], rax
0x18014a880  mov     qword ptr [rbp+1E0h+var_48.Data4], rax
0x18014a887  call    cs:__imp_EventActivityIdControl
0x18014a88d  mov     eax, cs:dword_180397B68
0x18014a893  lea     rcx, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014a89a  cmp     eax, 5
0x18014a89d  jbe     short loc_18014A8C8
0x18014a89f  lea     rax, [rbp+1E0h+var_254]
0x18014a8a3  mov     [rbp+1E0h+var_254], 306h
0x18014a8aa  mov     [rsp+2E0h+var_2B8], rax
0x18014a8af  lea     rdx, dword_18034EAC4
0x18014a8b6  lea     rax, [rbp+1E0h+var_220]
0x18014a8ba  mov     [rbp+1E0h+var_220], rcx
0x18014a8be  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014a8c3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014a8c8  xor     edx, edx; Val
0x18014a8ca  mov     dword ptr [rbp+1E0h+var_248], r13d
0x18014a8ce  mov     r8d, 0F8h; Size
0x18014a8d4  mov     [rbp+1E0h+var_220], r13
0x18014a8d8  lea     rcx, [rbp+1E0h+instance]; void *
0x18014a8dc  mov     [rbp+1E0h+var_258], r13d
0x18014a8e0  mov     [rbp+1E0h+var_228], r13d
0x18014a8e4  call    memset_0
0x18014a8e9  lea     rcx, [rbp+1E0h+var_218]; this
0x18014a8ed  mov     [rbp+1E0h+var_240], r13
0x18014a8f1  mov     r14, r13
0x18014a8f4  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014a8f9  lea     rcx, [rbp+1E0h+var_218]; this
0x18014a8fd  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014a902  mov     rcx, rdi; context
0x18014a905  call    WspIsRemoteRequest
0x18014a90a  mov     [rbp+1E0h+var_260], eax
0x18014a90d  cmp     [rsi+48h], r13b
0x18014a911  jz      short loc_18014A926
0x18014a913  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014a917  call    WspIsRemoteInstance
0x18014a91c  test    al, al
0x18014a91e  jz      short loc_18014A926
0x18014a920  mov     r13d, 1
0x18014a926  mov     rdx, [rsi+40h]
0x18014a92a  lea     r9, [rbp+1E0h+var_254]
0x18014a92e  mov     r8d, 1
0x18014a934  mov     [rbp+1E0h+var_254], r14d
0x18014a938  mov     rcx, rdi; context
0x18014a93b  call    WspProviderEnter
0x18014a940  mov     edx, eax
0x18014a942  test    eax, eax
0x18014a944  jz      loc_18014AA88
0x18014a94a  xor     r15d, r15d
0x18014a94d  test    rdi, rdi
0x18014a950  jz      short loc_18014A965
0x18014a952  mov     rax, [rdi]
0x18014a955  test    rax, rax
0x18014a958  jz      short loc_18014A965
0x18014a95a  mov     rax, [rax]
0x18014a95d  mov     rcx, rdi
0x18014a960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014a965  lea     rsi, aRepair_0; "Repair"
0x18014a96c  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014a973  mov     ecx, [rbp+1E0h+var_254]
0x18014a976  call    WspProviderExit
0x18014a97b  cmp     [rbp+1E0h+var_260], r15d
0x18014a97f  jz      loc_18014AA0F
0x18014a985  lea     rcx, [rbp+1E0h+var_218]; this
0x18014a989  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014a98e  mov     eax, cs:dword_180397B68
0x18014a994  cmp     eax, 5
0x18014a997  jbe     short loc_18014AA0F
0x18014a999  mov     rdx, 400000000000h
0x18014a9a3  lea     rcx, dword_180397B68
0x18014a9aa  call    _tlgKeywordOn
0x18014a9af  test    al, al
0x18014a9b1  jz      short loc_18014AA0F
0x18014a9b3  mov     rax, [rbp+1E0h+var_210]
0x18014a9b7  xor     edx, edx
0x18014a9b9  sub     rax, [rbp+1E0h+var_218]
0x18014a9bd  imul    rax, 3E8h
0x18014a9c4  mov     [rbp+1E0h+var_260], r13d
0x18014a9c8  div     [rbp+1E0h+var_208]
0x18014a9cc  lea     rdx, unk_180350208
0x18014a9d3  mov     [rbp+1E0h+var_230], rsi
0x18014a9d7  mov     [rbp+1E0h+var_250], rax
0x18014a9db  lea     rax, aWspvolume; "WspVolume"
0x18014a9e2  mov     [rbp+1E0h+var_238], rax
0x18014a9e6  lea     rax, [rbp+1E0h+var_250]
0x18014a9ea  mov     [rsp+2E0h+var_2A8], rax
0x18014a9ef  lea     rax, [rbp+1E0h+var_260]
0x18014a9f3  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014a9f8  lea     rax, [rbp+1E0h+var_230]
0x18014a9fc  mov     [rsp+2E0h+var_2B8], rax
0x18014aa01  lea     rax, [rbp+1E0h+var_238]
0x18014aa05  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014aa0a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18014aa0f  mov     eax, cs:dword_180397B68
0x18014aa15  cmp     eax, 5
0x18014aa18  jbe     short loc_18014AA43
0x18014aa1a  lea     rax, [rbp+1E0h+var_260]
0x18014aa1e  mov     [rbp+1E0h+var_260], 394h
0x18014aa25  mov     [rsp+2E0h+var_2B8], rax
0x18014aa2a  lea     rdx, byte_18034F3B1
0x18014aa31  lea     rax, [rbp+1E0h+var_250]
0x18014aa35  mov     [rbp+1E0h+var_250], r12
0x18014aa39  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014aa3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014aa43  lea     rcx, [rbp+1E0h+var_218]; this
0x18014aa47  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18014aa4c  lea     rdx, [rbp+1E0h+var_48]; ActivityId
0x18014aa53  mov     ecx, 4; ControlCode
0x18014aa58  call    cs:__imp_EventActivityIdControl
0x18014aa5e  mov     rcx, [rbp+1E0h+var_38]
0x18014aa65  xor     rcx, rsp; StackCookie
0x18014aa68  call    __security_check_cookie
0x18014aa6d  mov     rbx, [rsp+2E0h+arg_0]
0x18014aa75  add     rsp, 2B0h
0x18014aa7c  pop     r15
0x18014aa7e  pop     r14
0x18014aa80  pop     r13
0x18014aa82  pop     r12
0x18014aa84  pop     rdi
0x18014aa85  pop     rsi
0x18014aa86  pop     rbp
0x18014aa87  retn
0x18014aa88  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014aa8c  call    WspIsRemoteInstance
0x18014aa91  mov     rcx, [rsi+40h]
0x18014aa95  test    al, al
0x18014aa97  jz      short loc_18014AAB6
0x18014aa99  mov     r8, rcx; unsigned __int16 *
0x18014aa9c  mov     qword ptr [rsp+2E0h+var_2C0], r12; void *
0x18014aaa1  mov     rcx, rdi; struct _MI_Context *
0x18014aaa4  mov     r9, r15; unsigned __int16 *
0x18014aaa7  mov     rdx, rbx; unsigned __int16 *
0x18014aaaa  call    WspInvokeRemoteMethod
0x18014aaaf  mov     edx, eax
0x18014aab1  jmp     loc_18014A94A
0x18014aab6  xor     eax, eax
0x18014aab8  xorps   xmm0, xmm0
0x18014aabb  movups  [rbp+1E0h+var_70], xmm0
0x18014aac2  mov     [rbp+1E0h+var_60], eax
0x18014aac8  mov     [rbp+1E0h+var_25C], eax
0x18014aacb  call    WspGetSubsystemType
0x18014aad0  lea     rcx, [rbp+1E0h+var_25C]
0x18014aad4  mov     ebx, eax
0x18014aad6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18014aadb  lea     rdx, [rbp+1E0h+var_70]; struct _SUBSYSTEM_INFO *
0x18014aae2  mov     ecx, ebx; unsigned int
0x18014aae4  mov     r15d, eax
0x18014aae7  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18014aaec  mov     ecx, cs:dword_180397B68
0x18014aaf2  cmp     ecx, 5
0x18014aaf5  jbe     short loc_18014AB6C
0x18014aaf7  mov     rdx, 400000000000h
0x18014ab01  lea     rcx, dword_180397B68
0x18014ab08  call    _tlgKeywordOn
0x18014ab0d  test    al, al
0x18014ab0f  jz      short loc_18014AB6C
0x18014ab11  xor     eax, eax
0x18014ab13  mov     [rsp+2E0h+var_26C], ebx
0x18014ab17  cmp     r15d, [rbp+1E0h+var_25C]
0x18014ab1b  lea     rdx, byte_18034EE8D
0x18014ab22  setnz   al
0x18014ab25  mov     [rsp+2E0h+var_270], eax
0x18014ab29  movzx   eax, word ptr [rbp+1E0h+var_60]
0x18014ab30  mov     word ptr [rbp+1E0h+var_25C], ax
0x18014ab34  lea     rax, [rbp+1E0h+var_70]
0x18014ab3b  mov     [rsp+2E0h+var_268], rax
0x18014ab40  lea     rax, [rsp+2E0h+var_270]
0x18014ab45  mov     [rsp+2E0h+var_2A8], rax
0x18014ab4a  lea     rax, [rbp+1E0h+var_25C]
0x18014ab4e  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014ab53  lea     rax, [rsp+2E0h+var_26C]
0x18014ab58  mov     [rsp+2E0h+var_2B8], rax
0x18014ab5d  lea     rax, [rsp+2E0h+var_268]
0x18014ab62  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014ab67  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18014ab6c  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18014ab70  lea     r9, [rbp+1E0h+var_220]
0x18014ab74  lea     r8, [rbp+1E0h+var_228]
0x18014ab78  lea     rdx, [rbp+1E0h+var_258]
0x18014ab7c  call    WspUnpackObjectId
0x18014ab81  xor     r15d, r15d
0x18014ab84  mov     ebx, eax
0x18014ab86  test    eax, eax
0x18014ab88  jz      short loc_18014ABE0
0x18014ab8a  mov     ecx, cs:dword_180397B68
0x18014ab90  cmp     ecx, 2
0x18014ab93  jbe     loc_18014AD70
0x18014ab99  mov     [rsp+2E0h+var_26C], eax
0x18014ab9d  lea     rdx, byte_18034F855
0x18014aba4  mov     [rsp+2E0h+var_270], 326h
0x18014abac  lea     rax, [rsp+2E0h+var_26C]
0x18014abb1  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014abb6  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014abbd  lea     rax, [rsp+2E0h+var_270]
0x18014abc2  mov     [rsp+2E0h+var_268], r12
0x18014abc7  mov     [rsp+2E0h+var_2B8], rax
0x18014abcc  lea     rax, [rsp+2E0h+var_268]
0x18014abd1  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014abd6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18014abdb  jmp     loc_18014AD77
0x18014abe0  lea     r8, [rbp+1E0h+instance]; instance
0x18014abe4  mov     rcx, rdi; context
0x18014abe7  lea     rdx, WSP_Volume_Repair_rtti; methodDecl
0x18014abee  call    MI_Context_ConstructParameters
0x18014abf3  mov     ebx, eax
0x18014abf5  test    eax, eax
0x18014abf7  jz      short loc_18014AC1D
0x18014abf9  mov     eax, cs:dword_180397B68
0x18014abff  cmp     eax, 2
0x18014ac02  jbe     loc_18014AD70
0x18014ac08  mov     [rsp+2E0h+var_26C], ebx
0x18014ac0c  lea     rdx, unk_180351750
0x18014ac13  mov     [rsp+2E0h+var_270], 32Eh
0x18014ac1b  jmp     short loc_18014ABAC
0x18014ac1d  lea     r8, [rbp+1E0h+var_248]; enum SM_RETURN_CODE *
0x18014ac21  mov     rcx, r12; struct _WSP_Volume_Repair *
0x18014ac24  lea     rdx, [rbp+1E0h+var_240]; struct _PM_REPAIR_VOLUME_PARAMETERS_EX **
0x18014ac28  call    ?WSP_Volume_Params_Repair@@YA?AW4_MI_Result@@PEBU_WSP_Volume_Repair@@PEAPEAU_PM_REPAIR_VOLUME_PARAMETERS_EX@@PEAW4SM_RETURN_CODE@@@Z; WSP_Volume_Params_Repair(_WSP_Volume_Repair const *,_PM_REPAIR_VOLUME_PARAMETERS_EX * *,SM_RETURN_CODE *)
0x18014ac2d  mov     ebx, eax
0x18014ac2f  test    eax, eax
0x18014ac31  jnz     loc_18014AD14
0x18014ac37  cmp     dword ptr [rbp+1E0h+var_248], r15d
0x18014ac3b  jnz     loc_18014AD14
0x18014ac41  mov     r14, [rbp+1E0h+var_240]
0x18014ac45  lea     rax, [rbp+1E0h+var_248]
0x18014ac49  mov     [rsp+2E0h+var_298], rax; __int64
0x18014ac4e  lea     r9, ?WSP_Volume_Invoke_Repair_Async@@YAXPEAX0@Z; WSP_Volume_Invoke_Repair_Async(void *,void *)
0x18014ac55  lea     rax, [rbp+1E0h+instance]
0x18014ac59  mov     rcx, rdi; struct _MI_Context *
0x18014ac5c  mov     [rsp+2E0h+var_2A0], rax; struct _MI_Instance *
0x18014ac61  lea     r8d, [rbx+2]
0x18014ac65  mov     rax, [rsi+40h]
0x18014ac69  lea     rdx, aRepairVolume; "Repair Volume"
0x18014ac70  mov     [rsp+2E0h+var_2A8], rax; __int64
0x18014ac75  mov     eax, [rbp+1E0h+var_228]
0x18014ac78  mov     [rsp+2E0h+var_2B0], eax; int
0x18014ac7c  mov     eax, [rbp+1E0h+var_258]
0x18014ac7f  mov     dword ptr [rsp+2E0h+var_2B8], eax; int
0x18014ac83  mov     qword ptr [rsp+2E0h+var_2C0], r14; __int64
0x18014ac88  call    WspRunMethodAsJob
0x18014ac8d  mov     ebx, eax
0x18014ac8f  test    eax, eax
0x18014ac91  jz      short loc_18014ACBA
0x18014ac93  mov     eax, cs:dword_180397B68
0x18014ac99  cmp     eax, 2
0x18014ac9c  jbe     loc_18014AD70
0x18014aca2  mov     [rsp+2E0h+var_26C], ebx
0x18014aca6  lea     rdx, byte_18034EBFB
0x18014acad  mov     [rsp+2E0h+var_270], 349h
0x18014acb5  jmp     loc_18014ABAC
0x18014acba  mov     eax, dword ptr [rbp+1E0h+var_248]
0x18014acbd  mov     r14, r15
0x18014acc0  test    eax, eax
  ... truncated ...
```
