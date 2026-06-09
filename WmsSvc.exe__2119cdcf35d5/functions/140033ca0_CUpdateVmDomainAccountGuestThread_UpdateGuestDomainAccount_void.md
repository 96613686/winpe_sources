# CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount(void)

- ea: `0x140033ca0`
- end: `0x140033ee7`
- name: `?UpdateGuestDomainAccount@CUpdateVmDomainAccountGuestThread@@IEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CUpdateVmDomainAccountGuestThread *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140033b30`

## callees

- `0x140015438`
- `0x140033ca0`
- `0x140033ef0`
- `0x1400343d8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400675d8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140033cf6`
- `ADVAPI32!RegOpenKeyExW` at `0x140033dfe`
- `ADVAPI32!RegOpenKeyExW` at `0x140033cf6`
- `ADVAPI32!RegOpenKeyExW` at `0x140033dfe`
- `ADVAPI32!RegCloseKey` at `0x140033e7d`
- `ADVAPI32!RegCloseKey` at `0x140033ed4`
- `ADVAPI32!RegCloseKey` at `0x140033e7d`
- `ADVAPI32!RegCloseKey` at `0x140033ed4`
- `KERNEL32!IsDebuggerPresent` at `0x140033d54`
- `KERNEL32!IsDebuggerPresent` at `0x140033e4d`
- `KERNEL32!IsDebuggerPresent` at `0x140033d54`
- `KERNEL32!IsDebuggerPresent` at `0x140033e4d`

## string_xrefs

- `0x140033d3d`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140033e36`: `termsrv\wms\src\devices\wmssvc\updatevmdomainaccountguestthread.cpp`
- `0x140033cb9`: `CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount- started\n`
- `0x140033d33`: `CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount`
- `0x140033e2c`: `CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount`
- `0x140033eb8`: `CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount - Updating domain account on Virtual Machine\n`

## pseudocode

```c
__int64 __fastcall CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount(HANDLE *this)
{
  LSTATUS v2; // eax
  int UpdateVmDomainAccountValue; // ebx
  bool v4; // zf
  const unsigned __int16 *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  LSTATUS v8; // eax
  int v10; // [rsp+78h] [rbp+38h] BYREF
  int v11; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v11 = 0;
  v10 = 0;
  DEBUGMSG(L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount- started\n");
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
  UpdateVmDomainAccountValue = v2;
  if ( v2 )
  {
    if ( v2 != 2 )
    {
      if ( v2 > 0 )
        UpdateVmDomainAccountValue = (unsigned __int16)v2 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        0xF8u,
        L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        UpdateVmDomainAccountValue);
      v4 = !IsDebuggerPresent();
      v5 = L"lr == 0L || lr == 2L";
      if ( !v4 )
      {
        v6 = 248;
LABEL_7:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
          v6,
          L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount",
          L"CBRAEx",
          v5,
          UpdateVmDomainAccountValue);
        goto LABEL_26;
      }
      v7 = 248;
LABEL_9:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        v7,
        L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount",
        L"CBRAEx",
        v5,
        UpdateVmDomainAccountValue);
      goto LABEL_26;
    }
    UpdateVmDomainAccountValue = CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated(this, &v11);
    if ( UpdateVmDomainAccountValue < 0 )
      goto LABEL_26;
    if ( !v11 )
    {
LABEL_25:
      UpdateVmDomainAccountValue = 0;
      goto LABEL_26;
    }
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x10u, &hKey);
    UpdateVmDomainAccountValue = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        UpdateVmDomainAccountValue = (unsigned __int16)v8 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatevmdomainaccountguestthread.cpp",
        0x101u,
        L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount",
        L"CBRAEx",
        L"lr == 0L",
        UpdateVmDomainAccountValue);
      v4 = !IsDebuggerPresent();
      v5 = L"lr == 0L";
      if ( !v4 )
      {
        v6 = 257;
        goto LABEL_7;
      }
      v7 = 257;
      goto LABEL_9;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  UpdateVmDomainAccountValue = GetUpdateVmDomainAccountValue((enum EUpdateDomainAccount *)&v10);
  if ( UpdateVmDomainAccountValue >= 0 )
  {
    if ( v10 )
      goto LABEL_24;
    UpdateVmDomainAccountValue = CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet(
                                   this,
                                   (enum EUpdateDomainAccount *)&v10);
    if ( UpdateVmDomainAccountValue < 0 )
      goto LABEL_26;
    if ( v10 )
    {
LABEL_24:
      DEBUGMSG(L"CUpdateVmDomainAccountGuestThread::UpdateGuestDomainAccount - Updating domain account on Virtual Machine\n");
      CDiskProtection::s_UpdateDomainAccountPassword();
    }
    goto LABEL_25;
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)UpdateVmDomainAccountValue;
}

```

## disassembly

```asm
0x140033ca0  push    rbp
0x140033ca2  push    rbx
0x140033ca3  push    rsi
0x140033ca4  push    rdi
0x140033ca5  push    r14
0x140033ca7  mov     rbp, rsp
0x140033caa  sub     rsp, 40h
0x140033cae  mov     rdi, rcx
0x140033cb1  mov     [rbp+hKey], 0
0x140033cb9  lea     rcx, aCupdatevmdomai_14; "CUpdateVmDomainAccountGuestThread::Upda"...
0x140033cc0  mov     [rbp+arg_10], 0
0x140033cc7  mov     [rbp+arg_8], 0
0x140033cce  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140033cd3  lea     rax, [rbp+hKey]
0x140033cd7  mov     rsi, 0FFFFFFFF80000002h
0x140033cde  mov     rcx, rsi; hKey
0x140033ce1  mov     [rsp+40h+phkResult], rax; phkResult
0x140033ce6  mov     r9d, 20019h; samDesired
0x140033cec  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x140033cf3  xor     r8d, r8d; ulOptions
0x140033cf6  call    cs:__imp_RegOpenKeyExW
0x140033cfc  mov     ebx, eax
0x140033cfe  test    eax, eax
0x140033d00  jz      loc_140033E74
0x140033d06  cmp     eax, 2
0x140033d09  jz      loc_140033DC2
0x140033d0f  test    eax, eax
0x140033d11  jle     short loc_140033D1C
0x140033d13  movzx   ebx, ax
0x140033d16  or      ebx, 80070000h
0x140033d1c  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140033d23  mov     [rsp+40h+var_18], ebx; int
0x140033d27  lea     r14, aCbraex; "CBRAEx"
0x140033d2e  mov     [rsp+40h+phkResult], rax; unsigned __int16 *
0x140033d33  lea     rsi, aCupdatevmdomai_15; "CUpdateVmDomainAccountGuestThread::Upda"...
0x140033d3a  mov     r9, r14; unsigned __int16 *
0x140033d3d  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140033d44  mov     r8, rsi; unsigned __int16 *
0x140033d47  mov     rcx, rdi; unsigned __int16 *
0x140033d4a  mov     edx, 0F8h; unsigned int
0x140033d4f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140033d54  call    cs:__imp_IsDebuggerPresent
0x140033d5a  test    eax, eax
0x140033d5c  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140033d63  jz      short loc_140033D97
0x140033d65  mov     r9d, 0F8h
0x140033d6b  mov     [rsp+40h+var_8], ebx
0x140033d6f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140033d76  mov     [rsp+40h+var_10], rax
0x140033d7b  mov     r8, rdi
0x140033d7e  mov     qword ptr [rsp+40h+var_18], r14
0x140033d83  mov     ecx, 2; unsigned __int8
0x140033d88  mov     [rsp+40h+phkResult], rsi
0x140033d8d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140033d92  jmp     loc_140033ECB
0x140033d97  mov     r8d, 0F8h
0x140033d9d  mov     dword ptr [rsp+40h+var_10], ebx
0x140033da1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140033da8  mov     qword ptr [rsp+40h+var_18], rax
0x140033dad  mov     r9, rsi
0x140033db0  mov     rdx, rdi
0x140033db3  mov     [rsp+40h+phkResult], r14
0x140033db8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140033dbd  jmp     loc_140033ECB
0x140033dc2  lea     rdx, [rbp+arg_10]; int *
0x140033dc6  mov     rcx, rdi; this
0x140033dc9  call    ?WaitForExternalSubKeyToBeCreated@CUpdateVmDomainAccountGuestThread@@IEAAJPEAH@Z; CUpdateVmDomainAccountGuestThread::WaitForExternalSubKeyToBeCreated(int *)
0x140033dce  mov     ebx, eax
0x140033dd0  test    eax, eax
0x140033dd2  js      loc_140033ECB
0x140033dd8  cmp     [rbp+arg_10], 0
0x140033ddc  jz      loc_140033EC9
0x140033de2  lea     rax, [rbp+hKey]
0x140033de6  mov     r9d, 10h; samDesired
0x140033dec  xor     r8d, r8d; ulOptions
0x140033def  mov     [rsp+40h+phkResult], rax; phkResult
0x140033df4  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x140033dfb  mov     rcx, rsi; hKey
0x140033dfe  call    cs:__imp_RegOpenKeyExW
0x140033e04  mov     ebx, eax
0x140033e06  test    eax, eax
0x140033e08  jz      short loc_140033E74
0x140033e0a  jle     short loc_140033E15
0x140033e0c  movzx   ebx, ax
0x140033e0f  or      ebx, 80070000h
0x140033e15  lea     rax, aLr0l; "lr == 0L"
0x140033e1c  mov     [rsp+40h+var_18], ebx; int
0x140033e20  lea     r14, aCbraex; "CBRAEx"
0x140033e27  mov     [rsp+40h+phkResult], rax; unsigned __int16 *
0x140033e2c  lea     rsi, aCupdatevmdomai_15; "CUpdateVmDomainAccountGuestThread::Upda"...
0x140033e33  mov     r9, r14; unsigned __int16 *
0x140033e36  lea     rdi, aTermsrvWmsSrcD_10; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140033e3d  mov     r8, rsi; unsigned __int16 *
0x140033e40  mov     rcx, rdi; unsigned __int16 *
0x140033e43  mov     edx, 101h; unsigned int
0x140033e48  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140033e4d  call    cs:__imp_IsDebuggerPresent
0x140033e53  test    eax, eax
0x140033e55  lea     rax, aLr0l; "lr == 0L"
0x140033e5c  jz      short loc_140033E69
0x140033e5e  mov     r9d, 101h
0x140033e64  jmp     loc_140033D6B
0x140033e69  mov     r8d, 101h
0x140033e6f  jmp     loc_140033D9D
0x140033e74  mov     rcx, [rbp+hKey]; hKey
0x140033e78  test    rcx, rcx
0x140033e7b  jz      short loc_140033E83
0x140033e7d  call    cs:__imp_RegCloseKey
0x140033e83  lea     rcx, [rbp+arg_8]; enum EUpdateDomainAccount *
0x140033e87  mov     [rbp+hKey], 0
0x140033e8f  call    ?GetUpdateVmDomainAccountValue@@YAJPEAW4EUpdateDomainAccount@@@Z; GetUpdateVmDomainAccountValue(EUpdateDomainAccount *)
0x140033e94  mov     ebx, eax
0x140033e96  test    eax, eax
0x140033e98  js      short loc_140033ECB
0x140033e9a  cmp     [rbp+arg_8], 0
0x140033e9e  jnz     short loc_140033EB8
0x140033ea0  lea     rdx, [rbp+arg_8]; enum EUpdateDomainAccount *
0x140033ea4  mov     rcx, rdi; this
0x140033ea7  call    ?WaitForUpdateDomainAccountValueToBeSet@CUpdateVmDomainAccountGuestThread@@IEAAJPEAW4EUpdateDomainAccount@@@Z; CUpdateVmDomainAccountGuestThread::WaitForUpdateDomainAccountValueToBeSet(EUpdateDomainAccount *)
0x140033eac  mov     ebx, eax
0x140033eae  test    eax, eax
0x140033eb0  js      short loc_140033ECB
0x140033eb2  cmp     [rbp+arg_8], 0
0x140033eb6  jz      short loc_140033EC9
0x140033eb8  lea     rcx, aCupdatevmdomai_1; "CUpdateVmDomainAccountGuestThread::Upda"...
0x140033ebf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140033ec4  call    ?s_UpdateDomainAccountPassword@CDiskProtection@@SAJXZ; CDiskProtection::s_UpdateDomainAccountPassword(void)
0x140033ec9  xor     ebx, ebx
0x140033ecb  mov     rcx, [rbp+hKey]; hKey
0x140033ecf  test    rcx, rcx
0x140033ed2  jz      short loc_140033EDA
0x140033ed4  call    cs:__imp_RegCloseKey
0x140033eda  mov     eax, ebx
0x140033edc  add     rsp, 40h
0x140033ee0  pop     r14
0x140033ee2  pop     rdi
0x140033ee3  pop     rsi
0x140033ee4  pop     rbx
0x140033ee5  pop     rbp
0x140033ee6  retn
```
