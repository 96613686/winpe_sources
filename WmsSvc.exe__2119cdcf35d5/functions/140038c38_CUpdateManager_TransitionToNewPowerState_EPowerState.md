# CUpdateManager::TransitionToNewPowerState(_EPowerState *)

- ea: `0x140038c38`
- end: `0x140038f70`
- name: `?TransitionToNewPowerState@CUpdateManager@@IEAAJPEAW4_EPowerState@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this, enum _EPowerState *)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x140035acc`
- `0x140035ec0`
- `0x1400388c0`

## callees

- `0x14000be34`
- `0x140010444`
- `0x1400121f0`
- `0x140015034`
- `0x140038c38`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140068594`
- `0x1400692bc`
- `0x14006ea54`

## import_xrefs

- `KERNEL32!Sleep` at `0x140038f1f`
- `KERNEL32!Sleep` at `0x140038f68`
- `KERNEL32!Sleep` at `0x140038f1f`
- `KERNEL32!Sleep` at `0x140038f68`
- `KERNEL32!IsDebuggerPresent` at `0x140038cde`
- `KERNEL32!IsDebuggerPresent` at `0x140038da2`
- `KERNEL32!IsDebuggerPresent` at `0x140038e33`
- `KERNEL32!IsDebuggerPresent` at `0x140038cde`
- `KERNEL32!IsDebuggerPresent` at `0x140038da2`
- `KERNEL32!IsDebuggerPresent` at `0x140038e33`

## string_xrefs

- `0x140038d35`: `DpSoftwareUpdateReturnState`
- `0x140038c78`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140038ef9`: `DpSoftwareUpdateRunning`
- `0x140038f42`: `DpSoftwareUpdateRebootReason`
- `0x140038f29`: `DpSoftwareUpdateNewPowerState`
- `0x140038d76`: `CUpdateManager::DetermineNewPowerState`
- `0x140038ecc`: `CUpdateManager::DetermineNewPowerState eReturnState = %s, ePowerStateAtStartOfUpdateProcedure = %s, *peNewPowerState = %s\n`
- `0x140038c55`: `CUpdateManager::TransitionToNewPowerState\n`
- `0x140038c9a`: `DpSoftwareUpdateOriginalPowerState`
- `0x140038cb6`: `CUpdateManager::TransitionToNewPowerState - Unable to read original power state from registry\n`
- `0x140038c71`: `CUpdateManager::TransitionToNewPowerState`
- `0x140038e10`: `CUpdateManager::TransitionToNewPowerState - Unable to read return power state from registry\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::TransitionToNewPowerState(CDiskProtection **this, enum _EPowerState *a2)
{
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // r9
  unsigned __int64 v6; // r9
  unsigned int v7; // esi
  int v8; // ebx
  unsigned int v10; // ebp
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // rdi
  unsigned __int64 v13; // r9
  const unsigned __int16 *v14; // rbx
  unsigned __int64 v15; // r9
  const unsigned __int16 *v16; // rax
  unsigned int v17; // edx
  const unsigned __int16 *v18; // rcx
  unsigned int v19; // edx
  const unsigned __int16 *v20; // rcx
  __int64 v21; // [rsp+30h] [rbp-58h]
  Utils *v22; // [rsp+98h] [rbp+10h] BYREF

  LODWORD(v22) = 0;
  DEBUGMSG(L"CUpdateManager::TransitionToNewPowerState\n");
  if ( a2 )
  {
    v4 = *(_DWORD *)a2;
  }
  else if ( (int)CDiskProtection::s_GetSetting(L"DpSoftwareUpdateOriginalPowerState", (unsigned int *)&v22) < 0
         || (v4 = (unsigned int)v22, (unsigned int)v22 > 3) )
  {
    v4 = 3;
    DEBUGMSG(L"CUpdateManager::TransitionToNewPowerState - Unable to read original power state from registry\n");
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x30Cu,
      L"CUpdateManager::TransitionToNewPowerState",
      v5,
      L"FALSE");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        780,
        L"CUpdateManager::TransitionToNewPowerState",
        L"ASSERT",
        L"FALSE");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        780,
        L"CUpdateManager::TransitionToNewPowerState",
        L"ASSERT",
        L"FALSE");
  }
  if ( (int)CDiskProtection::s_GetSetting(L"DpSoftwareUpdateReturnState", (unsigned int *)&v22) < 0
    || (v7 = (unsigned int)v22, (unsigned int)v22 > 1) )
  {
    v7 = 0;
    DEBUGMSG(L"CUpdateManager::TransitionToNewPowerState - Unable to read return power state from registry\n");
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x319u,
      L"CUpdateManager::TransitionToNewPowerState",
      v11,
      L"FALSE");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        793,
        L"CUpdateManager::TransitionToNewPowerState",
        L"ASSERT",
        L"FALSE");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        793,
        L"CUpdateManager::TransitionToNewPowerState",
        L"ASSERT",
        L"FALSE");
    goto LABEL_20;
  }
  if ( !(_DWORD)v22 )
  {
LABEL_20:
    v10 = 0;
    goto LABEL_21;
  }
  if ( (_DWORD)v22 != 1 )
  {
    v8 = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x27Bu,
      L"CUpdateManager::DetermineNewPowerState",
      L"CHRA",
      L"((HRESULT)0x8000FFFFL)",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        635,
        L"CUpdateManager::DetermineNewPowerState",
        L"CHRA",
        L"((HRESULT)0x8000FFFFL)",
        -2147418113);
    }
    else
    {
      LODWORD(v21) = -2147418113;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        635,
        L"CUpdateManager::DetermineNewPowerState",
        L"CHRA",
        L"((HRESULT)0x8000FFFFL)",
        v21);
    }
    return (unsigned int)v8;
  }
  v10 = v4;
LABEL_21:
  v12 = Utils::StringTableHelper((Utils *)v10, (unsigned int)&qword_14009C220, (const struct Utils::SStringMap *)4, v6);
  v14 = Utils::StringTableHelper((Utils *)v4, (unsigned int)&qword_14009C220, (const struct Utils::SStringMap *)4, v13);
  v16 = Utils::StringTableHelper((Utils *)v7, (unsigned int)&qword_14009C260, (const struct Utils::SStringMap *)2, v15);
  DEBUGMSG(
    L"CUpdateManager::DetermineNewPowerState eReturnState = %s, ePowerStateAtStartOfUpdateProcedure = %s, *peNewPowerState = %s\n",
    v16,
    v14,
    v12);
  v8 = CDiskProtection::SetModeInternal(this[4], 1u);
  if ( v8 >= 0 )
  {
    if ( v10 )
    {
      v8 = CDiskProtection::s_SetSetting(L"DpSoftwareUpdateNewPowerState", v10);
      if ( v8 >= 0 )
      {
        v8 = CDiskProtection::s_SetSetting(L"DpSoftwareUpdateRebootReason", 2u);
        if ( v8 >= 0 )
        {
          Reboot(v20, v19, 0x20000u);
          while ( 1 )
            Sleep(0x1388u);
        }
      }
    }
    else
    {
      v8 = CDiskProtection::s_DeleteSetting(L"DpSoftwareUpdateRunning");
      if ( v8 >= 0 )
      {
        Shutdown(v18, v17, 0x20000u);
        while ( 1 )
          Sleep(0x1388u);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140038c38  mov     rax, rsp
0x140038c3b  push    rbx
0x140038c3c  push    rbp
0x140038c3d  push    rsi
0x140038c3e  push    rdi
0x140038c3f  push    r12
0x140038c41  push    r13
0x140038c43  push    r14
0x140038c45  push    r15
0x140038c47  sub     rsp, 48h
0x140038c4b  mov     r14, rcx
0x140038c4e  mov     dword ptr [rax+10h], 0
0x140038c55  lea     rcx, aCupdatemanager_60; "CUpdateManager::TransitionToNewPowerSta"...
0x140038c5c  mov     rbx, rdx
0x140038c5f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038c64  lea     r15, aFalse; "FALSE"
0x140038c6b  mov     r12d, 2
0x140038c71  lea     rbp, aCupdatemanager_36; "CUpdateManager::TransitionToNewPowerSta"...
0x140038c78  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140038c7f  lea     r13, aAssert; "ASSERT"
0x140038c86  test    rbx, rbx
0x140038c89  jz      short loc_140038C92
0x140038c8b  mov     ebx, [rbx]
0x140038c8d  jmp     loc_140038D2D
0x140038c92  lea     rdx, [rsp+88h+arg_8]; unsigned int *
0x140038c9a  lea     rcx, aDpsoftwareupda_1; "DpSoftwareUpdateOriginalPowerState"
0x140038ca1  call    ?s_GetSetting@CDiskProtection@@SAJPEBGPEAK@Z; CDiskProtection::s_GetSetting(ushort const *,ulong *)
0x140038ca6  test    eax, eax
0x140038ca8  js      short loc_140038CB6
0x140038caa  mov     ebx, dword ptr [rsp+88h+arg_8]
0x140038cb1  cmp     ebx, 3
0x140038cb4  jbe     short loc_140038D2D
0x140038cb6  lea     rcx, aCupdatemanager_75; "CUpdateManager::TransitionToNewPowerSta"...
0x140038cbd  mov     ebx, 3
0x140038cc2  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038cc7  mov     esi, 30Ch
0x140038ccc  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140038cd1  mov     edx, esi; unsigned int
0x140038cd3  mov     r8, rbp; unsigned __int16 *
0x140038cd6  mov     rcx, rdi; unsigned __int16 *
0x140038cd9  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140038cde  call    cs:__imp_IsDebuggerPresent
0x140038ce4  test    eax, eax
0x140038ce6  jz      short loc_140038D0E
0x140038ce8  mov     [rsp+88h+var_58], r15
0x140038ced  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140038cf4  mov     qword ptr [rsp+88h+var_60], r13
0x140038cf9  mov     r9d, esi
0x140038cfc  mov     r8, rdi
0x140038cff  mov     [rsp+88h+var_68], rbp
0x140038d04  mov     ecx, r12d; unsigned __int8
0x140038d07  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140038d0c  jmp     short loc_140038D2D
0x140038d0e  mov     qword ptr [rsp+88h+var_60], r15
0x140038d13  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140038d1a  mov     r9, rbp
0x140038d1d  mov     [rsp+88h+var_68], r13
0x140038d22  mov     r8d, esi
0x140038d25  mov     rdx, rdi
0x140038d28  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140038d2d  lea     rdx, [rsp+88h+arg_8]; unsigned int *
0x140038d35  lea     rcx, aDpsoftwareupda_2; "DpSoftwareUpdateReturnState"
0x140038d3c  call    ?s_GetSetting@CDiskProtection@@SAJPEBGPEAK@Z; CDiskProtection::s_GetSetting(ushort const *,ulong *)
0x140038d41  test    eax, eax
0x140038d43  js      loc_140038E10
0x140038d49  mov     esi, dword ptr [rsp+88h+arg_8]
0x140038d50  cmp     esi, 1
0x140038d53  ja      loc_140038E10
0x140038d59  test    esi, esi
0x140038d5b  jz      loc_140038E88
0x140038d61  cmp     esi, 1
0x140038d64  jz      loc_140038E0C
0x140038d6a  mov     ebx, 8000FFFFh
0x140038d6f  lea     r15, aChra; "CHRA"
0x140038d76  lea     rbp, aCupdatemanager_26; "CUpdateManager::DetermineNewPowerState"
0x140038d7d  mov     [rsp+88h+var_60], ebx; int
0x140038d81  mov     esi, 27Bh
0x140038d86  lea     r14, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x140038d8d  mov     r9, r15; unsigned __int16 *
0x140038d90  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x140038d95  mov     r8, rbp; unsigned __int16 *
0x140038d98  mov     edx, esi; unsigned int
0x140038d9a  mov     rcx, rdi; unsigned __int16 *
0x140038d9d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140038da2  call    cs:__imp_IsDebuggerPresent
0x140038da8  test    eax, eax
0x140038daa  jz      short loc_140038DE7
0x140038dac  mov     [rsp+88h+var_50], ebx
0x140038db0  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140038db7  mov     [rsp+88h+var_58], r14
0x140038dbc  mov     r9d, esi
0x140038dbf  mov     qword ptr [rsp+88h+var_60], r15
0x140038dc4  mov     r8, rdi
0x140038dc7  mov     ecx, r12d; unsigned __int8
0x140038dca  mov     [rsp+88h+var_68], rbp
0x140038dcf  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140038dd4  mov     eax, ebx
0x140038dd6  add     rsp, 48h
0x140038dda  pop     r15
0x140038ddc  pop     r14
0x140038dde  pop     r13
0x140038de0  pop     r12
0x140038de2  pop     rdi
0x140038de3  pop     rsi
0x140038de4  pop     rbp
0x140038de5  pop     rbx
0x140038de6  retn
0x140038de7  mov     dword ptr [rsp+88h+var_58], ebx
0x140038deb  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140038df2  mov     qword ptr [rsp+88h+var_60], r14
0x140038df7  mov     r9, rbp
0x140038dfa  mov     r8d, esi
0x140038dfd  mov     [rsp+88h+var_68], r15
0x140038e02  mov     rdx, rdi
0x140038e05  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140038e0a  jmp     short loc_140038DD4
0x140038e0c  mov     ebp, ebx
0x140038e0e  jmp     short loc_140038E8A
0x140038e10  lea     rcx, aCupdatemanager_63; "CUpdateManager::TransitionToNewPowerSta"...
0x140038e17  xor     esi, esi
0x140038e19  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038e1e  mov     r8, rbp; unsigned __int16 *
0x140038e21  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140038e26  mov     edx, 319h; unsigned int
0x140038e2b  mov     rcx, rdi; unsigned __int16 *
0x140038e2e  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140038e33  call    cs:__imp_IsDebuggerPresent
0x140038e39  test    eax, eax
0x140038e3b  jz      short loc_140038E66
0x140038e3d  mov     [rsp+88h+var_58], r15
0x140038e42  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140038e49  mov     qword ptr [rsp+88h+var_60], r13
0x140038e4e  mov     r9d, 319h
0x140038e54  mov     r8, rdi
0x140038e57  mov     [rsp+88h+var_68], rbp
0x140038e5c  mov     ecx, r12d; unsigned __int8
0x140038e5f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140038e64  jmp     short loc_140038E88
0x140038e66  mov     qword ptr [rsp+88h+var_60], r15
0x140038e6b  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140038e72  mov     r9, rbp
0x140038e75  mov     [rsp+88h+var_68], r13
0x140038e7a  mov     r8d, 319h
0x140038e80  mov     rdx, rdi
0x140038e83  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140038e88  xor     ebp, ebp
0x140038e8a  mov     r15d, 4
0x140038e90  lea     rdx, qword_14009C220; unsigned int
0x140038e97  mov     r8d, r15d; struct Utils::SStringMap *
0x140038e9a  mov     ecx, ebp; this
0x140038e9c  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140038ea1  mov     r8d, r15d; struct Utils::SStringMap *
0x140038ea4  lea     rdx, qword_14009C220; unsigned int
0x140038eab  mov     ecx, ebx; this
0x140038ead  mov     rdi, rax
0x140038eb0  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140038eb5  mov     r8, r12; struct Utils::SStringMap *
0x140038eb8  lea     rdx, qword_14009C260; unsigned int
0x140038ebf  mov     ecx, esi; this
0x140038ec1  mov     rbx, rax
0x140038ec4  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140038ec9  mov     r9, rdi
0x140038ecc  lea     rcx, aCupdatemanager_1; "CUpdateManager::DetermineNewPowerState "...
0x140038ed3  mov     r8, rbx
0x140038ed6  mov     rdx, rax
0x140038ed9  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038ede  mov     rcx, [r14+20h]
0x140038ee2  lea     edx, [r15-3]
0x140038ee6  call    ?SetModeInternal@CDiskProtection@@QEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0019@@@Z; CDiskProtection::SetModeInternal(__MIDL___MIDL_itf_wmssvc_0000_0000_0019)
0x140038eeb  mov     ebx, eax
0x140038eed  test    eax, eax
0x140038eef  js      loc_140038DD4
0x140038ef5  test    ebp, ebp
0x140038ef7  jnz     short loc_140038F27
0x140038ef9  lea     rcx, aDpsoftwareupda_3; "DpSoftwareUpdateRunning"
0x140038f00  call    ?s_DeleteSetting@CDiskProtection@@SAJPEBG@Z; CDiskProtection::s_DeleteSetting(ushort const *)
0x140038f05  mov     ebx, eax
0x140038f07  test    eax, eax
0x140038f09  js      loc_140038DD4
0x140038f0f  mov     r8d, 20000h; unsigned int
0x140038f15  call    ?Shutdown@@YAJPEBGKK@Z; Shutdown(ushort const *,ulong,ulong)
0x140038f1a  mov     ecx, 1388h; dwMilliseconds
0x140038f1f  call    cs:__imp_Sleep
0x140038f25  jmp     short loc_140038F1A
0x140038f27  mov     edx, ebp; unsigned int
0x140038f29  lea     rcx, aDpsoftwareupda_7; "DpSoftwareUpdateNewPowerState"
0x140038f30  call    ?s_SetSetting@CDiskProtection@@SAJPEBGK@Z; CDiskProtection::s_SetSetting(ushort const *,ulong)
0x140038f35  mov     ebx, eax
0x140038f37  test    eax, eax
0x140038f39  js      loc_140038DD4
0x140038f3f  mov     edx, r12d; unsigned int
0x140038f42  lea     rcx, aDpsoftwareupda_0; "DpSoftwareUpdateRebootReason"
0x140038f49  call    ?s_SetSetting@CDiskProtection@@SAJPEBGK@Z; CDiskProtection::s_SetSetting(ushort const *,ulong)
0x140038f4e  mov     ebx, eax
0x140038f50  test    eax, eax
0x140038f52  js      loc_140038DD4
0x140038f58  mov     r8d, 20000h; unsigned int
0x140038f5e  call    ?Reboot@@YAJPEBGKK@Z; Reboot(ushort const *,ulong,ulong)
0x140038f63  mov     ecx, 1388h; dwMilliseconds
0x140038f68  call    cs:__imp_Sleep
0x140038f6e  jmp     short loc_140038F63
```
