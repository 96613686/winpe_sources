# WaasMedic::RegCreateKeyHelperPrivate_0

- ea: `0x180025728`
- end: `0x180025922`
- name: `WaasMedic::RegCreateKeyHelperPrivate_0`
- size: `506`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ef58`
- `0x18004ff6c`

## callees

- `0x1800023dc`
- `0x18000d04c`
- `0x180025728`
- `0x18002e81c`
- `0x1800358d8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002578d`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002578d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800257fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800257fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025854`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025854`

## string_xrefs

- `0x18002586c`: `RegUtil: Error when attempting to create registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegCreateKeyHelperPrivate_0(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, char a4, HKEY *a5)
{
  bool v5; // zf
  HKEY *v7; // r14
  REGSAM samDesired; // ebx
  LSTATUS v10; // eax
  signed int v11; // ebx
  HKEY v12; // rdi
  __int64 v13; // rcx
  int v14; // r9d
  LPCWSTR v16; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v17; // [rsp+60h] [rbp-21h] BYREF
  __int64 v18; // [rsp+68h] [rbp-19h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKeya; // [rsp+E8h] [rbp+67h] BYREF
  signed int v21; // [rsp+F0h] [rbp+6Fh] BYREF

  LOBYTE(v21) = a4;
  v5 = dword_1800A55AC == 0;
  v7 = a5;
  hKeya = 0;
  samDesired = 131078;
  *a5 = 0;
  if ( v5 )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
    samDesired = 131334;
  if ( !lpSubKey )
    goto LABEL_16;
  v10 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &hKeya, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_17;
  }
  v12 = hKeya;
  hKeya = 0;
  if ( hKey == v12 || !v12 )
  {
LABEL_16:
    v11 = -2147024890;
    goto LABEL_17;
  }
  v11 = WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(v12, L"S:AI(TL;;KR;;;S-1-19-512-4096)");
  if ( v11 >= 0 )
    *v7 = v12;
LABEL_17:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v11 < 0 )
  {
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to create registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X",
      lpSubKey);
    v13 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v13 > 5u
      && (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v13 + 24) & 0x400000000000LL) == *(_QWORD *)(v13 + 24) )
    {
      v21 = v11;
      v17 = &gc_pszVersionString;
      a5 = 0;
      v16 = lpSubKey;
      v18 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_180092F6D,
        0,
        v14,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&a5,
        (__int64)&v21);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180025728  mov     rax, rsp
0x18002572b  mov     [rax+8], rbx
0x18002572f  mov     [rax+20h], r9b
0x180025733  mov     [rax+18h], r8
0x180025737  push    rbp
0x180025738  push    rsi
0x180025739  push    rdi
0x18002573a  push    r14
0x18002573c  push    r15
0x18002573e  lea     rbp, [rax-4Fh]
0x180025742  sub     rsp, 0A0h
0x180025749  cmp     cs:dword_1800A55AC, 0
0x180025750  mov     r15, rdx
0x180025753  mov     r14, [rbp+47h+arg_20]
0x180025757  mov     rsi, rcx
0x18002575a  mov     [rbp+47h+hKey], 0
0x180025762  mov     ebx, 20006h
0x180025767  mov     qword ptr [r14], 0
0x18002576e  jnz     short loc_1800257B6
0x180025770  xorps   xmm0, xmm0
0x180025773  mov     cs:dword_1800A55B0, 0
0x18002577d  lea     rcx, [rbp+47h+SystemInfo]; lpSystemInfo
0x180025781  movups  xmmword ptr [rbp+47h+SystemInfo], xmm0
0x180025785  movups  xmmword ptr [rbp+47h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180025789  movups  xmmword ptr [rbp+47h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002578d  call    cs:__imp_GetNativeSystemInfo
0x180025793  mov     eax, 6
0x180025798  lea     ecx, [rax-5]
0x18002579b  cmp     ax, word ptr [rbp+47h+SystemInfo]
0x18002579f  jz      short loc_1800257AA
0x1800257a1  lea     eax, [rcx+8]
0x1800257a4  cmp     ax, word ptr [rbp+47h+SystemInfo]
0x1800257a8  jnz     short loc_1800257B0
0x1800257aa  mov     cs:dword_1800A55B0, ecx
0x1800257b0  mov     cs:dword_1800A55AC, ecx
0x1800257b6  cmp     cs:dword_1800A55B0, 0
0x1800257bd  mov     eax, 20106h
0x1800257c2  cmovnz  ebx, eax
0x1800257c5  test    r15, r15
0x1800257c8  jz      short loc_180025846
0x1800257ca  mov     qword ptr [rsp+40h], 0; lpdwDisposition
0x1800257d3  lea     rax, [rbp+47h+hKey]
0x1800257d7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800257dc  xor     r9d, r9d; lpClass
0x1800257df  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800257e8  xor     r8d, r8d; Reserved
0x1800257eb  mov     [rsp+0C0h+samDesired], ebx; samDesired
0x1800257ef  mov     rdx, r15; lpSubKey
0x1800257f2  mov     rcx, rsi; hKey
0x1800257f5  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x1800257fd  call    cs:__imp_RegCreateKeyExW
0x180025803  mov     ebx, eax
0x180025805  test    eax, eax
0x180025807  jz      short loc_180025816
0x180025809  jle     short loc_18002584B
0x18002580b  movzx   ebx, ax
0x18002580e  or      ebx, 80070000h
0x180025814  jmp     short loc_18002584B
0x180025816  mov     rdi, [rbp+47h+hKey]
0x18002581a  mov     [rbp+47h+hKey], 0
0x180025822  cmp     rsi, rdi
0x180025825  jz      short loc_180025846
0x180025827  test    rdi, rdi
0x18002582a  jz      short loc_180025846
0x18002582c  lea     rdx, aSAiTlKrS119512; "S:AI(TL;;KR;;;S-1-19-512-4096)"
0x180025833  mov     rcx, rdi; handle
0x180025836  call    ?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z; WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)
0x18002583b  mov     ebx, eax
0x18002583d  test    eax, eax
0x18002583f  js      short loc_18002584B
0x180025841  mov     [r14], rdi
0x180025844  jmp     short loc_18002584B
0x180025846  mov     ebx, 80070006h
0x18002584b  mov     rcx, [rbp+47h+hKey]; hKey
0x18002584f  test    rcx, rcx
0x180025852  jz      short loc_18002585A
0x180025854  call    cs:__imp_RegCloseKey
0x18002585a  test    ebx, ebx
0x18002585c  jns     loc_180025909
0x180025862  xor     r9d, r9d
0x180025865  mov     [rsp+0C0h+dwOptions], ebx
0x180025869  mov     r8, r15
0x18002586c  lea     rdx, aRegutilErrorWh_5; "RegUtil: Error when attempting to creat"...
0x180025873  lea     ecx, [r9+2]; unsigned __int8
0x180025877  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002587c  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180025881  mov     rcx, [rax+8]
0x180025885  mov     eax, [rcx]
0x180025887  cmp     eax, 5
0x18002588a  jbe     short loc_180025909
0x18002588c  mov     rdx, [rcx+18h]
0x180025890  mov     r8, 400000000000h
0x18002589a  mov     rax, [rcx+10h]
0x18002589e  test    r8, rax
0x1800258a1  jz      short loc_180025909
0x1800258a3  mov     rax, rdx
0x1800258a6  and     rax, r8
0x1800258a9  cmp     rax, rdx
0x1800258ac  jnz     short loc_180025909
0x1800258ae  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800258b5  mov     [rbp+47h+arg_18], ebx
0x1800258b8  mov     [rbp+47h+var_68], rax
0x1800258bc  lea     rdx, byte_180092F6D
0x1800258c3  lea     rax, [rbp+47h+arg_18]
0x1800258c7  mov     [rbp+47h+arg_20], 0
0x1800258cf  mov     [rsp+40h], rax
0x1800258d4  lea     rax, [rbp+47h+arg_20]
0x1800258d8  mov     [rsp+0C0h+phkResult], rax
0x1800258dd  lea     rax, [rbp+47h+var_70]
0x1800258e1  mov     [rsp+0C0h+lpSecurityAttributes], rax
0x1800258e6  lea     rax, [rbp+47h+var_68]
0x1800258ea  mov     qword ptr [rsp+0C0h+samDesired], rax
0x1800258ef  lea     rax, [rbp+47h+var_60]
0x1800258f3  mov     qword ptr [rsp+0C0h+dwOptions], rax
0x1800258f8  mov     [rbp+47h+var_70], r15
0x1800258fc  mov     [rbp+47h+var_60], 1000000h
0x180025904  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180025909  mov     eax, ebx
0x18002590b  mov     rbx, [rsp+0C0h+arg_0]
0x180025913  add     rsp, 0A0h
0x18002591a  pop     r15
0x18002591c  pop     r14
0x18002591e  pop     rdi
0x18002591f  pop     rsi
0x180025920  pop     rbp
0x180025921  retn
```
