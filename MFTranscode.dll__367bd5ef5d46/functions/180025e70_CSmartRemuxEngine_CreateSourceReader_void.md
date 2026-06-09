# CSmartRemuxEngine::_CreateSourceReader(void)

- ea: `0x180025e70`
- end: `0x180026766`
- name: `?_CreateSourceReader@CSmartRemuxEngine@@IEAAJXZ`
- size: `2294`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001eed8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000b3ac`
- `0x1800174c0`
- `0x18001c240`
- `0x18001c280`
- `0x180025e70`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025fbd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025fbd`
- `MFPlat!MFCreateAttributes` at `0x180025ec5`
- `MFPlat!MFCreateAttributes` at `0x180025ec5`

## string_xrefs

- `0x180025e9a`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x18002632d`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x1800263f7`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x180026480`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x1800264da`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x180026534`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x180026587`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x180026604`: `CSmartRemuxEngine::_CreateSourceReader`
- `0x180026699`: `CSmartRemuxEngine::_CreateSourceReader`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_CreateSourceReader(LPVOID *this)
{
  HRESULT Instance; // ebx
  CallStackTracing *v3; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v5; // rdx
  CallStackTracing *v6; // rcx
  struct CallStackContext *v7; // rax
  _QWORD *v8; // rsi
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  LPVOID v11; // r8
  __int64 *v12; // r14
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  LPVOID v15; // r8
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  unsigned int v18; // esi
  char v19; // r13
  char v20; // r12
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  bool v24; // r14
  int v25; // eax
  bool v26; // r15
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  char *v30; // rcx
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  _BYTE v49[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v50; // [rsp+48h] [rbp-31h] BYREF
  int v51; // [rsp+50h] [rbp-29h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+58h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-19h] BYREF
  __int128 v54; // [rsp+70h] [rbp-9h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CSmartRemuxEngine::_CreateSourceReader", 726);
  ppMFAttributes = 0;
  Instance = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( Instance < 0 )
  {
    v3 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v3 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v3);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_CreateSourceReader", 736, Instance);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v5 = 56;
    goto LABEL_143;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_READWRITE_DISABLE_CONVERTERS,
               1);
  if ( Instance < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v6 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v7 + 499) != Instance )
        CallStackContext::TraceFailure(v7, "CSmartRemuxEngine::_CreateSourceReader", 739, Instance);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v5 = 57;
    goto LABEL_143;
  }
  v8 = this + 3;
  Instance = CoCreateInstance(
               &CLSID_MFReadWriteClassFactory,
               0,
               0x17u,
               &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627,
               this + 3);
  if ( Instance < 0 )
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v9 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v10 + 499) != Instance )
        CallStackContext::TraceFailure(v10, "CSmartRemuxEngine::_CreateSourceReader", 741, Instance);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v5 = 58;
    goto LABEL_143;
  }
  v11 = this[39];
  if ( v11 )
  {
    v12 = (__int64 *)(this + 4);
    Instance = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPVOID, IMFAttributes *, GUID *, char *))(*(_QWORD *)*v8 + 32LL))(
                 *v8,
                 &CLSID_MFSourceReader,
                 v11,
                 ppMFAttributes,
                 &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
                 (char *)this + 32);
    if ( Instance < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v13 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v14 + 499) != Instance )
          CallStackContext::TraceFailure(v14, "CSmartRemuxEngine::_CreateSourceReader", 745, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_144;
      v5 = 59;
      goto LABEL_143;
    }
    goto LABEL_43;
  }
  v15 = this[41];
  if ( !v15 )
  {
    v46 = CallStackTracing::s_wpInstance;
    Instance = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v46 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v47 = CallStackTracing::GetThreadRelativeContext(v46);
      if ( *((_DWORD *)v47 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v47, "CSmartRemuxEngine::_CreateSourceReader", 753, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v5 = 61;
LABEL_143:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, Instance);
    goto LABEL_144;
  }
  v12 = (__int64 *)(this + 4);
  Instance = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPVOID, IMFAttributes *, GUID *, char *))(*(_QWORD *)*v8 + 32LL))(
               *v8,
               &CLSID_MFSourceReader,
               v15,
               ppMFAttributes,
               &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
               (char *)this + 32);
  if ( Instance < 0 )
  {
    v16 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v16 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( *((_DWORD *)v17 + 499) != Instance )
        CallStackContext::TraceFailure(v17, "CSmartRemuxEngine::_CreateSourceReader", 749, Instance);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v5 = 60;
    goto LABEL_143;
  }
LABEL_43:
  v18 = 0;
  v19 = 0;
  v20 = 0;
  while ( 1 )
  {
    v21 = *v12;
    v51 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v21 + 24LL))(v21, v18, &v51);
    Instance = v22;
    if ( v22 == -1072875853 )
    {
      Instance = 0;
      if ( !v20 )
      {
        if ( byte_18006A389 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this);
        v44 = CallStackTracing::s_wpInstance;
        Instance = -1072875852;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v44 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext(v44);
          if ( *((_DWORD *)v45 + 499) != -1072875852 )
            CallStackContext::TraceFailure(v45, "CSmartRemuxEngine::_CreateSourceReader", 840, -1072875852);
        }
        if ( g_wppLevels )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            72,
            &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids,
            this,
            -1072875852);
      }
      goto LABEL_144;
    }
    if ( v22 < 0 )
      break;
    if ( v51 )
    {
      v23 = *v12;
      v50 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, v18, &v50);
      if ( Instance < 0 )
      {
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v40 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext(v40);
          if ( *((_DWORD *)v41 + 499) != Instance )
            CallStackContext::TraceFailure(v41, "CSmartRemuxEngine::_CreateSourceReader", 777, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v33 = 63;
LABEL_117:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v33,
          &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids,
          this,
          Instance);
        goto LABEL_118;
      }
      Buf1 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v50 + 264LL))(v50, &Buf1);
      if ( Instance < 0 )
      {
        v38 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v38 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v38);
          if ( *((_DWORD *)v39 + 499) != Instance )
            CallStackContext::TraceFailure(v39, "CSmartRemuxEngine::_CreateSourceReader", 780, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_118;
        v33 = 64;
        goto LABEL_117;
      }
      v24 = memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) == 0;
      v25 = memcmp_0(&Buf1, &MFMediaType_Video, 0x10u);
      v26 = v25 == 0;
      if ( !v24 && v25 || v19 && v24 || v20 && !v25 || !*((_DWORD *)this + 70) && v24 )
      {
        v12 = (__int64 *)(this + 4);
        Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)this[4] + 32LL))(this[4], v18, 0);
        if ( Instance < 0 )
        {
          v31 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v31 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext(v31);
            if ( *((_DWORD *)v32 + 499) != Instance )
              CallStackContext::TraceFailure(v32, "CSmartRemuxEngine::_CreateSourceReader", 790, Instance);
          }
          if ( !g_wppLevels )
            goto LABEL_118;
          v33 = 65;
          goto LABEL_117;
        }
        ++v18;
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
      }
      else
      {
        v54 = 0;
        Instance = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v50 + 80LL))(
                     v50,
                     &MF_MT_SUBTYPE,
                     &v54);
        if ( Instance < 0 )
        {
          v36 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v36 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext(v36);
            if ( *((_DWORD *)v37 + 499) != Instance )
              CallStackContext::TraceFailure(v37, "CSmartRemuxEngine::_CreateSourceReader", 797, Instance);
          }
          if ( !g_wppLevels )
            goto LABEL_118;
          v33 = 66;
          goto LABEL_117;
        }
        if ( v24 )
        {
          if ( memcmp_0(&v54, &MFAudioFormat_AAC, 0x10u) )
          {
            if ( byte_18006A389 )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this);
            v27 = CallStackTracing::s_wpInstance;
            Instance = -1072875852;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v27 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext(v27);
              if ( *((_DWORD *)v28 + 499) != -1072875852 )
                CallStackContext::TraceFailure(v28, "CSmartRemuxEngine::_CreateSourceReader", 803, -1072875852);
            }
            if ( g_wppLevels )
            {
              v29 = 68;
              goto LABEL_72;
            }
            goto LABEL_118;
          }
        }
        else if ( memcmp_0(&v54, &MFVideoFormat_H264, 0x10u) )
        {
          if ( byte_18006A389 )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this);
          v34 = CallStackTracing::s_wpInstance;
          Instance = -1072875852;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v34 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v34 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext(v34);
            if ( *((_DWORD *)v35 + 499) != -1072875852 )
              CallStackContext::TraceFailure(v35, "CSmartRemuxEngine::_CreateSourceReader", 811, -1072875852);
          }
          if ( g_wppLevels )
          {
            v29 = 70;
LABEL_72:
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v29,
              &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids,
              this,
              -1072875852);
          }
LABEL_118:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
          goto LABEL_144;
        }
        v19 |= v24;
        v20 |= v26;
        if ( v26 )
        {
          *((_DWORD *)this + 32) = v18;
          v30 = (char *)(this + 19);
          *((_WORD *)this + 74) = 256;
        }
        else
        {
          if ( !v24 )
            goto LABEL_79;
          *((_DWORD *)this + 24) = v18;
          v30 = (char *)(this + 15);
          *((_WORD *)this + 58) = 256;
        }
        ComSmartPtr<IMFMediaSource>::operator=(v30, &v50);
LABEL_79:
        ++v18;
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
        v12 = (__int64 *)(this + 4);
      }
    }
    else
    {
      ++v18;
    }
  }
  v42 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v42 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v42 + 8) )
  {
    v43 = CallStackTracing::GetThreadRelativeContext(v42);
    if ( *((_DWORD *)v43 + 499) != Instance )
      CallStackContext::TraceFailure(v43, "CSmartRemuxEngine::_CreateSourceReader", 768, Instance);
  }
  if ( g_wppLevels )
  {
    v5 = 62;
    goto LABEL_143;
  }
LABEL_144:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180025e70  push    rbp
0x180025e72  push    rbx
0x180025e73  push    rsi
0x180025e74  push    rdi
0x180025e75  push    r12
0x180025e77  push    r13
0x180025e79  push    r14
0x180025e7b  push    r15
0x180025e7d  lea     rbp, [rsp-1Fh]
0x180025e82  sub     rsp, 98h
0x180025e89  mov     rax, cs:__security_cookie
0x180025e90  xor     rax, rsp
0x180025e93  mov     [rbp+57h+var_50], rax
0x180025e97  mov     rdi, rcx
0x180025e9a  lea     r13, aCsmartremuxeng_3; "CSmartRemuxEngine::_CreateSourceReader"
0x180025ea1  mov     rdx, r13; char *
0x180025ea4  lea     rcx, [rbp+57h+var_90]; this
0x180025ea8  mov     r8d, 2D6h; int
0x180025eae  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180025eb3  xor     r15d, r15d
0x180025eb6  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180025eba  mov     [rbp+57h+ppMFAttributes], r15
0x180025ebe  lea     r12d, [r15+1]
0x180025ec2  mov     edx, r12d; cInitialSize
0x180025ec5  call    cs:__imp_MFCreateAttributes
0x180025ecb  mov     ebx, eax
0x180025ecd  test    eax, eax
0x180025ecf  jns     short loc_180025F27
0x180025ed1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025ed8  test    rcx, rcx
0x180025edb  jnz     short loc_180025EE9
0x180025edd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180025ee2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025ee9  cmp     [rcx+8], r15b
0x180025eed  jz      short loc_180025F10
0x180025eef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025ef4  cmp     [rax+7CCh], ebx
0x180025efa  jz      short loc_180025F10
0x180025efc  mov     r9d, ebx; int
0x180025eff  mov     r8d, 2E0h; int
0x180025f05  mov     rdx, r13; char *
0x180025f08  mov     rcx, rax; this
0x180025f0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025f10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180025f17  jb      loc_180026732
0x180025f1d  mov     edx, 38h ; '8'
0x180025f22  jmp     loc_180026714
0x180025f27  mov     rcx, [rbp+57h+ppMFAttributes]
0x180025f2b  lea     rdx, MF_READWRITE_DISABLE_CONVERTERS
0x180025f32  mov     r8d, r12d
0x180025f35  mov     rax, [rcx]
0x180025f38  mov     rax, [rax+0A8h]
0x180025f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f44  mov     ebx, eax
0x180025f46  test    eax, eax
0x180025f48  jns     short loc_180025FA0
0x180025f4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025f51  test    rcx, rcx
0x180025f54  jnz     short loc_180025F62
0x180025f56  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180025f5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025f62  cmp     [rcx+8], r15b
0x180025f66  jz      short loc_180025F89
0x180025f68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025f6d  cmp     [rax+7CCh], ebx
0x180025f73  jz      short loc_180025F89
0x180025f75  mov     r9d, ebx; int
0x180025f78  mov     r8d, 2E3h; int
0x180025f7e  mov     rdx, r13; char *
0x180025f81  mov     rcx, rax; this
0x180025f84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025f89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180025f90  jb      loc_180026732
0x180025f96  mov     edx, 39h ; '9'
0x180025f9b  jmp     loc_180026714
0x180025fa0  xor     edx, edx; pUnkOuter
0x180025fa2  lea     rsi, [rdi+18h]
0x180025fa6  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x180025fad  mov     [rsp+0D0h+ppv], rsi; ppv
0x180025fb2  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x180025fb9  lea     r8d, [rdx+17h]; dwClsContext
0x180025fbd  call    cs:__imp_CoCreateInstance
0x180025fc3  mov     ebx, eax
0x180025fc5  test    eax, eax
0x180025fc7  jns     short loc_18002601F
0x180025fc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025fd0  test    rcx, rcx
0x180025fd3  jnz     short loc_180025FE1
0x180025fd5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180025fda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025fe1  cmp     [rcx+8], r15b
0x180025fe5  jz      short loc_180026008
0x180025fe7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025fec  cmp     [rax+7CCh], ebx
0x180025ff2  jz      short loc_180026008
0x180025ff4  mov     r9d, ebx; int
0x180025ff7  mov     r8d, 2E5h; int
0x180025ffd  mov     rdx, r13; char *
0x180026000  mov     rcx, rax; this
0x180026003  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026008  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18002600f  jb      loc_180026732
0x180026015  mov     edx, 3Ah ; ':'
0x18002601a  jmp     loc_180026714
0x18002601f  mov     r8, [rdi+138h]
0x180026026  test    r8, r8
0x180026029  jz      loc_1800260BE
0x18002602f  mov     rcx, [rsi]
0x180026032  lea     rdx, _GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993
0x180026039  mov     r9, [rbp+57h+ppMFAttributes]
0x18002603d  lea     r14, [rdi+20h]
0x180026041  mov     [rsp+0D0h+var_A8], r14
0x180026046  mov     [rsp+0D0h+ppv], rdx
0x18002604b  lea     rdx, CLSID_MFSourceReader
0x180026052  mov     rax, [rcx]
0x180026055  mov     rax, [rax+20h]
0x180026059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002605e  mov     ebx, eax
0x180026060  test    eax, eax
0x180026062  jns     loc_180026159
0x180026068  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002606f  test    rcx, rcx
0x180026072  jnz     short loc_180026080
0x180026074  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026079  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180026080  cmp     [rcx+8], r15b
0x180026084  jz      short loc_1800260A7
0x180026086  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002608b  cmp     [rax+7CCh], ebx
0x180026091  jz      short loc_1800260A7
0x180026093  mov     r9d, ebx; int
0x180026096  mov     r8d, 2E9h; int
0x18002609c  mov     rdx, r13; char *
0x18002609f  mov     rcx, rax; this
0x1800260a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800260a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800260ae  jb      loc_180026732
0x1800260b4  mov     edx, 3Bh ; ';'
0x1800260b9  jmp     loc_180026714
0x1800260be  mov     r8, [rdi+148h]
0x1800260c5  test    r8, r8
0x1800260c8  jz      loc_1800266C2
0x1800260ce  mov     rcx, [rsi]
0x1800260d1  lea     rdx, _GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993
0x1800260d8  mov     r9, [rbp+57h+ppMFAttributes]
0x1800260dc  lea     r14, [rdi+20h]
0x1800260e0  mov     [rsp+0D0h+var_A8], r14
0x1800260e5  mov     [rsp+0D0h+ppv], rdx
0x1800260ea  lea     rdx, CLSID_MFSourceReader
0x1800260f1  mov     rax, [rcx]
0x1800260f4  mov     rax, [rax+20h]
0x1800260f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260fd  mov     ebx, eax
0x1800260ff  test    eax, eax
0x180026101  jns     short loc_180026159
0x180026103  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002610a  test    rcx, rcx
0x18002610d  jnz     short loc_18002611B
0x18002610f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026114  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002611b  cmp     [rcx+8], r15b
0x18002611f  jz      short loc_180026142
0x180026121  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026126  cmp     [rax+7CCh], ebx
0x18002612c  jz      short loc_180026142
0x18002612e  mov     r9d, ebx; int
0x180026131  mov     r8d, 2EDh; int
0x180026137  mov     rdx, r13; char *
0x18002613a  mov     rcx, rax; this
0x18002613d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026142  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180026149  jb      loc_180026732
0x18002614f  mov     edx, 3Ch ; '<'
0x180026154  jmp     loc_180026714
0x180026159  mov     esi, r15d
0x18002615c  mov     r13b, r15b
0x18002615f  mov     r12b, r15b
0x180026162  mov     rcx, [r14]
0x180026165  lea     r8, [rbp+57h+var_80]
0x180026169  mov     [rbp+57h+var_80], r15d
0x18002616d  mov     edx, esi
0x18002616f  mov     rax, [rcx]
0x180026172  mov     rax, [rax+18h]
0x180026176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002617b  mov     ebx, eax
0x18002617d  cmp     eax, 0C00D36B3h
0x180026182  jz      loc_180026630
0x180026188  test    eax, eax
0x18002618a  js      loc_1800265D6
0x180026190  cmp     [rbp+57h+var_80], r15d
0x180026194  jnz     short loc_18002619A
0x180026196  inc     esi
0x180026198  jmp     short loc_180026162
0x18002619a  mov     rcx, [r14]
0x18002619d  lea     r8, [rbp+57h+var_88]
0x1800261a1  mov     [rbp+57h+var_88], r15
0x1800261a5  mov     edx, esi
0x1800261a7  mov     rax, [rcx]
0x1800261aa  mov     rax, [rax+30h]
0x1800261ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261b3  mov     ebx, eax
0x1800261b5  test    eax, eax
0x1800261b7  js      loc_180026559
0x1800261bd  mov     rcx, [rbp+57h+var_88]
0x1800261c1  lea     rdx, [rbp+57h+Buf1]
0x1800261c5  xorps   xmm0, xmm0
0x1800261c8  movups  [rbp+57h+Buf1], xmm0
0x1800261cc  mov     rax, [rcx]
0x1800261cf  mov     rax, [rax+108h]
0x1800261d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261db  mov     ebx, eax
0x1800261dd  test    eax, eax
0x1800261df  js      loc_180026506
0x1800261e5  mov     ebx, 10h
0x1800261ea  lea     rdx, MFMediaType_Audio; Buf2
0x1800261f1  mov     r8d, ebx; Size
0x1800261f4  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800261f8  call    memcmp_0
0x1800261fd  test    eax, eax
0x1800261ff  lea     rdx, MFMediaType_Video; Buf2
0x180026206  mov     r8d, ebx; Size
0x180026209  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002620d  setz    r14b
0x180026211  call    memcmp_0
0x180026216  test    eax, eax
0x180026218  setz    r15b
0x18002621c  test    r14b, r14b
0x18002621f  jnz     short loc_180026226
0x180026221  test    r15b, r15b
0x180026224  jz      short loc_180026248
0x180026226  test    r13b, r13b
0x180026229  jz      short loc_180026230
0x18002622b  test    r14b, r14b
0x18002622e  jnz     short loc_180026248
0x180026230  test    r12b, r12b
0x180026233  jz      short loc_18002623A
0x180026235  test    r15b, r15b
0x180026238  jnz     short loc_180026248
0x18002623a  cmp     dword ptr [rdi+118h], 0
0x180026241  jnz     short loc_18002627D
0x180026243  test    r14b, r14b
0x180026246  jz      short loc_18002627D
0x180026248  lea     r14, [rdi+20h]
0x18002624c  xor     r8d, r8d
0x18002624f  mov     rcx, [r14]
0x180026252  mov     edx, esi
0x180026254  mov     rax, [rcx]
0x180026257  mov     rax, [rax+20h]
0x18002625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026260  xor     r15d, r15d
0x180026263  mov     ebx, eax
0x180026265  test    eax, eax
0x180026267  js      loc_1800263C9
0x18002626d  inc     esi
0x18002626f  lea     rcx, [rbp+57h+var_88]
0x180026273  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180026278  jmp     loc_180026162
0x18002627d  mov     rcx, [rbp+57h+var_88]
0x180026281  lea     r8, [rbp+57h+var_60]
0x180026285  xorps   xmm0, xmm0
0x180026288  lea     rdx, MF_MT_SUBTYPE
0x18002628f  movups  [rbp+57h+var_60], xmm0
0x180026293  mov     rax, [rcx]
0x180026296  mov     rax, [rax+50h]
0x18002629a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002629f  mov     ebx, eax
0x1800262a1  test    eax, eax
0x1800262a3  js      loc_1800264AC
0x1800262a9  lea     rcx, [rbp+57h+var_60]; Buf1
0x1800262ad  mov     r8d, 10h; Size
0x1800262b3  test    r14b, r14b
0x1800262b6  jz      loc_18002635D
0x1800262bc  lea     rdx, MFAudioFormat_AAC; Buf2
0x1800262c3  call    memcmp_0
0x1800262c8  test    eax, eax
0x1800262ca  jz      loc_180026371
0x1800262d0  cmp     cs:byte_18006A389, 1
0x1800262d7  jb      short loc_1800262F8
0x1800262d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e0  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x1800262e7  mov     edx, 43h ; 'C'
0x1800262ec  mov     r9, rdi
0x1800262ef  mov     rcx, [rcx+38h]
0x1800262f3  call    WPP_SF_q
0x1800262f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800262ff  mov     esi, 0C00D36B4h
0x180026304  mov     ebx, esi
0x180026306  test    rcx, rcx
0x180026309  jnz     short loc_180026317
0x18002630b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026310  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180026317  cmp     byte ptr [rcx+8], 0
0x18002631b  jz      short loc_180026342
0x18002631d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026322  cmp     [rax+7CCh], esi
0x180026328  jz      short loc_180026342
0x18002632a  mov     r9d, esi; int
0x18002632d  lea     rdx, aCsmartremuxeng_3; "CSmartRemuxEngine::_CreateSourceReader"
0x180026334  mov     r8d, 323h; int
0x18002633a  mov     rcx, rax; this
  ... truncated ...
```
