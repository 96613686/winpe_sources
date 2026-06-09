# CEventNotificationService::StationThreadProc(void)

- ea: `0x140025330`
- end: `0x140025703`
- name: `?StationThreadProc@CEventNotificationService@@IEAAJXZ`
- size: `979`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140028a60`

## callees

- `0x140025330`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x1400686c8`
- `0x14007e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140025699`
- `KERNEL32!SetEvent` at `0x140025699`
- `KERNEL32!IsDebuggerPresent` at `0x1400253a1`
- `KERNEL32!IsDebuggerPresent` at `0x14002543a`
- `KERNEL32!IsDebuggerPresent` at `0x1400254b6`
- `KERNEL32!IsDebuggerPresent` at `0x140025566`
- `KERNEL32!IsDebuggerPresent` at `0x140025624`
- `KERNEL32!IsDebuggerPresent` at `0x1400253a1`
- `KERNEL32!IsDebuggerPresent` at `0x14002543a`
- `KERNEL32!IsDebuggerPresent` at `0x1400254b6`
- `KERNEL32!IsDebuggerPresent` at `0x140025566`
- `KERNEL32!IsDebuggerPresent` at `0x140025624`
- `ole32!CoUninitialize` at `0x1400256dc`
- `ole32!CoUninitialize` at `0x1400256dc`
- `ole32!CoInitializeEx` at `0x140025355`
- `ole32!CoInitializeEx` at `0x140025355`
- `ole32!CoCreateInstance` at `0x14002552c`
- `ole32!CoCreateInstance` at `0x14002552c`

## string_xrefs

- `0x14002535b`: `CEventNotificationService::StationThreadProc`
- `0x140025498`: `m_hStationReadyEvent != NULL`
- `0x1400254be`: `m_hStationReadyEvent != NULL`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::StationThreadProc(CEventNotificationService *this)
{
  HRESULT v2; // eax
  const unsigned __int16 *v3; // r9
  int v4; // ebx
  LPVOID *v5; // r14
  HRESULT v6; // eax
  const unsigned __int16 *v7; // r9
  void *v8; // rcx
  HWND v9; // rdx
  __int64 v11; // [rsp+30h] [rbp-38h]
  int v12; // [rsp+30h] [rbp-38h]
  int v13; // [rsp+38h] [rbp-30h]
  int v14; // [rsp+38h] [rbp-30h]
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  ppv = 0;
  v2 = CoInitializeEx(0, 0);
  v4 = v2;
  if ( v2 >= 0 )
  {
    v5 = (LPVOID *)((char *)this + 520);
    if ( *((_QWORD *)this + 65) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x173Eu,
        L"CEventNotificationService::StationThreadProc",
        v3,
        L"m_pStationManager == NULL");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5950,
          L"CEventNotificationService::StationThreadProc",
          L"ASSERT",
          L"m_pStationManager == NULL");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5950,
          L"CEventNotificationService::StationThreadProc",
          L"ASSERT",
          L"m_pStationManager == NULL");
    }
    if ( !*((_QWORD *)this + 14) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x173Fu,
        L"CEventNotificationService::StationThreadProc",
        v3,
        L"m_hStationReadyEvent != NULL");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5951,
          L"CEventNotificationService::StationThreadProc",
          L"ASSERT",
          L"m_hStationReadyEvent != NULL");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5951,
          L"CEventNotificationService::StationThreadProc",
          L"ASSERT",
          L"m_hStationReadyEvent != NULL");
    }
    v6 = CoCreateInstance(&CLSID_SrcStationManager, 0, 1u, &GUID_c23f7c94_a678_4a6e_a693_2d9d2a5371ff, &ppv);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, unsigned __int64))(*(_QWORD *)ppv + 24LL))(
             ppv,
             2,
             0,
             ((unsigned __int64)this + 8) & -(__int64)(this != 0));
      if ( v4 >= 0 )
      {
        if ( !*((_QWORD *)this + 56) )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0x174Fu,
            L"CEventNotificationService::StationThreadProc",
            v7,
            L"m_pCore");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              5967,
              L"CEventNotificationService::StationThreadProc",
              L"ASSERT",
              L"m_pCore");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              5967,
              L"CEventNotificationService::StationThreadProc",
              L"ASSERT",
              L"m_pCore");
        }
        v8 = (void *)*((_QWORD *)this + 14);
        *v5 = ppv;
        ppv = 0;
        *((_DWORD *)this + 32) = v4;
        SetEvent(v8);
        v4 = SafeOuterMessagePump(*((void **)this + 15), v9);
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x1748u,
        L"CEventNotificationService::StationThreadProc",
        L"CHRA",
        L"hr",
        v6);
      if ( IsDebuggerPresent() )
      {
        v14 = v4;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5960,
          L"CEventNotificationService::StationThreadProc",
          L"CHRA",
          L"hr",
          v14);
      }
      else
      {
        LODWORD(v11) = v4;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          5960,
          L"CEventNotificationService::StationThreadProc",
          L"CHRA",
          L"hr",
          v11);
      }
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x173Cu,
      L"CEventNotificationService::StationThreadProc",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
    {
      v13 = v4;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        5948,
        L"CEventNotificationService::StationThreadProc",
        L"CHRA",
        L"hr",
        v13);
    }
    else
    {
      v12 = v4;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        5948,
        L"CEventNotificationService::StationThreadProc",
        L"CHRA",
        L"hr",
        v12);
    }
    v5 = (LPVOID *)((char *)this + 520);
  }
  if ( *v5 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v5 + 16LL))(*v5);
    *v5 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  CoUninitialize();
  *((_DWORD *)this + 32) = v4;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140025330  mov     [rsp+arg_8], rbx
0x140025335  mov     [rsp+arg_10], rbp
0x14002533a  push    rsi
0x14002533b  push    rdi
0x14002533c  push    r12
0x14002533e  push    r14
0x140025340  push    r15
0x140025342  sub     rsp, 40h
0x140025346  mov     rbp, rcx
0x140025349  xor     r15d, r15d
0x14002534c  xor     ecx, ecx; pvReserved
0x14002534e  mov     [rsp+68h+arg_0], r15
0x140025353  xor     edx, edx; dwCoInit
0x140025355  call    cs:__imp_CoInitializeEx
0x14002535b  lea     rsi, aCeventnotifica_112; "CEventNotificationService::StationThrea"...
0x140025362  mov     ebx, eax
0x140025364  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002536b  test    eax, eax
0x14002536d  jns     loc_140025409
0x140025373  mov     [rsp+68h+var_40], eax; int
0x140025377  lea     r12, aChra; "CHRA"
0x14002537e  mov     r14d, 173Ch
0x140025384  lea     r15, aHr; "hr"
0x14002538b  mov     r9, r12; unsigned __int16 *
0x14002538e  mov     [rsp+68h+ppv], r15; unsigned __int16 *
0x140025393  mov     edx, r14d; unsigned int
0x140025396  mov     r8, rsi; unsigned __int16 *
0x140025399  mov     rcx, rdi; unsigned __int16 *
0x14002539c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400253a1  call    cs:__imp_IsDebuggerPresent
0x1400253a7  test    eax, eax
0x1400253a9  jz      short loc_1400253D7
0x1400253ab  mov     [rsp+68h+var_30], ebx
0x1400253af  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400253b6  mov     [rsp+68h+var_38], r15
0x1400253bb  mov     r9d, r14d
0x1400253be  mov     qword ptr [rsp+68h+var_40], r12
0x1400253c3  mov     r8, rdi
0x1400253c6  mov     ecx, 2; unsigned __int8
0x1400253cb  mov     [rsp+68h+ppv], rsi
0x1400253d0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400253d5  jmp     short loc_1400253FA
0x1400253d7  mov     dword ptr [rsp+68h+var_38], ebx
0x1400253db  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400253e2  mov     qword ptr [rsp+68h+var_40], r15
0x1400253e7  mov     r9, rsi
0x1400253ea  mov     r8d, r14d
0x1400253ed  mov     [rsp+68h+ppv], r12
0x1400253f2  mov     rdx, rdi
0x1400253f5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400253fa  lea     r14, [rbp+208h]
0x140025401  xor     r15d, r15d
0x140025404  jmp     loc_1400256AA
0x140025409  lea     r14, [rbp+208h]
0x140025410  lea     r12, aAssert; "ASSERT"
0x140025417  cmp     [r14], r15
0x14002541a  jz      short loc_140025492
0x14002541c  lea     rax, aMPstationmanag_0; "m_pStationManager == NULL"
0x140025423  mov     ebx, 173Eh
0x140025428  mov     edx, ebx; unsigned int
0x14002542a  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x14002542f  mov     r8, rsi; unsigned __int16 *
0x140025432  mov     rcx, rdi; unsigned __int16 *
0x140025435  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14002543a  call    cs:__imp_IsDebuggerPresent
0x140025440  test    eax, eax
0x140025442  lea     rax, aMPstationmanag_0; "m_pStationManager == NULL"
0x140025449  jz      short loc_140025473
0x14002544b  mov     [rsp+68h+var_38], rax
0x140025450  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140025457  mov     qword ptr [rsp+68h+var_40], r12
0x14002545c  mov     r9d, ebx
0x14002545f  mov     r8, rdi
0x140025462  mov     [rsp+68h+ppv], rsi
0x140025467  mov     ecx, 2; unsigned __int8
0x14002546c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140025471  jmp     short loc_140025492
0x140025473  mov     qword ptr [rsp+68h+var_40], rax
0x140025478  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002547f  mov     r9, rsi
0x140025482  mov     [rsp+68h+ppv], r12
0x140025487  mov     r8d, ebx
0x14002548a  mov     rdx, rdi
0x14002548d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140025492  cmp     [rbp+70h], r15
0x140025496  jnz     short loc_14002550E
0x140025498  lea     rax, aMHstationready_0; "m_hStationReadyEvent != NULL"
0x14002549f  mov     ebx, 173Fh
0x1400254a4  mov     edx, ebx; unsigned int
0x1400254a6  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x1400254ab  mov     r8, rsi; unsigned __int16 *
0x1400254ae  mov     rcx, rdi; unsigned __int16 *
0x1400254b1  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400254b6  call    cs:__imp_IsDebuggerPresent
0x1400254bc  test    eax, eax
0x1400254be  lea     rax, aMHstationready_0; "m_hStationReadyEvent != NULL"
0x1400254c5  jz      short loc_1400254EF
0x1400254c7  mov     [rsp+68h+var_38], rax
0x1400254cc  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400254d3  mov     qword ptr [rsp+68h+var_40], r12
0x1400254d8  mov     r9d, ebx
0x1400254db  mov     r8, rdi
0x1400254de  mov     [rsp+68h+ppv], rsi
0x1400254e3  mov     ecx, 2; unsigned __int8
0x1400254e8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400254ed  jmp     short loc_14002550E
0x1400254ef  mov     qword ptr [rsp+68h+var_40], rax
0x1400254f4  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400254fb  mov     r9, rsi
0x1400254fe  mov     [rsp+68h+ppv], r12
0x140025503  mov     r8d, ebx
0x140025506  mov     rdx, rdi
0x140025509  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002550e  xor     edx, edx; pUnkOuter
0x140025510  lea     rax, [rsp+68h+arg_0]
0x140025515  lea     r9, _GUID_c23f7c94_a678_4a6e_a693_2d9d2a5371ff; riid
0x14002551c  mov     [rsp+68h+ppv], rax; ppv
0x140025521  lea     rcx, CLSID_SrcStationManager; rclsid
0x140025528  lea     r8d, [rdx+1]; dwClsContext
0x14002552c  call    cs:__imp_CoCreateInstance
0x140025532  mov     ebx, eax
0x140025534  test    eax, eax
0x140025536  jns     loc_1400255CD
0x14002553c  mov     [rsp+68h+var_40], eax; int
0x140025540  lea     r12, aChra; "CHRA"
0x140025547  lea     r15, aHr; "hr"
0x14002554e  mov     r9, r12; unsigned __int16 *
0x140025551  mov     r8, rsi; unsigned __int16 *
0x140025554  mov     [rsp+68h+ppv], r15; unsigned __int16 *
0x140025559  mov     edx, 1748h; unsigned int
0x14002555e  mov     rcx, rdi; unsigned __int16 *
0x140025561  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140025566  call    cs:__imp_IsDebuggerPresent
0x14002556c  test    eax, eax
0x14002556e  jz      short loc_1400255A2
0x140025570  mov     [rsp+68h+var_30], ebx
0x140025574  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002557b  mov     [rsp+68h+var_38], r15
0x140025580  mov     r9d, 1748h
0x140025586  mov     qword ptr [rsp+68h+var_40], r12
0x14002558b  mov     r8, rdi
0x14002558e  mov     ecx, 2; unsigned __int8
0x140025593  mov     [rsp+68h+ppv], rsi
0x140025598  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002559d  jmp     loc_140025401
0x1400255a2  mov     dword ptr [rsp+68h+var_38], ebx
0x1400255a6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400255ad  mov     qword ptr [rsp+68h+var_40], r15
0x1400255b2  mov     r9, rsi
0x1400255b5  mov     r8d, 1748h
0x1400255bb  mov     [rsp+68h+ppv], r12
0x1400255c0  mov     rdx, rdi
0x1400255c3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400255c8  jmp     loc_140025401
0x1400255cd  mov     rcx, [rsp+68h+arg_0]
0x1400255d2  lea     rdx, [rbp+8]
0x1400255d6  mov     rax, rbp
0x1400255d9  neg     rax
0x1400255dc  mov     r8, [rcx]
0x1400255df  sbb     r9, r9
0x1400255e2  and     r9, rdx
0x1400255e5  mov     rax, [r8+18h]
0x1400255e9  xor     r8d, r8d
0x1400255ec  lea     edx, [r8+2]
0x1400255f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255f5  mov     ebx, eax
0x1400255f7  test    eax, eax
0x1400255f9  js      loc_1400256AA
0x1400255ff  cmp     [rbp+1C0h], r15
0x140025606  jnz     short loc_140025682
0x140025608  lea     rax, aMPcore; "m_pCore"
0x14002560f  mov     r8, rsi; unsigned __int16 *
0x140025612  mov     edx, 174Fh; unsigned int
0x140025617  mov     [rsp+68h+ppv], rax; unsigned __int16 *
0x14002561c  mov     rcx, rdi; unsigned __int16 *
0x14002561f  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140025624  call    cs:__imp_IsDebuggerPresent
0x14002562a  test    eax, eax
0x14002562c  lea     rax, aMPcore; "m_pCore"
0x140025633  jz      short loc_140025660
0x140025635  mov     [rsp+68h+var_38], rax
0x14002563a  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140025641  mov     qword ptr [rsp+68h+var_40], r12
0x140025646  mov     r9d, 174Fh
0x14002564c  mov     r8, rdi
0x14002564f  mov     [rsp+68h+ppv], rsi
0x140025654  mov     ecx, 2; unsigned __int8
0x140025659  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002565e  jmp     short loc_140025682
0x140025660  mov     qword ptr [rsp+68h+var_40], rax
0x140025665  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002566c  mov     r9, rsi
0x14002566f  mov     [rsp+68h+ppv], r12
0x140025674  mov     r8d, 174Fh
0x14002567a  mov     rdx, rdi
0x14002567d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140025682  mov     rax, [rsp+68h+arg_0]
0x140025687  mov     rcx, [rbp+70h]; hEvent
0x14002568b  mov     [r14], rax
0x14002568e  mov     [rsp+68h+arg_0], r15
0x140025693  mov     [rbp+80h], ebx
0x140025699  call    cs:__imp_SetEvent
0x14002569f  mov     rcx, [rbp+78h]; void *
0x1400256a3  call    ?SafeOuterMessagePump@@YAJPEAXPEAUHWND__@@@Z; SafeOuterMessagePump(void *,HWND__ *)
0x1400256a8  mov     ebx, eax
0x1400256aa  mov     rcx, [r14]
0x1400256ad  test    rcx, rcx
0x1400256b0  jz      short loc_1400256C1
0x1400256b2  mov     rax, [rcx]
0x1400256b5  mov     rax, [rax+10h]
0x1400256b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400256be  mov     [r14], r15
0x1400256c1  mov     rcx, [rsp+68h+arg_0]
0x1400256c6  test    rcx, rcx
0x1400256c9  jz      short loc_1400256DC
0x1400256cb  mov     rax, [rcx]
0x1400256ce  mov     rax, [rax+10h]
0x1400256d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400256d7  mov     [rsp+68h+arg_0], r15
0x1400256dc  call    cs:__imp_CoUninitialize
0x1400256e2  lea     r11, [rsp+68h+var_28]
0x1400256e7  mov     [rbp+80h], ebx
0x1400256ed  mov     rbp, [r11+40h]
0x1400256f1  mov     eax, ebx
0x1400256f3  mov     rbx, [r11+38h]
0x1400256f7  mov     rsp, r11
0x1400256fa  pop     r15
0x1400256fc  pop     r14
0x1400256fe  pop     r12
0x140025700  pop     rdi
0x140025701  pop     rsi
0x140025702  retn
```
