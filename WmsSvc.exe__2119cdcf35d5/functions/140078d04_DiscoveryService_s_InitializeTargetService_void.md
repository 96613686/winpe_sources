# DiscoveryService::s_InitializeTargetService(void)

- ea: `0x140078d04`
- end: `0x140079033`
- name: `?s_InitializeTargetService@DiscoveryService@@CAJXZ`
- size: `815`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400080f0`

## callees

- `0x1400016c4`
- `0x140015f38`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140078d04`
- `0x140079428`
- `0x14007c7c0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140078e6e`
- `KERNEL32!IsDebuggerPresent` at `0x140078f07`
- `KERNEL32!IsDebuggerPresent` at `0x140078f79`
- `KERNEL32!IsDebuggerPresent` at `0x140078e6e`
- `KERNEL32!IsDebuggerPresent` at `0x140078f07`
- `KERNEL32!IsDebuggerPresent` at `0x140078f79`
- `wsdapi!WSDAllocateLinkedMemory` at `0x140078d7c`
- `wsdapi!WSDAllocateLinkedMemory` at `0x140078d7c`
- `wsdapi!WSDFreeLinkedMemory` at `0x140078fe2`
- `wsdapi!WSDFreeLinkedMemory` at `0x140078fe2`

## string_xrefs

- `0x140078e5f`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078d4a`: `DiscoveryService::s_InitializeTargetService: Adding scope %s.\n`
- `0x140078e4e`: `DiscoveryService::s_InitializeTargetService`
- `0x140078e38`: `s_pTargetService`
- `0x140078ee5`: `AddUriToList`
- `0x140078f59`: `AddUriToList`
- `0x140078ef8`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x140078f6a`: `termsrv\wms\src\middletier\discovery\common\common.cpp`
- `0x140078f43`: `pszUri != 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DiscoveryService::s_InitializeTargetService(void)
{
  const unsigned __int16 near *const *v0; // rdx
  const unsigned __int16 near *const *v1; // rax
  const unsigned __int16 near *v2; // rdi
  const struct _WSD_URI_LIST *v3; // rax
  int v4; // edi
  _DWORD *v5; // rax
  struct CTargetService *v6; // rbx
  __int64 v7; // r9
  struct _WSD_URI_LIST *v8; // rax
  struct _WSD_URI_LIST *Next; // rbx
  const unsigned __int16 *v11; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v12; // [rsp+30h] [rbp-38h]
  int v13; // [rsp+38h] [rbp-30h]
  const struct _WSD_URI_LIST *pVoid; // [rsp+70h] [rbp+8h]

  pVoid = 0;
  v0 = &off_14009C708;
  if ( !DiscoveryService::s_fMultiPointRoleInstalled )
    v0 = off_14009C700;
  DEBUGMSG(L"DiscoveryService::s_InitializeTargetService: Adding scope %s.\n", *v0);
  v1 = &off_14009C708;
  if ( !DiscoveryService::s_fMultiPointRoleInstalled )
    v1 = off_14009C700;
  v2 = *v1;
  if ( !*v1 )
  {
    v4 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      0x34u,
      L"AddUriToList",
      L"CBRAEx",
      L"pszUri != 0",
      -2147467261);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        52,
        L"AddUriToList",
        L"CBRAEx",
        L"pszUri != 0",
        -2147467261);
      goto LABEL_23;
    }
    v13 = -2147467261;
    v12 = L"pszUri != 0";
    v11 = L"CBRAEx";
    v7 = 52;
LABEL_21:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      v7,
      L"AddUriToList",
      v11,
      v12,
      v13);
    goto LABEL_23;
  }
  v3 = (const struct _WSD_URI_LIST *)WSDAllocateLinkedMemory(0, 0x10u);
  pVoid = v3;
  if ( !v3 )
  {
    v4 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
      0x3Au,
      L"AddUriToList",
      L"CPR",
      L"*ppNextNode",
      -2147024882);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\common.cpp",
        58,
        L"AddUriToList",
        L"CPR",
        L"*ppNextNode",
        -2147024882);
      goto LABEL_23;
    }
    v13 = -2147024882;
    v12 = L"*ppNextNode";
    v11 = L"CPR";
    v7 = 58;
    goto LABEL_21;
  }
  v3->Next = 0;
  v4 = s_DeepCopyStringHelper(1, v2, v3, &v3->Element);
  if ( v4 >= 0 )
  {
    v5 = operator new(0x90u);
    v6 = (struct CTargetService *)v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = &CTargetService::`vftable'{for `IWSDiscoveryPublisherNotify'};
      *((_QWORD *)v5 + 1) = &CTargetService::`vftable'{for `IWSDScopeMatchingRule'};
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 5) = 0;
      *((_QWORD *)v5 + 6) = 0;
      *((_QWORD *)v5 + 7) = 0;
      *((_QWORD *)v5 + 8) = 0;
      v5[18] = 0;
      v5[19] = 1;
      CCriticalSection::CCriticalSection((CCriticalSection *)(v5 + 20));
      *((_DWORD *)v6 + 34) = 1;
    }
    else
    {
      v6 = 0;
    }
    DiscoveryService::s_pTargetService = v6;
    if ( v6 )
    {
      v4 = CTargetService::Initialize(v6, pVoid);
    }
    else
    {
      v4 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        0xE3u,
        L"DiscoveryService::s_InitializeTargetService",
        L"CPR",
        L"s_pTargetService",
        -2147024882);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
          227,
          L"DiscoveryService::s_InitializeTargetService",
          L"CPR",
          L"s_pTargetService",
          -2147024882);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
          227,
          L"DiscoveryService::s_InitializeTargetService",
          L"CPR",
          L"s_pTargetService",
          -2147024882);
    }
  }
LABEL_23:
  v8 = (struct _WSD_URI_LIST *)pVoid;
  if ( pVoid )
  {
    do
    {
      Next = v8->Next;
      WSDFreeLinkedMemory(v8);
      v8 = Next;
    }
    while ( Next );
  }
  if ( v4 < 0 && DiscoveryService::s_pTargetService )
  {
    (*(void (__fastcall **)(struct CTargetService *))(*(_QWORD *)DiscoveryService::s_pTargetService + 16LL))(DiscoveryService::s_pTargetService);
    DiscoveryService::s_pTargetService = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140078d04  mov     rax, rsp
0x140078d07  mov     [rax+18h], rbx
0x140078d0b  mov     [rax+20h], rbp
0x140078d0f  push    rsi
0x140078d10  push    rdi
0x140078d11  push    r12
0x140078d13  push    r14
0x140078d15  push    r15
0x140078d17  sub     rsp, 40h
0x140078d1b  xor     r14d, r14d
0x140078d1e  mov     [rax+8], r14
0x140078d22  lea     rsi, [rax+8]
0x140078d26  mov     ebx, r14d
0x140078d29  lea     r15, off_14009C700; "http://www.microsoft.com/windowsserver/"...
0x140078d30  lea     ebp, [r14+1]
0x140078d34  lea     rdx, off_14009C708; "http://www.microsoft.com/windowsserver/"...
0x140078d3b  cmp     cs:?s_fMultiPointRoleInstalled@DiscoveryService@@0HA, r14d; int DiscoveryService::s_fMultiPointRoleInstalled
0x140078d42  cmovz   rdx, r15
0x140078d46  mov     rdx, [rdx+rbx*8]
0x140078d4a  lea     rcx, aDiscoveryservi_4; "DiscoveryService::s_InitializeTargetSer"...
0x140078d51  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140078d56  lea     rax, off_14009C708; "http://www.microsoft.com/windowsserver/"...
0x140078d5d  cmp     cs:?s_fMultiPointRoleInstalled@DiscoveryService@@0HA, r14d; int DiscoveryService::s_fMultiPointRoleInstalled
0x140078d64  cmovz   rax, r15
0x140078d68  mov     rdi, [rax+rbx*8]
0x140078d6c  test    rdi, rdi
0x140078d6f  jz      loc_140078F3A
0x140078d75  mov     edx, 10h; cbSize
0x140078d7a  xor     ecx, ecx; pParent
0x140078d7c  call    cs:__imp_WSDAllocateLinkedMemory
0x140078d82  mov     [rsi], rax
0x140078d85  test    rax, rax
0x140078d88  jz      loc_140078EC6
0x140078d8e  mov     [rax], r14
0x140078d91  mov     r8, [rsi]
0x140078d94  lea     r9, [r8+8]
0x140078d98  mov     rdx, rdi
0x140078d9b  mov     ecx, ebp
0x140078d9d  call    s_DeepCopyStringHelper
0x140078da2  mov     edi, eax
0x140078da4  test    eax, eax
0x140078da6  js      loc_140078FD2
0x140078dac  add     rbx, rbp
0x140078daf  cmp     rbx, rbp
0x140078db2  jnb     short loc_140078DBC
0x140078db4  mov     rsi, [rsi]
0x140078db7  jmp     loc_140078D34
0x140078dbc  mov     ecx, 90h; Size
0x140078dc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078dc6  mov     rbx, rax
0x140078dc9  mov     [rsp+68h+arg_8], rax
0x140078dce  test    rax, rax
0x140078dd1  jz      short loc_140078E1C
0x140078dd3  lea     rax, ??_7CTargetService@@6BIWSDiscoveryPublisherNotify@@@; const CTargetService::`vftable'{for `IWSDiscoveryPublisherNotify'}
0x140078dda  mov     [rbx], rax
0x140078ddd  lea     rax, ??_7CTargetService@@6BIWSDScopeMatchingRule@@@; const CTargetService::`vftable'{for `IWSDScopeMatchingRule'}
0x140078de4  mov     [rbx+8], rax
0x140078de8  mov     [rbx+10h], r14
0x140078dec  mov     [rbx+18h], r14
0x140078df0  mov     [rbx+20h], r14
0x140078df4  mov     [rbx+28h], r14
0x140078df8  mov     [rbx+30h], r14
0x140078dfc  mov     [rbx+38h], r14
0x140078e00  mov     [rbx+40h], r14
0x140078e04  mov     [rbx+48h], r14d
0x140078e08  mov     [rbx+4Ch], ebp
0x140078e0b  lea     rcx, [rbx+50h]; this
0x140078e0f  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x140078e14  mov     [rbx+88h], ebp
0x140078e1a  jmp     short loc_140078E1F
0x140078e1c  mov     rbx, r14
0x140078e1f  mov     cs:?s_pTargetService@DiscoveryService@@0PEAVCTargetService@@EA, rbx; CTargetService * DiscoveryService::s_pTargetService
0x140078e26  test    rbx, rbx
0x140078e29  jnz     loc_140078EB2
0x140078e2f  mov     edi, 8007000Eh
0x140078e34  mov     [rsp+68h+var_40], edi; int
0x140078e38  lea     r12, aSPtargetservic; "s_pTargetService"
0x140078e3f  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x140078e44  lea     rbp, aCpr; "CPR"
0x140078e4b  mov     r9, rbp; unsigned __int16 *
0x140078e4e  lea     r15, aDiscoveryservi_2; "DiscoveryService::s_InitializeTargetSer"...
0x140078e55  mov     r8, r15; unsigned __int16 *
0x140078e58  mov     ebx, 0E3h
0x140078e5d  mov     edx, ebx; unsigned int
0x140078e5f  lea     rsi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078e66  mov     rcx, rsi; unsigned __int16 *
0x140078e69  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078e6e  call    cs:__imp_IsDebuggerPresent
0x140078e74  test    eax, eax
0x140078e76  jz      short loc_140078E96
0x140078e78  mov     [rsp+68h+var_30], edi
0x140078e7c  mov     [rsp+68h+var_38], r12
0x140078e81  mov     qword ptr [rsp+68h+var_40], rbp
0x140078e86  mov     [rsp+68h+var_48], r15
0x140078e8b  mov     r9d, ebx
0x140078e8e  mov     r8, rsi
0x140078e91  jmp     loc_140078F9C
0x140078e96  mov     dword ptr [rsp+68h+var_38], edi
0x140078e9a  mov     qword ptr [rsp+68h+var_40], r12
0x140078e9f  mov     [rsp+68h+var_48], rbp
0x140078ea4  mov     r9, r15
0x140078ea7  mov     r8d, ebx
0x140078eaa  mov     rdx, rsi
0x140078ead  jmp     loc_140078FC6
0x140078eb2  mov     rdx, [rsp+68h+pVoid]; struct _WSD_URI_LIST *
0x140078eb7  mov     rcx, rbx; this
0x140078eba  call    ?Initialize@CTargetService@@QEAAJPEBU_WSD_URI_LIST@@@Z; CTargetService::Initialize(_WSD_URI_LIST const *)
0x140078ebf  mov     edi, eax
0x140078ec1  jmp     loc_140078FD2
0x140078ec6  mov     edi, 8007000Eh
0x140078ecb  mov     [rsp+68h+var_40], edi; int
0x140078ecf  lea     r12, aPpnextnode; "*ppNextNode"
0x140078ed6  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x140078edb  lea     rbp, aCpr; "CPR"
0x140078ee2  mov     r9, rbp; unsigned __int16 *
0x140078ee5  lea     rsi, aAdduritolist; "AddUriToList"
0x140078eec  mov     r8, rsi; unsigned __int16 *
0x140078eef  mov     r15d, 3Ah ; ':'
0x140078ef5  mov     edx, r15d; unsigned int
0x140078ef8  lea     rbx, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x140078eff  mov     rcx, rbx; unsigned __int16 *
0x140078f02  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078f07  call    cs:__imp_IsDebuggerPresent
0x140078f0d  test    eax, eax
0x140078f0f  jz      short loc_140078F24
0x140078f11  mov     [rsp+68h+var_30], edi
0x140078f15  mov     [rsp+68h+var_38], r12
0x140078f1a  mov     qword ptr [rsp+68h+var_40], rbp
0x140078f1f  mov     r9d, r15d
0x140078f22  jmp     short loc_140078F94
0x140078f24  mov     dword ptr [rsp+68h+var_38], edi
0x140078f28  mov     qword ptr [rsp+68h+var_40], r12
0x140078f2d  mov     [rsp+68h+var_48], rbp
0x140078f32  mov     r8d, r15d
0x140078f35  jmp     loc_140078FC0
0x140078f3a  mov     edi, 80004003h
0x140078f3f  mov     [rsp+68h+var_40], edi; int
0x140078f43  lea     r15, aPszuri0; "pszUri != 0"
0x140078f4a  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x140078f4f  lea     r12, aCbraex; "CBRAEx"
0x140078f56  mov     r9, r12; unsigned __int16 *
0x140078f59  lea     rsi, aAdduritolist; "AddUriToList"
0x140078f60  mov     r8, rsi; unsigned __int16 *
0x140078f63  mov     ebp, 34h ; '4'
0x140078f68  mov     edx, ebp; unsigned int
0x140078f6a  lea     rbx, aTermsrvWmsSrcM; "termsrv\\wms\\src\\middletier\\discover"...
0x140078f71  mov     rcx, rbx; unsigned __int16 *
0x140078f74  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078f79  call    cs:__imp_IsDebuggerPresent
0x140078f7f  test    eax, eax
0x140078f81  jz      short loc_140078FAF
0x140078f83  mov     [rsp+68h+var_30], edi
0x140078f87  mov     [rsp+68h+var_38], r15
0x140078f8c  mov     qword ptr [rsp+68h+var_40], r12
0x140078f91  mov     r9d, ebp
0x140078f94  mov     [rsp+68h+var_48], rsi
0x140078f99  mov     r8, rbx
0x140078f9c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140078fa3  mov     ecx, 2; unsigned __int8
0x140078fa8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140078fad  jmp     short loc_140078FD2
0x140078faf  mov     dword ptr [rsp+68h+var_38], edi
0x140078fb3  mov     qword ptr [rsp+68h+var_40], r15
0x140078fb8  mov     [rsp+68h+var_48], r12
0x140078fbd  mov     r8d, ebp
0x140078fc0  mov     rdx, rbx
0x140078fc3  mov     r9, rsi
0x140078fc6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140078fcd  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140078fd2  mov     rax, [rsp+68h+pVoid]
0x140078fd7  test    rax, rax
0x140078fda  jz      short loc_140078FF5
0x140078fdc  mov     rbx, [rax]
0x140078fdf  mov     rcx, rax; pVoid
0x140078fe2  call    cs:__imp_WSDFreeLinkedMemory
0x140078fe8  mov     rax, rbx
0x140078feb  mov     [rsp+68h+pVoid], rbx
0x140078ff0  test    rbx, rbx
0x140078ff3  jnz     short loc_140078FDC
0x140078ff5  test    edi, edi
0x140078ff7  jns     short loc_140079018
0x140078ff9  mov     rcx, cs:?s_pTargetService@DiscoveryService@@0PEAVCTargetService@@EA; CTargetService * DiscoveryService::s_pTargetService
0x140079000  test    rcx, rcx
0x140079003  jz      short loc_140079018
0x140079005  mov     rax, [rcx]
0x140079008  mov     rax, [rax+10h]
0x14007900c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079011  mov     cs:?s_pTargetService@DiscoveryService@@0PEAVCTargetService@@EA, r14; CTargetService * DiscoveryService::s_pTargetService
0x140079018  mov     eax, edi
0x14007901a  lea     r11, [rsp+68h+var_28]
0x14007901f  mov     rbx, [r11+40h]
0x140079023  mov     rbp, [r11+48h]
0x140079027  mov     rsp, r11
0x14007902a  pop     r15
0x14007902c  pop     r14
0x14007902e  pop     r12
0x140079030  pop     rdi
0x140079031  pop     rsi
0x140079032  retn
```
