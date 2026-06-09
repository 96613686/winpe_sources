# CTranscodeEngine::_CreateIInitializeWithStream(IInitializeWithStream * *)

- ea: `0x18002e1bc`
- end: `0x18002e753`
- name: `?_CreateIInitializeWithStream@CTranscodeEngine@@IEAAXPEAPEAUIInitializeWithStream@@@Z`
- size: `1431`
- prototype: `void __fastcall(CTranscodeEngine *__hidden this, struct IInitializeWithStream **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010fcc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001c280`
- `0x18002e1bc`
- `0x18004f3c8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e3cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e3cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e501`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e6f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e6f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e709`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e47e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e58d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e47e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e58d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6e9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002e5f7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002e5f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e674`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e674`

## string_xrefs

- `0x18002e1eb`: `CTranscodeEngine::_CreateIInitializeWithStream`
- `0x18002e45e`: `Extension`

## pseudocode

```c
void __fastcall CTranscodeEngine::_CreateIInitializeWithStream(CTranscodeEngine *this, LPVOID *a2)
{
  int (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v5; // rcx
  int v6; // edi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  LSTATUS ValueW; // edi
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  _BYTE v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v32; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  IID iid; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[256]; // [rsp+E0h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v26,
    "CTranscodeEngine::_CreateIInitializeWithStream",
    1970);
  v4 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 16);
  pcbData = 512;
  v35 = 0;
  ppv = 0;
  lpSubKey = 0;
  v27 = 0;
  hkey = 0;
  hKey = 0;
  v32 = 78;
  iid = 0;
  if ( (**v4)(v4, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, &v35) < 0
    || (*(int (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v35 + 104LL))(
         v35,
         &MF_BYTESTREAM_CONTENT_TYPE,
         &lpSubKey,
         &v27) < 0 )
  {
    v5 = *((_QWORD *)this + 22);
    v28 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, &v28);
    if ( v6 < 0 )
    {
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v7 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeEngine::_CreateIInitializeWithStream",
            1996,
            v6);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v9 = 217;
LABEL_19:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids, this, v6);
LABEL_20:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v28);
      goto LABEL_72;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v28 + 104LL))(
           v28,
           &MF_PD_MIME_TYPE,
           &lpSubKey,
           &v27);
    if ( v6 < 0 )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v10 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( *((_DWORD *)v11 + 499) != v6 )
          CallStackContext::TraceFailure(v11, "CTranscodeEngine::_CreateIInitializeWithStream", 2000, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v9 = 218;
      goto LABEL_19;
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v28);
  }
  ValueW = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"MIME\\Database\\Content Type", 0, 1u, &hkey);
  if ( ValueW >= 0 )
  {
    ValueW = RegGetValueW(hkey, lpSubKey, L"Extension", 2u, 0, SubKey, &pcbData);
    if ( ValueW >= 0 )
    {
      ValueW = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertyHandlers",
                 0,
                 1u,
                 &hKey);
      if ( ValueW >= 0 )
      {
        ValueW = RegGetValueW(hKey, SubKey, 0, 2u, 0, sz, &v32);
        if ( ValueW >= 0 )
        {
          ValueW = IIDFromString(sz, &iid);
          if ( ValueW >= 0 )
          {
            ValueW = CoCreateInstance(&iid, 0, 0x17u, &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f, &ppv);
            if ( ValueW >= 0 )
            {
              *a2 = ppv;
              ppv = 0;
            }
            else
            {
              v24 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v24 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v24 + 8) )
              {
                v25 = CallStackTracing::GetThreadRelativeContext(v24);
                if ( *((_DWORD *)v25 + 499) != ValueW )
                  CallStackContext::TraceFailure(v25, "CTranscodeEngine::_CreateIInitializeWithStream", 2015, ValueW);
              }
              if ( g_wppLevels )
              {
                v15 = 224;
                goto LABEL_30;
              }
            }
          }
          else
          {
            v22 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v22 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v22 + 8) )
            {
              v23 = CallStackTracing::GetThreadRelativeContext(v22);
              if ( *((_DWORD *)v23 + 499) != ValueW )
                CallStackContext::TraceFailure(v23, "CTranscodeEngine::_CreateIInitializeWithStream", 2011, ValueW);
            }
            if ( g_wppLevels )
            {
              v15 = 223;
              goto LABEL_30;
            }
          }
        }
        else
        {
          v20 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v20 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext(v20);
            if ( *((_DWORD *)v21 + 499) != ValueW )
              CallStackContext::TraceFailure(v21, "CTranscodeEngine::_CreateIInitializeWithStream", 2010, ValueW);
          }
          if ( g_wppLevels )
          {
            v15 = 222;
            goto LABEL_30;
          }
        }
      }
      else
      {
        v18 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v18 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext(v18);
          if ( *((_DWORD *)v19 + 499) != ValueW )
            CallStackContext::TraceFailure(v19, "CTranscodeEngine::_CreateIInitializeWithStream", 2009, ValueW);
        }
        if ( g_wppLevels )
        {
          v15 = 221;
          goto LABEL_30;
        }
      }
    }
    else
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
        if ( *((_DWORD *)v17 + 499) != ValueW )
          CallStackContext::TraceFailure(v17, "CTranscodeEngine::_CreateIInitializeWithStream", 2008, ValueW);
      }
      if ( g_wppLevels )
      {
        v15 = 220;
        goto LABEL_30;
      }
    }
  }
  else
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
      if ( *((_DWORD *)v14 + 499) != ValueW )
        CallStackContext::TraceFailure(v14, "CTranscodeEngine::_CreateIInitializeWithStream", 2007, ValueW);
    }
    if ( g_wppLevels )
    {
      v15 = 219;
LABEL_30:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        ValueW);
    }
  }
LABEL_72:
  if ( lpSubKey )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v35);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
}

```

## disassembly

```asm
0x18002e1bc  mov     [rsp-8+arg_10], rbx
0x18002e1c1  push    rbp
0x18002e1c2  push    rsi
0x18002e1c3  push    rdi
0x18002e1c4  push    r14
0x18002e1c6  push    r15
0x18002e1c8  lea     rbp, [rsp-1F0h]
0x18002e1d0  sub     rsp, 2F0h
0x18002e1d7  mov     rax, cs:__security_cookie
0x18002e1de  xor     rax, rsp
0x18002e1e1  mov     [rbp+210h+var_30], rax
0x18002e1e8  mov     rsi, rdx
0x18002e1eb  lea     r15, aCtranscodeengi_23; "CTranscodeEngine::_CreateIInitializeWit"...
0x18002e1f2  mov     rbx, rcx
0x18002e1f5  mov     rdx, r15; char *
0x18002e1f8  mov     r8d, 7B2h; int
0x18002e1fe  lea     rcx, [rsp+310h+var_2D0]; this
0x18002e203  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002e208  mov     rcx, [rbx+80h]
0x18002e20f  lea     r8, [rsp+310h+var_298]
0x18002e214  xor     r14d, r14d
0x18002e217  mov     [rsp+310h+var_2B0], 200h
0x18002e21f  xorps   xmm0, xmm0
0x18002e222  mov     [rsp+310h+var_298], r14
0x18002e227  mov     [rsp+310h+ppv], r14
0x18002e22c  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18002e233  mov     [rsp+310h+lpSubKey], r14
0x18002e238  mov     [rsp+310h+var_2CC], r14d
0x18002e23d  mov     [rsp+310h+hkey], r14
0x18002e242  mov     [rsp+310h+hKey], r14
0x18002e247  mov     [rsp+310h+var_2AC], 4Eh ; 'N'
0x18002e24f  movups  xmmword ptr [rbp+210h+iid.Data1], xmm0
0x18002e253  mov     rax, [rcx]
0x18002e256  mov     rax, [rax]
0x18002e259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e25e  test    eax, eax
0x18002e260  js      short loc_18002E28C
0x18002e262  mov     rcx, [rsp+310h+var_298]
0x18002e267  lea     r9, [rsp+310h+var_2CC]
0x18002e26c  lea     r8, [rsp+310h+lpSubKey]
0x18002e271  lea     rdx, MF_BYTESTREAM_CONTENT_TYPE
0x18002e278  mov     rax, [rcx]
0x18002e27b  mov     rax, [rax+68h]
0x18002e27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e284  test    eax, eax
0x18002e286  jns     loc_18002E3AE
0x18002e28c  mov     rcx, [rbx+0B0h]
0x18002e293  lea     rdx, [rsp+310h+var_2C8]
0x18002e298  mov     [rsp+310h+var_2C8], r14
0x18002e29d  mov     rax, [rcx]
0x18002e2a0  mov     rax, [rax+40h]
0x18002e2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2a9  mov     edi, eax
0x18002e2ab  test    eax, eax
0x18002e2ad  jns     short loc_18002E302
0x18002e2af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e2b6  test    rcx, rcx
0x18002e2b9  jnz     short loc_18002E2C7
0x18002e2bb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e2c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e2c7  cmp     [rcx+8], r14b
0x18002e2cb  jz      short loc_18002E2EE
0x18002e2cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e2d2  cmp     [rax+7CCh], edi
0x18002e2d8  jz      short loc_18002E2EE
0x18002e2da  mov     r9d, edi; int
0x18002e2dd  mov     r8d, 7CCh; int
0x18002e2e3  mov     rdx, r15; char *
0x18002e2e6  mov     rcx, rax; this
0x18002e2e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e2ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e2f5  jb      loc_18002E395
0x18002e2fb  mov     edx, 0D9h
0x18002e300  jmp     short loc_18002E377
0x18002e302  mov     rcx, [rsp+310h+var_2C8]
0x18002e307  lea     r9, [rsp+310h+var_2CC]
0x18002e30c  lea     r8, [rsp+310h+lpSubKey]
0x18002e311  lea     rdx, MF_PD_MIME_TYPE
0x18002e318  mov     rax, [rcx]
0x18002e31b  mov     rax, [rax+68h]
0x18002e31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e324  mov     edi, eax
0x18002e326  test    eax, eax
0x18002e328  jns     short loc_18002E3A4
0x18002e32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e331  test    rcx, rcx
0x18002e334  jnz     short loc_18002E342
0x18002e336  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e33b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e342  cmp     [rcx+8], r14b
0x18002e346  jz      short loc_18002E369
0x18002e348  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e34d  cmp     [rax+7CCh], edi
0x18002e353  jz      short loc_18002E369
0x18002e355  mov     r9d, edi; int
0x18002e358  mov     r8d, 7D0h; int
0x18002e35e  mov     rdx, r15; char *
0x18002e361  mov     rcx, rax; this
0x18002e364  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e369  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e370  jb      short loc_18002E395
0x18002e372  mov     edx, 0DAh
0x18002e377  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e37e  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x18002e385  mov     r9, rbx
0x18002e388  mov     dword ptr [rsp+310h+phkResult], edi
0x18002e38c  mov     rcx, [rcx+10h]
0x18002e390  call    WPP_SF_qd
0x18002e395  lea     rcx, [rsp+310h+var_2C8]
0x18002e39a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002e39f  jmp     loc_18002E6DF
0x18002e3a4  lea     rcx, [rsp+310h+var_2C8]
0x18002e3a9  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002e3ae  lea     rax, [rsp+310h+hkey]
0x18002e3b3  mov     r9d, 1; samDesired
0x18002e3b9  xor     r8d, r8d; ulOptions
0x18002e3bc  mov     [rsp+310h+phkResult], rax; phkResult
0x18002e3c1  lea     rdx, SubKey; "MIME\\Database\\Content Type"
0x18002e3c8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002e3cf  call    cs:__imp_RegOpenKeyExW
0x18002e3d5  mov     edi, eax
0x18002e3d7  test    eax, eax
0x18002e3d9  jns     short loc_18002E44F
0x18002e3db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e3e2  test    rcx, rcx
0x18002e3e5  jnz     short loc_18002E3F3
0x18002e3e7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e3ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e3f3  cmp     [rcx+8], r14b
0x18002e3f7  jz      short loc_18002E41A
0x18002e3f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e3fe  cmp     [rax+7CCh], edi
0x18002e404  jz      short loc_18002E41A
0x18002e406  mov     r9d, edi; int
0x18002e409  mov     r8d, 7D7h; int
0x18002e40f  mov     rdx, r15; char *
0x18002e412  mov     rcx, rax; this
0x18002e415  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e41a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e421  jb      loc_18002E6DF
0x18002e427  mov     edx, 0DBh
0x18002e42c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e433  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x18002e43a  mov     r9, rbx
0x18002e43d  mov     dword ptr [rsp+310h+phkResult], edi
0x18002e441  mov     rcx, [rcx+10h]
0x18002e445  call    WPP_SF_qd
0x18002e44a  jmp     loc_18002E6DF
0x18002e44f  mov     rdx, [rsp+310h+lpSubKey]; lpSubKey
0x18002e454  lea     rax, [rsp+310h+var_2B0]
0x18002e459  mov     rcx, [rsp+310h+hkey]; hkey
0x18002e45e  lea     r8, Value; "Extension"
0x18002e465  mov     [rsp+310h+pcbData], rax; pcbData
0x18002e46a  mov     r9d, 2; dwFlags
0x18002e470  lea     rax, [rbp+210h+SubKey]
0x18002e474  mov     [rsp+310h+pvData], rax; pvData
0x18002e479  mov     [rsp+310h+phkResult], r14; pdwType
0x18002e47e  call    cs:__imp_RegGetValueW
0x18002e484  mov     edi, eax
0x18002e486  test    eax, eax
0x18002e488  jns     short loc_18002E4E0
0x18002e48a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e491  test    rcx, rcx
0x18002e494  jnz     short loc_18002E4A2
0x18002e496  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e49b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e4a2  cmp     [rcx+8], r14b
0x18002e4a6  jz      short loc_18002E4C9
0x18002e4a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e4ad  cmp     [rax+7CCh], edi
0x18002e4b3  jz      short loc_18002E4C9
0x18002e4b5  mov     r9d, edi; int
0x18002e4b8  mov     r8d, 7D8h; int
0x18002e4be  mov     rdx, r15; char *
0x18002e4c1  mov     rcx, rax; this
0x18002e4c4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e4c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e4d0  jb      loc_18002E6DF
0x18002e4d6  mov     edx, 0DCh
0x18002e4db  jmp     loc_18002E42C
0x18002e4e0  lea     rax, [rsp+310h+hKey]
0x18002e4e5  mov     r9d, 1; samDesired
0x18002e4eb  xor     r8d, r8d; ulOptions
0x18002e4ee  mov     [rsp+310h+phkResult], rax; phkResult
0x18002e4f3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002e4fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e501  call    cs:__imp_RegOpenKeyExW
0x18002e507  mov     edi, eax
0x18002e509  test    eax, eax
0x18002e50b  jns     short loc_18002E563
0x18002e50d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e514  test    rcx, rcx
0x18002e517  jnz     short loc_18002E525
0x18002e519  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e51e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e525  cmp     [rcx+8], r14b
0x18002e529  jz      short loc_18002E54C
0x18002e52b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e530  cmp     [rax+7CCh], edi
0x18002e536  jz      short loc_18002E54C
0x18002e538  mov     r9d, edi; int
0x18002e53b  mov     r8d, 7D9h; int
0x18002e541  mov     rdx, r15; char *
0x18002e544  mov     rcx, rax; this
0x18002e547  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e54c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e553  jb      loc_18002E6DF
0x18002e559  mov     edx, 0DDh
0x18002e55e  jmp     loc_18002E42C
0x18002e563  mov     rcx, [rsp+310h+hKey]; hkey
0x18002e568  lea     rax, [rsp+310h+var_2AC]
0x18002e56d  mov     [rsp+310h+pcbData], rax; pcbData
0x18002e572  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18002e576  lea     rax, [rbp+210h+sz]
0x18002e57a  mov     r9d, 2; dwFlags
0x18002e580  mov     [rsp+310h+pvData], rax; pvData
0x18002e585  xor     r8d, r8d; lpValue
0x18002e588  mov     [rsp+310h+phkResult], r14; pdwType
0x18002e58d  call    cs:__imp_RegGetValueW
0x18002e593  mov     edi, eax
0x18002e595  test    eax, eax
0x18002e597  jns     short loc_18002E5EF
0x18002e599  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5a0  test    rcx, rcx
0x18002e5a3  jnz     short loc_18002E5B1
0x18002e5a5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e5aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e5b1  cmp     [rcx+8], r14b
0x18002e5b5  jz      short loc_18002E5D8
0x18002e5b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e5bc  cmp     [rax+7CCh], edi
0x18002e5c2  jz      short loc_18002E5D8
0x18002e5c4  mov     r9d, edi; int
0x18002e5c7  mov     r8d, 7DAh; int
0x18002e5cd  mov     rdx, r15; char *
0x18002e5d0  mov     rcx, rax; this
0x18002e5d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e5d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e5df  jb      loc_18002E6DF
0x18002e5e5  mov     edx, 0DEh
0x18002e5ea  jmp     loc_18002E42C
0x18002e5ef  lea     rdx, [rbp+210h+iid]; lpiid
0x18002e5f3  lea     rcx, [rbp+210h+sz]; lpsz
0x18002e5f7  call    cs:__imp_IIDFromString
0x18002e5fd  mov     edi, eax
0x18002e5ff  test    eax, eax
0x18002e601  jns     short loc_18002E659
0x18002e603  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e60a  test    rcx, rcx
0x18002e60d  jnz     short loc_18002E61B
0x18002e60f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e614  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e61b  cmp     [rcx+8], r14b
0x18002e61f  jz      short loc_18002E642
0x18002e621  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e626  cmp     [rax+7CCh], edi
0x18002e62c  jz      short loc_18002E642
0x18002e62e  mov     r9d, edi; int
0x18002e631  mov     r8d, 7DBh; int
0x18002e637  mov     rdx, r15; char *
0x18002e63a  mov     rcx, rax; this
0x18002e63d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e642  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e649  jb      loc_18002E6DF
0x18002e64f  mov     edx, 0DFh
0x18002e654  jmp     loc_18002E42C
0x18002e659  xor     edx, edx; pUnkOuter
0x18002e65b  lea     rax, [rsp+310h+ppv]
0x18002e660  lea     r9, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f; riid
0x18002e667  mov     [rsp+310h+phkResult], rax; ppv
0x18002e66c  lea     rcx, [rbp+210h+iid]; rclsid
0x18002e670  lea     r8d, [rdx+17h]; dwClsContext
0x18002e674  call    cs:__imp_CoCreateInstance
0x18002e67a  mov     edi, eax
0x18002e67c  test    eax, eax
0x18002e67e  jns     short loc_18002E6D2
0x18002e680  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e687  test    rcx, rcx
0x18002e68a  jnz     short loc_18002E698
0x18002e68c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e691  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002e698  cmp     [rcx+8], r14b
0x18002e69c  jz      short loc_18002E6BF
0x18002e69e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e6a3  cmp     [rax+7CCh], edi
0x18002e6a9  jz      short loc_18002E6BF
0x18002e6ab  mov     r9d, edi; int
0x18002e6ae  mov     r8d, 7DFh; int
0x18002e6b4  mov     rdx, r15; char *
0x18002e6b7  mov     rcx, rax; this
0x18002e6ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e6bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e6c6  jb      short loc_18002E6DF
0x18002e6c8  mov     edx, 0E0h
0x18002e6cd  jmp     loc_18002E42C
0x18002e6d2  mov     rax, [rsp+310h+ppv]
0x18002e6d7  mov     [rsi], rax
0x18002e6da  mov     [rsp+310h+ppv], r14
0x18002e6df  mov     rcx, [rsp+310h+lpSubKey]; pv
0x18002e6e4  test    rcx, rcx
  ... truncated ...
```
