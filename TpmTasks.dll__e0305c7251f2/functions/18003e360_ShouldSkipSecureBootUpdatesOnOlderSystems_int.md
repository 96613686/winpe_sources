# ShouldSkipSecureBootUpdatesOnOlderSystems(int *)

- ea: `0x18003e360`
- end: `0x18003e453`
- name: `?ShouldSkipSecureBootUpdatesOnOlderSystems@@YAJPEAH@Z`
- size: `243`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d8e0`

## callees

- `0x1800394b0`
- `0x18003c0b8`
- `0x18003c254`
- `0x18003c688`
- `0x18003e360`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e42f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e42f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e41f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e41f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e3b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e3b3`

## string_xrefs

- `0x18003e3e1`: `BIOSReleaseDateRegistryFailed`
- `0x18003e404`: `Skipping Secure Boot Update due to BIOS year %d`
- `0x18003e37f`: `SkipUpdateOnIncompatibleUEFI`
- `0x18003e43c`: `ShouldSkipSecureBootUpdatesOnOlderSystems`

## pseudocode

```c
__int64 __fastcall ShouldSkipSecureBootUpdatesOnOlderSystems(int *a1)
{
  int HWSystemInformationFromRegistry; // ebx
  const unsigned __int16 *v3; // rsi
  unsigned int BiosYear; // eax
  HANDLE ProcessHeap; // rax
  int v7; // [rsp+60h] [rbp+8h] BYREF
  DWORD v8; // [rsp+68h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp+18h] BYREF

  HWSystemInformationFromRegistry = 0;
  lpMem = 0;
  *a1 = 0;
  v7 = 0;
  v8 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot",
    L"SkipUpdateOnIncompatibleUEFI",
    0x10u,
    0,
    &v7,
    &v8);
  if ( v7 )
  {
    HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                        L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                        L"BIOSReleaseDate",
                                        (unsigned __int16 **)&lpMem);
    if ( HWSystemInformationFromRegistry >= 0 )
    {
      v3 = L"Passed";
      BiosYear = GetBiosYear((unsigned __int16 *)lpMem);
      if ( BiosYear <= 0x7E2 )
      {
        SBServicingLogMessage((wchar_t *)L"Skipping Secure Boot Update due to BIOS year %d", BiosYear);
        *a1 = 1;
      }
    }
    else
    {
      v3 = L"BIOSReleaseDateRegistryFailed";
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    if ( HWSystemInformationFromRegistry < 0 )
      SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ShouldSkipSecureBootUpdatesOnOlderSystems", v3);
  }
  return (unsigned int)HWSystemInformationFromRegistry;
}

```

## disassembly

```asm
0x18003e360  mov     r11, rsp
0x18003e363  push    rbx
0x18003e364  push    rsi
0x18003e365  push    r14
0x18003e367  sub     rsp, 40h
0x18003e36b  xor     ebx, ebx
0x18003e36d  mov     qword ptr [r11+18h], 0
0x18003e375  lea     rax, [r11+10h]
0x18003e379  mov     [rcx], ebx
0x18003e37b  mov     [r11-28h], rax
0x18003e37f  lea     r8, aSkipupdateonin; "SkipUpdateOnIncompatibleUEFI"
0x18003e386  lea     rax, [r11+8]
0x18003e38a  mov     [rsp+58h+arg_0], ebx
0x18003e38e  mov     r14, rcx
0x18003e391  mov     [r11-30h], rax
0x18003e395  lea     r9d, [rbx+10h]; dwFlags
0x18003e399  mov     [r11-38h], rbx
0x18003e39d  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003e3a4  mov     [rsp+58h+arg_8], 4
0x18003e3ac  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003e3b3  call    cs:__imp_RegGetValueW
0x18003e3b9  cmp     [rsp+58h+arg_0], ebx
0x18003e3bd  jz      loc_18003E448
0x18003e3c3  lea     r8, [rsp+58h+lpMem]; unsigned __int16 **
0x18003e3c8  lea     rdx, aBiosreleasedat_0; "BIOSReleaseDate"
0x18003e3cf  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003e3d6  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003e3db  mov     ebx, eax
0x18003e3dd  test    eax, eax
0x18003e3df  jns     short loc_18003E3EA
0x18003e3e1  lea     rsi, aBiosreleasedat; "BIOSReleaseDateRegistryFailed"
0x18003e3e8  jmp     short loc_18003E417
0x18003e3ea  mov     rcx, [rsp+58h+lpMem]; unsigned __int16 *
0x18003e3ef  lea     rsi, aPassed; "Passed"
0x18003e3f6  call    ?GetBiosYear@@YAKPEAG@Z; GetBiosYear(ushort *)
0x18003e3fb  cmp     eax, 7E2h
0x18003e400  ja      short loc_18003E417
0x18003e402  mov     edx, eax
0x18003e404  lea     rcx, aSkippingSecure_1; "Skipping Secure Boot Update due to BIOS"...
0x18003e40b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e410  mov     dword ptr [r14], 1
0x18003e417  cmp     [rsp+58h+lpMem], 0
0x18003e41d  jz      short loc_18003E435
0x18003e41f  call    cs:__imp_GetProcessHeap
0x18003e425  mov     r8, [rsp+58h+lpMem]; lpMem
0x18003e42a  xor     edx, edx; dwFlags
0x18003e42c  mov     rcx, rax; hHeap
0x18003e42f  call    cs:__imp_HeapFree
0x18003e435  test    ebx, ebx
0x18003e437  jns     short loc_18003E448
0x18003e439  mov     rdx, rsi; unsigned __int16 *
0x18003e43c  lea     rcx, aShouldskipsecu; "ShouldSkipSecureBootUpdatesOnOlderSyste"...
0x18003e443  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003e448  mov     eax, ebx
0x18003e44a  add     rsp, 40h
0x18003e44e  pop     r14
0x18003e450  pop     rsi
0x18003e451  pop     rbx
0x18003e452  retn
```
