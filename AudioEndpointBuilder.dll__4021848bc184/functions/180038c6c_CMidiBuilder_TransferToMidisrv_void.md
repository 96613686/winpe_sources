# CMidiBuilder::TransferToMidisrv(void)

- ea: `0x180038c6c`
- end: `0x180038d8f`
- name: `?TransferToMidisrv@CMidiBuilder@@QEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(CMidiBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038b64`

## callees

- `0x18001707c`
- `0x180033464`
- `0x180038c6c`
- `0x180038d98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038ce2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038d1e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038d67`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038ce2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038d1e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180038d67`

## string_xrefs

- `0x180038ca4`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`
- `0x180038d35`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`
- `0x180038cca`: `MidisrvTransferComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMidiBuilder::TransferToMidisrv(CMidiBuilder *this)
{
  int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // rdx
  int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h]

  v10 = 0;
  Data = 1;
  *((_BYTE *)this + 8) = 1;
  v2 = SyncWinMM();
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
      (const char *)(unsigned int)v2,
      lpData);
  v3 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
         L"MidisrvTransferComplete",
         4u,
         &Data,
         4u);
  if ( v3 )
  {
    v4 = 202;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
             (const char *)v3,
             lpDataa);
  }
  v3 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
         L"midi1",
         1u,
         L"wdmaud2.drv",
         0x18u);
  if ( v3 )
  {
    v4 = 207;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
             (const char *)v3,
             lpDataa);
  }
  v3 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
         L"midi1",
         1u,
         L"wdmaud2.drv",
         0x18u);
  if ( v3 )
  {
    v4 = 209;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
             (const char *)v3,
             lpDataa);
  }
  *((_BYTE *)this + 9) = 1;
  return 0;
}

```

## disassembly

```asm
0x180038c6c  mov     rax, rsp
0x180038c6f  mov     [rax+18h], rbx
0x180038c73  mov     [rax+20h], rbp
0x180038c77  push    r15
0x180038c79  sub     rsp, 30h
0x180038c7d  mov     rbx, rcx
0x180038c80  mov     qword ptr [rax+10h], 0
0x180038c88  mov     dword ptr [rax+8], 1
0x180038c8f  mov     byte ptr [rcx+8], 1
0x180038c93  call    ?SyncWinMM@@YAJXZ; SyncWinMM(void)
0x180038c98  mov     rcx, [rsp+38h]; this
0x180038c9d  test    eax, eax
0x180038c9f  jns     short loc_180038CB5
0x180038ca1  mov     r9d, eax; char *
0x180038ca4  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x180038cab  mov     edx, 0C8h; void *
0x180038cb0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038cb5  mov     r9d, 4; dwType
0x180038cbb  mov     [rsp+38h+cbData], r9d; cbData
0x180038cc0  lea     rax, [rsp+38h+Data]
0x180038cc5  mov     [rsp+38h+lpData], rax; lpData
0x180038cca  lea     r8, ?midisrvTransferComplete@@3QBGB; "MidisrvTransferComplete"
0x180038cd1  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180038cd8  mov     rbp, 0FFFFFFFF80000002h
0x180038cdf  mov     rcx, rbp; hKey
0x180038ce2  call    cs:__imp_RegSetKeyValueW
0x180038ce8  test    eax, eax
0x180038cea  jz      short loc_180038CF3
0x180038cec  mov     edx, 0CAh
0x180038cf1  jmp     short loc_180038D2D
0x180038cf3  mov     [rsp+38h+cbData], 18h; cbData
0x180038cfb  lea     r15, ?midi2DriverName@@3QBGB; "wdmaud2.drv"
0x180038d02  mov     [rsp+38h+lpData], r15; unsigned int
0x180038d07  mov     r9d, 1; dwType
0x180038d0d  lea     r8, ?midi2Alias@@3QBGB; "midi1"
0x180038d14  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180038d1b  mov     rcx, rbp; hKey
0x180038d1e  call    cs:__imp_RegSetKeyValueW
0x180038d24  test    eax, eax
0x180038d26  jz      short loc_180038D43
0x180038d28  mov     edx, 0CFh; void *
0x180038d2d  mov     rcx, [rsp+38h]; this
0x180038d32  mov     r9d, eax; char *
0x180038d35  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x180038d3c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038d41  jmp     short loc_180038D7E
0x180038d43  mov     [rsp+38h+cbData], 18h; cbData
0x180038d4b  mov     [rsp+38h+lpData], r15; lpData
0x180038d50  mov     r9d, 1; dwType
0x180038d56  lea     r8, ?midi2Alias@@3QBGB; "midi1"
0x180038d5d  lea     rdx, ?driver32WowPath@@3QBGB; "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x180038d64  mov     rcx, rbp; hKey
0x180038d67  call    cs:__imp_RegSetKeyValueW
0x180038d6d  test    eax, eax
0x180038d6f  jz      short loc_180038D78
0x180038d71  mov     edx, 0D1h
0x180038d76  jmp     short loc_180038D2D
0x180038d78  mov     byte ptr [rbx+9], 1
0x180038d7c  xor     eax, eax
0x180038d7e  mov     rbx, [rsp+38h+arg_10]
0x180038d83  mov     rbp, [rsp+38h+arg_18]
0x180038d88  add     rsp, 30h
0x180038d8c  pop     r15
0x180038d8e  retn
```
