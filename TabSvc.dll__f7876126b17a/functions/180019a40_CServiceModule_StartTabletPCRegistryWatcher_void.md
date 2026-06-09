# CServiceModule::StartTabletPCRegistryWatcher(void)

- ea: `0x180019a40`
- end: `0x180019bd0`
- name: `?StartTabletPCRegistryWatcher@CServiceModule@@QEAA_NXZ`
- size: `400`
- prototype: `char __fastcall(CServiceModule *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f5d0`

## callees

- `0x1800133e0`
- `0x180019a40`
- `0x180019bd8`
- `0x180019c3c`
- `0x18002b3a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019aeb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019b80`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019aeb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019b80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ac8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ac8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b61`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019aa6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019b3f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019aa6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019b3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019a60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019a60`

## string_xrefs

- `0x180019bac`: `PENSERVICE_CServiceModule::StartTabletPCRegistryWatcher`

## pseudocode

```c
char __fastcall CServiceModule::StartTabletPCRegistryWatcher(CServiceModule *this)
{
  struct _GUID *v2; // rcx
  __int64 v3; // rdx

  if ( !*((_QWORD *)this + 14) )
    *((_QWORD *)this + 14) = CreateEventW(0, 1, 0, 0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::GetImpl'::`2'::impl) )
  {
    if ( IsTabTipPrelaunchEnabled() )
    {
      if ( *((_QWORD *)this + 14) )
      {
        SafeCloseKey((HKEY *)this + 13);
        ResetEvent(*((HANDLE *)this + 14));
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\Tablet PC",
                0,
                0x20019u,
                (PHKEY)this + 13)
          && !RegNotifyChangeKeyValue(*((HKEY *)this + 13), 0, 4u, *((HANDLE *)this + 14), 1) )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
            return 1;
          v3 = 151;
LABEL_17:
          WPP_SF_s(
            *(_QWORD *)&v2[1].Data1,
            v3,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::StartTabletPCRegistryWatcher");
          return 1;
        }
      }
    }
  }
  else if ( *((_QWORD *)this + 14) )
  {
    SafeCloseKey((HKEY *)this + 13);
    ResetEvent(*((HANDLE *)this + 14));
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\Tablet PC", 0, 0x20019u, (PHKEY)this + 13)
      && !RegNotifyChangeKeyValue(*((HKEY *)this + 13), 0, 4u, *((HANDLE *)this + 14), 1) )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
        return 1;
      v3 = 152;
      goto LABEL_17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019a40  mov     [rsp+arg_0], rbx
0x180019a45  push    rdi
0x180019a46  sub     rsp, 30h
0x180019a4a  cmp     qword ptr [rcx+70h], 0
0x180019a4f  mov     rbx, rcx
0x180019a52  jnz     short loc_180019A6A
0x180019a54  xor     r9d, r9d; lpName
0x180019a57  xor     r8d, r8d; bInitialState
0x180019a5a  xor     ecx, ecx; lpEventAttributes
0x180019a5c  lea     edx, [r9+1]; bManualReset
0x180019a60  call    cs:__imp_CreateEventW
0x180019a66  mov     [rbx+70h], rax
0x180019a6a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession> `wil::Feature<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::GetImpl(void)'::`2'::impl
0x180019a71  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::__private_IsEnabled(void)
0x180019a76  test    al, al
0x180019a78  jz      loc_180019B24
0x180019a7e  call    ?IsTabTipPrelaunchEnabled@@YA_NXZ; IsTabTipPrelaunchEnabled(void)
0x180019a83  test    al, al
0x180019a85  jz      loc_180019BC3
0x180019a8b  cmp     qword ptr [rbx+70h], 0
0x180019a90  jz      loc_180019BC3
0x180019a96  lea     rdi, [rbx+68h]
0x180019a9a  mov     rcx, rdi; HKEY *
0x180019a9d  call    ?SafeCloseKey@@YAXPEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * *)
0x180019aa2  mov     rcx, [rbx+70h]; hEvent
0x180019aa6  call    cs:__imp_ResetEvent
0x180019aac  mov     r9d, 20019h; samDesired
0x180019ab2  mov     [rsp+38h+phkResult], rdi; phkResult
0x180019ab7  xor     r8d, r8d; ulOptions
0x180019aba  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\Tablet PC"
0x180019ac1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019ac8  call    cs:__imp_RegOpenKeyExW
0x180019ace  test    eax, eax
0x180019ad0  jnz     loc_180019BC3
0x180019ad6  mov     r9, [rbx+70h]; hEvent
0x180019ada  lea     r8d, [rax+4]; dwNotifyFilter
0x180019ade  mov     rcx, [rdi]; hKey
0x180019ae1  xor     edx, edx; bWatchSubtree
0x180019ae3  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180019aeb  call    cs:__imp_RegNotifyChangeKeyValue
0x180019af1  test    eax, eax
0x180019af3  jnz     loc_180019BC3
0x180019af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b00  lea     rax, WPP_GLOBAL_Control
0x180019b07  cmp     rcx, rax
0x180019b0a  jz      loc_180019BBF
0x180019b10  test    byte ptr [rcx+1Ch], 10h
0x180019b14  jz      loc_180019BBF
0x180019b1a  mov     edx, 97h
0x180019b1f  jmp     loc_180019BA8
0x180019b24  cmp     qword ptr [rbx+70h], 0
0x180019b29  jz      loc_180019BC3
0x180019b2f  lea     rdi, [rbx+68h]
0x180019b33  mov     rcx, rdi; HKEY *
0x180019b36  call    ?SafeCloseKey@@YAXPEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * *)
0x180019b3b  mov     rcx, [rbx+70h]; hEvent
0x180019b3f  call    cs:__imp_ResetEvent
0x180019b45  mov     r9d, 20019h; samDesired
0x180019b4b  mov     [rsp+38h+phkResult], rdi; phkResult
0x180019b50  xor     r8d, r8d; ulOptions
0x180019b53  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\Tablet PC"
0x180019b5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019b61  call    cs:__imp_RegOpenKeyExW
0x180019b67  test    eax, eax
0x180019b69  jnz     short loc_180019BC3
0x180019b6b  mov     r9, [rbx+70h]; hEvent
0x180019b6f  lea     r8d, [rax+4]; dwNotifyFilter
0x180019b73  mov     rcx, [rdi]; hKey
0x180019b76  xor     edx, edx; bWatchSubtree
0x180019b78  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180019b80  call    cs:__imp_RegNotifyChangeKeyValue
0x180019b86  test    eax, eax
0x180019b88  jnz     short loc_180019BC3
0x180019b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b91  lea     rax, WPP_GLOBAL_Control
0x180019b98  cmp     rcx, rax
0x180019b9b  jz      short loc_180019BBF
0x180019b9d  test    byte ptr [rcx+1Ch], 10h
0x180019ba1  jz      short loc_180019BBF
0x180019ba3  mov     edx, 98h
0x180019ba8  mov     rcx, [rcx+10h]
0x180019bac  lea     r9, aPenserviceCser_9; "PENSERVICE_CServiceModule::StartTabletP"...
0x180019bb3  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180019bba  call    WPP_SF_s
0x180019bbf  mov     al, 1
0x180019bc1  jmp     short loc_180019BC5
0x180019bc3  xor     al, al
0x180019bc5  mov     rbx, [rsp+38h+arg_0]
0x180019bca  add     rsp, 30h
0x180019bce  pop     rdi
0x180019bcf  retn
```
