# CUpdateDeploymentProvider::QueryUpdateDeploymentStatusInternal(tagQueryDeploymentStatusMode,ulong,uchar const *,IUpdateDeploymentStatus * *,tagDeploymentReportingUpdateGroup *,int *)

- ea: `0x180013494`
- end: `0x180013dc0`
- name: `?QueryUpdateDeploymentStatusInternal@CUpdateDeploymentProvider@@AEAAJW4tagQueryDeploymentStatusMode@@KPEBEPEAPEAUIUpdateDeploymentStatus@@PEAUtagDeploymentReportingUpdateGroup@@PEAH@Z`
- size: `2348`
- prototype: `__int64 __fastcall(__int64, int, UINT, const CHAR *, __int64, struct tagDeploymentReportingUpdateGroup *, _DWORD *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800133c0`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011bf0`
- `0x1800125f4`
- `0x180012694`
- `0x180013494`
- `0x180013ee0`
- `0x18001422c`
- `0x180017110`
- `0x180017248`
- `0x1800175c4`
- `0x180018790`
- `0x1800200fc`
- `0x1800201a4`
- `0x180020600`
- `0x180020fe8`
- `0x1800211a4`
- `0x180024fd8`
- `0x1800475f4`
- `0x18004763c`
- `0x1800476fc`
- `0x180047774`
- `0x1800482f0`
- `0x180048514`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800138b1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800138b1`
- `OLEAUT32!__imp_SysFreeString` at `0x180013609`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001389c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001395b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ae2`
- `OLEAUT32!__imp_SysFreeString` at `0x180013b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013609`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001389c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001395b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180013ae2`
- `OLEAUT32!__imp_SysFreeString` at `0x180013b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d8d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013be8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013be8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180013614`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180013614`

## string_xrefs

- `0x1800135ac`: `Update`
- `0x180013c67`: `Update progress`
- `0x180013c9f`: `Update success`
- `0x180013c96`: `Update aborted`
- `0x180013c8d`: `Update failed`
- `0x180013c84`: `Update skipped`
- `0x18001350b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x180013657`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x1800136e3`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x1800136f8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x1800135c5`: `QueryUpdateDeploymentStatusInternal invoked in %ws mode. Callback info byte len = %d`
- `0x180013783`: `Reporting event already finalized for update : %ws, skipping querying the handler.`
- `0x180013cc4`: `QueryUpdateDeploymentStatusInternal status for update %ws.%d : callback code = %ws, error code = 0x%08x, extended error code = 0x%08x`
- `0x180013c55`: `Job complete`
- `0x1800135b5`: `Readonly`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentProvider::QueryUpdateDeploymentStatusInternal(
        __int64 a1,
        int a2,
        UINT a3,
        const CHAR *a4,
        __int64 a5,
        struct tagDeploymentReportingUpdateGroup *a6,
        _DWORD *a7)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  wchar_t *v12; // r14
  CDeploymentReportingUpdateGroup *v13; // rdi
  struct UpdateDeploymentStatus *v14; // rbx
  int inited; // r15d
  __int64 v16; // rdx
  unsigned int v17; // edx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  unsigned int v21; // ecx
  unsigned int v22; // eax
  __int64 v23; // rdx
  OLECHAR *v24; // rsi
  __m128i *v25; // rax
  __m128i v26; // xmm0
  int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int Handler; // eax
  int v34; // r15d
  int v35; // ecx
  int v36; // eax
  int v37; // eax
  unsigned int v38; // r15d
  __int64 RegKeyPath; // rax
  __int64 v40; // rcx
  int v41; // eax
  int v42; // eax
  unsigned __int64 v43; // r9
  int v44; // eax
  OLECHAR *v45; // rax
  __int64 v46; // rbx
  void **v47; // r15
  unsigned int v48; // edx
  unsigned int v49; // r8d
  __int64 v50; // rdx
  int v51; // eax
  int UpdateDeploymentStatusFromPendingGroup; // eax
  unsigned __int8 **v53; // rsi
  void *v54; // rcx
  UINT v55; // eax
  int v56; // eax
  int v57; // [rsp+20h] [rbp-E0h]
  GUID *v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+60h] [rbp-A0h]
  int v60; // [rsp+64h] [rbp-9Ch]
  unsigned int v61; // [rsp+68h] [rbp-98h]
  unsigned int v62; // [rsp+6Ch] [rbp-94h]
  wchar_t *v64; // [rsp+78h] [rbp-88h] BYREF
  struct UpdateDeploymentStatus *v65; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR *v66; // [rsp+88h] [rbp-78h]
  unsigned int v67; // [rsp+90h] [rbp-70h]
  CDeploymentReportingUpdateGroup *v68; // [rsp+98h] [rbp-68h] BYREF
  struct tagDeploymentReportingUpdateGroup *v69; // [rsp+A0h] [rbp-60h]
  __int64 v70; // [rsp+A8h] [rbp-58h]
  _DWORD *v71; // [rsp+B0h] [rbp-50h]
  _OWORD v72[2]; // [rsp+B8h] [rbp-48h] BYREF
  OLECHAR *psz[2]; // [rsp+D8h] [rbp-28h]
  __int128 v74; // [rsp+E8h] [rbp-18h] BYREF
  void *lpMem[2]; // [rsp+F8h] [rbp-8h]
  __int64 v76; // [rsp+108h] [rbp+8h]
  __int64 v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v79[56]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v80[96]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v81[592]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  v70 = a5;
  v69 = a6;
  v71 = a7;
  if ( !a4 )
  {
    v9 = 165;
LABEL_3:
    v10 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
      (const char *)v10,
      v57);
    return v10;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v9 = 166;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v9 = 167;
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v9 = 168;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v9 = 169;
    goto LABEL_3;
  }
  v60 = 0;
  v12 = 0;
  v64 = 0;
  memset(v81, 0, 0x248u);
  CUHHandlerManager::CUHHandlerManager((CUHHandlerManager *)v81);
  v13 = 0;
  v68 = 0;
  v14 = 0;
  v65 = 0;
  v59 = 0;
  LODWORD(v58) = 0;
  WUTrace(0, 0, 0x1000000, 4);
  inited = CUHHandlerManager::Init((CUHHandlerManager *)v81);
  if ( inited < 0 )
  {
    v16 = 184;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
      (const char *)(unsigned int)inited,
      0);
    goto LABEL_106;
  }
  SysFreeString(0);
  v12 = SysAllocStringByteLen(a4, a3);
  v64 = v12;
  if ( !v12 )
  {
    inited = -2147024882;
    v16 = 189;
    goto LABEL_19;
  }
  inited = WuSmartPtr::XPtrBase<CDeploymentReportingUpdateGroup,WuSmartPtr::Policies::STPolicy<CDeploymentReportingUpdateGroup>>::ReleaseAndAlloc(&v68);
  if ( inited < 0 )
  {
    v16 = 192;
    v13 = v68;
    goto LABEL_19;
  }
  memset(v80, 0, sizeof(v80));
  CSerializationHelper::CSerializationHelper((CSerializationHelper *)v80);
  inited = CSerializationHelper::InitDeserializeFromStringWithHeader((CSerializationHelper *)v80, v17, v18, v12);
  v13 = v68;
  if ( inited < 0 )
  {
    v19 = 201;
LABEL_26:
    v20 = (unsigned int)inited;
    goto LABEL_103;
  }
  inited = CSerializationHelper::ReadFromBSTRWithHeader((CSerializationHelper *)v80, v12);
  if ( inited < 0 )
  {
    v19 = 202;
    goto LABEL_26;
  }
  inited = CDeploymentReportingUpdateGroup::Deserialize(v13, (struct CSerializationHelper *)v80);
  if ( inited < 0 )
  {
    v19 = 203;
    goto LABEL_26;
  }
  v21 = 0;
  v62 = 0;
  v22 = *((_DWORD *)v13 + 5);
  if ( !v22 )
  {
LABEL_74:
    if ( a2 == 2 )
    {
      memset(v79, 0, 0x60u);
      CSerializationHelper::CSerializationHelper((CSerializationHelper *)v79);
      inited = CSerializationHelper::InitSerializeToStringWithHeader((CSerializationHelper *)v79, v48, v49);
      if ( inited < 0 )
      {
        v50 = 305;
LABEL_89:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
          (const char *)(unsigned int)inited,
          (int)v58);
LABEL_92:
        CSerializationHelper::~CSerializationHelper((CSerializationHelper *)v79);
        goto LABEL_105;
      }
      inited = CDeploymentReportingUpdateGroup::Serialize(v13, (struct CSerializationHelper *)v79);
      if ( inited < 0 )
      {
        v50 = 306;
        goto LABEL_89;
      }
      SysFreeString(v12);
      v64 = 0;
      v51 = CSerializationHelper::WriteToBSTRWithHeader((CSerializationHelper *)v79, &v64);
      inited = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x133,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
          (const char *)(unsigned int)v51,
          (int)v58);
        v12 = v64;
        goto LABEL_92;
      }
      CSerializationHelper::~CSerializationHelper((CSerializationHelper *)v79);
      v12 = v64;
    }
    UpdateDeploymentStatusFromPendingGroup = GetUpdateDeploymentStatusFromPendingGroup(v13, &v65, v69);
    inited = UpdateDeploymentStatusFromPendingGroup;
    if ( UpdateDeploymentStatusFromPendingGroup < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
        (const char *)(unsigned int)UpdateDeploymentStatusFromPendingGroup,
        (int)v58);
      v14 = v65;
      goto LABEL_105;
    }
    v14 = v65;
    v53 = (unsigned __int8 **)((char *)v65 + 184);
    v54 = (void *)*((_QWORD *)v65 + 23);
    if ( v54 )
    {
      SusFree(v54);
      *v53 = 0;
    }
    v55 = SysStringByteLen(v12);
    v56 = DPCopyBufferWithAlloc(v55, (const unsigned __int8 *)v12, (unsigned int *)v14 + 44, v53);
    inited = v56;
    if ( v56 >= 0 )
    {
      *((_DWORD *)v14 + 28) |= v59;
      LODWORD(v58) = 0;
      WUTrace(0, 0, 0x1000000, 4);
      v56 = (**(__int64 (__fastcall ***)(struct UpdateDeploymentStatus *, GUID *, __int64))v14)(
              v14,
              &GUID_3acdcf0c_5353_4aed_821d_20e377ac4261,
              v70);
      inited = v56;
      if ( v56 >= 0 )
      {
        *v71 = v60 != 0;
        inited = 0;
        goto LABEL_105;
      }
      v19 = 337;
    }
    else
    {
      v19 = 323;
    }
    v20 = (unsigned int)v56;
LABEL_103:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
      (const char *)v20,
      (int)v58);
    goto LABEL_105;
  }
  while ( 1 )
  {
    v23 = 221;
    v77 = 0;
    v74 = 0;
    *(_OWORD *)lpMem = 0;
    v76 = 0;
    v24 = 0;
    v66 = 0;
    if ( v21 >= v22 )
      break;
    v25 = (__m128i *)(*((_QWORD *)v13 + 1) + 32LL * v21);
    v26 = *v25;
    v72[0] = v26;
    *(__m128i *)psz = v25[1];
    v72[1] = *(_OWORD *)psz;
    if ( !v26.m128i_i64[0] )
    {
      inited = -2145120257;
      goto LABEL_83;
    }
    if ( a2 == 2 && *(_DWORD *)(v26.m128i_i64[0] + 476) )
    {
      Trace::UpdateIdToString::UpdateIdToString(v79, (const struct tagDSGlobalUpdateId *)(v26.m128i_i64[0] + 236));
      LODWORD(v58) = 0;
      WUTrace(0, 0, 0x1000000, 4);
      SysFreeString(0);
      if ( v77 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      goto LABEL_73;
    }
    v67 = *(_DWORD *)(v26.m128i_i64[0] + 448);
    v27 = *(_DWORD *)(v26.m128i_i64[0] + 40);
    if ( v27 > 541 )
    {
      v30 = v27 - 542;
      v29 = v30 == 0;
    }
    else
    {
      if ( v27 == 541 || (v28 = v27 - 221) == 0 )
      {
LABEL_44:
        v61 = 0;
        goto LABEL_45;
      }
      v30 = v28 - 1;
      v29 = v30 == 0;
    }
    if ( v29 )
      goto LABEL_44;
    v31 = v30 - 1;
    if ( !v31 )
      goto LABEL_44;
    v32 = v31 - 1;
    if ( !v32 )
      goto LABEL_44;
    v61 = 1;
    if ( v32 == 1 )
      goto LABEL_44;
LABEL_45:
    v58 = &GUID_b114a32b_955f_4103_b299_d9ed046e5548;
    Handler = CUHHandlerManager::GetHandler(v81, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v26, 8)), 1);
    v34 = Handler;
    if ( Handler >= 0 )
    {
      v78 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 32LL))(v77, &v78);
      inited = v36;
      if ( v36 < 0 )
      {
        v43 = (unsigned int)v36;
        v23 = 251;
        goto LABEL_84;
      }
      SysFreeString(0);
      v24 = 0;
      v66 = 0;
      if ( psz[0] )
      {
        v24 = SysAllocString(psz[0]);
        v66 = v24;
        if ( !v24 )
        {
          inited = -2147024882;
          v23 = 252;
          goto LABEL_83;
        }
      }
      ++v60;
      v37 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *))(*(_QWORD *)v77 + 24LL))(
              v77,
              v24,
              v61,
              &v74);
      v38 = v37;
      if ( v37 >= 0 )
      {
        v59 |= HIDWORD(v76);
        v35 = v74;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101,
          (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
          (const char *)(unsigned int)v37);
        if ( v78 || (RegKeyPath = GetRegKeyPath(14), (int)RegKeyExists(v40, RegKeyPath) >= 0) || v67 < 0xA )
        {
          v41 = SetDeploymentEventStillPendingStatus(
                  (struct tagDeploymentReportingUpdateEvent *)v72,
                  (struct tagPostRebootResultData *)&v74);
          inited = v41;
          if ( v41 < 0 )
          {
            v43 = (unsigned int)v41;
            v23 = 277;
            goto LABEL_84;
          }
          SysFreeString(v24);
          if ( v77 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          goto LABEL_73;
        }
        v35 = -2145116139;
        LODWORD(v74) = -2145116139;
        *(_QWORD *)((char *)&v74 + 4) = v38;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF3,
        (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
        (const char *)(unsigned int)Handler);
      v35 = -2145116139;
      LODWORD(v74) = -2145116139;
      DWORD1(v74) = v34;
    }
    if ( DWORD2(v74) || v35 == -2145116140 )
    {
      v44 = SetDeploymentEventStillPendingStatus(
              (struct tagDeploymentReportingUpdateEvent *)v72,
              (struct tagPostRebootResultData *)&v74);
      inited = v44;
      if ( v44 < 0 )
      {
        v43 = (unsigned int)v44;
        v23 = 286;
        goto LABEL_84;
      }
    }
    else
    {
      v42 = SetDeploymentEventFinalStatus(
              (struct tagDeploymentReportingUpdateEvent *)v72,
              (struct tagPostRebootResultData *)&v74);
      inited = v42;
      if ( v42 < 0 )
      {
        v43 = (unsigned int)v42;
        v23 = 291;
        goto LABEL_84;
      }
    }
    v45 = (OLECHAR *)lpMem[1];
    v66 = (OLECHAR *)lpMem[1];
    if ( lpMem[1] )
    {
      if ( (_DWORD)v76 )
      {
        v46 = (unsigned int)v76;
        v47 = (void **)lpMem[1];
        do
        {
          SusFree(*v47);
          SusFree(v47[1]);
          v47 += 2;
          --v46;
        }
        while ( v46 );
        v14 = v65;
        v45 = v66;
      }
      SusFree(v45);
    }
    SysFreeString(v24);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
LABEL_73:
    v21 = v62 + 1;
    v62 = v21;
    v22 = *((_DWORD *)v13 + 5);
    if ( v21 >= v22 )
      goto LABEL_74;
  }
  inited = -2145124345;
  v23 = 220;
LABEL_83:
  v43 = (unsigned int)inited;
LABEL_84:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
    (const char *)v43,
    (int)v58);
  SysFreeString(v24);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
LABEL_105:
  CSerializationHelper::~CSerializationHelper((CSerializationHelper *)v80);
LABEL_106:
  if ( v14 )
    (*(void (__fastcall **)(struct UpdateDeploymentStatus *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
  {
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>((_QWORD *)v13 + 3);
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(v13);
    operator delete(v13, (const struct std::nothrow_t *)0x40);
  }
  CUHHandlerManager::~CUHHandlerManager((CUHHandlerManager *)v81);
  SysFreeString(v12);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180013494  mov     [rsp-8+arg_0], rbx
0x180013499  push    rbp
0x18001349a  push    rsi
0x18001349b  push    rdi
0x18001349c  push    r12
0x18001349e  push    r13
0x1800134a0  push    r14
0x1800134a2  push    r15
0x1800134a4  lea     rbp, [rsp-350h]
0x1800134ac  sub     rsp, 450h
0x1800134b3  mov     rax, cs:__security_cookie
0x1800134ba  xor     rax, rsp
0x1800134bd  mov     [rbp+380h+var_40], rax
0x1800134c4  mov     r12, r9
0x1800134c7  mov     esi, r8d
0x1800134ca  mov     r15d, edx
0x1800134cd  mov     [rsp+480h+var_410], edx
0x1800134d1  mov     rdx, [rbp+380h+arg_20]
0x1800134d8  mov     [rbp+380h+var_3D8], rdx
0x1800134dc  mov     rax, [rbp+380h+arg_28]
0x1800134e3  mov     [rbp+380h+var_3E0], rax
0x1800134e7  mov     rcx, [rbp+380h+arg_30]
0x1800134ee  mov     [rbp+380h+var_3D0], rcx
0x1800134f2  test    r9, r9
0x1800134f5  jnz     short loc_18001351E
0x1800134f7  mov     edx, 0A5h; void *
0x1800134fc  mov     ebx, 80004003h
0x180013501  mov     rcx, [rbp+388h]; this
0x180013508  mov     r9d, ebx; char *
0x18001350b  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180013512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013517  mov     eax, ebx
0x180013519  jmp     loc_180013D96
0x18001351e  test    esi, esi
0x180013520  jnz     short loc_18001352E
0x180013522  mov     ebx, 80070057h
0x180013527  mov     edx, 0A6h
0x18001352c  jmp     short loc_180013501
0x18001352e  test    rdx, rdx
0x180013531  jnz     short loc_18001353A
0x180013533  mov     edx, 0A7h
0x180013538  jmp     short loc_1800134FC
0x18001353a  test    rax, rax
0x18001353d  jnz     short loc_180013546
0x18001353f  mov     edx, 0A8h
0x180013544  jmp     short loc_1800134FC
0x180013546  test    rcx, rcx
0x180013549  jnz     short loc_180013552
0x18001354b  mov     edx, 0A9h
0x180013550  jmp     short loc_1800134FC
0x180013552  mov     [rsp+480h+var_41C], 0
0x18001355a  xor     r14d, r14d
0x18001355d  mov     [rsp+480h+var_408], r14
0x180013562  xor     edx, edx; Val
0x180013564  mov     r8d, 248h; Size
0x18001356a  lea     rcx, [rbp+380h+var_290]; void *
0x180013571  call    memset
0x180013576  lea     rcx, [rbp+380h+var_290]; this
0x18001357d  call    ??0CUHHandlerManager@@QEAA@XZ; CUHHandlerManager::CUHHandlerManager(void)
0x180013582  nop
0x180013583  xor     edi, edi
0x180013585  mov     [rbp+380h+var_3E8], rdi
0x180013589  xor     ebx, ebx
0x18001358b  mov     [rbp+380h+var_400], rbx
0x18001358f  mov     [rsp+480h+var_420], ebx
0x180013593  mov     ecx, r15d
0x180013596  lea     r13, aUnknown_0; "Unknown"
0x18001359d  sub     ecx, 1
0x1800135a0  jz      short loc_1800135B5
0x1800135a2  cmp     ecx, 1
0x1800135a5  jz      short loc_1800135AC
0x1800135a7  mov     rax, r13
0x1800135aa  jmp     short loc_1800135BC
0x1800135ac  lea     rax, aUpdate; "Update"
0x1800135b3  jmp     short loc_1800135BC
0x1800135b5  lea     rax, aReadonly; "Readonly"
0x1800135bc  mov     [rsp+480h+var_448], esi
0x1800135c0  mov     [rsp+480h+var_450], rax
0x1800135c5  lea     rax, aQueryupdatedep_0; "QueryUpdateDeploymentStatusInternal inv"...
0x1800135cc  mov     [rsp+480h+var_458], rax
0x1800135d1  mov     qword ptr [rsp+480h+var_460], 0; int
0x1800135da  xor     edx, edx
0x1800135dc  xor     ecx, ecx
0x1800135de  lea     r9d, [rdx+4]
0x1800135e2  mov     r8d, 1000000h
0x1800135e8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800135ed  lea     rcx, [rbp+380h+var_290]; this
0x1800135f4  call    ?Init@CUHHandlerManager@@QEAAJXZ; CUHHandlerManager::Init(void)
0x1800135f9  mov     r15d, eax
0x1800135fc  test    eax, eax
0x1800135fe  jns     short loc_180013607
0x180013600  mov     edx, 0B8h
0x180013605  jmp     short loc_18001364D
0x180013607  xor     ecx, ecx; bstrString
0x180013609  call    cs:__imp_SysFreeString
0x18001360f  mov     edx, esi; len
0x180013611  mov     rcx, r12; psz
0x180013614  call    cs:__imp_SysAllocStringByteLen
0x18001361a  mov     r14, rax
0x18001361d  mov     [rsp+480h+var_408], rax
0x180013622  test    rax, rax
0x180013625  jnz     short loc_180013634
0x180013627  mov     r15d, 8007000Eh
0x18001362d  mov     edx, 0BDh
0x180013632  jmp     short loc_18001364D
0x180013634  lea     rcx, [rbp+380h+var_3E8]
0x180013638  call    ?ReleaseAndAlloc@?$XPtrBase@VCDeploymentReportingUpdateGroup@@U?$STPolicy@VCDeploymentReportingUpdateGroup@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<CDeploymentReportingUpdateGroup,WuSmartPtr::Policies::STPolicy<CDeploymentReportingUpdateGroup>>::ReleaseAndAlloc(void)
0x18001363d  mov     r15d, eax
0x180013640  test    eax, eax
0x180013642  jns     short loc_180013668
0x180013644  mov     edx, 0C0h; void *
0x180013649  mov     rdi, [rbp+380h+var_3E8]
0x18001364d  mov     rcx, [rbp+388h]; this
0x180013654  mov     r9d, r15d; char *
0x180013657  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001365e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013663  jmp     loc_180013D44
0x180013668  xor     edx, edx; Val
0x18001366a  lea     r8d, [rdx+60h]; Size
0x18001366e  lea     rcx, [rbp+380h+var_2F0]; void *
0x180013675  call    memset
0x18001367a  lea     rcx, [rbp+380h+var_2F0]; this
0x180013681  call    ??0CSerializationHelper@@QEAA@XZ; CSerializationHelper::CSerializationHelper(void)
0x180013686  nop
0x180013687  mov     r9, r14; wchar_t *
0x18001368a  lea     rcx, [rbp+380h+var_2F0]; this
0x180013691  call    ?InitDeserializeFromStringWithHeader@CSerializationHelper@@QEAAJKKPEA_W@Z; CSerializationHelper::InitDeserializeFromStringWithHeader(ulong,ulong,wchar_t *)
0x180013696  mov     r15d, eax
0x180013699  mov     rdi, [rbp+380h+var_3E8]
0x18001369d  test    eax, eax
0x18001369f  jns     short loc_1800136A8
0x1800136a1  mov     edx, 0C9h
0x1800136a6  jmp     short loc_1800136E0
0x1800136a8  mov     rdx, r14; bstr
0x1800136ab  lea     rcx, [rbp+380h+var_2F0]; this
0x1800136b2  call    ?ReadFromBSTRWithHeader@CSerializationHelper@@QEAAJPEA_W@Z; CSerializationHelper::ReadFromBSTRWithHeader(wchar_t *)
0x1800136b7  mov     r15d, eax
0x1800136ba  test    eax, eax
0x1800136bc  jns     short loc_1800136C5
0x1800136be  mov     edx, 0CAh
0x1800136c3  jmp     short loc_1800136E0
0x1800136c5  lea     rdx, [rbp+380h+var_2F0]; struct CSerializationHelper *
0x1800136cc  mov     rcx, rdi; this
0x1800136cf  call    ?Deserialize@CDeploymentReportingUpdateGroup@@QEAAJAEAVCSerializationHelper@@@Z; CDeploymentReportingUpdateGroup::Deserialize(CSerializationHelper &)
0x1800136d4  mov     r15d, eax
0x1800136d7  test    eax, eax
0x1800136d9  jns     short loc_1800136EF
0x1800136db  mov     edx, 0CBh
0x1800136e0  mov     r9d, r15d
0x1800136e3  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800136ea  jmp     loc_180013D17
0x1800136ef  xor     ecx, ecx
0x1800136f1  mov     [rsp+480h+var_414], ecx
0x1800136f5  mov     eax, [rdi+14h]
0x1800136f8  lea     r12, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800136ff  test    eax, eax
0x180013701  jz      loc_180013A4C
0x180013707  mov     edx, 0DDh
0x18001370c  mov     [rbp+380h+var_370], 0
0x180013714  xorps   xmm0, xmm0
0x180013717  xor     r8d, r8d
0x18001371a  movups  [rbp+380h+var_398], xmm0
0x18001371e  movups  xmmword ptr [rbp+380h+lpMem], xmm0
0x180013722  mov     [rbp+380h+var_378], r8
0x180013726  xor     esi, esi
0x180013728  mov     [rbp+380h+var_3F8], rsi
0x18001372c  cmp     ecx, eax
0x18001372e  jnb     loc_180013AC1
0x180013734  mov     eax, ecx
0x180013736  shl     rax, 5
0x18001373a  add     rax, [rdi+8]
0x18001373e  movups  xmm0, xmmword ptr [rax]
0x180013741  movups  [rbp+380h+var_3C8], xmm0
0x180013745  movups  xmm1, xmmword ptr [rax+10h]
0x180013749  movups  xmmword ptr [rbp+380h+psz], xmm1
0x18001374d  movups  [rbp+380h+var_3B8], xmm1
0x180013751  movq    rcx, xmm0
0x180013756  test    rcx, rcx
0x180013759  jz      loc_180013AB9
0x18001375f  cmp     [rsp+480h+var_410], 2
0x180013764  jnz     short loc_1800137CC
0x180013766  cmp     [rcx+1DCh], esi
0x18001376c  jz      short loc_1800137CC
0x18001376e  lea     rdx, [rcx+0ECh]; struct tagDSGlobalUpdateId *
0x180013775  lea     rcx, [rbp+380h+var_360]; this
0x180013779  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18001377e  mov     [rsp+480h+var_450], rax
0x180013783  lea     rax, aReportingEvent; "Reporting event already finalized for u"...
0x18001378a  mov     [rsp+480h+var_458], rax
0x18001378f  mov     qword ptr [rsp+480h+var_460], rsi
0x180013794  xor     edx, edx
0x180013796  xor     ecx, ecx
0x180013798  lea     r9d, [rsi+4]
0x18001379c  mov     r8d, 1000000h
0x1800137a2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800137a7  nop
0x1800137a8  xor     ecx, ecx; bstrString
0x1800137aa  call    cs:__imp_SysFreeString
0x1800137b0  nop
0x1800137b1  mov     rcx, [rbp+380h+var_370]
0x1800137b5  test    rcx, rcx
0x1800137b8  jz      short loc_1800137C7
0x1800137ba  mov     rax, [rcx]
0x1800137bd  mov     rax, [rax+10h]
0x1800137c1  call    _guard_dispatch_icall
0x1800137c6  nop
0x1800137c7  jmp     loc_180013A37
0x1800137cc  mov     eax, [rcx+1C0h]
0x1800137d2  mov     [rbp+380h+var_3F0], eax
0x1800137d5  mov     ecx, [rcx+28h]
0x1800137d8  cmp     ecx, 21Dh
0x1800137de  jg      short loc_1800137EB
0x1800137e0  jz      short loc_18001380A
0x1800137e2  sub     ecx, edx
0x1800137e4  jz      short loc_18001380A
0x1800137e6  sub     ecx, 1
0x1800137e9  jmp     short loc_1800137F1
0x1800137eb  sub     ecx, 21Eh
0x1800137f1  jz      short loc_18001380A
0x1800137f3  sub     ecx, 1
0x1800137f6  jz      short loc_18001380A
0x1800137f8  sub     ecx, 1
0x1800137fb  jz      short loc_18001380A
0x1800137fd  cmp     ecx, 1
0x180013800  mov     [rsp+480h+var_418], 1
0x180013808  jnz     short loc_180013812
0x18001380a  mov     [rsp+480h+var_418], 0
0x180013812  lea     rax, [rbp+380h+var_370]
0x180013816  mov     [rsp+480h+var_458], rax
0x18001381b  lea     rax, _GUID_b114a32b_955f_4103_b299_d9ed046e5548
0x180013822  mov     qword ptr [rsp+480h+var_460], rax; int
0x180013827  mov     r9d, 1
0x18001382d  mov     r8d, r9d
0x180013830  psrldq  xmm0, 8
0x180013835  movd    edx, xmm0
0x180013839  lea     rcx, [rbp+380h+var_290]
0x180013840  call    ?GetHandler@CUHHandlerManager@@QEAAJW4tagUHUpdateHandler@@HHAEBU_GUID@@PEAPEAX@Z; CUHHandlerManager::GetHandler(tagUHUpdateHandler,int,int,_GUID const &,void * *)
0x180013845  mov     r15d, eax
0x180013848  mov     rcx, [rbp+388h]; this
0x18001384f  test    eax, eax
0x180013851  jns     short loc_180013874
0x180013853  mov     r9d, eax; char *
0x180013856  mov     r8, r12; unsigned int
0x180013859  mov     edx, 0F3h; void *
0x18001385e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013863  mov     ecx, 80242015h
0x180013868  mov     dword ptr [rbp+380h+var_398], ecx
0x18001386b  mov     dword ptr [rbp+380h+var_398+4], r15d
0x18001386f  jmp     loc_18001398B
0x180013874  mov     [rbp+380h+var_368], 0
0x18001387b  mov     rcx, [rbp+380h+var_370]
0x18001387f  mov     rax, [rcx]
0x180013882  lea     rdx, [rbp+380h+var_368]
0x180013886  mov     rax, [rax+20h]
0x18001388a  call    _guard_dispatch_icall
0x18001388f  mov     r15d, eax
0x180013892  test    eax, eax
0x180013894  js      loc_180013AAF
0x18001389a  xor     ecx, ecx; bstrString
0x18001389c  call    cs:__imp_SysFreeString
0x1800138a2  xor     esi, esi
0x1800138a4  mov     [rbp+380h+var_3F8], rsi
0x1800138a8  mov     rcx, [rbp+380h+psz]; psz
0x1800138ac  test    rcx, rcx
0x1800138af  jz      short loc_1800138C7
0x1800138b1  call    cs:__imp_SysAllocString
0x1800138b7  mov     rsi, rax
0x1800138ba  mov     [rbp+380h+var_3F8], rax
0x1800138be  test    rax, rax
0x1800138c1  jz      loc_180013A8E
0x1800138c7  inc     [rsp+480h+var_41C]
0x1800138cb  mov     rcx, [rbp+380h+var_370]
0x1800138cf  mov     rax, [rcx]
0x1800138d2  lea     r9, [rbp+380h+var_398]
0x1800138d6  mov     r8d, [rsp+480h+var_418]
0x1800138db  mov     rdx, rsi
0x1800138de  mov     rax, [rax+18h]
0x1800138e2  call    _guard_dispatch_icall
0x1800138e7  mov     r15d, eax
0x1800138ea  mov     rcx, [rbp+388h]; this
0x1800138f1  test    eax, eax
0x1800138f3  jns     loc_18001397D
0x1800138f9  mov     r9d, eax; char *
0x1800138fc  mov     r8, r12; unsigned int
0x1800138ff  mov     edx, 101h; void *
0x180013904  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013909  cmp     [rbp+380h+var_368], 0
0x18001390d  jnz     short loc_180013940
0x18001390f  mov     ecx, 0Eh
0x180013914  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180013919  mov     rdx, rax
0x18001391c  call    ?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z; RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)
0x180013921  test    eax, eax
0x180013923  jns     short loc_180013940
0x180013925  cmp     [rbp+380h+var_3F0], 0Ah
0x180013929  jb      short loc_180013940
0x18001392b  mov     ecx, 80242015h
0x180013930  mov     dword ptr [rbp+380h+var_398], ecx
0x180013933  mov     dword ptr [rbp+380h+var_398+4], r15d
0x180013937  mov     dword ptr [rbp+380h+var_398+8], 0
  ... truncated ...
```
