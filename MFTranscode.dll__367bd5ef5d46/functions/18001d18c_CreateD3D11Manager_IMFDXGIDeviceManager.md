# CreateD3D11Manager(IMFDXGIDeviceManager * *)

- ea: `0x18001d18c`
- end: `0x18001d633`
- name: `?CreateD3D11Manager@@YAJPEAPEAUIMFDXGIDeviceManager@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(IMFDXGIDeviceManager **ppDeviceManager)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180023ea0`
- `0x18002676c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180017074`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18001ceb8`
- `0x18001d18c`
- `0x18001ea44`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d276`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d3e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d491`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d557`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d276`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d3e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d491`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d557`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x18001d3c9`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x18001d3c9`

## string_xrefs

- `0x18001d243`: `CreateD3D11Manager`

## pseudocode

```c
__int64 __fastcall CreateD3D11Manager(IMFDXGIDeviceManager **ppDeviceManager)
{
  IMFDXGIDeviceManager **v1; // r14
  IMFDXGIDeviceManager **v2; // rax
  unsigned int v3; // edx
  int v4; // eax
  int (__fastcall **v5)(_QWORD, __int64, _QWORD, __int64, char *, int, int, __int64 *, int *, _QWORD); // rsi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  HRESULT v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  unsigned int i; // ebx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v26[8]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v27; // [rsp+68h] [rbp-31h] BYREF
  UINT resetToken; // [rsp+70h] [rbp-29h] BYREF
  __int64 v29; // [rsp+78h] [rbp-21h] BYREF
  int v30; // [rsp+80h] [rbp-19h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-11h] BYREF
  __int64 v32; // [rsp+90h] [rbp-9h] BYREF
  __m128i si128; // [rsp+98h] [rbp-1h] BYREF
  int v34; // [rsp+A8h] [rbp+Fh]
  int v35; // [rsp+ACh] [rbp+13h]
  int v36; // [rsp+B0h] [rbp+17h]

  v1 = ppDeviceManager;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v34 = 37632;
  v35 = 37376;
  v36 = 37120;
  v30 = 0;
  resetToken = 0;
  v27 = 0;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  if ( !qword_18006A3C8 )
  {
    v2 = (IMFDXGIDeviceManager **)operator new(0x18u);
    ppDeviceManager = v2;
    if ( v2 )
    {
      *v2 = 0;
      v2[1] = 0;
      v2[2] = 0;
      if ( _InterlockedCompareExchange64(&qword_18006A3C8, (signed __int64)v2, 0) )
        DX11Lib::`scalar deleting destructor'((DX11Lib *)v2, v3);
    }
    if ( !qword_18006A3C8 )
      goto LABEL_7;
  }
  v4 = DX11Lib::Init((DX11Lib *)ppDeviceManager);
  v5 = (int (__fastcall **)(_QWORD, __int64, _QWORD, __int64, char *, int, int, __int64 *, int *, _QWORD))qword_18006A3C8;
  if ( !v4 )
LABEL_7:
    v5 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v26, "CreateD3D11Manager", 182);
  if ( v5 )
  {
    for ( i = 0; i < 7; ++i )
    {
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
      }
      if ( (*v5)(0, 1, 0, 2048, &si128.m128i_i8[4 * i], 1, 7, &v27, &v30, 0) >= 0 )
      {
        if ( v29 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
        }
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
               v27,
               &GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333,
               &v29) >= 0 )
          break;
      }
    }
    v8 = MFCreateDXGIDeviceManager(&resetToken, v1);
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, __int64, _QWORD))(*v1)->lpVtbl->ResetDevice)(
             *v1,
             v27,
             resetToken);
      if ( v8 >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v27 + 320LL))(
          v27,
          &v31);
        v8 = (**v31)(v31, &GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0, &v32);
        if ( v8 >= 0 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 40LL))(v32, 1);
          goto LABEL_62;
        }
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CreateD3D11Manager", 207, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 13;
          goto LABEL_19;
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v8 )
            CallStackContext::TraceFailure(v20, "CreateD3D11Manager", 203, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 12;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CreateD3D11Manager", 201, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 11;
        goto LABEL_19;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -1072875818;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -1072875818 )
        CallStackContext::TraceFailure(v10, "CreateD3D11Manager", 182, -1072875818);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 10;
LABEL_19:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, 0, v8);
    }
  }
LABEL_62:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v31);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v32);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v29);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d18c  push    rbp
0x18001d18e  push    rbx
0x18001d18f  push    rsi
0x18001d190  push    r12
0x18001d192  push    r14
0x18001d194  push    r15
0x18001d196  lea     rbp, [rsp-2Fh]
0x18001d19b  sub     rsp, 0C8h
0x18001d1a2  mov     rax, cs:__security_cookie
0x18001d1a9  xor     rax, rsp
0x18001d1ac  mov     [rbp+57h+var_38], rax
0x18001d1b0  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x18001d1b8  xor     r15d, r15d
0x18001d1bb  cmp     cs:qword_18006A3C8, r15
0x18001d1c2  mov     r14, rcx
0x18001d1c5  movdqu  [rbp+57h+var_58], xmm0
0x18001d1ca  mov     [rbp+57h+var_48], 9300h
0x18001d1d1  mov     [rbp+57h+var_44], 9200h
0x18001d1d8  mov     [rbp+57h+var_40], 9100h
0x18001d1df  mov     [rbp+57h+var_70], r15d
0x18001d1e3  mov     [rbp+57h+resetToken], r15d
0x18001d1e7  mov     [rbp+57h+var_88], r15
0x18001d1eb  mov     [rbp+57h+var_78], r15
0x18001d1ef  mov     [rbp+57h+var_60], r15
0x18001d1f3  mov     [rbp+57h+var_68], r15
0x18001d1f7  jnz     short loc_18001D230
0x18001d1f9  lea     ecx, [r15+18h]; Size
0x18001d1fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d202  mov     rcx, rax; this
0x18001d205  test    rax, rax
0x18001d208  jz      short loc_18001D227
0x18001d20a  mov     [rax], r15
0x18001d20d  mov     [rax+8], r15
0x18001d211  mov     [rax+10h], r15
0x18001d215  xor     eax, eax
0x18001d217  lock cmpxchg cs:qword_18006A3C8, rcx
0x18001d220  jz      short loc_18001D227
0x18001d222  call    ??_GDX11Lib@@QEAAPEAXI@Z; DX11Lib::`scalar deleting destructor'(uint)
0x18001d227  cmp     cs:qword_18006A3C8, r15
0x18001d22e  jz      short loc_18001D240
0x18001d230  call    ?Init@DX11Lib@@QEAAHXZ; DX11Lib::Init(void)
0x18001d235  mov     rsi, cs:qword_18006A3C8
0x18001d23c  test    eax, eax
0x18001d23e  jnz     short loc_18001D243
0x18001d240  mov     rsi, r15
0x18001d243  lea     r12, aCreated3d11man; "CreateD3D11Manager"
0x18001d24a  mov     r8d, 0B6h; int
0x18001d250  mov     rdx, r12; char *
0x18001d253  lea     rcx, [rbp+57h+var_90]; this
0x18001d257  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001d25c  test    rsi, rsi
0x18001d25f  jnz     loc_18001D313
0x18001d265  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d26c  mov     ebx, 0C00D36D6h
0x18001d271  test    rcx, rcx
0x18001d274  jnz     short loc_18001D2B7
0x18001d276  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d27c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d283  mov     rcx, rax
0x18001d286  test    rax, rax
0x18001d289  jz      short loc_18001D2A9
0x18001d28b  mov     rax, [rax]
0x18001d28e  mov     edx, 7F0h
0x18001d293  mov     rax, [rax+8]
0x18001d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d29c  test    eax, eax
0x18001d29e  jz      short loc_18001D2A9
0x18001d2a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d2a7  jmp     short loc_18001D2B7
0x18001d2a9  lea     rcx, qword_180069A90; this
0x18001d2b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d2b7  cmp     [rcx+8], r15b
0x18001d2bb  jz      short loc_18001D2DE
0x18001d2bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d2c2  cmp     [rax+7CCh], ebx
0x18001d2c8  jz      short loc_18001D2DE
0x18001d2ca  mov     r9d, ebx; int
0x18001d2cd  mov     r8d, 0B6h; int
0x18001d2d3  mov     rdx, r12; char *
0x18001d2d6  mov     rcx, rax; this
0x18001d2d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d2de  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d2e3  cmp     al, 1
0x18001d2e5  jb      loc_18001D5E7
0x18001d2eb  mov     edx, 0Ah
0x18001d2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2f7  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18001d2fe  xor     r9d, r9d
0x18001d301  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001d305  mov     rcx, [rcx+10h]
0x18001d309  call    WPP_SF_qd
0x18001d30e  jmp     loc_18001D5E7
0x18001d313  mov     ebx, r15d
0x18001d316  mov     rcx, [rbp+57h+var_88]
0x18001d31a  test    rcx, rcx
0x18001d31d  jz      short loc_18001D32F
0x18001d31f  mov     rax, [rcx]
0x18001d322  mov     rax, [rax+10h]
0x18001d326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d32b  mov     [rbp+57h+var_88], r15
0x18001d32f  mov     [rsp+0F0h+var_A8], r15
0x18001d334  lea     rcx, [rbp+57h+var_58]
0x18001d338  mov     eax, ebx
0x18001d33a  xor     r8d, r8d
0x18001d33d  mov     r9d, 800h
0x18001d343  lea     rcx, [rcx+rax*4]
0x18001d347  lea     rax, [rbp+57h+var_70]
0x18001d34b  mov     [rsp+0F0h+var_B0], rax
0x18001d350  lea     edx, [r8+1]
0x18001d354  lea     rax, [rbp+57h+var_88]
0x18001d358  mov     [rsp+0F0h+var_B8], rax
0x18001d35d  mov     rax, [rsi]
0x18001d360  mov     [rsp+0F0h+var_C0], 7
0x18001d368  mov     [rsp+0F0h+var_C8], 1
0x18001d370  mov     [rsp+0F0h+var_D0], rcx
0x18001d375  xor     ecx, ecx
0x18001d377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d37c  test    eax, eax
0x18001d37e  js      short loc_18001D3B7
0x18001d380  mov     rcx, [rbp+57h+var_78]
0x18001d384  test    rcx, rcx
0x18001d387  jz      short loc_18001D399
0x18001d389  mov     rax, [rcx]
0x18001d38c  mov     rax, [rax+10h]
0x18001d390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d395  mov     [rbp+57h+var_78], r15
0x18001d399  mov     rcx, [rbp+57h+var_88]
0x18001d39d  lea     r8, [rbp+57h+var_78]
0x18001d3a1  lea     rdx, _GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333
0x18001d3a8  mov     rax, [rcx]
0x18001d3ab  mov     rax, [rax]
0x18001d3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3b3  test    eax, eax
0x18001d3b5  jns     short loc_18001D3C2
0x18001d3b7  inc     ebx
0x18001d3b9  cmp     ebx, 7
0x18001d3bc  jb      loc_18001D316
0x18001d3c2  mov     rdx, r14; ppDeviceManager
0x18001d3c5  lea     rcx, [rbp+57h+resetToken]; resetToken
0x18001d3c9  call    cs:__imp_MFCreateDXGIDeviceManager
0x18001d3cf  mov     ebx, eax
0x18001d3d1  test    eax, eax
0x18001d3d3  jns     loc_18001D464
0x18001d3d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d3e0  test    rcx, rcx
0x18001d3e3  jnz     short loc_18001D426
0x18001d3e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d3eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d3f2  mov     rcx, rax
0x18001d3f5  test    rax, rax
0x18001d3f8  jz      short loc_18001D418
0x18001d3fa  mov     rax, [rax]
0x18001d3fd  mov     edx, 7F0h
0x18001d402  mov     rax, [rax+8]
0x18001d406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40b  test    eax, eax
0x18001d40d  jz      short loc_18001D418
0x18001d40f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d416  jmp     short loc_18001D426
0x18001d418  lea     rcx, qword_180069A90; this
0x18001d41f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d426  cmp     [rcx+8], r15b
0x18001d42a  jz      short loc_18001D44D
0x18001d42c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d431  cmp     [rax+7CCh], ebx
0x18001d437  jz      short loc_18001D44D
0x18001d439  mov     r9d, ebx; int
0x18001d43c  mov     r8d, 0C9h; int
0x18001d442  mov     rdx, r12; char *
0x18001d445  mov     rcx, rax; this
0x18001d448  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d44d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d452  cmp     al, 1
0x18001d454  jb      loc_18001D5E7
0x18001d45a  mov     edx, 0Bh
0x18001d45f  jmp     loc_18001D2F0
0x18001d464  mov     rcx, [r14]
0x18001d467  mov     r8d, [rbp+57h+resetToken]
0x18001d46b  mov     rdx, [rbp+57h+var_88]
0x18001d46f  mov     rax, [rcx]
0x18001d472  mov     rax, [rax+38h]
0x18001d476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d47b  mov     ebx, eax
0x18001d47d  test    eax, eax
0x18001d47f  jns     loc_18001D510
0x18001d485  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d48c  test    rcx, rcx
0x18001d48f  jnz     short loc_18001D4D2
0x18001d491  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d497  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d49e  mov     rcx, rax
0x18001d4a1  test    rax, rax
0x18001d4a4  jz      short loc_18001D4C4
0x18001d4a6  mov     rax, [rax]
0x18001d4a9  mov     edx, 7F0h
0x18001d4ae  mov     rax, [rax+8]
0x18001d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b7  test    eax, eax
0x18001d4b9  jz      short loc_18001D4C4
0x18001d4bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d4c2  jmp     short loc_18001D4D2
0x18001d4c4  lea     rcx, qword_180069A90; this
0x18001d4cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d4d2  cmp     [rcx+8], r15b
0x18001d4d6  jz      short loc_18001D4F9
0x18001d4d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d4dd  cmp     [rax+7CCh], ebx
0x18001d4e3  jz      short loc_18001D4F9
0x18001d4e5  mov     r9d, ebx; int
0x18001d4e8  mov     r8d, 0CBh; int
0x18001d4ee  mov     rdx, r12; char *
0x18001d4f1  mov     rcx, rax; this
0x18001d4f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d4f9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d4fe  cmp     al, 1
0x18001d500  jb      loc_18001D5E7
0x18001d506  mov     edx, 0Ch
0x18001d50b  jmp     loc_18001D2F0
0x18001d510  mov     rcx, [rbp+57h+var_88]
0x18001d514  lea     rdx, [rbp+57h+var_68]
0x18001d518  mov     rax, [rcx]
0x18001d51b  mov     rax, [rax+140h]
0x18001d522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d527  mov     rcx, [rbp+57h+var_68]
0x18001d52b  lea     r8, [rbp+57h+var_60]
0x18001d52f  lea     rdx, _GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0
0x18001d536  mov     rax, [rcx]
0x18001d539  mov     rax, [rax]
0x18001d53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d541  mov     ebx, eax
0x18001d543  test    eax, eax
0x18001d545  jns     loc_18001D5D2
0x18001d54b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d552  test    rcx, rcx
0x18001d555  jnz     short loc_18001D598
0x18001d557  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d55d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d564  mov     rcx, rax
0x18001d567  test    rax, rax
0x18001d56a  jz      short loc_18001D58A
0x18001d56c  mov     rax, [rax]
0x18001d56f  mov     edx, 7F0h
0x18001d574  mov     rax, [rax+8]
0x18001d578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d57d  test    eax, eax
0x18001d57f  jz      short loc_18001D58A
0x18001d581  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d588  jmp     short loc_18001D598
0x18001d58a  lea     rcx, qword_180069A90; this
0x18001d591  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d598  cmp     [rcx+8], r15b
0x18001d59c  jz      short loc_18001D5BF
0x18001d59e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d5a3  cmp     [rax+7CCh], ebx
0x18001d5a9  jz      short loc_18001D5BF
0x18001d5ab  mov     r9d, ebx; int
0x18001d5ae  mov     r8d, 0CFh; int
0x18001d5b4  mov     rdx, r12; char *
0x18001d5b7  mov     rcx, rax; this
0x18001d5ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d5bf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d5c4  cmp     al, 1
0x18001d5c6  jb      short loc_18001D5E7
0x18001d5c8  mov     edx, 0Dh
0x18001d5cd  jmp     loc_18001D2F0
0x18001d5d2  mov     rcx, [rbp+57h+var_60]
0x18001d5d6  mov     edx, 1
0x18001d5db  mov     rax, [rcx]
0x18001d5de  mov     rax, [rax+28h]
0x18001d5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5e7  lea     rcx, [rbp+57h+var_90]; this
0x18001d5eb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001d5f0  lea     rcx, [rbp+57h+var_68]
0x18001d5f4  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001d5f9  lea     rcx, [rbp+57h+var_60]
0x18001d5fd  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001d602  lea     rcx, [rbp+57h+var_78]
0x18001d606  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001d60b  lea     rcx, [rbp+57h+var_88]
0x18001d60f  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001d614  mov     eax, ebx
0x18001d616  mov     rcx, [rbp+57h+var_38]
0x18001d61a  xor     rcx, rsp; StackCookie
0x18001d61d  call    __security_check_cookie
0x18001d622  add     rsp, 0C8h
0x18001d629  pop     r15
0x18001d62b  pop     r14
0x18001d62d  pop     r12
0x18001d62f  pop     rsi
0x18001d630  pop     rbx
0x18001d631  pop     rbp
0x18001d632  retn
```
