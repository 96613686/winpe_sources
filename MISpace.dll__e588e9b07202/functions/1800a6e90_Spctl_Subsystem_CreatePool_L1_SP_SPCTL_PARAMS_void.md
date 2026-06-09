# Spctl_Subsystem_CreatePool_L1(_SP_SPCTL_PARAMS *,void *)

- ea: `0x1800a6e90`
- end: `0x1800a764b`
- name: `?Spctl_Subsystem_CreatePool_L1@@YAKPEAU_SP_SPCTL_PARAMS@@PEAX@Z`
- size: `1979`
- prototype: `unsigned int(struct _SP_SPCTL_PARAMS *, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x18009304c`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x180006cf4`
- `0x180007141`
- `0x18000c704`
- `0x18000cdc8`
- `0x18002602c`
- `0x180029ea0`
- `0x180029ef0`
- `0x180029f60`
- `0x180029fd8`
- `0x18002c430`
- `0x18002cb80`
- `0x180032ba4`
- `0x180036804`
- `0x180045174`
- `0x18004662c`
- `0x18004a390`
- `0x180067a58`
- `0x1800692e8`
- `0x1800a6e90`
- `0x1800ac344`
- `0x1801b5b44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a75c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a75d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a75c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a75d4`

## string_xrefs

- `0x1800a6ec6`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a7070`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a70e3`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a71af`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a7260`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a7370`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a743e`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a74ef`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a7525`: `Spctl_Subsystem_CreatePool_L1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spctl_Subsystem_CreatePool_L1(struct _SP_SPCTL_PARAMS *a1, void *a2, int a3, int a4)
{
  struct _SP_POOL_INFO *v6; // rsi
  unsigned int v7; // eax
  unsigned int PoolErrors; // r14d
  __int64 v10; // rdi
  __int64 v11; // r15
  unsigned int v12; // ecx
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  unsigned int v17; // ebx
  __int64 Drives; // rax
  unsigned int v19; // eax
  int v20; // r8d
  int v21; // r9d
  int PoolTemplate; // eax
  int v23; // r8d
  int v24; // r9d
  char v25; // r11
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rax
  unsigned int v30; // ecx
  __int64 v31; // rax
  unsigned int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // ecx
  DWORD LastError; // eax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v44; // rax
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // [rsp+40h] [rbp-99h] BYREF
  int v49; // [rsp+44h] [rbp-95h] BYREF
  struct _SP_POOL_INFO *v50; // [rsp+48h] [rbp-91h] BYREF
  const char *v51; // [rsp+50h] [rbp-89h] BYREF
  int v52; // [rsp+58h] [rbp-81h]
  struct CSpCluster *v53; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v54; // [rsp+68h] [rbp-71h] BYREF
  HLOCAL v55; // [rsp+70h] [rbp-69h] BYREF
  struct _LIST_ENTRY hMem; // [rsp+78h] [rbp-61h] BYREF
  const char *v57; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v58[16]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v59[40]; // [rsp+A0h] [rbp-39h] BYREF
  struct _GUID Buf1[2]; // [rsp+C8h] [rbp-11h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v48 = 390;
    v50 = (struct _SP_POOL_INFO *)"Spctl_Subsystem_CreatePool_L1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Spctl_Subsystem_CreatePool_L1",
      (unsigned int)&dword_18031F68C,
      a3,
      a4,
      (__int64)&v50,
      (__int64)&v48);
  }
  v53 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
  v53 = 0;
  v54 = 0;
  v55 = 0;
  memset_0(v59, 0, 0x48u);
  v6 = 0;
  v50 = 0;
  v7 = *((_DWORD *)a1 + 142);
  if ( v7 < 0x18 )
    goto LABEL_4;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
LABEL_4:
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
    return 87;
  }
  PoolErrors = 0;
  v10 = *((_QWORD *)a1 + 70);
  v11 = *((_QWORD *)a1 + 72);
  hMem.Blink = &hMem;
  hMem.Flink = &hMem;
  v12 = *(_DWORD *)(v10 + 12);
  if ( v7 < v12 )
    goto LABEL_78;
  if ( *(_DWORD *)(v10 + 16) != 2001 )
    goto LABEL_78;
  if ( v12 < *(_DWORD *)(v10 + 8) )
    goto LABEL_78;
  if ( *(_DWORD *)(v10 + 8) < 0x52u )
    goto LABEL_78;
  v13 = *(unsigned int *)(v10 + 32);
  if ( (unsigned int)v13 < *(_DWORD *)(v10 + 8) )
    goto LABEL_78;
  if ( (unsigned int)v13 > v12 )
    goto LABEL_78;
  if ( (v13 & 3) != 0 )
    goto LABEL_78;
  v14 = v12 - v13;
  if ( v14 < 4 )
    goto LABEL_78;
  v15 = v10 + v13;
  v16 = 16LL * *(unsigned int *)(v10 + v13);
  if ( v16 > 0xFFFFFFFF || (int)v16 + 4 > v14 )
    goto LABEL_78;
  v17 = 0;
  Drives = SuexGetDrives(v58, v15, 0, 0, &hMem, &v54, &v55);
  v51 = *(const char **)Drives;
  v52 = *(_DWORD *)(Drives + 8);
  if ( _mm_cvtsi128_si32((__m128i)(unsigned __int64)v51) < 0 )
  {
    v19 = _status_t::ToSMRC(&v51);
    PoolErrors = v19;
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v48 = v19;
      v49 = 516;
      v50 = (struct _SP_POOL_INFO *)"Spctl_Subsystem_CreatePool_L1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_180397B68,
        (unsigned int)word_18031AF92,
        v20,
        v21,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48);
    }
    goto LABEL_79;
  }
  PoolTemplate = SuGetPoolTemplate(*(unsigned int *)(v10 + 24), &hMem, &v50);
  v25 = 0;
  if ( !PoolTemplate )
  {
    PoolErrors = GleToSmpReturnCode();
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v49 = PoolErrors;
      v48 = 529;
      v51 = "Spctl_Subsystem_CreatePool_L1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)byte_1803221EB,
        v27,
        v28,
        (__int64)&v51,
        (__int64)&v48,
        (__int64)&v49);
    }
    v6 = v50;
    goto LABEL_79;
  }
  v29 = *(unsigned int *)(v10 + 36);
  v6 = v50;
  if ( (_DWORD)v29 )
  {
    if ( (unsigned int)v29 < *(_DWORD *)(v10 + 8) )
      goto LABEL_78;
    v30 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v29 > v30
      || (v29 & 1) != 0
      || (int)StringCbLengthW((const unsigned __int16 *)(v10 + v29), v30 - (unsigned int)v29, (unsigned __int64 *)&v50) < 0 )
    {
      goto LABEL_78;
    }
    if ( (int)StringCchCopyW(
                (unsigned __int16 *)v6 + 12,
                0x100u,
                (const unsigned __int16 *)(v10 + *(unsigned int *)(v10 + 36))) < 0 )
    {
      PoolErrors = 5;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v49 = 5;
        v48 = 561;
        v51 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          5,
          (unsigned int)word_180318E52,
          v23,
          v24,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
      goto LABEL_79;
    }
  }
  v31 = *(unsigned int *)(v10 + 40);
  if ( (_DWORD)v31 )
  {
    if ( (unsigned int)v31 < *(_DWORD *)(v10 + 8) )
      goto LABEL_78;
    v32 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v31 > v32
      || (v31 & 1) != 0
      || (int)StringCbLengthW((const unsigned __int16 *)(v10 + v31), v32 - (unsigned int)v31, (unsigned __int64 *)&v50) < 0 )
    {
      goto LABEL_78;
    }
    if ( (int)StringCchCopyW(
                (unsigned __int16 *)v6 + 268,
                0x400u,
                (const unsigned __int16 *)(v10 + *(unsigned int *)(v10 + 40))) < 0 )
    {
      PoolErrors = 5;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v49 = 5;
        v48 = 594;
        v51 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          5,
          (unsigned int)byte_180321935,
          v23,
          v24,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
      goto LABEL_79;
    }
  }
  if ( *(_BYTE *)(v10 + 48) != v25 )
    *((_DWORD *)v6 + 672) = SmpToSpProvisioningType(*(unsigned __int16 *)(v10 + 50));
  if ( *(_DWORD *)(v10 + 8) >= 0x56u && *(_BYTE *)(v10 + 82) != v25 )
    *((_DWORD *)v6 + 676) = SmpToSpMediaType(*(unsigned __int16 *)(v10 + 84));
  if ( *(_BYTE *)(v10 + 60) != v25 )
    *((_DWORD *)v6 + 679) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v10 + 62));
  v33 = *(unsigned int *)(v10 + 44);
  if ( !(_DWORD)v33 )
  {
LABEL_54:
    if ( *(_BYTE *)(v10 + 52) != v25 )
      *((_DWORD *)v6 + 665) = *(_DWORD *)(v10 + 56);
    if ( *(_DWORD *)(v10 + 8) >= 0x68u && *(_BYTE *)(v10 + 88) != v25 )
    {
      if ( *(_QWORD *)(v10 + 96) > 0xFFFFFFFF )
      {
        PoolErrors = 5;
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v49 = 5;
          v48 = 655;
          v51 = "Spctl_Subsystem_CreatePool_L1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            5,
            (unsigned int)byte_18031FF5D,
            v23,
            v24,
            (__int64)&v51,
            (__int64)&v48,
            (__int64)&v49);
        }
        goto LABEL_79;
      }
      *((_DWORD *)v6 + 662) = *(_DWORD *)(v10 + 96);
    }
    if ( *(_DWORD *)(v10 + 8) >= 0x78u && *(_BYTE *)(v10 + 104) != v25 )
      *((_QWORD *)v6 + 335) = *(_QWORD *)(v10 + 112);
    if ( *(_BYTE *)(v10 + 64) != v25 )
      *((_QWORD *)v6 + 350) = *(_QWORD *)(v10 + 72);
    if ( *(_BYTE *)(v10 + 80) != v25 && *(_BYTE *)(v10 + 81) == 1 )
      *((_QWORD *)v6 + 350) = -1;
    if ( (unsigned int)SuexCreatePool(
                         v6,
                         &hMem,
                         v54,
                         (unsigned __int16 *const)(v11 + 4),
                         a2,
                         (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v55) )
    {
      if ( *(_BYTE *)(v10 + 28) )
      {
        SuexParseIdLite((const unsigned __int16 *)(v11 + 4), (struct _SUEX_ID *)v59);
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
        if ( CSpCluster::GetInstance(&v53) == MI_RESULT_OK )
        {
          v39 = CSpCluster::AddPoolToCluster(v53, v58, Buf1);
          v51 = *(const char **)v39;
          v52 = *(_DWORD *)(v39 + 8);
          if ( _mm_cvtsi128_si32((__m128i)(unsigned __int64)v51) < 0 )
          {
            PoolErrors = _status_t::ToSMRC(&v51);
            if ( (unsigned int)dword_180397B68 > 2 )
            {
              v49 = PoolErrors;
              v48 = 698;
              v51 = "Spctl_Subsystem_CreatePool_L1";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v40,
                (unsigned int)word_18031C1CA,
                v41,
                v42,
                (__int64)&v51,
                (__int64)&v48,
                (__int64)&v49);
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      PoolErrors = _TranslateCreatePoolErrors(LastError);
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v49 = PoolErrors;
        v48 = 684;
        v51 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v36,
          (unsigned int)byte_180322D41,
          v37,
          v38,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v49);
      }
    }
    goto LABEL_79;
  }
  if ( (unsigned int)v33 >= *(_DWORD *)(v10 + 8) )
  {
    v34 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v33 <= v34
      && (v33 & 1) == 0
      && (int)StringCbLengthW((const unsigned __int16 *)(v10 + v33), v34 - (unsigned int)v33, (unsigned __int64 *)&v50) >= 0 )
    {
      *((_DWORD *)v6 + 680) = SmpToSpResiliencyType(v10 + *(unsigned int *)(v10 + 44));
      v25 = 0;
      goto LABEL_54;
    }
  }
LABEL_78:
  v17 = 87;
LABEL_79:
  while ( 1 )
  {
    Flink = hMem.Flink;
    if ( hMem.Flink == &hMem )
      break;
    if ( hMem.Flink->Blink != &hMem || (v44 = hMem.Flink->Flink, hMem.Flink->Flink->Blink != hMem.Flink) )
      __fastfail(3u);
    hMem.Flink = hMem.Flink->Flink;
    v44->Blink = &hMem;
    LocalFree(Flink);
  }
  if ( PoolErrors && PoolErrors != 46011 && memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    SuexDeletePool(Buf1, a2);
  _FillMethodResponse(v11, *((unsigned int *)a1 + 146), PoolErrors, v55, *((_QWORD *)a1 + 74));
  if ( v6 )
    LocalFree(v6);
  v47 = (int)v55;
  if ( v55 )
  {
    LocalFree(v55);
    v55 = 0;
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v49 = 733;
    v57 = "Spctl_Subsystem_CreatePool_L1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v47,
      (unsigned int)qword_18031BDF0,
      v45,
      v46,
      (__int64)&v57,
      (__int64)&v49);
  }
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
  return v17;
}

```

## disassembly

```asm
0x1800a6e90  mov     [rsp-8+arg_10], rbx
0x1800a6e95  push    rbp
0x1800a6e96  push    rsi
0x1800a6e97  push    rdi
0x1800a6e98  push    r12
0x1800a6e9a  push    r13
0x1800a6e9c  push    r14
0x1800a6e9e  push    r15
0x1800a6ea0  lea     rbp, [rsp-27h]
0x1800a6ea5  sub     rsp, 100h
0x1800a6eac  mov     rax, cs:__security_cookie
0x1800a6eb3  xor     rax, rsp
0x1800a6eb6  mov     [rbp+57h+var_40], rax
0x1800a6eba  mov     r12, rdx
0x1800a6ebd  mov     r13, rcx
0x1800a6ec0  mov     eax, cs:dword_180397B68
0x1800a6ec6  lea     rcx, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a6ecd  cmp     eax, 5
0x1800a6ed0  jbe     short loc_1800A6EFF
0x1800a6ed2  mov     [rsp+130h+var_F0], 186h
0x1800a6eda  mov     [rsp+130h+var_E8], rcx
0x1800a6edf  lea     rax, [rsp+130h+var_F0]
0x1800a6ee4  mov     [rsp+130h+var_108], rax
0x1800a6ee9  lea     rax, [rsp+130h+var_E8]
0x1800a6eee  mov     [rsp+130h+var_110], rax
0x1800a6ef3  lea     rdx, dword_18031F68C
0x1800a6efa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a6eff  xor     ebx, ebx
0x1800a6f01  mov     [rbp+57h+var_D0], rbx
0x1800a6f05  lea     rcx, [rbp+57h+var_D0]
0x1800a6f09  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a6f0e  mov     [rbp+57h+var_D0], rbx
0x1800a6f12  mov     [rbp+57h+var_C8], ebx
0x1800a6f15  mov     [rbp+57h+var_C0], rbx
0x1800a6f19  xor     edx, edx; Val
0x1800a6f1b  lea     r8d, [rbx+48h]; Size
0x1800a6f1f  lea     rcx, [rbp+57h+var_90]; void *
0x1800a6f23  call    memset_0
0x1800a6f28  xor     r11d, r11d
0x1800a6f2b  mov     esi, r11d
0x1800a6f2e  mov     [rsp+130h+var_E8], r11
0x1800a6f33  mov     eax, [r13+238h]
0x1800a6f3a  cmp     eax, 18h
0x1800a6f3d  jnb     short loc_1800A6F52
0x1800a6f3f  lea     rcx, [rbp+57h+var_D0]
0x1800a6f43  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a6f48  mov     eax, 57h ; 'W'
0x1800a6f4d  jmp     loc_1800A7624
0x1800a6f52  mov     ecx, 220h
0x1800a6f57  cmp     [r13+248h], ecx
0x1800a6f5e  jnb     short loc_1800A6F6B
0x1800a6f60  mov     rax, [r13+250h]
0x1800a6f67  mov     [rax], ecx
0x1800a6f69  jmp     short loc_1800A6F3F
0x1800a6f6b  mov     r14d, r11d
0x1800a6f6e  mov     rdi, [r13+230h]
0x1800a6f75  mov     r15, [r13+240h]
0x1800a6f7c  lea     rcx, [rbp+57h+hMem]
0x1800a6f80  mov     [rbp+57h+var_B0], rcx
0x1800a6f84  lea     rcx, [rbp+57h+hMem]
0x1800a6f88  mov     [rbp+57h+hMem], rcx
0x1800a6f8c  mov     ecx, [rdi+0Ch]
0x1800a6f8f  cmp     eax, ecx
0x1800a6f91  jb      loc_1800A7520
0x1800a6f97  cmp     dword ptr [rdi+10h], 7D1h
0x1800a6f9e  jnz     loc_1800A7520
0x1800a6fa4  cmp     ecx, [rdi+8]
0x1800a6fa7  jb      loc_1800A7520
0x1800a6fad  cmp     dword ptr [rdi+8], 52h ; 'R'
0x1800a6fb1  jb      loc_1800A7520
0x1800a6fb7  mov     eax, [rdi+20h]
0x1800a6fba  cmp     eax, [rdi+8]
0x1800a6fbd  jb      loc_1800A7520
0x1800a6fc3  cmp     eax, ecx
0x1800a6fc5  ja      loc_1800A7520
0x1800a6fcb  test    al, 3
0x1800a6fcd  jnz     loc_1800A7520
0x1800a6fd3  sub     ecx, eax
0x1800a6fd5  cmp     ecx, 4
0x1800a6fd8  jb      loc_1800A7520
0x1800a6fde  lea     rdx, [rdi+rax]
0x1800a6fe2  mov     eax, [rdx]
0x1800a6fe4  shl     rax, 4
0x1800a6fe8  mov     r8d, 0FFFFFFFFh
0x1800a6fee  cmp     rax, r8
0x1800a6ff1  ja      loc_1800A7520
0x1800a6ff7  add     eax, 4
0x1800a6ffa  cmp     eax, ecx
0x1800a6ffc  ja      loc_1800A7520
0x1800a7002  mov     ebx, r11d
0x1800a7005  lea     rax, [rbp+57h+var_C0]
0x1800a7009  mov     [rsp+130h+var_100], rax
0x1800a700e  lea     rax, [rbp+57h+var_C8]
0x1800a7012  mov     [rsp+130h+var_108], rax
0x1800a7017  lea     rax, [rbp+57h+hMem]
0x1800a701b  mov     [rsp+130h+var_110], rax
0x1800a7020  xor     r9d, r9d
0x1800a7023  xor     r8d, r8d
0x1800a7026  lea     rcx, [rbp+57h+var_A0]
0x1800a702a  call    ?SuexGetDrives@@YA?AV_status_t@@PEAU_SP_IDS@@HKPEAU_LIST_ENTRY@@PEAKPEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; SuexGetDrives(_SP_IDS *,int,ulong,_LIST_ENTRY *,ulong *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x1800a702f  movsd   xmm0, qword ptr [rax]
0x1800a7033  movsd   [rsp+130h+var_E0], xmm0
0x1800a7039  mov     eax, [rax+8]
0x1800a703c  mov     [rsp+130h+var_D8], eax
0x1800a7040  movd    eax, xmm0
0x1800a7044  test    eax, eax
0x1800a7046  jns     short loc_1800A70AB
0x1800a7048  lea     rcx, [rsp+130h+var_E0]
0x1800a704d  call    ?ToSMRC@_status_t@@QEAA?AW4SM_RETURN_CODE@@XZ; _status_t::ToSMRC(void)
0x1800a7052  mov     r14d, eax
0x1800a7055  mov     ecx, cs:dword_180397B68
0x1800a705b  cmp     ecx, 2
0x1800a705e  jbe     loc_1800A7525
0x1800a7064  mov     [rsp+130h+var_F0], eax
0x1800a7068  mov     [rsp+130h+var_EC], 204h
0x1800a7070  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a7077  mov     [rsp+130h+var_E8], rdi
0x1800a707c  lea     rax, [rsp+130h+var_F0]
0x1800a7081  mov     [rsp+130h+var_100], rax
0x1800a7086  lea     rax, [rsp+130h+var_EC]
0x1800a708b  mov     [rsp+130h+var_108], rax
0x1800a7090  lea     rax, [rsp+130h+var_E8]
0x1800a7095  lea     rdx, word_18031AF92
0x1800a709c  mov     [rsp+130h+var_110], rax
0x1800a70a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a70a6  jmp     loc_1800A752C
0x1800a70ab  lea     r8, [rsp+130h+var_E8]
0x1800a70b0  lea     rdx, [rbp+57h+hMem]
0x1800a70b4  mov     ecx, [rdi+18h]
0x1800a70b7  call    ?SuGetPoolTemplate@@YAHW4_SC_VERSION@@PEAU_LIST_ENTRY@@PEAPEAU_SP_POOL_INFO@@@Z; SuGetPoolTemplate(_SC_VERSION,_LIST_ENTRY *,_SP_POOL_INFO * *)
0x1800a70bc  xor     r11d, r11d
0x1800a70bf  test    eax, eax
0x1800a70c1  jnz     short loc_1800A712D
0x1800a70c3  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800a70c8  mov     r14d, eax
0x1800a70cb  mov     eax, cs:dword_180397B68
0x1800a70d1  cmp     eax, 2
0x1800a70d4  jbe     short loc_1800A7123
0x1800a70d6  mov     [rsp+130h+var_EC], r14d
0x1800a70db  mov     [rsp+130h+var_F0], 211h
0x1800a70e3  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a70ea  mov     [rsp+130h+var_E0], rdi
0x1800a70ef  lea     rax, [rsp+130h+var_EC]
0x1800a70f4  mov     [rsp+130h+var_100], rax
0x1800a70f9  lea     rax, [rsp+130h+var_F0]
0x1800a70fe  mov     [rsp+130h+var_108], rax
0x1800a7103  lea     rax, [rsp+130h+var_E0]
0x1800a7108  mov     [rsp+130h+var_110], rax
0x1800a710d  lea     rdx, byte_1803221EB
0x1800a7114  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a7119  mov     rsi, [rsp+130h+var_E8]
0x1800a711e  jmp     loc_1800A752C
0x1800a7123  mov     rsi, [rsp+130h+var_E8]
0x1800a7128  jmp     loc_1800A7525
0x1800a712d  mov     eax, [rdi+24h]
0x1800a7130  mov     rsi, [rsp+130h+var_E8]
0x1800a7135  test    eax, eax
0x1800a7137  jz      loc_1800A71E0
0x1800a713d  cmp     eax, [rdi+8]
0x1800a7140  jb      loc_1800A7520
0x1800a7146  mov     ecx, [rdi+0Ch]
0x1800a7149  cmp     eax, ecx
0x1800a714b  ja      loc_1800A7520
0x1800a7151  test    al, 1
0x1800a7153  jnz     loc_1800A7520
0x1800a7159  sub     ecx, eax
0x1800a715b  mov     edx, ecx; unsigned __int64
0x1800a715d  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a7161  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a7166  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a716b  test    eax, eax
0x1800a716d  js      loc_1800A7520
0x1800a7173  mov     r8d, [rdi+24h]
0x1800a7177  add     r8, rdi; unsigned __int16 *
0x1800a717a  lea     rcx, [rsi+18h]; unsigned __int16 *
0x1800a717e  mov     edx, 100h; unsigned __int64
0x1800a7183  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a7188  test    eax, eax
0x1800a718a  jns     short loc_1800A71E0
0x1800a718c  mov     ecx, 5
0x1800a7191  mov     r14d, ecx
0x1800a7194  mov     eax, cs:dword_180397B68
0x1800a719a  cmp     eax, 2
0x1800a719d  jbe     loc_1800A7525
0x1800a71a3  mov     [rsp+130h+var_EC], ecx
0x1800a71a7  mov     [rsp+130h+var_F0], 231h
0x1800a71af  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a71b6  mov     [rsp+130h+var_E0], rdi
0x1800a71bb  lea     rax, [rsp+130h+var_EC]
0x1800a71c0  mov     [rsp+130h+var_100], rax
0x1800a71c5  lea     rax, [rsp+130h+var_F0]
0x1800a71ca  mov     [rsp+130h+var_108], rax
0x1800a71cf  lea     rax, [rsp+130h+var_E0]
0x1800a71d4  lea     rdx, word_180318E52
0x1800a71db  jmp     loc_1800A709C
0x1800a71e0  mov     eax, [rdi+28h]
0x1800a71e3  test    eax, eax
0x1800a71e5  jz      loc_1800A7291
0x1800a71eb  cmp     eax, [rdi+8]
0x1800a71ee  jb      loc_1800A7520
0x1800a71f4  mov     ecx, [rdi+0Ch]
0x1800a71f7  cmp     eax, ecx
0x1800a71f9  ja      loc_1800A7520
0x1800a71ff  test    al, 1
0x1800a7201  jnz     loc_1800A7520
0x1800a7207  sub     ecx, eax
0x1800a7209  mov     edx, ecx; unsigned __int64
0x1800a720b  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a720f  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a7214  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a7219  test    eax, eax
0x1800a721b  js      loc_1800A7520
0x1800a7221  mov     r8d, [rdi+28h]
0x1800a7225  add     r8, rdi; unsigned __int16 *
0x1800a7228  lea     rcx, [rsi+218h]; unsigned __int16 *
0x1800a722f  mov     edx, 400h; unsigned __int64
0x1800a7234  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a7239  test    eax, eax
0x1800a723b  jns     short loc_1800A7291
0x1800a723d  mov     ecx, 5
0x1800a7242  mov     r14d, ecx
0x1800a7245  mov     eax, cs:dword_180397B68
0x1800a724b  cmp     eax, 2
0x1800a724e  jbe     loc_1800A7525
0x1800a7254  mov     [rsp+130h+var_EC], ecx
0x1800a7258  mov     [rsp+130h+var_F0], 252h
0x1800a7260  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a7267  mov     [rsp+130h+var_E0], rdi
0x1800a726c  lea     rax, [rsp+130h+var_EC]
0x1800a7271  mov     [rsp+130h+var_100], rax
0x1800a7276  lea     rax, [rsp+130h+var_F0]
0x1800a727b  mov     [rsp+130h+var_108], rax
0x1800a7280  lea     rax, [rsp+130h+var_E0]
0x1800a7285  lea     rdx, byte_180321935
0x1800a728c  jmp     loc_1800A709C
0x1800a7291  cmp     [rdi+30h], r11b
0x1800a7295  jz      short loc_1800A72A6
0x1800a7297  movzx   ecx, word ptr [rdi+32h]
0x1800a729b  call    ?SmpToSpProvisioningType@@YA?AW4_SP_PROVISIONING_TYPE@@G@Z; SmpToSpProvisioningType(ushort)
0x1800a72a0  mov     [rsi+0A80h], eax
0x1800a72a6  cmp     dword ptr [rdi+8], 56h ; 'V'
0x1800a72aa  jb      short loc_1800A72C1
0x1800a72ac  cmp     [rdi+52h], r11b
0x1800a72b0  jz      short loc_1800A72C1
0x1800a72b2  movzx   ecx, word ptr [rdi+54h]
0x1800a72b6  call    ?SmpToSpMediaType@@YA?AW4_SC_MEDIA_TYPE@@W4MEDIA_TYPE@SM_CONSTANTS@@@Z; SmpToSpMediaType(SM_CONSTANTS::MEDIA_TYPE)
0x1800a72bb  mov     [rsi+0A90h], eax
0x1800a72c1  cmp     [rdi+3Ch], r11b
0x1800a72c5  jz      short loc_1800A72D6
0x1800a72c7  movzx   ecx, word ptr [rdi+3Eh]
0x1800a72cb  call    ?SmpToSpFaultDomainType@@YA?AW4_SC_FD_TYPE@@G@Z; SmpToSpFaultDomainType(ushort)
0x1800a72d0  mov     [rsi+0A9Ch], eax
0x1800a72d6  mov     eax, [rdi+2Ch]
0x1800a72d9  test    eax, eax
0x1800a72db  jz      short loc_1800A7327
0x1800a72dd  cmp     eax, [rdi+8]
0x1800a72e0  jb      loc_1800A7520
0x1800a72e6  mov     ecx, [rdi+0Ch]
0x1800a72e9  cmp     eax, ecx
0x1800a72eb  ja      loc_1800A7520
0x1800a72f1  test    al, 1
0x1800a72f3  jnz     loc_1800A7520
0x1800a72f9  sub     ecx, eax
0x1800a72fb  mov     edx, ecx; unsigned __int64
0x1800a72fd  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a7301  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a7306  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a730b  test    eax, eax
0x1800a730d  js      loc_1800A7520
0x1800a7313  mov     ecx, [rdi+2Ch]
0x1800a7316  add     rcx, rdi
0x1800a7319  call    ?SmpToSpResiliencyType@@YA?AW4_SP_RESILIENCY_TYPE@@PEBG@Z; SmpToSpResiliencyType(ushort const *)
0x1800a731e  mov     [rsi+0AA0h], eax
0x1800a7324  xor     r11d, r11d
0x1800a7327  cmp     [rdi+34h], r11b
0x1800a732b  jz      short loc_1800A7336
0x1800a732d  mov     eax, [rdi+38h]
0x1800a7330  mov     [rsi+0A64h], eax
0x1800a7336  cmp     dword ptr [rdi+8], 68h ; 'h'
0x1800a733a  jb      short loc_1800A73AA
0x1800a733c  cmp     [rdi+58h], r11b
0x1800a7340  jz      short loc_1800A73AA
0x1800a7342  mov     eax, 0FFFFFFFFh
0x1800a7347  cmp     [rdi+60h], rax
0x1800a734b  jbe     short loc_1800A73A1
0x1800a734d  mov     ecx, 5
0x1800a7352  mov     r14d, ecx
0x1800a7355  mov     eax, cs:dword_180397B68
0x1800a735b  cmp     eax, 2
0x1800a735e  jbe     loc_1800A7525
0x1800a7364  mov     [rsp+130h+var_EC], ecx
0x1800a7368  mov     [rsp+130h+var_F0], 28Fh
0x1800a7370  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a7377  mov     [rsp+130h+var_E0], rdi
0x1800a737c  lea     rax, [rsp+130h+var_EC]
0x1800a7381  mov     [rsp+130h+var_100], rax
0x1800a7386  lea     rax, [rsp+130h+var_F0]
0x1800a738b  mov     [rsp+130h+var_108], rax
0x1800a7390  lea     rax, [rsp+130h+var_E0]
0x1800a7395  lea     rdx, byte_18031FF5D
  ... truncated ...
```
