# AipInitializeGlobals

- ea: `0x1400380c4`
- end: `0x140038254`
- name: `AipInitializeGlobals`
- size: `400`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003825c`

## callees

- `0x1400016d8`
- `0x140006f40`
- `0x140021924`
- `0x1400293ac`
- `0x1400380c4`
- `0x140038a54`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400380ec`
- `ntoskrnl!ExInitializeResourceLite` at `0x140038122`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400380ec`
- `ntoskrnl!ExInitializeResourceLite` at `0x140038122`
- `ntoskrnl!EtwRegister` at `0x1400381a6`
- `ntoskrnl!EtwRegister` at `0x1400381a6`

## string_xrefs

- `0x1400381f7`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\`
- `0x14003820d`: `DisableExeLinkedTokenLookup`

## pseudocode

```c
__int64 AipInitializeGlobals()
{
  NTSTATUS ConfigOptions; // ebx
  __int64 v1; // rcx
  _QWORD v3[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-10h] BYREF
  int v5; // [rsp+50h] [rbp+10h] BYREF

  memset(&WPP_MAIN_CB.DeviceExtension, 0, 0x188u);
  ConfigOptions = ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  if ( ConfigOptions >= 0 )
  {
    LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) = 1;
    ConfigOptions = AipReadConfigOptions();
    if ( ConfigOptions >= 0 )
    {
      ConfigOptions = ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.Reserved);
      if ( ConfigOptions >= 0 )
      {
        byte_140019900 = 1;
        *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = &WPP_MAIN_CB.Dpc.DpcData;
        WPP_MAIN_CB.Dpc.DpcData = &WPP_MAIN_CB.Dpc.DpcData;
        *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = &WPP_MAIN_CB.SecurityDescriptor;
        WPP_MAIN_CB.SecurityDescriptor = &WPP_MAIN_CB.SecurityDescriptor;
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        WPP_MAIN_CB.DeviceObjectExtension = (struct _DEVOBJ_EXTENSION *)&WPP_MAIN_CB.SectorSize;
        *(_QWORD *)&WPP_MAIN_CB.SectorSize = &WPP_MAIN_CB.SectorSize;
        ConfigOptions = EtwRegister(&AppIdEventProviderId, 0, 0, (PREGHANDLE)&WPP_MAIN_CB.Queue.ListEntry.Blink);
        if ( ConfigOptions >= 0 )
        {
          ConfigOptions = AiInitializeLib();
          if ( ConfigOptions >= 0 )
          {
            v5 = 0;
            v4[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\";
            v4[0] = 7602290;
            v3[1] = L"DisableExeLinkedTokenLookup";
            v3[0] = 3670070;
            if ( (int)((__int64 (__fastcall *)(__int64, _QWORD *, _QWORD *, int *))AiRegReadDwordValue)(v1, v4, v3, &v5) >= 0 )
            {
              if ( v5 )
                DisableExeLinkedTokenLookup = 1;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
        }
      }
    }
  }
  return (unsigned int)ConfigOptions;
}

```

## disassembly

```asm
0x1400380c4  mov     [rsp-8+arg_8], rbx
0x1400380c9  push    rbp
0x1400380ca  mov     rbp, rsp
0x1400380cd  sub     rsp, 40h
0x1400380d1  xor     edx, edx; Val
0x1400380d3  lea     rcx, WPP_MAIN_CB.DeviceExtension; void *
0x1400380da  mov     r8d, 188h; Size
0x1400380e0  call    memset
0x1400380e5  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x1400380ec  call    cs:__imp_ExInitializeResourceLite
0x1400380f3  nop     dword ptr [rax+rax+00h]
0x1400380f8  mov     ebx, eax
0x1400380fa  test    eax, eax
0x1400380fc  js      loc_140038246
0x140038102  mov     dword ptr cs:WPP_MAIN_CB.Queue, 1
0x14003810c  call    AipReadConfigOptions
0x140038111  mov     ebx, eax
0x140038113  test    eax, eax
0x140038115  js      loc_140038246
0x14003811b  lea     rcx, WPP_MAIN_CB.Reserved; Resource
0x140038122  call    cs:__imp_ExInitializeResourceLite
0x140038129  nop     dword ptr [rax+rax+00h]
0x14003812e  mov     ebx, eax
0x140038130  test    eax, eax
0x140038132  js      loc_140038246
0x140038138  lea     rax, WPP_MAIN_CB.Dpc.DpcData
0x14003813f  mov     cs:byte_140019900, 1
0x140038146  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rax
0x14003814d  lea     r9, WPP_MAIN_CB.Queue+8; RegHandle
0x140038154  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rax
0x14003815b  lea     rcx, AppIdEventProviderId; ProviderId
0x140038162  lea     rax, WPP_MAIN_CB.SecurityDescriptor
0x140038169  xor     r8d, r8d; CallbackContext
0x14003816c  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header, rax
0x140038173  xor     edx, edx; EnableCallback
0x140038175  mov     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x14003817c  lea     rax, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140038183  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, rax
0x14003818a  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rax
0x140038191  lea     rax, WPP_MAIN_CB.SectorSize
0x140038198  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, rax
0x14003819f  mov     qword ptr cs:WPP_MAIN_CB.SectorSize, rax
0x1400381a6  call    cs:__imp_EtwRegister
0x1400381ad  nop     dword ptr [rax+rax+00h]
0x1400381b2  mov     ebx, eax
0x1400381b4  test    eax, eax
0x1400381b6  jns     short loc_1400381EC
0x1400381b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381bf  lea     rax, WPP_GLOBAL_Control
0x1400381c6  cmp     rcx, rax
0x1400381c9  jz      short loc_140038246
0x1400381cb  mov     eax, [rcx+2Ch]
0x1400381ce  test    al, 1
0x1400381d0  jz      short loc_140038246
0x1400381d2  mov     rcx, [rcx+18h]
0x1400381d6  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x1400381dd  mov     edx, 10h
0x1400381e2  mov     r9d, ebx
0x1400381e5  call    WPP_SF_D
0x1400381ea  jmp     short loc_140038246
0x1400381ec  call    AiInitializeLib
0x1400381f1  mov     ebx, eax
0x1400381f3  test    eax, eax
0x1400381f5  js      short loc_140038246
0x1400381f7  lea     rax, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400381fe  mov     [rbp+arg_0], 0
0x140038205  mov     [rbp+var_8], rax
0x140038209  lea     r9, [rbp+arg_0]
0x14003820d  lea     rax, aDisableexelink; "DisableExeLinkedTokenLookup"
0x140038214  mov     [rbp+var_10], 740072h
0x14003821c  lea     r8, [rbp+var_20]
0x140038220  mov     [rbp+var_18], rax
0x140038224  lea     rdx, [rbp+var_10]
0x140038228  mov     [rbp+var_20], 380036h
0x140038230  call    AiRegReadDwordValue
0x140038235  test    eax, eax
0x140038237  js      short loc_140038246
0x140038239  cmp     [rbp+arg_0], 0
0x14003823d  jz      short loc_140038246
0x14003823f  mov     cs:DisableExeLinkedTokenLookup, 1
0x140038246  mov     eax, ebx
0x140038248  mov     rbx, [rsp+40h+arg_8]
0x14003824d  add     rsp, 40h
0x140038251  pop     rbp
0x140038252  retn
```
