# Jot::CAsyncResult_IndexerQuery::CycleThreadProc_Go(void)

- ea: `0x180488380`
- end: `0x180488d91`
- name: `?CycleThreadProc_Go@CAsyncResult_IndexerQuery@Jot@@MEAAXXZ`
- size: `2577`
- prototype: `void __fastcall(Jot::CAsyncResult_IndexerQuery *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x1801efea0`
- `0x1802e2190`
- `0x1802e2251`
- `0x1802e3df4`
- `0x1802e3f10`
- `0x1802e5170`
- `0x1802e5190`
- `0x180431df8`
- `0x180487a98`
- `0x180488380`
- `0x180488ee8`
- `0x1804895d0`
- `0x180489690`
- `0x1804896e0`
- `0x18048972c`
- `0x1807d6c08`
- `0x1808e03b8`
- `0x1808e7d0c`

## import_xrefs

- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180488713`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180488b41`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180488713`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180488b41`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18048875f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18048875f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180488a88`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180488bd9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180488a88`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180488bd9`
- `ole32!CoTaskMemFree` at `0x180488523`
- `ole32!CoTaskMemFree` at `0x18048852d`
- `ole32!CoTaskMemFree` at `0x180488523`
- `ole32!CoTaskMemFree` at `0x18048852d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488963`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488b25`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488c77`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488963`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488b25`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180488c77`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18048867a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488689`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488698`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18048867a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488689`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488698`

## pseudocode

```c
void __fastcall Jot::CAsyncResult_IndexerQuery::CycleThreadProc_Go(Jot::CAsyncResult_IndexerQuery *this)
{
  uintptr_t Reserved; // r14
  unsigned __int64 v3; // rdi
  int v4; // eax
  unsigned int v5; // r8d
  __int128 *v6; // r8
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int v12; // r8d
  int v13; // eax
  unsigned int v14; // r8d
  int v15; // r13d
  int v16; // eax
  unsigned int v17; // r8d
  unsigned __int128 v18; // rax
  char *v19; // rbx
  unsigned int v20; // ecx
  unsigned __int64 v21; // r8
  int v22; // eax
  unsigned int v23; // r8d
  unsigned __int128 v24; // rax
  int v25; // r15d
  __m128i si128; // xmm6
  void *v27; // rdx
  unsigned int v28; // r8d
  void (__fastcall *v29)(Jot::CAsyncResult_IndexerQuery *, __int128 *); // rbx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  unsigned __int64 i; // r12
  unsigned __int64 v33; // rdx
  int v34; // eax
  unsigned __int64 v35; // rdx
  unsigned int v36; // r8d
  void *v37; // rax
  const struct tagPROPVARIANT *v38; // r9
  __int64 v39; // rcx
  unsigned int v40; // r12d
  struct Jot::PropertyKeyData **v41; // rax
  void (__fastcall *v42)(uintptr_t); // rax
  void (__fastcall *v43)(Jot::CAsyncResult_IndexerQuery *, __int64); // rbx
  __int64 v44; // rax
  void (__fastcall *v45)(Jot::CAsyncResult_IndexerQuery *, __int64); // rbx
  __int64 v46; // rax
  int v47; // r10d
  __int64 v48; // rdx
  void (__fastcall *v49)(Jot::CAsyncResult_IndexerQuery *, __int128 *); // rbx
  unsigned __int64 v50; // r9
  __int64 v51; // rdx
  __int128 *v52; // r8
  void (__fastcall *v53)(Jot::CAsyncResult_IndexerQuery *, __int64); // rbx
  __int64 v54; // rax
  __int128 v55; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v56; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v58; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v59; // [rsp+70h] [rbp-98h] BYREF
  __int64 v60; // [rsp+78h] [rbp-90h] BYREF
  __int64 v61; // [rsp+80h] [rbp-88h] BYREF
  uintptr_t v62; // [rsp+88h] [rbp-80h] BYREF
  __int64 v63; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v64[2]; // [rsp+98h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v66; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 v67; // [rsp+B8h] [rbp-50h]
  _QWORD v68[12]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v69; // [rsp+120h] [rbp+18h] BYREF
  __int64 v70; // [rsp+130h] [rbp+28h]
  unsigned __int64 v71; // [rsp+138h] [rbp+30h]
  __int128 v72; // [rsp+140h] [rbp+38h] BYREF
  __m128i v73; // [rsp+150h] [rbp+48h]
  _QWORD v74[100]; // [rsp+168h] [rbp+60h] BYREF

  Reserved = 0;
  if ( !*((_QWORD *)this + 50) )
  {
    v45 = *(void (__fastcall **)(Jot::CAsyncResult_IndexerQuery *, __int64))(*(_QWORD *)this + 96LL);
    Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v68, 17146963);
    v68[0] = &Jot::ErrIndex_Query_NotInitialized::`vftable';
    v46 = std::make_exception_ptr<Jot::ErrIndex_Query_NotInitialized>(&v55, v68);
    v45(this, v46);
    return;
  }
  v69 = 0;
  v70 = 0;
  v3 = 7;
  v71 = 7;
  LOWORD(v69) = 0;
  if ( (unsigned __int8)Jot::SQLHelper::Convert((char *)this + 408, &v69) )
  {
    if ( !v70 )
    {
      v53 = *(void (__fastcall **)(Jot::CAsyncResult_IndexerQuery *, __int64))(*(_QWORD *)this + 96LL);
      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v68, 17146965);
      v68[0] = &Jot::ErrIndex_QueryInvalid::`vftable';
      v54 = std::make_exception_ptr<Jot::ErrIndex_QueryInvalid>(&v55, v68);
      v53(this, v54);
      std::wstring::~wstring(&v69);
      return;
    }
    v61 = 0;
    v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 50))(
           *((_QWORD *)this + 50),
           &IID_ICommandText,
           &v61);
    if ( v4 < 0 )
      MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v4, 17146966, v5);
    v6 = &v69;
    if ( v71 > 7 )
      v6 = (__int128 *)v69;
    v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v61 + 56LL))(v61, &DBGUID_SQL, v6);
    if ( v7 < 0 )
      MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v7, 17146967, v8);
    v57 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 50) + 32LL))(
           *((_QWORD *)this + 50),
           0,
           &IID_IRowset,
           0,
           0,
           &v57);
    if ( v9 == -2147217842 )
    {
LABEL_95:
      v49 = *(void (__fastcall **)(Jot::CAsyncResult_IndexerQuery *, __int128 *))(*(_QWORD *)this + 96LL);
      v55 = 0;
      __ExceptionPtrCreate(&v55);
      v49(this, &v55);
      if ( v57 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      if ( v71 > v3 )
      {
        v30 = (_QWORD *)v69;
        if ( 2 * v71 + 2 >= 0x1000 )
        {
          v30 = *(_QWORD **)(v69 - 8);
          if ( (unsigned __int64)(v69 - (_QWORD)v30 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, Reserved);
        }
        goto LABEL_43;
      }
    }
    else
    {
      if ( v9 < 0 )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v9, 17146968, v10);
      v64[0] = 0;
      v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v57)(v57, &IID_IColumnsInfo, v64);
      if ( v11 < 0 )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v11, 17146969, v12);
      pv = 0;
      v66 = 0;
      v56 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v64[0] + 24LL))(
              v64[0],
              &v56,
              &pv,
              &v66);
      if ( v13 < 0 || !pv )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v13, 17146970, v14);
      v15 = 1;
      if ( (*((_BYTE *)pv + 24) & 1) != 0 )
        --v56;
      CoTaskMemFree(pv);
      CoTaskMemFree(v66);
      v60 = 0;
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v57)(v57, &IID_IAccessor, &v60);
      if ( v16 < 0 )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v16, 17146971, v17);
      v18 = (unsigned int)v56 * (unsigned __int128)0x58uLL;
      if ( !is_mul_ok((unsigned int)v56, 0x58u) )
        *(_QWORD *)&v18 = -1;
      v19 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v18, *((unsigned __int64 *)&v18 + 1), v17);
      v68[9] = v19;
      memset_0(v19, 0, 88 * v56);
      v20 = 0;
      v21 = v56;
      if ( v56 )
      {
        do
        {
          v50 = v20 + 1;
          v51 = 88LL * v20;
          *(_QWORD *)&v19[v51] = v50;
          *(_QWORD *)&v19[v51 + 8] = 8 * v20;
          *(_DWORD *)&v19[v51 + 56] = 1;
          *(_DWORD *)&v19[v51 + 60] = 1;
          *(_WORD *)&v19[v51 + 84] = 16396;
          ++v20;
          v21 = v56;
        }
        while ( v50 < v56 );
      }
      v63 = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, char *, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v60 + 32LL))(
              v60,
              2,
              v21,
              v19,
              0,
              &v63,
              0);
      if ( v22 < 0 )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v22, 17146972, v23);
      v24 = (unsigned int)v56 * (unsigned __int128)8uLL;
      if ( !is_mul_ok((unsigned int)v56, 8u) )
        *(_QWORD *)&v24 = -1;
      v3 = (unsigned __int64)Mso::Memory::Throw::AllocateEx(
                               (Mso::Memory::Throw *)v24,
                               *((unsigned __int64 *)&v24 + 1),
                               v23);
      v68[10] = v3;
      v25 = 0;
      *(_QWORD *)&v55 = 0;
      *((_QWORD *)&v55 + 1) = 0x8000000000000000uLL;
      if ( *((int *)this + 108) > 0 )
        goto LABEL_93;
LABEL_23:
      v15 = 31;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      Reserved = 0;
      do
      {
        v59 = 0;
        v58 = v74;
        if ( *((_BYTE *)this + 177) )
          break;
        v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned __int64 *, _QWORD **))(*(_QWORD *)v57 + 40LL))(
                v57,
                0,
                0,
                100,
                &v59,
                &v58);
        if ( v25 < 0 )
          break;
        for ( i = 0; ; ++i )
        {
          v67 = i;
          v33 = v59;
          if ( i >= v59 )
            break;
          if ( *((_BYTE *)this + 177) )
            goto LABEL_59;
          v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64))(*(_QWORD *)v57 + 32LL))(
                  v57,
                  v74[i],
                  v63,
                  v3);
          if ( v34 < 0 )
          {
            v25 = v34;
LABEL_59:
            v33 = v59;
            break;
          }
          if ( **(_WORD **)(v3 + 8) == 31 )
          {
            v37 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xA8, v35, v36);
            v68[11] = v37;
            if ( v37 )
              Reserved = Jot::CIndexerItemUrl::CIndexerItemUrl(v37, *(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL));
            if ( Reserved )
              (**(void (__fastcall ***)(uintptr_t))Reserved)(Reserved);
            v64[1] = Reserved;
            if ( Jot::CIndexerItemUrl::IsValidUrl((Jot::CIndexerItemUrl *)Reserved) )
            {
              v39 = *((_QWORD *)this + 51);
              if ( !v39
                || (*(unsigned __int8 (__fastcall **)(__int64, uintptr_t))(*(_QWORD *)v39 + 64LL))(v39, Reserved) )
              {
                v40 = 0;
                if ( *((int *)this + 108) > 0 )
                {
                  v41 = (struct Jot::PropertyKeyData **)(v3 + 16);
                  v62 = v3 + 16;
                  do
                  {
                    if ( v40 < DWORD2(v55) )
                    {
                      Jot::FillIndexerItemColumn(
                        (Jot *)Reserved,
                        (struct Jot::CIndexerItemUrl *)(v55 + 40LL * v40),
                        *v41,
                        v38);
                      if ( v40 >= *((_DWORD *)this + 108) )
                      {
                        CrashWithRecovery(0x1E892496u, 0);
                        while ( 1 )
                        {
                          Jot::IndexedPropertyEditor::GetPropertyKeyDataForProperty(*(unsigned int *)(*((_QWORD *)this + 53) + 4LL * (unsigned int)Reserved));
                          Reserved = (unsigned int)(v15 + Reserved);
                          if ( (int)Reserved >= *((_DWORD *)this + 108) )
                            goto LABEL_23;
LABEL_93:
                          Ofc::CArrayImpl::EnsureCapacityForOneElem(
                            (Ofc::CArrayImpl *)&v55,
                            0x28u,
                            (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Jot::PropertyKeyData,1>::Do);
                          v47 = DWORD2(v55);
                          v48 = v55 + 40LL * DWORD2(v55);
                          *(_OWORD *)v48 = 0;
                          *(_OWORD *)(v48 + 16) = 0;
                          *(_QWORD *)(v48 + 32) = 0;
                          DWORD2(v55) = v15 + v47;
                          if ( (unsigned int)Reserved >= *((_DWORD *)this + 108) )
                          {
                            CrashWithRecovery(0x1E892496u, 0);
                            goto LABEL_95;
                          }
                        }
                      }
                    }
                    else
                    {
                      CrashWithRecovery(0x1E892496u, 0);
                    }
                    if ( *(_DWORD *)(*((_QWORD *)this + 53) + 4LL * v40) == 107 )
                    {
                      v72 = 0;
                      v73 = si128;
                      LOWORD(v72) = 0;
                      (*(void (__fastcall **)(uintptr_t, __int64, __int128 *))(*(_QWORD *)Reserved + 176LL))(
                        Reserved,
                        107,
                        &v72);
                      v52 = &v72;
                      if ( v73.m128i_i64[1] > 7uLL )
                        v52 = (__int128 *)v72;
                      (*(void (__fastcall **)(uintptr_t, __int64, __int128 *))(*(_QWORD *)Reserved + 208LL))(
                        Reserved,
                        137,
                        v52);
                      std::wstring::~wstring(&v72);
                    }
                    ++v40;
                    v41 = (struct Jot::PropertyKeyData **)(v62 + 8);
                    v62 += 8LL;
                  }
                  while ( (signed int)v40 < *((_DWORD *)this + 108) );
                }
                if ( Reserved )
                  (**(void (__fastcall ***)(uintptr_t))Reserved)(Reserved);
                v62 = Reserved;
                MsoCF::CObjArray<MsoCF::CIPtr<Jot::CFindHitBase,Jot::CFindHitBase>>::Append((char *)this + 440, &v62);
                if ( Reserved )
                  (*(void (__fastcall **)(uintptr_t))(*(_QWORD *)Reserved + 8LL))(Reserved);
                i = v67;
              }
            }
            if ( Reserved )
            {
              v42 = *(void (__fastcall **)(uintptr_t))(*(_QWORD *)Reserved + 8LL);
              if ( (char *)v42 == (char *)MsoCF::IThreadSafeBaseImpl<Jot::ISearchHit>::Release )
                MsoCF::IThreadSafeBaseImpl<Jot::ISearchHit>::Release(Reserved);
              else
                v42(Reserved);
            }
            Reserved = 0;
          }
        }
        if ( v33 )
          (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v57 + 48LL))(
            v57,
            v33,
            v74,
            0,
            0,
            0);
        if ( v25 == 265926 || v25 == 265920 || v25 == 265942 )
        {
          v25 = 0;
          break;
        }
      }
      while ( v25 >= 0 );
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v60 + 48LL))(v60, v63, 0);
      if ( v25 < 0 )
        MsoCF::ThrowHRESULTTag((MsoCF *)(unsigned int)v25, 17146973, v28);
      if ( (_QWORD)v55 )
        Mso::Memory::Free((Mso::Memory *)v55, v27);
      if ( v3 )
        Mso::Memory::Free((Mso::Memory *)v3, v27);
      if ( v19 )
        Mso::Memory::Free((Mso::Memory *)v19, v27);
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      if ( v64[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v64[0] + 16LL))(v64[0]);
      if ( v57 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v29 = *(void (__fastcall **)(Jot::CAsyncResult_IndexerQuery *, __int128 *))(*(_QWORD *)this + 96LL);
      v55 = 0;
      __ExceptionPtrCreate(&v55);
      v29(this, &v55);
      if ( v71 > 7 )
      {
        v30 = (_QWORD *)v69;
        v31 = v69;
        if ( 2 * v71 + 2 >= 0x1000 )
          goto LABEL_42;
        goto LABEL_43;
      }
    }
  }
  else
  {
    v43 = *(void (__fastcall **)(Jot::CAsyncResult_IndexerQuery *, __int64))(*(_QWORD *)this + 96LL);
    Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v68, 17146964);
    v68[0] = &Jot::ErrIndex_QueryInvalid::`vftable';
    v44 = std::make_exception_ptr<Jot::ErrIndex_QueryInvalid>(&v55, v68);
    v43(this, v44);
    if ( v71 > 7 )
    {
      v30 = (_QWORD *)v69;
      v31 = v69;
      if ( 2 * v71 + 2 >= 0x1000 )
      {
LABEL_42:
        v30 = (_QWORD *)*(v30 - 1);
        if ( (unsigned __int64)(v31 - (_QWORD)v30 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
LABEL_43:
      free(v30);
    }
  }
}

```

## disassembly

```asm
0x180488380  mov     rax, rsp
0x180488383  mov     [rax+10h], rbx
0x180488387  mov     [rax+18h], rsi
0x18048838b  mov     [rax+20h], rdi
0x18048838f  push    rbp
0x180488390  push    r12
0x180488392  push    r13
0x180488394  push    r14
0x180488396  push    r15
0x180488398  lea     rbp, [rax-3C8h]
0x18048839f  sub     rsp, 4A0h
0x1804883a6  movaps  xmmword ptr [rax-38h], xmm6
0x1804883aa  mov     rax, cs:__security_cookie
0x1804883b1  xor     rax, rsp
0x1804883b4  mov     [rbp+3C0h+var_40], rax
0x1804883bb  mov     rsi, rcx
0x1804883be  xor     r14d, r14d
0x1804883c1  cmp     [rcx+190h], r14
0x1804883c8  jz      loc_180488A8F
0x1804883ce  xorps   xmm0, xmm0
0x1804883d1  movups  [rbp+3C0h+var_3A8], xmm0
0x1804883d5  mov     [rbp+3C0h+var_398], r14
0x1804883d9  lea     edi, [r14+7]
0x1804883dd  mov     [rbp+3C0h+var_390], rdi
0x1804883e1  mov     word ptr [rbp+3C0h+var_3A8], r14w
0x1804883e6  add     rcx, 198h
0x1804883ed  lea     rdx, [rbp+3C0h+var_3A8]
0x1804883f1  call    ?Convert@SQLHelper@Jot@@YA_NAEBUIndexerQueryParams@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Jot::SQLHelper::Convert(Jot::IndexerQueryParams const &,std::wstring &)
0x1804883f6  test    al, al
0x1804883f8  jz      loc_180488A09
0x1804883fe  cmp     [rbp+3C0h+var_398], r14
0x180488402  jz      loc_180488D45
0x180488408  mov     [rsp+4C0h+var_448], r14
0x18048840d  mov     rcx, [rsi+190h]
0x180488414  mov     rax, [rcx]
0x180488417  lea     r8, [rsp+4C0h+var_448]
0x18048841c  lea     rdx, IID_ICommandText
0x180488423  mov     rax, [rax]
0x180488426  call    cs:__guard_dispatch_icall_fptr
0x18048842c  test    eax, eax
0x18048842e  js      loc_18048879A
0x180488434  mov     rcx, [rsp+4C0h+var_448]
0x180488439  mov     rax, [rcx]
0x18048843c  lea     r8, [rbp+3C0h+var_3A8]
0x180488440  cmp     [rbp+3C0h+var_390], rdi
0x180488444  cmova   r8, qword ptr [rbp+3C0h+var_3A8]
0x180488449  lea     rdx, DBGUID_SQL
0x180488450  mov     rax, [rax+38h]
0x180488454  call    cs:__guard_dispatch_icall_fptr
0x18048845a  test    eax, eax
0x18048845c  js      loc_1804887A7
0x180488462  mov     [rsp+4C0h+var_468], r14
0x180488467  mov     rcx, [rsi+190h]
0x18048846e  mov     rax, [rcx]
0x180488471  lea     rdx, [rsp+4C0h+var_468]
0x180488476  mov     [rsp+4C0h+var_498], rdx
0x18048847b  mov     [rsp+4C0h+Reserved], r14
0x180488480  xor     r9d, r9d
0x180488483  lea     r8, IID_IRowset
0x18048848a  xor     edx, edx
0x18048848c  mov     rax, [rax+20h]
0x180488490  call    cs:__guard_dispatch_icall_fptr
0x180488496  cmp     eax, 80040E4Eh
0x18048849b  jz      loc_180488B2C
0x1804884a1  test    eax, eax
0x1804884a3  js      loc_1804887C9
0x1804884a9  mov     [rbp+3C0h+var_430], r14
0x1804884ad  mov     rcx, [rsp+4C0h+var_468]
0x1804884b2  mov     rax, [rcx]
0x1804884b5  lea     r8, [rbp+3C0h+var_430]
0x1804884b9  lea     rdx, IID_IColumnsInfo
0x1804884c0  mov     rax, [rax]
0x1804884c3  call    cs:__guard_dispatch_icall_fptr
0x1804884c9  test    eax, eax
0x1804884cb  js      loc_1804887D9
0x1804884d1  mov     [rbp+3C0h+pv], r14
0x1804884d5  mov     [rbp+3C0h+var_418], r14
0x1804884d9  mov     [rsp+4C0h+var_470], r14
0x1804884de  mov     rcx, [rbp+3C0h+var_430]
0x1804884e2  mov     rax, [rcx]
0x1804884e5  lea     r9, [rbp+3C0h+var_418]
0x1804884e9  lea     r8, [rbp+3C0h+pv]
0x1804884ed  lea     rdx, [rsp+4C0h+var_470]
0x1804884f2  mov     rax, [rax+18h]
0x1804884f6  call    cs:__guard_dispatch_icall_fptr
0x1804884fc  test    eax, eax
0x1804884fe  js      loc_1804887B9
0x180488504  mov     rcx, [rbp+3C0h+pv]; pv
0x180488508  test    rcx, rcx
0x18048850b  jz      loc_1804887B9
0x180488511  mov     eax, [rcx+18h]
0x180488514  lea     r13d, [r14+1]
0x180488518  and     eax, r13d
0x18048851b  test    al, al
0x18048851d  jnz     loc_180488CA5
0x180488523  call    cs:__imp_CoTaskMemFree
0x180488529  mov     rcx, [rbp+3C0h+var_418]; pv
0x18048852d  call    cs:__imp_CoTaskMemFree
0x180488533  mov     [rsp+4C0h+var_450], r14
0x180488538  mov     rcx, [rsp+4C0h+var_468]
0x18048853d  mov     rax, [rcx]
0x180488540  lea     r8, [rsp+4C0h+var_450]
0x180488545  lea     rdx, IID_IAccessor
0x18048854c  mov     rax, [rax]
0x18048854f  call    cs:__guard_dispatch_icall_fptr
0x180488555  test    eax, eax
0x180488557  js      loc_1804887E9
0x18048855d  mov     ecx, dword ptr [rsp+4C0h+var_470]
0x180488561  mov     eax, 58h ; 'X'
0x180488566  mul     rcx
0x180488569  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180488570  cmovb   rax, rdi
0x180488574  mov     rcx, rax; this
0x180488577  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18048857c  mov     rbx, rax
0x18048857f  mov     [rbp+3C0h+var_3C0], rax
0x180488583  imul    r8, [rsp+4C0h+var_470], 58h ; 'X'; Size
0x180488589  xor     edx, edx; Val
0x18048858b  mov     rcx, rax; void *
0x18048858e  call    memset_0
0x180488593  mov     ecx, r14d
0x180488596  mov     r8, [rsp+4C0h+var_470]
0x18048859b  test    r8, r8
0x18048859e  jnz     loc_180488BE0
0x1804885a4  mov     [rbp+3C0h+var_438], r14
0x1804885a8  mov     rcx, [rsp+4C0h+var_450]
0x1804885ad  mov     rax, [rcx]
0x1804885b0  mov     [rsp+4C0h+var_490], r14
0x1804885b5  lea     rdx, [rbp+3C0h+var_438]
0x1804885b9  mov     [rsp+4C0h+var_498], rdx
0x1804885be  mov     [rsp+4C0h+Reserved], r14
0x1804885c3  mov     r9, rbx
0x1804885c6  mov     edx, 2
0x1804885cb  mov     rax, [rax+20h]
0x1804885cf  call    cs:__guard_dispatch_icall_fptr
0x1804885d5  test    eax, eax
0x1804885d7  js      loc_1804887F9
0x1804885dd  mov     ecx, dword ptr [rsp+4C0h+var_470]
0x1804885e1  mov     eax, 8
0x1804885e6  mul     rcx
0x1804885e9  cmovb   rax, rdi
0x1804885ed  mov     rcx, rax; this
0x1804885f0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804885f5  mov     rdi, rax
0x1804885f8  mov     [rbp+3C0h+var_3B8], rax
0x1804885fc  mov     r15d, r14d
0x1804885ff  mov     qword ptr [rsp+4C0h+var_488+8], r14
0x180488604  mov     dword ptr [rsp+4C0h+var_478], r14d
0x180488609  mov     dword ptr [rsp+4C0h+var_478+4], 80000000h
0x180488611  cmp     dword ptr [rsi+1B0h], 0
0x180488618  jg      loc_180488AD1
0x18048861e  mov     r13d, 1Fh
0x180488624  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18048862c  xor     r14d, r14d
0x18048862f  mov     [rsp+4C0h+var_458], r14
0x180488634  lea     rax, [rbp+3C0h+var_360]
0x180488638  mov     [rsp+4C0h+var_460], rax
0x18048863d  mov     al, [rsi+0B1h]
0x180488643  test    al, al
0x180488645  jz      loc_180488817
0x18048864b  mov     rcx, [rsp+4C0h+var_450]
0x180488650  mov     rax, [rcx]
0x180488653  xor     r8d, r8d
0x180488656  mov     rdx, [rbp+3C0h+var_438]
0x18048865a  mov     rax, [rax+30h]
0x18048865e  call    cs:__guard_dispatch_icall_fptr
0x180488664  test    r15d, r15d
0x180488667  js      loc_180488809
0x18048866d  mov     r12, qword ptr [rsp+4C0h+var_488+8]
0x180488672  test    r12, r12
0x180488675  jz      short loc_180488681
0x180488677  mov     rcx, r12
0x18048867a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180488680  nop
0x180488681  test    rdi, rdi
0x180488684  jz      short loc_180488690
0x180488686  mov     rcx, rdi
0x180488689  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18048868f  nop
0x180488690  test    rbx, rbx
0x180488693  jz      short loc_1804886A0
0x180488695  mov     rcx, rbx
0x180488698  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18048869e  nop
0x18048869f  nop
0x1804886a0  mov     rcx, [rsp+4C0h+var_450]
0x1804886a5  test    rcx, rcx
0x1804886a8  jz      short loc_1804886B8
0x1804886aa  mov     rax, [rcx]
0x1804886ad  mov     rax, [rax+10h]
0x1804886b1  call    cs:__guard_dispatch_icall_fptr
0x1804886b7  nop
0x1804886b8  mov     rcx, [rbp+3C0h+var_430]
0x1804886bc  test    rcx, rcx
0x1804886bf  jz      short loc_1804886CF
0x1804886c1  mov     rax, [rcx]
0x1804886c4  mov     rax, [rax+10h]
0x1804886c8  call    cs:__guard_dispatch_icall_fptr
0x1804886ce  nop
0x1804886cf  mov     rcx, [rsp+4C0h+var_468]
0x1804886d4  test    rcx, rcx
0x1804886d7  jz      short loc_1804886E7
0x1804886d9  mov     rax, [rcx]
0x1804886dc  mov     rax, [rax+10h]
0x1804886e0  call    cs:__guard_dispatch_icall_fptr
0x1804886e6  nop
0x1804886e7  mov     rcx, [rsp+4C0h+var_448]
0x1804886ec  test    rcx, rcx
0x1804886ef  jz      short loc_1804886FE
0x1804886f1  mov     rax, [rcx]
0x1804886f4  mov     rax, [rax+10h]
0x1804886f8  call    cs:__guard_dispatch_icall_fptr
0x1804886fe  mov     rax, [rsi]
0x180488701  mov     rbx, [rax+60h]
0x180488705  xorps   xmm0, xmm0
0x180488708  movdqu  [rsp+4C0h+var_488+8], xmm0
0x18048870e  lea     rcx, [rsp+4C0h+var_488+8]
0x180488713  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180488719  lea     rdx, [rsp+4C0h+var_488+8]
0x18048871e  mov     rcx, rsi
0x180488721  mov     rax, rbx
0x180488724  call    cs:__guard_dispatch_icall_fptr
0x18048872a  mov     rax, [rbp+3C0h+var_390]
0x18048872e  cmp     rax, 7
0x180488732  jbe     short loc_180488765
0x180488734  mov     rcx, qword ptr [rbp+3C0h+var_3A8]
0x180488738  mov     rdx, rcx
0x18048873b  lea     rax, ds:2[rax*2]
0x180488743  cmp     rax, 1000h
0x180488749  jb      short loc_18048875F
0x18048874b  mov     rcx, [rcx-8]; Block
0x18048874f  sub     rdx, rcx
0x180488752  lea     rax, [rdx-8]
0x180488756  cmp     rax, r13
0x180488759  ja      loc_180488A79
0x18048875f  call    cs:__imp_free
0x180488765  mov     rcx, [rbp+3C0h+var_40]
0x18048876c  xor     rcx, rsp; StackCookie
0x18048876f  call    __security_check_cookie
0x180488774  lea     r11, [rsp+4C0h+var_20]
0x18048877c  mov     rbx, [r11+38h]
0x180488780  mov     rsi, [r11+40h]
0x180488784  mov     rdi, [r11+48h]
0x180488788  movaps  xmm6, xmmword ptr [r11-10h]
0x18048878d  mov     rsp, r11
0x180488790  pop     r15
0x180488792  pop     r14
0x180488794  pop     r13
0x180488796  pop     r12
0x180488798  pop     rbp
0x180488799  retn
0x18048879a  mov     edx, 105A456h; int
0x18048879f  mov     ecx, eax; this
0x1804887a1  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887a7  mov     edx, 105A457h; int
0x1804887ac  mov     ecx, eax; this
0x1804887ae  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887b4  jmp     short loc_1804887B8
0x1804887b8  nop
0x1804887b9  mov     edx, 105A45Ah; int
0x1804887be  mov     ecx, eax; this
0x1804887c0  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887c6  jmp     short $+2
0x1804887c8  nop
0x1804887c9  mov     edx, 105A458h; int
0x1804887ce  mov     ecx, eax; this
0x1804887d0  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887d6  jmp     short $+2
0x1804887d8  nop
0x1804887d9  mov     edx, 105A459h; int
0x1804887de  mov     ecx, eax; this
0x1804887e0  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887e6  jmp     short $+2
0x1804887e8  nop
0x1804887e9  mov     edx, 105A45Bh; int
0x1804887ee  mov     ecx, eax; this
0x1804887f0  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x1804887f6  jmp     short $+2
0x1804887f8  nop
0x1804887f9  mov     edx, 105A45Ch; int
0x1804887fe  mov     ecx, eax; this
0x180488800  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x180488806  jmp     short $+2
0x180488808  nop
0x180488809  mov     edx, 105A45Dh; int
0x18048880e  mov     ecx, r15d; this
0x180488811  call    ?ThrowHRESULTTag@MsoCF@@YAXJK@Z; MsoCF::ThrowHRESULTTag(long,ulong)
0x180488817  mov     rcx, [rsp+4C0h+var_468]
0x18048881c  mov     rax, [rcx]
0x18048881f  lea     rdx, [rsp+4C0h+var_460]
0x180488824  mov     [rsp+4C0h+var_498], rdx
0x180488829  lea     rdx, [rsp+4C0h+var_458]
0x18048882e  mov     [rsp+4C0h+Reserved], rdx
0x180488833  mov     r9d, 64h ; 'd'
0x180488839  xor     r8d, r8d
0x18048883c  xor     edx, edx
0x18048883e  mov     rax, [rax+28h]
0x180488842  call    cs:__guard_dispatch_icall_fptr
0x180488848  mov     r15d, eax
0x18048884b  test    eax, eax
  ... truncated ...
```
