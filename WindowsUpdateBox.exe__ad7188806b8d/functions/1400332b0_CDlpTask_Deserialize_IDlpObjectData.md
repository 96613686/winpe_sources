# CDlpTask::Deserialize(IDlpObjectData *)

- ea: `0x1400332b0`
- end: `0x140034aad`
- name: `?Deserialize@CDlpTask@@UEAAJPEAVIDlpObjectData@@@Z`
- size: `6141`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpObjectData *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005b2c`
- `0x1400076c8`
- `0x140008434`
- `0x1400110a4`
- `0x1400111f0`
- `0x1400135b8`
- `0x140029b38`
- `0x140029c30`
- `0x14002bc70`
- `0x14002bd40`
- `0x14002c07c`
- `0x14002ca54`
- `0x14002f2cc`
- `0x1400332b0`
- `0x140034ab4`
- `0x140038e64`
- `0x140041e6c`
- `0x1400434a4`
- `0x14004c024`
- `0x14004cd1c`
- `0x140080d36`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140033dc3`
- `KERNEL32!HeapFree` at `0x1400349bb`
- `KERNEL32!HeapFree` at `0x140033dc3`
- `KERNEL32!HeapFree` at `0x1400349bb`
- `KERNEL32!HeapAlloc` at `0x140033f6b`
- `KERNEL32!HeapAlloc` at `0x140033f6b`
- `KERNEL32!GetProcessHeap` at `0x140033daf`
- `KERNEL32!GetProcessHeap` at `0x140033f56`
- `KERNEL32!GetProcessHeap` at `0x1400349a7`
- `KERNEL32!GetProcessHeap` at `0x140033daf`
- `KERNEL32!GetProcessHeap` at `0x140033f56`
- `KERNEL32!GetProcessHeap` at `0x1400349a7`
- `KERNEL32!LeaveCriticalSection` at `0x140033ca6`
- `KERNEL32!LeaveCriticalSection` at `0x140033ca6`
- `KERNEL32!EnterCriticalSection` at `0x140033c7a`
- `KERNEL32!EnterCriticalSection` at `0x140033c7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140033bb8`
- `OLEAUT32!__imp_SysFreeString` at `0x140033d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x140033de8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400348d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400348f0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003490f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003492e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003494c`
- `OLEAUT32!__imp_SysFreeString` at `0x140034969`
- `OLEAUT32!__imp_SysFreeString` at `0x140034986`
- `OLEAUT32!__imp_SysFreeString` at `0x140033b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140033bb8`
- `OLEAUT32!__imp_SysFreeString` at `0x140033d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x140033de8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400348d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400348f0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003490f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003492e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003494c`
- `OLEAUT32!__imp_SysFreeString` at `0x140034969`
- `OLEAUT32!__imp_SysFreeString` at `0x140034986`
- `RPCRT4!UuidFromStringW` at `0x1400338b8`
- `RPCRT4!UuidFromStringW` at `0x140033d64`
- `RPCRT4!UuidFromStringW` at `0x1400338b8`
- `RPCRT4!UuidFromStringW` at `0x140033d64`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400338d4`
- `RPCRT4!I_RpcMapWin32Status` at `0x14003464a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400338d4`
- `RPCRT4!I_RpcMapWin32Status` at `0x14003464a`

## string_xrefs

- `0x140034105`: `CDlpTask::Deserialize`
- `0x140034895`: `CDlpTask::Deserialize`
- `0x1400336bc`: `WorkingPath`
- `0x140033964`: `Task->Deserialize(): TransportId = [%s]`
- `0x140033c3e`: `Task->Deserialize(): SourceUrl = [%s], DestPath = [%s]`
- `0x14003420b`: `DlpTask: Deserialize(): ActionId = [%s]`
- `0x140034762`: `DlpTask: Deserialize(): ActionIndex = [0x%X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::Deserialize(CDlpTask *this, struct IDlpObjectData *a2)
{
  struct CDlpFile *v4; // rbx
  int v5; // r14d
  __int64 v6; // rax
  unsigned int v7; // edi
  char *v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct IDlpTask *v12; // rdi
  RPC_STATUS v13; // eax
  int v14; // eax
  char *v15; // rsi
  __int64 v16; // rax
  RPC_WSTR v17; // rdi
  __int64 v18; // rax
  unsigned int v19; // r12d
  __int64 v20; // rax
  BSTR v21; // rbx
  BSTR v22; // rdi
  __int64 v23; // rax
  CDlpState *v24; // r14
  unsigned int v25; // r12d
  RPC_STATUS v26; // eax
  void *v27; // rdi
  HANDLE ProcessHeap; // rax
  int v29; // eax
  __int64 v30; // rcx
  HANDLE v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // r14
  CExclusiveAcquireLock *v34; // rdi
  int v35; // eax
  unsigned int v36; // edi
  __int64 v37; // rax
  unsigned int v38; // ebx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rax
  BSTR v42; // rdi
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  int v48; // eax
  void *v49; // rdi
  HANDLE v50; // rax
  __int64 v52; // [rsp+20h] [rbp-E0h]
  __int64 v53; // [rsp+28h] [rbp-D8h]
  unsigned int v54; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v55; // [rsp+38h] [rbp-C8h] BYREF
  struct CDlpFile *v56; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v57; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v58; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v59; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v60; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v61; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v62; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  BSTR v64; // [rsp+78h] [rbp-88h] BYREF
  int v65; // [rsp+80h] [rbp-80h] BYREF
  int v66; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v67; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v68; // [rsp+8Ch] [rbp-74h] BYREF
  int v69; // [rsp+90h] [rbp-70h] BYREF
  RPC_WSTR StringUuid; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v72; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-50h] BYREF
  CDlpTask *v74; // [rsp+B8h] [rbp-48h]
  BSTR v75; // [rsp+C0h] [rbp-40h] BYREF
  BSTR v76; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v77; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v78; // [rsp+D8h] [rbp-28h] BYREF
  struct IDlpObjectData *v79; // [rsp+E0h] [rbp-20h]
  __int64 v80; // [rsp+E8h] [rbp-18h] BYREF
  UUID v81; // [rsp+F0h] [rbp-10h] BYREF
  int v82; // [rsp+100h] [rbp+0h]
  __int64 v83; // [rsp+110h] [rbp+10h]
  UUID Uuid; // [rsp+120h] [rbp+20h] BYREF
  UUID v85; // [rsp+130h] [rbp+30h] BYREF

  v83 = -2;
  v79 = a2;
  v73 = 0;
  v72 = 0;
  v55 = 0;
  v4 = 0;
  v56 = 0;
  v78 = 0;
  v61 = 0;
  v77 = 0;
  v80 = 0;
  v71 = 0;
  v76 = 0;
  v75 = 0;
  StringUuid = 0;
  v60 = 0;
  v64 = 0;
  bstrString = 0;
  v62 = 0;
  Uuid = 0;
  v85 = 0;
  v54 = 0;
  v68 = 0;
  v66 = 0;
  v65 = 0;
  v69 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v67 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = -2147024809;
    LODWORD(v52) = 1119;
    goto LABEL_230;
  }
  v8 = (char *)a2 + 8;
  v5 = (**((__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))a2 + 1))((char *)a2 + 8, L"State", &v54);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1123;
    goto LABEL_230;
  }
  if ( ((v54 - 3) & 0xFFFFFFFD) == 0 )
    v54 = 4;
  v5 = (**(__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))v8)(v8, L"ErrorState", &v68);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1130;
    goto LABEL_230;
  }
  v5 = (**(__int64 (__fastcall ***)(char *, const wchar_t *, int *))v8)(v8, L"ErrorCode", &v69);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1131;
    goto LABEL_230;
  }
  v5 = (**(__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))v8)(v8, L"FileCount", &v57);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1132;
    goto LABEL_230;
  }
  v5 = (**(__int64 (__fastcall ***)(char *, const wchar_t *, unsigned int *))v8)(v8, L"ActionCount", &v58);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1133;
    goto LABEL_230;
  }
  v9 = (*(__int64 (__fastcall **)(char *, const wchar_t *, BSTR *))(*(_QWORD *)v8 + 16LL))(v8, L"Name", &v76);
  v5 = v9;
  if ( v9 != -2147023728 && v9 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1137;
    goto LABEL_230;
  }
  v10 = (*(__int64 (__fastcall **)(char *, const wchar_t *, BSTR *))(*(_QWORD *)v8 + 16LL))(v8, L"WorkingPath", &v75);
  v5 = v10;
  if ( v10 != -2147023728 && v10 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1141;
    goto LABEL_230;
  }
  v11 = (**(__int64 (__fastcall ***)(char *, const wchar_t *, int *))v8)(v8, L"Transferring", &v65);
  v5 = v11;
  if ( v11 != -2147023728 && v11 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1146;
    goto LABEL_230;
  }
  v12 = (CDlpTask *)((char *)this - 8);
  v74 = (CDlpTask *)((char *)this - 8);
  *((_DWORD *)this + 352) = v65 != 0;
  v5 = (*(__int64 (__fastcall **)(struct IDlpObjectData *, const wchar_t *, _QWORD, _QWORD **))(*(_QWORD *)a2 + 32LL))(
         a2,
         L"TRANSPORT",
         0,
         &v72);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1151;
    goto LABEL_230;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, RPC_WSTR *))(v72[1] + 16LL))(
         v72 + 1,
         L"TransportId",
         &StringUuid);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1153;
    goto LABEL_230;
  }
  v13 = UuidFromStringW(StringUuid, &Uuid);
  if ( v13 )
  {
    v14 = I_RpcMapWin32Status(v13);
    v5 = v14;
    if ( v14 > 0 )
      v5 = (unsigned __int16)v14 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
  }
  else
  {
    v5 = 0;
  }
  v15 = (char *)this + 168;
  v16 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
  if ( v5 < 0 )
  {
    if ( !v16 )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1155;
    goto LABEL_230;
  }
  if ( v16 )
  {
    v17 = StringUuid;
    v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
    CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"Task->Deserialize(): TransportId = [%s]", v17);
    v12 = (CDlpTask *)((char *)this - 8);
  }
  v81 = Uuid;
  v5 = CDlpTask::Initialize((__int64)v12, (__int128 *)&v81, v76, v75, v54, 0);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
      goto LABEL_233;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
    v7 = 0;
    if ( !v6 )
      goto LABEL_232;
    LODWORD(v53) = v5;
    LODWORD(v52) = 1165;
    goto LABEL_230;
  }
  if ( memcmp_0(&WINDLP_TRANSPORT_NONE, &Uuid, 0x10u) )
  {
    v5 = (*(__int64 (__fastcall **)(struct IDlpTask *, _QWORD **))(*(_QWORD *)v12 + 216LL))(v12, &v78);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( !v6 )
        goto LABEL_232;
      LODWORD(v53) = v5;
      LODWORD(v52) = 1173;
      goto LABEL_230;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(v78[1] + 8LL))(v78 + 1, v72);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( !v6 )
        goto LABEL_232;
      LODWORD(v53) = v5;
      LODWORD(v52) = 1174;
      goto LABEL_230;
    }
  }
  v19 = 0;
  if ( !v57 )
  {
LABEL_91:
    v24 = (CDlpTask *)((char *)this + 864);
    EnterCriticalSection((LPCRITICAL_SECTION)this + 22);
    v82 = 1;
    *((_DWORD *)this + 216) = 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v82 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 22);
      v82 = 0;
    }
    v25 = 0;
    if ( v58 )
    {
      while ( 1 )
      {
        if ( v55 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
          v55 = 0;
        }
        v5 = (*(__int64 (__fastcall **)(struct IDlpObjectData *, const wchar_t *, _QWORD, _QWORD **))(*(_QWORD *)v79 + 32LL))(
               v79,
               L"ACTION",
               v25,
               &v55);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1214;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        if ( v60 )
        {
          SysFreeString(v60);
          v60 = 0;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v55[1] + 16LL))(v55 + 1, L"ActionId", &v60);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1217;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v26 = UuidFromStringW(v60, &v85);
        if ( v26 )
          break;
        v5 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, unsigned int *))v55[1])(
               v55 + 1,
               L"ActionWeight",
               &v67);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1221;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        if ( v71 )
        {
          v27 = (void *)(v71 - 4);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v27);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v71 = 0;
        }
        if ( v64 )
        {
          SysFreeString(v64);
          v64 = 0;
        }
        v29 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v55[1] + 16LL))(
                v55 + 1,
                L"ActionName",
                &v64);
        v5 = v29;
        if ( v29 != -2147023728 && v29 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1227;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        if ( v64 )
        {
          v5 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v64);
          if ( v5 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
              goto LABEL_233;
            v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
            v7 = 0;
            if ( v6 )
            {
              LODWORD(v53) = v5;
              LODWORD(v52) = 1230;
              goto LABEL_230;
            }
            goto LABEL_232;
          }
        }
        v30 = *((_QWORD *)this + 162);
        v81 = v85;
        v5 = (*(__int64 (__fastcall **)(__int64, UUID *, _QWORD **))(*(_QWORD *)v30 + 48LL))(v30, &v81, &v61);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)v74 + 22) + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1235;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD *, char *))(*v61 + 104LL))(v61, (char *)this - 8);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1236;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(v61[1] + 8LL))(v61 + 1, v55);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1240;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v61 + 24LL))(v61, &v66);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1244;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        if ( v66 == 6 )
        {
          v5 = CDword::Increment((CDlpTask *)((char *)this + 864), &v59);
          if ( v5 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
              goto LABEL_233;
            v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
            v7 = 0;
            if ( v6 )
            {
              LODWORD(v53) = v5;
              LODWORD(v52) = 1249;
              goto LABEL_230;
            }
            goto LABEL_232;
          }
        }
        v5 = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
               (__int64)this + 368,
               (__int64 *)&v61);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1254;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1184, &v71);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1255;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1200, v67);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1256;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v31 = GetProcessHeap();
        v32 = HeapAlloc(v31, 0, 0x40u);
        v33 = (__int64)v32;
        if ( v32 )
        {
          *v32 = 0;
          v32[1] = 0;
          v34 = (CExclusiveAcquireLock *)(v32 + 2);
          *((_OWORD *)v32 + 1) = 0;
          *((_OWORD *)v32 + 2) = 0;
          *((_OWORD *)v32 + 3) = 0;
          CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v32 + 2));
          v35 = CExclusiveAcquireLock::Init(v34);
          v36 = v35;
          if ( v35 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v35);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v36);
        }
        else
        {
          v33 = 0;
        }
        SP<CULargeInteger,DP_CPP<CULargeInteger>>::Attach(&v77, v33);
        if ( !v77 )
        {
          v5 = -2147024882;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = -2147024882;
            LODWORD(v52) = 1261;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v40 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v77 + 16));
        v5 = v40;
        if ( v40 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
        if ( v5 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1262;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        v5 = CArray<DP_CPP<CULargeInteger>,DP_CPP<CULargeInteger>,CAdaptorDefault,CPoliciesDefault>::Append(
               (char *)this + 1168,
               &v77);
        v41 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
        if ( v5 < 0 )
        {
          if ( !v41 )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( v6 )
          {
            LODWORD(v53) = v5;
            LODWORD(v52) = 1263;
            goto LABEL_230;
          }
          goto LABEL_232;
        }
        if ( v41 )
        {
          v42 = v60;
          v43 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          CDlpLogT<CEmptyType>::DlpLogFormat(v43, 2, L"DlpTask: Deserialize(): ActionId = [%s]", v42);
        }
        if ( ++v25 >= v58 )
        {
          v24 = (CDlpTask *)((char *)this + 864);
          goto LABEL_155;
        }
      }
      v45 = I_RpcMapWin32Status(v26);
      v5 = v45;
      if ( v45 > 0 )
        v5 = (unsigned __int16)v45 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( !v6 )
        goto LABEL_232;
      LODWORD(v53) = v5;
      LODWORD(v52) = 1219;
    }
    else
    {
LABEL_155:
      v5 = CDlpState::Get(v24, (enum WINDLP_STATE *)&v59);
      v44 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      if ( v5 >= 0 )
      {
        if ( v44 )
        {
          v46 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          CDlpLogT<CEmptyType>::DlpLogFormat(v46, 2, L"DlpTask: Deserialize(): ActionIndex = [0x%X]", v59);
        }
        v47 = CDlpState::Set((char *)this + 288, v54);
        v5 = v47;
        if ( v47 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v47);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
        if ( v5 >= 0 )
        {
          v5 = CDlpState::SetError((char *)this + 288, v68);
          if ( v5 >= 0 )
          {
            v5 = CDlpTask::InternalSetError(v74, v69);
            if ( v5 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
              goto LABEL_233;
            v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
            v7 = 0;
            if ( !v6 )
              goto LABEL_232;
            LODWORD(v53) = v5;
            LODWORD(v52) = 1273;
          }
          else
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)v74 + 22) + 16LL))((char *)this + 168) )
              goto LABEL_233;
            v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
            v7 = 0;
            if ( !v6 )
              goto LABEL_232;
            LODWORD(v53) = v5;
            LODWORD(v52) = 1272;
          }
        }
        else
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)v74 + 22) + 16LL))((char *)this + 168) )
            goto LABEL_233;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
          v7 = 0;
          if ( !v6 )
            goto LABEL_232;
          LODWORD(v53) = v5;
          LODWORD(v52) = 1271;
        }
      }
      else
      {
        if ( !v44 )
          goto LABEL_233;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
        v7 = 0;
        if ( !v6 )
          goto LABEL_232;
        LODWORD(v53) = v5;
        LODWORD(v52) = 1268;
      }
    }
LABEL_230:
    v48 = CDlpLogT<CEmptyType>::DlpLogFormat(v6, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Deserialize", v52, v53);
    v7 = v48;
    if ( v48 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v48);
    goto LABEL_232;
  }
  while ( 1 )
  {
    if ( v73 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v73 = 0;
    }
    v5 = (*(__int64 (__fastcall **)(struct IDlpObjectData *, const wchar_t *, _QWORD, __int64 *))(*(_QWORD *)v79 + 32LL))(
           v79,
           L"FILE",
           v19,
           &v73);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( !v6 )
        goto LABEL_232;
      LODWORD(v53) = v5;
      LODWORD(v52) = 1182;
      goto LABEL_230;
    }
    v5 = CDlpFile::CreateInstance(*((struct IDlpManager **)this + 162), v12, (struct IUnknown *)v12, &v56);
    if ( v5 < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
      {
        v37 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
        v38 = 0;
        if ( v37 )
        {
          LODWORD(v53) = v5;
          LODWORD(v52) = 1186;
          goto LABEL_138;
        }
LABEL_140:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
      }
LABEL_141:
      v4 = v56;
      goto LABEL_233;
    }
    v4 = v56;
    v5 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)v56 + 1) + 8LL))((char *)v56 + 8, v73);
    if ( v5 < 0 )
      break;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    v5 = (*(__int64 (__fastcall **)(struct CDlpFile *, BSTR *))(*(_QWORD *)v4 + 48LL))(v4, &bstrString);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( v6 )
      {
        LODWORD(v53) = v5;
        LODWORD(v52) = 1195;
        goto LABEL_230;
      }
      goto LABEL_232;
    }
    if ( v62 )
    {
      SysFreeString(v62);
      v62 = 0;
    }
    v5 = (*(__int64 (__fastcall **)(struct CDlpFile *, BSTR *))(*(_QWORD *)v4 + 56LL))(v4, &v62);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
        goto LABEL_233;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      v7 = 0;
      if ( v6 )
      {
        LODWORD(v53) = v5;
        LODWORD(v52) = 1197;
        goto LABEL_230;
      }
      goto LABEL_232;
    }
    v5 = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
           (__int64)this + 352,
           (__int64 *)&v56);
    v20 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
    if ( v5 < 0 )
    {
      if ( v20 )
      {
        v37 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
        v38 = 0;
        if ( v37 )
        {
          LODWORD(v53) = v5;
          LODWORD(v52) = 1201;
LABEL_138:
          v39 = CDlpLogT<CEmptyType>::DlpLogFormat(v37, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Deserialize", v52, v53);
          v38 = v39;
          if ( v39 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v39);
        }
        goto LABEL_140;
      }
      goto LABEL_141;
    }
    if ( v20 )
    {
      v21 = v62;
      v22 = bstrString;
      v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
      CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"Task->Deserialize(): SourceUrl = [%s], DestPath = [%s]", v22, v21);
      v12 = (CDlpTask *)((char *)this - 8);
    }
    ++v19;
    v4 = v56;
    if ( v19 >= v57 )
      goto LABEL_91;
  }
  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168) )
    goto LABEL_233;
  v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
  v7 = 0;
  if ( v6 )
  {
    LODWORD(v53) = v5;
    LODWORD(v52) = 1190;
    goto LABEL_230;
  }
LABEL_232:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
LABEL_233:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v62 )
  {
    SysFreeString(v62);
    v62 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v64 )
  {
    SysFreeString(v64);
    v64 = 0;
  }
  if ( v60 )
  {
    SysFreeString(v60);
    v60 = 0;
  }
  if ( StringUuid )
  {
    SysFreeString(StringUuid);
    StringUuid = 0;
  }
  if ( v75 )
  {
    SysFreeString(v75);
    v75 = 0;
  }
  if ( v76 )
  {
    SysFreeString(v76);
    v76 = 0;
  }
  if ( v71 )
  {
    v49 = (void *)(v71 - 4);
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  SP<CDword,DP_CPP<CDword>>::~SP<CDword,DP_CPP<CDword>>(&v80);
  SP<CULargeInteger,DP_CPP<CULargeInteger>>::~SP<CULargeInteger,DP_CPP<CULargeInteger>>(&v77);
  if ( v61 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v78 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v78 + 16LL))(v78);
    v78 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct CDlpFile *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v55 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400332b0  mov     rax, rsp
0x1400332b3  push    rbp
0x1400332b4  push    rsi
0x1400332b5  push    rdi
0x1400332b6  push    r12
0x1400332b8  push    r13
0x1400332ba  push    r14
0x1400332bc  push    r15
0x1400332be  lea     rbp, [rsp-50h]
0x1400332c3  sub     rsp, 150h
0x1400332ca  mov     [rbp+80h+var_70], 0FFFFFFFFFFFFFFFEh
0x1400332d2  mov     [rax+18h], rbx
0x1400332d6  mov     rax, cs:__security_cookie
0x1400332dd  xor     rax, rsp
0x1400332e0  mov     [rbp+80h+var_40], rax
0x1400332e4  mov     rsi, rdx
0x1400332e7  mov     [rbp+80h+var_A0], rdx
0x1400332eb  mov     r13, rcx
0x1400332ee  mov     [rbp+80h+var_D0], 0
0x1400332f6  mov     [rbp+80h+var_D8], 0
0x1400332fe  mov     [rsp+180h+var_148], 0
0x140033307  xor     ebx, ebx
0x140033309  mov     [rsp+180h+var_140], rbx
0x14003330e  mov     [rbp+80h+var_A8], rbx
0x140033312  mov     [rsp+180h+var_120], rbx
0x140033317  mov     [rbp+80h+var_B0], rbx
0x14003331b  mov     [rbp+80h+var_98], rbx
0x14003331f  mov     [rbp+80h+var_E0], rbx
0x140033323  mov     [rbp+80h+var_B8], rbx
0x140033327  mov     [rbp+80h+var_C0], rbx
0x14003332b  mov     [rbp+80h+StringUuid], rbx
0x14003332f  mov     [rsp+180h+var_128], rbx
0x140033334  mov     [rsp+180h+var_108], rbx
0x140033339  mov     [rsp+180h+bstrString], rbx
0x14003333e  mov     [rsp+180h+var_118], rbx
0x140033343  xorps   xmm0, xmm0
0x140033346  movups  xmmword ptr [rbp+80h+Uuid.Data1], xmm0
0x14003334a  xorps   xmm1, xmm1
0x14003334d  movups  xmmword ptr [rbp+80h+var_50.Data1], xmm1
0x140033351  mov     [rsp+180h+var_150], ebx
0x140033355  mov     [rbp+80h+var_F4], ebx
0x140033358  mov     [rbp+80h+var_FC], ebx
0x14003335b  mov     [rbp+80h+var_100], ebx
0x14003335e  mov     [rbp+80h+var_F0], ebx
0x140033361  mov     [rsp+180h+var_138], ebx
0x140033365  mov     [rsp+180h+var_134], ebx
0x140033369  mov     [rsp+180h+var_130], ebx
0x14003336d  mov     [rbp+80h+var_F8], ebx
0x140033370  test    rdx, rdx
0x140033373  jnz     short loc_1400333D4
0x140033375  mov     r14d, 80070057h
0x14003337b  mov     rax, [rcx+0A8h]
0x140033382  add     rcx, 0A8h
0x140033389  mov     rax, [rax+10h]
0x14003338d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033392  test    rax, rax
0x140033395  jz      loc_1400348BF
0x14003339b  mov     rax, [r13+0A8h]
0x1400333a2  lea     rcx, [r13+0A8h]
0x1400333a9  mov     rax, [rax+10h]
0x1400333ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400333b2  xor     edi, edi
0x1400333b4  test    rax, rax
0x1400333b7  jz      loc_1400348B8
0x1400333bd  mov     dword ptr [rsp+180h+var_158], r14d
0x1400333c2  mov     dword ptr [rsp+180h+var_160], 45Fh
0x1400333ca  mov     edx, 4
0x1400333cf  jmp     loc_140034895
0x1400333d4  lea     rdi, [rdx+8]
0x1400333d8  mov     rax, [rdi]
0x1400333db  lea     r8, [rsp+180h+var_150]
0x1400333e0  lea     rdx, aState; "State"
0x1400333e7  mov     rcx, rdi
0x1400333ea  mov     rax, [rax]
0x1400333ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400333f2  mov     r14d, eax
0x1400333f5  test    eax, eax
0x1400333f7  jns     short loc_14003344A
0x1400333f9  mov     rdx, [r13+0A8h]
0x140033400  lea     rcx, [r13+0A8h]
0x140033407  mov     rax, [rdx+10h]
0x14003340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033410  test    rax, rax
0x140033413  jz      loc_1400348BF
0x140033419  mov     rax, [r13+0A8h]
0x140033420  lea     rcx, [r13+0A8h]
0x140033427  mov     rax, [rax+10h]
0x14003342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033430  xor     edi, edi
0x140033432  test    rax, rax
0x140033435  jz      loc_1400348B8
0x14003343b  mov     dword ptr [rsp+180h+var_158], r14d
0x140033440  mov     dword ptr [rsp+180h+var_160], 463h
0x140033448  jmp     short loc_1400333CA
0x14003344a  mov     eax, [rsp+180h+var_150]
0x14003344e  add     eax, 0FFFFFFFDh
0x140033451  mov     r15d, 4
0x140033457  test    eax, 0FFFFFFFDh
0x14003345c  jnz     short loc_140033463
0x14003345e  mov     [rsp+180h+var_150], r15d
0x140033463  mov     rax, [rdi]
0x140033466  lea     r8, [rbp+80h+var_F4]
0x14003346a  lea     rdx, aErrorstate; "ErrorState"
0x140033471  mov     rcx, rdi
0x140033474  mov     rax, [rax]
0x140033477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003347c  mov     r14d, eax
0x14003347f  test    eax, eax
0x140033481  jns     short loc_1400334D7
0x140033483  mov     rax, [r13+0A8h]
0x14003348a  lea     rcx, [r13+0A8h]
0x140033491  mov     rax, [rax+10h]
0x140033495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003349a  test    rax, rax
0x14003349d  jz      loc_1400348BF
0x1400334a3  mov     rax, [r13+0A8h]
0x1400334aa  lea     rcx, [r13+0A8h]
0x1400334b1  mov     rax, [rax+10h]
0x1400334b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400334ba  xor     edi, edi
0x1400334bc  test    rax, rax
0x1400334bf  jz      loc_1400348B8
0x1400334c5  mov     dword ptr [rsp+180h+var_158], r14d
0x1400334ca  mov     dword ptr [rsp+180h+var_160], 46Ah
0x1400334d2  jmp     loc_140034892
0x1400334d7  mov     rax, [rdi]
0x1400334da  lea     r8, [rbp+80h+var_F0]
0x1400334de  lea     rdx, aErrorcode; "ErrorCode"
0x1400334e5  mov     rcx, rdi
0x1400334e8  mov     rax, [rax]
0x1400334eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400334f0  mov     r14d, eax
0x1400334f3  test    eax, eax
0x1400334f5  jns     short loc_14003354B
0x1400334f7  mov     rax, [r13+0A8h]
0x1400334fe  lea     rcx, [r13+0A8h]
0x140033505  mov     rax, [rax+10h]
0x140033509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003350e  test    rax, rax
0x140033511  jz      loc_1400348BF
0x140033517  mov     rax, [r13+0A8h]
0x14003351e  lea     rcx, [r13+0A8h]
0x140033525  mov     rax, [rax+10h]
0x140033529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003352e  xor     edi, edi
0x140033530  test    rax, rax
0x140033533  jz      loc_1400348B8
0x140033539  mov     dword ptr [rsp+180h+var_158], r14d
0x14003353e  mov     dword ptr [rsp+180h+var_160], 46Bh
0x140033546  jmp     loc_140034892
0x14003354b  mov     rax, [rdi]
0x14003354e  lea     r8, [rsp+180h+var_138]
0x140033553  lea     rdx, aFilecount; "FileCount"
0x14003355a  mov     rcx, rdi
0x14003355d  mov     rax, [rax]
0x140033560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033565  mov     r14d, eax
0x140033568  test    eax, eax
0x14003356a  jns     short loc_1400335C0
0x14003356c  mov     rax, [r13+0A8h]
0x140033573  lea     rcx, [r13+0A8h]
0x14003357a  mov     rax, [rax+10h]
0x14003357e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033583  test    rax, rax
0x140033586  jz      loc_1400348BF
0x14003358c  mov     rax, [r13+0A8h]
0x140033593  lea     rcx, [r13+0A8h]
0x14003359a  mov     rax, [rax+10h]
0x14003359e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335a3  xor     edi, edi
0x1400335a5  test    rax, rax
0x1400335a8  jz      loc_1400348B8
0x1400335ae  mov     dword ptr [rsp+180h+var_158], r14d
0x1400335b3  mov     dword ptr [rsp+180h+var_160], 46Ch
0x1400335bb  jmp     loc_140034892
0x1400335c0  mov     rax, [rdi]
0x1400335c3  lea     r8, [rsp+180h+var_134]
0x1400335c8  lea     rdx, aActioncount; "ActionCount"
0x1400335cf  mov     rcx, rdi
0x1400335d2  mov     rax, [rax]
0x1400335d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335da  mov     r14d, eax
0x1400335dd  test    eax, eax
0x1400335df  jns     short loc_140033635
0x1400335e1  mov     rax, [r13+0A8h]
0x1400335e8  lea     rcx, [r13+0A8h]
0x1400335ef  mov     rax, [rax+10h]
0x1400335f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335f8  test    rax, rax
0x1400335fb  jz      loc_1400348BF
0x140033601  mov     rax, [r13+0A8h]
0x140033608  lea     rcx, [r13+0A8h]
0x14003360f  mov     rax, [rax+10h]
0x140033613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033618  xor     edi, edi
0x14003361a  test    rax, rax
0x14003361d  jz      loc_1400348B8
0x140033623  mov     dword ptr [rsp+180h+var_158], r14d
0x140033628  mov     dword ptr [rsp+180h+var_160], 46Dh
0x140033630  jmp     loc_140034892
0x140033635  mov     rax, [rdi]
0x140033638  lea     r8, [rbp+80h+var_B8]
0x14003363c  lea     rdx, aName; "Name"
0x140033643  mov     rcx, rdi
0x140033646  mov     rax, [rax+10h]
0x14003364a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003364f  mov     r14d, eax
0x140033652  mov     r12d, 80070490h
0x140033658  cmp     eax, r12d
0x14003365b  jz      short loc_1400336B5
0x14003365d  test    eax, eax
0x14003365f  jns     short loc_1400336B5
0x140033661  mov     rax, [r13+0A8h]
0x140033668  lea     rcx, [r13+0A8h]
0x14003366f  mov     rax, [rax+10h]
0x140033673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033678  test    rax, rax
0x14003367b  jz      loc_1400348BF
0x140033681  mov     rax, [r13+0A8h]
0x140033688  lea     rcx, [r13+0A8h]
0x14003368f  mov     rax, [rax+10h]
0x140033693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033698  xor     edi, edi
0x14003369a  test    rax, rax
0x14003369d  jz      loc_1400348B8
0x1400336a3  mov     dword ptr [rsp+180h+var_158], r14d
0x1400336a8  mov     dword ptr [rsp+180h+var_160], 471h
0x1400336b0  jmp     loc_140034892
0x1400336b5  mov     rax, [rdi]
0x1400336b8  lea     r8, [rbp+80h+var_C0]
0x1400336bc  lea     rdx, aWorkingpath; "WorkingPath"
0x1400336c3  mov     rcx, rdi
0x1400336c6  mov     rax, [rax+10h]
0x1400336ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400336cf  mov     r14d, eax
0x1400336d2  cmp     eax, r12d
0x1400336d5  jz      short loc_14003372F
0x1400336d7  test    eax, eax
0x1400336d9  jns     short loc_14003372F
0x1400336db  mov     rax, [r13+0A8h]
0x1400336e2  lea     rcx, [r13+0A8h]
0x1400336e9  mov     rax, [rax+10h]
0x1400336ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400336f2  test    rax, rax
0x1400336f5  jz      loc_1400348BF
0x1400336fb  mov     rax, [r13+0A8h]
0x140033702  lea     rcx, [r13+0A8h]
0x140033709  mov     rax, [rax+10h]
0x14003370d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033712  xor     edi, edi
0x140033714  test    rax, rax
0x140033717  jz      loc_1400348B8
0x14003371d  mov     dword ptr [rsp+180h+var_158], r14d
0x140033722  mov     dword ptr [rsp+180h+var_160], 475h
0x14003372a  jmp     loc_140034892
0x14003372f  mov     rax, [rdi]
0x140033732  lea     r8, [rbp+80h+var_100]
0x140033736  lea     rdx, aTransferring; "Transferring"
0x14003373d  mov     rcx, rdi
0x140033740  mov     rax, [rax]
0x140033743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033748  mov     r14d, eax
0x14003374b  cmp     eax, r12d
0x14003374e  jz      short loc_1400337A8
0x140033750  test    eax, eax
0x140033752  jns     short loc_1400337A8
0x140033754  mov     rax, [r13+0A8h]
0x14003375b  lea     rcx, [r13+0A8h]
0x140033762  mov     rax, [rax+10h]
0x140033766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003376b  test    rax, rax
0x14003376e  jz      loc_1400348BF
0x140033774  mov     rax, [r13+0A8h]
0x14003377b  lea     rcx, [r13+0A8h]
0x140033782  mov     rax, [rax+10h]
0x140033786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003378b  xor     edi, edi
0x14003378d  test    rax, rax
0x140033790  jz      loc_1400348B8
0x140033796  mov     dword ptr [rsp+180h+var_158], r14d
0x14003379b  mov     dword ptr [rsp+180h+var_160], 47Ah
0x1400337a3  jmp     loc_140034892
0x1400337a8  xor     eax, eax
0x1400337aa  cmp     [rbp+80h+var_100], eax
0x1400337ad  setnz   al
0x1400337b0  lea     rdi, [r13-8]
0x1400337b4  mov     [rbp+80h+var_C8], rdi
0x1400337b8  mov     [rdi+588h], eax
0x1400337be  mov     rax, [rsi]
0x1400337c1  lea     r9, [rbp+80h+var_D8]
0x1400337c5  xor     r8d, r8d
0x1400337c8  lea     rdx, aTransport; "TRANSPORT"
0x1400337cf  mov     rcx, rsi
0x1400337d2  mov     rax, [rax+20h]
0x1400337d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400337db  mov     r14d, eax
0x1400337de  test    eax, eax
0x1400337e0  jns     short loc_140033836
0x1400337e2  mov     rax, [r13+0A8h]
0x1400337e9  lea     rcx, [r13+0A8h]
  ... truncated ...
```
