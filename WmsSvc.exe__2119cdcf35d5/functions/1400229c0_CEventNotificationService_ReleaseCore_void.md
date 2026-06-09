# CEventNotificationService::ReleaseCore(void)

- ea: `0x1400229c0`
- end: `0x140022d67`
- name: `?ReleaseCore@CEventNotificationService@@IEAAJXZ`
- size: `935`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1400221e0`
- `0x1400267d0`

## callees

- `0x140004730`
- `0x140004a04`
- `0x14001eb38`
- `0x1400229c0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14006eb38`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140022a86`
- `KERNEL32!IsDebuggerPresent` at `0x140022b2a`
- `KERNEL32!IsDebuggerPresent` at `0x140022ba2`
- `KERNEL32!IsDebuggerPresent` at `0x140022c1a`
- `KERNEL32!IsDebuggerPresent` at `0x140022ce5`
- `KERNEL32!IsDebuggerPresent` at `0x140022a86`
- `KERNEL32!IsDebuggerPresent` at `0x140022b2a`
- `KERNEL32!IsDebuggerPresent` at `0x140022ba2`
- `KERNEL32!IsDebuggerPresent` at `0x140022c1a`
- `KERNEL32!IsDebuggerPresent` at `0x140022ce5`

## string_xrefs

- `0x140022c00`: `m_hKillStationThreadEvent`
- `0x1400229ea`: `CEventNotificationService::ReleaseCore - Start\n`
- `0x140022a04`: `CEventNotificationService::ReleaseCore - m_modeCore = %s\n`
- `0x140022a30`: `m_pCore is already NULL; exiting`
- `0x140022a19`: `CEventNotificationService::ReleaseCore`
- `0x140022b88`: `m_hStationThread`
- `0x140022c6b`: `CEventNotificationService::ReleaseCore - Releasing m_pStationManager\n`
- `0x140022d36`: `CEventNotificationService::ReleaseCore - End\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::ReleaseCore(
        CEventNotificationService *this,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rax
  const unsigned __int16 *v6; // r9
  int v7; // ebp
  __int64 v8; // rcx
  CEventNotificationService *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *v12; // r9
  PSRWLOCK v14; // [rsp+70h] [rbp+8h] BYREF

  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v14, (CEventNotificationService *)((char *)this + 2312), a3, a4);
  DEBUGMSG(L"CEventNotificationService::ReleaseCore - Start\n");
  v5 = Utils::WmsModeToString(*((unsigned int *)this + 114));
  DEBUGMSG(L"CEventNotificationService::ReleaseCore - m_modeCore = %s\n", v5);
  v7 = 0;
  if ( *((_QWORD *)this + 56) )
  {
    if ( !*((_DWORD *)this + 114) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x16Fu,
        L"CEventNotificationService::ReleaseCore",
        v6,
        L"m_modeCore != WM_Invalid");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          367,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_modeCore != WM_Invalid");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          367,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_modeCore != WM_Invalid");
    }
    v8 = *((_QWORD *)this + 56);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 56) = 0;
    }
    if ( *((_DWORD *)this + 114) != 2 )
      goto LABEL_25;
    if ( !*((_QWORD *)this + 65) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x175u,
        L"CEventNotificationService::ReleaseCore",
        v6,
        L"m_pStationManager");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          373,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_pStationManager");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          373,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_pStationManager");
    }
    if ( !*((_QWORD *)this + 13) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x176u,
        L"CEventNotificationService::ReleaseCore",
        v6,
        L"m_hStationThread");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          374,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_hStationThread");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          374,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_hStationThread");
    }
    if ( !*((_QWORD *)this + 15) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x177u,
        L"CEventNotificationService::ReleaseCore",
        v6,
        L"m_hKillStationThreadEvent");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          375,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_hKillStationThreadEvent");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          375,
          L"CEventNotificationService::ReleaseCore",
          L"ASSERT",
          L"m_hKillStationThreadEvent");
    }
    DEBUGMSG(L"CEventNotificationService::ReleaseCore - Releasing m_pStationManager\n");
    v9 = (CEventNotificationService *)*((_QWORD *)this + 65);
    if ( v9 )
    {
      (*(void (__fastcall **)(CEventNotificationService *))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 65) = 0;
    }
    v7 = CEventNotificationService::KillThread(v9, L"Station", (void **)this + 13, *((void **)this + 15));
    if ( v7 >= 0 )
LABEL_25:
      *((_DWORD *)this + 114) = 0;
  }
  else
  {
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      364,
      L"CEventNotificationService::ReleaseCore",
      L"m_pCore is already NULL; exiting");
  }
  if ( *((_DWORD *)this + 114) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x184u,
      L"CEventNotificationService::ReleaseCore",
      v6,
      L"m_modeCore == WM_Invalid");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        388,
        L"CEventNotificationService::ReleaseCore",
        L"ASSERT",
        L"m_modeCore == WM_Invalid");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        388,
        L"CEventNotificationService::ReleaseCore",
        L"ASSERT",
        L"m_modeCore == WM_Invalid");
  }
  DEBUGMSG(L"CEventNotificationService::ReleaseCore - End\n");
  CAutoWriteLock::~CAutoWriteLock(&v14, v10, v11, v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400229c0  mov     [rsp+arg_8], rbx
0x1400229c5  mov     [rsp+arg_10], rbp
0x1400229ca  push    rsi
0x1400229cb  push    rdi
0x1400229cc  push    r12
0x1400229ce  push    r13
0x1400229d0  push    r15
0x1400229d2  sub     rsp, 40h
0x1400229d6  mov     rbx, rcx
0x1400229d9  lea     rdx, [rcx+908h]; struct CSharedReaderWriterLock *
0x1400229e0  lea     rcx, [rsp+68h+arg_0]; this
0x1400229e5  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x1400229ea  lea     rcx, aCeventnotifica_154; "CEventNotificationService::ReleaseCore "...
0x1400229f1  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400229f6  mov     ecx, [rbx+1C8h]
0x1400229fc  call    ?WmsModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0001@@@Z; Utils::WmsModeToString(__MIDL___MIDL_itf_wmssvc_0000_0000_0001)
0x140022a01  mov     rdx, rax
0x140022a04  lea     rcx, aCeventnotifica_120; "CEventNotificationService::ReleaseCore "...
0x140022a0b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140022a10  xor     ebp, ebp
0x140022a12  lea     r12, aAssert; "ASSERT"
0x140022a19  lea     rsi, aCeventnotifica_1; "CEventNotificationService::ReleaseCore"
0x140022a20  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140022a27  cmp     [rbx+1C0h], rbp
0x140022a2e  jnz     short loc_140022A5E
0x140022a30  lea     rax, aMPcoreIsAlread; "m_pCore is already NULL; exiting"
0x140022a37  mov     r9d, 16Ch
0x140022a3d  mov     [rsp+68h+var_40], rax
0x140022a42  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140022a49  mov     r8, rdi
0x140022a4c  mov     [rsp+68h+var_48], rsi
0x140022a51  lea     ecx, [rbp+4]; unsigned __int8
0x140022a54  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022a59  jmp     loc_140022CBE
0x140022a5e  cmp     [rbx+1C8h], ebp
0x140022a64  jnz     short loc_140022AD7
0x140022a66  mov     r15d, 16Fh
0x140022a6c  lea     r13, aMModecoreWmInv_0; "m_modeCore != WM_Invalid"
0x140022a73  mov     edx, r15d; unsigned int
0x140022a76  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x140022a7b  mov     r8, rsi; unsigned __int16 *
0x140022a7e  mov     rcx, rdi; unsigned __int16 *
0x140022a81  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022a86  call    cs:__imp_IsDebuggerPresent
0x140022a8c  test    eax, eax
0x140022a8e  jz      short loc_140022AB8
0x140022a90  mov     [rsp+68h+var_38], r13
0x140022a95  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022a9c  mov     [rsp+68h+var_40], r12
0x140022aa1  mov     r9d, r15d
0x140022aa4  mov     r8, rdi
0x140022aa7  mov     [rsp+68h+var_48], rsi
0x140022aac  mov     ecx, 2; unsigned __int8
0x140022ab1  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022ab6  jmp     short loc_140022AD7
0x140022ab8  mov     [rsp+68h+var_40], r13
0x140022abd  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022ac4  mov     r9, rsi
0x140022ac7  mov     [rsp+68h+var_48], r12
0x140022acc  mov     r8d, r15d
0x140022acf  mov     rdx, rdi
0x140022ad2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140022ad7  mov     rcx, [rbx+1C0h]
0x140022ade  test    rcx, rcx
0x140022ae1  jz      short loc_140022AF6
0x140022ae3  mov     rax, [rcx]
0x140022ae6  mov     rax, [rax+10h]
0x140022aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022aef  mov     [rbx+1C0h], rbp
0x140022af6  cmp     dword ptr [rbx+1C8h], 2
0x140022afd  jnz     loc_140022CB4
0x140022b03  cmp     [rbx+208h], rbp
0x140022b0a  jnz     short loc_140022B7B
0x140022b0c  mov     ebp, 175h
0x140022b11  lea     r15, aMPstationmanag_1; "m_pStationManager"
0x140022b18  mov     edx, ebp; unsigned int
0x140022b1a  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x140022b1f  mov     r8, rsi; unsigned __int16 *
0x140022b22  mov     rcx, rdi; unsigned __int16 *
0x140022b25  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022b2a  call    cs:__imp_IsDebuggerPresent
0x140022b30  test    eax, eax
0x140022b32  jz      short loc_140022B5C
0x140022b34  mov     [rsp+68h+var_38], r15
0x140022b39  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022b40  mov     [rsp+68h+var_40], r12
0x140022b45  mov     r9d, ebp
0x140022b48  mov     r8, rdi
0x140022b4b  mov     [rsp+68h+var_48], rsi
0x140022b50  mov     ecx, 2; unsigned __int8
0x140022b55  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022b5a  jmp     short loc_140022B7B
0x140022b5c  mov     [rsp+68h+var_40], r15
0x140022b61  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022b68  mov     r9, rsi
0x140022b6b  mov     [rsp+68h+var_48], r12
0x140022b70  mov     r8d, ebp
0x140022b73  mov     rdx, rdi
0x140022b76  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140022b7b  cmp     qword ptr [rbx+68h], 0
0x140022b80  jnz     short loc_140022BF3
0x140022b82  mov     r15d, 176h
0x140022b88  lea     r13, aMHstationthrea; "m_hStationThread"
0x140022b8f  mov     edx, r15d; unsigned int
0x140022b92  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x140022b97  mov     r8, rsi; unsigned __int16 *
0x140022b9a  mov     rcx, rdi; unsigned __int16 *
0x140022b9d  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022ba2  call    cs:__imp_IsDebuggerPresent
0x140022ba8  test    eax, eax
0x140022baa  jz      short loc_140022BD4
0x140022bac  mov     [rsp+68h+var_38], r13
0x140022bb1  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022bb8  mov     [rsp+68h+var_40], r12
0x140022bbd  mov     r9d, r15d
0x140022bc0  mov     r8, rdi
0x140022bc3  mov     [rsp+68h+var_48], rsi
0x140022bc8  mov     ecx, 2; unsigned __int8
0x140022bcd  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022bd2  jmp     short loc_140022BF3
0x140022bd4  mov     [rsp+68h+var_40], r13
0x140022bd9  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022be0  mov     r9, rsi
0x140022be3  mov     [rsp+68h+var_48], r12
0x140022be8  mov     r8d, r15d
0x140022beb  mov     rdx, rdi
0x140022bee  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140022bf3  cmp     qword ptr [rbx+78h], 0
0x140022bf8  jnz     short loc_140022C6B
0x140022bfa  mov     r15d, 177h
0x140022c00  lea     r13, aMHkillstationt; "m_hKillStationThreadEvent"
0x140022c07  mov     edx, r15d; unsigned int
0x140022c0a  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x140022c0f  mov     r8, rsi; unsigned __int16 *
0x140022c12  mov     rcx, rdi; unsigned __int16 *
0x140022c15  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022c1a  call    cs:__imp_IsDebuggerPresent
0x140022c20  test    eax, eax
0x140022c22  jz      short loc_140022C4C
0x140022c24  mov     [rsp+68h+var_38], r13
0x140022c29  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022c30  mov     [rsp+68h+var_40], r12
0x140022c35  mov     r9d, r15d
0x140022c38  mov     r8, rdi
0x140022c3b  mov     [rsp+68h+var_48], rsi
0x140022c40  mov     ecx, 2; unsigned __int8
0x140022c45  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022c4a  jmp     short loc_140022C6B
0x140022c4c  mov     [rsp+68h+var_40], r13
0x140022c51  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022c58  mov     r9, rsi
0x140022c5b  mov     [rsp+68h+var_48], r12
0x140022c60  mov     r8d, r15d
0x140022c63  mov     rdx, rdi
0x140022c66  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140022c6b  lea     rcx, aCeventnotifica_43; "CEventNotificationService::ReleaseCore "...
0x140022c72  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140022c77  mov     rcx, [rbx+208h]
0x140022c7e  test    rcx, rcx
0x140022c81  jz      short loc_140022C9A
0x140022c83  mov     rax, [rcx]
0x140022c86  mov     rax, [rax+10h]
0x140022c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022c8f  mov     qword ptr [rbx+208h], 0
0x140022c9a  mov     r9, [rbx+78h]; void *
0x140022c9e  lea     r8, [rbx+68h]; void **
0x140022ca2  lea     rdx, aStation; "Station"
0x140022ca9  call    ?KillThread@CEventNotificationService@@IEAAJPEBGPEAPEAXPEAX@Z; CEventNotificationService::KillThread(ushort const *,void * *,void *)
0x140022cae  mov     ebp, eax
0x140022cb0  test    eax, eax
0x140022cb2  js      short loc_140022CBE
0x140022cb4  mov     dword ptr [rbx+1C8h], 0
0x140022cbe  cmp     dword ptr [rbx+1C8h], 0
0x140022cc5  jz      short loc_140022D36
0x140022cc7  mov     ebx, 184h
0x140022ccc  lea     r15, aMModecoreWmInv; "m_modeCore == WM_Invalid"
0x140022cd3  mov     edx, ebx; unsigned int
0x140022cd5  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x140022cda  mov     r8, rsi; unsigned __int16 *
0x140022cdd  mov     rcx, rdi; unsigned __int16 *
0x140022ce0  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022ce5  call    cs:__imp_IsDebuggerPresent
0x140022ceb  test    eax, eax
0x140022ced  jz      short loc_140022D17
0x140022cef  mov     [rsp+68h+var_38], r15
0x140022cf4  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022cfb  mov     [rsp+68h+var_40], r12
0x140022d00  mov     r9d, ebx
0x140022d03  mov     r8, rdi
0x140022d06  mov     [rsp+68h+var_48], rsi
0x140022d0b  mov     ecx, 2; unsigned __int8
0x140022d10  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022d15  jmp     short loc_140022D36
0x140022d17  mov     [rsp+68h+var_40], r15
0x140022d1c  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022d23  mov     r9, rsi
0x140022d26  mov     [rsp+68h+var_48], r12
0x140022d2b  mov     r8d, ebx
0x140022d2e  mov     rdx, rdi
0x140022d31  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140022d36  lea     rcx, aCeventnotifica_155; "CEventNotificationService::ReleaseCore "...
0x140022d3d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140022d42  lea     rcx, [rsp+68h+arg_0]; this
0x140022d47  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x140022d4c  lea     r11, [rsp+68h+var_28]
0x140022d51  mov     eax, ebp
0x140022d53  mov     rbx, [r11+38h]
0x140022d57  mov     rbp, [r11+40h]
0x140022d5b  mov     rsp, r11
0x140022d5e  pop     r15
0x140022d60  pop     r13
0x140022d62  pop     r12
0x140022d64  pop     rdi
0x140022d65  pop     rsi
0x140022d66  retn
```
