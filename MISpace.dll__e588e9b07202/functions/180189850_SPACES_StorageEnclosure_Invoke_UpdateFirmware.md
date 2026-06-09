# SPACES_StorageEnclosure_Invoke_UpdateFirmware

- ea: `0x180189850`
- end: `0x180189e2d`
- name: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- size: `1501`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x180189850`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801898cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018992c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180189dfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801898cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018992c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180189dfd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801898f0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801898f0`

## string_xrefs

- `0x180189d01`: `UpdateFirmware`
- `0x180189938`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189a4c`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189aae`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189b56`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189bcb`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189c13`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x180189d9b`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`

## pseudocode

```c
ULONG __fastcall SPACES_StorageEnclosure_Invoke_UpdateFirmware(
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
  enum _MI_Result Instance; // ebx
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
  int v26; // eax
  int v27; // r8d
  int v28; // r9d
  const MI_Char *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char *v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v36; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v37; // [rsp+80h] [rbp-80h] BYREF
  const char *v38; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v39; // [rsp+90h] [rbp-70h] BYREF
  int v40; // [rsp+98h] [rbp-68h] BYREF
  const char *v41; // [rsp+A0h] [rbp-60h] BYREF
  const char *v42; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v43; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v44; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v46; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v47[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v48; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v49; // [rsp+100h] [rbp+0h]
  MI_Value value; // [rsp+108h] [rbp+8h] BYREF
  MI_Instance self; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v54; // [rsp+1B0h] [rbp+B0h]
  GUID v55; // [rsp+1C0h] [rbp+C0h] BYREF

  v39 = a4;
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
    v35 = 718;
    v34 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageEnclosure_Invoke_UpdateFirmware",
      (unsigned int)word_1803669C2,
      v11,
      v12,
      (__int64)&v34,
      (__int64)&v35);
  }
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x68u);
  v48 = 0;
  v49 = 0;
  v37 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  v37 = 0;
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
  Instance = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( Instance == MI_RESULT_OK )
  {
    LODWORD(v48) = 8;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
    Instance = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v37, 1);
    if ( Instance )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v35 = Instance;
        v40 = 750;
        v34 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&word_18036610E,
          v18,
          v19,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&v35);
      }
      goto LABEL_31;
    }
    if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) < 3 )
    {
      Instance = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v41) = 7;
        LODWORD(v42) = 760;
        v34 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&byte_180365F17,
          v21,
          v22,
          (__int64)&v34,
          (__int64)&v42,
          (__int64)&v41);
      }
      goto LABEL_31;
    }
    if ( a2 && a2->ft )
    {
      Instance = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructParameters)(
                   a2,
                   &SPACES_StorageEnclosure_UpdateFirmware_rtti,
                   &self);
      if ( Instance == MI_RESULT_OK )
      {
        Instance = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v37 + 48LL))(
                     v37,
                     524294,
                     a2,
                     a7,
                     &self);
        if ( Instance )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v43) = Instance;
            LODWORD(v44) = 779;
            v34 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_18036668A,
              v24,
              v25,
              (__int64)&v34,
              (__int64)&v44,
              (__int64)&v43);
          }
          goto LABEL_31;
        }
        if ( a2->ft )
        {
          v26 = ((__int64 (__fastcall *)(MI_Context *, MI_Instance *))a2->ft->PostInstance)(a2, &self);
          Instance = v26;
          if ( !v26 )
          {
LABEL_31:
            MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
            goto LABEL_32;
          }
        }
        else
        {
          v26 = 4;
          Instance = MI_RESULT_INVALID_PARAMETER;
        }
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v45) = v26;
          LODWORD(v38) = 787;
          v34 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_180366291,
            v24,
            v25,
            (__int64)&v34,
            (__int64)&v38,
            (__int64)&v45);
        }
        goto LABEL_31;
      }
    }
    else
    {
      Instance = MI_RESULT_INVALID_PARAMETER;
    }
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v36 = Instance;
      LODWORD(v34) = 768;
      v38 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)byte_180365B9D,
        v21,
        v22,
        (__int64)&v38,
        (__int64)&v34,
        (__int64)&v36);
    }
    goto LABEL_31;
  }
LABEL_32:
  SmLogOnMethodFailure(v39, v46, a6 + 4, &v52, Instance, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v47);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        v39 = 0;
        v46 = 0;
        v45 = 0;
        v44 = (unsigned __int64)(1000LL * (v47[1] - v47[0])) / v47[2];
        LODWORD(v34) = Instance;
        v36 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v38) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v43 = v29;
        v42 = "UpdateFirmware";
        v41 = "StorageEnclosure";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&word_180366056,
          v27,
          v28,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v38,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v39);
      }
    }
  }
  MI_Instance_Destruct(&self);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v34) = 820;
    v39 = (unsigned __int16 *)"SPACES_StorageEnclosure_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_180365B15,
      v31,
      v32,
      (__int64)&v39,
      (__int64)&v34);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)Instance);
  CSmTimer::~CSmTimer((CSmTimer *)v47);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  return EventActivityIdControl(4u, &v55);
}

```

## disassembly

```asm
0x180189850  mov     [rsp-8+arg_10], rbx
0x180189855  push    rbp
0x180189856  push    rsi
0x180189857  push    rdi
0x180189858  push    r12
0x18018985a  push    r13
0x18018985c  push    r14
0x18018985e  push    r15
0x180189860  lea     rbp, [rsp-0E0h]
0x180189868  sub     rsp, 1E0h
0x18018986f  mov     rax, cs:__security_cookie
0x180189876  xor     rax, rsp
0x180189879  mov     [rbp+110h+var_40], rax
0x180189880  mov     [rbp+110h+var_180], r9
0x180189884  mov     rdi, rdx
0x180189887  mov     rsi, rcx
0x18018988a  mov     rax, [rbp+110h+arg_20]
0x180189891  mov     [rbp+110h+var_148], rax
0x180189895  mov     r14, [rbp+110h+arg_28]
0x18018989c  mov     r12, [rbp+110h+arg_30]
0x1801898a3  xorps   xmm0, xmm0
0x1801898a6  xor     eax, eax
0x1801898a8  movups  xmmword ptr [rbp+110h+value], xmm0
0x1801898ac  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x1801898b0  mov     qword ptr [rbp+110h+value+20h], rax
0x1801898b4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801898bb  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x1801898c3  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x1801898ca  lea     ecx, [rax+1]; ControlCode
0x1801898cd  call    cs:__imp_EventActivityIdControl
0x1801898d3  lea     r9, [rbp+110h+value]; value
0x1801898d7  mov     rcx, rdi; context
0x1801898da  call    MI_Context_GetCustomOption_1
0x1801898df  xor     ebx, ebx
0x1801898e1  test    eax, eax
0x1801898e3  jnz     short loc_1801898F6
0x1801898e5  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x1801898ec  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x1801898f0  call    cs:__imp_CLSIDFromString
0x1801898f6  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x1801898fd  mov     [rbp+110h+var_60], rcx
0x180189904  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18018990b  mov     [rbp+110h+var_58], rax
0x180189912  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x180189919  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x180189920  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180189927  mov     ecx, 4; ControlCode
0x18018992c  call    cs:__imp_EventActivityIdControl
0x180189932  mov     eax, cs:dword_180397B68
0x180189938  lea     rcx, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018993f  cmp     eax, 5
0x180189942  jbe     short loc_180189971
0x180189944  mov     [rsp+210h+var_198], 2CEh
0x18018994c  mov     [rsp+210h+var_1A0], rcx
0x180189951  lea     rax, [rsp+210h+var_198]
0x180189956  mov     [rsp+210h+var_1E8], rax
0x18018995b  lea     rax, [rsp+210h+var_1A0]
0x180189960  mov     qword ptr [rsp+210h+var_1F0], rax
0x180189965  lea     rdx, word_1803669C2
0x18018996c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180189971  mov     [rbp+110h+self.ft], rbx
0x180189975  xor     edx, edx; Val
0x180189977  lea     r8d, [rdx+68h]; Size
0x18018997b  lea     rcx, [rbp+110h+self.classDecl]; void *
0x18018997f  call    memset_0
0x180189984  xorps   xmm0, xmm0
0x180189987  xor     eax, eax
0x180189989  movups  [rbp+110h+var_120], xmm0
0x18018998d  mov     [rbp+110h+var_110], rax
0x180189991  mov     [rbp+110h+var_190], rbx
0x180189995  lea     rcx, [rbp+110h+var_190]
0x180189999  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18018999e  mov     [rbp+110h+var_190], rbx
0x1801899a2  mov     r15d, ebx
0x1801899a5  lea     rcx, [rbp+110h+var_140]; this
0x1801899a9  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801899ae  mov     rcx, rdi; context
0x1801899b1  call    WspIsRemoteRequest
0x1801899b6  mov     r13d, eax
0x1801899b9  test    eax, eax
0x1801899bb  jnz     short loc_1801899E0
0x1801899bd  lea     rcx, [rbp+110h+var_140]; this
0x1801899c1  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801899c6  cmp     [r14+48h], bl
0x1801899ca  jz      short loc_1801899DD
0x1801899cc  mov     rcx, [r14+40h]; unsigned __int16 *
0x1801899d0  call    WspIsRemoteInstance
0x1801899d5  test    al, al
0x1801899d7  lea     r15d, [r13+1]
0x1801899db  jnz     short loc_1801899E0
0x1801899dd  mov     r15d, ebx
0x1801899e0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801899e7  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801899ec  mov     ebx, eax
0x1801899ee  test    eax, eax
0x1801899f0  jnz     loc_180189C53
0x1801899f6  mov     dword ptr [rbp+110h+var_120], 8
0x1801899fd  mov     rax, [r14+40h]
0x180189a01  mov     qword ptr [rbp+110h+var_120+8], rax
0x180189a05  mov     rbx, [rsi]
0x180189a08  lea     rcx, [rbp+110h+var_190]
0x180189a0c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180189a11  mov     [rsp+210h+var_1F0], 1; int
0x180189a19  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x180189a1d  lea     r8, [rbp+110h+var_120]; struct _SP_OBJECT_ID *
0x180189a21  mov     rdx, rdi; context
0x180189a24  mov     rcx, rbx; this
0x180189a27  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180189a2c  mov     ebx, eax
0x180189a2e  test    eax, eax
0x180189a30  jz      short loc_180189A7C
0x180189a32  mov     eax, cs:dword_180397B68
0x180189a38  cmp     eax, 2
0x180189a3b  jbe     loc_180189C47
0x180189a41  mov     [rsp+210h+var_198], ebx
0x180189a45  mov     [rbp+110h+var_178], 2EEh
0x180189a4c  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x180189a53  mov     [rsp+210h+var_1A0], rax
0x180189a58  lea     rax, [rsp+210h+var_198]
0x180189a5d  mov     [rsp+210h+var_1E0], rax
0x180189a62  lea     rax, [rbp+110h+var_178]
0x180189a66  mov     [rsp+210h+var_1E8], rax
0x180189a6b  lea     rax, [rsp+210h+var_1A0]
0x180189a70  lea     rdx, word_18036610E
0x180189a77  jmp     loc_180189C3D
0x180189a7c  mov     r8, [r14+40h]
0x180189a80  mov     rdx, rdi
0x180189a83  mov     rcx, [rsi]
0x180189a86  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180189a8b  cmp     eax, 3
0x180189a8e  jnb     short loc_180189ADD
0x180189a90  mov     ebx, 7
0x180189a95  mov     eax, cs:dword_180397B68
0x180189a9b  cmp     eax, 2
0x180189a9e  jbe     loc_180189C47
0x180189aa4  mov     dword ptr [rbp+110h+var_170], ebx
0x180189aa7  mov     dword ptr [rbp+110h+var_168], 2F8h
0x180189aae  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x180189ab5  mov     [rsp+210h+var_1A0], rax
0x180189aba  lea     rax, [rbp+110h+var_170]
0x180189abe  mov     [rsp+210h+var_1E0], rax
0x180189ac3  lea     rax, [rbp+110h+var_168]
0x180189ac7  mov     [rsp+210h+var_1E8], rax
0x180189acc  lea     rax, [rsp+210h+var_1A0]
0x180189ad1  lea     rdx, byte_180365F17
0x180189ad8  jmp     loc_180189C3D
0x180189add  test    rdi, rdi
0x180189ae0  jz      loc_180189BF7
0x180189ae6  mov     rax, [rdi]
0x180189ae9  test    rax, rax
0x180189aec  jz      loc_180189BF7
0x180189af2  lea     r8, [rbp+110h+self]
0x180189af6  lea     rdx, SPACES_StorageEnclosure_UpdateFirmware_rtti
0x180189afd  mov     rcx, rdi
0x180189b00  mov     rax, [rax+20h]
0x180189b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180189b09  mov     ebx, eax
0x180189b0b  test    eax, eax
0x180189b0d  jnz     loc_180189BFC
0x180189b13  mov     rcx, [rbp+110h+var_190]
0x180189b17  mov     rax, [rcx]
0x180189b1a  lea     rdx, [rbp+110h+self]
0x180189b1e  mov     qword ptr [rsp+210h+var_1F0], rdx
0x180189b23  mov     r9, r12
0x180189b26  mov     r8, rdi
0x180189b29  mov     edx, 80006h
0x180189b2e  mov     rax, [rax+30h]
0x180189b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180189b37  mov     ebx, eax
0x180189b39  test    eax, eax
0x180189b3b  jz      short loc_180189B85
0x180189b3d  mov     eax, cs:dword_180397B68
0x180189b43  cmp     eax, 2
0x180189b46  jbe     loc_180189C47
0x180189b4c  mov     dword ptr [rbp+110h+var_160], ebx
0x180189b4f  mov     dword ptr [rbp+110h+var_158], 30Bh
0x180189b56  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x180189b5d  mov     [rsp+210h+var_1A0], rax
0x180189b62  lea     rax, [rbp+110h+var_160]
0x180189b66  mov     [rsp+210h+var_1E0], rax
0x180189b6b  lea     rax, [rbp+110h+var_158]
0x180189b6f  mov     [rsp+210h+var_1E8], rax
0x180189b74  lea     rax, [rsp+210h+var_1A0]
0x180189b79  lea     rdx, word_18036668A
0x180189b80  jmp     loc_180189C3D
0x180189b85  mov     rax, [rdi]
0x180189b88  test    rax, rax
0x180189b8b  jz      short loc_180189BA9
0x180189b8d  lea     rdx, [rbp+110h+self]
0x180189b91  mov     rcx, rdi
0x180189b94  mov     rax, [rax+8]
0x180189b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180189b9d  mov     ebx, eax
0x180189b9f  test    eax, eax
0x180189ba1  jz      loc_180189C47
0x180189ba7  jmp     short loc_180189BB0
0x180189ba9  mov     eax, 4
0x180189bae  mov     ebx, eax
0x180189bb0  mov     ecx, eax
0x180189bb2  mov     eax, cs:dword_180397B68
0x180189bb8  cmp     eax, 2
0x180189bbb  jbe     loc_180189C47
0x180189bc1  mov     dword ptr [rbp+110h+var_150], ecx
0x180189bc4  mov     dword ptr [rbp+110h+var_188], 313h
0x180189bcb  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x180189bd2  mov     [rsp+210h+var_1A0], rax
0x180189bd7  lea     rax, [rbp+110h+var_150]
0x180189bdb  mov     [rsp+210h+var_1E0], rax
0x180189be0  lea     rax, [rbp+110h+var_188]
0x180189be4  mov     [rsp+210h+var_1E8], rax
0x180189be9  lea     rax, [rsp+210h+var_1A0]
0x180189bee  lea     rdx, byte_180366291
0x180189bf5  jmp     short loc_180189C3D
0x180189bf7  mov     ebx, 4
0x180189bfc  mov     eax, cs:dword_180397B68
0x180189c02  cmp     eax, 2
0x180189c05  jbe     short loc_180189C47
0x180189c07  mov     [rsp+210h+var_194], ebx
0x180189c0b  mov     dword ptr [rsp+210h+var_1A0], 300h
0x180189c13  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x180189c1a  mov     [rbp+110h+var_188], rax
0x180189c1e  lea     rax, [rsp+210h+var_194]
0x180189c23  mov     [rsp+210h+var_1E0], rax
0x180189c28  lea     rax, [rsp+210h+var_1A0]
0x180189c2d  mov     [rsp+210h+var_1E8], rax
0x180189c32  lea     rax, [rbp+110h+var_188]
0x180189c36  lea     rdx, byte_180365B9D
0x180189c3d  mov     qword ptr [rsp+210h+var_1F0], rax
0x180189c42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180189c47  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180189c4e  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180189c53  xor     r12d, r12d
0x180189c56  mov     [rsp+210h+var_1E8], r12; unsigned __int16 *
0x180189c5b  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x180189c5f  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x180189c63  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x180189c67  mov     rdx, [rbp+110h+var_148]; unsigned __int16 *
0x180189c6b  mov     rcx, [rbp+110h+var_180]; unsigned __int16 *
0x180189c6f  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180189c74  test    r13d, r13d
0x180189c77  jnz     loc_180189D7F
0x180189c7d  lea     rcx, [rbp+110h+var_140]; this
0x180189c81  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180189c86  mov     eax, cs:dword_180397B68
0x180189c8c  cmp     eax, 5
0x180189c8f  jbe     loc_180189D7F
0x180189c95  mov     rdx, 400000000000h
0x180189c9f  lea     rcx, dword_180397B68
0x180189ca6  call    _tlgKeywordOn
0x180189cab  test    al, al
0x180189cad  jz      loc_180189D7F
0x180189cb3  mov     [rbp+110h+var_180], r12
0x180189cb7  mov     [rbp+110h+var_148], r12
0x180189cbb  mov     [rbp+110h+var_150], r12
0x180189cbf  mov     rax, [rbp+110h+var_138]
0x180189cc3  sub     rax, [rbp+110h+var_140]
0x180189cc7  imul    rax, 3E8h
0x180189cce  xor     edx, edx
0x180189cd0  div     [rbp+110h+var_130]
0x180189cd4  mov     [rbp+110h+var_158], rax
0x180189cd8  mov     dword ptr [rsp+210h+var_1A0], ebx
0x180189cdc  mov     al, [rbp+110h+var_A0.exists]
0x180189cdf  neg     al
0x180189ce1  sbb     ecx, ecx
0x180189ce3  and     ecx, [rbp+110h+var_A0.value]
0x180189ce6  mov     [rsp+210h+var_194], ecx
0x180189cea  mov     dword ptr [rbp+110h+var_188], r15d
0x180189cee  cmp     [r14+48h], r12b
0x180189cf2  jz      short loc_180189CFA
0x180189cf4  mov     rax, [r14+40h]
0x180189cf8  jmp     short loc_180189CFD
0x180189cfa  mov     rax, r12
0x180189cfd  mov     [rbp+110h+var_160], rax
0x180189d01  lea     rax, aUpdatefirmware_0; "UpdateFirmware"
0x180189d08  mov     [rbp+110h+var_168], rax
0x180189d0c  lea     rax, aStorageenclosu; "StorageEnclosure"
0x180189d13  mov     [rbp+110h+var_170], rax
0x180189d17  lea     rax, [rbp+110h+var_180]
0x180189d1b  mov     [rsp+210h+var_1A8], rax
0x180189d20  lea     rax, [rbp+110h+var_148]
0x180189d24  mov     [rsp+210h+var_1B0], rax
0x180189d29  lea     rax, [rbp+110h+var_150]
0x180189d2d  mov     [rsp+210h+var_1B8], rax
0x180189d32  lea     rax, [rbp+110h+var_158]
0x180189d36  mov     [rsp+210h+var_1C0], rax
0x180189d3b  lea     rax, [rsp+210h+var_1A0]
0x180189d40  mov     [rsp+210h+var_1C8], rax
0x180189d45  lea     rax, [rsp+210h+var_194]
0x180189d4a  mov     [rsp+210h+var_1D0], rax
0x180189d4f  lea     rax, [rbp+110h+var_188]
0x180189d53  mov     [rsp+210h+var_1D8], rax
0x180189d58  lea     rax, [rbp+110h+var_160]
0x180189d5c  mov     [rsp+210h+var_1E0], rax
0x180189d61  lea     rax, [rbp+110h+var_168]
0x180189d65  mov     [rsp+210h+var_1E8], rax
0x180189d6a  lea     rax, [rbp+110h+var_170]
0x180189d6e  mov     qword ptr [rsp+210h+var_1F0], rax
0x180189d73  lea     rdx, word_180366056
0x180189d7a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180189d7f  lea     rcx, [rbp+110h+self]; self
  ... truncated ...
```
