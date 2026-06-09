# DdcRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18000456c`
- end: `0x18000467d`
- name: `?SetDWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z`
- size: `273`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000450c`

## callees

- `0x1800026ac`
- `0x18000456c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800045c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800045c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000466f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000466f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000462d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000462d`

## string_xrefs

- `0x1800045f8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::SetDWORDValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  int v9; // edx
  int v10; // ecx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v7 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v7 = (unsigned __int16)v4 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        v7,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        210,
        (__int64)"CBR(0L == dwResult)");
  }
  else
  {
    v8 = RegSetValueExW(hKey, L"EnableLostMode", 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          v7,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          219,
          (__int64)"CBR(0L == dwResult)");
    }
    else
    {
      v7 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18000456c  mov     r11, rsp
0x18000456f  mov     [r11+20h], r9d
0x180004573  mov     [r11+18h], r8
0x180004577  push    rbx
0x180004578  sub     rsp, 50h
0x18000457c  mov     qword ptr [r11-18h], 0
0x180004584  lea     rax, [r11+18h]
0x180004588  mov     [r11-20h], rax
0x18000458c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180004593  mov     qword ptr [r11-28h], 0
0x18000459b  xor     r9d, r9d; lpClass
0x18000459e  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800045a6  xor     r8d, r8d; Reserved
0x1800045a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800045b0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800045b8  mov     qword ptr [r11+18h], 0
0x1800045c0  call    cs:__imp_RegCreateKeyExW
0x1800045c6  mov     ebx, eax
0x1800045c8  test    eax, eax
0x1800045ca  jz      short loc_180004609
0x1800045cc  jle     short loc_1800045D7
0x1800045ce  movzx   ebx, ax
0x1800045d1  or      ebx, 80070000h
0x1800045d7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800045de  jz      loc_180004665
0x1800045e4  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x1800045eb  mov     qword ptr [rsp+58h+samDesired], rax
0x1800045f0  mov     [rsp+58h+dwOptions], 0D2h
0x1800045f8  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800045ff  mov     r8d, ebx
0x180004602  call    McTemplateU0dsqs_EventWriteTransfer
0x180004607  jmp     short loc_180004665
0x180004609  mov     rcx, [rsp+58h+hKey]; hKey
0x18000460e  lea     rax, [rsp+58h+Data]
0x180004613  mov     r9d, 4; dwType
0x180004619  lea     rdx, ValueName; "EnableLostMode"
0x180004620  mov     [rsp+58h+samDesired], r9d; cbData
0x180004625  xor     r8d, r8d; Reserved
0x180004628  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000462d  call    cs:__imp_RegSetValueExW
0x180004633  mov     ebx, eax
0x180004635  test    eax, eax
0x180004637  jz      short loc_180004663
0x180004639  jle     short loc_180004644
0x18000463b  movzx   ebx, ax
0x18000463e  or      ebx, 80070000h
0x180004644  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000464b  jz      short loc_180004665
0x18000464d  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x180004654  mov     qword ptr [rsp+58h+samDesired], rax
0x180004659  mov     [rsp+58h+dwOptions], 0DBh
0x180004661  jmp     short loc_1800045F8
0x180004663  xor     ebx, ebx
0x180004665  mov     rcx, [rsp+58h+hKey]; hKey
0x18000466a  test    rcx, rcx
0x18000466d  jz      short loc_180004675
0x18000466f  call    cs:__imp_RegCloseKey
0x180004675  mov     eax, ebx
0x180004677  add     rsp, 50h
0x18000467b  pop     rbx
0x18000467c  retn
```
