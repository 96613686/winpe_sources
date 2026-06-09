# CTargetService::Initialize(_WSD_URI_LIST const *)

- ea: `0x140079428`
- end: `0x140079833`
- name: `?Initialize@CTargetService@@QEAAJPEBU_WSD_URI_LIST@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(CTargetService *__hidden this, const struct _WSD_URI_LIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140078d04`

## callees

- `0x1400016b8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140079428`
- `0x140079b10`
- `0x140079d40`
- `0x14007bf90`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400795a1`
- `KERNEL32!IsDebuggerPresent` at `0x140079667`
- `KERNEL32!IsDebuggerPresent` at `0x1400796d7`
- `KERNEL32!IsDebuggerPresent` at `0x1400795a1`
- `KERNEL32!IsDebuggerPresent` at `0x140079667`
- `KERNEL32!IsDebuggerPresent` at `0x1400796d7`
- `msvcrt!time` at `0x1400797f1`
- `msvcrt!time` at `0x1400797f1`
- `wsdapi!WSDCreateDiscoveryPublisher` at `0x140079692`
- `wsdapi!WSDCreateDiscoveryPublisher` at `0x140079692`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079528`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079537`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079528`
- `wsdapi!WSDFreeLinkedMemory` at `0x140079537`

## string_xrefs

- `0x140079483`: `CTargetService::Initialize`
- `0x14007956f`: `CTargetService::Initialize`
- `0x140079635`: `CTargetService::Initialize`
- `0x1400796a6`: `CTargetService::Initialize`
- `0x14007948a`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x14007957b`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x140079641`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`
- `0x1400796b7`: `termsrv\wms\src\middletier\discovery\service\disctargetservice.cpp`

## pseudocode

```c
__int64 __fastcall CTargetService::Initialize(CTargetService *this, const struct _WSD_URI_LIST *a2)
{
  struct CTargetService *v2; // rdi
  wchar_t *v4; // r12
  struct _WSD_URI_LIST *v5; // r15
  int v6; // r13d
  int v7; // ebx
  IWSDiscoveryPublisher *v8; // r9
  bool v10; // zf
  const unsigned __int16 *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  time_t v17; // rax
  void *v18; // rax
  void *pVoid; // [rsp+40h] [rbp-20h] BYREF
  struct _WSD_URI_LIST *v20; // [rsp+48h] [rbp-18h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-10h] BYREF
  IWSDiscoveryPublisher *ppPublisher; // [rsp+B8h] [rbp+58h] BYREF

  v2 = DiscoveryService::s_pTargetService;
  ppPublisher = 0;
  v4 = 0;
  String1 = 0;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  pVoid = 0;
  if ( !*((_QWORD *)DiscoveryService::s_pTargetService + 10) )
  {
    v7 = -2147024882;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      134,
      L"CTargetService::Initialize",
      L"Critical section is not initialized.");
    goto LABEL_3;
  }
  if ( *((_DWORD *)DiscoveryService::s_pTargetService + 18) )
  {
    v7 = -2147467260;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      0x8Bu,
      L"CTargetService::Initialize",
      L"CBRAEx",
      L"(m_fIsActive == 0)",
      -2147467260);
    v10 = !IsDebuggerPresent();
    v11 = L"(m_fIsActive == 0)";
    if ( !v10 )
    {
      v12 = 139;
LABEL_16:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        v12,
        L"CTargetService::Initialize",
        L"CBRAEx",
        v11,
        -2147467260);
LABEL_17:
      v6 = 0;
      goto LABEL_3;
    }
    v13 = 139;
    goto LABEL_19;
  }
  if ( *((_QWORD *)DiscoveryService::s_pTargetService + 6) )
  {
    v7 = -2147467260;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      0x8Cu,
      L"CTargetService::Initialize",
      L"CBRAEx",
      L"(m_pPublisher == 0)",
      -2147467260);
    v10 = !IsDebuggerPresent();
    v11 = L"(m_pPublisher == 0)";
    if ( !v10 )
    {
      v12 = 140;
      goto LABEL_16;
    }
    v13 = 140;
LABEL_19:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      v13,
      L"CTargetService::Initialize",
      L"CBRAEx",
      v11,
      -2147467260);
    goto LABEL_17;
  }
  v14 = WSDCreateDiscoveryPublisher(0, &ppPublisher);
  v7 = v14;
  if ( v14 >= 0 )
  {
    v15 = GenerateEndpointReference(&String1);
    v4 = String1;
    v7 = v15;
    if ( v15 >= 0 )
    {
      v7 = GenerateXAddrsList(String1, &pVoid);
      if ( v7 >= 0 )
      {
        if ( !a2 || (v16 = DeepCopyWsdUriList(a2, &v20), v5 = v20, v7 = v16, v16 >= 0) )
        {
          v7 = ((__int64 (__fastcall *)(IWSDiscoveryPublisher *, _QWORD))ppPublisher->lpVtbl->RegisterScopeMatchingRule)(
                 ppPublisher,
                 ((unsigned __int64)v2 + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)v2 >> 64));
          if ( v7 >= 0 )
          {
            v6 = 1;
            v7 = ((__int64 (__fastcall *)(IWSDiscoveryPublisher *, struct CTargetService *))ppPublisher->lpVtbl->RegisterNotificationSink)(
                   ppPublisher,
                   v2);
            if ( v7 >= 0 )
            {
              v17 = time(0);
              *((_QWORD *)v2 + 2) = v4;
              *((_QWORD *)v2 + 7) = v17;
              v4 = 0;
              *((_QWORD *)v2 + 6) = ppPublisher;
              v18 = pVoid;
              *((_QWORD *)v2 + 4) = v5;
              v5 = 0;
              *((_QWORD *)v2 + 5) = v18;
              *((_QWORD *)v2 + 8) = 0;
              ppPublisher = 0;
              pVoid = 0;
              *((_QWORD *)v2 + 9) = 1;
              goto LABEL_8;
            }
          }
        }
      }
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
      0x96u,
      L"CTargetService::Initialize",
      L"CHRA",
      L"hr",
      v14);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        150,
        L"CTargetService::Initialize",
        L"CHRA",
        L"hr",
        v7);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\disctargetservice.cpp",
        150,
        L"CTargetService::Initialize",
        L"CHRA",
        L"hr",
        v7);
  }
LABEL_3:
  v8 = ppPublisher;
  if ( ppPublisher )
  {
    if ( v6 == 1 )
    {
      ((void (__fastcall *)(IWSDiscoveryPublisher *, unsigned __int64))ppPublisher->lpVtbl->UnRegisterScopeMatchingRule)(
        ppPublisher,
        ((unsigned __int64)v2 + 8) & -(__int64)(v2 != 0));
      v8 = ppPublisher;
    }
    if ( v8 )
    {
      ((void (__fastcall *)(IWSDiscoveryPublisher *))v8->lpVtbl->Release)(v8);
      ppPublisher = 0;
    }
  }
LABEL_8:
  operator delete(v4);
  if ( v5 )
    WSDFreeLinkedMemory(v5);
  if ( pVoid )
    WSDFreeLinkedMemory(pVoid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140079428  mov     [rsp-38h+arg_8], rbx
0x14007942d  push    rbp
0x14007942e  push    rsi
0x14007942f  push    rdi
0x140079430  push    r12
0x140079432  push    r13
0x140079434  push    r14
0x140079436  push    r15
0x140079438  mov     rbp, rsp
0x14007943b  sub     rsp, 60h
0x14007943f  mov     rdi, cs:?s_pTargetService@DiscoveryService@@0PEAVCTargetService@@EA; CTargetService * DiscoveryService::s_pTargetService
0x140079446  xor     ecx, ecx; pContext
0x140079448  mov     rsi, rdx
0x14007944b  mov     [rbp+ppPublisher], rcx
0x14007944f  mov     r12d, ecx
0x140079452  mov     [rbp+String1], rcx
0x140079456  mov     r15d, ecx
0x140079459  mov     [rbp+var_18], rcx
0x14007945d  mov     r13d, ecx
0x140079460  mov     [rbp+pVoid], rcx
0x140079464  mov     r14d, ecx
0x140079467  cmp     [rdi+50h], rcx
0x14007946b  jnz     loc_140079557
0x140079471  lea     rax, aCriticalSectio; "Critical section is not initialized."
0x140079478  mov     r9d, 86h
0x14007947e  mov     qword ptr [rsp+60h+var_38], rax
0x140079483  lea     r14, aCtargetservice_1; "CTargetService::Initialize"
0x14007948a  lea     r8, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079491  mov     [rsp+60h+var_40], r14
0x140079496  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14007949d  mov     ebx, 8007000Eh
0x1400794a2  lea     ecx, [r15+4]; unsigned __int8
0x1400794a6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400794ab  mov     r14d, r12d
0x1400794ae  mov     r9, [rbp+ppPublisher]
0x1400794b2  test    r9, r9
0x1400794b5  jz      short loc_140079518
0x1400794b7  cmp     r13d, 1
0x1400794bb  jnz     short loc_1400794E0
0x1400794bd  mov     r8, [r9]
0x1400794c0  lea     rcx, [rdi+8]
0x1400794c4  mov     rax, rdi
0x1400794c7  neg     rax
0x1400794ca  mov     rax, [r8+70h]
0x1400794ce  sbb     rdx, rdx
0x1400794d1  and     rdx, rcx
0x1400794d4  mov     rcx, r9
0x1400794d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400794dc  mov     r9, [rbp+ppPublisher]
0x1400794e0  cmp     r14d, 1
0x1400794e4  jnz     short loc_1400794FC
0x1400794e6  mov     rax, [r9]
0x1400794e9  mov     rdx, rdi
0x1400794ec  mov     rcx, r9
0x1400794ef  mov     rax, [rax+28h]
0x1400794f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400794f8  mov     r9, [rbp+ppPublisher]
0x1400794fc  test    r9, r9
0x1400794ff  jz      short loc_140079518
0x140079501  mov     rax, [r9]
0x140079504  mov     rcx, r9
0x140079507  mov     rax, [rax+10h]
0x14007950b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079510  mov     [rbp+ppPublisher], 0
0x140079518  mov     rcx, r12; Block
0x14007951b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140079520  test    r15, r15
0x140079523  jz      short loc_14007952E
0x140079525  mov     rcx, r15; pVoid
0x140079528  call    cs:__imp_WSDFreeLinkedMemory
0x14007952e  mov     rcx, [rbp+pVoid]; pVoid
0x140079532  test    rcx, rcx
0x140079535  jz      short loc_14007953D
0x140079537  call    cs:__imp_WSDFreeLinkedMemory
0x14007953d  mov     eax, ebx
0x14007953f  mov     rbx, [rsp+60h+arg_8]
0x140079547  add     rsp, 60h
0x14007954b  pop     r15
0x14007954d  pop     r14
0x14007954f  pop     r13
0x140079551  pop     r12
0x140079553  pop     rdi
0x140079554  pop     rsi
0x140079555  pop     rbp
0x140079556  retn
0x140079557  mov     eax, [rdi+48h]
0x14007955a  test    eax, eax
0x14007955c  jz      loc_140079622
0x140079562  mov     r13d, 80004004h
0x140079568  lea     rax, aMFisactive0; "(m_fIsActive == 0)"
0x14007956f  lea     r14, aCtargetservice_1; "CTargetService::Initialize"
0x140079576  mov     [rsp+60h+var_38], r13d; int
0x14007957b  lea     rsi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079582  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x140079587  mov     r8, r14; unsigned __int16 *
0x14007958a  lea     r9, aCbraex; "CBRAEx"
0x140079591  mov     rcx, rsi; unsigned __int16 *
0x140079594  mov     edx, 8Bh; unsigned int
0x140079599  mov     ebx, r13d
0x14007959c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400795a1  call    cs:__imp_IsDebuggerPresent
0x1400795a7  test    eax, eax
0x1400795a9  lea     rax, aMFisactive0; "(m_fIsActive == 0)"
0x1400795b0  jz      short loc_1400795F2
0x1400795b2  mov     r9d, 8Bh
0x1400795b8  mov     [rsp+60h+var_28], r13d
0x1400795bd  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400795c4  mov     [rsp+60h+var_30], rax
0x1400795c9  mov     r8, rsi
0x1400795cc  lea     rax, aCbraex; "CBRAEx"
0x1400795d3  mov     ecx, 2; unsigned __int8
0x1400795d8  mov     qword ptr [rsp+60h+var_38], rax
0x1400795dd  mov     [rsp+60h+var_40], r14
0x1400795e2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400795e7  mov     r14d, r12d
0x1400795ea  mov     r13d, r12d
0x1400795ed  jmp     loc_1400794AE
0x1400795f2  mov     r8d, 8Bh
0x1400795f8  mov     dword ptr [rsp+60h+var_30], r13d
0x1400795fd  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140079604  mov     qword ptr [rsp+60h+var_38], rax
0x140079609  mov     r9, r14
0x14007960c  lea     rax, aCbraex; "CBRAEx"
0x140079613  mov     rdx, rsi
0x140079616  mov     [rsp+60h+var_40], rax
0x14007961b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140079620  jmp     short loc_1400795E7
0x140079622  cmp     [rdi+30h], rcx
0x140079626  jz      short loc_14007968E
0x140079628  mov     r13d, 80004004h
0x14007962e  lea     rax, aMPpublisher0; "(m_pPublisher == 0)"
0x140079635  lea     r14, aCtargetservice_1; "CTargetService::Initialize"
0x14007963c  mov     [rsp+60h+var_38], r13d; int
0x140079641  lea     rsi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x140079648  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x14007964d  mov     r8, r14; unsigned __int16 *
0x140079650  lea     r9, aCbraex; "CBRAEx"
0x140079657  mov     rcx, rsi; unsigned __int16 *
0x14007965a  mov     edx, 8Ch; unsigned int
0x14007965f  mov     ebx, r13d
0x140079662  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140079667  call    cs:__imp_IsDebuggerPresent
0x14007966d  test    eax, eax
0x14007966f  lea     rax, aMPpublisher0; "(m_pPublisher == 0)"
0x140079676  jz      short loc_140079683
0x140079678  mov     r9d, 8Ch
0x14007967e  jmp     loc_1400795B8
0x140079683  mov     r8d, 8Ch
0x140079689  jmp     loc_1400795F8
0x14007968e  lea     rdx, [rbp+ppPublisher]; ppPublisher
0x140079692  call    cs:__imp_WSDCreateDiscoveryPublisher
0x140079698  mov     ebx, eax
0x14007969a  test    eax, eax
0x14007969c  jns     loc_140079753
0x1400796a2  mov     [rsp+60h+var_38], eax; int
0x1400796a6  lea     r14, aCtargetservice_1; "CTargetService::Initialize"
0x1400796ad  lea     rax, aHr; "hr"
0x1400796b4  mov     r8, r14; unsigned __int16 *
0x1400796b7  lea     rsi, aTermsrvWmsSrcM_2; "termsrv\\wms\\src\\middletier\\discover"...
0x1400796be  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x1400796c3  mov     rcx, rsi; unsigned __int16 *
0x1400796c6  lea     r9, aChra; "CHRA"
0x1400796cd  mov     edx, 96h; unsigned int
0x1400796d2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400796d7  call    cs:__imp_IsDebuggerPresent
0x1400796dd  test    eax, eax
0x1400796df  lea     rax, aHr; "hr"
0x1400796e6  jz      short loc_14007971E
0x1400796e8  mov     [rsp+60h+var_28], ebx
0x1400796ec  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400796f3  mov     [rsp+60h+var_30], rax
0x1400796f8  mov     r9d, 96h
0x1400796fe  lea     rax, aChra; "CHRA"
0x140079705  mov     r8, rsi
0x140079708  mov     qword ptr [rsp+60h+var_38], rax
0x14007970d  mov     ecx, 2; unsigned __int8
0x140079712  mov     [rsp+60h+var_40], r14
0x140079717  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007971c  jmp     short loc_14007974B
0x14007971e  mov     dword ptr [rsp+60h+var_30], ebx
0x140079722  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140079729  mov     qword ptr [rsp+60h+var_38], rax
0x14007972e  mov     r9, r14
0x140079731  lea     rax, aChra; "CHRA"
0x140079738  mov     r8d, 96h
0x14007973e  mov     rdx, rsi
0x140079741  mov     [rsp+60h+var_40], rax
0x140079746  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007974b  xor     r14d, r14d
0x14007974e  jmp     loc_1400794AE
0x140079753  lea     rcx, [rbp+String1]
0x140079757  call    _GenerateEndpointReference
0x14007975c  mov     r12, [rbp+String1]
0x140079760  mov     ebx, eax
0x140079762  test    eax, eax
0x140079764  js      loc_1400794AE
0x14007976a  lea     rdx, [rbp+pVoid]
0x14007976e  mov     rcx, r12; String1
0x140079771  call    _GenerateXAddrsList
0x140079776  mov     ebx, eax
0x140079778  test    eax, eax
0x14007977a  js      loc_1400794AE
0x140079780  test    rsi, rsi
0x140079783  jz      short loc_14007979F
0x140079785  lea     rdx, [rbp+var_18]; struct _WSD_URI_LIST **
0x140079789  mov     rcx, rsi; struct _WSD_URI_LIST *
0x14007978c  call    ?DeepCopyWsdUriList@@YAJPEBU_WSD_URI_LIST@@PEAPEAU1@@Z; DeepCopyWsdUriList(_WSD_URI_LIST const *,_WSD_URI_LIST * *)
0x140079791  mov     r15, [rbp+var_18]
0x140079795  mov     ebx, eax
0x140079797  test    eax, eax
0x140079799  js      loc_1400794AE
0x14007979f  mov     r9, [rbp+ppPublisher]
0x1400797a3  lea     rcx, [rdi+8]
0x1400797a7  mov     rax, rdi
0x1400797aa  neg     rax
0x1400797ad  mov     r8, [r9]
0x1400797b0  sbb     rdx, rdx
0x1400797b3  and     rdx, rcx
0x1400797b6  mov     rcx, r9
0x1400797b9  mov     rax, [r8+68h]
0x1400797bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400797c2  mov     ebx, eax
0x1400797c4  test    eax, eax
0x1400797c6  js      loc_1400794AE
0x1400797cc  mov     rcx, [rbp+ppPublisher]
0x1400797d0  mov     rdx, rdi
0x1400797d3  mov     r13d, 1
0x1400797d9  mov     rax, [rcx]
0x1400797dc  mov     rax, [rax+20h]
0x1400797e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400797e5  mov     ebx, eax
0x1400797e7  test    eax, eax
0x1400797e9  js      loc_1400794AE
0x1400797ef  xor     ecx, ecx; Time
0x1400797f1  call    cs:__imp_time
0x1400797f7  xor     ecx, ecx
0x1400797f9  mov     [rdi+10h], r12
0x1400797fd  mov     [rdi+38h], rax
0x140079801  mov     r12d, ecx
0x140079804  mov     rax, [rbp+ppPublisher]
0x140079808  mov     [rdi+30h], rax
0x14007980c  mov     rax, [rbp+pVoid]
0x140079810  mov     [rdi+20h], r15
0x140079814  mov     r15d, ecx
0x140079817  mov     [rdi+28h], rax
0x14007981b  mov     [rdi+40h], rcx
0x14007981f  mov     [rbp+ppPublisher], rcx
0x140079823  mov     [rbp+pVoid], rcx
0x140079827  mov     [rdi+48h], r13d
0x14007982b  mov     [rdi+4Ch], ecx
0x14007982e  jmp     loc_140079518
```
