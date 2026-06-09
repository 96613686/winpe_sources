# SPACES_PhysicalDisk_Invoke_UpdateFirmware

- ea: `0x18017ff20`
- end: `0x1801804bd`
- name: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- size: `1437`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x180138120`
- `0x18017ff20`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017ff9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017fffc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018048d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017ff9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017fffc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018048d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017ffc0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017ffc0`

## string_xrefs

- `0x180180391`: `UpdateFirmware`
- `0x180180008`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018011c`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018017b`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x1801801dc`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018024e`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x1801802a3`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018042b`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`

## pseudocode

```c
ULONG __fastcall SPACES_PhysicalDisk_Invoke_UpdateFirmware(
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
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v59; // [rsp+1B0h] [rbp+B0h]
  GUID v60; // [rsp+1C0h] [rbp+C0h] BYREF

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
    v40 = 1371;
    v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_PhysicalDisk_Invoke_UpdateFirmware",
      (unsigned int)qword_180362118,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v40);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
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
        v45 = 1403;
        v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180363688,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_PhysicalDisk_UpdateFirmware_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1421;
          v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&unk_180361DE0,
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
                262154,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1432;
            v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&byte_1803634D7,
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
            LODWORD(v39) = 1440;
            v43 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&word_180361D6E,
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
        LODWORD(v47) = 1413;
        v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_180362C55,
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
        v47 = "UpdateFirmware";
        v46 = "PhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)byte_180362EDB,
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
    LODWORD(v39) = 1473;
    v44 = (unsigned __int16 *)"SPACES_PhysicalDisk_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)word_180361C3A,
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
0x18017ff20  mov     [rsp-8+arg_10], rbx
0x18017ff25  push    rbp
0x18017ff26  push    rsi
0x18017ff27  push    rdi
0x18017ff28  push    r12
0x18017ff2a  push    r13
0x18017ff2c  push    r14
0x18017ff2e  push    r15
0x18017ff30  lea     rbp, [rsp-0E0h]
0x18017ff38  sub     rsp, 1E0h
0x18017ff3f  mov     rax, cs:__security_cookie
0x18017ff46  xor     rax, rsp
0x18017ff49  mov     [rbp+110h+var_40], rax
0x18017ff50  mov     [rbp+110h+var_180], r9
0x18017ff54  mov     rdi, rdx
0x18017ff57  mov     rsi, rcx
0x18017ff5a  mov     rax, [rbp+110h+arg_20]
0x18017ff61  mov     [rbp+110h+var_148], rax
0x18017ff65  mov     r14, [rbp+110h+arg_28]
0x18017ff6c  mov     r12, [rbp+110h+arg_30]
0x18017ff73  xorps   xmm0, xmm0
0x18017ff76  xor     eax, eax
0x18017ff78  movups  xmmword ptr [rbp+110h+value], xmm0
0x18017ff7c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18017ff80  mov     qword ptr [rbp+110h+value+20h], rax
0x18017ff84  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017ff8b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18017ff93  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18017ff9a  lea     ecx, [rax+1]; ControlCode
0x18017ff9d  call    cs:__imp_EventActivityIdControl
0x18017ffa3  lea     r9, [rbp+110h+value]; value
0x18017ffa7  mov     rcx, rdi; context
0x18017ffaa  call    MI_Context_GetCustomOption_1
0x18017ffaf  xor     ebx, ebx
0x18017ffb1  test    eax, eax
0x18017ffb3  jnz     short loc_18017FFC6
0x18017ffb5  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18017ffbc  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18017ffc0  call    cs:__imp_CLSIDFromString
0x18017ffc6  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18017ffcd  mov     [rbp+110h+var_60], rcx
0x18017ffd4  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18017ffdb  mov     [rbp+110h+var_58], rax
0x18017ffe2  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18017ffe9  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18017fff0  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18017fff7  mov     ecx, 4; ControlCode
0x18017fffc  call    cs:__imp_EventActivityIdControl
0x180180002  mov     eax, cs:dword_180397B68
0x180180008  lea     rcx, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x18018000f  cmp     eax, 5
0x180180012  jbe     short loc_180180041
0x180180014  mov     [rsp+210h+var_198], 55Bh
0x18018001c  mov     [rsp+210h+var_1A0], rcx
0x180180021  lea     rax, [rsp+210h+var_198]
0x180180026  mov     [rsp+210h+var_1E8], rax
0x18018002b  lea     rax, [rsp+210h+var_1A0]
0x180180030  mov     qword ptr [rsp+210h+var_1F0], rax
0x180180035  lea     rdx, qword_180362118
0x18018003c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180180041  mov     [rbp+110h+instance.ft], rbx
0x180180045  xor     edx, edx; Val
0x180180047  lea     r8d, [rdx+68h]; Size
0x18018004b  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18018004f  call    memset_0
0x180180054  xorps   xmm0, xmm0
0x180180057  xor     eax, eax
0x180180059  movups  [rbp+110h+var_120], xmm0
0x18018005d  mov     [rbp+110h+var_110], rax
0x180180061  mov     [rbp+110h+var_190], rbx
0x180180065  lea     rcx, [rbp+110h+var_190]
0x180180069  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18018006e  mov     [rbp+110h+var_190], rbx
0x180180072  mov     r15d, ebx
0x180180075  lea     rcx, [rbp+110h+var_140]; this
0x180180079  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18018007e  mov     rcx, rdi; context
0x180180081  call    WspIsRemoteRequest
0x180180086  mov     r13d, eax
0x180180089  test    eax, eax
0x18018008b  jnz     short loc_1801800B0
0x18018008d  lea     rcx, [rbp+110h+var_140]; this
0x180180091  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180180096  cmp     [r14+48h], bl
0x18018009a  jz      short loc_1801800AD
0x18018009c  mov     rcx, [r14+40h]; unsigned __int16 *
0x1801800a0  call    WspIsRemoteInstance
0x1801800a5  test    al, al
0x1801800a7  lea     r15d, [r13+1]
0x1801800ab  jnz     short loc_1801800B0
0x1801800ad  mov     r15d, ebx
0x1801800b0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801800b7  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801800bc  mov     ebx, eax
0x1801800be  test    eax, eax
0x1801800c0  jnz     loc_1801802E3
0x1801800c6  mov     dword ptr [rbp+110h+var_120], 4
0x1801800cd  mov     rax, [r14+40h]
0x1801800d1  mov     qword ptr [rbp+110h+var_120+8], rax
0x1801800d5  mov     rbx, [rsi]
0x1801800d8  lea     rcx, [rbp+110h+var_190]
0x1801800dc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801800e1  mov     [rsp+210h+var_1F0], 1; int
0x1801800e9  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x1801800ed  lea     r8, [rbp+110h+var_120]; struct _SP_OBJECT_ID *
0x1801800f1  mov     rdx, rdi; context
0x1801800f4  mov     rcx, rbx; this
0x1801800f7  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x1801800fc  mov     ebx, eax
0x1801800fe  test    eax, eax
0x180180100  jz      short loc_18018014C
0x180180102  mov     eax, cs:dword_180397B68
0x180180108  cmp     eax, 2
0x18018010b  jbe     loc_1801802D7
0x180180111  mov     [rsp+210h+var_198], ebx
0x180180115  mov     [rbp+110h+var_178], 57Bh
0x18018011c  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180180123  mov     [rsp+210h+var_1A0], rax
0x180180128  lea     rax, [rsp+210h+var_198]
0x18018012d  mov     [rsp+210h+var_1E0], rax
0x180180132  lea     rax, [rbp+110h+var_178]
0x180180136  mov     [rsp+210h+var_1E8], rax
0x18018013b  lea     rax, [rsp+210h+var_1A0]
0x180180140  lea     rdx, unk_180363688
0x180180147  jmp     loc_1801802CD
0x18018014c  mov     r8, [r14+40h]
0x180180150  mov     rdx, rdi
0x180180153  mov     rcx, [rsi]
0x180180156  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18018015b  test    eax, eax
0x18018015d  jnz     short loc_1801801AA
0x18018015f  lea     ebx, [rax+7]
0x180180162  mov     eax, cs:dword_180397B68
0x180180168  cmp     eax, 2
0x18018016b  jbe     loc_1801802D7
0x180180171  mov     dword ptr [rbp+110h+var_170], ebx
0x180180174  mov     dword ptr [rbp+110h+var_168], 585h
0x18018017b  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180180182  mov     [rsp+210h+var_1A0], rax
0x180180187  lea     rax, [rbp+110h+var_170]
0x18018018b  mov     [rsp+210h+var_1E0], rax
0x180180190  lea     rax, [rbp+110h+var_168]
0x180180194  mov     [rsp+210h+var_1E8], rax
0x180180199  lea     rax, [rsp+210h+var_1A0]
0x18018019e  lea     rdx, byte_180362C55
0x1801801a5  jmp     loc_1801802CD
0x1801801aa  lea     r8, [rbp+110h+instance]; instance
0x1801801ae  lea     rdx, SPACES_PhysicalDisk_UpdateFirmware_rtti; methodDecl
0x1801801b5  mov     rcx, rdi; context
0x1801801b8  call    MI_Context_ConstructParameters
0x1801801bd  mov     ebx, eax
0x1801801bf  test    eax, eax
0x1801801c1  jz      short loc_18018020B
0x1801801c3  mov     eax, cs:dword_180397B68
0x1801801c9  cmp     eax, 2
0x1801801cc  jbe     loc_1801802D7
0x1801801d2  mov     dword ptr [rbp+110h+var_160], ebx
0x1801801d5  mov     dword ptr [rbp+110h+var_158], 58Dh
0x1801801dc  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801801e3  mov     [rsp+210h+var_1A0], rax
0x1801801e8  lea     rax, [rbp+110h+var_160]
0x1801801ec  mov     [rsp+210h+var_1E0], rax
0x1801801f1  lea     rax, [rbp+110h+var_158]
0x1801801f5  mov     [rsp+210h+var_1E8], rax
0x1801801fa  lea     rax, [rsp+210h+var_1A0]
0x1801801ff  lea     rdx, unk_180361DE0
0x180180206  jmp     loc_1801802CD
0x18018020b  mov     rcx, [rbp+110h+var_190]
0x18018020f  mov     rax, [rcx]
0x180180212  lea     rdx, [rbp+110h+instance]
0x180180216  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18018021b  mov     r9, r12
0x18018021e  mov     r8, rdi
0x180180221  mov     edx, 4000Ah
0x180180226  mov     rax, [rax+30h]
0x18018022a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018022f  mov     ebx, eax
0x180180231  test    eax, eax
0x180180233  jz      short loc_18018027A
0x180180235  mov     eax, cs:dword_180397B68
0x18018023b  cmp     eax, 2
0x18018023e  jbe     loc_1801802D7
0x180180244  mov     dword ptr [rbp+110h+var_150], ebx
0x180180247  mov     dword ptr [rbp+110h+var_188], 598h
0x18018024e  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180180255  mov     [rsp+210h+var_1A0], rax
0x18018025a  lea     rax, [rbp+110h+var_150]
0x18018025e  mov     [rsp+210h+var_1E0], rax
0x180180263  lea     rax, [rbp+110h+var_188]
0x180180267  mov     [rsp+210h+var_1E8], rax
0x18018026c  lea     rax, [rsp+210h+var_1A0]
0x180180271  lea     rdx, byte_1803634D7
0x180180278  jmp     short loc_1801802CD
0x18018027a  lea     rdx, [rbp+110h+instance]
0x18018027e  mov     rcx, rdi; self
0x180180281  call    MI_Instance_Destruct
0x180180286  mov     ebx, eax
0x180180288  test    eax, eax
0x18018028a  jz      short loc_1801802D7
0x18018028c  mov     eax, cs:dword_180397B68
0x180180292  cmp     eax, 2
0x180180295  jbe     short loc_1801802D7
0x180180297  mov     [rsp+210h+var_194], ebx
0x18018029b  mov     dword ptr [rsp+210h+var_1A0], 5A0h
0x1801802a3  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801802aa  mov     [rbp+110h+var_188], rax
0x1801802ae  lea     rax, [rsp+210h+var_194]
0x1801802b3  mov     [rsp+210h+var_1E0], rax
0x1801802b8  lea     rax, [rsp+210h+var_1A0]
0x1801802bd  mov     [rsp+210h+var_1E8], rax
0x1801802c2  lea     rax, [rbp+110h+var_188]
0x1801802c6  lea     rdx, word_180361D6E
0x1801802cd  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801802d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801802d7  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801802de  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801802e3  xor     r12d, r12d
0x1801802e6  mov     [rsp+210h+var_1E8], r12; unsigned __int16 *
0x1801802eb  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x1801802ef  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x1801802f3  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x1801802f7  mov     rdx, [rbp+110h+var_148]; unsigned __int16 *
0x1801802fb  mov     rcx, [rbp+110h+var_180]; unsigned __int16 *
0x1801802ff  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180180304  test    r13d, r13d
0x180180307  jnz     loc_18018040F
0x18018030d  lea     rcx, [rbp+110h+var_140]; this
0x180180311  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180180316  mov     eax, cs:dword_180397B68
0x18018031c  cmp     eax, 5
0x18018031f  jbe     loc_18018040F
0x180180325  mov     rdx, 400000000000h
0x18018032f  lea     rcx, dword_180397B68
0x180180336  call    _tlgKeywordOn
0x18018033b  test    al, al
0x18018033d  jz      loc_18018040F
0x180180343  mov     [rbp+110h+var_180], r12
0x180180347  mov     [rbp+110h+var_148], r12
0x18018034b  mov     [rbp+110h+var_150], r12
0x18018034f  mov     rax, [rbp+110h+var_138]
0x180180353  sub     rax, [rbp+110h+var_140]
0x180180357  imul    rax, 3E8h
0x18018035e  xor     edx, edx
0x180180360  div     [rbp+110h+var_130]
0x180180364  mov     [rbp+110h+var_158], rax
0x180180368  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18018036c  mov     al, [rbp+110h+var_A0.exists]
0x18018036f  neg     al
0x180180371  sbb     ecx, ecx
0x180180373  and     ecx, [rbp+110h+var_A0.value]
0x180180376  mov     [rsp+210h+var_194], ecx
0x18018037a  mov     dword ptr [rbp+110h+var_188], r15d
0x18018037e  cmp     [r14+48h], r12b
0x180180382  jz      short loc_18018038A
0x180180384  mov     rax, [r14+40h]
0x180180388  jmp     short loc_18018038D
0x18018038a  mov     rax, r12
0x18018038d  mov     [rbp+110h+var_160], rax
0x180180391  lea     rax, aUpdatefirmware_0; "UpdateFirmware"
0x180180398  mov     [rbp+110h+var_168], rax
0x18018039c  lea     rax, aPhysicaldisk_0; "PhysicalDisk"
0x1801803a3  mov     [rbp+110h+var_170], rax
0x1801803a7  lea     rax, [rbp+110h+var_180]
0x1801803ab  mov     [rsp+210h+var_1A8], rax
0x1801803b0  lea     rax, [rbp+110h+var_148]
0x1801803b4  mov     [rsp+210h+var_1B0], rax
0x1801803b9  lea     rax, [rbp+110h+var_150]
0x1801803bd  mov     [rsp+210h+var_1B8], rax
0x1801803c2  lea     rax, [rbp+110h+var_158]
0x1801803c6  mov     [rsp+210h+var_1C0], rax
0x1801803cb  lea     rax, [rsp+210h+var_1A0]
0x1801803d0  mov     [rsp+210h+var_1C8], rax
0x1801803d5  lea     rax, [rsp+210h+var_194]
0x1801803da  mov     [rsp+210h+var_1D0], rax
0x1801803df  lea     rax, [rbp+110h+var_188]
0x1801803e3  mov     [rsp+210h+var_1D8], rax
0x1801803e8  lea     rax, [rbp+110h+var_160]
0x1801803ec  mov     [rsp+210h+var_1E0], rax
0x1801803f1  lea     rax, [rbp+110h+var_168]
0x1801803f5  mov     [rsp+210h+var_1E8], rax
0x1801803fa  lea     rax, [rbp+110h+var_170]
0x1801803fe  mov     qword ptr [rsp+210h+var_1F0], rax
0x180180403  lea     rdx, byte_180362EDB
0x18018040a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18018040f  lea     rcx, [rbp+110h+instance]; self
0x180180413  call    MI_Instance_Destruct
0x180180418  mov     eax, cs:dword_180397B68
0x18018041e  cmp     eax, 5
0x180180421  jbe     short loc_180180455
0x180180423  mov     dword ptr [rsp+210h+var_1A0], 5C1h
0x18018042b  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180180432  mov     [rbp+110h+var_180], rax
0x180180436  lea     rax, [rsp+210h+var_1A0]
0x18018043b  mov     [rsp+210h+var_1E8], rax
0x180180440  lea     rax, [rbp+110h+var_180]
0x180180444  mov     qword ptr [rsp+210h+var_1F0], rax
0x180180449  lea     rdx, word_180361C3A
0x180180450  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180180455  test    rdi, rdi
0x180180458  jz      short loc_18018046F
  ... truncated ...
```
