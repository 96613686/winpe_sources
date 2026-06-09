# SPACES_StorageTier_Invoke_RemoveStorageFaultDomain

- ea: `0x180178010`
- end: `0x180178579`
- name: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- size: `1385`
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
- `0x1800175f0`
- `0x18001a5e4`
- `0x18001afd0`
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180137a24`
- `0x180138120`
- `0x180178010`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017808a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801780d1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180178549`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017808a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801780d1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180178549`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801780aa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801780aa`

## string_xrefs

- `0x180178450`: `RemoveStorageFaultDomain`
- `0x1801780dd`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x1801781d9`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017823b`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017829c`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017830e`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x180178363`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x1801784ea`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`

## pseudocode

```c
ULONG __fastcall SPACES_StorageTier_Invoke_RemoveStorageFaultDomain(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  int v10; // r15d
  const MI_Char *v11; // rdx
  MI_Type *v12; // r8
  int v13; // r8d
  int v14; // r9d
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
  const char *v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v51[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v52; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h]
  MI_Value value; // [rsp+100h] [rbp+0h] BYREF
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF
  GUID v56; // [rsp+138h] [rbp+38h]
  GUID v57; // [rsp+148h] [rbp+48h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v59; // [rsp+1A0h] [rbp+A0h] BYREF

  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  v10 = 1;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v11, v12, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v56 = ActivityId;
  v57 = ActivityId;
  EventActivityIdControl(4u, &v57);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v40 = 1245;
    v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageTier_Invoke_RemoveStorageFaultDomain",
      (unsigned int)word_1803607C2,
      v13,
      v14,
      (__int64)&v39,
      (__int64)&v40);
  }
  v52 = 0;
  v53 = 0;
  memset_0(&instance, 0, 0x80u);
  CSmTimer::CSmTimer((CSmTimer *)v51);
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  CSmTimer::Start((CSmTimer *)v51);
  if ( !a6[4].exists || !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v10 = 0;
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v52) = 12;
    *((_QWORD *)&v52 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v52, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v40 = v15;
        LODWORD(v45) = 1274;
        v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&word_180360EE6,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageTier_RemoveStorageFaultDomain_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1291;
          v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)word_18035FD8A,
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
                786442,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1302;
            v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&word_1803610DE,
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
            LODWORD(v39) = 1310;
            v43 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&unk_180360390,
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
        LODWORD(v47) = 1283;
        v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&byte_180361117,
          v21,
          v22,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v46);
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(a4, v44, a6 + 4, &v59, v15, 0);
  CSmTimer::Stop((CSmTimer *)v51);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v44 = 0;
    v50 = 0;
    v49 = 0;
    v48 = (unsigned __int64)(1000LL * (v51[1] - v51[0])) / v51[2];
    LODWORD(v39) = v15;
    v41 = v59.exists != 0 ? v59.value : 0;
    LODWORD(v43) = v10;
    if ( a6[4].exists )
      v34 = a6[4].value;
    else
      v34 = 0;
    v47 = v34;
    v46 = "RemoveStorageFaultDomain";
    v45 = "StorageTier";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v59.exists != 0 ? v59.value : 0,
      (unsigned int)&unk_1803602D8,
      v32,
      v33,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v41,
      (__int64)&v39,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v50,
      (__int64)&v44);
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v39) = 1344;
    v44 = (unsigned __int16 *)"SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&dword_180361504,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v39);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  CSmTimer::~CSmTimer((CSmTimer *)v51);
  return EventActivityIdControl(4u, &v57);
}

```

## disassembly

```asm
0x180178010  mov     [rsp-8+arg_10], rbx
0x180178015  push    rbp
0x180178016  push    rsi
0x180178017  push    rdi
0x180178018  push    r12
0x18017801a  push    r13
0x18017801c  push    r14
0x18017801e  push    r15
0x180178020  lea     rbp, [rsp-0F0h]
0x180178028  sub     rsp, 1F0h
0x18017802f  mov     rax, cs:__security_cookie
0x180178036  xor     rax, rsp
0x180178039  mov     [rbp+120h+var_40], rax
0x180178040  mov     r13, r9
0x180178043  mov     rdi, rdx
0x180178046  mov     rsi, rcx
0x180178049  mov     rax, [rbp+120h+arg_20]
0x180178050  mov     [rbp+120h+var_190], rax
0x180178054  mov     r14, [rbp+120h+arg_28]
0x18017805b  mov     r12, [rbp+120h+arg_30]
0x180178062  xorps   xmm0, xmm0
0x180178065  xor     eax, eax
0x180178067  movups  xmmword ptr [rbp+120h+value], xmm0
0x18017806b  movups  xmmword ptr [rbp+120h+value+10h], xmm0
0x18017806f  mov     qword ptr [rbp+120h+value+20h], rax
0x180178073  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017807a  movdqu  xmmword ptr [rbp+120h+ActivityId.Data1], xmm0
0x18017807f  lea     rdx, [rbp+120h+ActivityId]; ActivityId
0x180178083  lea     r15d, [rax+1]
0x180178087  mov     ecx, r15d; ControlCode
0x18017808a  call    cs:__imp_EventActivityIdControl
0x180178090  lea     r9, [rbp+120h+value]; value
0x180178094  mov     rcx, rdi; context
0x180178097  call    MI_Context_GetCustomOption_1
0x18017809c  xor     ebx, ebx
0x18017809e  test    eax, eax
0x1801780a0  jnz     short loc_1801780B0
0x1801780a2  lea     rdx, [rbp+120h+ActivityId]; pclsid
0x1801780a6  mov     rcx, qword ptr [rbp+120h+value]; lpsz
0x1801780aa  call    cs:__imp_CLSIDFromString
0x1801780b0  mov     rcx, qword ptr [rbp+120h+ActivityId.Data1]
0x1801780b4  mov     [rbp+120h+var_E8], rcx
0x1801780b8  mov     rax, qword ptr [rbp+120h+ActivityId.Data4]
0x1801780bc  mov     [rbp+120h+var_E0], rax
0x1801780c0  mov     qword ptr [rbp+120h+var_D8.Data1], rcx
0x1801780c4  mov     qword ptr [rbp+120h+var_D8.Data4], rax
0x1801780c8  lea     rdx, [rbp+120h+var_D8]; ActivityId
0x1801780cc  mov     ecx, 4; ControlCode
0x1801780d1  call    cs:__imp_EventActivityIdControl
0x1801780d7  mov     eax, cs:dword_180397B68
0x1801780dd  lea     rcx, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x1801780e4  cmp     eax, 5
0x1801780e7  jbe     short loc_180178116
0x1801780e9  mov     [rsp+220h+var_1A8], 4DDh
0x1801780f1  mov     [rsp+220h+var_1B0], rcx
0x1801780f6  lea     rax, [rsp+220h+var_1A8]
0x1801780fb  mov     [rsp+220h+var_1F8], rax
0x180178100  lea     rax, [rsp+220h+var_1B0]
0x180178105  mov     qword ptr [rsp+220h+var_200], rax
0x18017810a  lea     rdx, word_1803607C2
0x180178111  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180178116  xorps   xmm0, xmm0
0x180178119  xor     eax, eax
0x18017811b  movups  [rbp+120h+var_138], xmm0
0x18017811f  mov     [rbp+120h+var_128], rax
0x180178123  xor     edx, edx; Val
0x180178125  mov     r8d, 80h; Size
0x18017812b  lea     rcx, [rbp+120h+instance]; void *
0x18017812f  call    memset_0
0x180178134  lea     rcx, [rbp+120h+var_158]; this
0x180178138  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18017813d  mov     [rbp+120h+var_1A0], rbx
0x180178141  lea     rcx, [rbp+120h+var_1A0]
0x180178145  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017814a  mov     [rbp+120h+var_1A0], rbx
0x18017814e  lea     rcx, [rbp+120h+var_158]; this
0x180178152  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180178157  cmp     [r14+48h], bl
0x18017815b  jz      short loc_18017816A
0x18017815d  mov     rcx, [r14+40h]; unsigned __int16 *
0x180178161  call    WspIsRemoteInstance
0x180178166  test    al, al
0x180178168  jnz     short loc_18017816D
0x18017816a  mov     r15d, ebx
0x18017816d  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180178174  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180178179  mov     ebx, eax
0x18017817b  test    eax, eax
0x18017817d  jnz     loc_1801783A3
0x180178183  mov     dword ptr [rbp+120h+var_138], 0Ch
0x18017818a  mov     rax, [r14+40h]
0x18017818e  mov     qword ptr [rbp+120h+var_138+8], rax
0x180178192  mov     rbx, [rsi]
0x180178195  lea     rcx, [rbp+120h+var_1A0]
0x180178199  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017819e  mov     [rsp+220h+var_200], 1; int
0x1801781a6  lea     r9, [rbp+120h+var_1A0]; struct ISpWmiObject **
0x1801781aa  lea     r8, [rbp+120h+var_138]; struct _SP_OBJECT_ID *
0x1801781ae  mov     rdx, rdi; context
0x1801781b1  mov     rcx, rbx; this
0x1801781b4  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x1801781b9  mov     ebx, eax
0x1801781bb  test    eax, eax
0x1801781bd  jz      short loc_180178209
0x1801781bf  mov     eax, cs:dword_180397B68
0x1801781c5  cmp     eax, 2
0x1801781c8  jbe     loc_180178397
0x1801781ce  mov     [rsp+220h+var_1A8], ebx
0x1801781d2  mov     dword ptr [rbp+120h+var_188], 4FAh
0x1801781d9  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x1801781e0  mov     [rsp+220h+var_1B0], rax
0x1801781e5  lea     rax, [rsp+220h+var_1A8]
0x1801781ea  mov     [rsp+220h+var_1F0], rax
0x1801781ef  lea     rax, [rbp+120h+var_188]
0x1801781f3  mov     [rsp+220h+var_1F8], rax
0x1801781f8  lea     rax, [rsp+220h+var_1B0]
0x1801781fd  lea     rdx, word_180360EE6
0x180178204  jmp     loc_18017838D
0x180178209  mov     r8, [r14+40h]
0x18017820d  mov     rdx, rdi
0x180178210  mov     rcx, [rsi]
0x180178213  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180178218  cmp     eax, 3
0x18017821b  jnb     short loc_18017826A
0x18017821d  mov     ebx, 7
0x180178222  mov     eax, cs:dword_180397B68
0x180178228  cmp     eax, 2
0x18017822b  jbe     loc_180178397
0x180178231  mov     dword ptr [rbp+120h+var_180], ebx
0x180178234  mov     dword ptr [rbp+120h+var_178], 503h
0x18017823b  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x180178242  mov     [rsp+220h+var_1B0], rax
0x180178247  lea     rax, [rbp+120h+var_180]
0x18017824b  mov     [rsp+220h+var_1F0], rax
0x180178250  lea     rax, [rbp+120h+var_178]
0x180178254  mov     [rsp+220h+var_1F8], rax
0x180178259  lea     rax, [rsp+220h+var_1B0]
0x18017825e  lea     rdx, byte_180361117
0x180178265  jmp     loc_18017838D
0x18017826a  lea     r8, [rbp+120h+instance]; instance
0x18017826e  lea     rdx, SPACES_StorageTier_RemoveStorageFaultDomain_rtti; methodDecl
0x180178275  mov     rcx, rdi; context
0x180178278  call    MI_Context_ConstructParameters
0x18017827d  mov     ebx, eax
0x18017827f  test    eax, eax
0x180178281  jz      short loc_1801782CB
0x180178283  mov     eax, cs:dword_180397B68
0x180178289  cmp     eax, 2
0x18017828c  jbe     loc_180178397
0x180178292  mov     dword ptr [rbp+120h+var_170], ebx
0x180178295  mov     dword ptr [rbp+120h+var_168], 50Bh
0x18017829c  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x1801782a3  mov     [rsp+220h+var_1B0], rax
0x1801782a8  lea     rax, [rbp+120h+var_170]
0x1801782ac  mov     [rsp+220h+var_1F0], rax
0x1801782b1  lea     rax, [rbp+120h+var_168]
0x1801782b5  mov     [rsp+220h+var_1F8], rax
0x1801782ba  lea     rax, [rsp+220h+var_1B0]
0x1801782bf  lea     rdx, word_18035FD8A
0x1801782c6  jmp     loc_18017838D
0x1801782cb  mov     rcx, [rbp+120h+var_1A0]
0x1801782cf  mov     rax, [rcx]
0x1801782d2  lea     rdx, [rbp+120h+instance]
0x1801782d6  mov     qword ptr [rsp+220h+var_200], rdx
0x1801782db  mov     r9, r12
0x1801782de  mov     r8, rdi
0x1801782e1  mov     edx, 0C000Ah
0x1801782e6  mov     rax, [rax+30h]
0x1801782ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801782ef  mov     ebx, eax
0x1801782f1  test    eax, eax
0x1801782f3  jz      short loc_18017833A
0x1801782f5  mov     eax, cs:dword_180397B68
0x1801782fb  cmp     eax, 2
0x1801782fe  jbe     loc_180178397
0x180178304  mov     dword ptr [rbp+120h+var_160], ebx
0x180178307  mov     dword ptr [rbp+120h+var_198], 516h
0x18017830e  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x180178315  mov     [rsp+220h+var_1B0], rax
0x18017831a  lea     rax, [rbp+120h+var_160]
0x18017831e  mov     [rsp+220h+var_1F0], rax
0x180178323  lea     rax, [rbp+120h+var_198]
0x180178327  mov     [rsp+220h+var_1F8], rax
0x18017832c  lea     rax, [rsp+220h+var_1B0]
0x180178331  lea     rdx, word_1803610DE
0x180178338  jmp     short loc_18017838D
0x18017833a  lea     rdx, [rbp+120h+instance]
0x18017833e  mov     rcx, rdi; self
0x180178341  call    MI_Instance_Destruct
0x180178346  mov     ebx, eax
0x180178348  test    eax, eax
0x18017834a  jz      short loc_180178397
0x18017834c  mov     eax, cs:dword_180397B68
0x180178352  cmp     eax, 2
0x180178355  jbe     short loc_180178397
0x180178357  mov     [rsp+220h+var_1A4], ebx
0x18017835b  mov     dword ptr [rsp+220h+var_1B0], 51Eh
0x180178363  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017836a  mov     [rbp+120h+var_198], rax
0x18017836e  lea     rax, [rsp+220h+var_1A4]
0x180178373  mov     [rsp+220h+var_1F0], rax
0x180178378  lea     rax, [rsp+220h+var_1B0]
0x18017837d  mov     [rsp+220h+var_1F8], rax
0x180178382  lea     rax, [rbp+120h+var_198]
0x180178386  lea     rdx, unk_180360390
0x18017838d  mov     qword ptr [rsp+220h+var_200], rax
0x180178392  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180178397  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18017839e  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801783a3  xor     r12d, r12d
0x1801783a6  mov     [rsp+220h+var_1F8], r12; unsigned __int16 *
0x1801783ab  mov     [rsp+220h+var_200], ebx; enum _MI_Result
0x1801783af  lea     r9, [rbp+120h+var_80]; struct _MI_ConstUint32Field *
0x1801783b6  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x1801783ba  mov     rdx, [rbp+120h+var_190]; unsigned __int16 *
0x1801783be  mov     rcx, r13; unsigned __int16 *
0x1801783c1  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801783c6  lea     rcx, [rbp+120h+var_158]; this
0x1801783ca  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801783cf  mov     eax, cs:dword_180397B68
0x1801783d5  cmp     eax, 5
0x1801783d8  jbe     loc_1801784CE
0x1801783de  mov     rdx, 400000000000h
0x1801783e8  lea     rcx, dword_180397B68
0x1801783ef  call    _tlgKeywordOn
0x1801783f4  test    al, al
0x1801783f6  jz      loc_1801784CE
0x1801783fc  mov     [rbp+120h+var_190], r12
0x180178400  mov     [rbp+120h+var_160], r12
0x180178404  mov     [rbp+120h+var_168], r12
0x180178408  mov     rax, [rbp+120h+var_150]
0x18017840c  sub     rax, [rbp+120h+var_158]
0x180178410  imul    rax, 3E8h
0x180178417  xor     edx, edx
0x180178419  div     [rbp+120h+var_148]
0x18017841d  mov     [rbp+120h+var_170], rax
0x180178421  mov     dword ptr [rsp+220h+var_1B0], ebx
0x180178425  mov     al, [rbp+120h+var_80.exists]
0x18017842b  neg     al
0x18017842d  sbb     ecx, ecx
0x18017842f  and     ecx, [rbp+120h+var_80.value]
0x180178435  mov     [rsp+220h+var_1A4], ecx
0x180178439  mov     dword ptr [rbp+120h+var_198], r15d
0x18017843d  cmp     [r14+48h], r12b
0x180178441  jz      short loc_180178449
0x180178443  mov     rax, [r14+40h]
0x180178447  jmp     short loc_18017844C
0x180178449  mov     rax, r12
0x18017844c  mov     [rbp+120h+var_178], rax
0x180178450  lea     rax, aRemovestoragef_0; "RemoveStorageFaultDomain"
0x180178457  mov     [rbp+120h+var_180], rax
0x18017845b  lea     rax, aStoragetier; "StorageTier"
0x180178462  mov     [rbp+120h+var_188], rax
0x180178466  lea     rax, [rbp+120h+var_190]
0x18017846a  mov     [rsp+220h+var_1B8], rax
0x18017846f  lea     rax, [rbp+120h+var_160]
0x180178473  mov     [rsp+220h+var_1C0], rax
0x180178478  lea     rax, [rbp+120h+var_168]
0x18017847c  mov     [rsp+220h+var_1C8], rax
0x180178481  lea     rax, [rbp+120h+var_170]
0x180178485  mov     [rsp+220h+var_1D0], rax
0x18017848a  lea     rax, [rsp+220h+var_1B0]
0x18017848f  mov     [rsp+220h+var_1D8], rax
0x180178494  lea     rax, [rsp+220h+var_1A4]
0x180178499  mov     [rsp+220h+var_1E0], rax
0x18017849e  lea     rax, [rbp+120h+var_198]
0x1801784a2  mov     [rsp+220h+var_1E8], rax
0x1801784a7  lea     rax, [rbp+120h+var_178]
0x1801784ab  mov     [rsp+220h+var_1F0], rax
0x1801784b0  lea     rax, [rbp+120h+var_180]
0x1801784b4  mov     [rsp+220h+var_1F8], rax
0x1801784b9  lea     rax, [rbp+120h+var_188]
0x1801784bd  mov     qword ptr [rsp+220h+var_200], rax
0x1801784c2  lea     rdx, unk_1803602D8
0x1801784c9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801784ce  lea     rcx, [rbp+120h+instance]; self
0x1801784d2  call    MI_Instance_Destruct
0x1801784d7  mov     eax, cs:dword_180397B68
0x1801784dd  cmp     eax, 5
0x1801784e0  jbe     short loc_180178514
0x1801784e2  mov     dword ptr [rsp+220h+var_1B0], 540h
0x1801784ea  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x1801784f1  mov     [rbp+120h+var_190], rax
0x1801784f5  lea     rax, [rsp+220h+var_1B0]
0x1801784fa  mov     [rsp+220h+var_1F8], rax
0x1801784ff  lea     rax, [rbp+120h+var_190]
0x180178503  mov     qword ptr [rsp+220h+var_200], rax
0x180178508  lea     rdx, dword_180361504
0x18017850f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180178514  test    rdi, rdi
0x180178517  jz      short loc_18017852E
0x180178519  mov     rax, [rdi]
0x18017851c  test    rax, rax
0x18017851f  jz      short loc_18017852E
0x180178521  mov     edx, ebx
0x180178523  mov     rcx, rdi
0x180178526  mov     rax, [rax]
0x180178529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017852e  lea     rcx, [rbp+120h+var_1A0]
0x180178532  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
  ... truncated ...
```
