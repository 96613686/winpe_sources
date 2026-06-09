# WaasMedic::RegDelTree(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180025ba0`
- end: `0x180025d57`
- name: `?RegDelTree@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z`
- size: `439`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180022d30`
- `0x18004ef58`
- `0x18004ff6c`
- `0x1800524b0`
- `0x1800525b0`

## callees

- `0x1800023dc`
- `0x18000d04c`
- `0x180025ba0`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025bfb`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025bfb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180025c64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180025c64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c8b`

## string_xrefs

- `0x180025ca3`: `RegUtil: Error when attempting to delete registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelTree(__int64 a1, const WCHAR *a2, const WCHAR *a3, signed int a4)
{
  REGSAM v6; // esi
  signed int v7; // ebx
  LSTATUS v8; // eax
  bool v9; // zf
  __int64 v10; // rcx
  int v11; // r9d
  PHKEY phkResult; // [rsp+28h] [rbp-39h]
  const WCHAR *v14; // [rsp+58h] [rbp-9h] BYREF
  const WCHAR *v15; // [rsp+60h] [rbp-1h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp+7h] BYREF
  __int64 v17; // [rsp+70h] [rbp+Fh] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+67h] BYREF
  signed int v20; // [rsp+E0h] [rbp+7Fh] BYREF

  v20 = a4;
  hKey = 0;
  v6 = 65547;
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
    v6 = 65803;
  v7 = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v6, &hKey);
  if ( v8 )
  {
    v9 = v8 == 2;
  }
  else
  {
    v8 = RegDeleteTreeW(hKey, a3);
    v9 = (v8 & 0xFFFFFFFD) == 0;
  }
  if ( !v9 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    else
      v7 = v8;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 < 0 )
  {
    LODWORD(phkResult) = v7;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to delete registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X",
      a2,
      a3,
      phkResult);
    v10 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v10 > 5u
      && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      v20 = v7;
      v16 = &gc_pszVersionString;
      v14 = a3;
      v15 = a2;
      v17 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_180092E35,
        0,
        v11,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v20);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025ba0  mov     rax, rsp
0x180025ba3  mov     [rax+10h], rbx
0x180025ba7  mov     [rax+18h], rsi
0x180025bab  mov     [rax+20h], r9d
0x180025baf  mov     [rax+8], rcx
0x180025bb3  push    rbp
0x180025bb4  push    rdi
0x180025bb5  push    r14
0x180025bb7  lea     rbp, [rax-5Fh]
0x180025bbb  sub     rsp, 0A0h
0x180025bc2  cmp     cs:dword_1800A55AC, 0
0x180025bc9  mov     rdi, r8
0x180025bcc  mov     r14, rdx
0x180025bcf  mov     [rbp+57h+hKey], 0
0x180025bd7  mov     esi, 1000Bh
0x180025bdc  jnz     short loc_180025C24
0x180025bde  xorps   xmm0, xmm0
0x180025be1  mov     cs:dword_1800A55B0, 0
0x180025beb  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180025bef  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180025bf3  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180025bf7  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180025bfb  call    cs:__imp_GetNativeSystemInfo
0x180025c01  mov     eax, 6
0x180025c06  lea     ecx, [rax-5]
0x180025c09  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180025c0d  jz      short loc_180025C18
0x180025c0f  lea     eax, [rcx+8]
0x180025c12  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180025c16  jnz     short loc_180025C1E
0x180025c18  mov     cs:dword_1800A55B0, ecx
0x180025c1e  mov     cs:dword_1800A55AC, ecx
0x180025c24  cmp     cs:dword_1800A55B0, 0
0x180025c2b  mov     eax, 1010Bh
0x180025c30  cmovnz  esi, eax
0x180025c33  lea     rax, [rbp+57h+hKey]
0x180025c37  mov     r9d, esi; samDesired
0x180025c3a  xor     r8d, r8d; ulOptions
0x180025c3d  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180025c42  mov     rdx, r14; lpSubKey
0x180025c45  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025c4c  xor     ebx, ebx
0x180025c4e  call    cs:__imp_RegOpenKeyExW
0x180025c54  test    eax, eax
0x180025c56  jz      short loc_180025C5D
0x180025c58  cmp     eax, 2
0x180025c5b  jmp     short loc_180025C6F
0x180025c5d  mov     rcx, [rbp+57h+hKey]; hKey
0x180025c61  mov     rdx, rdi; lpSubKey
0x180025c64  call    cs:__imp_RegDeleteTreeW
0x180025c6a  test    eax, 0FFFFFFFDh
0x180025c6f  jz      short loc_180025C82
0x180025c71  test    eax, eax
0x180025c73  jg      short loc_180025C79
0x180025c75  mov     ebx, eax
0x180025c77  jmp     short loc_180025C82
0x180025c79  movzx   ebx, ax
0x180025c7c  or      ebx, 80070000h
0x180025c82  mov     rcx, [rbp+57h+hKey]; hKey
0x180025c86  test    rcx, rcx
0x180025c89  jz      short loc_180025C91
0x180025c8b  call    cs:__imp_RegCloseKey
0x180025c91  test    ebx, ebx
0x180025c93  jns     loc_180025D3D
0x180025c99  mov     r9, rdi
0x180025c9c  mov     dword ptr [rsp+0B0h+phkResult], ebx
0x180025ca0  mov     r8, r14
0x180025ca3  lea     rdx, aRegutilErrorWh_8; "RegUtil: Error when attempting to delet"...
0x180025caa  mov     ecx, 2; unsigned __int8
0x180025caf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025cb4  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180025cb9  mov     rcx, [rax+8]
0x180025cbd  mov     eax, [rcx]
0x180025cbf  cmp     eax, 5
0x180025cc2  jbe     short loc_180025D3D
0x180025cc4  mov     rdx, [rcx+18h]
0x180025cc8  mov     r8, 400000000000h
0x180025cd2  mov     rax, [rcx+10h]
0x180025cd6  test    r8, rax
0x180025cd9  jz      short loc_180025D3D
0x180025cdb  mov     rax, rdx
0x180025cde  and     rax, r8
0x180025ce1  cmp     rax, rdx
0x180025ce4  jnz     short loc_180025D3D
0x180025ce6  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180025ced  mov     [rbp+57h+arg_18], ebx
0x180025cf0  mov     [rbp+57h+var_50], rax
0x180025cf4  lea     rdx, byte_180092E35
0x180025cfb  lea     rax, [rbp+57h+arg_18]
0x180025cff  mov     [rbp+57h+var_60], rdi
0x180025d03  mov     [rsp+0B0h+var_70], rax
0x180025d08  lea     rax, [rbp+57h+var_60]
0x180025d0c  mov     [rsp+0B0h+var_78], rax
0x180025d11  lea     rax, [rbp+57h+var_58]
0x180025d15  mov     [rsp+0B0h+var_80], rax
0x180025d1a  lea     rax, [rbp+57h+var_50]
0x180025d1e  mov     [rsp+0B0h+var_88], rax
0x180025d23  lea     rax, [rbp+57h+var_48]
0x180025d27  mov     [rsp+0B0h+phkResult], rax
0x180025d2c  mov     [rbp+57h+var_58], r14
0x180025d30  mov     [rbp+57h+var_48], 1000000h
0x180025d38  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180025d3d  lea     r11, [rsp+0B0h+var_10]
0x180025d45  mov     eax, ebx
0x180025d47  mov     rbx, [r11+28h]
0x180025d4b  mov     rsi, [r11+30h]
0x180025d4f  mov     rsp, r11
0x180025d52  pop     r14
0x180025d54  pop     rdi
0x180025d55  pop     rbp
0x180025d56  retn
```
