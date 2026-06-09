# ServiceManager::ShowUpdateToast(__MIDL_odmlapi_0005)

- ea: `0x18001ca00`
- end: `0x18001cb59`
- name: `?ShowUpdateToast@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180014744`

## callees

- `0x180015f30`
- `0x18001be24`
- `0x18001ca00`
- `0x180020978`
- `0x180022a2c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001ca9c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001ca9c`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ca37`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ca37`

## string_xrefs

- `0x18001cb28`: `LastMapUpdateNotification`
- `0x18001ca8d`: `ServiceManager::IsActiveMapsUser`
- `0x18001ca2e`: `ServiceManager::ShowUpdateToast`
- `0x18001caf8`: `MapsUpdateAvail`

## pseudocode

```c
int __fastcall ServiceManager::ShowUpdateToast(ServiceManager *a1, int a2, __int64 a3)
{
  int AutoUpdateEnabledSetting; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // r8d
  int MapsPersistedRegQword; // eax
  bool v11; // cl
  unsigned __int64 CurrentFileTimeAsUint64; // rax
  __int64 v13; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(v13) = 1;
  AutoUpdateEnabledSetting = ServiceManager::GetAutoUpdateEnabledSetting(a1, (int *)&v13, a3);
  if ( AutoUpdateEnabledSetting < 0 )
  {
    v8 = 3392;
    return ZTraceReportOrigination(AutoUpdateEnabledSetting, "ServiceManager::ShowUpdateToast", v8, a1);
  }
  if ( !(_DWORD)v13 && a2 == 2 && *((_BYTE *)a1 + 4314) )
  {
    v13 = 0;
    MapsPersistedRegQword = RegUtils::GetMapsPersistedRegQword(v6, L"LastMosHostConnection", v7, &v13);
    if ( MapsPersistedRegQword >= 0 )
    {
      CurrentFileTimeAsUint64 = TimeUtils::GetCurrentFileTimeAsUint64();
      v11 = v13 && CurrentFileTimeAsUint64 - v13 <= 0x1792F8648000LL;
    }
    else
    {
      AutoUpdateEnabledSetting = ZTraceReportPropagation(
                                   MapsPersistedRegQword,
                                   "ServiceManager::IsActiveMapsUser",
                                   3098,
                                   a1);
      v11 = 0;
      if ( AutoUpdateEnabledSetting < 0 )
      {
        v8 = 3400;
        return ZTraceReportOrigination(AutoUpdateEnabledSetting, "ServiceManager::ShowUpdateToast", v8, a1);
      }
    }
    if ( v11 )
    {
      AutoUpdateEnabledSetting = ServiceManager::ShowToast(
                                   a1,
                                   105,
                                   102,
                                   (SAFEARRAY *)L"MapsUpdateAvail",
                                   L"LastMapUpdateNotification",
                                   0xB0051C88000uLL,
                                   1,
                                   (unsigned __int16 *)&dword_180027ABC,
                                   (unsigned __int16 *)&dword_180027ABC,
                                   0,
                                   0);
      if ( AutoUpdateEnabledSetting < 0 )
      {
        v8 = 3410;
        return ZTraceReportOrigination(AutoUpdateEnabledSetting, "ServiceManager::ShowUpdateToast", v8, a1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ca00  mov     rax, rsp
0x18001ca03  mov     [rax+8], rbx
0x18001ca07  push    rdi
0x18001ca08  sub     rsp, 60h
0x18001ca0c  mov     edi, edx
0x18001ca0e  mov     dword ptr [rax+18h], 1
0x18001ca15  lea     rdx, [rax+18h]; int *
0x18001ca19  mov     rbx, rcx
0x18001ca1c  call    ?GetAutoUpdateEnabledSetting@ServiceManager@@UEAAJPEAH@Z; ServiceManager::GetAutoUpdateEnabledSetting(int *)
0x18001ca21  test    eax, eax
0x18001ca23  jns     short loc_18001CA42
0x18001ca25  mov     r8d, 0D40h
0x18001ca2b  mov     r9, rbx
0x18001ca2e  lea     rdx, aServicemanager_84; "ServiceManager::ShowUpdateToast"
0x18001ca35  mov     ecx, eax
0x18001ca37  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001ca3d  jmp     loc_18001CB4E
0x18001ca42  cmp     dword ptr [rsp+68h+arg_10], 0
0x18001ca4a  jnz     loc_18001CB4C
0x18001ca50  cmp     edi, 2
0x18001ca53  jnz     loc_18001CB4C
0x18001ca59  cmp     byte ptr [rbx+10DAh], 0
0x18001ca60  jz      loc_18001CB4C
0x18001ca66  lea     r9, [rsp+68h+arg_10]
0x18001ca6e  mov     [rsp+68h+arg_10], 0
0x18001ca7a  lea     rdx, aLastmoshostcon; "LastMosHostConnection"
0x18001ca81  call    ?GetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_KPEA_K@Z; RegUtils::GetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ca86  test    eax, eax
0x18001ca88  jns     short loc_18001CAB3
0x18001ca8a  mov     r9, rbx
0x18001ca8d  lea     rdx, aServicemanager_64; "ServiceManager::IsActiveMapsUser"
0x18001ca94  mov     r8d, 0C1Ah
0x18001ca9a  mov     ecx, eax
0x18001ca9c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001caa2  xor     cl, cl
0x18001caa4  test    eax, eax
0x18001caa6  jns     short loc_18001CADD
0x18001caa8  mov     r8d, 0D48h
0x18001caae  jmp     loc_18001CA2B
0x18001cab3  call    ?GetCurrentFileTimeAsUint64@TimeUtils@@SA_KXZ; TimeUtils::GetCurrentFileTimeAsUint64(void)
0x18001cab8  mov     rcx, [rsp+68h+arg_10]
0x18001cac0  test    rcx, rcx
0x18001cac3  jz      short loc_18001CADB
0x18001cac5  sub     rax, rcx
0x18001cac8  mov     rcx, 1792F8648000h
0x18001cad2  cmp     rax, rcx
0x18001cad5  ja      short loc_18001CADB
0x18001cad7  mov     cl, 1
0x18001cad9  jmp     short loc_18001CADD
0x18001cadb  xor     cl, cl
0x18001cadd  test    cl, cl
0x18001cadf  jz      short loc_18001CB4C
0x18001cae1  mov     [rsp+68h+var_18], 0; unsigned int
0x18001cae9  lea     rax, dword_180027ABC
0x18001caf0  mov     [rsp+68h+var_20], 0; unsigned int
0x18001caf8  lea     r9, aMapsupdateavai; "MapsUpdateAvail"
0x18001caff  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x18001cb04  mov     edx, 69h ; 'i'; unsigned int
0x18001cb09  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x18001cb0e  mov     rcx, rbx; this
0x18001cb11  mov     rax, 0B0051C88000h
0x18001cb1b  mov     [rsp+68h+var_38], 1; int
0x18001cb23  mov     [rsp+68h+var_40], rax; unsigned __int64
0x18001cb28  lea     rax, aLastmapupdaten; "LastMapUpdateNotification"
0x18001cb2f  lea     r8d, [rdx-3]; unsigned int
0x18001cb33  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001cb38  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x18001cb3d  test    eax, eax
0x18001cb3f  jns     short loc_18001CB4C
0x18001cb41  mov     r8d, 0D52h
0x18001cb47  jmp     loc_18001CA2B
0x18001cb4c  xor     eax, eax
0x18001cb4e  mov     rbx, [rsp+68h+arg_0]
0x18001cb53  add     rsp, 60h
0x18001cb57  pop     rdi
0x18001cb58  retn
```
