# WaasMedic::RegDelTree(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180027a80`
- end: `0x180027c34`
- name: `?RegDelTree@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z`
- size: `436`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180021060`

## callees

- `0x180002150`
- `0x180016c9c`
- `0x18002543c`
- `0x180027a80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027ad7`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027ad7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027b47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027b47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027b2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027b2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027b6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027b6e`

## string_xrefs

- `0x180027b86`: `RegUtil: Error when attempting to delete registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelTree(const WCHAR *a1, const WCHAR *a2, __int64 a3, signed int a4)
{
  REGSAM v5; // edi
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // zf
  const struct _tlgProvider_t *v9; // rcx
  int v10; // r9d
  PHKEY phkResult; // [rsp+28h] [rbp-39h]
  const WCHAR *v13; // [rsp+58h] [rbp-9h] BYREF
  unsigned __int16 *v14; // [rsp+60h] [rbp-1h] BYREF
  __int64 v15; // [rsp+68h] [rbp+7h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+70h] [rbp+Fh] BYREF
  const WCHAR *v17; // [rsp+C8h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+77h] BYREF
  signed int v19; // [rsp+E0h] [rbp+7Fh] BYREF

  v19 = a4;
  v17 = a1;
  hKey = 0;
  v5 = 65547;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  if ( dword_180098D54 )
    v5 = 65803;
  v6 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v5, &hKey);
  if ( v7 )
  {
    v8 = v7 == 2;
  }
  else
  {
    v7 = RegDeleteTreeW(hKey, L"State");
    v8 = (v7 & 0xFFFFFFFD) == 0;
  }
  if ( !v8 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    else
      v6 = v7;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 < 0 )
  {
    LODWORD(phkResult) = v6;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to delete registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X",
      a2,
      L"State",
      phkResult);
    v9 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 5u
      && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
    {
      v19 = v6;
      v14 = &gc_pszVersionString;
      v17 = L"State";
      v13 = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)word_180089322,
        0,
        v10,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v17,
        (__int64)&v19);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180027a80  mov     rax, rsp
0x180027a83  mov     [rax+10h], rbx
0x180027a87  mov     [rax+20h], r9d
0x180027a8b  mov     [rax+18h], r8
0x180027a8f  mov     [rax+8], rcx
0x180027a93  push    rbp
0x180027a94  push    rsi
0x180027a95  push    rdi
0x180027a96  lea     rbp, [rax-5Fh]
0x180027a9a  sub     rsp, 0A0h
0x180027aa1  cmp     cs:dword_180098D58, 0
0x180027aa8  mov     rsi, rdx
0x180027aab  mov     [rbp+57h+hKey], 0
0x180027ab3  mov     edi, 1000Bh
0x180027ab8  jnz     short loc_180027B00
0x180027aba  xorps   xmm0, xmm0
0x180027abd  mov     cs:dword_180098D54, 0
0x180027ac7  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180027acb  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180027acf  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180027ad3  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180027ad7  call    cs:__imp_GetNativeSystemInfo
0x180027add  mov     eax, 6
0x180027ae2  lea     ecx, [rax-5]
0x180027ae5  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180027ae9  jz      short loc_180027AF4
0x180027aeb  lea     eax, [rcx+8]
0x180027aee  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180027af2  jnz     short loc_180027AFA
0x180027af4  mov     cs:dword_180098D54, ecx
0x180027afa  mov     cs:dword_180098D58, ecx
0x180027b00  cmp     cs:dword_180098D54, 0
0x180027b07  mov     eax, 1010Bh
0x180027b0c  cmovnz  edi, eax
0x180027b0f  lea     rax, [rbp+57h+hKey]
0x180027b13  mov     r9d, edi; samDesired
0x180027b16  xor     r8d, r8d; ulOptions
0x180027b19  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180027b1e  mov     rdx, rsi; lpSubKey
0x180027b21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027b28  xor     ebx, ebx
0x180027b2a  call    cs:__imp_RegOpenKeyExW
0x180027b30  lea     rdi, aState; "State"
0x180027b37  test    eax, eax
0x180027b39  jz      short loc_180027B40
0x180027b3b  cmp     eax, 2
0x180027b3e  jmp     short loc_180027B52
0x180027b40  mov     rcx, [rbp+57h+hKey]; hKey
0x180027b44  mov     rdx, rdi; lpSubKey
0x180027b47  call    cs:__imp_RegDeleteTreeW
0x180027b4d  test    eax, 0FFFFFFFDh
0x180027b52  jz      short loc_180027B65
0x180027b54  test    eax, eax
0x180027b56  jg      short loc_180027B5C
0x180027b58  mov     ebx, eax
0x180027b5a  jmp     short loc_180027B65
0x180027b5c  movzx   ebx, ax
0x180027b5f  or      ebx, 80070000h
0x180027b65  mov     rcx, [rbp+57h+hKey]; hKey
0x180027b69  test    rcx, rcx
0x180027b6c  jz      short loc_180027B74
0x180027b6e  call    cs:__imp_RegCloseKey
0x180027b74  test    ebx, ebx
0x180027b76  jns     loc_180027C1F
0x180027b7c  mov     r9, rdi
0x180027b7f  mov     dword ptr [rsp+0B0h+phkResult], ebx
0x180027b83  mov     r8, rsi
0x180027b86  lea     rdx, aRegutilErrorWh_8; "RegUtil: Error when attempting to delet"...
0x180027b8d  mov     ecx, 2; unsigned __int8
0x180027b92  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027b97  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180027b9c  mov     rcx, rax
0x180027b9f  mov     eax, [rax]
0x180027ba1  cmp     eax, 5
0x180027ba4  jbe     short loc_180027C1F
0x180027ba6  mov     rdx, [rcx+18h]
0x180027baa  mov     r8, 400000000000h
0x180027bb4  mov     rax, [rcx+10h]
0x180027bb8  test    r8, rax
0x180027bbb  jz      short loc_180027C1F
0x180027bbd  mov     rax, rdx
0x180027bc0  and     rax, r8
0x180027bc3  cmp     rax, rdx
0x180027bc6  jnz     short loc_180027C1F
0x180027bc8  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180027bcf  mov     [rbp+57h+arg_18], ebx
0x180027bd2  mov     [rbp+57h+var_58], rax
0x180027bd6  lea     rdx, word_180089322
0x180027bdd  lea     rax, [rbp+57h+arg_18]
0x180027be1  mov     [rbp+57h+arg_0], rdi
0x180027be5  mov     [rsp+40h], rax
0x180027bea  lea     rax, [rbp+57h+arg_0]
0x180027bee  mov     [rsp+0B0h+var_78], rax
0x180027bf3  lea     rax, [rbp+57h+var_60]
0x180027bf7  mov     [rsp+0B0h+var_80], rax
0x180027bfc  lea     rax, [rbp+57h+var_58]
0x180027c00  mov     [rsp+0B0h+var_88], rax
0x180027c05  lea     rax, [rbp+57h+var_50]
0x180027c09  mov     [rsp+0B0h+phkResult], rax
0x180027c0e  mov     [rbp+57h+var_60], rsi
0x180027c12  mov     [rbp+57h+var_50], 1000000h
0x180027c1a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180027c1f  mov     eax, ebx
0x180027c21  mov     rbx, [rsp+0B0h+arg_8]
0x180027c29  add     rsp, 0A0h
0x180027c30  pop     rdi
0x180027c31  pop     rsi
0x180027c32  pop     rbp
0x180027c33  retn
```
