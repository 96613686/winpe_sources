# CUpdateManager::ProcessUpdateTime(void)

- ea: `0x140037a1c`
- end: `0x140037d8a`
- name: `?ProcessUpdateTime@CUpdateManager@@QEAAJXZ`
- size: `878`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14000a460`
- `0x14000bfb0`
- `0x1400372cc`

## callees

- `0x1400016b8`
- `0x140004730`
- `0x140004a04`
- `0x1400121f0`
- `0x14002feb4`
- `0x140037a1c`
- `0x140037e2c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140037ae4`
- `KERNEL32!IsDebuggerPresent` at `0x140037bc6`
- `KERNEL32!IsDebuggerPresent` at `0x140037ce4`
- `KERNEL32!IsDebuggerPresent` at `0x140037ae4`
- `KERNEL32!IsDebuggerPresent` at `0x140037bc6`
- `KERNEL32!IsDebuggerPresent` at `0x140037ce4`

## string_xrefs

- `0x140037ac0`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140037b9d`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140037cbd`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140037a84`: `DpSoftwareUpdateRunning`
- `0x140037a44`: `CUpdateManager::ProcessUpdateTime\n`
- `0x140037ab3`: `CUpdateManager::ProcessUpdateTime`
- `0x140037b96`: `CUpdateManager::ProcessUpdateTime`
- `0x140037cb6`: `CUpdateManager::ProcessUpdateTime`
- `0x140037bad`: `fDiskProtectionInstalled`
- `0x140037c1e`: `Currently in the update process, don't reset the timer!\n`
- `0x140037ccb`: `m_pUpdateTimer == NULL`
- `0x140037d3c`: `DP is in passive mode, let AU handle updates.\n`
- `0x140037c80`: `CUpdateManager::ClearUpdateTimers\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::ProcessUpdateTime(CUpdateManager *this)
{
  __int64 v2; // r8
  const unsigned __int16 *v3; // r9
  int Setting; // eax
  int Settings; // ebx
  unsigned int v6; // edi
  const unsigned __int16 *v7; // r9
  int v8; // eax
  const wchar_t *v9; // rax
  __int64 v10; // r9
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  int v16; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int v18; // [rsp+48h] [rbp-18h] BYREF
  void *Block; // [rsp+50h] [rbp-10h] BYREF
  PSRWLOCK v20; // [rsp+58h] [rbp-8h] BYREF
  int v21; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v22; // [rsp+A8h] [rbp+48h] BYREF
  int v23; // [rsp+B0h] [rbp+50h] BYREF
  int v24; // [rsp+B8h] [rbp+58h] BYREF

  v24 = 0;
  v18 = 0;
  v16 = 1;
  v23 = 1;
  Block = 0;
  v17 = 0;
  v22 = 0;
  v21 = 0;
  DEBUGMSG(L"CUpdateManager::ProcessUpdateTime\n");
  CAutoWriteLock::CAutoWriteLock((CAutoWriteLock *)&v20, (CUpdateManager *)((char *)this + 40), v2, v3);
  Setting = CDiskProtection::s_GetSetting(L"DpSoftwareUpdateRunning", &v22);
  Settings = Setting;
  if ( Setting == -2147024894 )
  {
    v6 = 0;
  }
  else
  {
    if ( Setting < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        0x376u,
        L"CUpdateManager::ProcessUpdateTime",
        L"CHRA",
        L"hr",
        Setting);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          886,
          L"CUpdateManager::ProcessUpdateTime",
          L"CHRA",
          L"hr",
          Settings);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          886,
          L"CUpdateManager::ProcessUpdateTime",
          L"CHRA",
          L"hr",
          Settings);
      goto LABEL_32;
    }
    v6 = v22;
  }
  Settings = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 40LL))(*((_QWORD *)this + 4), &v21);
  if ( Settings >= 0 )
  {
    v8 = v21;
    if ( v21 )
    {
      Settings = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 56LL))(
                   *((_QWORD *)this + 4),
                   &v23);
      if ( Settings < 0 )
        goto LABEL_32;
      v8 = v21;
    }
    if ( v6 )
    {
      if ( !v8 )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          0x389u,
          L"CUpdateManager::ProcessUpdateTime",
          v7,
          L"fDiskProtectionInstalled");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            905,
            L"CUpdateManager::ProcessUpdateTime",
            L"ASSERT",
            L"fDiskProtectionInstalled");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            905,
            L"CUpdateManager::ProcessUpdateTime",
            L"ASSERT",
            L"fDiskProtectionInstalled");
      }
      v9 = L"Currently in the update process, don't reset the timer!\n";
      v10 = 907;
LABEL_31:
      Settings = 0;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v10,
        L"CUpdateManager::ProcessUpdateTime",
        v9);
      goto LABEL_32;
    }
    if ( !v8 || !v23 )
    {
      if ( *((_QWORD *)this + 3) )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
          0x38Fu,
          L"CUpdateManager::ProcessUpdateTime",
          v7,
          L"m_pUpdateTimer == NULL");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            911,
            L"CUpdateManager::ProcessUpdateTime",
            L"ASSERT",
            L"m_pUpdateTimer == NULL");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            911,
            L"CUpdateManager::ProcessUpdateTime",
            L"ASSERT",
            L"m_pUpdateTimer == NULL");
      }
      v9 = L"DP is in passive mode, let AU handle updates.\n";
      v10 = 913;
      goto LABEL_31;
    }
    Settings = CSoftwareUpdates::GetSettings(
                 *((CSoftwareUpdates **)this + 2),
                 (enum __MIDL___MIDL_itf_wmssvc_0000_0000_0022 *)&v24,
                 &v18,
                 (unsigned __int16 **)&Block,
                 &v17,
                 (enum __MIDL___MIDL_itf_wmssvc_0000_0000_0023 *)&v16);
    if ( Settings >= 0 )
    {
      if ( v24 )
      {
        Settings = CUpdateManager::ResetUpdateTimers(this);
      }
      else
      {
        DEBUGMSG(L"CUpdateManager::ClearUpdateTimers\n");
        v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
        if ( v11 )
          (**v11)(v11, 1);
        *((_QWORD *)this + 3) = 0;
        Settings = 0;
      }
    }
  }
LABEL_32:
  operator delete(Block);
  CAutoWriteLock::~CAutoWriteLock(&v20, v12, v13, v14);
  return (unsigned int)Settings;
}

```

## disassembly

```asm
0x140037a1c  push    rbp
0x140037a1e  push    rbx
0x140037a1f  push    rsi
0x140037a20  push    rdi
0x140037a21  push    r12
0x140037a23  push    r13
0x140037a25  push    r14
0x140037a27  mov     rbp, rsp
0x140037a2a  sub     rsp, 60h
0x140037a2e  mov     r14, rcx
0x140037a31  mov     [rbp+arg_18], 0
0x140037a38  mov     esi, 1
0x140037a3d  mov     [rbp+var_18], 0
0x140037a44  lea     rcx, aCupdatemanager_23; "CUpdateManager::ProcessUpdateTime\n"
0x140037a4b  mov     [rbp+var_20], esi
0x140037a4e  mov     [rbp+arg_10], esi
0x140037a51  mov     [rbp+Block], 0
0x140037a59  mov     [rbp+var_1C], 0
0x140037a60  mov     [rbp+arg_8], 0
0x140037a67  mov     [rbp+arg_0], 0
0x140037a6e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037a73  lea     rdx, [r14+28h]; struct CSharedReaderWriterLock *
0x140037a77  lea     rcx, [rbp+var_8]; this
0x140037a7b  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x140037a80  lea     rdx, [rbp+arg_8]; unsigned int *
0x140037a84  lea     rcx, aDpsoftwareupda_3; "DpSoftwareUpdateRunning"
0x140037a8b  call    ?s_GetSetting@CDiskProtection@@SAJPEBGPEAK@Z; CDiskProtection::s_GetSetting(ushort const *,ulong *)
0x140037a90  mov     ebx, eax
0x140037a92  cmp     eax, 80070002h
0x140037a97  jnz     short loc_140037AA0
0x140037a99  xor     edi, edi
0x140037a9b  jmp     loc_140037B48
0x140037aa0  test    ebx, ebx
0x140037aa2  jns     loc_140037B45
0x140037aa8  lea     r13, aChra; "CHRA"
0x140037aaf  mov     dword ptr [rsp+60h+var_38], ebx; int
0x140037ab3  lea     rsi, aCupdatemanager_14; "CUpdateManager::ProcessUpdateTime"
0x140037aba  mov     r14d, 376h
0x140037ac0  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140037ac7  mov     r9, r13; unsigned __int16 *
0x140037aca  lea     r12, aHr; "hr"
0x140037ad1  mov     r8, rsi; unsigned __int16 *
0x140037ad4  mov     edx, r14d; unsigned int
0x140037ad7  mov     [rsp+60h+var_40], r12; unsigned __int16 *
0x140037adc  mov     rcx, rdi; unsigned __int16 *
0x140037adf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140037ae4  call    cs:__imp_IsDebuggerPresent
0x140037aea  test    eax, eax
0x140037aec  jz      short loc_140037B1D
0x140037aee  mov     [rsp+60h+var_28], ebx
0x140037af2  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140037af9  mov     [rsp+60h+var_30], r12
0x140037afe  mov     r9d, r14d
0x140037b01  mov     [rsp+60h+var_38], r13
0x140037b06  mov     r8, rdi
0x140037b09  mov     ecx, 2; unsigned __int8
0x140037b0e  mov     [rsp+60h+var_40], rsi
0x140037b13  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140037b18  jmp     loc_140037D67
0x140037b1d  mov     dword ptr [rsp+60h+var_30], ebx
0x140037b21  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140037b28  mov     [rsp+60h+var_38], r12
0x140037b2d  mov     r9, rsi
0x140037b30  mov     r8d, r14d
0x140037b33  mov     [rsp+60h+var_40], r13
0x140037b38  mov     rdx, rdi
0x140037b3b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140037b40  jmp     loc_140037D67
0x140037b45  mov     edi, [rbp+arg_8]
0x140037b48  mov     rcx, [r14+20h]
0x140037b4c  lea     rdx, [rbp+arg_0]
0x140037b50  mov     rax, [rcx]
0x140037b53  mov     rax, [rax+28h]
0x140037b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b5c  mov     ebx, eax
0x140037b5e  test    eax, eax
0x140037b60  js      loc_140037D67
0x140037b66  mov     eax, [rbp+arg_0]
0x140037b69  test    eax, eax
0x140037b6b  jz      short loc_140037B8E
0x140037b6d  mov     rcx, [r14+20h]
0x140037b71  lea     rdx, [rbp+arg_10]
0x140037b75  mov     rax, [rcx]
0x140037b78  mov     rax, [rax+38h]
0x140037b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b81  mov     ebx, eax
0x140037b83  test    eax, eax
0x140037b85  js      loc_140037D67
0x140037b8b  mov     eax, [rbp+arg_0]
0x140037b8e  test    edi, edi
0x140037b90  jz      loc_140037C30
0x140037b96  lea     rsi, aCupdatemanager_14; "CUpdateManager::ProcessUpdateTime"
0x140037b9d  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140037ba4  test    eax, eax
0x140037ba6  jnz     short loc_140037C1E
0x140037ba8  mov     ebx, 389h
0x140037bad  lea     r14, aFdiskprotectio; "fDiskProtectionInstalled"
0x140037bb4  mov     edx, ebx; unsigned int
0x140037bb6  mov     [rsp+60h+var_40], r14; unsigned __int16 *
0x140037bbb  mov     r8, rsi; unsigned __int16 *
0x140037bbe  mov     rcx, rdi; unsigned __int16 *
0x140037bc1  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140037bc6  call    cs:__imp_IsDebuggerPresent
0x140037bcc  test    eax, eax
0x140037bce  lea     rax, aAssert; "ASSERT"
0x140037bd5  jz      short loc_140037BFF
0x140037bd7  mov     [rsp+60h+var_30], r14
0x140037bdc  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140037be3  mov     [rsp+60h+var_38], rax
0x140037be8  mov     r9d, ebx
0x140037beb  mov     r8, rdi
0x140037bee  mov     [rsp+60h+var_40], rsi
0x140037bf3  mov     ecx, 2; unsigned __int8
0x140037bf8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140037bfd  jmp     short loc_140037C1E
0x140037bff  mov     [rsp+60h+var_38], r14
0x140037c04  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140037c0b  mov     r9, rsi
0x140037c0e  mov     [rsp+60h+var_40], rax
0x140037c13  mov     r8d, ebx
0x140037c16  mov     rdx, rdi
0x140037c19  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140037c1e  lea     rax, aCurrentlyInThe; "Currently in the update process, don't "...
0x140037c25  mov     r9d, 38Bh
0x140037c2b  jmp     loc_140037D49
0x140037c30  test    eax, eax
0x140037c32  jz      short loc_140037CB1
0x140037c34  cmp     [rbp+arg_10], 0
0x140037c38  jz      short loc_140037CB1
0x140037c3a  mov     rcx, [r14+10h]; this
0x140037c3e  lea     rax, [rbp+var_20]
0x140037c42  mov     [rsp+60h+var_38], rax; enum __MIDL___MIDL_itf_wmssvc_0000_0000_0023 *
0x140037c47  lea     r9, [rbp+Block]; unsigned __int16 **
0x140037c4b  lea     rax, [rbp+var_1C]
0x140037c4f  lea     r8, [rbp+var_18]; unsigned int *
0x140037c53  mov     [rsp+60h+var_40], rax; unsigned int *
0x140037c58  lea     rdx, [rbp+arg_18]; enum __MIDL___MIDL_itf_wmssvc_0000_0000_0022 *
0x140037c5c  call    ?GetSettings@CSoftwareUpdates@@QEAAJPEAW4__MIDL___MIDL_itf_wmssvc_0000_0000_0022@@PEAKPEAPEAG1PEAW4__MIDL___MIDL_itf_wmssvc_0000_0000_0023@@@Z; CSoftwareUpdates::GetSettings(__MIDL___MIDL_itf_wmssvc_0000_0000_0022 *,ulong *,ushort * *,ulong *,__MIDL___MIDL_itf_wmssvc_0000_0000_0023 *)
0x140037c61  mov     ebx, eax
0x140037c63  test    eax, eax
0x140037c65  js      loc_140037D67
0x140037c6b  cmp     [rbp+arg_18], 0
0x140037c6f  jz      short loc_140037C80
0x140037c71  mov     rcx, r14; this
0x140037c74  call    ?ResetUpdateTimers@CUpdateManager@@IEAAJXZ; CUpdateManager::ResetUpdateTimers(void)
0x140037c79  mov     ebx, eax
0x140037c7b  jmp     loc_140037D67
0x140037c80  lea     rcx, aCupdatemanager_55; "CUpdateManager::ClearUpdateTimers\n"
0x140037c87  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037c8c  mov     rcx, [r14+18h]
0x140037c90  test    rcx, rcx
0x140037c93  jz      short loc_140037CA2
0x140037c95  mov     rax, [rcx]
0x140037c98  mov     edx, esi
0x140037c9a  mov     rax, [rax]
0x140037c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ca2  mov     qword ptr [r14+18h], 0
0x140037caa  xor     ebx, ebx
0x140037cac  jmp     loc_140037D67
0x140037cb1  cmp     qword ptr [r14+18h], 0
0x140037cb6  lea     rsi, aCupdatemanager_14; "CUpdateManager::ProcessUpdateTime"
0x140037cbd  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140037cc4  jz      short loc_140037D3C
0x140037cc6  mov     ebx, 38Fh
0x140037ccb  lea     r14, aMPupdatetimerN; "m_pUpdateTimer == NULL"
0x140037cd2  mov     edx, ebx; unsigned int
0x140037cd4  mov     [rsp+60h+var_40], r14; unsigned __int16 *
0x140037cd9  mov     r8, rsi; unsigned __int16 *
0x140037cdc  mov     rcx, rdi; unsigned __int16 *
0x140037cdf  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140037ce4  call    cs:__imp_IsDebuggerPresent
0x140037cea  test    eax, eax
0x140037cec  lea     rax, aAssert; "ASSERT"
0x140037cf3  jz      short loc_140037D1D
0x140037cf5  mov     [rsp+60h+var_30], r14
0x140037cfa  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140037d01  mov     [rsp+60h+var_38], rax
0x140037d06  mov     r9d, ebx
0x140037d09  mov     r8, rdi
0x140037d0c  mov     [rsp+60h+var_40], rsi
0x140037d11  mov     ecx, 2; unsigned __int8
0x140037d16  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140037d1b  jmp     short loc_140037D3C
0x140037d1d  mov     [rsp+60h+var_38], r14
0x140037d22  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140037d29  mov     r9, rsi
0x140037d2c  mov     [rsp+60h+var_40], rax
0x140037d31  mov     r8d, ebx
0x140037d34  mov     rdx, rdi
0x140037d37  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140037d3c  lea     rax, aDpIsInPassiveM; "DP is in passive mode, let AU handle up"...
0x140037d43  mov     r9d, 391h
0x140037d49  xor     ebx, ebx
0x140037d4b  mov     [rsp+60h+var_38], rax
0x140037d50  mov     r8, rdi
0x140037d53  mov     [rsp+60h+var_40], rsi
0x140037d58  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140037d5f  lea     ecx, [rbx+4]; unsigned __int8
0x140037d62  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140037d67  mov     rcx, [rbp+Block]; Block
0x140037d6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140037d70  lea     rcx, [rbp+var_8]; this
0x140037d74  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x140037d79  mov     eax, ebx
0x140037d7b  add     rsp, 60h
0x140037d7f  pop     r14
0x140037d81  pop     r13
0x140037d83  pop     r12
0x140037d85  pop     rdi
0x140037d86  pop     rsi
0x140037d87  pop     rbx
0x140037d88  pop     rbp
0x140037d89  retn
```
