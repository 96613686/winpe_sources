# SPACES_VirtualDisk_Invoke_GetSecurityDescriptor

- ea: `0x18013ad60`
- end: `0x18013b29c`
- name: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
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
- `0x18013ad60`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013addd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013ae3c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b26c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013addd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013ae3c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b26c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013ae00`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013ae00`

## string_xrefs

- `0x18013ae48`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013af5a`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013afbb`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013b02d`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013b082`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013b20a`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013b170`: `GetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_GetSecurityDescriptor(
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
    LODWORD(v39) = 469;
    v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_GetSecurityDescriptor",
      (unsigned int)qword_18034AC70,
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
        LODWORD(v42) = 500;
        v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_18034AD05,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_GetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 508;
          v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&byte_18034B6DF,
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
                1048580,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 519;
            v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&word_18034BF6E,
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
            LODWORD(v36) = 527;
            v40 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&unk_18034AFA8,
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
        v39 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)byte_18034BBFD,
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
    LODWORD(v36) = 560;
    v41 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)&word_18034B746,
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
0x18013ad60  mov     [rsp-8+arg_10], rbx
0x18013ad65  push    rbp
0x18013ad66  push    rsi
0x18013ad67  push    rdi
0x18013ad68  push    r12
0x18013ad6a  push    r13
0x18013ad6c  push    r14
0x18013ad6e  push    r15
0x18013ad70  lea     rbp, [rsp-0E0h]
0x18013ad78  sub     rsp, 1E0h
0x18013ad7f  mov     rax, cs:__security_cookie
0x18013ad86  xor     rax, rsp
0x18013ad89  mov     [rbp+110h+var_40], rax
0x18013ad90  mov     [rbp+110h+var_178], r9
0x18013ad94  mov     rdi, rdx
0x18013ad97  mov     rsi, rcx
0x18013ad9a  mov     rax, [rbp+110h+arg_20]
0x18013ada1  mov     [rbp+110h+var_150], rax
0x18013ada5  mov     r14, [rbp+110h+arg_28]
0x18013adac  mov     r13, [rbp+110h+arg_30]
0x18013adb3  xorps   xmm0, xmm0
0x18013adb6  xor     eax, eax
0x18013adb8  movups  xmmword ptr [rbp+110h+value], xmm0
0x18013adbc  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18013adc0  mov     qword ptr [rbp+110h+value+20h], rax
0x18013adc4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013adcb  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18013add3  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18013adda  lea     ecx, [rax+1]; ControlCode
0x18013addd  call    cs:__imp_EventActivityIdControl
0x18013ade3  lea     r9, [rbp+110h+value]; value
0x18013ade7  mov     rcx, rdi; context
0x18013adea  call    MI_Context_GetCustomOption_1
0x18013adef  xor     ebx, ebx
0x18013adf1  test    eax, eax
0x18013adf3  jnz     short loc_18013AE06
0x18013adf5  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18013adfc  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18013ae00  call    cs:__imp_CLSIDFromString
0x18013ae06  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18013ae0d  mov     [rbp+110h+var_60], rcx
0x18013ae14  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18013ae1b  mov     [rbp+110h+var_58], rax
0x18013ae22  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18013ae29  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18013ae30  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013ae37  mov     ecx, 4; ControlCode
0x18013ae3c  call    cs:__imp_EventActivityIdControl
0x18013ae42  mov     eax, cs:dword_180397B68
0x18013ae48  lea     rcx, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013ae4f  cmp     eax, 5
0x18013ae52  jbe     short loc_18013AE7F
0x18013ae54  mov     dword ptr [rbp+110h+var_188], 1D5h
0x18013ae5b  mov     [rsp+210h+var_1A0], rcx
0x18013ae60  lea     rax, [rbp+110h+var_188]
0x18013ae64  mov     [rsp+210h+var_1E8], rax
0x18013ae69  lea     rax, [rsp+210h+var_1A0]
0x18013ae6e  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013ae73  lea     rdx, qword_18034AC70
0x18013ae7a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013ae7f  mov     [rbp+110h+instance.ft], rbx
0x18013ae83  xor     edx, edx; Val
0x18013ae85  lea     r8d, [rdx+60h]; Size
0x18013ae89  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18013ae8d  call    memset_0
0x18013ae92  xorps   xmm0, xmm0
0x18013ae95  xor     eax, eax
0x18013ae97  movups  [rbp+110h+var_128], xmm0
0x18013ae9b  mov     [rbp+110h+var_118], rax
0x18013ae9f  mov     [rbp+110h+var_190], rbx
0x18013aea3  lea     rcx, [rbp+110h+var_190]
0x18013aea7  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013aeac  mov     [rbp+110h+var_190], rbx
0x18013aeb0  lea     rcx, [rbp+110h+var_148]; this
0x18013aeb4  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013aeb9  mov     r15d, ebx
0x18013aebc  mov     rcx, rdi; context
0x18013aebf  call    WspIsRemoteRequest
0x18013aec4  mov     r12d, eax
0x18013aec7  test    eax, eax
0x18013aec9  jnz     short loc_18013AEEF
0x18013aecb  lea     rcx, [rbp+110h+var_148]; this
0x18013aecf  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013aed4  cmp     [r14+48h], bl
0x18013aed8  jz      short loc_18013AEEC
0x18013aeda  mov     rcx, [r14+40h]; unsigned __int16 *
0x18013aede  call    WspIsRemoteInstance
0x18013aee3  test    al, al
0x18013aee5  lea     r15d, [r12+1]
0x18013aeea  jnz     short loc_18013AEEF
0x18013aeec  mov     r15d, ebx
0x18013aeef  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013aef6  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013aefb  mov     ebx, eax
0x18013aefd  test    eax, eax
0x18013aeff  jnz     loc_18013B0C2
0x18013af05  mov     dword ptr [rbp+110h+var_128], 10h
0x18013af0c  mov     rax, [r14+40h]
0x18013af10  mov     qword ptr [rbp+110h+var_128+8], rax
0x18013af14  mov     rbx, [rsi]
0x18013af17  lea     rcx, [rbp+110h+var_190]
0x18013af1b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013af20  mov     [rsp+210h+var_1F0], 1; int
0x18013af28  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18013af2c  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x18013af30  mov     rdx, rdi; context
0x18013af33  mov     rcx, rbx; this
0x18013af36  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013af3b  mov     ebx, eax
0x18013af3d  test    eax, eax
0x18013af3f  jz      short loc_18013AF89
0x18013af41  mov     eax, cs:dword_180397B68
0x18013af47  cmp     eax, 2
0x18013af4a  jbe     loc_18013B0B6
0x18013af50  mov     dword ptr [rbp+110h+var_188], ebx
0x18013af53  mov     dword ptr [rbp+110h+var_170], 1F4h
0x18013af5a  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013af61  mov     [rsp+210h+var_1A0], rax
0x18013af66  lea     rax, [rbp+110h+var_188]
0x18013af6a  mov     [rsp+210h+var_1E0], rax
0x18013af6f  lea     rax, [rbp+110h+var_170]
0x18013af73  mov     [rsp+210h+var_1E8], rax
0x18013af78  lea     rax, [rsp+210h+var_1A0]
0x18013af7d  lea     rdx, byte_18034AD05
0x18013af84  jmp     loc_18013B0AC
0x18013af89  lea     r8, [rbp+110h+instance]; instance
0x18013af8d  lea     rdx, SPACES_VirtualDisk_GetSecurityDescriptor_rtti; methodDecl
0x18013af94  mov     rcx, rdi; context
0x18013af97  call    MI_Context_ConstructParameters
0x18013af9c  mov     ebx, eax
0x18013af9e  test    eax, eax
0x18013afa0  jz      short loc_18013AFEA
0x18013afa2  mov     eax, cs:dword_180397B68
0x18013afa8  cmp     eax, 2
0x18013afab  jbe     loc_18013B0B6
0x18013afb1  mov     dword ptr [rbp+110h+var_168], ebx
0x18013afb4  mov     dword ptr [rbp+110h+var_160], 1FCh
0x18013afbb  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013afc2  mov     [rsp+210h+var_1A0], rax
0x18013afc7  lea     rax, [rbp+110h+var_168]
0x18013afcb  mov     [rsp+210h+var_1E0], rax
0x18013afd0  lea     rax, [rbp+110h+var_160]
0x18013afd4  mov     [rsp+210h+var_1E8], rax
0x18013afd9  lea     rax, [rsp+210h+var_1A0]
0x18013afde  lea     rdx, byte_18034B6DF
0x18013afe5  jmp     loc_18013B0AC
0x18013afea  mov     rcx, [rbp+110h+var_190]
0x18013afee  mov     rax, [rcx]
0x18013aff1  lea     rdx, [rbp+110h+instance]
0x18013aff5  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18013affa  mov     r9, r13
0x18013affd  mov     r8, rdi
0x18013b000  mov     edx, 100004h
0x18013b005  mov     rax, [rax+30h]
0x18013b009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b00e  mov     ebx, eax
0x18013b010  test    eax, eax
0x18013b012  jz      short loc_18013B059
0x18013b014  mov     eax, cs:dword_180397B68
0x18013b01a  cmp     eax, 2
0x18013b01d  jbe     loc_18013B0B6
0x18013b023  mov     dword ptr [rbp+110h+var_158], ebx
0x18013b026  mov     dword ptr [rbp+110h+var_180], 207h
0x18013b02d  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013b034  mov     [rsp+210h+var_1A0], rax
0x18013b039  lea     rax, [rbp+110h+var_158]
0x18013b03d  mov     [rsp+210h+var_1E0], rax
0x18013b042  lea     rax, [rbp+110h+var_180]
0x18013b046  mov     [rsp+210h+var_1E8], rax
0x18013b04b  lea     rax, [rsp+210h+var_1A0]
0x18013b050  lea     rdx, word_18034BF6E
0x18013b057  jmp     short loc_18013B0AC
0x18013b059  lea     rdx, [rbp+110h+instance]
0x18013b05d  mov     rcx, rdi; self
0x18013b060  call    MI_Instance_Destruct
0x18013b065  mov     ebx, eax
0x18013b067  test    eax, eax
0x18013b069  jz      short loc_18013B0B6
0x18013b06b  mov     eax, cs:dword_180397B68
0x18013b071  cmp     eax, 2
0x18013b074  jbe     short loc_18013B0B6
0x18013b076  mov     [rsp+210h+var_198], ebx
0x18013b07a  mov     dword ptr [rsp+210h+var_1A0], 20Fh
0x18013b082  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013b089  mov     [rbp+110h+var_180], rax
0x18013b08d  lea     rax, [rsp+210h+var_198]
0x18013b092  mov     [rsp+210h+var_1E0], rax
0x18013b097  lea     rax, [rsp+210h+var_1A0]
0x18013b09c  mov     [rsp+210h+var_1E8], rax
0x18013b0a1  lea     rax, [rbp+110h+var_180]
0x18013b0a5  lea     rdx, unk_18034AFA8
0x18013b0ac  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013b0b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013b0b6  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013b0bd  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013b0c2  xor     r13d, r13d
0x18013b0c5  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18013b0ca  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18013b0ce  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18013b0d2  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18013b0d6  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18013b0da  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18013b0de  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013b0e3  test    r12d, r12d
0x18013b0e6  jnz     loc_18013B1EE
0x18013b0ec  lea     rcx, [rbp+110h+var_148]; this
0x18013b0f0  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013b0f5  mov     eax, cs:dword_180397B68
0x18013b0fb  cmp     eax, 5
0x18013b0fe  jbe     loc_18013B1EE
0x18013b104  mov     rdx, 400000000000h
0x18013b10e  lea     rcx, dword_180397B68
0x18013b115  call    _tlgKeywordOn
0x18013b11a  test    al, al
0x18013b11c  jz      loc_18013B1EE
0x18013b122  mov     [rbp+110h+var_178], r13
0x18013b126  mov     [rbp+110h+var_150], r13
0x18013b12a  mov     [rbp+110h+var_158], r13
0x18013b12e  mov     rax, [rbp+110h+var_140]
0x18013b132  sub     rax, [rbp+110h+var_148]
0x18013b136  imul    rax, 3E8h
0x18013b13d  xor     edx, edx
0x18013b13f  div     [rbp+110h+var_138]
0x18013b143  mov     [rbp+110h+var_160], rax
0x18013b147  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18013b14b  mov     al, [rbp+110h+var_A0.exists]
0x18013b14e  neg     al
0x18013b150  sbb     ecx, ecx
0x18013b152  and     ecx, [rbp+110h+var_A0.value]
0x18013b155  mov     [rsp+210h+var_198], ecx
0x18013b159  mov     dword ptr [rbp+110h+var_180], r15d
0x18013b15d  cmp     [r14+48h], r13b
0x18013b161  jz      short loc_18013B169
0x18013b163  mov     rax, [r14+40h]
0x18013b167  jmp     short loc_18013B16C
0x18013b169  mov     rax, r13
0x18013b16c  mov     [rbp+110h+var_168], rax
0x18013b170  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptor"
0x18013b177  mov     [rbp+110h+var_170], rax
0x18013b17b  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013b182  mov     [rbp+110h+var_188], rax
0x18013b186  lea     rax, [rbp+110h+var_178]
0x18013b18a  mov     [rsp+210h+var_1A8], rax
0x18013b18f  lea     rax, [rbp+110h+var_150]
0x18013b193  mov     [rsp+210h+var_1B0], rax
0x18013b198  lea     rax, [rbp+110h+var_158]
0x18013b19c  mov     [rsp+210h+var_1B8], rax
0x18013b1a1  lea     rax, [rbp+110h+var_160]
0x18013b1a5  mov     [rsp+210h+var_1C0], rax
0x18013b1aa  lea     rax, [rsp+210h+var_1A0]
0x18013b1af  mov     [rsp+210h+var_1C8], rax
0x18013b1b4  lea     rax, [rsp+210h+var_198]
0x18013b1b9  mov     [rsp+210h+var_1D0], rax
0x18013b1be  lea     rax, [rbp+110h+var_180]
0x18013b1c2  mov     [rsp+210h+var_1D8], rax
0x18013b1c7  lea     rax, [rbp+110h+var_168]
0x18013b1cb  mov     [rsp+210h+var_1E0], rax
0x18013b1d0  lea     rax, [rbp+110h+var_170]
0x18013b1d4  mov     [rsp+210h+var_1E8], rax
0x18013b1d9  lea     rax, [rbp+110h+var_188]
0x18013b1dd  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013b1e2  lea     rdx, byte_18034BBFD
0x18013b1e9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18013b1ee  lea     rcx, [rbp+110h+instance]; self
0x18013b1f2  call    MI_Instance_Destruct
0x18013b1f7  mov     eax, cs:dword_180397B68
0x18013b1fd  cmp     eax, 5
0x18013b200  jbe     short loc_18013B234
0x18013b202  mov     dword ptr [rsp+210h+var_1A0], 230h
0x18013b20a  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013b211  mov     [rbp+110h+var_178], rax
0x18013b215  lea     rax, [rsp+210h+var_1A0]
0x18013b21a  mov     [rsp+210h+var_1E8], rax
0x18013b21f  lea     rax, [rbp+110h+var_178]
0x18013b223  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013b228  lea     rdx, word_18034B746
0x18013b22f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013b234  test    rdi, rdi
0x18013b237  jz      short loc_18013B24E
0x18013b239  mov     rax, [rdi]
0x18013b23c  test    rax, rax
0x18013b23f  jz      short loc_18013B24E
0x18013b241  mov     edx, ebx
0x18013b243  mov     rcx, rdi
0x18013b246  mov     rax, [rax]
0x18013b249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b24e  lea     rcx, [rbp+110h+var_148]; this
0x18013b252  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18013b257  lea     rcx, [rbp+110h+var_190]
0x18013b25b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013b260  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013b267  mov     ecx, 4; ControlCode
0x18013b26c  call    cs:__imp_EventActivityIdControl
0x18013b272  mov     rcx, [rbp+110h+var_40]
0x18013b279  xor     rcx, rsp; StackCookie
0x18013b27c  call    __security_check_cookie
0x18013b281  mov     rbx, [rsp+210h+arg_10]
0x18013b289  add     rsp, 1E0h
0x18013b290  pop     r15
0x18013b292  pop     r14
  ... truncated ...
```
