# DdcRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x180004684`
- end: `0x1800047a5`
- name: `?SetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG11KK@Z`
- size: `289`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const BYTE *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x1800026ac`
- `0x180004684`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800046db`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800046db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004792`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004750`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004750`

## string_xrefs

- `0x180004713`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::SetStringValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int a5)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // edx
  int v12; // ecx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v9 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        105,
        (__int64)"CBR(lRet == 0L)");
  }
  else
  {
    v10 = RegSetValueExW(hKey, L"LostModeMessage", 0, 1u, a4, 2 * a5 + 2);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          116,
          (__int64)"CBR(lRet == 0L)");
    }
    else
    {
      v9 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180004684  mov     r11, rsp
0x180004687  mov     [r11+8], rbx
0x18000468b  mov     [r11+18h], r8
0x18000468f  push    rdi
0x180004690  sub     rsp, 50h
0x180004694  mov     qword ptr [r11-18h], 0
0x18000469c  lea     rax, [r11+18h]
0x1800046a0  mov     [r11-20h], rax
0x1800046a4  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800046ab  mov     qword ptr [r11-28h], 0
0x1800046b3  mov     rdi, r9
0x1800046b6  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800046be  xor     r9d, r9d; lpClass
0x1800046c1  xor     r8d, r8d; Reserved
0x1800046c4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800046cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800046d3  mov     qword ptr [r11+18h], 0
0x1800046db  call    cs:__imp_RegCreateKeyExW
0x1800046e1  mov     ebx, eax
0x1800046e3  test    eax, eax
0x1800046e5  jz      short loc_180004724
0x1800046e7  jle     short loc_1800046F2
0x1800046e9  movzx   ebx, ax
0x1800046ec  or      ebx, 80070000h
0x1800046f2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800046f9  jz      loc_180004788
0x1800046ff  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x180004706  mov     qword ptr [rsp+58h+samDesired], rax
0x18000470b  mov     [rsp+58h+dwOptions], 169h
0x180004713  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000471a  mov     r8d, ebx
0x18000471d  call    McTemplateU0dsqs_EventWriteTransfer
0x180004722  jmp     short loc_180004788
0x180004724  mov     eax, [rsp+58h+arg_20]
0x18000472b  lea     rdx, aLostmodemessag; "LostModeMessage"
0x180004732  mov     rcx, [rsp+58h+hKey]; hKey
0x180004737  mov     r9d, 1; dwType
0x18000473d  xor     r8d, r8d; Reserved
0x180004740  lea     eax, ds:2[rax*2]
0x180004747  mov     [rsp+58h+samDesired], eax; cbData
0x18000474b  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x180004750  call    cs:__imp_RegSetValueExW
0x180004756  mov     ebx, eax
0x180004758  test    eax, eax
0x18000475a  jz      short loc_180004786
0x18000475c  jle     short loc_180004767
0x18000475e  movzx   ebx, ax
0x180004761  or      ebx, 80070000h
0x180004767  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000476e  jz      short loc_180004788
0x180004770  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x180004777  mov     qword ptr [rsp+58h+samDesired], rax
0x18000477c  mov     [rsp+58h+dwOptions], 174h
0x180004784  jmp     short loc_180004713
0x180004786  xor     ebx, ebx
0x180004788  mov     rcx, [rsp+58h+hKey]; hKey
0x18000478d  test    rcx, rcx
0x180004790  jz      short loc_180004798
0x180004792  call    cs:__imp_RegCloseKey
0x180004798  mov     eax, ebx
0x18000479a  mov     rbx, [rsp+58h+arg_0]
0x18000479f  add     rsp, 50h
0x1800047a3  pop     rdi
0x1800047a4  retn
```
