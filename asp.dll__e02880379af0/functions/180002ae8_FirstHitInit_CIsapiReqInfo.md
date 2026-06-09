# FirstHitInit(CIsapiReqInfo *)

- ea: `0x180002ae8`
- end: `0x180002dca`
- name: `?FirstHitInit@@YAHPEAVCIsapiReqInfo@@@Z`
- size: `738`
- prototype: `_BOOL8 __fastcall(struct _EXTENSION_CONTROL_BLOCK **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x180002ae8`
- `0x180002dd0`
- `0x180002e40`
- `0x180003314`
- `0x1800033e8`
- `0x180003424`
- `0x180003560`
- `0x1800036dc`
- `0x180019e7c`
- `0x180034c90`
- `0x18003e918`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180002b7b`
- `iisutil!PuDbgPrint` at `0x180002bca`
- `iisutil!PuDbgPrint` at `0x180002c11`
- `iisutil!PuDbgPrint` at `0x180002c40`
- `iisutil!PuDbgPrint` at `0x180002c89`
- `iisutil!PuDbgPrint` at `0x180002d18`
- `iisutil!PuDbgPrint` at `0x180002d4b`
- `iisutil!PuDbgPrint` at `0x180002b7b`
- `iisutil!PuDbgPrint` at `0x180002bca`
- `iisutil!PuDbgPrint` at `0x180002c11`
- `iisutil!PuDbgPrint` at `0x180002c40`
- `iisutil!PuDbgPrint` at `0x180002c89`
- `iisutil!PuDbgPrint` at `0x180002d18`
- `iisutil!PuDbgPrint` at `0x180002d4b`

## string_xrefs

- `0x180002bf9`: `FirstHitInit: Template Cache Initialized\n`
- `0x180002c28`: `FirstHitInit: MTS configured\n`
- `0x180002c71`: `FirstHitInit: CViperReqManager configured\n`
- `0x180002d00`: `FirstHitInit: Hang Detection configured\n`
- `0x180002d33`: `ASP First Hit Initialization complete\n`

## pseudocode

```c
_BOOL8 __fastcall FirstHitInit(struct _EXTENSION_CONTROL_BLOCK **a1)
{
  const struct _GUID *v2; // rdx
  struct CIsapiReqInfo *v3; // rcx
  int ConfigFromSystem; // edi
  unsigned int v5; // ebp
  unsigned int v6; // ebx
  CTemplateCacheManager *v7; // rcx
  CViperReqManager *v8; // rcx
  char v9; // r8
  struct CIsapiReqInfo *v10; // rcx
  const struct _GUID *v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  HANDLE TokenHandle; // [rsp+70h] [rbp+8h] BYREF

  TokenHandle = (HANDLE)-1LL;
  AspDoRevertHack(&TokenHandle);
  if ( a1 && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(a1[1], 4u) )
    AspReqEvents::ASP_FIRST_REQUEST_FOR_ASP::RaiseEvent(a1[1], v2);
  ConfigFromSystem = ReadConfigFromSystem(0, (int)v2);
  v5 = 8;
  if ( ConfigFromSystem >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        802,
        "FirstHitInit",
        "FirstHitInit: Metadata loaded successfully\n");
    if ( (int)InitDebugging(v3) < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
          814,
          "FirstHitInit",
          "FirstHitInit: Debugger Initialization Failed\n");
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        810,
        "FirstHitInit",
        "FirstHitInit: Debugging Initialized\n");
    }
    ConfigFromSystem = CTemplateCacheManager::FirstHitInit(v7, a1);
    if ( ConfigFromSystem >= 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
          824,
          "FirstHitInit",
          "FirstHitInit: Template Cache Initialized\n");
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
            832,
            "FirstHitInit",
            "FirstHitInit: MTS configured\n");
      }
      ConfigFromSystem = CViperReqManager::Init(v8);
      if ( ConfigFromSystem >= 0 )
      {
        v9 = g_dwDebugFlags;
        v6 = 0;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
            842,
            "FirstHitInit",
            "FirstHitInit: CViperReqManager configured\n");
          v9 = g_dwDebugFlags;
        }
        v10 = (struct CIsapiReqInfo *)(unsigned int)g_AspRegistryParams;
        g_HangDetectConfig = dword_180079FA4 / 3u;
        if ( (g_AspRegistryParams & 2) != 0 )
          g_HangDetectConfig = *(_DWORD *)&dword_18007D838;
        if ( (g_AspRegistryParams & 4) != 0 )
          dword_180078784 = *(_DWORD *)&dword_18007D83C;
        if ( (g_AspRegistryParams & 8) != 0 )
          dword_180078788 = *(_DWORD *)&dword_18007D840;
        if ( (g_AspRegistryParams & 0x10) != 0 )
          dword_18007878C = *(_DWORD *)&dword_18007D844;
        if ( (v9 & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
            849,
            "FirstHitInit",
            "FirstHitInit: Hang Detection configured\n");
        InitPerfDataOnFirstRequest(v10);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
            858,
            "FirstHitInit",
            "ASP First Hit Initialization complete\n");
      }
      else
      {
        v6 = 4;
      }
    }
    else
    {
      v6 = 2;
    }
  }
  else
  {
    v6 = 1;
  }
  AspUndoRevertHack(&TokenHandle);
  if ( ConfigFromSystem >= 0 )
    return ConfigFromSystem >= 0;
  g_fFirstHitFailed = v6;
  if ( !a1 || !(unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(a1[1], 2u) )
    return ConfigFromSystem >= 0;
  v12 = v6 - 1;
  if ( !v12 )
  {
    v5 = 1;
    goto LABEL_46;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v5 = 2;
    goto LABEL_46;
  }
  v14 = v13 - 1;
  if ( !v14 || (v15 = v14 - 1) == 0 )
  {
    v5 = 4;
LABEL_46:
    AspReqEvents::ASP_INIT_FAILURE::RaiseEvent(a1[1], v11, v5);
    return ConfigFromSystem >= 0;
  }
  if ( v15 == 1 )
    goto LABEL_46;
  return ConfigFromSystem >= 0;
}

```

## disassembly

```asm
0x180002ae8  push    rbx
0x180002aea  push    rbp
0x180002aeb  push    rsi
0x180002aec  push    rdi
0x180002aed  push    r12
0x180002aef  push    r15
0x180002af1  sub     rsp, 38h
0x180002af5  mov     rsi, rcx
0x180002af8  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180002b01  lea     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180002b06  call    ?AspDoRevertHack@@YAXPEAPEAX@Z; AspDoRevertHack(void * *)
0x180002b0b  test    rsi, rsi
0x180002b0e  jz      short loc_180002B2B
0x180002b10  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180002b14  mov     edx, 4; unsigned int
0x180002b19  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180002b1e  test    eax, eax
0x180002b20  jz      short loc_180002B2B
0x180002b22  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180002b26  call    ?RaiseEvent@ASP_FIRST_REQUEST_FOR_ASP@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_FIRST_REQUEST_FOR_ASP::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180002b2b  xor     ecx, ecx; this
0x180002b2d  call    ?ReadConfigFromSystem@@YAJPEAVCAppConfig@@H@Z; ReadConfigFromSystem(CAppConfig *,int)
0x180002b32  mov     edi, eax
0x180002b34  mov     ebp, 8
0x180002b39  test    eax, eax
0x180002b3b  jns     short loc_180002B45
0x180002b3d  lea     ebx, [rbp-7]
0x180002b40  jmp     loc_180002D51
0x180002b45  test    byte ptr cs:g_dwDebugFlags, 3
0x180002b4c  lea     r15, aFirsthitinit; "FirstHitInit"
0x180002b53  lea     r12, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180002b5a  jz      short loc_180002B81
0x180002b5c  mov     rcx, cs:g_pDebug
0x180002b63  lea     rax, aFirsthitinitMe; "FirstHitInit: Metadata loaded successfu"...
0x180002b6a  mov     r9, r15
0x180002b6d  mov     [rsp+68h+var_48], rax
0x180002b72  mov     r8d, 322h
0x180002b78  mov     rdx, r12
0x180002b7b  call    cs:__imp_PuDbgPrint
0x180002b81  call    ?InitDebugging@@YAJPEAVCIsapiReqInfo@@@Z; InitDebugging(CIsapiReqInfo *)
0x180002b86  test    eax, eax
0x180002b88  js      short loc_180002BA2
0x180002b8a  test    byte ptr cs:g_dwDebugFlags, 3
0x180002b91  jz      short loc_180002BD0
0x180002b93  lea     rax, aFirsthitinitDe_0; "FirstHitInit: Debugging Initialized\n"
0x180002b9a  mov     r8d, 32Ah
0x180002ba0  jmp     short loc_180002BB8
0x180002ba2  test    byte ptr cs:g_dwDebugFlags, 3
0x180002ba9  jz      short loc_180002BD0
0x180002bab  lea     rax, aFirsthitinitDe; "FirstHitInit: Debugger Initialization F"...
0x180002bb2  mov     r8d, 32Eh
0x180002bb8  mov     rcx, cs:g_pDebug
0x180002bbf  mov     r9, r15
0x180002bc2  mov     rdx, r12
0x180002bc5  mov     [rsp+68h+var_48], rax
0x180002bca  call    cs:__imp_PuDbgPrint
0x180002bd0  mov     rdx, rsi; struct CIsapiReqInfo *
0x180002bd3  call    ?FirstHitInit@CTemplateCacheManager@@QEAAJPEAVCIsapiReqInfo@@@Z; CTemplateCacheManager::FirstHitInit(CIsapiReqInfo *)
0x180002bd8  mov     edi, eax
0x180002bda  test    eax, eax
0x180002bdc  jns     short loc_180002BE8
0x180002bde  mov     ebx, 2
0x180002be3  jmp     loc_180002D51
0x180002be8  mov     eax, cs:g_dwDebugFlags
0x180002bee  test    al, 3
0x180002bf0  jz      short loc_180002C46
0x180002bf2  mov     rcx, cs:g_pDebug
0x180002bf9  lea     rax, aFirsthitinitTe; "FirstHitInit: Template Cache Initialize"...
0x180002c00  mov     r9, r15
0x180002c03  mov     [rsp+68h+var_48], rax
0x180002c08  mov     r8d, 338h
0x180002c0e  mov     rdx, r12
0x180002c11  call    cs:__imp_PuDbgPrint
0x180002c17  mov     eax, cs:g_dwDebugFlags
0x180002c1d  test    al, 3
0x180002c1f  jz      short loc_180002C46
0x180002c21  mov     rcx, cs:g_pDebug
0x180002c28  lea     rax, aFirsthitinitMt; "FirstHitInit: MTS configured\n"
0x180002c2f  mov     r9, r15
0x180002c32  mov     [rsp+68h+var_48], rax
0x180002c37  mov     r8d, 340h
0x180002c3d  mov     rdx, r12
0x180002c40  call    cs:__imp_PuDbgPrint
0x180002c46  call    ?Init@CViperReqManager@@QEAAJXZ; CViperReqManager::Init(void)
0x180002c4b  mov     edi, eax
0x180002c4d  test    eax, eax
0x180002c4f  jns     short loc_180002C5B
0x180002c51  mov     ebx, 4
0x180002c56  jmp     loc_180002D51
0x180002c5b  mov     r8d, cs:g_dwDebugFlags
0x180002c62  xor     ebx, ebx
0x180002c64  test    r8b, 3
0x180002c68  jz      short loc_180002C96
0x180002c6a  mov     rcx, cs:g_pDebug
0x180002c71  lea     rax, aFirsthitinitCv; "FirstHitInit: CViperReqManager configur"...
0x180002c78  mov     r9, r15
0x180002c7b  mov     [rsp+68h+var_48], rax
0x180002c80  mov     r8d, 34Ah
0x180002c86  mov     rdx, r12
0x180002c89  call    cs:__imp_PuDbgPrint
0x180002c8f  mov     r8d, cs:g_dwDebugFlags
0x180002c96  mov     ecx, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180002c9c  mov     eax, 0AAAAAAABh
0x180002ca1  mul     cs:dword_180079FA4
0x180002ca7  shr     edx, 1
0x180002ca9  mov     cs:?g_HangDetectConfig@@3VCHangDetectConfig@@A, edx; CHangDetectConfig g_HangDetectConfig
0x180002caf  test    cl, 2
0x180002cb2  jz      short loc_180002CC0
0x180002cb4  mov     eax, cs:dword_18007D838
0x180002cba  mov     cs:?g_HangDetectConfig@@3VCHangDetectConfig@@A, eax; CHangDetectConfig g_HangDetectConfig
0x180002cc0  test    cl, 4
0x180002cc3  jz      short loc_180002CD1
0x180002cc5  mov     eax, cs:dword_18007D83C
0x180002ccb  mov     cs:dword_180078784, eax
0x180002cd1  test    bpl, cl
0x180002cd4  jz      short loc_180002CE2
0x180002cd6  mov     eax, cs:dword_18007D840
0x180002cdc  mov     cs:dword_180078788, eax
0x180002ce2  test    cl, 10h
0x180002ce5  jz      short loc_180002CF3
0x180002ce7  mov     eax, cs:dword_18007D844
0x180002ced  mov     cs:dword_18007878C, eax
0x180002cf3  test    r8b, 3
0x180002cf7  jz      short loc_180002D1E
0x180002cf9  mov     rcx, cs:g_pDebug
0x180002d00  lea     rax, aFirsthitinitHa; "FirstHitInit: Hang Detection configured"...
0x180002d07  mov     r9, r15
0x180002d0a  mov     [rsp+68h+var_48], rax
0x180002d0f  mov     r8d, 351h
0x180002d15  mov     rdx, r12
0x180002d18  call    cs:__imp_PuDbgPrint
0x180002d1e  call    ?InitPerfDataOnFirstRequest@@YAJPEAVCIsapiReqInfo@@@Z; InitPerfDataOnFirstRequest(CIsapiReqInfo *)
0x180002d23  test    byte ptr cs:g_dwDebugFlags, 3
0x180002d2a  jz      short loc_180002D51
0x180002d2c  mov     rcx, cs:g_pDebug
0x180002d33  lea     rax, aAspFirstHitIni; "ASP First Hit Initialization complete\n"
0x180002d3a  mov     r9, r15
0x180002d3d  mov     [rsp+68h+var_48], rax
0x180002d42  mov     r8d, 35Ah
0x180002d48  mov     rdx, r12
0x180002d4b  call    cs:__imp_PuDbgPrint
0x180002d51  lea     rcx, [rsp+68h+TokenHandle]; void **
0x180002d56  call    ?AspUndoRevertHack@@YAXPEAPEAX@Z; AspUndoRevertHack(void * *)
0x180002d5b  test    edi, edi
0x180002d5d  jns     short loc_180002DB6
0x180002d5f  mov     cs:?g_fFirstHitFailed@@3KA, ebx; ulong g_fFirstHitFailed
0x180002d65  test    rsi, rsi
0x180002d68  jz      short loc_180002DB6
0x180002d6a  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180002d6e  mov     edx, 2; unsigned int
0x180002d73  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180002d78  test    eax, eax
0x180002d7a  jz      short loc_180002DB6
0x180002d7c  sub     ebx, 1
0x180002d7f  jz      short loc_180002DA5
0x180002d81  sub     ebx, 1
0x180002d84  jz      short loc_180002D9E
0x180002d86  sub     ebx, 1
0x180002d89  jz      short loc_180002D97
0x180002d8b  sub     ebx, 1
0x180002d8e  jz      short loc_180002D97
0x180002d90  cmp     ebx, 1
0x180002d93  jnz     short loc_180002DB6
0x180002d95  jmp     short loc_180002DAA
0x180002d97  mov     ebp, 4
0x180002d9c  jmp     short loc_180002DAA
0x180002d9e  mov     ebp, 2
0x180002da3  jmp     short loc_180002DAA
0x180002da5  mov     ebp, 1
0x180002daa  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180002dae  mov     r8d, ebp; unsigned int
0x180002db1  call    ?RaiseEvent@ASP_INIT_FAILURE@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@K@Z; AspReqEvents::ASP_INIT_FAILURE::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ulong)
0x180002db6  not     edi
0x180002db8  shr     edi, 1Fh
0x180002dbb  mov     eax, edi
0x180002dbd  add     rsp, 38h
0x180002dc1  pop     r15
0x180002dc3  pop     r12
0x180002dc5  pop     rdi
0x180002dc6  pop     rsi
0x180002dc7  pop     rbp
0x180002dc8  pop     rbx
0x180002dc9  retn
```
