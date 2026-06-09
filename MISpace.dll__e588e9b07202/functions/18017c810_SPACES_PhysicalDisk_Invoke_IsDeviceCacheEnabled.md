# SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled

- ea: `0x18017c810`
- end: `0x18017cdad`
- name: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- size: `1437`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x180137a24`
- `0x180138120`
- `0x18017c810`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c88d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c8ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017cd7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c88d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c8ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017cd7d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017c8b0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017c8b0`

## string_xrefs

- `0x18017cc81`: `IsDeviceCacheEnabled`
- `0x18017c8f8`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017ca0c`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017ca6b`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017cacc`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017cb3e`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017cb93`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18017cd1b`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`

## pseudocode

```c
ULONG __fastcall SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled(
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
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  const MI_Char *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v41; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v42; // [rsp+80h] [rbp-80h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const char *v47; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v48; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v51; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v52[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h]
  MI_Value value; // [rsp+108h] [rbp+8h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+190h] [rbp+90h] BYREF
  GUID v59; // [rsp+1A0h] [rbp+A0h]
  GUID v60; // [rsp+1B0h] [rbp+B0h] BYREF

  v44 = a4;
  v51 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v59 = ActivityId;
  v60 = ActivityId;
  EventActivityIdControl(4u, &v60);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v40 = 1024;
    v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled",
      (unsigned int)&dword_1803625BC,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v40);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x58u);
  v53 = 0;
  v54 = 0;
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v52);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v52);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v53) = 4;
    *((_QWORD *)&v53 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v53, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v40 = v15;
        v45 = 1056;
        v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_1803624F0,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_PhysicalDisk_IsDeviceCacheEnabled_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1074;
          v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)byte_180362755,
            v24,
            v25,
            (__int64)&v39,
            (__int64)&v49,
            (__int64)&v48);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v42 + 48LL))(
                v42,
                262152,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1085;
            v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_180363005,
              v27,
              v28,
              (__int64)&v39,
              (__int64)&v43,
              (__int64)&v50);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_180397B68 > 2 )
          {
            v41 = v15;
            LODWORD(v39) = 1093;
            v43 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&word_18036349E,
              v30,
              v31,
              (__int64)&v43,
              (__int64)&v39,
              (__int64)&v41);
          }
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v46) = 7;
        LODWORD(v47) = 1066;
        v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_1803626E3,
          v21,
          v22,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v46);
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v44, v51, a6 + 4, &v57, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v52);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        v44 = 0;
        v51 = 0;
        v50 = 0;
        v49 = (unsigned __int64)(1000LL * (v52[1] - v52[0])) / v52[2];
        LODWORD(v39) = v15;
        v41 = v57.exists != 0 ? v57.value : 0;
        LODWORD(v43) = v13;
        if ( a6[4].exists )
          v34 = a6[4].value;
        else
          v34 = 0;
        v48 = v34;
        v47 = "IsDeviceCacheEnabled";
        v46 = "PhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)&byte_180362B6F,
          v32,
          v33,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v44);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v39) = 1126;
    v44 = (unsigned __int16 *)"SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_1803630DD,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v39);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v52);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  return EventActivityIdControl(4u, &v60);
}

```

## disassembly

```asm
0x18017c810  mov     [rsp-8+arg_10], rbx
0x18017c815  push    rbp
0x18017c816  push    rsi
0x18017c817  push    rdi
0x18017c818  push    r12
0x18017c81a  push    r13
0x18017c81c  push    r14
0x18017c81e  push    r15
0x18017c820  lea     rbp, [rsp-0D0h]
0x18017c828  sub     rsp, 1D0h
0x18017c82f  mov     rax, cs:__security_cookie
0x18017c836  xor     rax, rsp
0x18017c839  mov     [rbp+100h+var_40], rax
0x18017c840  mov     [rbp+100h+var_170], r9
0x18017c844  mov     rdi, rdx
0x18017c847  mov     rsi, rcx
0x18017c84a  mov     rax, [rbp+100h+arg_20]
0x18017c851  mov     [rbp+100h+var_138], rax
0x18017c855  mov     r14, [rbp+100h+arg_28]
0x18017c85c  mov     r12, [rbp+100h+arg_30]
0x18017c863  xorps   xmm0, xmm0
0x18017c866  xor     eax, eax
0x18017c868  movups  xmmword ptr [rbp+100h+value], xmm0
0x18017c86c  movups  xmmword ptr [rbp+100h+value+10h], xmm0
0x18017c870  mov     qword ptr [rbp+100h+value+20h], rax
0x18017c874  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017c87b  movdqu  xmmword ptr [rbp+100h+ActivityId.Data1], xmm0
0x18017c883  lea     rdx, [rbp+100h+ActivityId]; ActivityId
0x18017c88a  lea     ecx, [rax+1]; ControlCode
0x18017c88d  call    cs:__imp_EventActivityIdControl
0x18017c893  lea     r9, [rbp+100h+value]; value
0x18017c897  mov     rcx, rdi; context
0x18017c89a  call    MI_Context_GetCustomOption_1
0x18017c89f  xor     ebx, ebx
0x18017c8a1  test    eax, eax
0x18017c8a3  jnz     short loc_18017C8B6
0x18017c8a5  lea     rdx, [rbp+100h+ActivityId]; pclsid
0x18017c8ac  mov     rcx, qword ptr [rbp+100h+value]; lpsz
0x18017c8b0  call    cs:__imp_CLSIDFromString
0x18017c8b6  mov     rcx, qword ptr [rbp+100h+ActivityId.Data1]
0x18017c8bd  mov     [rbp+100h+var_60], rcx
0x18017c8c4  mov     rax, qword ptr [rbp+100h+ActivityId.Data4]
0x18017c8cb  mov     [rbp+100h+var_58], rax
0x18017c8d2  mov     qword ptr [rbp+100h+var_50.Data1], rcx
0x18017c8d9  mov     qword ptr [rbp+100h+var_50.Data4], rax
0x18017c8e0  lea     rdx, [rbp+100h+var_50]; ActivityId
0x18017c8e7  mov     ecx, 4; ControlCode
0x18017c8ec  call    cs:__imp_EventActivityIdControl
0x18017c8f2  mov     eax, cs:dword_180397B68
0x18017c8f8  lea     rcx, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017c8ff  cmp     eax, 5
0x18017c902  jbe     short loc_18017C931
0x18017c904  mov     [rsp+200h+var_188], 400h
0x18017c90c  mov     [rsp+200h+var_190], rcx
0x18017c911  lea     rax, [rsp+200h+var_188]
0x18017c916  mov     [rsp+200h+var_1D8], rax
0x18017c91b  lea     rax, [rsp+200h+var_190]
0x18017c920  mov     qword ptr [rsp+200h+var_1E0], rax
0x18017c925  lea     rdx, dword_1803625BC
0x18017c92c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017c931  mov     [rbp+100h+instance.ft], rbx
0x18017c935  xor     edx, edx; Val
0x18017c937  lea     r8d, [rdx+58h]; Size
0x18017c93b  lea     rcx, [rbp+100h+instance.classDecl]; void *
0x18017c93f  call    memset_0
0x18017c944  xorps   xmm0, xmm0
0x18017c947  xor     eax, eax
0x18017c949  movups  [rbp+100h+var_110], xmm0
0x18017c94d  mov     [rbp+100h+var_100], rax
0x18017c951  mov     [rbp+100h+var_180], rbx
0x18017c955  lea     rcx, [rbp+100h+var_180]
0x18017c959  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017c95e  mov     [rbp+100h+var_180], rbx
0x18017c962  mov     r15d, ebx
0x18017c965  lea     rcx, [rbp+100h+var_130]; this
0x18017c969  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18017c96e  mov     rcx, rdi; context
0x18017c971  call    WspIsRemoteRequest
0x18017c976  mov     r13d, eax
0x18017c979  test    eax, eax
0x18017c97b  jnz     short loc_18017C9A0
0x18017c97d  lea     rcx, [rbp+100h+var_130]; this
0x18017c981  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18017c986  cmp     [r14+48h], bl
0x18017c98a  jz      short loc_18017C99D
0x18017c98c  mov     rcx, [r14+40h]; unsigned __int16 *
0x18017c990  call    WspIsRemoteInstance
0x18017c995  test    al, al
0x18017c997  lea     r15d, [r13+1]
0x18017c99b  jnz     short loc_18017C9A0
0x18017c99d  mov     r15d, ebx
0x18017c9a0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18017c9a7  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18017c9ac  mov     ebx, eax
0x18017c9ae  test    eax, eax
0x18017c9b0  jnz     loc_18017CBD3
0x18017c9b6  mov     dword ptr [rbp+100h+var_110], 4
0x18017c9bd  mov     rax, [r14+40h]
0x18017c9c1  mov     qword ptr [rbp+100h+var_110+8], rax
0x18017c9c5  mov     rbx, [rsi]
0x18017c9c8  lea     rcx, [rbp+100h+var_180]
0x18017c9cc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017c9d1  mov     [rsp+200h+var_1E0], 1; int
0x18017c9d9  lea     r9, [rbp+100h+var_180]; struct ISpWmiObject **
0x18017c9dd  lea     r8, [rbp+100h+var_110]; struct _SP_OBJECT_ID *
0x18017c9e1  mov     rdx, rdi; context
0x18017c9e4  mov     rcx, rbx; this
0x18017c9e7  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18017c9ec  mov     ebx, eax
0x18017c9ee  test    eax, eax
0x18017c9f0  jz      short loc_18017CA3C
0x18017c9f2  mov     eax, cs:dword_180397B68
0x18017c9f8  cmp     eax, 2
0x18017c9fb  jbe     loc_18017CBC7
0x18017ca01  mov     [rsp+200h+var_188], ebx
0x18017ca05  mov     [rbp+100h+var_168], 420h
0x18017ca0c  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017ca13  mov     [rsp+200h+var_190], rax
0x18017ca18  lea     rax, [rsp+200h+var_188]
0x18017ca1d  mov     [rsp+200h+var_1D0], rax
0x18017ca22  lea     rax, [rbp+100h+var_168]
0x18017ca26  mov     [rsp+200h+var_1D8], rax
0x18017ca2b  lea     rax, [rsp+200h+var_190]
0x18017ca30  lea     rdx, unk_1803624F0
0x18017ca37  jmp     loc_18017CBBD
0x18017ca3c  mov     r8, [r14+40h]
0x18017ca40  mov     rdx, rdi
0x18017ca43  mov     rcx, [rsi]
0x18017ca46  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18017ca4b  test    eax, eax
0x18017ca4d  jnz     short loc_18017CA9A
0x18017ca4f  lea     ebx, [rax+7]
0x18017ca52  mov     eax, cs:dword_180397B68
0x18017ca58  cmp     eax, 2
0x18017ca5b  jbe     loc_18017CBC7
0x18017ca61  mov     dword ptr [rbp+100h+var_160], ebx
0x18017ca64  mov     dword ptr [rbp+100h+var_158], 42Ah
0x18017ca6b  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017ca72  mov     [rsp+200h+var_190], rax
0x18017ca77  lea     rax, [rbp+100h+var_160]
0x18017ca7b  mov     [rsp+200h+var_1D0], rax
0x18017ca80  lea     rax, [rbp+100h+var_158]
0x18017ca84  mov     [rsp+200h+var_1D8], rax
0x18017ca89  lea     rax, [rsp+200h+var_190]
0x18017ca8e  lea     rdx, byte_1803626E3
0x18017ca95  jmp     loc_18017CBBD
0x18017ca9a  lea     r8, [rbp+100h+instance]; instance
0x18017ca9e  lea     rdx, SPACES_PhysicalDisk_IsDeviceCacheEnabled_rtti; methodDecl
0x18017caa5  mov     rcx, rdi; context
0x18017caa8  call    MI_Context_ConstructParameters
0x18017caad  mov     ebx, eax
0x18017caaf  test    eax, eax
0x18017cab1  jz      short loc_18017CAFB
0x18017cab3  mov     eax, cs:dword_180397B68
0x18017cab9  cmp     eax, 2
0x18017cabc  jbe     loc_18017CBC7
0x18017cac2  mov     dword ptr [rbp+100h+var_150], ebx
0x18017cac5  mov     dword ptr [rbp+100h+var_148], 432h
0x18017cacc  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017cad3  mov     [rsp+200h+var_190], rax
0x18017cad8  lea     rax, [rbp+100h+var_150]
0x18017cadc  mov     [rsp+200h+var_1D0], rax
0x18017cae1  lea     rax, [rbp+100h+var_148]
0x18017cae5  mov     [rsp+200h+var_1D8], rax
0x18017caea  lea     rax, [rsp+200h+var_190]
0x18017caef  lea     rdx, byte_180362755
0x18017caf6  jmp     loc_18017CBBD
0x18017cafb  mov     rcx, [rbp+100h+var_180]
0x18017caff  mov     rax, [rcx]
0x18017cb02  lea     rdx, [rbp+100h+instance]
0x18017cb06  mov     qword ptr [rsp+200h+var_1E0], rdx
0x18017cb0b  mov     r9, r12
0x18017cb0e  mov     r8, rdi
0x18017cb11  mov     edx, 40008h
0x18017cb16  mov     rax, [rax+30h]
0x18017cb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017cb1f  mov     ebx, eax
0x18017cb21  test    eax, eax
0x18017cb23  jz      short loc_18017CB6A
0x18017cb25  mov     eax, cs:dword_180397B68
0x18017cb2b  cmp     eax, 2
0x18017cb2e  jbe     loc_18017CBC7
0x18017cb34  mov     dword ptr [rbp+100h+var_140], ebx
0x18017cb37  mov     dword ptr [rbp+100h+var_178], 43Dh
0x18017cb3e  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017cb45  mov     [rsp+200h+var_190], rax
0x18017cb4a  lea     rax, [rbp+100h+var_140]
0x18017cb4e  mov     [rsp+200h+var_1D0], rax
0x18017cb53  lea     rax, [rbp+100h+var_178]
0x18017cb57  mov     [rsp+200h+var_1D8], rax
0x18017cb5c  lea     rax, [rsp+200h+var_190]
0x18017cb61  lea     rdx, byte_180363005
0x18017cb68  jmp     short loc_18017CBBD
0x18017cb6a  lea     rdx, [rbp+100h+instance]
0x18017cb6e  mov     rcx, rdi; self
0x18017cb71  call    MI_Instance_Destruct
0x18017cb76  mov     ebx, eax
0x18017cb78  test    eax, eax
0x18017cb7a  jz      short loc_18017CBC7
0x18017cb7c  mov     eax, cs:dword_180397B68
0x18017cb82  cmp     eax, 2
0x18017cb85  jbe     short loc_18017CBC7
0x18017cb87  mov     [rsp+200h+var_184], ebx
0x18017cb8b  mov     dword ptr [rsp+200h+var_190], 445h
0x18017cb93  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017cb9a  mov     [rbp+100h+var_178], rax
0x18017cb9e  lea     rax, [rsp+200h+var_184]
0x18017cba3  mov     [rsp+200h+var_1D0], rax
0x18017cba8  lea     rax, [rsp+200h+var_190]
0x18017cbad  mov     [rsp+200h+var_1D8], rax
0x18017cbb2  lea     rax, [rbp+100h+var_178]
0x18017cbb6  lea     rdx, word_18036349E
0x18017cbbd  mov     qword ptr [rsp+200h+var_1E0], rax
0x18017cbc2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18017cbc7  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18017cbce  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18017cbd3  xor     r12d, r12d
0x18017cbd6  mov     [rsp+200h+var_1D8], r12; unsigned __int16 *
0x18017cbdb  mov     [rsp+200h+var_1E0], ebx; enum _MI_Result
0x18017cbdf  lea     r9, [rbp+100h+var_90]; struct _MI_ConstUint32Field *
0x18017cbe3  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18017cbe7  mov     rdx, [rbp+100h+var_138]; unsigned __int16 *
0x18017cbeb  mov     rcx, [rbp+100h+var_170]; unsigned __int16 *
0x18017cbef  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18017cbf4  test    r13d, r13d
0x18017cbf7  jnz     loc_18017CCFF
0x18017cbfd  lea     rcx, [rbp+100h+var_130]; this
0x18017cc01  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18017cc06  mov     eax, cs:dword_180397B68
0x18017cc0c  cmp     eax, 5
0x18017cc0f  jbe     loc_18017CCFF
0x18017cc15  mov     rdx, 400000000000h
0x18017cc1f  lea     rcx, dword_180397B68
0x18017cc26  call    _tlgKeywordOn
0x18017cc2b  test    al, al
0x18017cc2d  jz      loc_18017CCFF
0x18017cc33  mov     [rbp+100h+var_170], r12
0x18017cc37  mov     [rbp+100h+var_138], r12
0x18017cc3b  mov     [rbp+100h+var_140], r12
0x18017cc3f  mov     rax, [rbp+100h+var_128]
0x18017cc43  sub     rax, [rbp+100h+var_130]
0x18017cc47  imul    rax, 3E8h
0x18017cc4e  xor     edx, edx
0x18017cc50  div     [rbp+100h+var_120]
0x18017cc54  mov     [rbp+100h+var_148], rax
0x18017cc58  mov     dword ptr [rsp+200h+var_190], ebx
0x18017cc5c  mov     al, [rbp+100h+var_90.exists]
0x18017cc5f  neg     al
0x18017cc61  sbb     ecx, ecx
0x18017cc63  and     ecx, [rbp+100h+var_90.value]
0x18017cc66  mov     [rsp+200h+var_184], ecx
0x18017cc6a  mov     dword ptr [rbp+100h+var_178], r15d
0x18017cc6e  cmp     [r14+48h], r12b
0x18017cc72  jz      short loc_18017CC7A
0x18017cc74  mov     rax, [r14+40h]
0x18017cc78  jmp     short loc_18017CC7D
0x18017cc7a  mov     rax, r12
0x18017cc7d  mov     [rbp+100h+var_150], rax
0x18017cc81  lea     rax, aIsdevicecachee_0; "IsDeviceCacheEnabled"
0x18017cc88  mov     [rbp+100h+var_158], rax
0x18017cc8c  lea     rax, aPhysicaldisk_0; "PhysicalDisk"
0x18017cc93  mov     [rbp+100h+var_160], rax
0x18017cc97  lea     rax, [rbp+100h+var_170]
0x18017cc9b  mov     [rsp+200h+var_198], rax
0x18017cca0  lea     rax, [rbp+100h+var_138]
0x18017cca4  mov     [rsp+200h+var_1A0], rax
0x18017cca9  lea     rax, [rbp+100h+var_140]
0x18017ccad  mov     [rsp+200h+var_1A8], rax
0x18017ccb2  lea     rax, [rbp+100h+var_148]
0x18017ccb6  mov     [rsp+200h+var_1B0], rax
0x18017ccbb  lea     rax, [rsp+200h+var_190]
0x18017ccc0  mov     [rsp+200h+var_1B8], rax
0x18017ccc5  lea     rax, [rsp+200h+var_184]
0x18017ccca  mov     [rsp+200h+var_1C0], rax
0x18017cccf  lea     rax, [rbp+100h+var_178]
0x18017ccd3  mov     [rsp+200h+var_1C8], rax
0x18017ccd8  lea     rax, [rbp+100h+var_150]
0x18017ccdc  mov     [rsp+200h+var_1D0], rax
0x18017cce1  lea     rax, [rbp+100h+var_158]
0x18017cce5  mov     [rsp+200h+var_1D8], rax
0x18017ccea  lea     rax, [rbp+100h+var_160]
0x18017ccee  mov     qword ptr [rsp+200h+var_1E0], rax
0x18017ccf3  lea     rdx, byte_180362B6F
0x18017ccfa  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18017ccff  lea     rcx, [rbp+100h+instance]; self
0x18017cd03  call    MI_Instance_Destruct
0x18017cd08  mov     eax, cs:dword_180397B68
0x18017cd0e  cmp     eax, 5
0x18017cd11  jbe     short loc_18017CD45
0x18017cd13  mov     dword ptr [rsp+200h+var_190], 466h
0x18017cd1b  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18017cd22  mov     [rbp+100h+var_170], rax
0x18017cd26  lea     rax, [rsp+200h+var_190]
0x18017cd2b  mov     [rsp+200h+var_1D8], rax
0x18017cd30  lea     rax, [rbp+100h+var_170]
0x18017cd34  mov     qword ptr [rsp+200h+var_1E0], rax
0x18017cd39  lea     rdx, byte_1803630DD
0x18017cd40  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017cd45  test    rdi, rdi
0x18017cd48  jz      short loc_18017CD5F
  ... truncated ...
```
