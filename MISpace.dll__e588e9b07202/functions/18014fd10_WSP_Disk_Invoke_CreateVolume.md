# WSP_Disk_Invoke_CreateVolume

- ea: `0x18014fd10`
- end: `0x180150571`
- name: `WSP_Disk_Invoke_CreateVolume`
- size: `2145`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
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
- `0x1800167e0`
- `0x180016c80`
- `0x1800234e4`
- `0x18007ea44`
- `0x18007ed50`
- `0x18007f6b4`
- `0x180137a24`
- `0x180138120`
- `0x18014d9b8`
- `0x18014fd10`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014fd85`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014fde5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ffd1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014fd85`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014fde5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ffd1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014fda9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014fda9`

## string_xrefs

- `0x18014fedb`: `CreateVolume`
- `0x180150496`: `CreateVolume`
- `0x180150517`: `CreateVolume`
- `0x180150274`: `Create Volume`
- `0x18014fdf1`: `WSP_Disk_Invoke_CreateVolume`
- `0x18014fee2`: `WSP_Disk_Invoke_CreateVolume`
- `0x1801500f4`: `WSP_Disk_Invoke_CreateVolume`
- `0x1801501c7`: `WSP_Disk_Invoke_CreateVolume`
- `0x18015044c`: `WSP_Disk_Invoke_CreateVolume`
- `0x180150477`: `WSP_Disk_Invoke_CreateVolume`

## pseudocode

```c
ULONG __fastcall WSP_Disk_Invoke_CreateVolume(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        void *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r12d
  int v12; // r8d
  int v13; // r9d
  int IsRemoteRequest; // r13d
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  char IsRemoteInstance; // al
  __int64 v23; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  unsigned int v29; // ebx
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rax
  unsigned int v33; // eax
  int v34; // r8d
  int v35; // r9d
  int v36; // ecx
  char *v37; // rdx
  unsigned int v38; // ebx
  int v39; // eax
  int v40; // esi
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  __int16 *v44; // rdx
  int v45; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int v47; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v48; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  const char *v51; // [rsp+98h] [rbp-68h] BYREF
  void *Block; // [rsp+A0h] [rbp-60h] BYREF
  const char *v53; // [rsp+A8h] [rbp-58h] BYREF
  const char *v54; // [rsp+B0h] [rbp-50h] BYREF
  const char *v55; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v58; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v59; // [rsp+E0h] [rbp-20h] BYREF
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  int v62; // [rsp+150h] [rbp+50h]
  char v63; // [rsp+154h] [rbp+54h]
  MI_Instance self; // [rsp+1C0h] [rbp+C0h] BYREF
  GUID ActivityId; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v66; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v67; // [rsp+2F0h] [rbp+1F0h]
  GUID v68; // [rsp+2F8h] [rbp+1F8h]
  GUID v69; // [rsp+308h] [rbp+208h] BYREF
  __int128 v70; // [rsp+320h] [rbp+220h] BYREF
  __int64 v71; // [rsp+330h] [rbp+230h]
  __int16 v72; // [rsp+338h] [rbp+238h]
  __int64 v73; // [rsp+340h] [rbp+240h]
  __int64 v74; // [rsp+348h] [rbp+248h]
  int v75; // [rsp+350h] [rbp+250h]
  _BYTE v76[64]; // [rsp+354h] [rbp+254h] BYREF
  int v77; // [rsp+394h] [rbp+294h]

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v68 = ActivityId;
  v69 = ActivityId;
  EventActivityIdControl(4u, &v69);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v48 = 2251;
    v53 = "WSP_Disk_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Disk_Invoke_CreateVolume",
      (unsigned int)&byte_18035250F,
      v12,
      v13,
      (__int64)&v53,
      (__int64)&v48);
  }
  v53 = 0;
  LODWORD(v49) = 0;
  v47 = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xA0u);
  Block = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v56);
  CSmTimer::Start((CSmTimer *)&v56);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( *(_BYTE *)(a6 + 72) && (unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64)) )
    v11 = 1;
  v15 = *(_QWORD *)(a6 + 64);
  v48 = 0;
  v16 = WspProviderEnter(a2, v15, 1u, &v48);
  v17 = v16;
  if ( v16 )
    goto LABEL_9;
  IsRemoteInstance = WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64));
  v23 = *(_QWORD *)(a6 + 64);
  if ( IsRemoteInstance )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(unsigned __int16 **)(a6 + 64), a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(struct _MI_Context *, __int64))a2->ft->PostResult)(a2, v17);
    goto LABEL_12;
  }
  v66 = 0;
  v67 = 0;
  LODWORD(v50) = 0;
  SubsystemType = WspGetSubsystemType(v23);
  SubsystemVersion = _GetSubsystemVersion(&v50);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v66);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v45 = SubsystemType;
    *(_DWORD *)v46 = SubsystemVersion != v50;
    LOWORD(v50) = v67;
    *(_QWORD *)&v46[4] = &v66;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v26,
      (unsigned int)&byte_180352447,
      v27,
      v28,
      (__int64)&v46[4],
      (__int64)&v45,
      (__int64)&v50,
      (__int64)v46);
  }
  if ( !a7 )
  {
    v29 = 4;
    goto LABEL_26;
  }
  v33 = WspUnpackObjectId(*(unsigned __int16 **)(a6 + 64));
  v29 = v33;
  if ( v33 )
  {
    v36 = dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v45 = v33;
    v37 = byte_1803532DD;
    *(_DWORD *)v46 = 2288;
    goto LABEL_33;
  }
  v29 = MI_Context_ConstructParameters(a2, &WSP_Disk_CreateVolume_rtti, &instance);
  if ( v29 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v45 = v29;
      v37 = (char *)&unk_180351D30;
      *(_DWORD *)v46 = 2296;
LABEL_33:
      *(_QWORD *)&v46[4] = "WSP_Disk_Invoke_CreateVolume";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v36,
        (_DWORD)v37,
        v34,
        v35,
        (__int64)&v46[4],
        (__int64)v46,
        (__int64)&v45);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v38 = v49;
  v39 = WspParseCreateVolumeParameters(a2, a7, (unsigned int)v49, &Block);
  LODWORD(v49) = v39;
  v40 = v39;
  if ( v39 )
  {
    if ( v39 != 43001 )
      goto LABEL_42;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v70 = 0;
    v74 = 0;
    v75 = 16;
    v77 = 0;
    memset_0(v76, 0, sizeof(v76));
    CSpExtendedStatus::Initialize((CSpExtendedStatus *)&v70, 0x8011u, 0);
    if ( a2 && a2->ft )
    {
      v29 = ((__int64 (__fastcall *)(struct _MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
              a2,
              &MSFT_StorageExtendedStatus_rtti,
              &self);
      if ( !v29 )
      {
        if ( (unsigned int)CSpExtendedStatus::ToMsftExtendedStatus(
                             (CSpExtendedStatus *)&v70,
                             (struct _MSFT_StorageExtendedStatus *)&self) )
        {
          *(_QWORD *)&v46[4] = &self;
          v29 = ((__int64 (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _DWORD))instance.ft->SetElementAt)(
                  &instance,
                  v29 + 7,
                  &v46[4],
                  v29 + 15,
                  0);
          if ( v29 )
          {
            if ( (unsigned int)dword_180397B68 > 2 )
            {
              *(_DWORD *)v46 = 2345;
              v44 = &word_180351CBE;
LABEL_57:
              *(_QWORD *)&v46[4] = "WSP_Disk_Invoke_CreateVolume";
              v45 = v29;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v41,
                (_DWORD)v44,
                v42,
                v43,
                (__int64)&v46[4],
                (__int64)v46,
                (__int64)&v45);
              goto LABEL_58;
            }
            goto LABEL_58;
          }
        }
        CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)&v70);
LABEL_42:
        v62 = v40;
        v63 = 1;
        v29 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( !v29 || (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_26;
        v45 = v29;
        v37 = (char *)&unk_180351B78;
        *(_DWORD *)v46 = 2363;
        goto LABEL_33;
      }
    }
    else
    {
      v29 = 4;
    }
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      *(_DWORD *)v46 = 2335;
      v44 = (__int16 *)byte_180353219;
      goto LABEL_57;
    }
LABEL_58:
    CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)&v70);
    goto LABEL_26;
  }
  v29 = WspRunMethodAsJob(
          a2,
          (__int64)L"Create Volume",
          4u,
          (__int64)WSP_Disk_Invoke_CreateVolume_Async,
          (__int64)Block,
          v38,
          v47,
          *(_QWORD *)(a6 + 64),
          &instance,
          &v49);
  if ( !v29 )
  {
    v40 = v49;
    Block = 0;
    goto LABEL_42;
  }
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v45 = v29;
    v37 = (char *)&unk_180353408;
    *(_DWORD *)v46 = 2320;
    goto LABEL_33;
  }
LABEL_26:
  CSmTimer::Stop((CSmTimer *)&v56);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    *(_DWORD *)&v46[8] = 0;
    v49 = 0;
    v59 = 1000 * (v57 - v56) / v58;
    v50 = 0;
    v45 = v29;
    v47 = v11;
    *(_QWORD *)v46 = v62 & (unsigned int)-(v63 != 0);
    if ( *(_BYTE *)(a6 + 72) )
      v32 = *(const char **)(a6 + 64);
    else
      v32 = 0;
    v54 = v32;
    v55 = "CreateVolume";
    v51 = "WspDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v63 != 0 ? v62 : 0,
      (unsigned int)byte_180351FB1,
      v30,
      v31,
      (__int64)&v51,
      (__int64)&v55,
      (__int64)&v54,
      (__int64)&v47,
      (__int64)v46,
      (__int64)&v45,
      (__int64)&v59,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v46[4]);
  }
  WspFreeString(v53);
  if ( Block )
    operator delete(Block);
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a2->ft->PostResult)(a2, v29);
LABEL_12:
  WspProviderExit(v48, v17);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v56);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        v45 = v11;
        v55 = "CreateVolume";
        v51 = (const char *)(1000 * (v57 - v56) / v58);
        v54 = "WspDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v18,
          (unsigned int)word_1803522CA,
          v19,
          v20,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v45,
          (__int64)&v51);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v45 = 2407;
    v51 = "WSP_Disk_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&word_180353DD6,
      v19,
      v20,
      (__int64)&v51,
      (__int64)&v45);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v56);
  return EventActivityIdControl(4u, &v69);
}

```

## disassembly

```asm
0x18014fd10  mov     [rsp-8+arg_0], rbx
0x18014fd15  push    rbp
0x18014fd16  push    rsi
0x18014fd17  push    rdi
0x18014fd18  push    r12
0x18014fd1a  push    r13
0x18014fd1c  push    r14
0x18014fd1e  push    r15
0x18014fd20  lea     rbp, [rsp-2B0h]
0x18014fd28  sub     rsp, 3B0h
0x18014fd2f  mov     rax, cs:__security_cookie
0x18014fd36  xor     rax, rsp
0x18014fd39  mov     [rbp+2E0h+var_40], rax
0x18014fd40  mov     r15, [rbp+2E0h+arg_20]
0x18014fd47  xorps   xmm0, xmm0
0x18014fd4a  mov     r14, [rbp+2E0h+arg_28]
0x18014fd51  xor     eax, eax
0x18014fd53  mov     rsi, [rbp+2E0h+arg_30]
0x18014fd5a  mov     rdi, rdx
0x18014fd5d  movups  xmmword ptr [rbp+2E0h+value], xmm0
0x18014fd61  lea     rdx, [rbp+2E0h+ActivityId]; ActivityId
0x18014fd68  mov     rbx, r9
0x18014fd6b  movups  xmmword ptr [rbp+2E0h+value+10h], xmm0
0x18014fd6f  lea     ecx, [rax+1]; ControlCode
0x18014fd72  mov     qword ptr [rbp+2E0h+value+20h], rax
0x18014fd76  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014fd7d  movdqu  xmmword ptr [rbp+2E0h+ActivityId.Data1], xmm0
0x18014fd85  call    cs:__imp_EventActivityIdControl
0x18014fd8b  lea     r9, [rbp+2E0h+value]; value
0x18014fd8f  mov     rcx, rdi; context
0x18014fd92  call    MI_Context_GetCustomOption_1
0x18014fd97  xor     r12d, r12d
0x18014fd9a  test    eax, eax
0x18014fd9c  jnz     short loc_18014FDAF
0x18014fd9e  mov     rcx, qword ptr [rbp+2E0h+value]; lpsz
0x18014fda2  lea     rdx, [rbp+2E0h+ActivityId]; pclsid
0x18014fda9  call    cs:__imp_CLSIDFromString
0x18014fdaf  mov     rcx, qword ptr [rbp+2E0h+ActivityId.Data1]
0x18014fdb6  lea     rdx, [rbp+2E0h+var_D8]; ActivityId
0x18014fdbd  mov     rax, qword ptr [rbp+2E0h+ActivityId.Data4]
0x18014fdc4  mov     [rbp+2E0h+var_E8], rcx
0x18014fdcb  mov     qword ptr [rbp+2E0h+var_D8.Data1], rcx
0x18014fdd2  mov     ecx, 4; ControlCode
0x18014fdd7  mov     [rbp+2E0h+var_E0], rax
0x18014fdde  mov     qword ptr [rbp+2E0h+var_D8.Data4], rax
0x18014fde5  call    cs:__imp_EventActivityIdControl
0x18014fdeb  mov     eax, cs:dword_180397B68
0x18014fdf1  lea     rcx, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x18014fdf8  cmp     eax, 5
0x18014fdfb  jbe     short loc_18014FE26
0x18014fdfd  lea     rax, [rbp+2E0h+var_35C]
0x18014fe01  mov     [rbp+2E0h+var_35C], 8CBh
0x18014fe08  mov     qword ptr [rsp+3E0h+var_3B8], rax
0x18014fe0d  lea     rdx, byte_18035250F
0x18014fe14  lea     rax, [rbp+2E0h+var_338]
0x18014fe18  mov     [rbp+2E0h+var_338], rcx
0x18014fe1c  mov     [rsp+3E0h+var_3C0], rax
0x18014fe21  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014fe26  xor     edx, edx; Val
0x18014fe28  mov     [rbp+2E0h+var_338], r12
0x18014fe2c  mov     r8d, 108h; Size
0x18014fe32  mov     dword ptr [rbp+2E0h+var_358], r12d
0x18014fe36  lea     rcx, [rbp+2E0h+self.classDecl]; void *
0x18014fe3d  mov     [rbp+2E0h+var_360], r12d
0x18014fe41  mov     [rbp+2E0h+self.ft], r12
0x18014fe48  call    memset_0
0x18014fe4d  xor     edx, edx; Val
0x18014fe4f  mov     [rbp+2E0h+instance.ft], r12
0x18014fe53  mov     r8d, 0A0h; Size
0x18014fe59  lea     rcx, [rbp+2E0h+instance.classDecl]; void *
0x18014fe5d  call    memset_0
0x18014fe62  lea     rcx, [rbp+2E0h+var_320]; this
0x18014fe66  mov     [rbp+2E0h+Block], r12
0x18014fe6a  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014fe6f  lea     rcx, [rbp+2E0h+var_320]; this
0x18014fe73  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014fe78  mov     rcx, rdi; context
0x18014fe7b  call    WspIsRemoteRequest
0x18014fe80  mov     r13d, eax
0x18014fe83  cmp     [r14+48h], r12b
0x18014fe87  jz      short loc_18014FE9C
0x18014fe89  mov     rcx, [r14+40h]; unsigned __int16 *
0x18014fe8d  call    WspIsRemoteInstance
0x18014fe92  test    al, al
0x18014fe94  jz      short loc_18014FE9C
0x18014fe96  mov     r12d, 1
0x18014fe9c  mov     rdx, [r14+40h]
0x18014fea0  lea     r9, [rbp+2E0h+var_35C]
0x18014fea4  mov     r8d, 1
0x18014feaa  mov     [rbp+2E0h+var_35C], 0
0x18014feb1  mov     rcx, rdi; context
0x18014feb4  call    WspProviderEnter
0x18014feb9  mov     edx, eax
0x18014febb  test    eax, eax
0x18014febd  jz      loc_180150001
0x18014fec3  test    rdi, rdi
0x18014fec6  jz      short loc_18014FEDB
0x18014fec8  mov     rax, [rdi]
0x18014fecb  test    rax, rax
0x18014fece  jz      short loc_18014FEDB
0x18014fed0  mov     rax, [rax]
0x18014fed3  mov     rcx, rdi
0x18014fed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014fedb  lea     r14, aCreatevolume_0; "CreateVolume"
0x18014fee2  lea     rsi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x18014fee9  mov     ecx, [rbp+2E0h+var_35C]
0x18014feec  call    WspProviderExit
0x18014fef1  test    r13d, r13d
0x18014fef4  jz      loc_18014FF86
0x18014fefa  lea     rcx, [rbp+2E0h+var_320]; this
0x18014fefe  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014ff03  mov     eax, cs:dword_180397B68
0x18014ff09  cmp     eax, 5
0x18014ff0c  jbe     short loc_18014FF86
0x18014ff0e  mov     rdx, 400000000000h
0x18014ff18  lea     rcx, dword_180397B68
0x18014ff1f  call    _tlgKeywordOn
0x18014ff24  test    al, al
0x18014ff26  jz      short loc_18014FF86
0x18014ff28  mov     rax, [rbp+2E0h+var_318]
0x18014ff2c  xor     edx, edx
0x18014ff2e  sub     rax, [rbp+2E0h+var_320]
0x18014ff32  imul    rax, 3E8h
0x18014ff39  mov     [rsp+3E0h+var_370], r12d
0x18014ff3e  div     [rbp+2E0h+var_310]
0x18014ff42  lea     rdx, word_1803522CA
0x18014ff49  mov     [rbp+2E0h+var_328], r14
0x18014ff4d  mov     [rbp+2E0h+var_348], rax
0x18014ff51  lea     rax, aWspdisk; "WspDisk"
0x18014ff58  mov     [rbp+2E0h+var_330], rax
0x18014ff5c  lea     rax, [rbp+2E0h+var_348]
0x18014ff60  mov     [rsp+3E0h+var_3A8], rax
0x18014ff65  lea     rax, [rsp+3E0h+var_370]
0x18014ff6a  mov     qword ptr [rsp+3E0h+var_3B0], rax
0x18014ff6f  lea     rax, [rbp+2E0h+var_328]
0x18014ff73  mov     qword ptr [rsp+3E0h+var_3B8], rax
0x18014ff78  lea     rax, [rbp+2E0h+var_330]
0x18014ff7c  mov     [rsp+3E0h+var_3C0], rax
0x18014ff81  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18014ff86  mov     eax, cs:dword_180397B68
0x18014ff8c  cmp     eax, 5
0x18014ff8f  jbe     short loc_18014FFBC
0x18014ff91  lea     rax, [rsp+3E0h+var_370]
0x18014ff96  mov     [rsp+3E0h+var_370], 967h
0x18014ff9e  mov     qword ptr [rsp+3E0h+var_3B8], rax
0x18014ffa3  lea     rdx, word_180353DD6
0x18014ffaa  lea     rax, [rbp+2E0h+var_348]
0x18014ffae  mov     [rbp+2E0h+var_348], rsi
0x18014ffb2  mov     [rsp+3E0h+var_3C0], rax
0x18014ffb7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014ffbc  lea     rcx, [rbp+2E0h+var_320]; this
0x18014ffc0  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18014ffc5  lea     rdx, [rbp+2E0h+var_D8]; ActivityId
0x18014ffcc  mov     ecx, 4; ControlCode
0x18014ffd1  call    cs:__imp_EventActivityIdControl
0x18014ffd7  mov     rcx, [rbp+2E0h+var_40]
0x18014ffde  xor     rcx, rsp; StackCookie
0x18014ffe1  call    __security_check_cookie
0x18014ffe6  mov     rbx, [rsp+3E0h+arg_0]
0x18014ffee  add     rsp, 3B0h
0x18014fff5  pop     r15
0x18014fff7  pop     r14
0x18014fff9  pop     r13
0x18014fffb  pop     r12
0x18014fffd  pop     rdi
0x18014fffe  pop     rsi
0x18014ffff  pop     rbp
0x180150000  retn
0x180150001  mov     rcx, [r14+40h]; unsigned __int16 *
0x180150005  call    WspIsRemoteInstance
0x18015000a  mov     rcx, [r14+40h]
0x18015000e  test    al, al
0x180150010  jz      short loc_18015002F
0x180150012  mov     r8, rcx; unsigned __int16 *
0x180150015  mov     [rsp+3E0h+var_3C0], rsi; void *
0x18015001a  mov     rcx, rdi; struct _MI_Context *
0x18015001d  mov     r9, r15; unsigned __int16 *
0x180150020  mov     rdx, rbx; unsigned __int16 *
0x180150023  call    WspInvokeRemoteMethod
0x180150028  mov     edx, eax
0x18015002a  jmp     loc_18014FEC3
0x18015002f  xor     eax, eax
0x180150031  xorps   xmm0, xmm0
0x180150034  movups  [rbp+2E0h+var_100], xmm0
0x18015003b  mov     [rbp+2E0h+var_F0], eax
0x180150041  mov     dword ptr [rbp+2E0h+var_350], eax
0x180150044  call    WspGetSubsystemType
0x180150049  lea     rcx, [rbp+2E0h+var_350]
0x18015004d  mov     ebx, eax
0x18015004f  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180150054  lea     rdx, [rbp+2E0h+var_100]; struct _SUBSYSTEM_INFO *
0x18015005b  mov     ecx, ebx; unsigned int
0x18015005d  mov     r15d, eax
0x180150060  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180150065  mov     ecx, cs:dword_180397B68
0x18015006b  cmp     ecx, 5
0x18015006e  jbe     short loc_1801500E5
0x180150070  mov     rdx, 400000000000h
0x18015007a  lea     rcx, dword_180397B68
0x180150081  call    _tlgKeywordOn
0x180150086  test    al, al
0x180150088  jz      short loc_1801500E5
0x18015008a  xor     eax, eax
0x18015008c  mov     [rsp+3E0h+var_370], ebx
0x180150090  cmp     r15d, dword ptr [rbp+2E0h+var_350]
0x180150094  lea     rdx, byte_180352447
0x18015009b  setnz   al
0x18015009e  mov     [rsp+3E0h+var_36C], eax
0x1801500a2  movzx   eax, word ptr [rbp+2E0h+var_F0]
0x1801500a9  mov     word ptr [rbp+2E0h+var_350], ax
0x1801500ad  lea     rax, [rbp+2E0h+var_100]
0x1801500b4  mov     [rsp+3E0h+var_368], rax
0x1801500b9  lea     rax, [rsp+3E0h+var_36C]
0x1801500be  mov     [rsp+3E0h+var_3A8], rax
0x1801500c3  lea     rax, [rbp+2E0h+var_350]
0x1801500c7  mov     qword ptr [rsp+3E0h+var_3B0], rax
0x1801500cc  lea     rax, [rsp+3E0h+var_370]
0x1801500d1  mov     qword ptr [rsp+3E0h+var_3B8], rax
0x1801500d6  lea     rax, [rsp+3E0h+var_368]
0x1801500db  mov     [rsp+3E0h+var_3C0], rax
0x1801500e0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801500e5  xor     r15d, r15d
0x1801500e8  test    rsi, rsi
0x1801500eb  jnz     loc_180150180
0x1801500f1  lea     ebx, [rsi+4]
0x1801500f4  lea     rsi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x1801500fb  lea     rcx, [rbp+2E0h+var_320]; this
0x1801500ff  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180150104  mov     eax, cs:dword_180397B68
0x18015010a  cmp     eax, 5
0x18015010d  jbe     loc_180150517
0x180150113  mov     rdx, 400000000000h
0x18015011d  lea     rcx, dword_180397B68
0x180150124  call    _tlgKeywordOn
0x180150129  test    al, al
0x18015012b  jz      loc_180150517
0x180150131  mov     rax, [rbp+2E0h+var_318]
0x180150135  xor     edx, edx
0x180150137  sub     rax, [rbp+2E0h+var_320]
0x18015013b  imul    rax, 3E8h
0x180150142  mov     [rsp+3E0h+var_368], r15
0x180150147  div     [rbp+2E0h+var_310]
0x18015014b  mov     [rbp+2E0h+var_358], r15
0x18015014f  mov     [rbp+2E0h+var_300], rax
0x180150153  mov     al, [rbp+2E0h+var_28C]
0x180150156  neg     al
0x180150158  mov     [rbp+2E0h+var_350], r15
0x18015015c  mov     [rsp+3E0h+var_370], ebx
0x180150160  sbb     ecx, ecx
0x180150162  mov     [rbp+2E0h+var_360], r12d
0x180150166  and     ecx, [rbp+2E0h+var_290]
0x180150169  mov     [rsp+3E0h+var_36C], ecx
0x18015016d  cmp     [r14+48h], r15b
0x180150171  jz      loc_18015048F
0x180150177  mov     rax, [r14+40h]
0x18015017b  jmp     loc_180150492
0x180150180  mov     rcx, [r14+40h]; unsigned __int16 *
0x180150184  lea     r9, [rbp+2E0h+var_338]
0x180150188  lea     r8, [rbp+2E0h+var_360]
0x18015018c  lea     rdx, [rbp+2E0h+var_358]
0x180150190  call    WspUnpackObjectId
0x180150195  mov     ebx, eax
0x180150197  test    eax, eax
0x180150199  jz      short loc_1801501F1
0x18015019b  mov     ecx, cs:dword_180397B68
0x1801501a1  cmp     ecx, 2
0x1801501a4  jbe     loc_1801500F4
0x1801501aa  mov     [rsp+3E0h+var_370], eax
0x1801501ae  lea     rdx, byte_1803532DD
0x1801501b5  mov     [rsp+3E0h+var_36C], 8F0h
0x1801501bd  lea     rax, [rsp+3E0h+var_370]
0x1801501c2  mov     qword ptr [rsp+3E0h+var_3B0], rax
0x1801501c7  lea     rsi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x1801501ce  lea     rax, [rsp+3E0h+var_36C]
0x1801501d3  mov     [rsp+3E0h+var_368], rsi
0x1801501d8  mov     qword ptr [rsp+3E0h+var_3B8], rax
0x1801501dd  lea     rax, [rsp+3E0h+var_368]
0x1801501e2  mov     [rsp+3E0h+var_3C0], rax
0x1801501e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801501ec  jmp     loc_1801500FB
0x1801501f1  lea     r8, [rbp+2E0h+instance]; instance
0x1801501f5  mov     rcx, rdi; context
0x1801501f8  lea     rdx, WSP_Disk_CreateVolume_rtti; methodDecl
0x1801501ff  call    MI_Context_ConstructParameters
0x180150204  mov     ebx, eax
0x180150206  test    eax, eax
0x180150208  jz      short loc_18015022E
0x18015020a  mov     eax, cs:dword_180397B68
0x180150210  cmp     eax, 2
0x180150213  jbe     loc_1801500F4
0x180150219  mov     [rsp+3E0h+var_370], ebx
0x18015021d  lea     rdx, unk_180351D30
0x180150224  mov     [rsp+3E0h+var_36C], 8F8h
0x18015022c  jmp     short loc_1801501BD
0x18015022e  mov     ebx, dword ptr [rbp+2E0h+var_358]
0x180150231  lea     r9, [rbp+2E0h+Block]
0x180150235  mov     r8d, ebx
0x180150238  mov     rdx, rsi
0x18015023b  mov     rcx, rdi
0x18015023e  call    ?WspParseCreateVolumeParameters@@YA?AW4SM_RETURN_CODE@@PEAU_MI_Context@@PEBU_WSP_Disk_CreateVolume@@W4WSP_SUBSYSTEM_TYPE@@PEAPEAU_PM_CREATE_VOLUME_PARAMETERS@@@Z; WspParseCreateVolumeParameters(_MI_Context *,_WSP_Disk_CreateVolume const *,WSP_SUBSYSTEM_TYPE,_PM_CREATE_VOLUME_PARAMETERS * *)
  ... truncated ...
```
