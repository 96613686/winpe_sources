# DllInitialize

- ea: `0x18000cbb0`
- end: `0x18000cd0b`
- name: `DllInitialize`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c9b4`
- `0x18000cbb0`
- `0x18000ce38`
- `0x18000d98c`
- `0x18000da98`
- `0x18000dffc`
- `0x18001f404`
- `0x18001f4e4`
- `0x1800203c0`
- `0x1800525e4`
- `0x180052668`
- `0x1800526fc`
- `0x18006c044`
- `0x18006c078`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000cce7`
- `ntoskrnl!ZwClose` at `0x18000cce7`

## string_xrefs

- `0x18000ccbb`: `WfpComponentsStart`
- `0x18000cca4`: `WfpComponentsDispatchForward`

## pseudocode

```c
__int64 DllInitialize()
{
  __int64 v0; // rcx
  __int64 v1; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v3; // rbx
  __int64 v4; // rax
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+24h] [rbp-24h]
  int v12; // [rsp+28h] [rbp-20h]
  HANDLE Handle; // [rsp+30h] [rbp-18h] BYREF

  Handle = 0;
  _security_init_cookie();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)&WPP_ThisDir_CTLGUID_FWPKCLNT;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  wil_InitializeFeatureStaging(v0);
  if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    InitializeWfpVerifierSettings();
  }
  else
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
    WfpRegOpenKey(&Handle, v1, &v10);
    if ( v10 )
    {
      WfpRegGetUint32Value(Handle);
      if ( v11 )
        gWfpSpPoolVerifierValue = v12;
    }
  }
  v3 = 0;
  while ( 1 )
  {
    v4 = WfpComponentDispatch(&FWPP_COMPONENTS[2 * v3], 0);
    v5 = v4;
    if ( v4 )
      break;
    if ( (unsigned __int64)++v3 >= 8 )
      goto LABEL_14;
  }
  WfpReportError(v4, (int)"WfpComponentsDispatchForward");
  WfpComponentsDispatchReverse(v7, v6, v8, v3);
  WfpReportError(v5, (int)"WfpComponentsStart");
  WfpReportError(v5, (int)"FwppInit");
  WppCleanupKm();
LABEL_14:
  if ( Handle )
    ZwClose(Handle);
  return v5;
}

```

## disassembly

```asm
0x18000cbb0  push    rbp
0x18000cbb2  push    rbx
0x18000cbb3  push    rsi
0x18000cbb4  push    rdi
0x18000cbb5  mov     rbp, rsp
0x18000cbb8  sub     rsp, 48h
0x18000cbbc  mov     rax, cs:__security_cookie
0x18000cbc3  xor     rax, rsp
0x18000cbc6  mov     [rbp+var_10], rax
0x18000cbca  xor     esi, esi
0x18000cbcc  mov     [rbp+Handle], rsi
0x18000cbd0  call    __security_init_cookie
0x18000cbd5  lea     rax, WPP_ThisDir_CTLGUID_FWPKCLNT
0x18000cbdc  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x18000cbe3  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x18000cbea  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x18000cbf1  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x18000cbf8  mov     cs:WPP_MAIN_CB.Timer, 1
0x18000cc03  call    WppLoadTracingSupport
0x18000cc08  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x18000cc0f  call    WppInitKm
0x18000cc14  call    wil_InitializeFeatureStaging
0x18000cc19  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext
0x18000cc1f  test    al, 10h
0x18000cc21  jz      short loc_18000CC28
0x18000cc23  and     eax, 1
0x18000cc26  jmp     short loc_18000CC2D
0x18000cc28  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x18000cc2d  test    eax, eax
0x18000cc2f  jnz     short loc_18000CC74
0x18000cc31  lea     r8, [rbp+var_28]
0x18000cc35  mov     [rbp+var_28], esi
0x18000cc38  lea     rcx, [rbp+Handle]; KeyHandle
0x18000cc3c  mov     [rbp+var_24], esi
0x18000cc3f  mov     [rbp+var_20], esi
0x18000cc42  call    WfpRegOpenKey
0x18000cc47  cmp     [rbp+var_28], esi
0x18000cc4a  jz      short loc_18000CC79
0x18000cc4c  mov     rcx, [rbp+Handle]; KeyHandle
0x18000cc50  lea     r9, [rbp+var_24]
0x18000cc54  lea     r8, [rbp+var_20]
0x18000cc58  lea     rdx, aNblverificatio; "NblVerificationState"
0x18000cc5f  call    WfpRegGetUint32Value
0x18000cc64  cmp     [rbp+var_24], esi
0x18000cc67  jz      short loc_18000CC79
0x18000cc69  mov     eax, [rbp+var_20]
0x18000cc6c  mov     cs:gWfpSpPoolVerifierValue, eax
0x18000cc72  jmp     short loc_18000CC79
0x18000cc74  call    InitializeWfpVerifierSettings
0x18000cc79  mov     rbx, rsi
0x18000cc7c  mov     rcx, rbx
0x18000cc7f  xor     edx, edx
0x18000cc81  shl     rcx, 4
0x18000cc85  add     rcx, cs:FWPP_COMPONENTS
0x18000cc8c  call    WfpComponentDispatch
0x18000cc91  mov     rdi, rax
0x18000cc94  test    rax, rax
0x18000cc97  jnz     short loc_18000CCA4
0x18000cc99  inc     rbx
0x18000cc9c  cmp     rbx, 8
0x18000cca0  jb      short loc_18000CC7C
0x18000cca2  jmp     short loc_18000CCDE
0x18000cca4  lea     rdx, aWfpcomponentsd; "WfpComponentsDispatchForward"
0x18000ccab  mov     rcx, rdi
0x18000ccae  call    WfpReportError
0x18000ccb3  mov     r9, rbx
0x18000ccb6  call    WfpComponentsDispatchReverse
0x18000ccbb  lea     rdx, aWfpcomponentss; "WfpComponentsStart"
0x18000ccc2  mov     rcx, rdi
0x18000ccc5  call    WfpReportError
0x18000ccca  lea     rdx, aFwppinit; "FwppInit"
0x18000ccd1  mov     rcx, rdi
0x18000ccd4  call    WfpReportError
0x18000ccd9  call    WppCleanupKm
0x18000ccde  mov     rcx, [rbp+Handle]; Handle
0x18000cce2  test    rcx, rcx
0x18000cce5  jz      short loc_18000CCF3
0x18000cce7  call    cs:__imp_ZwClose
0x18000ccee  nop     dword ptr [rax+rax+00h]
0x18000ccf3  mov     eax, edi
0x18000ccf5  mov     rcx, [rbp+var_10]
0x18000ccf9  xor     rcx, rsp; StackCookie
0x18000ccfc  call    __security_check_cookie
0x18000cd01  add     rsp, 48h
0x18000cd05  pop     rdi
0x18000cd06  pop     rsi
0x18000cd07  pop     rbx
0x18000cd08  pop     rbp
0x18000cd09  retn
```
