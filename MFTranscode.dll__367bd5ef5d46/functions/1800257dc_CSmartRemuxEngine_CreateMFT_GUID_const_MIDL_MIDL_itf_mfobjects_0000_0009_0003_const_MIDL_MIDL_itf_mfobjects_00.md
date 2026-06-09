# CSmartRemuxEngine::_CreateMFT(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,uint)

- ea: `0x1800257dc`
- end: `0x180025a5c`
- name: `?_CreateMFT@CSmartRemuxEngine@@KAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAUIMFTransform@@I@Z`
- size: `640`
- prototype: `static int(const struct _GUID *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFTransform **, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002676c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001c280`
- `0x1800257dc`
- `0x18002bc50`
- `0x18004f3c8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a2d`
- `MFPlat!MFTEnumEx` at `0x180025858`
- `MFPlat!MFTEnumEx` at `0x180025858`

## string_xrefs

- `0x1800257fa`: `CSmartRemuxEngine::_CreateMFT`
- `0x180025892`: `CSmartRemuxEngine::_CreateMFT`
- `0x18002593e`: `CSmartRemuxEngine::_CreateMFT`
- `0x1800259bf`: `CSmartRemuxEngine::_CreateMFT`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_CreateMFT(
        const struct _GUID *a1,
        const MFT_REGISTER_TYPE_INFO *a2,
        const MFT_REGISTER_TYPE_INFO *a3,
        struct IMFTransform **a4,
        UINT32 Flags)
{
  UINT32 v9; // edx
  GUID v10; // xmm0
  HRESULT v11; // ebx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 i; // rdi
  IMFActivate *v20; // rcx
  IMFActivate **pppMFTActivate; // [rsp+30h] [rbp-20h] BYREF
  struct IMFTransform *v23; // [rsp+38h] [rbp-18h] BYREF
  GUID guidCategory; // [rsp+40h] [rbp-10h] BYREF
  char v25; // [rsp+70h] [rbp+20h] BYREF
  UINT32 pnumMFTActivate; // [rsp+88h] [rbp+38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v25, "CSmartRemuxEngine::_CreateMFT", 1343);
  v9 = Flags;
  *a4 = 0;
  v10 = *a1;
  pppMFTActivate = 0;
  v23 = 0;
  pnumMFTActivate = 0;
  guidCategory = v10;
  v11 = MFTEnumEx(&guidCategory, v9, a2, a3, &pppMFTActivate, &pnumMFTActivate);
  if ( v11 >= 0 )
  {
    if ( pnumMFTActivate )
    {
      v11 = ((__int64 (__fastcall *)(IMFActivate *, GUID *, struct IMFTransform **))(*pppMFTActivate)->lpVtbl->ActivateObject)(
              *pppMFTActivate,
              &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
              &v23);
      if ( v11 >= 0 )
      {
        *a4 = v23;
        v23 = 0;
      }
      else
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v17 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_CreateMFT", 1365, v11);
        }
        if ( g_wppLevels )
        {
          v14 = 157;
          goto LABEL_9;
        }
      }
    }
    else
    {
      if ( byte_18006A389 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 155, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids);
      v15 = CallStackTracing::s_wpInstance;
      v11 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v15 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( *((_DWORD *)v16 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v16, "CSmartRemuxEngine::_CreateMFT", 1362, -1072875845);
      }
      if ( g_wppLevels )
      {
        v14 = 156;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v13 + 499) != v11 )
        CallStackContext::TraceFailure(v13, "CSmartRemuxEngine::_CreateMFT", 1357, v11);
    }
    if ( g_wppLevels )
    {
      v14 = 154;
LABEL_9:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, 0, v11);
    }
  }
  for ( i = 0; (unsigned int)i < pnumMFTActivate; i = (unsigned int)(i + 1) )
  {
    v20 = pppMFTActivate[i];
    if ( v20 )
    {
      ((void (__fastcall *)(IMFActivate *))v20->lpVtbl->Release)(v20);
      pppMFTActivate[i] = 0;
    }
  }
  CoTaskMemFree(pppMFTActivate);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v23);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800257dc  mov     [rsp-18h+arg_8], rbx
0x1800257e1  mov     [rsp-18h+arg_10], rsi
0x1800257e6  push    rbp
0x1800257e7  push    rdi
0x1800257e8  push    r14
0x1800257ea  mov     rbp, rsp
0x1800257ed  sub     rsp, 50h
0x1800257f1  mov     rdi, r8
0x1800257f4  mov     rsi, rdx
0x1800257f7  mov     rbx, rcx
0x1800257fa  lea     rdx, aCsmartremuxeng_23; "CSmartRemuxEngine::_CreateMFT"
0x180025801  mov     r8d, 53Fh; int
0x180025807  lea     rcx, [rbp+arg_0]; this
0x18002580b  mov     r14, r9
0x18002580e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180025813  mov     edx, [rbp+Flags]; Flags
0x180025816  lea     rax, [rbp+arg_18]
0x18002581a  mov     [rsp+50h+pnumMFTActivate], rax; pnumMFTActivate
0x18002581f  lea     rcx, [rbp+guidCategory]; guidCategory
0x180025823  mov     qword ptr [r14], 0
0x18002582a  lea     rax, [rbp+var_20]
0x18002582e  movups  xmm0, xmmword ptr [rbx]
0x180025831  mov     r9, rdi; pOutputType
0x180025834  mov     [rsp+50h+pppMFTActivate], rax; pppMFTActivate
0x180025839  mov     r8, rsi; pInputType
0x18002583c  mov     [rbp+var_20], 0
0x180025844  mov     [rbp+var_18], 0
0x18002584c  mov     [rbp+arg_18], 0
0x180025853  movdqu  xmmword ptr [rbp+guidCategory.Data1], xmm0
0x180025858  call    cs:__imp_MFTEnumEx
0x18002585e  mov     ebx, eax
0x180025860  test    eax, eax
0x180025862  jns     short loc_1800258DC
0x180025864  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002586b  test    rcx, rcx
0x18002586e  jnz     short loc_18002587C
0x180025870  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180025875  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002587c  cmp     byte ptr [rcx+8], 0
0x180025880  jz      short loc_1800258A7
0x180025882  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025887  cmp     [rax+7CCh], ebx
0x18002588d  jz      short loc_1800258A7
0x18002588f  mov     r9d, ebx; int
0x180025892  lea     rdx, aCsmartremuxeng_23; "CSmartRemuxEngine::_CreateMFT"
0x180025899  mov     r8d, 54Dh; int
0x18002589f  mov     rcx, rax; this
0x1800258a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800258a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800258ae  jb      loc_1800259F6
0x1800258b4  mov     edx, 9Ah
0x1800258b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c0  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x1800258c7  xor     r9d, r9d
0x1800258ca  mov     dword ptr [rsp+50h+pppMFTActivate], ebx
0x1800258ce  mov     rcx, [rcx+10h]
0x1800258d2  call    WPP_SF_qd
0x1800258d7  jmp     loc_1800259F6
0x1800258dc  cmp     [rbp+arg_18], 0
0x1800258e0  jnz     loc_18002596A
0x1800258e6  cmp     cs:byte_18006A389, 1
0x1800258ed  jb      short loc_18002590B
0x1800258ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258f6  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x1800258fd  mov     edx, 9Bh
0x180025902  mov     rcx, [rcx+38h]
0x180025906  call    WPP_SF_
0x18002590b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025912  mov     ebx, 0C00D36BBh
0x180025917  test    rcx, rcx
0x18002591a  jnz     short loc_180025928
0x18002591c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180025921  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025928  cmp     byte ptr [rcx+8], 0
0x18002592c  jz      short loc_180025953
0x18002592e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025933  cmp     [rax+7CCh], ebx
0x180025939  jz      short loc_180025953
0x18002593b  mov     r9d, ebx; int
0x18002593e  lea     rdx, aCsmartremuxeng_23; "CSmartRemuxEngine::_CreateMFT"
0x180025945  mov     r8d, 552h; int
0x18002594b  mov     rcx, rax; this
0x18002594e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180025953  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002595a  jb      loc_1800259F6
0x180025960  mov     edx, 9Ch
0x180025965  jmp     loc_1800258B9
0x18002596a  mov     rax, [rbp+var_20]
0x18002596e  lea     r8, [rbp+var_18]
0x180025972  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x180025979  mov     rcx, [rax]
0x18002597c  mov     rax, [rcx]
0x18002597f  mov     rax, [rax+108h]
0x180025986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002598b  mov     ebx, eax
0x18002598d  test    eax, eax
0x18002598f  jns     short loc_1800259E7
0x180025991  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025998  test    rcx, rcx
0x18002599b  jnz     short loc_1800259A9
0x18002599d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800259a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800259a9  cmp     byte ptr [rcx+8], 0
0x1800259ad  jz      short loc_1800259D4
0x1800259af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800259b4  cmp     [rax+7CCh], ebx
0x1800259ba  jz      short loc_1800259D4
0x1800259bc  mov     r9d, ebx; int
0x1800259bf  lea     rdx, aCsmartremuxeng_23; "CSmartRemuxEngine::_CreateMFT"
0x1800259c6  mov     r8d, 555h; int
0x1800259cc  mov     rcx, rax; this
0x1800259cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800259d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800259db  jb      short loc_1800259F6
0x1800259dd  mov     edx, 9Dh
0x1800259e2  jmp     loc_1800258B9
0x1800259e7  mov     rax, [rbp+var_18]
0x1800259eb  mov     [r14], rax
0x1800259ee  mov     [rbp+var_18], 0
0x1800259f6  xor     edi, edi
0x1800259f8  cmp     [rbp+arg_18], edi
0x1800259fb  jbe     short loc_180025A29
0x1800259fd  mov     rax, [rbp+var_20]
0x180025a01  mov     rcx, [rax+rdi*8]
0x180025a05  test    rcx, rcx
0x180025a08  jz      short loc_180025A22
0x180025a0a  mov     rax, [rcx]
0x180025a0d  mov     rax, [rax+10h]
0x180025a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a16  mov     rax, [rbp+var_20]
0x180025a1a  mov     qword ptr [rax+rdi*8], 0
0x180025a22  inc     edi
0x180025a24  cmp     edi, [rbp+arg_18]
0x180025a27  jb      short loc_1800259FD
0x180025a29  mov     rcx, [rbp+var_20]; pv
0x180025a2d  call    cs:__imp_CoTaskMemFree
0x180025a33  lea     rcx, [rbp+var_18]
0x180025a37  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180025a3c  lea     rcx, [rbp+arg_0]; this
0x180025a40  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180025a45  lea     r11, [rsp+50h+var_s0]
0x180025a4a  mov     eax, ebx
0x180025a4c  mov     rbx, [r11+28h]
0x180025a50  mov     rsi, [r11+30h]
0x180025a54  mov     rsp, r11
0x180025a57  pop     r14
0x180025a59  pop     rdi
0x180025a5a  pop     rbp
0x180025a5b  retn
```
