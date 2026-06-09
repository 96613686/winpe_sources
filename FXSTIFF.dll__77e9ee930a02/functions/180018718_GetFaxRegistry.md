# GetFaxRegistry

- ea: `0x180018718`
- end: `0x18001886e`
- name: `GetFaxRegistry`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017744`

## callees

- `0x180009f04`
- `0x18000f128`
- `0x18000f550`
- `0x18000f940`
- `0x180018718`
- `0x18001899e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018782`
- `KERNEL32!GetLastError` at `0x180018782`
- `ADVAPI32!RegCloseKey` at `0x18001884f`
- `ADVAPI32!RegCloseKey` at `0x18001884f`

## string_xrefs

- `0x180018811`: `Routing Extensions`

## pseudocode

```c
DWORD __fastcall GetFaxRegistry(__int64 *a1)
{
  HKEY v2; // rsi
  int v3; // r8d
  void *v5; // rax
  __int64 v6; // rdi
  int v7; // ebx
  int v8; // r8d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // r8d
  __int64 v13; // [rsp+20h] [rbp-18h]
  __int64 v14; // [rsp+20h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x20019u);
  if ( !v2 )
    return GetLastError();
  if ( *a1 )
  {
    v9 = EnumerateRegistryKeys(
           (_DWORD)v2,
           (unsigned int)L"Device Providers",
           v3,
           (unsigned int)EnumDeviceProviders,
           *a1);
    v13 = *a1;
    *(_DWORD *)(v13 + 8) = v9;
    v11 = EnumerateRegistryKeys(
            (_DWORD)v2,
            (unsigned int)L"Routing Extensions",
            v10,
            (unsigned int)EnumRoutingExtensions,
            v13);
    v14 = *a1;
    *(_DWORD *)(v14 + 24) = v11;
    *(_DWORD *)(*a1 + 40) = EnumerateRegistryKeys(
                              (_DWORD)v2,
                              (unsigned int)L"Devices",
                              v12,
                              (unsigned int)EnumDevices,
                              v14);
    goto LABEL_12;
  }
  v5 = pMemAlloc(0x40u);
  *a1 = (__int64)v5;
  v6 = (__int64)v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x40u);
    *(_DWORD *)(*a1 + 56) = EnumerateRegistryKeys(
                              (_DWORD)v2,
                              (unsigned int)L"Logging",
                              v8,
                              (unsigned int)EnumLogging,
                              v6);
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v7 = 14;
LABEL_13:
  RegCloseKey(v2);
  return v7;
}

```

## disassembly

```asm
0x180018718  mov     [rsp+arg_0], rbx
0x18001871d  mov     [rsp+arg_8], rsi
0x180018722  push    rdi
0x180018723  sub     rsp, 30h
0x180018727  mov     rbx, rcx
0x18001872a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018731  lea     rax, WPP_GLOBAL_Control
0x180018738  cmp     rcx, rax
0x18001873b  jz      short loc_18001875E
0x18001873d  test    byte ptr [rcx+1Ch], 2
0x180018741  jz      short loc_18001875E
0x180018743  cmp     byte ptr [rcx+19h], 5
0x180018747  jb      short loc_18001875E
0x180018749  mov     rcx, [rcx+10h]
0x18001874d  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x180018754  mov     edx, 18h
0x180018759  call    WPP_SF_
0x18001875e  mov     r9d, 20019h
0x180018764  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax"
0x18001876b  xor     r8d, r8d
0x18001876e  mov     rcx, 0FFFFFFFF80000002h
0x180018775  call    OpenRegistryKey
0x18001877a  mov     rsi, rax
0x18001877d  test    rax, rax
0x180018780  jnz     short loc_180018793
0x180018782  call    cs:__imp_GetLastError
0x180018789  nop     dword ptr [rax+rax+00h]
0x18001878e  jmp     loc_18001885D
0x180018793  mov     rax, [rbx]
0x180018796  test    rax, rax
0x180018799  jnz     short loc_1800187E7
0x18001879b  lea     ecx, [rax+40h]; dwBytes
0x18001879e  call    pMemAlloc
0x1800187a3  mov     [rbx], rax
0x1800187a6  mov     rdi, rax
0x1800187a9  test    rax, rax
0x1800187ac  jnz     short loc_1800187B6
0x1800187ae  lea     ebx, [rax+0Eh]
0x1800187b1  jmp     loc_18001884C
0x1800187b6  xor     edx, edx; Val
0x1800187b8  mov     rcx, rdi; void *
0x1800187bb  lea     r8d, [rdx+40h]; Size
0x1800187bf  call    memset_0
0x1800187c4  lea     r9, ?EnumLogging@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumLogging(HKEY__ *,ushort const *,ulong,void *)
0x1800187cb  mov     [rsp+38h+var_18], rdi
0x1800187d0  lea     rdx, aLogging; "Logging"
0x1800187d7  mov     rcx, rsi
0x1800187da  call    EnumerateRegistryKeys
0x1800187df  mov     rcx, [rbx]
0x1800187e2  mov     [rcx+38h], eax
0x1800187e5  jmp     short loc_18001884A
0x1800187e7  lea     r9, ?EnumDeviceProviders@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDeviceProviders(HKEY__ *,ushort const *,ulong,void *)
0x1800187ee  mov     [rsp+38h+var_18], rax
0x1800187f3  lea     rdx, aDeviceProvider; "Device Providers"
0x1800187fa  mov     rcx, rsi
0x1800187fd  call    EnumerateRegistryKeys
0x180018802  mov     rcx, [rbx]
0x180018805  lea     r9, ?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)
0x18001880c  mov     [rsp+38h+var_18], rcx
0x180018811  lea     rdx, aRoutingExtensi; "Routing Extensions"
0x180018818  mov     [rcx+8], eax
0x18001881b  mov     rcx, rsi
0x18001881e  call    EnumerateRegistryKeys
0x180018823  mov     rcx, [rbx]
0x180018826  lea     r9, ?EnumDevices@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDevices(HKEY__ *,ushort const *,ulong,void *)
0x18001882d  mov     [rsp+38h+var_18], rcx
0x180018832  lea     rdx, aDevices; "Devices"
0x180018839  mov     [rcx+18h], eax
0x18001883c  mov     rcx, rsi
0x18001883f  call    EnumerateRegistryKeys
0x180018844  mov     rcx, [rbx]
0x180018847  mov     [rcx+28h], eax
0x18001884a  xor     ebx, ebx
0x18001884c  mov     rcx, rsi; hKey
0x18001884f  call    cs:__imp_RegCloseKey
0x180018856  nop     dword ptr [rax+rax+00h]
0x18001885b  mov     eax, ebx
0x18001885d  mov     rbx, [rsp+38h+arg_0]
0x180018862  mov     rsi, [rsp+38h+arg_8]
0x180018867  add     rsp, 30h
0x18001886b  pop     rdi
0x18001886c  retn
```
