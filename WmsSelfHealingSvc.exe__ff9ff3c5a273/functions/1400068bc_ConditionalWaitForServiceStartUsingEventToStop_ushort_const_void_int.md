# ConditionalWaitForServiceStartUsingEventToStop(ushort const *,void *,int *)

- ea: `0x1400068bc`
- end: `0x140006a7f`
- name: `?ConditionalWaitForServiceStartUsingEventToStop@@YAJPEBGPEAXPEAH@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009470`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x1400068bc`
- `0x140007d88`
- `0x140008090`
- `0x140008510`
- `0x14000988c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400069fc`
- `KERNEL32!IsDebuggerPresent` at `0x1400069fc`

## string_xrefs

- `0x1400069eb`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006a12`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006a41`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400068f1`: `ConditionalWaitForServiceStartUsingEventToStop - %s.\n`
- `0x1400069d5`: `ConditionalWaitForServiceStartUsingEventToStop`
- `0x140006932`: `ConditionalWaitForServiceStartUsingEventToStop - %s service is running.\n`
- `0x140006a65`: `ConditionalWaitForServiceStartUsingEventToStop - %s service is running.\n`
- `0x14000694e`: `ConditionalWaitForServiceStartUsingEventToStop - %s service is auto-start.\n`
- `0x14000698d`: `ConditionalWaitForServiceStartUsingEventToStop - OS is booted in safe mode, but %s service is in the safe mode list.\n`
- `0x140006996`: `ConditionalWaitForServiceStartUsingEventToStop - OS is booted in normal mode.\n`
- `0x1400069a9`: `ConditionalWaitForServiceStartUsingEventToStop- %s is in state %u, waiting for service to start running.\n`
- `0x1400069e1`: `eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged`

## pseudocode

```c
__int64 __fastcall ConditionalWaitForServiceStartUsingEventToStop(const unsigned __int16 *a1, void *a2, int *a3)
{
  const unsigned __int16 *v3; // rcx
  int WindowsServiceInformation; // ebx
  __int64 v5; // rcx
  unsigned int v6; // edx
  const unsigned __int16 *v7; // rcx
  void *v8; // r8
  const unsigned __int16 *v9; // r9
  _DWORD v11[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+80h] [rbp+30h] BYREF
  int v13; // [rsp+84h] [rbp+34h]
  unsigned int v14; // [rsp+88h] [rbp+38h] BYREF
  int v15; // [rsp+8Ch] [rbp+3Ch]
  unsigned int v16; // [rsp+90h] [rbp+40h] BYREF
  int v17; // [rsp+94h] [rbp+44h]
  int v18; // [rsp+98h] [rbp+48h] BYREF

  v17 = HIDWORD(a3);
  v15 = HIDWORD(a2);
  v13 = HIDWORD(a1);
  v11[0] = 0;
  v14 = 0;
  v16 = 0;
  v12 = 0;
  v18 = 0;
  DEBUGMSG(L"ConditionalWaitForServiceStartUsingEventToStop - %s.\n", L"Wms");
  WindowsServiceInformation = GetWindowsServiceInformation(v3, &v14, &v16);
  if ( WindowsServiceInformation >= 0 )
  {
    if ( v16 == 4 )
    {
      DEBUGMSG(L"ConditionalWaitForServiceStartUsingEventToStop - %s service is running.\n", L"Wms");
      return 0;
    }
    if ( v14 != 2 )
      return 0;
    DEBUGMSG(L"ConditionalWaitForServiceStartUsingEventToStop - %s service is auto-start.\n", L"Wms");
    WindowsServiceInformation = GetSystemStartMode((enum ESystemStartMode *)&v12);
    if ( WindowsServiceInformation < 0 )
      return (unsigned int)WindowsServiceInformation;
    if ( v12 )
    {
      WindowsServiceInformation = IsServiceInSafeModeList(v5, v12, &v18);
      if ( WindowsServiceInformation < 0 )
        return (unsigned int)WindowsServiceInformation;
      if ( !v18 )
        return 0;
      DEBUGMSG(
        L"ConditionalWaitForServiceStartUsingEventToStop - OS is booted in safe mode, but %s service is in the safe mode list.\n",
        L"Wms");
    }
    else
    {
      DEBUGMSG(L"ConditionalWaitForServiceStartUsingEventToStop - OS is booted in normal mode.\n", L"Wms");
    }
    DEBUGMSG(
      L"ConditionalWaitForServiceStartUsingEventToStop- %s is in state %u, waiting for service to start running.\n",
      L"Wms",
      v16);
    WindowsServiceInformation = WaitForServiceStatusChange(v7, v6, v8, (enum EServiceStatusChangeWaitResult *)v11);
    if ( WindowsServiceInformation >= 0 )
    {
      if ( v11[0] != 1 )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0xB75u,
          L"ConditionalWaitForServiceStartUsingEventToStop",
          v9,
          L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2933,
            L"ConditionalWaitForServiceStartUsingEventToStop",
            L"ASSERT",
            L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            2933,
            L"ConditionalWaitForServiceStartUsingEventToStop",
            L"ASSERT",
            L"eServiceStatusChangeWaitResult == SSWR_ServiceStatusChanged");
      }
      DEBUGMSG(L"ConditionalWaitForServiceStartUsingEventToStop - %s service is running.\n", L"Wms");
    }
  }
  return (unsigned int)WindowsServiceInformation;
}

```

## disassembly

```asm
0x1400068bc  mov     qword ptr [rsp-28h+arg_10], r8
0x1400068c1  mov     qword ptr [rsp-28h+arg_8], rdx
0x1400068c6  mov     [rsp-28h+arg_0], rcx
0x1400068cb  push    rbp
0x1400068cc  push    rbx
0x1400068cd  push    rsi
0x1400068ce  push    r12
0x1400068d0  push    r13
0x1400068d2  mov     rbp, rsp
0x1400068d5  sub     rsp, 50h
0x1400068d9  lea     rsi, ServiceName; "Wms"
0x1400068e0  mov     [rbp+var_10], 0
0x1400068e7  mov     rdx, rsi
0x1400068ea  mov     [rbp+arg_8], 0
0x1400068f1  lea     rcx, aConditionalwai_1; "ConditionalWaitForServiceStartUsingEven"...
0x1400068f8  mov     [rbp+arg_10], 0
0x1400068ff  mov     dword ptr [rbp+arg_0], 0
0x140006906  mov     [rbp+arg_18], 0
0x14000690d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140006912  lea     r8, [rbp+arg_10]; unsigned int *
0x140006916  lea     rdx, [rbp+arg_8]; unsigned int *
0x14000691a  call    ?GetWindowsServiceInformation@@YAJPEBGPEAK1@Z; GetWindowsServiceInformation(ushort const *,ulong *,ulong *)
0x14000691f  mov     ebx, eax
0x140006921  test    eax, eax
0x140006923  js      loc_140006A71
0x140006929  cmp     [rbp+arg_10], 4
0x14000692d  jnz     short loc_140006945
0x14000692f  mov     rdx, rsi
0x140006932  lea     rcx, aConditionalwai_0; "ConditionalWaitForServiceStartUsingEven"...
0x140006939  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000693e  xor     ebx, ebx
0x140006940  jmp     loc_140006A71
0x140006945  cmp     [rbp+arg_8], 2
0x140006949  jnz     short loc_14000693E
0x14000694b  mov     rdx, rsi
0x14000694e  lea     rcx, aConditionalwai_5; "ConditionalWaitForServiceStartUsingEven"...
0x140006955  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000695a  lea     rcx, [rbp+arg_0]; enum ESystemStartMode *
0x14000695e  call    ?GetSystemStartMode@@YAJPEAW4ESystemStartMode@@@Z; GetSystemStartMode(ESystemStartMode *)
0x140006963  mov     ebx, eax
0x140006965  test    eax, eax
0x140006967  js      loc_140006A71
0x14000696d  mov     edx, dword ptr [rbp+arg_0]
0x140006970  test    edx, edx
0x140006972  jz      short loc_140006996
0x140006974  lea     r8, [rbp+arg_18]
0x140006978  call    ?IsServiceInSafeModeList@@YAJPEBGW4ESystemStartMode@@PEAH@Z; IsServiceInSafeModeList(ushort const *,ESystemStartMode,int *)
0x14000697d  mov     ebx, eax
0x14000697f  test    eax, eax
0x140006981  js      loc_140006A71
0x140006987  cmp     [rbp+arg_18], 0
0x14000698b  jz      short loc_14000693E
0x14000698d  lea     rcx, aConditionalwai; "ConditionalWaitForServiceStartUsingEven"...
0x140006994  jmp     short loc_14000699D
0x140006996  lea     rcx, aConditionalwai_2; "ConditionalWaitForServiceStartUsingEven"...
0x14000699d  mov     rdx, rsi
0x1400069a0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400069a5  mov     r8d, [rbp+arg_10]
0x1400069a9  lea     rcx, aConditionalwai_3; "ConditionalWaitForServiceStartUsingEven"...
0x1400069b0  mov     rdx, rsi
0x1400069b3  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400069b8  lea     r9, [rbp+var_10]; enum EServiceStatusChangeWaitResult *
0x1400069bc  call    ?WaitForServiceStatusChange@@YAJPEBGKPEAXPEAW4EServiceStatusChangeWaitResult@@@Z; WaitForServiceStatusChange(ushort const *,ulong,void *,EServiceStatusChangeWaitResult *)
0x1400069c1  mov     ebx, eax
0x1400069c3  test    eax, eax
0x1400069c5  js      loc_140006A71
0x1400069cb  cmp     [rbp+var_10], 1
0x1400069cf  jz      loc_140006A62
0x1400069d5  lea     r12, aConditionalwai_4; "ConditionalWaitForServiceStartUsingEven"...
0x1400069dc  mov     edx, 0B75h; unsigned int
0x1400069e1  lea     r13, aEservicestatus; "eServiceStatusChangeWaitResult == SSWR_"...
0x1400069e8  mov     r8, r12; unsigned __int16 *
0x1400069eb  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400069f2  mov     [rsp+50h+var_30], r13; unsigned __int16 *
0x1400069f7  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400069fc  call    cs:__imp_IsDebuggerPresent
0x140006a02  test    eax, eax
0x140006a04  lea     rax, aAssert; "ASSERT"
0x140006a0b  jz      short loc_140006A3C
0x140006a0d  mov     [rsp+50h+var_20], r13
0x140006a12  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006a19  mov     [rsp+50h+var_28], rax
0x140006a1e  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140006a25  mov     r9d, 0B75h
0x140006a2b  mov     [rsp+50h+var_30], r12
0x140006a30  mov     ecx, 2; unsigned __int8
0x140006a35  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140006a3a  jmp     short loc_140006A62
0x140006a3c  mov     [rsp+50h+var_28], r13
0x140006a41  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006a48  mov     r9, r12
0x140006a4b  mov     [rsp+50h+var_30], rax
0x140006a50  mov     r8d, 0B75h
0x140006a56  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140006a5d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140006a62  mov     rdx, rsi
0x140006a65  lea     rcx, aConditionalwai_0; "ConditionalWaitForServiceStartUsingEven"...
0x140006a6c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140006a71  mov     eax, ebx
0x140006a73  add     rsp, 50h
0x140006a77  pop     r13
0x140006a79  pop     r12
0x140006a7b  pop     rsi
0x140006a7c  pop     rbx
0x140006a7d  pop     rbp
0x140006a7e  retn
```
