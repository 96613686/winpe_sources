# WaasMedic::RegCreateKeyHelperPrivate

- ea: `0x18002555c`
- end: `0x18002571f`
- name: `WaasMedic::RegCreateKeyHelperPrivate`
- size: `451`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, __int64, HKEY *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18002744c`
- `0x18003a660`
- `0x18003ba20`
- `0x180068100`

## callees

- `0x1800023dc`
- `0x18000d04c`
- `0x18002555c`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800255b1`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800255b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002561b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002561b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025651`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025651`

## string_xrefs

- `0x180025669`: `RegUtil: Error when attempting to create registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegCreateKeyHelperPrivate(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, HKEY *a4, int a5)
{
  HKEY v7; // rcx
  bool v9; // zf
  REGSAM samDesired; // esi
  signed int v11; // ebx
  LSTATUS v12; // eax
  __int64 v13; // rcx
  int v14; // r9d
  LPCWSTR v16; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-19h] BYREF
  __int64 v18; // [rsp+60h] [rbp-11h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+68h] [rbp-9h] BYREF
  HKEY hKeya; // [rsp+E0h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+E8h] [rbp+77h] BYREF

  v7 = 0;
  v9 = dword_1800A55AC == 0;
  samDesired = 131078;
  hKeya = 0;
  *a4 = 0;
  if ( v9 )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
    v7 = hKeya;
  }
  if ( dword_1800A55B0 )
    samDesired = 131334;
  v11 = 0;
  if ( lpSubKey )
  {
    v12 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &hKeya, 0);
    if ( v12 )
    {
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
      else
        v11 = v12;
      v7 = hKeya;
    }
    else
    {
      v7 = 0;
      *a4 = hKeya;
      hKeya = 0;
    }
  }
  else
  {
    *a4 = hKey;
  }
  if ( v7 )
    RegCloseKey(v7);
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
      a5 = v11;
      v17 = &gc_pszVersionString;
      v21 = 0;
      v16 = lpSubKey;
      v18 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_180092FCD,
        0,
        v14,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v21,
        (__int64)&a5);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002555c  mov     [rsp-8+arg_0], rbx
0x180025561  mov     [rsp-8+hKey], r8
0x180025566  push    rbp
0x180025567  push    rsi
0x180025568  push    rdi
0x180025569  push    r14
0x18002556b  push    r15
0x18002556d  lea     rbp, [rsp-2Fh]
0x180025572  sub     rsp, 0A0h
0x180025579  mov     r15, rcx
0x18002557c  mov     rdi, r9
0x18002557f  xor     ecx, ecx
0x180025581  mov     r14, rdx
0x180025584  cmp     cs:dword_1800A55AC, ecx
0x18002558a  mov     esi, 20006h
0x18002558f  mov     [rbp+4Fh+hKey], rcx
0x180025593  mov     [r9], rcx
0x180025596  jnz     short loc_1800255DE
0x180025598  xorps   xmm0, xmm0
0x18002559b  mov     cs:dword_1800A55B0, ecx
0x1800255a1  lea     rcx, [rbp+4Fh+SystemInfo]; lpSystemInfo
0x1800255a5  movups  xmmword ptr [rbp+4Fh+SystemInfo], xmm0
0x1800255a9  movups  xmmword ptr [rbp+4Fh+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800255ad  movups  xmmword ptr [rbp+4Fh+SystemInfo.dwNumberOfProcessors], xmm0
0x1800255b1  call    cs:__imp_GetNativeSystemInfo
0x1800255b7  mov     eax, 6
0x1800255bc  lea     ecx, [rax-5]
0x1800255bf  cmp     ax, word ptr [rbp+4Fh+SystemInfo]
0x1800255c3  jz      short loc_1800255CE
0x1800255c5  lea     eax, [rcx+8]
0x1800255c8  cmp     ax, word ptr [rbp+4Fh+SystemInfo]
0x1800255cc  jnz     short loc_1800255D4
0x1800255ce  mov     cs:dword_1800A55B0, ecx
0x1800255d4  mov     cs:dword_1800A55AC, ecx
0x1800255da  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800255de  cmp     cs:dword_1800A55B0, 0
0x1800255e5  mov     eax, 20106h
0x1800255ea  cmovnz  esi, eax
0x1800255ed  xor     ebx, ebx
0x1800255ef  test    r14, r14
0x1800255f2  jz      short loc_180025649
0x1800255f4  mov     [rsp+0C0h+lpdwDisposition], rbx; lpdwDisposition
0x1800255f9  lea     rax, [rbp+4Fh+hKey]
0x1800255fd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180025602  xor     r9d, r9d; lpClass
0x180025605  mov     [rsp+0C0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002560a  xor     r8d, r8d; Reserved
0x18002560d  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180025611  mov     rdx, r14; lpSubKey
0x180025614  mov     rcx, r15; hKey
0x180025617  mov     [rsp+0C0h+dwOptions], ebx; dwOptions
0x18002561b  call    cs:__imp_RegCreateKeyExW
0x180025621  test    eax, eax
0x180025623  jz      short loc_18002563A
0x180025625  jg      short loc_18002562B
0x180025627  mov     ebx, eax
0x180025629  jmp     short loc_180025634
0x18002562b  movzx   ebx, ax
0x18002562e  or      ebx, 80070000h
0x180025634  mov     rcx, [rbp+4Fh+hKey]
0x180025638  jmp     short loc_18002564C
0x18002563a  mov     rax, [rbp+4Fh+hKey]
0x18002563e  xor     ecx, ecx
0x180025640  mov     [rdi], rax
0x180025643  mov     [rbp+4Fh+hKey], rcx
0x180025647  jmp     short loc_18002564C
0x180025649  mov     [rdi], r15
0x18002564c  test    rcx, rcx
0x18002564f  jz      short loc_180025657
0x180025651  call    cs:__imp_RegCloseKey
0x180025657  test    ebx, ebx
0x180025659  jns     loc_180025706
0x18002565f  xor     r9d, r9d
0x180025662  mov     [rsp+0C0h+dwOptions], ebx
0x180025666  mov     r8, r14
0x180025669  lea     rdx, aRegutilErrorWh_5; "RegUtil: Error when attempting to creat"...
0x180025670  lea     ecx, [r9+2]; unsigned __int8
0x180025674  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025679  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18002567e  mov     rcx, [rax+8]
0x180025682  mov     eax, [rcx]
0x180025684  cmp     eax, 5
0x180025687  jbe     short loc_180025706
0x180025689  mov     rdx, [rcx+18h]
0x18002568d  mov     r8, 400000000000h
0x180025697  mov     rax, [rcx+10h]
0x18002569b  test    r8, rax
0x18002569e  jz      short loc_180025706
0x1800256a0  mov     rax, rdx
0x1800256a3  and     rax, r8
0x1800256a6  cmp     rax, rdx
0x1800256a9  jnz     short loc_180025706
0x1800256ab  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800256b2  mov     [rbp+4Fh+arg_20], ebx
0x1800256b5  mov     [rbp+4Fh+var_68], rax
0x1800256b9  lea     rdx, byte_180092FCD
0x1800256c0  lea     rax, [rbp+4Fh+arg_20]
0x1800256c4  mov     [rbp+4Fh+arg_18], 0
0x1800256cc  mov     [rsp+0C0h+lpdwDisposition], rax
0x1800256d1  lea     rax, [rbp+4Fh+arg_18]
0x1800256d5  mov     [rsp+0C0h+phkResult], rax
0x1800256da  lea     rax, [rbp+4Fh+var_70]
0x1800256de  mov     [rsp+0C0h+lpSecurityAttributes], rax
0x1800256e3  lea     rax, [rbp+4Fh+var_68]
0x1800256e7  mov     qword ptr [rsp+0C0h+samDesired], rax
0x1800256ec  lea     rax, [rbp+4Fh+var_60]
0x1800256f0  mov     qword ptr [rsp+0C0h+dwOptions], rax
0x1800256f5  mov     [rbp+4Fh+var_70], r14
0x1800256f9  mov     [rbp+4Fh+var_60], 1000000h
0x180025701  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180025706  mov     eax, ebx
0x180025708  mov     rbx, [rsp+0C0h+arg_0]
0x180025710  add     rsp, 0A0h
0x180025717  pop     r15
0x180025719  pop     r14
0x18002571b  pop     rdi
0x18002571c  pop     rsi
0x18002571d  pop     rbp
0x18002571e  retn
```
