# GetFaxRegistry

- ea: `0x14007cc68`
- end: `0x14007cdbd`
- name: `GetFaxRegistry`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140047c20`
- `0x1400480f0`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140065d14`
- `0x1400703a8`
- `0x1400708c4`
- `0x14007cc68`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007cda5`
- `ADVAPI32!RegCloseKey` at `0x14007cda5`
- `KERNEL32!GetLastError` at `0x14007ccd2`
- `KERNEL32!GetLastError` at `0x14007ccd2`

## string_xrefs

- `0x14007cd61`: `Routing Extensions`

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
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x20019u);
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
0x14007cc68  mov     [rsp+arg_0], rbx
0x14007cc6d  mov     [rsp+arg_8], rsi
0x14007cc72  push    rdi
0x14007cc73  sub     rsp, 30h
0x14007cc77  mov     rbx, rcx
0x14007cc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cc81  lea     rax, WPP_GLOBAL_Control
0x14007cc88  cmp     rcx, rax
0x14007cc8b  jz      short loc_14007CCAE
0x14007cc8d  test    byte ptr [rcx+1Ch], 2
0x14007cc91  jz      short loc_14007CCAE
0x14007cc93  cmp     byte ptr [rcx+19h], 5
0x14007cc97  jb      short loc_14007CCAE
0x14007cc99  mov     rcx, [rcx+10h]
0x14007cc9d  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007cca4  mov     edx, 18h
0x14007cca9  call    WPP_SF_
0x14007ccae  mov     r9d, 20019h
0x14007ccb4  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14007ccbb  xor     r8d, r8d
0x14007ccbe  mov     rcx, 0FFFFFFFF80000002h
0x14007ccc5  call    OpenRegistryKey
0x14007ccca  mov     rsi, rax
0x14007cccd  test    rax, rax
0x14007ccd0  jnz     short loc_14007CCDD
0x14007ccd2  call    cs:__imp_GetLastError
0x14007ccd8  jmp     loc_14007CDAD
0x14007ccdd  mov     rax, [rbx]
0x14007cce0  test    rax, rax
0x14007cce3  jnz     short loc_14007CD34
0x14007cce5  lea     ecx, [rax+40h]; dwBytes
0x14007cce8  call    pMemAlloc
0x14007cced  mov     [rbx], rax
0x14007ccf0  mov     rdi, rax
0x14007ccf3  test    rax, rax
0x14007ccf6  jnz     short loc_14007CD00
0x14007ccf8  lea     ebx, [rax+0Eh]
0x14007ccfb  jmp     loc_14007CDA2
0x14007cd00  xor     edx, edx; Val
0x14007cd02  mov     rcx, rdi; void *
0x14007cd05  lea     r8d, [rdx+40h]; Size
0x14007cd09  call    memset_0
0x14007cd0e  lea     r9, ?EnumLogging@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumLogging(HKEY__ *,ushort const *,ulong,void *)
0x14007cd15  mov     [rsp+38h+var_18], rdi
0x14007cd1a  xor     r8d, r8d
0x14007cd1d  lea     rdx, aLogging; "Logging"
0x14007cd24  mov     rcx, rsi
0x14007cd27  call    EnumerateRegistryKeys
0x14007cd2c  mov     rcx, [rbx]
0x14007cd2f  mov     [rcx+38h], eax
0x14007cd32  jmp     short loc_14007CDA0
0x14007cd34  lea     r9, ?EnumDeviceProviders@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDeviceProviders(HKEY__ *,ushort const *,ulong,void *)
0x14007cd3b  mov     [rsp+38h+var_18], rax
0x14007cd40  xor     r8d, r8d
0x14007cd43  lea     rdx, aDeviceProvider; "Device Providers"
0x14007cd4a  mov     rcx, rsi
0x14007cd4d  call    EnumerateRegistryKeys
0x14007cd52  mov     rcx, [rbx]
0x14007cd55  lea     r9, ?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)
0x14007cd5c  mov     [rsp+38h+var_18], rcx
0x14007cd61  lea     rdx, aRoutingExtensi; "Routing Extensions"
0x14007cd68  xor     r8d, r8d
0x14007cd6b  mov     [rcx+8], eax
0x14007cd6e  mov     rcx, rsi
0x14007cd71  call    EnumerateRegistryKeys
0x14007cd76  mov     rcx, [rbx]
0x14007cd79  lea     r9, ?EnumDevices@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDevices(HKEY__ *,ushort const *,ulong,void *)
0x14007cd80  mov     [rsp+38h+var_18], rcx
0x14007cd85  lea     rdx, aDevices; "Devices"
0x14007cd8c  xor     r8d, r8d
0x14007cd8f  mov     [rcx+18h], eax
0x14007cd92  mov     rcx, rsi
0x14007cd95  call    EnumerateRegistryKeys
0x14007cd9a  mov     rcx, [rbx]
0x14007cd9d  mov     [rcx+28h], eax
0x14007cda0  xor     ebx, ebx
0x14007cda2  mov     rcx, rsi; hKey
0x14007cda5  call    cs:__imp_RegCloseKey
0x14007cdab  mov     eax, ebx
0x14007cdad  mov     rbx, [rsp+38h+arg_0]
0x14007cdb2  mov     rsi, [rsp+38h+arg_8]
0x14007cdb7  add     rsp, 30h
0x14007cdbb  pop     rdi
0x14007cdbc  retn
```
