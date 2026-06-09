# CUpdateManager::ThreadProc(void)

- ea: `0x1400388c0`
- end: `0x140038b39`
- name: `?ThreadProc@CUpdateManager@@IEAAJXZ`
- size: `633`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140039630`

## callees

- `0x1400121f0`
- `0x14002f8e0`
- `0x140035ec0`
- `0x1400377b8`
- `0x1400388c0`
- `0x140038c38`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140068594`

## import_xrefs

- `KERNEL32!Sleep` at `0x140038af4`
- `KERNEL32!Sleep` at `0x140038af4`
- `KERNEL32!IsDebuggerPresent` at `0x140038942`
- `KERNEL32!IsDebuggerPresent` at `0x1400389ef`
- `KERNEL32!IsDebuggerPresent` at `0x140038a7a`
- `KERNEL32!IsDebuggerPresent` at `0x140038942`
- `KERNEL32!IsDebuggerPresent` at `0x1400389ef`
- `KERNEL32!IsDebuggerPresent` at `0x140038a7a`

## string_xrefs

- `0x14003891f`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x1400389c9`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140038a54`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x1400388e1`: `CUpdateManager::ThreadProc\n`
- `0x1400388f2`: `DpSoftwareUpdateRebootReason`
- `0x140038913`: `CUpdateManager::ThreadProc`
- `0x1400389b8`: `CUpdateManager::ThreadProc`
- `0x140038a43`: `CUpdateManager::ThreadProc`
- `0x1400389d0`: `iTemp <= __SURR_Last`
- `0x140038aad`: `CUpdateManager::OnRebootForWindowsUpdate\n`
- `0x140038ad8`: `CUpdateManager::OnRebootForWindowsUpdate Windows updates needs ANOTHER reboot!\n`
- `0x140038b08`: `CUpdateManager::OnRebootToStartUpdate\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::ThreadProc(CDiskProtection **this)
{
  int Setting; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // r8
  CSoftwareUpdates *v7; // rcx
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  const unsigned __int16 *v11; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v12; // [rsp+30h] [rbp-38h]
  int v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+38h] [rbp-30h]
  unsigned int v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  DEBUGMSG(L"CUpdateManager::ThreadProc\n");
  Setting = CDiskProtection::s_GetSetting(L"DpSoftwareUpdateRebootReason", &v15);
  v3 = Setting;
  if ( Setting < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x13Cu,
      L"CUpdateManager::ThreadProc",
      L"CHRA",
      L"hr",
      Setting);
    if ( IsDebuggerPresent() )
    {
      v14 = v3;
      v4 = 316;
      v12 = L"hr";
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v4,
        L"CUpdateManager::ThreadProc",
        L"CHRA",
        v12,
        v14);
      return v3;
    }
    v13 = v3;
    v5 = 316;
    v11 = L"hr";
    goto LABEL_7;
  }
  if ( v15 <= 2 )
  {
    if ( v15 )
    {
      if ( v15 == 1 )
      {
        v15 = 0;
        DEBUGMSG(L"CUpdateManager::OnRebootForWindowsUpdate\n");
        v3 = CSoftwareUpdates::CheckRebootRequired(v7, (int *)&v15);
        if ( (v3 & 0x80000000) != 0 )
          return v3;
        if ( v15 )
        {
          DEBUGMSG(L"CUpdateManager::OnRebootForWindowsUpdate Windows updates needs ANOTHER reboot!\n");
          Reboot(v9, v8, 0x20000u);
          while ( 1 )
            Sleep(0x1388u);
        }
        return (unsigned int)CUpdateManager::TransitionToNewPowerState(this, 0);
      }
      else
      {
        if ( v15 != 2 )
        {
          v3 = -2147418113;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            0x155u,
            L"CUpdateManager::ThreadProc",
            L"CHRA",
            L"((HRESULT)0x8000FFFFL)",
            -2147418113);
          if ( IsDebuggerPresent() )
          {
            v14 = -2147418113;
            v4 = 341;
            v12 = L"((HRESULT)0x8000FFFFL)";
            goto LABEL_4;
          }
          v13 = -2147418113;
          v5 = 341;
          v11 = L"((HRESULT)0x8000FFFFL)";
LABEL_7:
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
            v5,
            L"CUpdateManager::ThreadProc",
            L"CHRA",
            v11,
            v13);
          return v3;
        }
        return (unsigned int)CUpdateManager::OnRebootToTransitionToDiscard((CUpdateManager *)(v15 - 1));
      }
    }
    else
    {
      DEBUGMSG(L"CUpdateManager::OnRebootToStartUpdate\n");
      return (unsigned int)CUpdateManager::DoUpdate(this);
    }
  }
  v3 = -2147418113;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
    0x13Du,
    L"CUpdateManager::ThreadProc",
    L"CBRAEx",
    L"iTemp <= __SURR_Last",
    -2147418113);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      317,
      L"CUpdateManager::ThreadProc",
      L"CBRAEx",
      L"iTemp <= __SURR_Last",
      -2147418113);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      317,
      L"CUpdateManager::ThreadProc",
      L"CBRAEx",
      L"iTemp <= __SURR_Last",
      -2147418113);
  return v3;
}

```

## disassembly

```asm
0x1400388c0  mov     [rsp+arg_0], rbx
0x1400388c5  mov     [rsp+arg_10], rbp
0x1400388ca  push    rsi
0x1400388cb  push    rdi
0x1400388cc  push    r12
0x1400388ce  push    r13
0x1400388d0  push    r14
0x1400388d2  sub     rsp, 40h
0x1400388d6  mov     rdi, rcx
0x1400388d9  mov     [rsp+68h+arg_8], 0
0x1400388e1  lea     rcx, aCupdatemanager_65; "CUpdateManager::ThreadProc\n"
0x1400388e8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400388ed  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x1400388f2  lea     rcx, aDpsoftwareupda_0; "DpSoftwareUpdateRebootReason"
0x1400388f9  call    ?s_GetSetting@CDiskProtection@@SAJPEBGPEAK@Z; CDiskProtection::s_GetSetting(ushort const *,ulong *)
0x1400388fe  mov     ebx, eax
0x140038900  test    eax, eax
0x140038902  jns     loc_1400389A3
0x140038908  mov     [rsp+68h+var_40], eax; int
0x14003890c  lea     r14, aChra; "CHRA"
0x140038913  lea     rsi, aCupdatemanager_68; "CUpdateManager::ThreadProc"
0x14003891a  mov     ebp, 13Ch
0x14003891f  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140038926  mov     r9, r14; unsigned __int16 *
0x140038929  lea     r12, aHr; "hr"
0x140038930  mov     r8, rsi; unsigned __int16 *
0x140038933  mov     edx, ebp; unsigned int
0x140038935  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x14003893a  mov     rcx, rdi; unsigned __int16 *
0x14003893d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140038942  call    cs:__imp_IsDebuggerPresent
0x140038948  test    eax, eax
0x14003894a  jz      short loc_14003897B
0x14003894c  mov     [rsp+68h+var_30], ebx
0x140038950  mov     r9d, ebp
0x140038953  mov     [rsp+68h+var_38], r12
0x140038958  mov     qword ptr [rsp+68h+var_40], r14
0x14003895d  mov     r8, rdi
0x140038960  mov     [rsp+68h+var_48], rsi
0x140038965  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14003896c  mov     ecx, 2; unsigned __int8
0x140038971  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140038976  jmp     loc_140038B1E
0x14003897b  mov     dword ptr [rsp+68h+var_38], ebx
0x14003897f  mov     r8d, ebp
0x140038982  mov     qword ptr [rsp+68h+var_40], r12
0x140038987  mov     [rsp+68h+var_48], r14
0x14003898c  mov     r9, rsi
0x14003898f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140038996  mov     rdx, rdi
0x140038999  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14003899e  jmp     loc_140038B1E
0x1400389a3  mov     ecx, [rsp+68h+arg_8]
0x1400389a7  cmp     ecx, 2
0x1400389aa  jbe     short loc_140038A25
0x1400389ac  mov     ebp, 8000FFFFh
0x1400389b1  lea     r13, aCbraex; "CBRAEx"
0x1400389b8  lea     rsi, aCupdatemanager_68; "CUpdateManager::ThreadProc"
0x1400389bf  mov     [rsp+68h+var_40], ebp; int
0x1400389c3  mov     r14d, 13Dh
0x1400389c9  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400389d0  lea     r12, aItempSurrLast; "iTemp <= __SURR_Last"
0x1400389d7  mov     r9, r13; unsigned __int16 *
0x1400389da  mov     r8, rsi; unsigned __int16 *
0x1400389dd  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x1400389e2  mov     edx, r14d; unsigned int
0x1400389e5  mov     rcx, rdi; unsigned __int16 *
0x1400389e8  mov     ebx, ebp
0x1400389ea  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400389ef  call    cs:__imp_IsDebuggerPresent
0x1400389f5  test    eax, eax
0x1400389f7  jz      short loc_140038A0F
0x1400389f9  mov     [rsp+68h+var_30], ebp
0x1400389fd  mov     r9d, r14d
0x140038a00  mov     [rsp+68h+var_38], r12
0x140038a05  mov     qword ptr [rsp+68h+var_40], r13
0x140038a0a  jmp     loc_14003895D
0x140038a0f  mov     dword ptr [rsp+68h+var_38], ebp
0x140038a13  mov     r8d, r14d
0x140038a16  mov     qword ptr [rsp+68h+var_40], r12
0x140038a1b  mov     [rsp+68h+var_48], r13
0x140038a20  jmp     loc_14003898C
0x140038a25  test    ecx, ecx
0x140038a27  jz      loc_140038B08
0x140038a2d  sub     ecx, 1; this
0x140038a30  jz      short loc_140038AAD
0x140038a32  cmp     ecx, 1
0x140038a35  jz      short loc_140038AA6
0x140038a37  mov     ebp, 8000FFFFh
0x140038a3c  lea     r14, aChra; "CHRA"
0x140038a43  lea     rsi, aCupdatemanager_68; "CUpdateManager::ThreadProc"
0x140038a4a  mov     [rsp+68h+var_40], ebp; int
0x140038a4e  mov     r12d, 155h
0x140038a54  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140038a5b  lea     r13, aHresult0x8000f; "((HRESULT)0x8000FFFFL)"
0x140038a62  mov     r9, r14; unsigned __int16 *
0x140038a65  mov     r8, rsi; unsigned __int16 *
0x140038a68  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x140038a6d  mov     edx, r12d; unsigned int
0x140038a70  mov     rcx, rdi; unsigned __int16 *
0x140038a73  mov     ebx, ebp
0x140038a75  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140038a7a  call    cs:__imp_IsDebuggerPresent
0x140038a80  test    eax, eax
0x140038a82  jz      short loc_140038A95
0x140038a84  mov     [rsp+68h+var_30], ebp
0x140038a88  mov     r9d, r12d
0x140038a8b  mov     [rsp+68h+var_38], r13
0x140038a90  jmp     loc_140038958
0x140038a95  mov     dword ptr [rsp+68h+var_38], ebp
0x140038a99  mov     r8d, r12d
0x140038a9c  mov     qword ptr [rsp+68h+var_40], r13
0x140038aa1  jmp     loc_140038987
0x140038aa6  call    ?OnRebootToTransitionToDiscard@CUpdateManager@@IEAAJXZ; CUpdateManager::OnRebootToTransitionToDiscard(void)
0x140038aab  jmp     short loc_140038B1C
0x140038aad  lea     rcx, aCupdatemanager_17; "CUpdateManager::OnRebootForWindowsUpdat"...
0x140038ab4  mov     [rsp+68h+arg_8], 0
0x140038abc  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038ac1  lea     rdx, [rsp+68h+arg_8]; int *
0x140038ac6  call    ?CheckRebootRequired@CSoftwareUpdates@@QEAAJPEAH@Z; CSoftwareUpdates::CheckRebootRequired(int *)
0x140038acb  mov     ebx, eax
0x140038acd  test    eax, eax
0x140038acf  js      short loc_140038B1E
0x140038ad1  cmp     [rsp+68h+arg_8], 0
0x140038ad6  jz      short loc_140038AFC
0x140038ad8  lea     rcx, aCupdatemanager_33; "CUpdateManager::OnRebootForWindowsUpdat"...
0x140038adf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038ae4  mov     r8d, 20000h; unsigned int
0x140038aea  call    ?Reboot@@YAJPEBGKK@Z; Reboot(ushort const *,ulong,ulong)
0x140038aef  mov     ecx, 1388h; dwMilliseconds
0x140038af4  call    cs:__imp_Sleep
0x140038afa  jmp     short loc_140038AEF
0x140038afc  xor     edx, edx; enum _EPowerState *
0x140038afe  mov     rcx, rdi; this
0x140038b01  call    ?TransitionToNewPowerState@CUpdateManager@@IEAAJPEAW4_EPowerState@@@Z; CUpdateManager::TransitionToNewPowerState(_EPowerState *)
0x140038b06  jmp     short loc_140038B1C
0x140038b08  lea     rcx, aCupdatemanager_42; "CUpdateManager::OnRebootToStartUpdate\n"
0x140038b0f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140038b14  mov     rcx, rdi; this
0x140038b17  call    ?DoUpdate@CUpdateManager@@IEAAJXZ; CUpdateManager::DoUpdate(void)
0x140038b1c  mov     ebx, eax
0x140038b1e  lea     r11, [rsp+68h+var_28]
0x140038b23  mov     eax, ebx
0x140038b25  mov     rbx, [r11+30h]
0x140038b29  mov     rbp, [r11+40h]
0x140038b2d  mov     rsp, r11
0x140038b30  pop     r14
0x140038b32  pop     r13
0x140038b34  pop     r12
0x140038b36  pop     rdi
0x140038b37  pop     rsi
0x140038b38  retn
```
