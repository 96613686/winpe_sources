# GetFaxRegistry

- ea: `0x140081de4`
- end: `0x140081f46`
- name: `GetFaxRegistry`
- size: `354`
- prototype: `DWORD __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004a944`
- `0x14004ae64`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x1400698ec`
- `0x1400749a0`
- `0x140074f18`
- `0x140081de4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140081f27`
- `ADVAPI32!RegCloseKey` at `0x140081f27`
- `KERNEL32!GetLastError` at `0x140081e4e`
- `KERNEL32!GetLastError` at `0x140081e4e`

## string_xrefs

- `0x140081ee3`: `Routing Extensions`

## pseudocode

```c
DWORD __fastcall GetFaxRegistry(__int64 *a1)
{
  HKEY v2; // rsi
  void *v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // [rsp+20h] [rbp-18h]
  __int64 v10; // [rsp+20h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax", 0, 131097);
  if ( !v2 )
    return GetLastError();
  if ( *a1 )
  {
    v7 = EnumerateRegistryKeys((_DWORD)v2, (unsigned int)L"Device Providers", 0, (unsigned int)EnumDeviceProviders, *a1);
    v9 = *a1;
    *(_DWORD *)(v9 + 8) = v7;
    v8 = EnumerateRegistryKeys(
           (_DWORD)v2,
           (unsigned int)L"Routing Extensions",
           0,
           (unsigned int)EnumRoutingExtensions,
           v9);
    v10 = *a1;
    *(_DWORD *)(v10 + 24) = v8;
    *(_DWORD *)(*a1 + 40) = EnumerateRegistryKeys(
                              (_DWORD)v2,
                              (unsigned int)L"Devices",
                              0,
                              (unsigned int)EnumDevices,
                              v10);
    goto LABEL_12;
  }
  v4 = (void *)pMemAlloc(0x40u);
  *a1 = (__int64)v4;
  v5 = (__int64)v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x40u);
    *(_DWORD *)(*a1 + 56) = EnumerateRegistryKeys(
                              (_DWORD)v2,
                              (unsigned int)L"Logging",
                              0,
                              (unsigned int)EnumLogging,
                              v5);
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
  v6 = 14;
LABEL_13:
  RegCloseKey(v2);
  return v6;
}

```

## disassembly

```asm
0x140081de4  mov     [rsp+arg_0], rbx
0x140081de9  mov     [rsp+arg_8], rsi
0x140081dee  push    rdi
0x140081def  sub     rsp, 30h
0x140081df3  mov     rbx, rcx
0x140081df6  mov     rcx, cs:WPP_GLOBAL_Control
0x140081dfd  lea     rax, WPP_GLOBAL_Control
0x140081e04  cmp     rcx, rax
0x140081e07  jz      short loc_140081E2A
0x140081e09  test    byte ptr [rcx+1Ch], 2
0x140081e0d  jz      short loc_140081E2A
0x140081e0f  cmp     byte ptr [rcx+19h], 5
0x140081e13  jb      short loc_140081E2A
0x140081e15  mov     rcx, [rcx+10h]
0x140081e19  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081e20  mov     edx, 18h
0x140081e25  call    WPP_SF_
0x140081e2a  mov     r9d, 20019h
0x140081e30  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140081e37  xor     r8d, r8d
0x140081e3a  mov     rcx, 0FFFFFFFF80000002h
0x140081e41  call    OpenRegistryKey
0x140081e46  mov     rsi, rax
0x140081e49  test    rax, rax
0x140081e4c  jnz     short loc_140081E5F
0x140081e4e  call    cs:__imp_GetLastError
0x140081e55  nop     dword ptr [rax+rax+00h]
0x140081e5a  jmp     loc_140081F35
0x140081e5f  mov     rax, [rbx]
0x140081e62  test    rax, rax
0x140081e65  jnz     short loc_140081EB6
0x140081e67  lea     ecx, [rax+40h]; dwBytes
0x140081e6a  call    pMemAlloc
0x140081e6f  mov     [rbx], rax
0x140081e72  mov     rdi, rax
0x140081e75  test    rax, rax
0x140081e78  jnz     short loc_140081E82
0x140081e7a  lea     ebx, [rax+0Eh]
0x140081e7d  jmp     loc_140081F24
0x140081e82  xor     edx, edx; Val
0x140081e84  mov     rcx, rdi; void *
0x140081e87  lea     r8d, [rdx+40h]; Size
0x140081e8b  call    memset_0
0x140081e90  lea     r9, ?EnumLogging@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumLogging(HKEY__ *,ushort const *,ulong,void *)
0x140081e97  mov     [rsp+38h+var_18], rdi
0x140081e9c  xor     r8d, r8d
0x140081e9f  lea     rdx, aLogging; "Logging"
0x140081ea6  mov     rcx, rsi
0x140081ea9  call    EnumerateRegistryKeys
0x140081eae  mov     rcx, [rbx]
0x140081eb1  mov     [rcx+38h], eax
0x140081eb4  jmp     short loc_140081F22
0x140081eb6  lea     r9, ?EnumDeviceProviders@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDeviceProviders(HKEY__ *,ushort const *,ulong,void *)
0x140081ebd  mov     [rsp+38h+var_18], rax
0x140081ec2  xor     r8d, r8d
0x140081ec5  lea     rdx, aDeviceProvider; "Device Providers"
0x140081ecc  mov     rcx, rsi
0x140081ecf  call    EnumerateRegistryKeys
0x140081ed4  mov     rcx, [rbx]
0x140081ed7  lea     r9, ?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)
0x140081ede  mov     [rsp+38h+var_18], rcx
0x140081ee3  lea     rdx, aRoutingExtensi; "Routing Extensions"
0x140081eea  xor     r8d, r8d
0x140081eed  mov     [rcx+8], eax
0x140081ef0  mov     rcx, rsi
0x140081ef3  call    EnumerateRegistryKeys
0x140081ef8  mov     rcx, [rbx]
0x140081efb  lea     r9, ?EnumDevices@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDevices(HKEY__ *,ushort const *,ulong,void *)
0x140081f02  mov     [rsp+38h+var_18], rcx
0x140081f07  lea     rdx, aDevices; "Devices"
0x140081f0e  xor     r8d, r8d
0x140081f11  mov     [rcx+18h], eax
0x140081f14  mov     rcx, rsi
0x140081f17  call    EnumerateRegistryKeys
0x140081f1c  mov     rcx, [rbx]
0x140081f1f  mov     [rcx+28h], eax
0x140081f22  xor     ebx, ebx
0x140081f24  mov     rcx, rsi; hKey
0x140081f27  call    cs:__imp_RegCloseKey
0x140081f2e  nop     dword ptr [rax+rax+00h]
0x140081f33  mov     eax, ebx
0x140081f35  mov     rbx, [rsp+38h+arg_0]
0x140081f3a  mov     rsi, [rsp+38h+arg_8]
0x140081f3f  add     rsp, 30h
0x140081f43  pop     rdi
0x140081f44  retn
```
