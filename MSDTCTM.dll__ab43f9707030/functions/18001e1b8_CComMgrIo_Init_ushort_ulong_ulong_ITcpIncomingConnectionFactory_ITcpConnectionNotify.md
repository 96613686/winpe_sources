# CComMgrIo::Init(ushort,ulong,ulong,ITcpIncomingConnectionFactory *,ITcpConnectionNotify *)

- ea: `0x18001e1b8`
- end: `0x18001e606`
- name: `?Init@CComMgrIo@@QEAAJGKKPEAUITcpIncomingConnectionFactory@@PEAUITcpConnectionNotify@@@Z`
- size: `1102`
- prototype: `__int64 __fastcall(CComMgrIo *__hidden this, unsigned __int16, unsigned int, unsigned int, struct ITcpIncomingConnectionFactory *, struct ITcpConnectionNotify *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b5430`

## callees

- `0x1800063b0`
- `0x180018d14`
- `0x18001e1b8`
- `0x18001e60c`
- `0x18002003c`
- `0x1800240fc`
- `0x1800249ec`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5de`
- `WS2_32!getaddrinfo` at `0x18001e372`
- `WS2_32!getaddrinfo` at `0x18001e372`
- `WS2_32!__imp_WSAGetLastError` at `0x18001e37c`
- `WS2_32!__imp_WSAGetLastError` at `0x18001e37c`
- `WS2_32!__imp_WSAStartup` at `0x18001e2e0`
- `WS2_32!__imp_WSAStartup` at `0x18001e2e0`
- `WS2_32!__imp_WSACleanup` at `0x18001e584`
- `WS2_32!__imp_WSACleanup` at `0x18001e584`

## string_xrefs

- `0x18001e2b3`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`
- `0x18001e30c`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`
- `0x18001e41e`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`
- `0x18001e5c0`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`
- `0x18001e2a1`: `CComMgrIo::Init`
- `0x18001e2fa`: `CComMgrIo::Init`
- `0x18001e40c`: `CComMgrIo::Init`
- `0x18001e5b4`: `CComMgrIo::Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CComMgrIo::Init(
        CComMgrIo *this,
        unsigned __int16 a2,
        __int64 a3,
        int a4,
        struct ITcpIncomingConnectionFactory *a5,
        struct ITcpConnectionNotify *a6)
{
  char *v7; // r15
  int Error; // edi
  char *v9; // r12
  const wchar_t *v10; // rax
  __int64 v11; // r9
  int v12; // eax
  int v13; // eax
  __int64 *v14; // rbx
  __int64 v15; // rax
  int v16; // ecx
  void *v17; // rax
  __int64 i; // rdx
  struct ITcpConnectionNotify *v19; // rbx
  unsigned __int64 v20; // r12
  __int64 v21; // rax
  bool v22; // cf
  size_t v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rbx
  unsigned int j; // r12d
  __int64 v27; // rbx
  __int64 v29; // [rsp+28h] [rbp-71h]
  char *v30; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  struct ITcpConnectionNotify *v32; // [rsp+50h] [rbp-49h]
  ADDRINFOA pHints; // [rsp+58h] [rbp-41h] BYREF
  CHAR pServiceName[8]; // [rsp+88h] [rbp-11h] BYREF

  v32 = a6;
  memset(&pHints, 0, sizeof(pHints));
  pv = 0;
  v7 = 0;
  v30 = 0;
  *(_WORD *)this = a2;
  *((_DWORD *)this + 1) = a4;
  if ( !a2 )
  {
    CComMgrIo::Finalize(this);
    Error = -2147418113;
    v10 = L"Unexpected Port Number";
    v11 = 404;
    goto LABEL_37;
  }
  TracedStringCchPrintfA(pServiceName, 6u, "%d", a2);
  pServiceName[5] = 0;
  if ( g_szTipTMHostname )
  {
    Error = 0;
    v9 = &g_szTipTMHostname;
    goto LABEL_9;
  }
  Error = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)g_pTipTmInstance + 40LL))(
            g_pTipTmInstance,
            &pv);
  if ( Error < 0 )
  {
    v10 = L"Failed to get host name from TM instance";
    v11 = 421;
LABEL_37:
    LODWORD(v29) = Error;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\commgrio.cpp",
      v11,
      L"CComMgrIo::Init",
      v29,
      v10);
    goto LABEL_38;
  }
  v12 = DuplicateString((LPCWCH)pv, &v30);
  Error = v12;
  if ( v12 < 0 )
  {
    LODWORD(v29) = v12;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\commgrio.cpp",
      430,
      L"CComMgrIo::Init",
      v29,
      L"Failed to convert host name to ANSI");
    v7 = v30;
    goto LABEL_38;
  }
  v7 = v30;
  v9 = v30;
LABEL_9:
  v13 = WSAStartup(2u, (LPWSADATA)((char *)this + 8));
  if ( v13 )
  {
    LODWORD(v29) = v13;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\commgrio.cpp",
      442,
      L"CComMgrIo::Init",
      v29,
      L"Failed to start Winsock runtime libraries.");
LABEL_11:
    Error = -2147418113;
    goto LABEL_38;
  }
  if ( *((_BYTE *)this + 8) < 2u )
  {
    WSACleanup();
    goto LABEL_11;
  }
  memset(&pHints.ai_addrlen, 0, 32);
  pHints.ai_family = 0;
  pHints.ai_socktype = 1;
  pHints.ai_flags = 1;
  pHints.ai_protocol = 6;
  v14 = (__int64 *)((char *)this + 424);
  if ( getaddrinfo(v9, pServiceName, &pHints, (PADDRINFOA *)this + 53) )
  {
    Error = WSAGetLastError();
    CComMgrIo::Finalize(this);
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
  }
  else
  {
    v15 = *v14;
    *((_QWORD *)this + 52) = *v14;
    if ( v15 )
    {
      v16 = *((_DWORD *)this + 108);
      do
      {
        *((_DWORD *)this + 108) = ++v16;
        v15 = *(_QWORD *)(v15 + 40);
      }
      while ( v15 );
    }
    v17 = operator new[](saturated_mul(*((unsigned int *)this + 108), 8u));
    *((_QWORD *)this + 55) = v17;
    if ( v17 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 108); i = (unsigned int)(i + 1) )
        *(_QWORD *)(*((_QWORD *)this + 55) + 8 * i) = -1;
      (*(void (__fastcall **)(struct ITcpIncomingConnectionFactory *))(*(_QWORD *)a5 + 8LL))(a5);
      *((_QWORD *)this + 56) = a5;
      v19 = v32;
      (*(void (__fastcall **)(struct ITcpConnectionNotify *))(*(_QWORD *)v32 + 8LL))(v32);
      *((_QWORD *)this + 57) = v19;
      v20 = *((unsigned int *)this + 108);
      v21 = 464 * v20;
      if ( !is_mul_ok(v20, 0x1D0u) )
        v21 = -1;
      v22 = __CFADD__(v21, 8);
      v23 = v21 + 8;
      if ( v22 )
        v23 = -1;
      v24 = operator new[](v23);
      v32 = (struct ITcpConnectionNotify *)v24;
      if ( v24 )
      {
        *v24 = v20;
        v25 = v24 + 1;
        `eh vector constructor iterator'(
          v24 + 1,
          0x1D0u,
          (unsigned int)v20,
          (void (*)(void *))CTcpCCB::CTcpCCB,
          (void (*)(void *))CTcpCCB::~CTcpCCB);
      }
      else
      {
        v25 = 0;
      }
      *((_QWORD *)this + 58) = v25;
      if ( v25 )
      {
        for ( j = 0; j < *((_DWORD *)this + 108); ++j )
        {
          v27 = *((_QWORD *)this + 58) + 464LL * j;
          Error = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v27)(v27, &IID_ICompletion, v27 + 48);
          *(_DWORD *)(v27 + 56) = 0;
          memset_0((void *)(v27 + 112), 0, 0x120u);
        }
      }
      else
      {
        Error = -2147024882;
        LODWORD(v29) = -2147024882;
        TraceStringInline(
          10,
          1,
          L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\commgrio.cpp",
          519,
          L"CComMgrIo::Init",
          v29,
          L"Failed to allocate memory for connection control block set.");
      }
    }
    else
    {
      Error = -2147024882;
      LODWORD(v29) = -2147024882;
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\commgrio.cpp",
        491,
        L"CComMgrIo::Init",
        v29,
        L"Failed to allocate memory for listener sockets");
      CComMgrIo::Finalize(this);
    }
  }
LABEL_38:
  CoTaskMemFree(pv);
  CoTaskMemFree(v7);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001e1b8  push    rbp
0x18001e1ba  push    rbx
0x18001e1bb  push    rsi
0x18001e1bc  push    rdi
0x18001e1bd  push    r12
0x18001e1bf  push    r13
0x18001e1c1  push    r14
0x18001e1c3  push    r15
0x18001e1c5  lea     rbp, [rsp-0Fh]
0x18001e1ca  sub     rsp, 0A8h
0x18001e1d1  mov     rax, cs:__security_cookie
0x18001e1d8  xor     rax, rsp
0x18001e1db  mov     [rbp+47h+var_50], rax
0x18001e1df  mov     rsi, rcx
0x18001e1e2  mov     r13, [rbp+47h+arg_20]
0x18001e1e6  mov     rax, [rbp+47h+arg_28]
0x18001e1ea  mov     [rbp+47h+var_90], rax
0x18001e1ee  xorps   xmm0, xmm0
0x18001e1f1  movups  xmmword ptr [rbp+47h+pHints.ai_flags], xmm0
0x18001e1f5  movups  xmmword ptr [rbp+47h+pHints.ai_addrlen], xmm0
0x18001e1f9  movups  xmmword ptr [rbp+47h+pHints.ai_addr], xmm0
0x18001e1fd  xor     r14d, r14d
0x18001e200  mov     [rbp+47h+pv], r14
0x18001e204  mov     r15d, r14d
0x18001e207  mov     [rbp+47h+var_A0], r14
0x18001e20b  mov     [rcx], dx
0x18001e20e  mov     [rcx+4], r9d
0x18001e212  test    dx, dx
0x18001e215  jz      loc_18001E58F
0x18001e21b  movzx   r9d, dx
0x18001e21f  lea     r8, aD; "%d"
0x18001e226  lea     edx, [r14+6]; unsigned __int64
0x18001e22a  lea     rcx, [rbp+47h+pServiceName]; char *
0x18001e22e  call    ?TracedStringCchPrintfA@@YAXPEAD_KPEBDZZ; TracedStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001e233  mov     [rbp+47h+var_53], r14b
0x18001e237  cmp     cs:?g_szTipTMHostname@@3PADA, r14b; char near * g_szTipTMHostname
0x18001e23e  jz      short loc_18001E24F
0x18001e240  mov     edi, r14d
0x18001e243  lea     r12, ?g_szTipTMHostname@@3PADA; char near * g_szTipTMHostname
0x18001e24a  jmp     loc_18001E2D7
0x18001e24f  mov     rcx, cs:?g_pTipTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pTipTmInstance
0x18001e256  mov     rax, [rcx]
0x18001e259  lea     rdx, [rbp+47h+pv]
0x18001e25d  mov     rax, [rax+28h]
0x18001e261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e266  mov     edi, eax
0x18001e268  test    eax, eax
0x18001e26a  jns     short loc_18001E27E
0x18001e26c  lea     rax, aFailedToGetHos; "Failed to get host name from TM instanc"...
0x18001e273  mov     r9d, 1A5h
0x18001e279  jmp     loc_18001E5A6
0x18001e27e  lea     rdx, [rbp+47h+var_A0]; char **
0x18001e282  mov     rcx, [rbp+47h+pv]; lpWideCharStr
0x18001e286  call    ?DuplicateString@@YAJPEBGPEAPEAD@Z; DuplicateString(ushort const *,char * *)
0x18001e28b  mov     edi, eax
0x18001e28d  test    eax, eax
0x18001e28f  jns     short loc_18001E2D0
0x18001e291  lea     rax, aFailedToConver; "Failed to convert host name to ANSI"
0x18001e298  mov     [rsp+0E0h+var_B0], rax
0x18001e29d  mov     dword ptr [rsp+0E0h+var_B8], edi
0x18001e2a1  lea     rax, aCcommgrioInit; "CComMgrIo::Init"
0x18001e2a8  mov     [rsp+0E0h+var_C0], rax
0x18001e2ad  mov     r9d, 1AEh
0x18001e2b3  lea     r8, aComComplusDtcD_89; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001e2ba  mov     edx, 1
0x18001e2bf  lea     ecx, [rdx+9]
0x18001e2c2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e2c7  mov     r15, [rbp+47h+var_A0]
0x18001e2cb  jmp     loc_18001E5D1
0x18001e2d0  mov     r15, [rbp+47h+var_A0]
0x18001e2d4  mov     r12, r15
0x18001e2d7  mov     ecx, 2; wVersionRequested
0x18001e2dc  lea     rdx, [rsi+8]; lpWSAData
0x18001e2e0  call    cs:__imp_WSAStartup
0x18001e2e6  test    eax, eax
0x18001e2e8  jz      short loc_18001E32A
0x18001e2ea  lea     rcx, aFailedToStartW; "Failed to start Winsock runtime librari"...
0x18001e2f1  mov     [rsp+0E0h+var_B0], rcx
0x18001e2f6  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001e2fa  lea     rax, aCcommgrioInit; "CComMgrIo::Init"
0x18001e301  mov     [rsp+0E0h+var_C0], rax
0x18001e306  mov     r9d, 1BAh
0x18001e30c  lea     r8, aComComplusDtcD_89; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001e313  mov     edx, 1
0x18001e318  lea     ecx, [rdx+9]
0x18001e31b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e320  mov     edi, 8000FFFFh
0x18001e325  jmp     loc_18001E5D1
0x18001e32a  cmp     byte ptr [rsi+8], 2
0x18001e32e  jb      loc_18001E584
0x18001e334  xorps   xmm0, xmm0
0x18001e337  movdqu  xmmword ptr [rbp+47h+pHints.ai_addrlen], xmm0
0x18001e33c  xorps   xmm1, xmm1
0x18001e33f  movdqu  xmmword ptr [rbp+47h+pHints.ai_addr], xmm1
0x18001e344  mov     [rbp+47h+pHints.ai_family], r14d
0x18001e348  mov     r14d, 1
0x18001e34e  mov     [rbp+47h+pHints.ai_socktype], r14d
0x18001e352  mov     [rbp+47h+pHints.ai_flags], r14d
0x18001e356  mov     [rbp+47h+pHints.ai_protocol], 6
0x18001e35d  lea     rbx, [rsi+1A8h]
0x18001e364  mov     r9, rbx; ppResult
0x18001e367  lea     r8, [rbp+47h+pHints]; pHints
0x18001e36b  lea     rdx, [rbp+47h+pServiceName]; pServiceName
0x18001e36f  mov     rcx, r12; pNodeName
0x18001e372  call    cs:__imp_getaddrinfo
0x18001e378  test    eax, eax
0x18001e37a  jz      short loc_18001E3A2
0x18001e37c  call    cs:__imp_WSAGetLastError
0x18001e382  mov     edi, eax
0x18001e384  mov     rcx, rsi; this
0x18001e387  call    ?Finalize@CComMgrIo@@AEAAXXZ; CComMgrIo::Finalize(void)
0x18001e38c  test    edi, edi
0x18001e38e  jle     loc_18001E5D1
0x18001e394  movzx   edi, di
0x18001e397  or      edi, 80070000h
0x18001e39d  jmp     loc_18001E5D1
0x18001e3a2  mov     rax, [rbx]
0x18001e3a5  mov     [rsi+1A0h], rax
0x18001e3ac  test    rax, rax
0x18001e3af  jz      short loc_18001E3C8
0x18001e3b1  mov     ecx, [rsi+1B0h]
0x18001e3b7  inc     ecx
0x18001e3b9  mov     [rsi+1B0h], ecx
0x18001e3bf  mov     rax, [rax+28h]
0x18001e3c3  test    rax, rax
0x18001e3c6  jnz     short loc_18001E3B7
0x18001e3c8  mov     ecx, [rsi+1B0h]
0x18001e3ce  mov     eax, 8
0x18001e3d3  mul     rcx
0x18001e3d6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e3dd  cmovb   rax, rbx
0x18001e3e1  mov     rcx, rax; unsigned __int64
0x18001e3e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e3e9  mov     [rsi+1B8h], rax
0x18001e3f0  test    rax, rax
0x18001e3f3  jnz     short loc_18001E43D
0x18001e3f5  mov     eax, 8007000Eh
0x18001e3fa  mov     edi, eax
0x18001e3fc  lea     rcx, aFailedToAlloca; "Failed to allocate memory for listener "...
0x18001e403  mov     [rsp+0E0h+var_B0], rcx
0x18001e408  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001e40c  lea     rax, aCcommgrioInit; "CComMgrIo::Init"
0x18001e413  mov     [rsp+0E0h+var_C0], rax
0x18001e418  mov     r9d, 1EBh
0x18001e41e  lea     r8, aComComplusDtcD_89; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001e425  mov     edx, r14d
0x18001e428  lea     ecx, [rbx+0Bh]
0x18001e42b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e430  mov     rcx, rsi; this
0x18001e433  call    ?Finalize@CComMgrIo@@AEAAXXZ; CComMgrIo::Finalize(void)
0x18001e438  jmp     loc_18001E5D1
0x18001e43d  xor     edx, edx
0x18001e43f  cmp     [rsi+1B0h], edx
0x18001e445  jbe     short loc_18001E45D
0x18001e447  mov     rax, [rsi+1B8h]
0x18001e44e  mov     [rax+rdx*8], rbx
0x18001e452  add     edx, r14d
0x18001e455  cmp     edx, [rsi+1B0h]
0x18001e45b  jb      short loc_18001E447
0x18001e45d  mov     rax, [r13+0]
0x18001e461  mov     rcx, r13
0x18001e464  mov     rax, [rax+8]
0x18001e468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46d  mov     [rsi+1C0h], r13
0x18001e474  mov     rbx, [rbp+47h+var_90]
0x18001e478  mov     rax, [rbx]
0x18001e47b  mov     rcx, rbx
0x18001e47e  mov     rax, [rax+8]
0x18001e482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e487  mov     [rsi+1C8h], rbx
0x18001e48e  mov     r12d, [rsi+1B0h]
0x18001e495  mov     r13d, 1D0h
0x18001e49b  mov     eax, r13d
0x18001e49e  mul     r12
0x18001e4a1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e4a8  cmovb   rax, rcx
0x18001e4ac  add     rax, 8
0x18001e4b0  cmovb   rax, rcx
0x18001e4b4  mov     rcx, rax; unsigned __int64
0x18001e4b7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e4bc  mov     [rbp+47h+var_90], rax
0x18001e4c0  test    rax, rax
0x18001e4c3  jz      short loc_18001E4EF
0x18001e4c5  mov     [rax], r12
0x18001e4c8  lea     rbx, [rax+8]
0x18001e4cc  lea     rax, ??1CTcpCCB@@QEAA@XZ; CTcpCCB::~CTcpCCB(void)
0x18001e4d3  mov     [rsp+0E0h+var_C0], rax; void (*)(void *)
0x18001e4d8  lea     r9, ??0CTcpCCB@@QEAA@XZ; void (*)(void *)
0x18001e4df  mov     r8d, r12d; unsigned __int64
0x18001e4e2  mov     edx, r13d; unsigned __int64
0x18001e4e5  mov     rcx, rbx; void *
0x18001e4e8  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001e4ed  jmp     short loc_18001E4F1
0x18001e4ef  xor     ebx, ebx
0x18001e4f1  mov     [rsi+1D0h], rbx
0x18001e4f8  test    rbx, rbx
0x18001e4fb  jnz     short loc_18001E522
0x18001e4fd  mov     eax, 8007000Eh
0x18001e502  mov     edi, eax
0x18001e504  lea     rcx, aFailedToAlloca_0; "Failed to allocate memory for connectio"...
0x18001e50b  mov     [rsp+0E0h+var_B0], rcx
0x18001e510  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001e514  mov     r9d, 207h
0x18001e51a  mov     edx, r14d
0x18001e51d  jmp     loc_18001E5B4
0x18001e522  xor     r12d, r12d
0x18001e525  cmp     [rsi+1B0h], r12d
0x18001e52c  jbe     loc_18001E5D1
0x18001e532  mov     eax, r12d
0x18001e535  imul    rbx, rax, 1D0h
0x18001e53c  add     rbx, [rsi+1D0h]
0x18001e543  mov     rax, [rbx]
0x18001e546  lea     r8, [rbx+30h]
0x18001e54a  lea     rdx, IID_ICompletion
0x18001e551  mov     rcx, rbx
0x18001e554  mov     rax, [rax]
0x18001e557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e55c  mov     edi, eax
0x18001e55e  mov     dword ptr [rbx+38h], 0
0x18001e565  lea     rcx, [rbx+70h]; void *
0x18001e569  xor     edx, edx; Val
0x18001e56b  mov     r8d, 120h; Size
0x18001e571  call    memset_0
0x18001e576  add     r12d, r14d
0x18001e579  cmp     r12d, [rsi+1B0h]
0x18001e580  jb      short loc_18001E532
0x18001e582  jmp     short loc_18001E5D1
0x18001e584  call    cs:__imp_WSACleanup
0x18001e58a  jmp     loc_18001E320
0x18001e58f  call    ?Finalize@CComMgrIo@@AEAAXXZ; CComMgrIo::Finalize(void)
0x18001e594  mov     edi, 8000FFFFh
0x18001e599  lea     rax, aUnexpectedPort; "Unexpected Port Number"
0x18001e5a0  mov     r9d, 194h
0x18001e5a6  mov     [rsp+0E0h+var_B0], rax
0x18001e5ab  mov     dword ptr [rsp+0E0h+var_B8], edi
0x18001e5af  mov     edx, 1
0x18001e5b4  lea     rax, aCcommgrioInit; "CComMgrIo::Init"
0x18001e5bb  mov     [rsp+0E0h+var_C0], rax
0x18001e5c0  lea     r8, aComComplusDtcD_89; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001e5c7  mov     ecx, 0Ah
0x18001e5cc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e5d1  mov     rcx, [rbp+47h+pv]; pv
0x18001e5d5  call    cs:__imp_CoTaskMemFree
0x18001e5db  mov     rcx, r15; pv
0x18001e5de  call    cs:__imp_CoTaskMemFree
0x18001e5e4  mov     eax, edi
0x18001e5e6  mov     rcx, [rbp+47h+var_50]
0x18001e5ea  xor     rcx, rsp; StackCookie
0x18001e5ed  call    __security_check_cookie
0x18001e5f2  add     rsp, 0A8h
0x18001e5f9  pop     r15
0x18001e5fb  pop     r14
0x18001e5fd  pop     r13
0x18001e5ff  pop     r12
0x18001e601  pop     rdi
0x18001e602  pop     rsi
0x18001e603  pop     rbx
0x18001e604  pop     rbp
0x18001e605  retn
```
