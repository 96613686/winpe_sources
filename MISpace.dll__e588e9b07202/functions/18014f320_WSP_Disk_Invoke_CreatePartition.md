# WSP_Disk_Invoke_CreatePartition

- ea: `0x18014f320`
- end: `0x18014fd05`
- name: `WSP_Disk_Invoke_CreatePartition`
- size: `2533`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
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
- `0x18000c704`
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
- `0x180025444`
- `0x18007f590`
- `0x180110ea8`
- `0x180112b78`
- `0x18011402c`
- `0x180115e70`
- `0x180137a24`
- `0x180138120`
- `0x18014d794`
- `0x18014f320`
- `0x180163480`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f3a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f401`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f66a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f3a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f401`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f66a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014fcaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014fcaf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014f3c5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014f3c5`

## string_xrefs

- `0x18014f40d`: `WSP_Disk_Invoke_CreatePartition`
- `0x18014f56e`: `WSP_Disk_Invoke_CreatePartition`
- `0x18014f78f`: `WSP_Disk_Invoke_CreatePartition`
- `0x18014f89a`: `WSP_Disk_Invoke_CreatePartition`
- `0x18014fa79`: `WSP_Disk_Invoke_CreatePartition`
- `0x18014f567`: `CreatePartition`
- `0x18014fc16`: `CreatePartition`
- `0x18014fc97`: `CreatePartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall WSP_Disk_Invoke_CreatePartition(
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
  int v11; // r8d
  int v12; // r9d
  const WCHAR *v13; // r14
  const struct _MI_ConstStringField *v14; // r12
  unsigned int v15; // r13d
  unsigned int v16; // eax
  __int64 v17; // rdx
  int v18; // r15d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  enum _MI_Result v28; // ebx
  int v29; // r8d
  int v30; // r9d
  unsigned __int16 *v31; // rax
  __int32 v32; // eax
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int *v36; // rdx
  int v37; // ecx
  MI_Uint32 Partition; // esi
  int v39; // r8d
  int v40; // r9d
  struct CPmPartition *v41; // rcx
  struct CPmPartition *v42; // rcx
  char *v43; // rdx
  const MI_Char *v44; // rax
  int v45; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v46; // [rsp+74h] [rbp-8Ch] BYREF
  const char *p_self; // [rsp+78h] [rbp-88h] BYREF
  const char *v48; // [rsp+80h] [rbp-80h] BYREF
  int v49; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v50; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v51; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp-68h] BYREF
  struct CPmPartition *v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v56; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v57; // [rsp+C0h] [rbp-40h] BYREF
  const char *v58; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v60; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v61; // [rsp+E0h] [rbp-20h]
  struct _MI_Instance v62; // [rsp+F0h] [rbp-10h] BYREF
  MI_Value value; // [rsp+130h] [rbp+30h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v65; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _MI_Instance *v66; // [rsp+200h] [rbp+100h]
  char v67; // [rsp+208h] [rbp+108h]
  MI_Instance self; // [rsp+220h] [rbp+120h] BYREF
  MI_Instance v69; // [rsp+330h] [rbp+230h] BYREF
  GUID ActivityId; // [rsp+480h] [rbp+380h] BYREF
  __int128 v71; // [rsp+490h] [rbp+390h] BYREF
  int v72; // [rsp+4A0h] [rbp+3A0h]
  GUID v73; // [rsp+4A8h] [rbp+3A8h]
  GUID v74; // [rsp+4B8h] [rbp+3B8h] BYREF
  __int128 v75; // [rsp+4D0h] [rbp+3D0h] BYREF
  int v76; // [rsp+4E0h] [rbp+3E0h]
  char v77; // [rsp+4E4h] [rbp+3E4h]
  __int16 v78; // [rsp+4E6h] [rbp+3E6h]
  __int128 v79; // [rsp+4E8h] [rbp+3E8h]
  __int128 v80; // [rsp+4F8h] [rbp+3F8h]
  __int64 v81; // [rsp+508h] [rbp+408h]

  v57 = a4;
  v56 = a5;
  v54 = (unsigned __int64)a6;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v73 = ActivityId;
  v74 = ActivityId;
  EventActivityIdControl(4u, &v74);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v51 = 807;
    lpFileName = (LPCWSTR)"WSP_Disk_Invoke_CreatePartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Disk_Invoke_CreatePartition",
      (unsigned int)byte_18035378B,
      v11,
      v12,
      (__int64)&lpFileName,
      (__int64)&v51);
  }
  v13 = 0;
  lpFileName = 0;
  LODWORD(v58) = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xB8u);
  v69.ft = 0;
  memset_0(&v69.classDecl, 0, 0x148u);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v53 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
  v53 = 0;
  v50 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v59);
  hMem = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v59);
  LODWORD(v48) = WspIsRemoteRequest(a2);
  v14 = a6 + 4;
  v15 = a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value);
  v51 = 0;
  v16 = WspProviderEnter(a2, (__int64)v14->value, 1u, &v51);
  v17 = v16;
  if ( v16 )
    goto LABEL_10;
  if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value) )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v14->value, a5, a7);
LABEL_10:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v17);
    v18 = (int)v48;
    goto LABEL_14;
  }
  v71 = 0;
  v72 = 0;
  v49 = 0;
  SubsystemType = WspGetSubsystemType(v14->value);
  SubsystemVersion = _GetSubsystemVersion(&v49);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v71);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v46 = SubsystemVersion != v49;
    LOWORD(v49) = v72;
    v45 = SubsystemType;
    p_self = (const char *)&v71;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v25,
      (unsigned int)&word_18035300E,
      v26,
      v27,
      (__int64)&p_self,
      (__int64)&v45,
      (__int64)&v49,
      (__int64)&v46);
  }
  if ( !a7 )
  {
    v28 = MI_RESULT_INVALID_PARAMETER;
LABEL_28:
    v18 = (int)v48;
    goto LABEL_29;
  }
  v32 = WspUnpackObjectId((unsigned __int16 *)v14->value);
  v28 = v32;
  if ( v32 )
  {
    v35 = dword_180397B68;
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v45 = v32;
      v46 = 848;
      v36 = &dword_180353B4C;
LABEL_36:
      p_self = "WSP_Disk_Invoke_CreatePartition";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v35,
        (_DWORD)v36,
        v33,
        v34,
        (__int64)&p_self,
        (__int64)&v46,
        (__int64)&v45);
      v13 = lpFileName;
      v18 = (int)v48;
      goto LABEL_29;
    }
    goto LABEL_40;
  }
  v28 = MI_Context_ConstructParameters(a2, &WSP_Disk_CreatePartition_rtti, &instance);
  if ( v28 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v45 = v28;
      v46 = 856;
      v36 = (int *)byte_180352AD1;
      goto LABEL_36;
    }
LABEL_40:
    v13 = lpFileName;
    goto LABEL_28;
  }
  Partition = WspParseCreatePartitionParameters(a7, &v75);
  v13 = lpFileName;
  if ( Partition )
  {
    v18 = (int)v48;
    goto LABEL_62;
  }
  if ( (_DWORD)v58 )
  {
    Partition = PmcCreatePartition(lpFileName, &v75, &v53, &hMem);
    v18 = (int)v48;
    if ( Partition )
      goto LABEL_62;
    v41 = v53;
    *((_BYTE *)v53 + 76) = 0;
    *(_WORD *)((char *)v41 + 77) = *(_WORD *)((char *)&p_self + 1);
    *((_BYTE *)v41 + 79) = BYTE3(p_self);
    *((_DWORD *)v41 + 20) = 0;
    if ( !v18 && (unsigned int)PmGetDiskNumber(v13, &v50) )
    {
      v42 = v53;
      *((_DWORD *)v53 + 20) = v50;
      *((_BYTE *)v42 + 76) = 1;
    }
    PmcRefreshDisk(v13);
  }
  else
  {
    Partition = PmCreatePartition((unsigned __int16 *)lpFileName);
    v18 = (int)v48;
    if ( Partition )
      goto LABEL_62;
  }
  if ( !a2 || !a2->ft )
  {
    v28 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_58;
  }
  v28 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
          a2,
          &WSP_Partition_rtti,
          &v69);
  if ( v28 )
  {
LABEL_58:
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_29;
    v46 = 909;
    v43 = byte_1803524A9;
    goto LABEL_60;
  }
  if ( WSP_Partition_PopulateMIStructure(v53, 0, (struct _WSP_Partition *)&v69) == MI_RESULT_OK )
  {
    p_self = (const char *)&v69;
    v28 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const char **, _QWORD, enum _MI_Result))instance.ft->SetElementAt)(
            &instance,
            (unsigned int)(v28 + 11),
            &p_self,
            (unsigned int)(v28 + 15),
            v28);
    if ( v28 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_29;
      v46 = 921;
      v43 = (char *)&unk_180353858;
      goto LABEL_60;
    }
  }
LABEL_62:
  v65.value = Partition;
  v65.exists = 1;
  if ( !hMem )
    goto LABEL_73;
  if ( a2 && a2->ft )
  {
    v28 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
            a2,
            &MSFT_StorageExtendedStatus_rtti,
            &self);
    if ( v28 == MI_RESULT_OK )
    {
      if ( (unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(
                           (struct _SUEX_EXTENDEDSTATUS_OBJECT *)hMem,
                           (struct _MSFT_StorageExtendedStatus *)&self) )
      {
        p_self = (const char *)&self;
        v28 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const char **, _QWORD, enum _MI_Result))instance.ft->SetElementAt)(
                &instance,
                (unsigned int)(v28 + 12),
                &p_self,
                (unsigned int)(v28 + 15),
                v28);
        if ( v28 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            v46 = 952;
            v43 = (char *)&word_180352DEE;
LABEL_60:
            p_self = "WSP_Disk_Invoke_CreatePartition";
            v45 = v28;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v37,
              (_DWORD)v43,
              v39,
              v40,
              (__int64)&p_self,
              (__int64)&v46,
              (__int64)&v45);
            goto LABEL_29;
          }
          goto LABEL_29;
        }
      }
LABEL_73:
      v28 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v28 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_29;
      v46 = 962;
      v43 = byte_180352C8D;
      goto LABEL_60;
    }
  }
  else
  {
    v28 = MI_RESULT_INVALID_PARAMETER;
  }
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v46 = 942;
    v43 = &byte_180351CF7;
    goto LABEL_60;
  }
LABEL_29:
  CSmTimer::Stop((CSmTimer *)&v59);
  SmLogOnMethodFailure(v57, v56, v14, &v65, v28, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v57 = 0;
    if ( v67 )
    {
      v62 = *v66;
      v31 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v62, 0);
    }
    else
    {
      v31 = 0;
    }
    v56 = v31;
    p_self = "WspPartition";
    lpFileName = (LPCWSTR)(1000 * (v60 - v59) / v61);
    v45 = v28;
    v46 = v65.exists != 0 ? v65.value : 0;
    v50 = v15;
    if ( *(_BYTE *)(v54 + 72) )
      v44 = v14->value;
    else
      v44 = 0;
    v54 = (unsigned __int64)v44;
    v58 = "CreatePartition";
    v48 = "WspDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v65.exists != 0 ? v65.value : 0,
      (unsigned int)&byte_1803517EF,
      v29,
      v30,
      (__int64)&v48,
      (__int64)&v58,
      (__int64)&v54,
      (__int64)&v50,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&lpFileName,
      (__int64)&p_self,
      (__int64)&v56,
      (__int64)&v57);
  }
  WspFreeString(v13);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&v69);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v28);
LABEL_14:
  WspProviderExit(v51, v17);
  if ( v18 )
  {
    CSmTimer::Stop((CSmTimer *)&v59);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        v54 = 1000 * (v60 - v59) / v61;
        v45 = v15;
        v57 = (unsigned __int16 *)"CreatePartition";
        v56 = (unsigned __int16 *)"WspDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v19,
          (unsigned int)byte_180351E7B,
          v20,
          v21,
          (__int64)&v56,
          (__int64)&v57,
          (__int64)&v45,
          (__int64)&v54);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v45 = 1013;
    v54 = (unsigned __int64)"WSP_Disk_Invoke_CreatePartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_1803529B3,
      v20,
      v21,
      (__int64)&v54,
      (__int64)&v45);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v59);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
  return EventActivityIdControl(4u, &v74);
}

```

## disassembly

```asm
0x18014f320  mov     [rsp-8+arg_0], rbx
0x18014f325  push    rbp
0x18014f326  push    rsi
0x18014f327  push    rdi
0x18014f328  push    r12
0x18014f32a  push    r13
0x18014f32c  push    r14
0x18014f32e  push    r15
0x18014f330  lea     rbp, [rsp-420h]
0x18014f338  sub     rsp, 520h
0x18014f33f  mov     rax, cs:__security_cookie
0x18014f346  xor     rax, rsp
0x18014f349  mov     [rbp+450h+var_40], rax
0x18014f350  mov     rbx, r9
0x18014f353  mov     [rbp+450h+var_490], rbx
0x18014f357  mov     rdi, rdx
0x18014f35a  mov     r15, [rbp+450h+arg_20]
0x18014f361  mov     [rbp+450h+var_498], r15
0x18014f365  mov     r13, [rbp+450h+arg_28]
0x18014f36c  mov     [rbp+450h+var_4A8], r13
0x18014f370  mov     rsi, [rbp+450h+arg_30]
0x18014f377  xorps   xmm0, xmm0
0x18014f37a  xor     eax, eax
0x18014f37c  movups  xmmword ptr [rbp+450h+value], xmm0
0x18014f380  movups  xmmword ptr [rbp+450h+value+10h], xmm0
0x18014f384  mov     qword ptr [rbp+450h+value+20h], rax
0x18014f388  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014f38f  movdqu  xmmword ptr [rbp+450h+ActivityId.Data1], xmm0
0x18014f397  lea     rdx, [rbp+450h+ActivityId]; ActivityId
0x18014f39e  lea     ecx, [rax+1]; ControlCode
0x18014f3a1  call    cs:__imp_EventActivityIdControl
0x18014f3a7  lea     r9, [rbp+450h+value]; value
0x18014f3ab  mov     rcx, rdi; context
0x18014f3ae  call    MI_Context_GetCustomOption_1
0x18014f3b3  xor     r12d, r12d
0x18014f3b6  test    eax, eax
0x18014f3b8  jnz     short loc_18014F3CB
0x18014f3ba  lea     rdx, [rbp+450h+ActivityId]; pclsid
0x18014f3c1  mov     rcx, qword ptr [rbp+450h+value]; lpsz
0x18014f3c5  call    cs:__imp_CLSIDFromString
0x18014f3cb  mov     rcx, qword ptr [rbp+450h+ActivityId.Data1]
0x18014f3d2  mov     [rbp+450h+var_A8], rcx
0x18014f3d9  mov     rax, qword ptr [rbp+450h+ActivityId.Data4]
0x18014f3e0  mov     [rbp+450h+var_A0], rax
0x18014f3e7  mov     qword ptr [rbp+450h+var_98.Data1], rcx
0x18014f3ee  mov     qword ptr [rbp+450h+var_98.Data4], rax
0x18014f3f5  lea     rdx, [rbp+450h+var_98]; ActivityId
0x18014f3fc  mov     ecx, 4; ControlCode
0x18014f401  call    cs:__imp_EventActivityIdControl
0x18014f407  mov     eax, cs:dword_180397B68
0x18014f40d  lea     rcx, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x18014f414  cmp     eax, 5
0x18014f417  jbe     short loc_18014F442
0x18014f419  mov     [rbp+450h+var_4C0], 327h
0x18014f420  mov     [rbp+450h+lpFileName], rcx
0x18014f424  lea     rax, [rbp+450h+var_4C0]
0x18014f428  mov     [rsp+550h+var_528], rax
0x18014f42d  lea     rax, [rbp+450h+lpFileName]
0x18014f431  mov     qword ptr [rsp+550h+var_530], rax
0x18014f436  lea     rdx, byte_18035378B
0x18014f43d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014f442  mov     r14, r12
0x18014f445  mov     [rbp+450h+lpFileName], r12
0x18014f449  mov     dword ptr [rbp+450h+var_488], r12d
0x18014f44d  mov     [rbp+450h+instance.ft], r12
0x18014f451  xor     edx, edx; Val
0x18014f453  mov     r8d, 0B8h; Size
0x18014f459  lea     rcx, [rbp+450h+instance.classDecl]; void *
0x18014f45d  call    memset_0
0x18014f462  mov     [rbp+450h+var_220.ft], r12
0x18014f469  xor     edx, edx; Val
0x18014f46b  mov     r8d, 148h; Size
0x18014f471  lea     rcx, [rbp+450h+var_220.classDecl]; void *
0x18014f478  call    memset_0
0x18014f47d  xorps   xmm0, xmm0
0x18014f480  xor     eax, eax
0x18014f482  movups  [rbp+450h+var_80], xmm0
0x18014f489  mov     [rbp+450h+var_70], eax
0x18014f48f  mov     [rbp+450h+var_6C], r12b
0x18014f496  mov     [rbp+450h+var_6A], r12w
0x18014f49e  movups  [rbp+450h+var_68], xmm0
0x18014f4a5  movups  [rbp+450h+var_58], xmm0
0x18014f4ac  mov     [rbp+450h+var_48], rax
0x18014f4b3  mov     [rbp+450h+var_4B0], r12
0x18014f4b7  lea     rcx, [rbp+450h+var_4B0]
0x18014f4bb  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18014f4c0  mov     [rbp+450h+var_4B0], r12
0x18014f4c4  mov     [rbp+450h+var_4C4], r12d
0x18014f4c8  lea     rcx, [rbp+450h+var_480]; this
0x18014f4cc  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014f4d1  mov     [rbp+450h+hMem], r12
0x18014f4d5  mov     [rbp+450h+self.ft], r12
0x18014f4dc  xor     edx, edx; Val
0x18014f4de  mov     r8d, 108h; Size
0x18014f4e4  lea     rcx, [rbp+450h+self.classDecl]; void *
0x18014f4eb  call    memset_0
0x18014f4f0  lea     rcx, [rbp+450h+var_480]; this
0x18014f4f4  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014f4f9  mov     rcx, rdi; context
0x18014f4fc  call    WspIsRemoteRequest
0x18014f501  mov     dword ptr [rbp+450h+var_4D0], eax
0x18014f504  lea     r12, [r13+40h]
0x18014f508  cmp     byte ptr [r12+8], 0
0x18014f50e  jz      short loc_18014F525
0x18014f510  mov     rcx, [r12]; unsigned __int16 *
0x18014f514  call    WspIsRemoteInstance
0x18014f519  test    al, al
0x18014f51b  jz      short loc_18014F525
0x18014f51d  mov     r13d, 1
0x18014f523  jmp     short loc_18014F528
0x18014f525  xor     r13d, r13d
0x18014f528  mov     [rbp+450h+var_4C0], 0
0x18014f52f  lea     r9, [rbp+450h+var_4C0]
0x18014f533  mov     r8d, 1
0x18014f539  mov     rdx, [r12]
0x18014f53d  mov     rcx, rdi; context
0x18014f540  call    WspProviderEnter
0x18014f545  mov     edx, eax
0x18014f547  test    eax, eax
0x18014f549  jz      loc_18014F69A
0x18014f54f  test    rdi, rdi
0x18014f552  jz      short loc_18014F567
0x18014f554  mov     rax, [rdi]
0x18014f557  test    rax, rax
0x18014f55a  jz      short loc_18014F567
0x18014f55c  mov     rcx, rdi
0x18014f55f  mov     rax, [rax]
0x18014f562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f567  lea     r12, aCreatepartitio_0; "CreatePartition"
0x18014f56e  lea     rsi, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x18014f575  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x18014f579  mov     ecx, [rbp+450h+var_4C0]
0x18014f57c  call    WspProviderExit
0x18014f581  test    r15d, r15d
0x18014f584  jz      loc_18014F616
0x18014f58a  lea     rcx, [rbp+450h+var_480]; this
0x18014f58e  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014f593  mov     eax, cs:dword_180397B68
0x18014f599  cmp     eax, 5
0x18014f59c  jbe     short loc_18014F616
0x18014f59e  mov     rdx, 400000000000h
0x18014f5a8  lea     rcx, dword_180397B68
0x18014f5af  call    _tlgKeywordOn
0x18014f5b4  test    al, al
0x18014f5b6  jz      short loc_18014F616
0x18014f5b8  mov     rax, [rbp+450h+var_478]
0x18014f5bc  sub     rax, [rbp+450h+var_480]
0x18014f5c0  imul    rax, 3E8h
0x18014f5c7  xor     edx, edx
0x18014f5c9  div     [rbp+450h+var_470]
0x18014f5cd  mov     [rbp+450h+var_4A8], rax
0x18014f5d1  mov     [rsp+550h+var_4E0], r13d
0x18014f5d6  mov     [rbp+450h+var_490], r12
0x18014f5da  lea     rax, aWspdisk; "WspDisk"
0x18014f5e1  mov     [rbp+450h+var_498], rax
0x18014f5e5  lea     rax, [rbp+450h+var_4A8]
0x18014f5e9  mov     [rsp+550h+var_518], rax
0x18014f5ee  lea     rax, [rsp+550h+var_4E0]
0x18014f5f3  mov     [rsp+550h+var_520], rax
0x18014f5f8  lea     rax, [rbp+450h+var_490]
0x18014f5fc  mov     [rsp+550h+var_528], rax
0x18014f601  lea     rax, [rbp+450h+var_498]
0x18014f605  mov     qword ptr [rsp+550h+var_530], rax
0x18014f60a  lea     rdx, byte_180351E7B
0x18014f611  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18014f616  mov     eax, cs:dword_180397B68
0x18014f61c  cmp     eax, 5
0x18014f61f  jbe     short loc_18014F64C
0x18014f621  mov     [rsp+550h+var_4E0], 3F5h
0x18014f629  mov     [rbp+450h+var_4A8], rsi
0x18014f62d  lea     rax, [rsp+550h+var_4E0]
0x18014f632  mov     [rsp+550h+var_528], rax
0x18014f637  lea     rax, [rbp+450h+var_4A8]
0x18014f63b  mov     qword ptr [rsp+550h+var_530], rax
0x18014f640  lea     rdx, byte_1803529B3
0x18014f647  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014f64c  lea     rcx, [rbp+450h+var_480]; this
0x18014f650  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18014f655  lea     rcx, [rbp+450h+var_4B0]
0x18014f659  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18014f65e  lea     rdx, [rbp+450h+var_98]; ActivityId
0x18014f665  mov     ecx, 4; ControlCode
0x18014f66a  call    cs:__imp_EventActivityIdControl
0x18014f670  mov     rcx, [rbp+450h+var_40]
0x18014f677  xor     rcx, rsp; StackCookie
0x18014f67a  call    __security_check_cookie
0x18014f67f  mov     rbx, [rsp+550h+arg_0]
0x18014f687  add     rsp, 520h
0x18014f68e  pop     r15
0x18014f690  pop     r14
0x18014f692  pop     r13
0x18014f694  pop     r12
0x18014f696  pop     rdi
0x18014f697  pop     rsi
0x18014f698  pop     rbp
0x18014f699  retn
0x18014f69a  mov     rcx, [r12]; unsigned __int16 *
0x18014f69e  call    WspIsRemoteInstance
0x18014f6a3  test    al, al
0x18014f6a5  jz      short loc_18014F6C5
0x18014f6a7  mov     qword ptr [rsp+550h+var_530], rsi; void *
0x18014f6ac  mov     r9, r15; unsigned __int16 *
0x18014f6af  mov     r8, [r12]; unsigned __int16 *
0x18014f6b3  mov     rdx, rbx; unsigned __int16 *
0x18014f6b6  mov     rcx, rdi; struct _MI_Context *
0x18014f6b9  call    WspInvokeRemoteMethod
0x18014f6be  mov     edx, eax
0x18014f6c0  jmp     loc_18014F54F
0x18014f6c5  xorps   xmm0, xmm0
0x18014f6c8  xor     eax, eax
0x18014f6ca  movups  [rbp+450h+var_C0], xmm0
0x18014f6d1  mov     [rbp+450h+var_B0], eax
0x18014f6d7  mov     [rbp+450h+var_4C8], eax
0x18014f6da  mov     rcx, [r12]
0x18014f6de  call    WspGetSubsystemType
0x18014f6e3  mov     ebx, eax
0x18014f6e5  lea     rcx, [rbp+450h+var_4C8]
0x18014f6e9  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18014f6ee  mov     r15d, eax
0x18014f6f1  lea     rdx, [rbp+450h+var_C0]; struct _SUBSYSTEM_INFO *
0x18014f6f8  mov     ecx, ebx; unsigned int
0x18014f6fa  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18014f6ff  mov     ecx, cs:dword_180397B68
0x18014f705  cmp     ecx, 5
0x18014f708  jbe     short loc_18014F77F
0x18014f70a  mov     rdx, 400000000000h
0x18014f714  lea     rcx, dword_180397B68
0x18014f71b  call    _tlgKeywordOn
0x18014f720  test    al, al
0x18014f722  jz      short loc_18014F77F
0x18014f724  xor     eax, eax
0x18014f726  cmp     r15d, [rbp+450h+var_4C8]
0x18014f72a  setnz   al
0x18014f72d  mov     [rsp+550h+var_4DC], eax
0x18014f731  movzx   eax, word ptr [rbp+450h+var_B0]
0x18014f738  mov     word ptr [rbp+450h+var_4C8], ax
0x18014f73c  mov     [rsp+550h+var_4E0], ebx
0x18014f740  lea     rax, [rbp+450h+var_C0]
0x18014f747  mov     [rsp+550h+var_4D8], rax
0x18014f74c  lea     rax, [rsp+550h+var_4DC]
0x18014f751  mov     [rsp+550h+var_518], rax
0x18014f756  lea     rax, [rbp+450h+var_4C8]
0x18014f75a  mov     [rsp+550h+var_520], rax
0x18014f75f  lea     rax, [rsp+550h+var_4E0]
0x18014f764  mov     [rsp+550h+var_528], rax
0x18014f769  lea     rax, [rsp+550h+var_4D8]
0x18014f76e  mov     qword ptr [rsp+550h+var_530], rax
0x18014f773  lea     rdx, word_18035300E
0x18014f77a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18014f77f  test    rsi, rsi
0x18014f782  jnz     loc_18014F843
0x18014f788  lea     ebx, [rsi+4]
0x18014f78b  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x18014f78f  lea     rsi, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x18014f796  lea     rcx, [rbp+450h+var_480]; this
0x18014f79a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014f79f  mov     [rsp+550h+var_528], 0; unsigned __int16 *
0x18014f7a8  mov     [rsp+550h+var_530], ebx; enum _MI_Result
0x18014f7ac  lea     r9, [rbp+450h+var_3B0]; struct _MI_ConstUint32Field *
0x18014f7b3  mov     r8, r12; struct _MI_ConstStringField *
0x18014f7b6  mov     rdx, [rbp+450h+var_498]; unsigned __int16 *
0x18014f7ba  mov     rcx, [rbp+450h+var_490]; unsigned __int16 *
0x18014f7be  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18014f7c3  mov     eax, cs:dword_180397B68
0x18014f7c9  cmp     eax, 5
0x18014f7cc  jbe     loc_18014FC97
0x18014f7d2  mov     rdx, 400000000000h
0x18014f7dc  lea     rcx, dword_180397B68
0x18014f7e3  call    _tlgKeywordOn
0x18014f7e8  test    al, al
0x18014f7ea  jz      loc_18014FC97
0x18014f7f0  mov     [rbp+450h+var_490], 0
0x18014f7f8  cmp     [rbp+450h+var_348], 0
0x18014f7ff  jz      loc_18014FBB9
0x18014f805  mov     rax, [rbp+450h+var_350]
0x18014f80c  movups  xmm0, xmmword ptr [rax]
0x18014f80f  movaps  xmmword ptr [rbp+450h+var_460.ft], xmm0
0x18014f813  movups  xmm1, xmmword ptr [rax+10h]
0x18014f817  movaps  xmmword ptr [rbp+450h+var_460.serverName], xmm1
0x18014f81b  movups  xmm0, xmmword ptr [rax+20h]
0x18014f81f  movaps  xmmword ptr [rbp+450h+var_460.reserved], xmm0
0x18014f823  movups  xmm1, xmmword ptr [rax+30h]
0x18014f827  movaps  xmmword ptr [rbp+450h+var_460.reserved+10h], xmm1
0x18014f82b  xor     r8d, r8d; unsigned __int16 *
0x18014f82e  lea     rdx, [rbp+450h+var_460]; struct _MI_Instance
0x18014f832  lea     rcx, name; "ObjectId"
0x18014f839  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18014f83e  jmp     loc_18014FBBB
0x18014f843  lea     r9, [rbp+450h+lpFileName]
0x18014f847  lea     r8, [rsp+550h+var_4E0]
0x18014f84c  lea     rdx, [rbp+450h+var_488]
0x18014f850  mov     rcx, [r12]; unsigned __int16 *
0x18014f854  call    WspUnpackObjectId
0x18014f859  mov     ebx, eax
0x18014f85b  test    eax, eax
0x18014f85d  jz      short loc_18014F8BD
0x18014f85f  mov     ecx, cs:dword_180397B68
0x18014f865  cmp     ecx, 2
0x18014f868  jbe     loc_18014F8F6
0x18014f86e  mov     [rsp+550h+var_4E0], eax
  ... truncated ...
```
