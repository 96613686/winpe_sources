# WifiSignal::Create(__int64,WifiSignal::Properties const &,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *)

- ea: `0x18003b798`
- end: `0x18003b918`
- name: `?Create@WifiSignal@@SAJ_JAEBUProperties@1@PEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(__int64, struct Properties *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18003c830`

## callees

- `0x18000459c`
- `0x18000a7f8`
- `0x18000b7b8`
- `0x180012b0c`
- `0x18003b180`
- `0x18003b798`
- `0x18003cea4`

## import_xrefs

- `wlanapi!WlanRegisterNotification` at `0x18003b899`
- `wlanapi!WlanRegisterNotification` at `0x18003b899`
- `wlanapi!WlanOpenHandle` at `0x18003b7f1`
- `wlanapi!WlanOpenHandle` at `0x18003b7f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WifiSignal::Create(__int64 a1, struct Properties *a2, WifiSignal **a3)
{
  WifiSignal *pCallbackContext; // rbx
  DWORD v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD v11; // eax
  WifiSignal *v12; // rdx
  DWORD pdwNegotiatedVersion; // [rsp+60h] [rbp+18h] BYREF
  WifiSignal *v15; // [rsp+68h] [rbp+20h] BYREF

  pdwNegotiatedVersion = 0;
  v15 = (WifiSignal *)operator new(0xC8u);
  pCallbackContext = WifiSignal::WifiSignal(v15, a1, a2);
  v15 = pCallbackContext;
  v7 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)pCallbackContext + 22);
  *((_DWORD *)pCallbackContext + 46) = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
      v10 = v7;
LABEL_9:
      WPP_SF_d(v8[2], v9, &WPP_144dc3462c353fa21006ff9a189489cc_Traceguids, v10);
    }
  }
  else
  {
    v10 = pdwNegotiatedVersion;
    if ( pdwNegotiatedVersion == 2 )
    {
      v11 = WlanRegisterNotification(
              *((HANDLE *)pCallbackContext + 22),
              0x10u,
              1,
              WifiSignal::WifiChangeCallback,
              pCallbackContext,
              0,
              0);
      *((_DWORD *)pCallbackContext + 46) = v11;
      if ( v11 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_144dc3462c353fa21006ff9a189489cc_Traceguids, v11);
      WifiSignal::UpdateState(pCallbackContext);
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 11;
        goto LABEL_9;
      }
    }
  }
  v15 = 0;
  v12 = *a3;
  *a3 = pCallbackContext;
  if ( v12 )
    std::default_delete<NASignal>::operator()();
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>((__int64 (__fastcall ****)(_QWORD, __int64))&v15);
  return 0;
}

```

## disassembly

```asm
0x18003b798  mov     [rsp+arg_0], rbx
0x18003b79d  mov     [rsp+arg_8], rsi
0x18003b7a2  push    rdi
0x18003b7a3  sub     rsp, 40h
0x18003b7a7  mov     rsi, r8
0x18003b7aa  mov     rbx, rdx
0x18003b7ad  mov     rdi, rcx
0x18003b7b0  mov     [rsp+48h+pdwNegotiatedVersion], 0
0x18003b7b8  mov     ecx, 0C8h; Size
0x18003b7bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b7c2  mov     [rsp+48h+arg_18], rax
0x18003b7c7  mov     r8, rbx; struct Properties *
0x18003b7ca  mov     rdx, rdi; __int64
0x18003b7cd  mov     rcx, rax; this
0x18003b7d0  call    ??0WifiSignal@@AEAA@_JAEBUProperties@0@@Z; WifiSignal::WifiSignal(__int64,WifiSignal::Properties const &)
0x18003b7d5  mov     rbx, rax
0x18003b7d8  mov     [rsp+48h+arg_18], rax
0x18003b7dd  lea     rdi, [rax+0B0h]
0x18003b7e4  mov     r9, rdi; phClientHandle
0x18003b7e7  lea     r8, [rsp+48h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18003b7ec  xor     edx, edx; pReserved
0x18003b7ee  lea     ecx, [rdx+2]; dwClientVersion
0x18003b7f1  call    cs:__imp_WlanOpenHandle
0x18003b7f7  mov     [rbx+0B8h], eax
0x18003b7fd  test    eax, eax
0x18003b7ff  jz      short loc_18003B82C
0x18003b801  lea     rdx, WPP_GLOBAL_Control
0x18003b808  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b80f  cmp     rcx, rdx
0x18003b812  jz      loc_18003B8E2
0x18003b818  test    byte ptr [rcx+1Ch], 1
0x18003b81c  jz      loc_18003B8E2
0x18003b822  mov     edx, 0Ah
0x18003b827  mov     r9d, eax
0x18003b82a  jmp     short loc_18003B85D
0x18003b82c  mov     r9d, [rsp+48h+pdwNegotiatedVersion]
0x18003b831  cmp     r9d, 2
0x18003b835  jz      short loc_18003B86F
0x18003b837  lea     rdx, WPP_GLOBAL_Control
0x18003b83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b845  cmp     rcx, rdx
0x18003b848  jz      loc_18003B8E2
0x18003b84e  test    byte ptr [rcx+1Ch], 1
0x18003b852  jz      loc_18003B8E2
0x18003b858  mov     edx, 0Bh
0x18003b85d  lea     r8, WPP_144dc3462c353fa21006ff9a189489cc_Traceguids
0x18003b864  mov     rcx, [rcx+10h]
0x18003b868  call    WPP_SF_d
0x18003b86d  jmp     short loc_18003B8E2
0x18003b86f  mov     [rsp+48h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x18003b878  mov     [rsp+48h+pReserved], 0; pReserved
0x18003b881  mov     [rsp+48h+pCallbackContext], rbx; pCallbackContext
0x18003b886  lea     r9, ?WifiChangeCallback@WifiSignal@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18003b88d  mov     edx, 10h; dwNotifSource
0x18003b892  lea     r8d, [rdx-0Fh]; bIgnoreDuplicate
0x18003b896  mov     rcx, [rdi]; hClientHandle
0x18003b899  call    cs:__imp_WlanRegisterNotification
0x18003b89f  mov     [rbx+0B8h], eax
0x18003b8a5  test    eax, eax
0x18003b8a7  jz      short loc_18003B8DA
0x18003b8a9  lea     rdx, WPP_GLOBAL_Control
0x18003b8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8b7  cmp     rcx, rdx
0x18003b8ba  jz      short loc_18003B8DA
0x18003b8bc  test    byte ptr [rcx+1Ch], 1
0x18003b8c0  jz      short loc_18003B8DA
0x18003b8c2  mov     edx, 0Ch
0x18003b8c7  mov     r9d, eax
0x18003b8ca  lea     r8, WPP_144dc3462c353fa21006ff9a189489cc_Traceguids
0x18003b8d1  mov     rcx, [rcx+10h]
0x18003b8d5  call    WPP_SF_d
0x18003b8da  mov     rcx, rbx; this
0x18003b8dd  call    ?UpdateState@WifiSignal@@AEAAXXZ; WifiSignal::UpdateState(void)
0x18003b8e2  mov     [rsp+48h+arg_18], 0
0x18003b8eb  mov     rdx, [rsi]
0x18003b8ee  mov     [rsi], rbx
0x18003b8f1  test    rdx, rdx
0x18003b8f4  jz      short loc_18003B8FC
0x18003b8f6  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18003b8fb  nop
0x18003b8fc  lea     rcx, [rsp+48h+arg_18]
0x18003b901  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18003b906  xor     eax, eax
0x18003b908  mov     rbx, [rsp+48h+arg_0]
0x18003b90d  mov     rsi, [rsp+48h+arg_8]
0x18003b912  add     rsp, 40h
0x18003b916  pop     rdi
0x18003b917  retn
```
