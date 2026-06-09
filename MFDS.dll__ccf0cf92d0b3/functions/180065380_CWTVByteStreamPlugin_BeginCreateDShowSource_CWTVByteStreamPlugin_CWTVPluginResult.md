# CWTVByteStreamPlugin::BeginCreateDShowSource(CWTVByteStreamPlugin::CWTVPluginResult *)

- ea: `0x180065380`
- end: `0x1800657f0`
- name: `?BeginCreateDShowSource@CWTVByteStreamPlugin@@AEAAJPEAVCWTVPluginResult@1@@Z`
- size: `1136`
- prototype: `__int64 __fastcall(CWTVByteStreamPlugin *__hidden this, struct CWTVByteStreamPlugin::CWTVPluginResult *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005069c`

## callees

- `0x1800140b0`
- `0x180032a50`
- `0x180065380`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x1800653ab`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x1800653ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800653e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800653e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800657d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800657d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800653ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800654a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065551`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065621`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800656e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006575f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800653ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800654a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065551`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065621`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800656e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006575f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180065487`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180065487`

## string_xrefs

- `0x1800657c2`: `CWTVByteStreamPlugin::BeginCreateDShowSource`

## pseudocode

```c
__int64 __fastcall CWTVByteStreamPlugin::BeginCreateDShowSource(
        CWTVByteStreamPlugin *this,
        struct CWTVByteStreamPlugin::CWTVPluginResult *a2)
{
  _QWORD *v4; // r14
  HRESULT Instance; // ebx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v9; // r8d
  _QWORD *v10; // rsi
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  __int64 v13; // rcx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  __int64 v18; // rdx
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  PROPVARIANT pvar; // [rsp+50h] [rbp-48h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  memset(&pvar, 0, sizeof(pvar));
  v4 = (_QWORD *)((char *)this + 160);
  if ( *((_QWORD *)this + 20)
    || (Instance = CoCreateInstance(
                     &CLSID_DShowSourceResolver,
                     0,
                     1u,
                     &GUID_fbe5a32d_a497_4b61_bb85_97b1a848a6e3,
                     (LPVOID *)this + 20),
        Instance >= 0) )
  {
    v10 = (_QWORD *)((char *)a2 + 136);
    if ( *((_QWORD *)a2 + 17)
      || (Instance = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)a2 + 17),
          Instance >= 0) )
    {
      v13 = *v10;
      pvar.lVal = 1;
      pvar.vt = 22;
      Instance = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v13 + 48LL))(
                   v13,
                   &MFPKEY_SBESourceMode,
                   &pvar);
      if ( Instance >= 0 )
      {
        if ( *((_DWORD *)a2 + 40) == 2 )
        {
          v18 = *((_QWORD *)a2 + 15);
          if ( v18 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, char *, char *, struct CWTVByteStreamPlugin::CWTVPluginResult *))(*(_QWORD *)*v4 + 40LL))(
                         *v4,
                         v18,
                         *((unsigned int *)a2 + 32),
                         *v10,
                         (char *)a2 + 144,
                         (char *)this + 112,
                         a2);
            if ( Instance < 0 )
            {
              v19 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v20;
                if ( v20
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
                {
                  v19 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v19 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v19 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
                {
                  v9 = 329;
                  goto LABEL_58;
                }
              }
            }
          }
          else
          {
            v21 = CallStackTracing::s_wpInstance;
            Instance = -1072875836;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
              {
                v21 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v21 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v21);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875836 )
              {
                v9 = 333;
                goto LABEL_58;
              }
            }
          }
        }
        else
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *, char *, struct CWTVByteStreamPlugin::CWTVPluginResult *))(*(_QWORD *)*v4 + 56LL))(
                       *v4,
                       *((_QWORD *)a2 + 14),
                       *((_QWORD *)a2 + 15),
                       *((unsigned int *)a2 + 32),
                       *v10,
                       (char *)a2 + 144,
                       (char *)this + 112,
                       a2);
          if ( Instance < 0 )
          {
            v16 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v17;
              if ( v17
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
              {
                v16 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v16 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v16 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
              {
                v9 = 320;
                goto LABEL_58;
              }
            }
          }
        }
      }
      else
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
          {
            v9 = 309;
            goto LABEL_58;
          }
        }
      }
    }
    else
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
        {
          v9 = 301;
          goto LABEL_58;
        }
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
      {
        v9 = 292;
LABEL_58:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWTVByteStreamPlugin::BeginCreateDShowSource",
          v9,
          Instance);
      }
    }
  }
  PropVariantClear(&pvar);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180065380  push    rbx
0x180065382  push    rbp
0x180065383  push    rsi
0x180065384  push    rdi
0x180065385  push    r14
0x180065387  sub     rsp, 70h
0x18006538b  xor     eax, eax
0x18006538d  mov     rdi, rdx
0x180065390  mov     rbp, rcx
0x180065393  mov     qword ptr [rsp+98h+pvar+10h], rax
0x180065398  xorps   xmm0, xmm0
0x18006539b  lea     rcx, [rsp+98h+pvar]; void *
0x1800653a0  xor     edx, edx; Val
0x1800653a2  lea     r8d, [rax+18h]; Size
0x1800653a6  movups  xmmword ptr [rsp+98h+pvar], xmm0
0x1800653ab  call    cs:__imp_memset
0x1800653b2  nop     dword ptr [rax+rax+00h]
0x1800653b7  lea     r14, [rbp+0A0h]
0x1800653be  cmp     qword ptr [r14], 0
0x1800653c2  jnz     loc_18006546C
0x1800653c8  xor     edx, edx; pUnkOuter
0x1800653ca  mov     [rsp+98h+ppv], r14; ppv
0x1800653cf  lea     r9, _GUID_fbe5a32d_a497_4b61_bb85_97b1a848a6e3; riid
0x1800653d6  lea     rcx, CLSID_DShowSourceResolver; rclsid
0x1800653dd  lea     r8d, [rdx+1]; dwClsContext
0x1800653e1  call    cs:__imp_CoCreateInstance
0x1800653e8  nop     dword ptr [rax+rax+00h]
0x1800653ed  mov     ebx, eax
0x1800653ef  test    eax, eax
0x1800653f1  jns     short loc_18006546C
0x1800653f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800653fa  test    rcx, rcx
0x1800653fd  jnz     short loc_180065446
0x1800653ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065406  nop     dword ptr [rax+rax+00h]
0x18006540b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065412  mov     rcx, rax
0x180065415  test    rax, rax
0x180065418  jz      short loc_180065438
0x18006541a  mov     rax, [rax]
0x18006541d  mov     edx, 7F0h
0x180065422  mov     rax, [rax+8]
0x180065426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006542b  test    eax, eax
0x18006542d  jz      short loc_180065438
0x18006542f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065436  jmp     short loc_180065446
0x180065438  lea     rcx, qword_1800EB130; this
0x18006543f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065446  cmp     byte ptr [rcx+8], 0
0x18006544a  jz      loc_1800657D1
0x180065450  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065455  cmp     [rax+7CCh], ebx
0x18006545b  jz      loc_1800657D1
0x180065461  mov     r8d, 124h
0x180065467  jmp     loc_1800657BF
0x18006546c  lea     rsi, [rdi+88h]
0x180065473  cmp     qword ptr [rsi], 0
0x180065477  jnz     loc_180065512
0x18006547d  mov     rdx, rsi; ppv
0x180065480  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180065487  call    cs:__imp_PSCreateMemoryPropertyStore
0x18006548e  nop     dword ptr [rax+rax+00h]
0x180065493  mov     ebx, eax
0x180065495  test    eax, eax
0x180065497  jns     short loc_180065512
0x180065499  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654a0  test    rcx, rcx
0x1800654a3  jnz     short loc_1800654EC
0x1800654a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800654ac  nop     dword ptr [rax+rax+00h]
0x1800654b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654b8  mov     rcx, rax
0x1800654bb  test    rax, rax
0x1800654be  jz      short loc_1800654DE
0x1800654c0  mov     rax, [rax]
0x1800654c3  mov     edx, 7F0h
0x1800654c8  mov     rax, [rax+8]
0x1800654cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654d1  test    eax, eax
0x1800654d3  jz      short loc_1800654DE
0x1800654d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654dc  jmp     short loc_1800654EC
0x1800654de  lea     rcx, qword_1800EB130; this
0x1800654e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800654ec  cmp     byte ptr [rcx+8], 0
0x1800654f0  jz      loc_1800657D1
0x1800654f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800654fb  cmp     [rax+7CCh], ebx
0x180065501  jz      loc_1800657D1
0x180065507  mov     r8d, 12Dh
0x18006550d  jmp     loc_1800657BF
0x180065512  mov     rcx, [rsi]
0x180065515  lea     r8, [rsp+98h+pvar]
0x18006551a  mov     eax, 16h
0x18006551f  mov     dword ptr [rsp+98h+pvar+8], 1
0x180065527  mov     word ptr [rsp+98h+pvar], ax
0x18006552c  lea     rdx, MFPKEY_SBESourceMode
0x180065533  mov     rax, [rcx]
0x180065536  mov     rax, [rax+30h]
0x18006553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006553f  mov     ebx, eax
0x180065541  test    eax, eax
0x180065543  jns     short loc_1800655BE
0x180065545  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006554c  test    rcx, rcx
0x18006554f  jnz     short loc_180065598
0x180065551  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065558  nop     dword ptr [rax+rax+00h]
0x18006555d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065564  mov     rcx, rax
0x180065567  test    rax, rax
0x18006556a  jz      short loc_18006558A
0x18006556c  mov     rax, [rax]
0x18006556f  mov     edx, 7F0h
0x180065574  mov     rax, [rax+8]
0x180065578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006557d  test    eax, eax
0x18006557f  jz      short loc_18006558A
0x180065581  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065588  jmp     short loc_180065598
0x18006558a  lea     rcx, qword_1800EB130; this
0x180065591  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065598  cmp     byte ptr [rcx+8], 0
0x18006559c  jz      loc_1800657D1
0x1800655a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800655a7  cmp     [rax+7CCh], ebx
0x1800655ad  jz      loc_1800657D1
0x1800655b3  mov     r8d, 135h
0x1800655b9  jmp     loc_1800657BF
0x1800655be  cmp     dword ptr [rdi+0A0h], 2
0x1800655c5  jz      loc_18006568E
0x1800655cb  mov     rcx, [r14]
0x1800655ce  lea     rdx, [rbp+70h]
0x1800655d2  mov     r9d, [rdi+80h]
0x1800655d9  lea     r8, [rdi+90h]
0x1800655e0  mov     [rsp+98h+var_60], rdi
0x1800655e5  mov     [rsp+98h+var_68], rdx
0x1800655ea  mov     rdx, [rsi]
0x1800655ed  mov     rax, [rcx]
0x1800655f0  mov     [rsp+98h+var_70], r8
0x1800655f5  mov     r8, [rdi+78h]
0x1800655f9  mov     [rsp+98h+ppv], rdx
0x1800655fe  mov     rax, [rax+38h]
0x180065602  mov     rdx, [rdi+70h]
0x180065606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006560b  mov     ebx, eax
0x18006560d  test    eax, eax
0x18006560f  jns     loc_1800657D1
0x180065615  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006561c  test    rcx, rcx
0x18006561f  jnz     short loc_180065668
0x180065621  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065628  nop     dword ptr [rax+rax+00h]
0x18006562d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065634  mov     rcx, rax
0x180065637  test    rax, rax
0x18006563a  jz      short loc_18006565A
0x18006563c  mov     rax, [rax]
0x18006563f  mov     edx, 7F0h
0x180065644  mov     rax, [rax+8]
0x180065648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006564d  test    eax, eax
0x18006564f  jz      short loc_18006565A
0x180065651  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065658  jmp     short loc_180065668
0x18006565a  lea     rcx, qword_1800EB130; this
0x180065661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065668  cmp     byte ptr [rcx+8], 0
0x18006566c  jz      loc_1800657D1
0x180065672  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065677  cmp     [rax+7CCh], ebx
0x18006567d  jz      loc_1800657D1
0x180065683  mov     r8d, 140h
0x180065689  jmp     loc_1800657BF
0x18006568e  mov     rdx, [rdi+78h]
0x180065692  test    rdx, rdx
0x180065695  jz      loc_18006574E
0x18006569b  mov     rcx, [r14]
0x18006569e  lea     r8, [rbp+70h]
0x1800656a2  mov     r9, [rsi]
0x1800656a5  lea     r10, [rdi+90h]
0x1800656ac  mov     [rsp+98h+var_68], rdi
0x1800656b1  mov     [rsp+98h+var_70], r8
0x1800656b6  mov     rax, [rcx]
0x1800656b9  mov     r8d, [rdi+80h]
0x1800656c0  mov     [rsp+98h+ppv], r10
0x1800656c5  mov     rax, [rax+28h]
0x1800656c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656ce  mov     ebx, eax
0x1800656d0  test    eax, eax
0x1800656d2  jns     loc_1800657D1
0x1800656d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800656df  test    rcx, rcx
0x1800656e2  jnz     short loc_18006572B
0x1800656e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800656eb  nop     dword ptr [rax+rax+00h]
0x1800656f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800656f7  mov     rcx, rax
0x1800656fa  test    rax, rax
0x1800656fd  jz      short loc_18006571D
0x1800656ff  mov     rax, [rax]
0x180065702  mov     edx, 7F0h
0x180065707  mov     rax, [rax+8]
0x18006570b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065710  test    eax, eax
0x180065712  jz      short loc_18006571D
0x180065714  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006571b  jmp     short loc_18006572B
0x18006571d  lea     rcx, qword_1800EB130; this
0x180065724  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006572b  cmp     byte ptr [rcx+8], 0
0x18006572f  jz      loc_1800657D1
0x180065735  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006573a  cmp     [rax+7CCh], ebx
0x180065740  jz      loc_1800657D1
0x180065746  mov     r8d, 149h
0x18006574c  jmp     short loc_1800657BF
0x18006574e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065755  mov     ebx, 0C00D36C4h
0x18006575a  test    rcx, rcx
0x18006575d  jnz     short loc_1800657A6
0x18006575f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065766  nop     dword ptr [rax+rax+00h]
0x18006576b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065772  mov     rcx, rax
0x180065775  test    rax, rax
0x180065778  jz      short loc_180065798
0x18006577a  mov     rax, [rax]
0x18006577d  mov     edx, 7F0h
0x180065782  mov     rax, [rax+8]
0x180065786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006578b  test    eax, eax
0x18006578d  jz      short loc_180065798
0x18006578f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065796  jmp     short loc_1800657A6
0x180065798  lea     rcx, qword_1800EB130; this
0x18006579f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800657a6  cmp     byte ptr [rcx+8], 0
0x1800657aa  jz      short loc_1800657D1
0x1800657ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800657b1  cmp     [rax+7CCh], ebx
0x1800657b7  jz      short loc_1800657D1
0x1800657b9  mov     r8d, 14Dh; int
0x1800657bf  mov     r9d, ebx; int
0x1800657c2  lea     rdx, aCwtvbytestream_2; "CWTVByteStreamPlugin::BeginCreateDShowS"...
0x1800657c9  mov     rcx, rax; this
0x1800657cc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800657d1  lea     rcx, [rsp+98h+pvar]; pvar
0x1800657d6  call    cs:__imp_PropVariantClear
0x1800657dd  nop     dword ptr [rax+rax+00h]
0x1800657e2  mov     eax, ebx
0x1800657e4  add     rsp, 70h
0x1800657e8  pop     r14
0x1800657ea  pop     rdi
0x1800657eb  pop     rsi
0x1800657ec  pop     rbp
0x1800657ed  pop     rbx
0x1800657ee  retn
```
