# CaProgressiveCompressor::EndSurfaceUpdate(void)

- ea: `0x18006ec20`
- end: `0x18006f338`
- name: `?EndSurfaceUpdate@CaProgressiveCompressor@@UEAAJXZ`
- size: `1816`
- prototype: `__int64 __fastcall(CaProgressiveCompressor *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000116c`
- `0x1800097b0`
- `0x180009fe0`
- `0x18000ce04`
- `0x18000ce34`
- `0x1800458d8`
- `0x18004f52c`
- `0x180052c2c`
- `0x18006ec20`
- `0x18007e9e0`
- `0x18016cf94`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ef64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ef64`

## string_xrefs

- `0x18006ec83`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18006ed3d`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18006ee73`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18006ec96`: `CaProgressiveCompressor::EndSurfaceUpdate: BeginUpdate hasn't been called`
- `0x18006ed49`: `CaProgressiveCompressor::EndSurfaceUpdate: wrong state to be in, expected:%s, actual:%s`
- `0x18006ec68`: `EndSurfaceUpdate`
- `0x18006ed31`: `EndSurfaceUpdate`
- `0x18006ee59`: `EndSurfaceUpdate`
- `0x18006f0cb`: `End Surface Update for surface# 0x%I64x (%dx%d), Mapping data`

## pseudocode

```c
__int64 __fastcall CaProgressiveCompressor::EndSurfaceUpdate(CaProgressiveCompressor *this, __int64 a2, int a3, int a4)
{
  char *v4; // r15
  __int64 v5; // rax
  __int64 v8; // rax
  CaProgressiveSurfaceContext *v9; // rcx
  bool v10; // zf
  __int64 (__fastcall ***v11)(_QWORD, GUID *, const char **); // rcx
  int v12; // edi
  const char *v13; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rcx
  const char *v18; // rcx
  const char *v19; // rcx
  void (*v20)(void); // rax
  _DWORD *v21; // r14
  _DWORD *v22; // rsi
  RTL_SRWLOCK *v23; // rcx
  int v24; // eax
  const char *v25; // rcx
  const char *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // r8d
  int v30; // r9d
  const char *v31; // rcx
  const char *v32; // rcx
  __int64 v33; // r8
  unsigned int v34; // r12d
  __int64 v35; // rax
  __int64 v36; // r14
  const char *v37; // rsi
  __int64 v38; // rcx
  const char *v39; // rcx
  __int64 v40; // rax
  const char *v41; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  const char *v43; // [rsp+70h] [rbp-90h] BYREF
  struct CacNx::ISurfaceEncoder *v44; // [rsp+78h] [rbp-88h] BYREF
  const char *v45; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-78h] BYREF
  const char *v47; // [rsp+90h] [rbp-70h] BYREF
  const char *v48; // [rsp+98h] [rbp-68h] BYREF
  int v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+B0h] [rbp-50h]
  int v52; // [rsp+B4h] [rbp-4Ch]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+C0h] [rbp-40h]
  int v55; // [rsp+C4h] [rbp-3Ch]
  __int64 v56; // [rsp+C8h] [rbp-38h]
  __int64 v57; // [rsp+D0h] [rbp-30h]
  int v58; // [rsp+D8h] [rbp-28h]
  int v59; // [rsp+DCh] [rbp-24h]
  __int128 v60; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v61; // [rsp+F0h] [rbp-10h]
  __int128 v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+110h] [rbp+10h]
  _QWORD v64[2]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v65; // [rsp+128h] [rbp+28h] BYREF
  __int128 v66; // [rsp+138h] [rbp+38h]
  __int128 v67; // [rsp+148h] [rbp+48h]

  v4 = (char *)this + 88;
  v5 = *((_QWORD *)this + 11);
  if ( !v5 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v42 = 0x80004005000001DDuLL;
      v43 = "EndSurfaceUpdate";
      v45 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
      v44 = (struct CacNx::ISurfaceEncoder *)"CaProgressiveCompressor::EndSurfaceUpdate: BeginUpdate hasn't been called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1802A1B29,
        a3,
        a4,
        (__int64)&v44,
        (__int64)&v42 + 4,
        (__int64)&v45,
        (__int64)&v42,
        (__int64)&v43);
    }
    return 0;
  }
  if ( *(_DWORD *)(v5 + 56) == 2 )
  {
    *(_DWORD *)(v5 + 56) = 10;
    v9 = *(CaProgressiveSurfaceContext **)v4;
    v44 = 0;
    CaProgressiveSurfaceContext::GetSurfaceEncoder(v9, &v44);
    v10 = *((_DWORD *)this + 15) == 2;
    v46 = 0;
    if ( !v10 )
    {
      v41 = 0;
      (**(void (__fastcall ***)(struct CacNx::ISurfaceEncoder *, GUID *, const char **))v44)(
        v44,
        &IID_ISurfaceEncoderCpu,
        &v41);
      v27 = *((_QWORD *)this + 32);
      v28 = *(_QWORD *)v4;
      v63 = 0;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v27 + 56LL))(
              v27,
              *(_QWORD *)(v28 + 88),
              &v65);
      if ( v12 < 0 )
      {
        v31 = v41;
        if ( !v41 )
          goto LABEL_61;
        v41 = 0;
        v20 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
LABEL_22:
        v20();
LABEL_61:
        TCntPtr<IRdpVCMgr>::SafeRelease(&v44);
        return (unsigned int)v12;
      }
      v64[1] = *((_QWORD *)&v65 + 1);
      v64[0] = 0;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v42 = *((_QWORD *)&v65 + 1);
        v32 = *(const char **)(*(_QWORD *)v4 + 88LL);
        v47 = "End Surface Update for surface# 0x%I64x (%dx%d), Mapping data";
        v48 = v32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v32,
          (unsigned int)word_1802A1772,
          v29,
          v30,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v42,
          (__int64)&v42 + 4);
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, __int64, __int128 *))(**((_QWORD **)this + 32) + 64LL))(
              *((_QWORD *)this + 32),
              *(_QWORD *)(*(_QWORD *)v4 + 88LL),
              v64,
              2,
              &v60);
      if ( v12 < 0 )
      {
        v19 = v41;
        if ( !v41 )
          goto LABEL_61;
        v41 = 0;
        goto LABEL_21;
      }
      v21 = (_DWORD *)((char *)this + 128);
      v56 = *((_QWORD *)this + 15);
      v22 = (_DWORD *)((char *)this + 152);
      v33 = *((unsigned int *)this + 38);
      v54 = *((_DWORD *)this + 32);
      v58 = DWORD2(v66);
      v53 = *((_QWORD *)&v61 + 1);
      v50 = *((_QWORD *)&v60 + 1);
      v51 = v61;
      v52 = 0;
      v55 = 0;
      v59 = 0;
      v57 = 0;
      if ( (_DWORD)v33 )
        v12 = (*(__int64 (__fastcall **)(const char *, __int64 *, __int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v41 + 72LL))(
                v41,
                &v50,
                v33,
                *((_QWORD *)this + 18),
                *((_QWORD *)this + 25),
                &v46);
      (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 32) + 72LL))(*((_QWORD *)this + 32), &v60);
      v26 = v41;
      if ( !v41 )
      {
LABEL_50:
        if ( v12 >= 0 )
        {
          v34 = 0;
          if ( v46 )
          {
            do
            {
              v35 = *((_QWORD *)this + 20);
              v43 = 0;
              v12 = (*(__int64 (__fastcall **)(char *, _QWORD, const char **))(v35 + 48))((char *)this + 160, v34, &v43);
              v36 = *(_QWORD *)(*((_QWORD *)this + 25) + 8LL * v34);
              if ( v36 )
              {
                v37 = v43;
                if ( v36 != *((_QWORD *)v43 + 7) )
                {
                  TCntPtr<IRdpVCMgr>::SafeRelease(v43 + 56);
                  *((_QWORD *)v37 + 7) = v36;
                  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v37 + 56);
                }
              }
              v38 = *(_QWORD *)(*((_QWORD *)this + 25) + 8LL * v34);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              *(_QWORD *)(*((_QWORD *)this + 25) + 8LL * v34) = 0;
              v39 = v43;
              if ( v43 )
              {
                v43 = 0;
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v39 + 5) + 16LL))(*((_QWORD *)v39 + 5));
              }
              ++v34;
            }
            while ( v34 < v46 );
            v22 = (_DWORD *)((char *)this + 152);
            v21 = (_DWORD *)((char *)this + 128);
            v4 = (char *)this + 88;
          }
          *v22 = 0;
          v40 = *((_QWORD *)this + 20);
          *v21 = 0;
          (*(void (__fastcall **)(char *))(v40 + 24))((char *)this + 160);
          *(_DWORD *)(*((_QWORD *)this + 11) + 56LL) = 3;
        }
        TCntPtr<CaProgressiveSurfaceContext>::operator=(v4, 0);
        goto LABEL_61;
      }
      v41 = 0;
LABEL_49:
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v26 + 16LL))(v26);
      goto LABEL_50;
    }
    v43 = 0;
    (**(void (__fastcall ***)(struct CacNx::ISurfaceEncoder *, GUID *, const char **))v44)(
      v44,
      &IID_ISurfaceEncoderX11,
      &v43);
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 32);
    v45 = 0;
    v41 = 0;
    v12 = (**v11)(v11, &IID_ICaGfxSourceProgressive, &v41);
    if ( v12 >= 0 )
    {
      v13 = v41;
      if ( !v41 )
      {
LABEL_24:
        v21 = (_DWORD *)((char *)this + 128);
        *(_QWORD *)&v65 = v45;
        v22 = (_DWORD *)((char *)this + 152);
        v66 = *((unsigned __int64 *)this + 15);
        *((_QWORD *)&v65 + 1) = *((unsigned int *)this + 32);
        if ( *((_DWORD *)this + 38) )
        {
          v23 = (RTL_SRWLOCK *)*((_QWORD *)this + 10);
          v48 = (const char *)v23;
          v49 = 0;
          if ( v23 )
          {
            AcquireSRWLockExclusive(v23);
            v49 = 1;
          }
          v24 = (*(__int64 (__fastcall **)(const char *, __int128 *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v43 + 72LL))(
                  v43,
                  &v65,
                  (unsigned int)*v22,
                  *((_QWORD *)this + 18),
                  *((_QWORD *)this + 25),
                  &v46);
          v12 = v24;
          if ( v24 < 0 && v41 )
            CaProgressiveCompressor::handleCodecError(this, v24);
          CAutoLockExclusive::~CAutoLockExclusive((CAutoLockExclusive *)&v48);
          v13 = v41;
        }
        if ( v13 )
        {
          v41 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v25 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v26 = v43;
        if ( !v43 )
          goto LABEL_50;
        v43 = 0;
        goto LABEL_49;
      }
      v12 = (*(__int64 (__fastcall **)(const char *, _QWORD, const char **))(*(_QWORD *)v41 + 48LL))(
              v41,
              *(unsigned int *)(*(_QWORD *)v4 + 88LL),
              &v45);
      if ( v12 < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v64[0] = "EndSurfaceUpdate";
          v42 = 0x20280004005LL;
          v47 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
          v48 = "Could not obtain encoding input surface";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v14,
            (unsigned int)byte_1802A0EBB,
            v15,
            v16,
            (__int64)&v48,
            (__int64)&v42,
            (__int64)&v47,
            (__int64)&v42 + 4,
            (__int64)v64);
        }
        v17 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v18 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = v43;
        if ( !v43 )
          goto LABEL_61;
        v43 = 0;
LABEL_21:
        v20 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
        goto LABEL_22;
      }
    }
    v13 = v41;
    goto LABEL_24;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v8 = *(int *)(*(_QWORD *)v4 + 56LL);
    v42 = 0x1E280004005LL;
    v43 = (const char *)off_1801A4A00[v8];
    v45 = (const char *)L"PCS_SURFACE_UPDATE";
    v44 = (struct CacNx::ISurfaceEncoder *)"EndSurfaceUpdate";
    v41 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
    v64[0] = "CaProgressiveCompressor::EndSurfaceUpdate: wrong state to be in, expected:%s, actual:%s";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (unsigned int)off_1801A4A00,
      (unsigned int)&word_1802A110E,
      a3,
      a4,
      (__int64)v64,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v42 + 4,
      (__int64)&v44,
      (__int64)&v45,
      (__int64)&v43);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18006ec20  push    rbp
0x18006ec22  push    rbx
0x18006ec23  push    rsi
0x18006ec24  push    rdi
0x18006ec25  push    r12
0x18006ec27  push    r13
0x18006ec29  push    r14
0x18006ec2b  push    r15
0x18006ec2d  lea     rbp, [rsp-68h]
0x18006ec32  sub     rsp, 168h
0x18006ec39  mov     rax, cs:__security_cookie
0x18006ec40  xor     rax, rsp
0x18006ec43  mov     [rbp+0A0h+var_48], rax
0x18006ec47  lea     r15, [rcx+58h]
0x18006ec4b  xor     r13d, r13d
0x18006ec4e  mov     rax, [r15]
0x18006ec51  mov     rbx, rcx
0x18006ec54  test    rax, rax
0x18006ec57  jnz     loc_18006ECDF
0x18006ec5d  mov     eax, cs:CallbackContext
0x18006ec63  cmp     eax, 2
0x18006ec66  jbe     short loc_18006ECD8
0x18006ec68  lea     rax, aEndsurfaceupda_0; "EndSurfaceUpdate"
0x18006ec6f  mov     dword ptr [rsp+1A0h+var_138], 1DDh
0x18006ec77  mov     [rsp+1A0h+var_130], rax
0x18006ec7c  lea     rdx, byte_1802A1B29
0x18006ec83  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18006ec8a  mov     dword ptr [rsp+1A0h+var_138+4], 80004005h
0x18006ec92  mov     [rbp+0A0h+var_120], rax
0x18006ec96  lea     rax, aCaprogressivec_26; "CaProgressiveCompressor::EndSurfaceUpda"...
0x18006ec9d  mov     [rsp+1A0h+var_128], rax
0x18006eca2  lea     rax, [rsp+1A0h+var_130]
0x18006eca7  mov     [rsp+1A0h+var_160], rax
0x18006ecac  lea     rax, [rsp+1A0h+var_138]
0x18006ecb1  mov     [rsp+1A0h+var_168], rax
0x18006ecb6  lea     rax, [rbp+0A0h+var_120]
0x18006ecba  mov     [rsp+1A0h+var_170], rax
0x18006ecbf  lea     rax, [rsp+1A0h+var_138+4]
0x18006ecc4  mov     [rsp+1A0h+var_178], rax
0x18006ecc9  lea     rax, [rsp+1A0h+var_128]
0x18006ecce  mov     [rsp+1A0h+var_180], rax
0x18006ecd3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006ecd8  xor     eax, eax
0x18006ecda  jmp     loc_18006F318
0x18006ecdf  cmp     dword ptr [rax+38h], 2
0x18006ece3  jz      loc_18006EDA7
0x18006ece9  mov     eax, cs:CallbackContext
0x18006ecef  cmp     eax, 2
0x18006ecf2  jbe     loc_18006ED9D
0x18006ecf8  mov     rax, [r15]
0x18006ecfb  lea     rcx, off_1801A4A00; "PCS_UNINITIALIZED"
0x18006ed02  lea     rdx, word_1802A110E
0x18006ed09  movsxd  rax, dword ptr [rax+38h]
0x18006ed0d  mov     dword ptr [rsp+1A0h+var_138+4], 1E2h
0x18006ed15  mov     dword ptr [rsp+1A0h+var_138], 80004005h
0x18006ed1d  mov     rax, [rcx+rax*8]
0x18006ed21  mov     [rsp+1A0h+var_130], rax
0x18006ed26  mov     rax, cs:off_1801A4A10; "PCS_SURFACE_UPDATE"
0x18006ed2d  mov     [rbp+0A0h+var_120], rax
0x18006ed31  lea     rax, aEndsurfaceupda_0; "EndSurfaceUpdate"
0x18006ed38  mov     [rsp+1A0h+var_128], rax
0x18006ed3d  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18006ed44  mov     [rsp+1A0h+var_140], rax
0x18006ed49  lea     rax, aCaprogressivec_22; "CaProgressiveCompressor::EndSurfaceUpda"...
0x18006ed50  mov     [rbp+0A0h+var_88], rax
0x18006ed54  lea     rax, [rsp+1A0h+var_130]
0x18006ed59  mov     [rsp+1A0h+var_150], rax
0x18006ed5e  lea     rax, [rbp+0A0h+var_120]
0x18006ed62  mov     [rsp+1A0h+var_158], rax
0x18006ed67  lea     rax, [rsp+1A0h+var_128]
0x18006ed6c  mov     [rsp+1A0h+var_160], rax
0x18006ed71  lea     rax, [rsp+1A0h+var_138+4]
0x18006ed76  mov     [rsp+1A0h+var_168], rax
0x18006ed7b  lea     rax, [rsp+1A0h+var_140]
0x18006ed80  mov     [rsp+1A0h+var_170], rax
0x18006ed85  lea     rax, [rsp+1A0h+var_138]
0x18006ed8a  mov     [rsp+1A0h+var_178], rax
0x18006ed8f  lea     rax, [rbp+0A0h+var_88]
0x18006ed93  mov     [rsp+1A0h+var_180], rax
0x18006ed98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006ed9d  mov     eax, 80070057h
0x18006eda2  jmp     loc_18006F318
0x18006eda7  mov     dword ptr [rax+38h], 0Ah
0x18006edae  lea     rdx, [rsp+1A0h+var_128]; struct CacNx::ISurfaceEncoder **
0x18006edb3  mov     rcx, [r15]; this
0x18006edb6  mov     [rsp+1A0h+var_128], r13
0x18006edbb  call    ?GetSurfaceEncoder@CaProgressiveSurfaceContext@@QEAAJPEAPEAVISurfaceEncoder@CacNx@@@Z; CaProgressiveSurfaceContext::GetSurfaceEncoder(CacNx::ISurfaceEncoder * *)
0x18006edc0  cmp     dword ptr [rbx+3Ch], 2
0x18006edc4  mov     rcx, [rsp+1A0h+var_128]
0x18006edc9  mov     [rbp+0A0h+var_118], r13d
0x18006edcd  jnz     loc_18006F011
0x18006edd3  mov     [rsp+1A0h+var_130], r13
0x18006edd8  lea     r8, [rsp+1A0h+var_130]
0x18006eddd  mov     rax, [rcx]
0x18006ede0  lea     rdx, IID_ISurfaceEncoderX11
0x18006ede7  mov     rax, [rax]
0x18006edea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006edef  mov     rcx, [rbx+100h]
0x18006edf6  lea     r8, [rsp+1A0h+var_140]
0x18006edfb  mov     [rbp+0A0h+var_120], r13
0x18006edff  lea     rdx, IID_ICaGfxSourceProgressive
0x18006ee06  mov     [rsp+1A0h+var_140], r13
0x18006ee0b  mov     rax, [rcx]
0x18006ee0e  mov     rax, [rax]
0x18006ee11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee16  mov     edi, eax
0x18006ee18  test    eax, eax
0x18006ee1a  js      loc_18006EF1D
0x18006ee20  mov     rcx, [rsp+1A0h+var_140]
0x18006ee25  test    rcx, rcx
0x18006ee28  jz      loc_18006EF22
0x18006ee2e  mov     rax, [rcx]
0x18006ee31  lea     r8, [rbp+0A0h+var_120]
0x18006ee35  mov     rdx, [r15]
0x18006ee38  mov     rax, [rax+30h]
0x18006ee3c  mov     edx, [rdx+58h]
0x18006ee3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee44  mov     edi, eax
0x18006ee46  test    eax, eax
0x18006ee48  jns     loc_18006EF1D
0x18006ee4e  mov     eax, cs:CallbackContext
0x18006ee54  cmp     eax, 2
0x18006ee57  jbe     short loc_18006EEC5
0x18006ee59  lea     rax, aEndsurfaceupda_0; "EndSurfaceUpdate"
0x18006ee60  mov     dword ptr [rsp+1A0h+var_138+4], 202h
0x18006ee68  mov     [rbp+0A0h+var_88], rax
0x18006ee6c  lea     rdx, byte_1802A0EBB
0x18006ee73  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18006ee7a  mov     dword ptr [rsp+1A0h+var_138], 80004005h
0x18006ee82  mov     [rbp+0A0h+var_110], rax
0x18006ee86  lea     rax, aCouldNotObtain; "Could not obtain encoding input surface"
0x18006ee8d  mov     [rbp+0A0h+var_108], rax
0x18006ee91  lea     rax, [rbp+0A0h+var_88]
0x18006ee95  mov     [rsp+1A0h+var_160], rax
0x18006ee9a  lea     rax, [rsp+1A0h+var_138+4]
0x18006ee9f  mov     [rsp+1A0h+var_168], rax
0x18006eea4  lea     rax, [rbp+0A0h+var_110]
0x18006eea8  mov     [rsp+1A0h+var_170], rax
0x18006eead  lea     rax, [rsp+1A0h+var_138]
0x18006eeb2  mov     [rsp+1A0h+var_178], rax
0x18006eeb7  lea     rax, [rbp+0A0h+var_108]
0x18006eebb  mov     [rsp+1A0h+var_180], rax
0x18006eec0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006eec5  mov     rcx, [rsp+1A0h+var_140]
0x18006eeca  test    rcx, rcx
0x18006eecd  jz      short loc_18006EEE0
0x18006eecf  mov     [rsp+1A0h+var_140], r13
0x18006eed4  mov     rax, [rcx]
0x18006eed7  mov     rax, [rax+10h]
0x18006eedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eee0  mov     rcx, [rbp+0A0h+var_120]
0x18006eee4  test    rcx, rcx
0x18006eee7  jz      short loc_18006EEF9
0x18006eee9  mov     [rbp+0A0h+var_120], r13
0x18006eeed  mov     rax, [rcx]
0x18006eef0  mov     rax, [rax+10h]
0x18006eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eef9  mov     rcx, [rsp+1A0h+var_130]
0x18006eefe  test    rcx, rcx
0x18006ef01  jz      loc_18006F30C
0x18006ef07  mov     [rsp+1A0h+var_130], r13
0x18006ef0c  mov     rax, [rcx]
0x18006ef0f  mov     rax, [rax+10h]
0x18006ef13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef18  jmp     loc_18006F30C
0x18006ef1d  mov     rcx, [rsp+1A0h+var_140]
0x18006ef22  mov     rax, [rbp+0A0h+var_120]
0x18006ef26  lea     r14, [rbx+80h]
0x18006ef2d  mov     qword ptr [rbp+0A0h+var_78], rax
0x18006ef31  lea     rsi, [rbx+98h]
0x18006ef38  mov     rax, [rbx+78h]
0x18006ef3c  mov     qword ptr [rbp+0A0h+var_68], rax
0x18006ef40  mov     eax, [r14]
0x18006ef43  mov     dword ptr [rbp+0A0h+var_78+8], eax
0x18006ef46  mov     dword ptr [rbp+0A0h+var_78+0Ch], r13d
0x18006ef4a  mov     qword ptr [rbp+0A0h+var_68+8], r13
0x18006ef4e  cmp     [rsi], r13d
0x18006ef51  jbe     short loc_18006EFCA
0x18006ef53  mov     rcx, [rbx+50h]; SRWLock
0x18006ef57  mov     [rbp+0A0h+var_108], rcx
0x18006ef5b  mov     [rbp+0A0h+var_100], r13d
0x18006ef5f  test    rcx, rcx
0x18006ef62  jz      short loc_18006EF71
0x18006ef64  call    cs:__imp_AcquireSRWLockExclusive
0x18006ef6a  mov     [rbp+0A0h+var_100], 1
0x18006ef71  mov     rcx, [rsp+1A0h+var_130]
0x18006ef76  lea     rdx, [rbp+0A0h+var_118]
0x18006ef7a  mov     r9, [rbx+90h]
0x18006ef81  mov     r8d, [rsi]
0x18006ef84  mov     [rsp+1A0h+var_178], rdx
0x18006ef89  mov     rdx, [rbx+0C8h]
0x18006ef90  mov     rax, [rcx]
0x18006ef93  mov     [rsp+1A0h+var_180], rdx
0x18006ef98  lea     rdx, [rbp+0A0h+var_78]
0x18006ef9c  mov     rax, [rax+48h]
0x18006efa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efa5  mov     edi, eax
0x18006efa7  test    eax, eax
0x18006efa9  jns     short loc_18006EFBC
0x18006efab  cmp     [rsp+1A0h+var_140], r13
0x18006efb0  jz      short loc_18006EFBC
0x18006efb2  mov     edx, eax; int
0x18006efb4  mov     rcx, rbx; this
0x18006efb7  call    ?handleCodecError@CaProgressiveCompressor@@AEAAXJ@Z; CaProgressiveCompressor::handleCodecError(long)
0x18006efbc  lea     rcx, [rbp+0A0h+var_108]; this
0x18006efc0  call    ??1CAutoLockExclusive@@QEAA@XZ; CAutoLockExclusive::~CAutoLockExclusive(void)
0x18006efc5  mov     rcx, [rsp+1A0h+var_140]
0x18006efca  test    rcx, rcx
0x18006efcd  jz      short loc_18006EFE0
0x18006efcf  mov     [rsp+1A0h+var_140], r13
0x18006efd4  mov     rax, [rcx]
0x18006efd7  mov     rax, [rax+10h]
0x18006efdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efe0  mov     rcx, [rbp+0A0h+var_120]
0x18006efe4  test    rcx, rcx
0x18006efe7  jz      short loc_18006EFF9
0x18006efe9  mov     [rbp+0A0h+var_120], r13
0x18006efed  mov     rax, [rcx]
0x18006eff0  mov     rax, [rax+10h]
0x18006eff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eff9  mov     rcx, [rsp+1A0h+var_130]
0x18006effe  test    rcx, rcx
0x18006f001  jz      loc_18006F209
0x18006f007  mov     [rsp+1A0h+var_130], r13
0x18006f00c  jmp     loc_18006F1FD
0x18006f011  mov     [rsp+1A0h+var_140], r13
0x18006f016  lea     r8, [rsp+1A0h+var_140]
0x18006f01b  mov     rax, [rcx]
0x18006f01e  lea     rdx, IID_ISurfaceEncoderCpu
0x18006f025  mov     rax, [rax]
0x18006f028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f02d  mov     rcx, [rbx+100h]
0x18006f034  lea     r8, [rbp+0A0h+var_78]
0x18006f038  mov     rdx, [r15]
0x18006f03b  xorps   xmm0, xmm0
0x18006f03e  xorps   xmm1, xmm1
0x18006f041  xor     eax, eax
0x18006f043  mov     [rbp+0A0h+var_90], rax
0x18006f047  movups  [rbp+0A0h+var_78], xmm0
0x18006f04b  movups  [rbp+0A0h+var_68], xmm0
0x18006f04f  movups  [rbp+0A0h+var_58], xmm0
0x18006f053  movups  [rbp+0A0h+var_C0], xmm1
0x18006f057  movups  [rbp+0A0h+var_B0], xmm1
0x18006f05b  movups  [rbp+0A0h+var_A0], xmm1
0x18006f05f  mov     rax, [rcx]
0x18006f062  mov     rdx, [rdx+58h]
0x18006f066  mov     rax, [rax+38h]
0x18006f06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f06f  mov     edi, eax
0x18006f071  test    eax, eax
0x18006f073  jns     short loc_18006F094
0x18006f075  mov     rcx, [rsp+1A0h+var_140]
0x18006f07a  test    rcx, rcx
0x18006f07d  jz      loc_18006F30C
0x18006f083  mov     [rsp+1A0h+var_140], r13
0x18006f088  mov     rdx, [rcx]
0x18006f08b  mov     rax, [rdx+10h]
0x18006f08f  jmp     loc_18006EF13
0x18006f094  mov     eax, dword ptr [rbp+0A0h+var_78+8]
0x18006f097  mov     dword ptr [rbp+0A0h+var_80], eax
0x18006f09a  mov     eax, dword ptr [rbp+0A0h+var_78+0Ch]
0x18006f09d  mov     dword ptr [rbp+0A0h+var_80+4], eax
0x18006f0a0  mov     eax, cs:CallbackContext
0x18006f0a6  mov     [rbp+0A0h+var_88], r13
0x18006f0aa  cmp     eax, 4
0x18006f0ad  jbe     short loc_18006F105
0x18006f0af  mov     eax, dword ptr [rbp+0A0h+var_78+0Ch]
0x18006f0b2  lea     rdx, word_1802A1772
0x18006f0b9  mov     dword ptr [rsp+1A0h+var_138+4], eax
0x18006f0bd  mov     eax, dword ptr [rbp+0A0h+var_78+8]
0x18006f0c0  mov     dword ptr [rsp+1A0h+var_138], eax
0x18006f0c4  mov     rax, [r15]
0x18006f0c7  mov     rcx, [rax+58h]
0x18006f0cb  lea     rax, aEndSurfaceUpda; "End Surface Update for surface# 0x%I64x"...
0x18006f0d2  mov     [rbp+0A0h+var_110], rax
0x18006f0d6  lea     rax, [rsp+1A0h+var_138+4]
0x18006f0db  mov     [rsp+1A0h+var_168], rax
0x18006f0e0  lea     rax, [rsp+1A0h+var_138]
0x18006f0e5  mov     [rsp+1A0h+var_170], rax
0x18006f0ea  lea     rax, [rbp+0A0h+var_108]
0x18006f0ee  mov     [rsp+1A0h+var_178], rax
0x18006f0f3  lea     rax, [rbp+0A0h+var_110]
0x18006f0f7  mov     [rsp+1A0h+var_180], rax
0x18006f0fc  mov     [rbp+0A0h+var_108], rcx
0x18006f100  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006f105  mov     rcx, [rbx+100h]
0x18006f10c  lea     r8, [rbp+0A0h+var_C0]
0x18006f110  mov     rdx, [r15]
0x18006f113  mov     r9d, 2
0x18006f119  mov     [rsp+1A0h+var_180], r8
0x18006f11e  lea     r8, [rbp+0A0h+var_88]
0x18006f122  mov     rax, [rcx]
0x18006f125  mov     rdx, [rdx+58h]
0x18006f129  mov     rax, [rax+40h]
0x18006f12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f132  mov     edi, eax
0x18006f134  test    eax, eax
0x18006f136  jns     short loc_18006F150
0x18006f138  mov     rcx, [rsp+1A0h+var_140]
0x18006f13d  test    rcx, rcx
  ... truncated ...
```
