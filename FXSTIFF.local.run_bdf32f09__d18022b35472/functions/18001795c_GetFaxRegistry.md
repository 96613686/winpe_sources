# GetFaxRegistry

- ea: `0x18001795c`
- end: `0x180017aa5`
- name: `GetFaxRegistry`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016a08`

## callees

- `0x180009a7c`
- `0x18000ea18`
- `0x18000ee14`
- `0x18000f1b4`
- `0x18001795c`
- `0x180017bce`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800179c6`
- `KERNEL32!GetLastError` at `0x1800179c6`
- `ADVAPI32!RegCloseKey` at `0x180017a8d`
- `ADVAPI32!RegCloseKey` at `0x180017a8d`

## string_xrefs

- `0x180017a4f`: `Routing Extensions`

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
0x18001795c  mov     [rsp+arg_0], rbx
0x180017961  mov     [rsp+arg_8], rsi
0x180017966  push    rdi
0x180017967  sub     rsp, 30h
0x18001796b  mov     rbx, rcx
0x18001796e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017975  lea     rax, WPP_GLOBAL_Control
0x18001797c  cmp     rcx, rax
0x18001797f  jz      short loc_1800179A2
0x180017981  test    byte ptr [rcx+1Ch], 2
0x180017985  jz      short loc_1800179A2
0x180017987  cmp     byte ptr [rcx+19h], 5
0x18001798b  jb      short loc_1800179A2
0x18001798d  mov     rcx, [rcx+10h]
0x180017991  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x180017998  mov     edx, 18h
0x18001799d  call    WPP_SF_
0x1800179a2  mov     r9d, 20019h
0x1800179a8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax"
0x1800179af  xor     r8d, r8d
0x1800179b2  mov     rcx, 0FFFFFFFF80000002h
0x1800179b9  call    OpenRegistryKey
0x1800179be  mov     rsi, rax
0x1800179c1  test    rax, rax
0x1800179c4  jnz     short loc_1800179D1
0x1800179c6  call    cs:__imp_GetLastError
0x1800179cc  jmp     loc_180017A95
0x1800179d1  mov     rax, [rbx]
0x1800179d4  test    rax, rax
0x1800179d7  jnz     short loc_180017A25
0x1800179d9  lea     ecx, [rax+40h]; dwBytes
0x1800179dc  call    pMemAlloc
0x1800179e1  mov     [rbx], rax
0x1800179e4  mov     rdi, rax
0x1800179e7  test    rax, rax
0x1800179ea  jnz     short loc_1800179F4
0x1800179ec  lea     ebx, [rax+0Eh]
0x1800179ef  jmp     loc_180017A8A
0x1800179f4  xor     edx, edx; Val
0x1800179f6  mov     rcx, rdi; void *
0x1800179f9  lea     r8d, [rdx+40h]; Size
0x1800179fd  call    memset_0
0x180017a02  lea     r9, ?EnumLogging@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumLogging(HKEY__ *,ushort const *,ulong,void *)
0x180017a09  mov     [rsp+38h+var_18], rdi
0x180017a0e  lea     rdx, aLogging; "Logging"
0x180017a15  mov     rcx, rsi
0x180017a18  call    EnumerateRegistryKeys
0x180017a1d  mov     rcx, [rbx]
0x180017a20  mov     [rcx+38h], eax
0x180017a23  jmp     short loc_180017A88
0x180017a25  lea     r9, ?EnumDeviceProviders@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDeviceProviders(HKEY__ *,ushort const *,ulong,void *)
0x180017a2c  mov     [rsp+38h+var_18], rax
0x180017a31  lea     rdx, aDeviceProvider; "Device Providers"
0x180017a38  mov     rcx, rsi
0x180017a3b  call    EnumerateRegistryKeys
0x180017a40  mov     rcx, [rbx]
0x180017a43  lea     r9, ?EnumRoutingExtensions@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumRoutingExtensions(HKEY__ *,ushort const *,ulong,void *)
0x180017a4a  mov     [rsp+38h+var_18], rcx
0x180017a4f  lea     rdx, aRoutingExtensi; "Routing Extensions"
0x180017a56  mov     [rcx+8], eax
0x180017a59  mov     rcx, rsi
0x180017a5c  call    EnumerateRegistryKeys
0x180017a61  mov     rcx, [rbx]
0x180017a64  lea     r9, ?EnumDevices@@YAHPEAUHKEY__@@PEBGKPEAX@Z; EnumDevices(HKEY__ *,ushort const *,ulong,void *)
0x180017a6b  mov     [rsp+38h+var_18], rcx
0x180017a70  lea     rdx, aDevices; "Devices"
0x180017a77  mov     [rcx+18h], eax
0x180017a7a  mov     rcx, rsi
0x180017a7d  call    EnumerateRegistryKeys
0x180017a82  mov     rcx, [rbx]
0x180017a85  mov     [rcx+28h], eax
0x180017a88  xor     ebx, ebx
0x180017a8a  mov     rcx, rsi; hKey
0x180017a8d  call    cs:__imp_RegCloseKey
0x180017a93  mov     eax, ebx
0x180017a95  mov     rbx, [rsp+38h+arg_0]
0x180017a9a  mov     rsi, [rsp+38h+arg_8]
0x180017a9f  add     rsp, 30h
0x180017aa3  pop     rdi
0x180017aa4  retn
```
