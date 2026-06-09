# SvcInit(void)

- ea: `0x180005bc4`
- end: `0x180005eb9`
- name: `?SvcInit@@YAXXZ`
- size: `757`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180006040`

## callees

- `0x180001930`
- `0x180001f7c`
- `0x180005a20`
- `0x180005ac0`
- `0x180005bc4`
- `0x180005ff8`
- `0x180006140`
- `0x180006168`
- `0x1800061ac`
- `0x180006554`
- `0x180006c94`
- `0x180007124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005c30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005c30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005e0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d62`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d62`

## pseudocode

```c
void SvcInit(void)
{
  HANDLE EventW; // rdi
  HANDLE v1; // rsi
  DWORD LastError; // ebx
  DWORD v3; // eax
  __int64 v4; // r8
  DWORD v5; // edx
  CApxSvc *v6; // rax
  CApxSvc *v7; // rcx
  int v8; // eax
  DWORD v9; // ebx
  int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  DWORD v13; // eax
  __int64 v14; // r8
  int v15[2]; // [rsp+20h] [rbp-38h] BYREF
  int v16; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v18; // [rsp+60h] [rbp+8h] BYREF
  CApxSvc *v19; // [rsp+68h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
  }
  LOBYTE(v18) = 0;
  *(_QWORD *)v15 = &v18;
  LOBYTE(v16) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  v1 = g_SvcStopEvent;
  if ( (char *)g_SvcStopEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v1);
    SetLastError(LastError);
  }
  g_SvcStopEvent = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = GetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v4, v3, *(_QWORD *)v15, v16);
    }
    v5 = GetLastError();
LABEL_13:
    ReportSvcStatus(1u, v5, 0);
    goto LABEL_45;
  }
  v6 = (CApxSvc *)operator new(0xCu);
  v19 = v6;
  *(_QWORD *)v6 = 0;
  *((_BYTE *)v6 + 8) = 0;
  v7 = g_ApxService;
  g_ApxService = v6;
  if ( v7 )
  {
    operator delete(v7);
    v6 = g_ApxService;
  }
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
    }
    v5 = 8;
    goto LABEL_13;
  }
  if ( !pti )
  {
    dword_18000E1FC = 120;
    dword_18000E4C8 = 0;
    pti = CreateThreadpoolTimer(anonymous_namespace_::TimerCallback, 0, 0);
    if ( pti )
    {
      if ( (unsigned int)anonymous_namespace_::SetShutdownTimer() )
      {
        LOBYTE(v18) = 1;
        v8 = CApxSvc::Initialize(g_ApxService);
        v9 = v8;
        if ( v8 >= 0 )
        {
          ReportSvcStatus(4u, 0, 0);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
          }
          WaitForSingleObject(g_SvcStopEvent, 0xFFFFFFFF);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
          }
          v10 = CApxSvc::Cleanup(g_ApxService);
          v9 = v10;
          if ( v10 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, v11, v12, (const char *)(unsigned int)v10, v15[0]);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && *((char *)WPP_GLOBAL_Control + 28) < 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids,
            (unsigned int)v8);
        }
        v5 = v9;
        goto LABEL_13;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v14, v13, *(_QWORD *)v15, v16);
  }
LABEL_45:
  wil::details::lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___::_lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___(v15);
}

```

## disassembly

```asm
0x180005bc4  mov     [rsp+arg_10], rbx
0x180005bc9  push    rsi
0x180005bca  push    rdi
0x180005bcb  push    r12
0x180005bcd  push    r14
0x180005bcf  push    r15
0x180005bd1  sub     rsp, 30h
0x180005bd5  lea     r14, WPP_GLOBAL_Control
0x180005bdc  lea     r12, WPP_27ea2efe8112346a6f92681e48c92895_Traceguids
0x180005be3  mov     r15d, 1
0x180005be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bf0  cmp     rcx, r14
0x180005bf3  jz      short loc_180005C11
0x180005bf5  test    [rcx+1Ch], r15b
0x180005bf9  jz      short loc_180005C11
0x180005bfb  cmp     byte ptr [rcx+19h], 5
0x180005bff  jb      short loc_180005C11
0x180005c01  lea     edx, [r15+0Ah]
0x180005c05  mov     r8, r12
0x180005c08  mov     rcx, [rcx+10h]
0x180005c0c  call    WPP_SF_
0x180005c11  mov     byte ptr [rsp+58h+arg_0], 0
0x180005c16  lea     rax, [rsp+58h+arg_0]
0x180005c1b  mov     qword ptr [rsp+58h+var_38], rax; int
0x180005c20  mov     byte ptr [rsp+58h+var_30], r15b
0x180005c25  xor     r9d, r9d; lpName
0x180005c28  xor     r8d, r8d; bInitialState
0x180005c2b  mov     edx, r15d; bManualReset
0x180005c2e  xor     ecx, ecx; lpEventAttributes
0x180005c30  call    cs:__imp_CreateEventW
0x180005c36  mov     rdi, rax
0x180005c39  mov     rsi, cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_SvcStopEvent
0x180005c40  lea     rcx, [rsi-1]
0x180005c44  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180005c48  ja      short loc_180005C63
0x180005c4a  call    cs:__imp_GetLastError
0x180005c50  mov     ebx, eax
0x180005c52  mov     rcx, rsi; hObject
0x180005c55  call    cs:__imp_CloseHandle
0x180005c5b  mov     ecx, ebx; dwErrCode
0x180005c5d  call    cs:__imp_SetLastError
0x180005c63  mov     cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, rdi; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_SvcStopEvent
0x180005c6a  lea     rax, [rdi+1]
0x180005c6e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180005c74  jnz     short loc_180005CC4
0x180005c76  mov     rax, cs:WPP_GLOBAL_Control
0x180005c7d  cmp     rax, r14
0x180005c80  jz      short loc_180005CAC
0x180005c82  test    byte ptr [rax+1Ch], 80h
0x180005c86  jz      short loc_180005CAC
0x180005c88  cmp     byte ptr [rax+19h], 2
0x180005c8c  jb      short loc_180005CAC
0x180005c8e  call    cs:__imp_GetLastError
0x180005c94  mov     edx, 0Dh
0x180005c99  mov     r9d, eax
0x180005c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ca3  mov     rcx, [rcx+10h]
0x180005ca7  call    WPP_SF_D
0x180005cac  call    cs:__imp_GetLastError
0x180005cb2  mov     edx, eax; unsigned int
0x180005cb4  xor     r8d, r8d; unsigned int
0x180005cb7  mov     ecx, r15d; unsigned int
0x180005cba  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x180005cbf  jmp     loc_180005E9D
0x180005cc4  mov     ebx, 0Ch
0x180005cc9  mov     ecx, ebx; Size
0x180005ccb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cd0  mov     [rsp+58h+arg_8], rax
0x180005cd5  mov     qword ptr [rax], 0
0x180005cdc  mov     byte ptr [rax+8], 0
0x180005ce0  mov     rcx, cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A; Block
0x180005ce7  mov     cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A, rax; std::unique_ptr<CApxSvc> g_ApxService
0x180005cee  test    rcx, rcx
0x180005cf1  jz      short loc_180005D01
0x180005cf3  mov     edx, ebx
0x180005cf5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005cfa  mov     rax, cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A; std::unique_ptr<CApxSvc> g_ApxService
0x180005d01  test    rax, rax
0x180005d04  jnz     short loc_180005D34
0x180005d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d0d  cmp     rcx, r14
0x180005d10  jz      short loc_180005D2D
0x180005d12  test    byte ptr [rcx+1Ch], 80h
0x180005d16  jz      short loc_180005D2D
0x180005d18  cmp     byte ptr [rcx+19h], 2
0x180005d1c  jb      short loc_180005D2D
0x180005d1e  lea     edx, [rax+0Eh]
0x180005d21  mov     r8, r12
0x180005d24  mov     rcx, [rcx+10h]
0x180005d28  call    WPP_SF_
0x180005d2d  mov     edx, 8
0x180005d32  jmp     short loc_180005CB4
0x180005d34  cmp     cs:pti, 0
0x180005d3c  jnz     loc_180005E66
0x180005d42  mov     cs:dword_18000E1FC, 78h ; 'x'
0x180005d4c  mov     cs:dword_18000E4C8, 0
0x180005d56  xor     r8d, r8d; pcbe
0x180005d59  xor     edx, edx; pv
0x180005d5b  lea     rcx, _anonymous_namespace___TimerCallback; pfnti
0x180005d62  call    cs:__imp_CreateThreadpoolTimer
0x180005d68  mov     cs:pti, rax
0x180005d6f  test    rax, rax
0x180005d72  jz      loc_180005E66
0x180005d78  call    _anonymous_namespace___SetShutdownTimer
0x180005d7d  test    eax, eax
0x180005d7f  jz      loc_180005E66
0x180005d85  mov     byte ptr [rsp+58h+arg_0], r15b
0x180005d8a  mov     rcx, cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A; this
0x180005d91  call    ?Initialize@CApxSvc@@QEAAJXZ; CApxSvc::Initialize(void)
0x180005d96  mov     ebx, eax
0x180005d98  test    eax, eax
0x180005d9a  jns     short loc_180005DCF
0x180005d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005da3  cmp     rcx, r14
0x180005da6  jz      short loc_180005DC8
0x180005da8  test    byte ptr [rcx+1Ch], 80h
0x180005dac  jz      short loc_180005DC8
0x180005dae  cmp     byte ptr [rcx+19h], 2
0x180005db2  jb      short loc_180005DC8
0x180005db4  mov     edx, 10h
0x180005db9  mov     r9d, eax
0x180005dbc  mov     r8, r12
0x180005dbf  mov     rcx, [rcx+10h]
0x180005dc3  call    WPP_SF_d
0x180005dc8  mov     edx, ebx
0x180005dca  jmp     loc_180005CB4
0x180005dcf  xor     r8d, r8d; unsigned int
0x180005dd2  xor     edx, edx; unsigned int
0x180005dd4  lea     ecx, [rdx+4]; unsigned int
0x180005dd7  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x180005ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005de3  cmp     rcx, r14
0x180005de6  jz      short loc_180005E05
0x180005de8  test    byte ptr [rcx+1Ch], 80h
0x180005dec  jz      short loc_180005E05
0x180005dee  cmp     byte ptr [rcx+19h], 4
0x180005df2  jb      short loc_180005E05
0x180005df4  mov     edx, 11h
0x180005df9  mov     r8, r12
0x180005dfc  mov     rcx, [rcx+10h]
0x180005e00  call    WPP_SF_
0x180005e05  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005e08  mov     rcx, cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hHandle
0x180005e0f  call    cs:__imp_WaitForSingleObject
0x180005e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e1c  cmp     rcx, r14
0x180005e1f  jz      short loc_180005E3E
0x180005e21  test    byte ptr [rcx+1Ch], 80h
0x180005e25  jz      short loc_180005E3E
0x180005e27  cmp     byte ptr [rcx+19h], 4
0x180005e2b  jb      short loc_180005E3E
0x180005e2d  mov     edx, 12h
0x180005e32  mov     r8, r12
0x180005e35  mov     rcx, [rcx+10h]
0x180005e39  call    WPP_SF_
0x180005e3e  mov     rcx, cs:?g_ApxService@@3V?$unique_ptr@VCApxSvc@@U?$default_delete@VCApxSvc@@@std@@@std@@A; this
0x180005e45  call    ?Cleanup@CApxSvc@@QEAAJXZ; CApxSvc::Cleanup(void)
0x180005e4a  mov     ebx, eax
0x180005e4c  mov     rcx, [rsp+58h]; this
0x180005e51  test    eax, eax
0x180005e53  jns     loc_180005DC8
0x180005e59  mov     r9d, eax; char *
0x180005e5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005e61  jmp     loc_180005DC8
0x180005e66  mov     rax, cs:WPP_GLOBAL_Control
0x180005e6d  cmp     rax, r14
0x180005e70  jz      short loc_180005E9D
0x180005e72  test    byte ptr [rax+1Ch], 80h
0x180005e76  jz      short loc_180005E9D
0x180005e78  cmp     byte ptr [rax+19h], 2
0x180005e7c  jb      short loc_180005E9D
0x180005e7e  call    cs:__imp_GetLastError
0x180005e84  mov     edx, 0Fh
0x180005e89  mov     r9d, eax
0x180005e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e93  mov     rcx, [rcx+10h]
0x180005e97  call    WPP_SF_D
0x180005e9c  nop
0x180005e9d  lea     rcx, [rsp+58h+var_38]
0x180005ea2  call    wil__details__lambda_call__lambda_953d85168c89f2a2817997a2c632e42b______lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___
0x180005ea7  mov     rbx, [rsp+58h+arg_10]
0x180005eac  add     rsp, 30h
0x180005eb0  pop     r15
0x180005eb2  pop     r14
0x180005eb4  pop     r12
0x180005eb6  pop     rdi
0x180005eb7  pop     rsi
0x180005eb8  retn
```
