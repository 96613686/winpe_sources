# CFilterSink::Init(CFilterPipeClient *,CriticalSection *,CTPtrKPtrHashMap<CFilterSinkID,CFilterSinkID,CFilterSinkID> *,ISearchIdleCallback *,ulong)

- ea: `0x14003cd00`
- end: `0x14003d4bd`
- name: `?Init@CFilterSink@@QEAAJPEAVCFilterPipeClient@@PEAVCriticalSection@@PEAV?$CTPtrKPtrHashMap@VCFilterSinkID@@V1@V1@@@PEAUISearchIdleCallback@@K@Z`
- size: `1981`
- prototype: `__int64 __usercall@<rax>(CFilterSink *this@<rcx>, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x1400055b4`
- `0x14000c91c`
- `0x14000eb08`
- `0x14000f2ec`
- `0x1400102a0`
- `0x140015958`
- `0x14001eb94`
- `0x1400200d4`
- `0x1400317a8`
- `0x140033cbc`
- `0x14003bfbc`
- `0x14003ca9c`
- `0x14003cc34`
- `0x14003cd00`
- `0x14003d4c4`
- `0x14003de50`
- `0x14004bb64`
- `0x14004bd34`
- `0x14004dddc`
- `0x14004f0f4`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d378`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d378`

## string_xrefs

- `0x14003d398`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003d451`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003d491`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003d485`: `[SrchFilterDaemon] Thread Pipe failed to switch into read mode`
- `0x14003d445`: `[SrchFilterDaemon] Thread Pipe failed to switch into write mode`
- `0x14003d46b`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003d4ab`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CFilterSink::Init(CFilterSink *this, __int64 a2, CFilterSinkID *a3, ...)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  struct ISearchIdleCallback **v6; // rsi
  wchar_t *v7; // rax
  CFilterSinkID *v8; // r14
  int v10; // ebx
  const wchar_t *v11; // r9
  int BufferWithCallback; // ebx
  int v13; // eax
  int v14; // r8d
  unsigned int v15; // edx
  unsigned int v16; // ecx
  unsigned int *v17; // rsi
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // edx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  int v24; // r8d
  unsigned int v25; // edx
  unsigned int v26; // ecx
  unsigned int v27; // r8d
  int *v28; // rax
  int v29; // ecx
  int v30; // ecx
  unsigned int v31; // edx
  _DWORD *v32; // rcx
  int v33; // ecx
  unsigned int v34; // edx
  _DWORD *v35; // rcx
  _DWORD *v36; // r15
  int v37; // ecx
  unsigned int v38; // edx
  _DWORD *v39; // rcx
  int v40; // ecx
  unsigned int v41; // edx
  _DWORD *v42; // rcx
  int v43; // r8d
  unsigned int v44; // ecx
  unsigned int v45; // edx
  unsigned int v46; // r8d
  unsigned int *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  const wchar_t *v50; // r9
  struct CSingleLink **v51; // rsi
  const wchar_t *v52; // r9
  unsigned int v53; // eax
  unsigned int v54; // eax
  int v55; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  CFilterSinkID *v57; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *v58; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  __int64 v60; // [rsp+90h] [rbp+50h]
  __int64 v61; // [rsp+98h] [rbp+58h] BYREF
  va_list va1; // [rsp+98h] [rbp+58h]
  va_list va2; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v58 = va_arg(va1, wchar_t *);
  v60 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v61 = va_arg(va2, _QWORD);
  v57 = a3;
  if ( a2 )
  {
    v4 = g_pFilterSinkMap;
    if ( g_pFilterSinkMap )
    {
      v5 = g_dwCallBackIntervalInMS;
      *((_DWORD *)this + 633) = 0;
      *((_QWORD *)this + 133) = a2;
      *((_QWORD *)this + 318) = &g_CriticalSection;
      *((_QWORD *)this + 319) = v4;
      *((_DWORD *)this + 648) = 0;
      *((_QWORD *)this + 326) = a2;
      v6 = (struct ISearchIdleCallback **)((char *)this + 2656);
      TComPointer<IFilter>::operator=((char *)this + 2656, v60);
      *((_DWORD *)this + 666) = v5;
      v7 = (wchar_t *)operator new(0x290u, (const struct std::nothrow_t *)&std::nothrow);
      v58 = v7;
      if ( v7 )
        v8 = CFilterSinkID::CFilterSinkID((CFilterSinkID *)v7);
      else
        v8 = 0;
      v57 = v8;
      if ( !v8 )
      {
        TPointer<CFilterSinkID>::~TPointer<CFilterSinkID>(&v57);
        return 2147942414LL;
      }
      v10 = CShMPipe::Want2ReadWithCallback(*((CShMPipe **)this + 133), *v6, *((_DWORD *)this + 666));
      if ( v10 < 0 )
      {
        if ( v10 != -2147217996 )
          SearchIndexerTrace::Error(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
            (const wchar_t *)0x51,
            (unsigned int)L"[SrchFilterDaemon] Thread Pipe failed to switch into read mode",
            v11);
        v54 = wil::verify_hresult<long>((unsigned int)v10);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
          (const char *)v54,
          v55);
      }
      BufferWithCallback = CFilterSink::ReadBufferWithCallback(this);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
      {
        v13 = *((_DWORD *)this + 422);
        if ( (v13 & 0x100000) != 0 )
          *((_DWORD *)this + 662) |= 0x100000u;
        if ( (v13 & 0x200000) != 0 )
          *((_DWORD *)this + 662) |= 0x200000u;
      }
      v58 = 0;
      LODWORD(v61) = 0;
      if ( BufferWithCallback < 0 )
        goto LABEL_64;
      v14 = *((_DWORD *)this + 660);
      v15 = (v14 + 3) & 0xFFFFFFFC;
      v16 = v15 - v14;
      v17 = (unsigned int *)((char *)this + 2644);
      if ( v15 == v14 )
      {
        v15 = *((_DWORD *)this + 660);
      }
      else
      {
        *((_QWORD *)this + 329) += v16;
        *v17 -= v16;
        *((_DWORD *)this + 660) = v15;
      }
      v18 = *v17;
      if ( *v17 >= 4 )
      {
        *((_QWORD *)this + 329) += 4LL;
        v19 = v18 - 4;
        *v17 = v19;
        v20 = v15 + 4;
        *((_DWORD *)this + 660) = v20;
        v21 = (v20 + 3) & 0xFFFFFFFC;
        v22 = v21 - v20;
        if ( v21 == v20 )
        {
          v21 = v20;
        }
        else
        {
          *((_QWORD *)this + 329) += v22;
          *v17 -= v22;
          v19 = *v17;
          *((_DWORD *)this + 660) = v21;
        }
        if ( v19 >= 4 )
        {
          *((_QWORD *)this + 329) += 4LL;
          *v17 = v19 - 4;
          *((_DWORD *)this + 660) = v21 + 4;
          BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
          if ( BufferWithCallback < 0 )
            goto LABEL_64;
          (*(void (__fastcall **)(__int64, wchar_t *, _QWORD, _QWORD))(*((_QWORD *)v8 + 24) + 32LL))(
            (__int64)v8 + 192,
            v58,
            0,
            (unsigned int)v61);
          BufferWithCallback = CURL::Init((CFilterSink *)((char *)this + 1072), v58, v23);
          if ( BufferWithCallback < 0 )
            goto LABEL_64;
          v24 = *((_DWORD *)this + 660);
          v25 = (v24 + 3) & 0xFFFFFFFC;
          v26 = v25 - v24;
          if ( v25 == v24 )
          {
            v25 = *((_DWORD *)this + 660);
          }
          else
          {
            *((_QWORD *)this + 329) += v26;
            *v17 -= v26;
            *((_DWORD *)this + 660) = v25;
          }
          v27 = *v17;
          if ( *v17 >= 4 )
          {
            v28 = (int *)*((_QWORD *)this + 329);
            v29 = *v28;
            *((_QWORD *)this + 329) = v28 + 1;
            *v17 = v27 - 4;
            *((_DWORD *)this + 660) = v25 + 4;
            *((_DWORD *)v8 + 152) = v29;
            BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
            if ( BufferWithCallback < 0 )
              goto LABEL_64;
            (*(void (__fastcall **)(__int64, wchar_t *, _QWORD, _QWORD))(*((_QWORD *)v8 + 12) + 32LL))(
              (__int64)v8 + 96,
              v58,
              0,
              (unsigned int)v61);
            BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
            if ( BufferWithCallback < 0 )
              goto LABEL_64;
            (*(void (__fastcall **)(CFilterSinkID *, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v8 + 32LL))(
              v8,
              v58,
              0,
              (unsigned int)v61);
            BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
            if ( BufferWithCallback < 0 )
              goto LABEL_64;
            (*(void (__fastcall **)(char *, wchar_t *, _QWORD, _QWORD))(*((_QWORD *)this + 197) + 32LL))(
              (char *)this + 1576,
              v58,
              0,
              (unsigned int)v61);
            BufferWithCallback = CFilterSink::GetFILETIME(this, (struct _FILETIME *)this + 209);
            if ( BufferWithCallback < 0 )
              goto LABEL_64;
            if ( this == (CFilterSink *)-1680LL )
              goto LABEL_56;
            v30 = *((_DWORD *)this + 660);
            v31 = ((v30 + 3) & 0xFFFFFFFC) - v30;
            if ( v31 )
            {
              *((_QWORD *)this + 329) += v31;
              *v17 -= v31;
              *((_DWORD *)this + 660) = (v30 + 3) & 0xFFFFFFFC;
            }
            if ( *v17 >= 4 )
            {
              v32 = (_DWORD *)*((_QWORD *)this + 329);
              *((_DWORD *)this + 420) = *v32;
              *((_QWORD *)this + 329) = v32 + 1;
              *v17 -= 4;
              *((_DWORD *)this + 660) += 4;
              if ( this == (CFilterSink *)-1684LL )
                goto LABEL_56;
              v33 = *((_DWORD *)this + 660);
              v34 = ((v33 + 3) & 0xFFFFFFFC) - v33;
              if ( v34 )
              {
                *((_QWORD *)this + 329) += v34;
                *v17 -= v34;
                *((_DWORD *)this + 660) = (v33 + 3) & 0xFFFFFFFC;
              }
              if ( *v17 < 4 )
                goto LABEL_58;
              v35 = (_DWORD *)*((_QWORD *)this + 329);
              *((_DWORD *)this + 421) = *v35;
              *((_QWORD *)this + 329) = v35 + 1;
              *v17 -= 4;
              *((_DWORD *)this + 660) += 4;
              v36 = (_DWORD *)((char *)this + 1688);
              if ( this == (CFilterSink *)-1688LL )
                goto LABEL_56;
              v37 = *((_DWORD *)this + 660);
              v38 = ((v37 + 3) & 0xFFFFFFFC) - v37;
              if ( v38 )
              {
                *((_QWORD *)this + 329) += v38;
                *v17 -= v38;
                *((_DWORD *)this + 660) = (v37 + 3) & 0xFFFFFFFC;
              }
              if ( *v17 < 4 )
                goto LABEL_58;
              v39 = (_DWORD *)*((_QWORD *)this + 329);
              *v36 = *v39;
              *((_QWORD *)this + 329) = v39 + 1;
              *v17 -= 4;
              *((_DWORD *)this + 660) += 4;
              if ( this == (CFilterSink *)-1692LL )
              {
LABEL_56:
                BufferWithCallback = -2147467261;
LABEL_64:
                TPointer<CFilterSinkID>::~TPointer<CFilterSinkID>(&v57);
                return (unsigned int)BufferWithCallback;
              }
              v40 = *((_DWORD *)this + 660);
              v41 = ((v40 + 3) & 0xFFFFFFFC) - v40;
              if ( v41 )
              {
                *((_QWORD *)this + 329) += v41;
                *v17 -= v41;
                *((_DWORD *)this + 660) = (v40 + 3) & 0xFFFFFFFC;
              }
              if ( *v17 >= 4 )
              {
                v42 = (_DWORD *)*((_QWORD *)this + 329);
                *((_DWORD *)this + 423) = *v42;
                *((_QWORD *)this + 329) = v42 + 1;
                *v17 -= 4;
                *((_DWORD *)this + 660) += 4;
                BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
                if ( BufferWithCallback < 0 )
                  goto LABEL_64;
                (*(void (__fastcall **)(char *, wchar_t *, _QWORD, _QWORD))(*((_QWORD *)this + 212) + 32LL))(
                  (char *)this + 1696,
                  v58,
                  0,
                  (unsigned int)v61);
                BufferWithCallback = CFilterSink::GetWStr(this, (wchar_t **)va, (unsigned int *)va1);
                if ( BufferWithCallback < 0 )
                  goto LABEL_64;
                (*(void (__fastcall **)(char *, wchar_t *, _QWORD, _QWORD))(*((_QWORD *)this + 264) + 32LL))(
                  (char *)this + 2112,
                  v58,
                  0,
                  (unsigned int)v61);
                v43 = *((_DWORD *)this + 660);
                v44 = (v43 + 3) & 0xFFFFFFFC;
                v45 = v44 - v43;
                if ( v44 == v43 )
                {
                  v44 = *((_DWORD *)this + 660);
                }
                else
                {
                  *((_QWORD *)this + 329) += v45;
                  *v17 -= v45;
                  *((_DWORD *)this + 660) = v44;
                }
                v46 = *v17;
                if ( *v17 >= 4 )
                {
                  v47 = (unsigned int *)*((_QWORD *)this + 329);
                  v48 = *v47;
                  *((_QWORD *)this + 329) = v47 + 1;
                  *v17 = v46 - 4;
                  *((_DWORD *)this + 660) = v44 + 4;
                  *((_DWORD *)this + 668) = v48;
                  if ( this == (CFilterSink *)-2680LL )
                    goto LABEL_56;
                  if ( *v17 >= (unsigned int)v48 )
                  {
                    v49 = *((_QWORD *)this + 329);
                    *((_QWORD *)this + 335) = v49;
                    *((_QWORD *)this + 329) = v49 + v48;
                    *v17 -= v48;
                    *((_DWORD *)this + 660) += v48;
                    LODWORD(v49) = *v36;
                    *((_DWORD *)this + 388) = (*v36 >> 4) & 1;
                    *((_DWORD *)this + 389) = ((unsigned int)v49 >> 5) & 1;
                    *((_DWORD *)this + 390) = ((unsigned int)v49 >> 6) & 1;
                    *((_DWORD *)this + 392) = ((unsigned int)v49 >> 7) & 1;
                    *((_DWORD *)this + 391) = ((unsigned int)v49 >> 10) & 1;
                    *((_DWORD *)this + 393) = ((unsigned int)v49 >> 12) & 1;
                    BufferWithCallback = CShMPipe::Want2Write(*((CShMPipe **)this + 133), 1);
                    if ( BufferWithCallback < 0 )
                    {
                      if ( BufferWithCallback != -2147217996 )
                        SearchIndexerTrace::Error(
                          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
                          (const wchar_t *)0xCD,
                          (unsigned int)L"[SrchFilterDaemon] Thread Pipe failed to switch into write mode",
                          v50);
                      v53 = wil::verify_hresult<long>((unsigned int)BufferWithCallback);
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0xCF,
                        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
                        (const char *)v53,
                        v55);
                    }
                    v58 = (wchar_t *)*((_QWORD *)this + 318);
                    EnterCriticalSection((LPCRITICAL_SECTION)v58);
                    v51 = *(struct CSingleLink ***)CTPtrKPtrHashMap<CFilterSinkID,CFilterSinkID,CFilterSinkID>::Lookup(
                                                     *((_QWORD *)this + 319),
                                                     v8);
                    v52 = (const wchar_t *)*((_QWORD *)v8 + 25);
                    if ( v51 )
                    {
                      SearchIndexerTrace::Information(
                        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
                        (const wchar_t *)0xE9,
                        (unsigned int)L"[SrchFilterDaemon] AddRef'ing %ls to CFilterSink map\n",
                        v52);
                      CLnkList::InsertAfter((CLnkList *)(v51 + 78), v51[80], this);
                      v8 = (CFilterSinkID *)v51;
                    }
                    else
                    {
                      SearchIndexerTrace::Information(
                        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
                        (const wchar_t *)0xDD,
                        (unsigned int)L"[SrchFilterDaemon] Inserting %ls to CFilterSink map\n",
                        v52);
                      CLnkList::InsertAfter(
                        (CFilterSinkID *)((char *)v8 + 624),
                        *((struct CSingleLink **)v8 + 80),
                        this);
                      CTPtrKPtrHashMap<CFilterSinkID,CFilterSinkID,CFilterSinkID>::Insert(
                        *((_QWORD *)this + 319),
                        v8,
                        v8);
                      v57 = 0;
                    }
                    *((_QWORD *)this + 320) = v8;
                    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>((wchar_t **)va);
                    goto LABEL_64;
                  }
                }
              }
            }
          }
        }
      }
LABEL_58:
      BufferWithCallback = -2147218158;
      goto LABEL_64;
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x14003cd00  mov     [rsp-28h+arg_18], r9
0x14003cd05  mov     [rsp-28h+arg_10], r8
0x14003cd0a  push    rbp
0x14003cd0b  push    rsi
0x14003cd0c  push    rdi
0x14003cd0d  push    r14
0x14003cd0f  push    r15
0x14003cd11  mov     rbp, rsp
0x14003cd14  sub     rsp, 40h
0x14003cd18  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x14003cd20  mov     [rsp+40h+arg_0], rbx
0x14003cd25  mov     rdi, rcx
0x14003cd28  test    rdx, rdx
0x14003cd2b  jz      loc_14003D427
0x14003cd31  mov     rax, cs:?g_pFilterSinkMap@@3PEAV?$CTPtrKPtrHashMap@VCFilterSinkID@@V1@V1@@@EA; CTPtrKPtrHashMap<CFilterSinkID,CFilterSinkID,CFilterSinkID> * g_pFilterSinkMap
0x14003cd38  test    rax, rax
0x14003cd3b  jz      loc_14003D427
0x14003cd41  mov     ebx, cs:?g_dwCallBackIntervalInMS@@3KA; ulong g_dwCallBackIntervalInMS
0x14003cd47  mov     dword ptr [rcx+9E4h], 0
0x14003cd51  mov     [rcx+428h], rdx
0x14003cd58  lea     rcx, ?g_CriticalSection@@3VCriticalSection@@A; CriticalSection g_CriticalSection
0x14003cd5f  mov     [rdi+9F0h], rcx
0x14003cd66  mov     [rdi+9F8h], rax
0x14003cd6d  mov     dword ptr [rdi+0A20h], 0
0x14003cd77  mov     [rdi+0A30h], rdx
0x14003cd7e  lea     rsi, [rdi+0A60h]
0x14003cd85  mov     rdx, [rbp+arg_20]
0x14003cd89  mov     rcx, rsi
0x14003cd8c  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x14003cd91  mov     [rdi+0A68h], ebx
0x14003cd97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003cd9e  mov     ecx, 290h; unsigned __int64
0x14003cda3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003cda8  mov     [rbp+arg_18], rax
0x14003cdac  test    rax, rax
0x14003cdaf  jz      short loc_14003CDBE
0x14003cdb1  mov     rcx, rax; this
0x14003cdb4  call    ??0CFilterSinkID@@QEAA@XZ; CFilterSinkID::CFilterSinkID(void)
0x14003cdb9  mov     r14, rax
0x14003cdbc  jmp     short loc_14003CDC1
0x14003cdbe  xor     r14d, r14d
0x14003cdc1  mov     [rbp+arg_10], r14
0x14003cdc5  test    r14, r14
0x14003cdc8  jnz     short loc_14003CDDD
0x14003cdca  lea     rcx, [rbp+arg_10]
0x14003cdce  call    ??1?$TPointer@VCFilterSinkID@@@@QEAA@XZ; TPointer<CFilterSinkID>::~TPointer<CFilterSinkID>(void)
0x14003cdd3  mov     eax, 8007000Eh
0x14003cdd8  jmp     loc_14003D42C
0x14003cddd  mov     r8d, [rdi+0A68h]; unsigned int
0x14003cde4  mov     rdx, [rsi]; struct ISearchIdleCallback *
0x14003cde7  mov     rcx, [rdi+428h]; this
0x14003cdee  call    ?Want2ReadWithCallback@CShMPipe@@QEAAJPEAUISearchIdleCallback@@K@Z; CShMPipe::Want2ReadWithCallback(ISearchIdleCallback *,ulong)
0x14003cdf3  mov     ebx, eax
0x14003cdf5  test    eax, eax
0x14003cdf7  js      loc_14003D47D
0x14003cdfd  mov     rcx, rdi; this
0x14003ce00  call    ?ReadBufferWithCallback@CFilterSink@@AEAAJXZ; CFilterSink::ReadBufferWithCallback(void)
0x14003ce05  mov     ebx, eax
0x14003ce07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x14003ce0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x14003ce13  test    al, al
0x14003ce15  jz      short loc_14003CE3B
0x14003ce17  mov     eax, [rdi+698h]
0x14003ce1d  mov     ecx, 100000h
0x14003ce22  test    ecx, eax
0x14003ce24  jz      short loc_14003CE2C
0x14003ce26  or      [rdi+0A58h], ecx
0x14003ce2c  mov     ecx, 200000h
0x14003ce31  test    ecx, eax
0x14003ce33  jz      short loc_14003CE3B
0x14003ce35  or      [rdi+0A58h], ecx
0x14003ce3b  mov     [rbp+arg_18], 0
0x14003ce43  mov     dword ptr [rbp+arg_28], 0
0x14003ce4a  test    ebx, ebx
0x14003ce4c  js      loc_14003D41A
0x14003ce52  mov     r8d, [rdi+0A50h]
0x14003ce59  lea     eax, [r8+3]
0x14003ce5d  mov     r15d, 0FFFFFFFCh
0x14003ce63  and     eax, r15d
0x14003ce66  mov     edx, eax
0x14003ce68  mov     ecx, eax
0x14003ce6a  sub     ecx, r8d
0x14003ce6d  lea     rsi, [rdi+0A54h]
0x14003ce74  jz      short loc_14003CE89
0x14003ce76  mov     eax, ecx
0x14003ce78  add     [rdi+0A48h], rax
0x14003ce7f  sub     [rsi], ecx
0x14003ce81  mov     [rdi+0A50h], edx
0x14003ce87  jmp     short loc_14003CE8C
0x14003ce89  mov     edx, r8d
0x14003ce8c  mov     ecx, [rsi]
0x14003ce8e  cmp     ecx, 4
0x14003ce91  jb      loc_14003D2DC
0x14003ce97  add     qword ptr [rdi+0A48h], 4
0x14003ce9f  add     ecx, r15d
0x14003cea2  mov     [rsi], ecx
0x14003cea4  add     edx, 4
0x14003cea7  mov     [rdi+0A50h], edx
0x14003cead  lea     eax, [rdx+3]
0x14003ceb0  and     eax, r15d
0x14003ceb3  mov     r9d, eax
0x14003ceb6  mov     r8d, eax
0x14003ceb9  sub     r8d, edx
0x14003cebc  jz      short loc_14003CED6
0x14003cebe  mov     eax, r8d
0x14003cec1  add     [rdi+0A48h], rax
0x14003cec8  sub     [rsi], r8d
0x14003cecb  mov     ecx, [rsi]
0x14003cecd  mov     [rdi+0A50h], r9d
0x14003ced4  jmp     short loc_14003CED9
0x14003ced6  mov     r9d, edx
0x14003ced9  cmp     ecx, 4
0x14003cedc  jb      loc_14003D2DC
0x14003cee2  add     qword ptr [rdi+0A48h], 4
0x14003ceea  lea     eax, [rcx-4]
0x14003ceed  mov     [rsi], eax
0x14003ceef  lea     eax, [r9+4]
0x14003cef3  mov     [rdi+0A50h], eax
0x14003cef9  lea     r8, [rbp+arg_28]; unsigned int *
0x14003cefd  lea     rdx, [rbp+arg_18]; wchar_t **
0x14003cf01  mov     rcx, rdi; this
0x14003cf04  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003cf09  mov     ebx, eax
0x14003cf0b  test    eax, eax
0x14003cf0d  js      loc_14003D41A
0x14003cf13  lea     rcx, [r14+0C0h]
0x14003cf1a  mov     rax, [rcx]
0x14003cf1d  mov     r9d, dword ptr [rbp+arg_28]
0x14003cf21  xor     r8d, r8d
0x14003cf24  mov     rdx, [rbp+arg_18]
0x14003cf28  mov     rax, [rax+20h]
0x14003cf2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cf31  lea     rcx, [rdi+430h]; this
0x14003cf38  mov     rdx, [rbp+arg_18]; wchar_t *
0x14003cf3c  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x14003cf41  mov     ebx, eax
0x14003cf43  test    eax, eax
0x14003cf45  js      loc_14003D41A
0x14003cf4b  mov     r8d, [rdi+0A50h]
0x14003cf52  lea     eax, [r8+3]
0x14003cf56  and     eax, r15d
0x14003cf59  mov     edx, eax
0x14003cf5b  mov     ecx, eax
0x14003cf5d  sub     ecx, r8d
0x14003cf60  jz      short loc_14003CF75
0x14003cf62  mov     eax, ecx
0x14003cf64  add     [rdi+0A48h], rax
0x14003cf6b  sub     [rsi], ecx
0x14003cf6d  mov     [rdi+0A50h], edx
0x14003cf73  jmp     short loc_14003CF78
0x14003cf75  mov     edx, r8d
0x14003cf78  mov     r8d, [rsi]
0x14003cf7b  cmp     r8d, 4
0x14003cf7f  jb      loc_14003D2DC
0x14003cf85  mov     rax, [rdi+0A48h]
0x14003cf8c  mov     ecx, [rax]
0x14003cf8e  add     rax, 4
0x14003cf92  mov     [rdi+0A48h], rax
0x14003cf99  lea     eax, [r8-4]
0x14003cf9d  mov     [rsi], eax
0x14003cf9f  lea     eax, [rdx+4]
0x14003cfa2  mov     [rdi+0A50h], eax
0x14003cfa8  mov     [r14+260h], ecx
0x14003cfaf  lea     r8, [rbp+arg_28]; unsigned int *
0x14003cfb3  lea     rdx, [rbp+arg_18]; wchar_t **
0x14003cfb7  mov     rcx, rdi; this
0x14003cfba  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003cfbf  mov     ebx, eax
0x14003cfc1  test    eax, eax
0x14003cfc3  js      loc_14003D41A
0x14003cfc9  lea     rcx, [r14+60h]
0x14003cfcd  mov     rax, [rcx]
0x14003cfd0  mov     r9d, dword ptr [rbp+arg_28]
0x14003cfd4  xor     r8d, r8d
0x14003cfd7  mov     rdx, [rbp+arg_18]
0x14003cfdb  mov     rax, [rax+20h]
0x14003cfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cfe4  lea     r8, [rbp+arg_28]; unsigned int *
0x14003cfe8  lea     rdx, [rbp+arg_18]; wchar_t **
0x14003cfec  mov     rcx, rdi; this
0x14003cfef  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003cff4  mov     ebx, eax
0x14003cff6  test    eax, eax
0x14003cff8  js      loc_14003D41A
0x14003cffe  mov     rax, [r14]
0x14003d001  mov     r9d, dword ptr [rbp+arg_28]
0x14003d005  xor     r8d, r8d
0x14003d008  mov     rdx, [rbp+arg_18]
0x14003d00c  mov     rcx, r14
0x14003d00f  mov     rax, [rax+20h]
0x14003d013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d018  lea     r8, [rbp+arg_28]; unsigned int *
0x14003d01c  lea     rdx, [rbp+arg_18]; wchar_t **
0x14003d020  mov     rcx, rdi; this
0x14003d023  call    ?GetWStr@CFilterSink@@AEAAJPEAPEA_WPEAK@Z; CFilterSink::GetWStr(wchar_t * *,ulong *)
0x14003d028  mov     ebx, eax
0x14003d02a  test    eax, eax
0x14003d02c  js      loc_14003D41A
0x14003d032  lea     rcx, [rdi+628h]
0x14003d039  mov     rax, [rcx]
0x14003d03c  mov     r9d, dword ptr [rbp+arg_28]
0x14003d040  xor     r8d, r8d
0x14003d043  mov     rdx, [rbp+arg_18]
0x14003d047  mov     rax, [rax+20h]
0x14003d04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d050  lea     rdx, [rdi+688h]; struct _FILETIME *
0x14003d057  mov     rcx, rdi; this
0x14003d05a  call    ?GetFILETIME@CFilterSink@@AEAAJPEAU_FILETIME@@@Z; CFilterSink::GetFILETIME(_FILETIME *)
0x14003d05f  mov     ebx, eax
0x14003d061  test    eax, eax
0x14003d063  js      loc_14003D41A
0x14003d069  lea     r8, [rdi+690h]
0x14003d070  test    r8, r8
0x14003d073  jz      loc_14003D2CE
0x14003d079  mov     ecx, [rdi+0A50h]
0x14003d07f  lea     eax, [rcx+3]
0x14003d082  and     eax, r15d
0x14003d085  mov     r9d, eax
0x14003d088  mov     edx, eax
0x14003d08a  sub     edx, ecx
0x14003d08c  jz      short loc_14003D0A0
0x14003d08e  mov     eax, edx
0x14003d090  add     [rdi+0A48h], rax
0x14003d097  sub     [rsi], edx
0x14003d099  mov     [rdi+0A50h], r9d
0x14003d0a0  cmp     dword ptr [rsi], 4
0x14003d0a3  jb      loc_14003D2DC
0x14003d0a9  mov     rcx, [rdi+0A48h]
0x14003d0b0  mov     eax, [rcx]
0x14003d0b2  mov     [r8], eax
0x14003d0b5  lea     rax, [rcx+4]
0x14003d0b9  mov     [rdi+0A48h], rax
0x14003d0c0  add     [rsi], r15d
0x14003d0c3  add     dword ptr [rdi+0A50h], 4
0x14003d0ca  lea     r9, [rdi+694h]
0x14003d0d1  test    r9, r9
0x14003d0d4  jz      loc_14003D2CE
0x14003d0da  mov     ecx, [rdi+0A50h]
0x14003d0e0  lea     eax, [rcx+3]
0x14003d0e3  and     eax, r15d
0x14003d0e6  mov     r8d, eax
0x14003d0e9  mov     edx, eax
0x14003d0eb  sub     edx, ecx
0x14003d0ed  jz      short loc_14003D101
0x14003d0ef  mov     eax, edx
0x14003d0f1  add     [rdi+0A48h], rax
0x14003d0f8  sub     [rsi], edx
0x14003d0fa  mov     [rdi+0A50h], r8d
0x14003d101  cmp     dword ptr [rsi], 4
0x14003d104  jb      loc_14003D2DC
0x14003d10a  mov     rcx, [rdi+0A48h]
0x14003d111  mov     eax, [rcx]
0x14003d113  mov     [r9], eax
0x14003d116  lea     rax, [rcx+4]
0x14003d11a  mov     [rdi+0A48h], rax
0x14003d121  add     [rsi], r15d
0x14003d124  add     dword ptr [rdi+0A50h], 4
0x14003d12b  lea     r15, [rdi+698h]
0x14003d132  test    r15, r15
0x14003d135  jz      loc_14003D2CE
0x14003d13b  mov     ecx, [rdi+0A50h]
0x14003d141  lea     eax, [rcx+3]
0x14003d144  mov     r10d, 0FFFFFFFCh
0x14003d14a  and     eax, r10d
0x14003d14d  mov     r8d, eax
0x14003d150  mov     edx, eax
0x14003d152  sub     edx, ecx
0x14003d154  jz      short loc_14003D168
0x14003d156  mov     eax, edx
0x14003d158  add     [rdi+0A48h], rax
0x14003d15f  sub     [rsi], edx
0x14003d161  mov     [rdi+0A50h], r8d
0x14003d168  cmp     dword ptr [rsi], 4
0x14003d16b  jb      loc_14003D2DC
0x14003d171  mov     rcx, [rdi+0A48h]
0x14003d178  mov     eax, [rcx]
0x14003d17a  mov     [r15], eax
0x14003d17d  lea     rax, [rcx+4]
0x14003d181  mov     [rdi+0A48h], rax
0x14003d188  add     [rsi], r10d
0x14003d18b  add     dword ptr [rdi+0A50h], 4
0x14003d192  lea     r9, [rdi+69Ch]
0x14003d199  test    r9, r9
0x14003d19c  jz      loc_14003D2CE
0x14003d1a2  mov     ecx, [rdi+0A50h]
0x14003d1a8  lea     eax, [rcx+3]
0x14003d1ab  and     eax, r10d
0x14003d1ae  mov     r8d, eax
0x14003d1b1  mov     edx, eax
0x14003d1b3  sub     edx, ecx
0x14003d1b5  jz      short loc_14003D1C9
0x14003d1b7  mov     eax, edx
0x14003d1b9  add     [rdi+0A48h], rax
0x14003d1c0  sub     [rsi], edx
0x14003d1c2  mov     [rdi+0A50h], r8d
0x14003d1c9  cmp     dword ptr [rsi], 4
0x14003d1cc  jb      loc_14003D2DC
0x14003d1d2  mov     rcx, [rdi+0A48h]
0x14003d1d9  mov     eax, [rcx]
0x14003d1db  mov     [r9], eax
  ... truncated ...
```
