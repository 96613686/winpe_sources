# SPACES_StorageSubsystem_Invoke_CreateStoragePool2

- ea: `0x18016ca50`
- end: `0x18016d0d8`
- name: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- size: `1672`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800047c0`
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
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x18007f384`
- `0x180137a24`
- `0x180138120`
- `0x18016ca50`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016cabe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016cb1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016d0a8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016cabe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016cb1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016d0a8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016cae1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016cae1`

## string_xrefs

- `0x18016cb29`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016cc41`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016cc9e`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016cd00`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016cdb2`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016ce8a`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016d047`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x18016cfa4`: `CreateStoragePool`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateStoragePool2(
        CSpProvider **a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r8d
  int v12; // r9d
  enum _MI_Result v13; // r15d
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
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rax
  __int64 v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v43; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v44; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v45; // [rsp+90h] [rbp-70h] BYREF
  const char *v46; // [rsp+98h] [rbp-68h] BYREF
  const char *v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  const char *v50; // [rsp+B8h] [rbp-48h] BYREF
  const unsigned __int16 *v51; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v52; // [rsp+C8h] [rbp-38h] BYREF
  const char *v53; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v54[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v57; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  int v60; // [rsp+1C0h] [rbp+C0h]
  char v61; // [rsp+1C4h] [rbp+C4h]
  struct _MI_Instance *v62; // [rsp+270h] [rbp+170h]
  char v63; // [rsp+278h] [rbp+178h]
  struct _MI_Instance *v64; // [rsp+280h] [rbp+180h]
  char v65; // [rsp+288h] [rbp+188h]
  GUID ActivityId; // [rsp+2A0h] [rbp+1A0h] BYREF
  GUID v67; // [rsp+2B0h] [rbp+1B0h]
  GUID v68; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v67 = ActivityId;
  v68 = ActivityId;
  EventActivityIdControl(4u, &v68);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v46) = 255;
    v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageSubsystem_Invoke_CreateStoragePool2",
      (unsigned int)byte_18035D519,
      v11,
      v12,
      (__int64)&v42,
      (__int64)&v46);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x118u);
  v55 = 0;
  v56 = 0;
  v45 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
  v45 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v54);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v54);
    if ( !*(_BYTE *)(a6 + 72)
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64))) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v55) = 13;
    *((_QWORD *)&v55 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v55, &v45, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v46) = v15;
        LODWORD(v48) = 287;
        v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_18035CDFB,
          v18,
          v19,
          (__int64)&v42,
          (__int64)&v48,
          (__int64)&v46);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateStoragePool2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v51) = v15;
          LODWORD(v52) = 306;
          v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)word_18035C942,
            v24,
            v25,
            (__int64)&v42,
            (__int64)&v52,
            (__int64)&v51);
        }
      }
      else
      {
        if ( v13 && *(_BYTE *)(a7 + 128) && *(_DWORD *)(a7 + 120) > 0x200u )
        {
          v60 = 5;
          v61 = 1;
          PostExtendedStatus(a2, &instance, 0x8022u, 1u, L"512");
        }
        else
        {
          v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, struct _MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v45 + 48LL))(
                  v45,
                  851978,
                  a2,
                  a7,
                  &instance);
          if ( v15 )
          {
            if ( (unsigned int)dword_180397B68 > 2 )
            {
              v43 = v15;
              LODWORD(v47) = 333;
              v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v32,
                (unsigned int)&unk_18035DC70,
                v33,
                v34,
                (__int64)&v42,
                (__int64)&v47,
                (__int64)&v43);
            }
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_180397B68 > 2 )
        {
          v44 = v15;
          LODWORD(v42) = 342;
          v47 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_18035CD95,
            v27,
            v28,
            (__int64)&v47,
            (__int64)&v42,
            (__int64)&v44);
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v49) = 7;
        LODWORD(v50) = 298;
        v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&word_18035C85E,
          v21,
          v22,
          (__int64)&v42,
          (__int64)&v50,
          (__int64)&v49);
      }
    }
LABEL_26:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v54);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 128) )
          v31 = *(_DWORD *)(a7 + 120);
        else
          v31 = 0;
        LODWORD(v42) = v31;
        if ( v65 )
        {
          v57 = *v64;
          v35 = SmMIGetString(L"ObjectId", &v57, 0);
        }
        else
        {
          v35 = 0;
        }
        v52 = v35;
        if ( v63 )
        {
          v57 = *v62;
          v36 = SmMIGetString(L"ObjectId", &v57, 0);
        }
        else
        {
          v36 = 0;
        }
        v51 = v36;
        v50 = "StoragePool";
        v49 = (unsigned __int64)(1000LL * (v54[1] - v54[0])) / v54[2];
        v44 = v15;
        LODWORD(v47) = v61 != 0 ? v60 : 0;
        v43 = v13;
        if ( *(_BYTE *)(a6 + 72) )
          v37 = *(_QWORD *)(a6 + 64);
        else
          v37 = 0;
        v48 = v37;
        v46 = "CreateStoragePool";
        v53 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v61 != 0 ? v60 : 0,
          (unsigned int)byte_18035D80B,
          v29,
          v30,
          (__int64)&v53,
          (__int64)&v46,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v47,
          (__int64)&v44,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v42);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v42) = 370;
    v53 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v38,
      (unsigned int)&word_18035CDCE,
      v39,
      v40,
      (__int64)&v53,
      (__int64)&v42);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v54);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
  return EventActivityIdControl(4u, &v68);
}

```

## disassembly

```asm
0x18016ca50  mov     [rsp-8+arg_10], rbx
0x18016ca55  push    rbp
0x18016ca56  push    rsi
0x18016ca57  push    rdi
0x18016ca58  push    r12
0x18016ca5a  push    r13
0x18016ca5c  push    r14
0x18016ca5e  push    r15
0x18016ca60  lea     rbp, [rsp-1E0h]
0x18016ca68  sub     rsp, 2E0h
0x18016ca6f  mov     rax, cs:__security_cookie
0x18016ca76  xor     rax, rsp
0x18016ca79  mov     [rbp+210h+var_40], rax
0x18016ca80  mov     rdi, rdx
0x18016ca83  mov     r12, rcx
0x18016ca86  mov     r14, [rbp+210h+arg_28]
0x18016ca8d  mov     rsi, [rbp+210h+arg_30]
0x18016ca94  xorps   xmm0, xmm0
0x18016ca97  xor     eax, eax
0x18016ca99  movups  xmmword ptr [rbp+210h+value], xmm0
0x18016ca9d  movups  xmmword ptr [rbp+210h+value+10h], xmm0
0x18016caa1  mov     qword ptr [rbp+210h+value+20h], rax
0x18016caa5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016caac  movdqu  xmmword ptr [rbp+210h+ActivityId.Data1], xmm0
0x18016cab4  lea     rdx, [rbp+210h+ActivityId]; ActivityId
0x18016cabb  lea     ecx, [rax+1]; ControlCode
0x18016cabe  call    cs:__imp_EventActivityIdControl
0x18016cac4  lea     r9, [rbp+210h+value]; value
0x18016cac8  mov     rcx, rdi; context
0x18016cacb  call    MI_Context_GetCustomOption_1
0x18016cad0  xor     ebx, ebx
0x18016cad2  test    eax, eax
0x18016cad4  jnz     short loc_18016CAE7
0x18016cad6  lea     rdx, [rbp+210h+ActivityId]; pclsid
0x18016cadd  mov     rcx, qword ptr [rbp+210h+value]; lpsz
0x18016cae1  call    cs:__imp_CLSIDFromString
0x18016cae7  mov     rcx, qword ptr [rbp+210h+ActivityId.Data1]
0x18016caee  mov     [rbp+210h+var_60], rcx
0x18016caf5  mov     rax, qword ptr [rbp+210h+ActivityId.Data4]
0x18016cafc  mov     [rbp+210h+var_58], rax
0x18016cb03  mov     qword ptr [rbp+210h+var_50.Data1], rcx
0x18016cb0a  mov     qword ptr [rbp+210h+var_50.Data4], rax
0x18016cb11  lea     rdx, [rbp+210h+var_50]; ActivityId
0x18016cb18  mov     ecx, 4; ControlCode
0x18016cb1d  call    cs:__imp_EventActivityIdControl
0x18016cb23  mov     eax, cs:dword_180397B68
0x18016cb29  lea     rcx, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016cb30  cmp     eax, 5
0x18016cb33  jbe     short loc_18016CB5E
0x18016cb35  mov     dword ptr [rbp+210h+var_278], 0FFh
0x18016cb3c  mov     [rbp+210h+var_290], rcx
0x18016cb40  lea     rax, [rbp+210h+var_278]
0x18016cb44  mov     [rsp+310h+var_2E8], rax
0x18016cb49  lea     rax, [rbp+210h+var_290]
0x18016cb4d  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016cb52  lea     rdx, byte_18035D519
0x18016cb59  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016cb5e  mov     [rbp+210h+instance.ft], rbx
0x18016cb65  xor     edx, edx; Val
0x18016cb67  mov     r8d, 118h; Size
0x18016cb6d  lea     rcx, [rbp+210h+instance.classDecl]; void *
0x18016cb74  call    memset_0
0x18016cb79  xorps   xmm0, xmm0
0x18016cb7c  xor     eax, eax
0x18016cb7e  movups  [rbp+210h+var_218], xmm0
0x18016cb82  mov     [rbp+210h+var_208], rax
0x18016cb86  mov     [rbp+210h+var_280], rbx
0x18016cb8a  lea     rcx, [rbp+210h+var_280]
0x18016cb8e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016cb93  mov     [rbp+210h+var_280], rbx
0x18016cb97  mov     r15d, ebx
0x18016cb9a  lea     rcx, [rbp+210h+var_238]; this
0x18016cb9e  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016cba3  mov     rcx, rdi; context
0x18016cba6  call    WspIsRemoteRequest
0x18016cbab  mov     r13d, eax
0x18016cbae  test    eax, eax
0x18016cbb0  jnz     short loc_18016CBD5
0x18016cbb2  lea     rcx, [rbp+210h+var_238]; this
0x18016cbb6  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016cbbb  cmp     [r14+48h], bl
0x18016cbbf  jz      short loc_18016CBD2
0x18016cbc1  mov     rcx, [r14+40h]; unsigned __int16 *
0x18016cbc5  call    WspIsRemoteInstance
0x18016cbca  test    al, al
0x18016cbcc  lea     r15d, [r13+1]
0x18016cbd0  jnz     short loc_18016CBD5
0x18016cbd2  mov     r15d, ebx
0x18016cbd5  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18016cbdc  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18016cbe1  mov     ebx, eax
0x18016cbe3  test    eax, eax
0x18016cbe5  jnz     loc_18016CDF0
0x18016cbeb  mov     dword ptr [rbp+210h+var_218], 0Dh
0x18016cbf2  mov     rax, [r14+40h]
0x18016cbf6  mov     qword ptr [rbp+210h+var_218+8], rax
0x18016cbfa  mov     rbx, [r12]
0x18016cbfe  lea     rcx, [rbp+210h+var_280]
0x18016cc02  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016cc07  mov     [rsp+310h+var_2F0], 1; int
0x18016cc0f  lea     r9, [rbp+210h+var_280]; struct ISpWmiObject **
0x18016cc13  lea     r8, [rbp+210h+var_218]; struct _SP_OBJECT_ID *
0x18016cc17  mov     rdx, rdi; context
0x18016cc1a  mov     rcx, rbx; this
0x18016cc1d  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18016cc22  mov     ebx, eax
0x18016cc24  test    eax, eax
0x18016cc26  jz      short loc_18016CC6E
0x18016cc28  mov     eax, cs:dword_180397B68
0x18016cc2e  cmp     eax, 2
0x18016cc31  jbe     loc_18016CDE4
0x18016cc37  mov     dword ptr [rbp+210h+var_278], ebx
0x18016cc3a  mov     dword ptr [rbp+210h+var_268], 11Fh
0x18016cc41  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016cc48  mov     [rbp+210h+var_290], rax
0x18016cc4c  lea     rax, [rbp+210h+var_278]
0x18016cc50  mov     [rsp+310h+var_2E0], rax
0x18016cc55  lea     rax, [rbp+210h+var_268]
0x18016cc59  mov     [rsp+310h+var_2E8], rax
0x18016cc5e  lea     rax, [rbp+210h+var_290]
0x18016cc62  lea     rdx, byte_18035CDFB
0x18016cc69  jmp     loc_18016CDDA
0x18016cc6e  mov     r8, [r14+40h]
0x18016cc72  mov     rdx, rdi
0x18016cc75  mov     rcx, [r12]
0x18016cc79  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18016cc7e  test    eax, eax
0x18016cc80  jnz     short loc_18016CCCB
0x18016cc82  lea     ebx, [rax+7]
0x18016cc85  mov     eax, cs:dword_180397B68
0x18016cc8b  cmp     eax, 2
0x18016cc8e  jbe     loc_18016CDE4
0x18016cc94  mov     dword ptr [rbp+210h+var_260], ebx
0x18016cc97  mov     dword ptr [rbp+210h+var_258], 12Ah
0x18016cc9e  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016cca5  mov     [rbp+210h+var_290], rax
0x18016cca9  lea     rax, [rbp+210h+var_260]
0x18016ccad  mov     [rsp+310h+var_2E0], rax
0x18016ccb2  lea     rax, [rbp+210h+var_258]
0x18016ccb6  mov     [rsp+310h+var_2E8], rax
0x18016ccbb  lea     rax, [rbp+210h+var_290]
0x18016ccbf  lea     rdx, word_18035C85E
0x18016ccc6  jmp     loc_18016CDDA
0x18016cccb  lea     r8, [rbp+210h+instance]; instance
0x18016ccd2  lea     rdx, SPACES_StorageSubsystem_CreateStoragePool2_rtti; methodDecl
0x18016ccd9  mov     rcx, rdi; context
0x18016ccdc  call    MI_Context_ConstructParameters
0x18016cce1  mov     ebx, eax
0x18016cce3  test    eax, eax
0x18016cce5  jz      short loc_18016CD2D
0x18016cce7  mov     eax, cs:dword_180397B68
0x18016cced  cmp     eax, 2
0x18016ccf0  jbe     loc_18016CDE4
0x18016ccf6  mov     dword ptr [rbp+210h+var_250], ebx
0x18016ccf9  mov     dword ptr [rbp+210h+var_248], 132h
0x18016cd00  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016cd07  mov     [rbp+210h+var_290], rax
0x18016cd0b  lea     rax, [rbp+210h+var_250]
0x18016cd0f  mov     [rsp+310h+var_2E0], rax
0x18016cd14  lea     rax, [rbp+210h+var_248]
0x18016cd18  mov     [rsp+310h+var_2E8], rax
0x18016cd1d  lea     rax, [rbp+210h+var_290]
0x18016cd21  lea     rdx, word_18035C942
0x18016cd28  jmp     loc_18016CDDA
0x18016cd2d  test    r15d, r15d
0x18016cd30  jz      loc_18016CE40
0x18016cd36  cmp     byte ptr [rsi+80h], 0
0x18016cd3d  jz      loc_18016CE40
0x18016cd43  cmp     dword ptr [rsi+78h], 200h
0x18016cd4a  jbe     loc_18016CE40
0x18016cd50  mov     [rbp+210h+var_150], 5
0x18016cd5a  mov     [rbp+210h+var_14C], 1
0x18016cd61  lea     rax, a512; "512"
0x18016cd68  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016cd6d  mov     r9d, 1; unsigned int
0x18016cd73  mov     r8d, 8022h; unsigned int
0x18016cd79  lea     rdx, [rbp+210h+instance]; struct _MI_Instance *
0x18016cd80  mov     rcx, rdi; struct _MI_Context *
0x18016cd83  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x18016cd88  lea     rdx, [rbp+210h+instance]
0x18016cd8f  mov     rcx, rdi; self
0x18016cd92  call    MI_Instance_Destruct
0x18016cd97  mov     ebx, eax
0x18016cd99  test    eax, eax
0x18016cd9b  jz      short loc_18016CDE4
0x18016cd9d  mov     eax, cs:dword_180397B68
0x18016cda3  cmp     eax, 2
0x18016cda6  jbe     short loc_18016CDE4
0x18016cda8  mov     [rbp+210h+var_284], ebx
0x18016cdab  mov     dword ptr [rbp+210h+var_290], 156h
0x18016cdb2  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016cdb9  mov     [rbp+210h+var_270], rax
0x18016cdbd  lea     rax, [rbp+210h+var_284]
0x18016cdc1  mov     [rsp+310h+var_2E0], rax
0x18016cdc6  lea     rax, [rbp+210h+var_290]
0x18016cdca  mov     [rsp+310h+var_2E8], rax
0x18016cdcf  lea     rax, [rbp+210h+var_270]
0x18016cdd3  lea     rdx, byte_18035CD95
0x18016cdda  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016cddf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016cde4  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18016cdeb  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18016cdf0  xor     r12d, r12d
0x18016cdf3  test    r13d, r13d
0x18016cdf6  jnz     loc_18016D029
0x18016cdfc  lea     rcx, [rbp+210h+var_238]; this
0x18016ce00  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016ce05  mov     eax, cs:dword_180397B68
0x18016ce0b  cmp     eax, 5
0x18016ce0e  jbe     loc_18016D029
0x18016ce14  mov     rdx, 400000000000h
0x18016ce1e  lea     rcx, dword_180397B68
0x18016ce25  call    _tlgKeywordOn
0x18016ce2a  test    al, al
0x18016ce2c  jz      loc_18016D029
0x18016ce32  cmp     [rsi+80h], r12b
0x18016ce39  jz      short loc_18016CEB7
0x18016ce3b  mov     eax, [rsi+78h]
0x18016ce3e  jmp     short loc_18016CEBA
0x18016ce40  mov     rcx, [rbp+210h+var_280]
0x18016ce44  mov     rax, [rcx]
0x18016ce47  lea     rdx, [rbp+210h+instance]
0x18016ce4e  mov     qword ptr [rsp+310h+var_2F0], rdx
0x18016ce53  mov     r9, rsi
0x18016ce56  mov     r8, rdi
0x18016ce59  mov     edx, 0D000Ah
0x18016ce5e  mov     rax, [rax+30h]
0x18016ce62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ce67  mov     ebx, eax
0x18016ce69  test    eax, eax
0x18016ce6b  jz      loc_18016CD88
0x18016ce71  mov     eax, cs:dword_180397B68
0x18016ce77  cmp     eax, 2
0x18016ce7a  jbe     loc_18016CDE4
0x18016ce80  mov     [rbp+210h+var_288], ebx
0x18016ce83  mov     dword ptr [rbp+210h+var_270], 14Dh
0x18016ce8a  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016ce91  mov     [rbp+210h+var_290], rax
0x18016ce95  lea     rax, [rbp+210h+var_288]
0x18016ce99  mov     [rsp+310h+var_2E0], rax
0x18016ce9e  lea     rax, [rbp+210h+var_270]
0x18016cea2  mov     [rsp+310h+var_2E8], rax
0x18016cea7  lea     rax, [rbp+210h+var_290]
0x18016ceab  lea     rdx, unk_18035DC70
0x18016ceb2  jmp     loc_18016CDDA
0x18016ceb7  mov     eax, r12d
0x18016ceba  mov     dword ptr [rbp+210h+var_290], eax
0x18016cebd  cmp     [rbp+210h+var_88], r12b
0x18016cec4  jz      short loc_18016CF01
0x18016cec6  mov     rax, [rbp+210h+var_90]
0x18016cecd  movups  xmm0, xmmword ptr [rax]
0x18016ced0  movaps  xmmword ptr [rbp+210h+var_200.ft], xmm0
0x18016ced4  movups  xmm1, xmmword ptr [rax+10h]
0x18016ced8  movaps  xmmword ptr [rbp+210h+var_200.serverName], xmm1
0x18016cedc  movups  xmm0, xmmword ptr [rax+20h]
0x18016cee0  movaps  xmmword ptr [rbp+210h+var_200.reserved], xmm0
0x18016cee4  movups  xmm1, xmmword ptr [rax+30h]
0x18016cee8  movaps  xmmword ptr [rbp+210h+var_200.reserved+10h], xmm1
0x18016ceec  xor     r8d, r8d; unsigned __int16 *
0x18016ceef  lea     rdx, [rbp+210h+var_200]; struct _MI_Instance
0x18016cef3  lea     rcx, name; "ObjectId"
0x18016cefa  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016ceff  jmp     short loc_18016CF04
0x18016cf01  mov     rax, r12
0x18016cf04  mov     [rbp+210h+var_248], rax
0x18016cf08  cmp     [rbp+210h+var_98], r12b
0x18016cf0f  jz      short loc_18016CF4C
0x18016cf11  mov     rax, [rbp+210h+var_A0]
0x18016cf18  movups  xmm0, xmmword ptr [rax]
0x18016cf1b  movaps  xmmword ptr [rbp+210h+var_200.ft], xmm0
0x18016cf1f  movups  xmm1, xmmword ptr [rax+10h]
0x18016cf23  movaps  xmmword ptr [rbp+210h+var_200.serverName], xmm1
0x18016cf27  movups  xmm0, xmmword ptr [rax+20h]
0x18016cf2b  movaps  xmmword ptr [rbp+210h+var_200.reserved], xmm0
0x18016cf2f  movups  xmm1, xmmword ptr [rax+30h]
0x18016cf33  movaps  xmmword ptr [rbp+210h+var_200.reserved+10h], xmm1
0x18016cf37  xor     r8d, r8d; unsigned __int16 *
0x18016cf3a  lea     rdx, [rbp+210h+var_200]; struct _MI_Instance
0x18016cf3e  lea     rcx, name; "ObjectId"
0x18016cf45  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016cf4a  jmp     short loc_18016CF4F
0x18016cf4c  mov     rax, r12
0x18016cf4f  mov     [rbp+210h+var_250], rax
0x18016cf53  lea     rax, aStoragepool_0; "StoragePool"
0x18016cf5a  mov     [rbp+210h+var_258], rax
0x18016cf5e  mov     rax, [rbp+210h+var_230]
0x18016cf62  sub     rax, [rbp+210h+var_238]
0x18016cf66  imul    rax, 3E8h
0x18016cf6d  xor     edx, edx
0x18016cf6f  div     [rbp+210h+var_228]
0x18016cf73  mov     [rbp+210h+var_260], rax
0x18016cf77  mov     [rbp+210h+var_284], ebx
0x18016cf7a  mov     al, [rbp+210h+var_14C]
0x18016cf80  neg     al
0x18016cf82  sbb     ecx, ecx
0x18016cf84  and     ecx, [rbp+210h+var_150]
0x18016cf8a  mov     dword ptr [rbp+210h+var_270], ecx
0x18016cf8d  mov     [rbp+210h+var_288], r15d
0x18016cf91  cmp     [r14+48h], r12b
0x18016cf95  jz      short loc_18016CF9D
  ... truncated ...
```
