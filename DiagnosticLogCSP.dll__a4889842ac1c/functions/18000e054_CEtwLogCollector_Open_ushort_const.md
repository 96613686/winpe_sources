# CEtwLogCollector::Open(ushort const *)

- ea: `0x18000e054`
- end: `0x18000e152`
- name: `?Open@CEtwLogCollector@@QEAAJPEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800076d0`
- `0x180007a30`
- `0x180007b80`
- `0x180007ca0`
- `0x180008080`
- `0x180008380`
- `0x18000eaf8`
- `0x180011e94`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x18000e054`
- `0x18001107c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e09f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e09f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e092`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::Open(HKEY *this, const unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  const WCHAR *v4; // rdi
  int v6; // ebx
  HKEY v7; // rcx
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // r9
  int v11; // [rsp+30h] [rbp-238h] BYREF
  const WCHAR *v12; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  v4 = a2;
  if ( a2 )
  {
    v7 = *this;
    if ( v7 )
    {
      RegCloseKey(v7);
      *this = 0;
    }
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v9 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\EtwLog\\Registered\\Collectors";
    if ( !IsStateSeparationEnabled )
      v9 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\EtwLog\\Registered\\Collectors";
    v6 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v9, v4);
    if ( v6 >= 0 )
      v6 = CRegUtils::OpenKey(SubKey, this);
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v11 = v6;
    if ( !v4 )
      v4 = &String2;
    v12 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&byte_18003F777,
      a3,
      a4,
      &v12,
      (__int64)&v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e054  mov     [rsp+arg_10], rbx
0x18000e059  mov     [rsp+arg_18], rsi
0x18000e05e  push    rdi
0x18000e05f  sub     rsp, 260h
0x18000e066  mov     rax, cs:__security_cookie
0x18000e06d  xor     rax, rsp
0x18000e070  mov     [rsp+268h+var_18], rax
0x18000e078  mov     rdi, rdx
0x18000e07b  mov     rsi, rcx
0x18000e07e  test    rdx, rdx
0x18000e081  jnz     short loc_18000E08A
0x18000e083  mov     ebx, 80070057h
0x18000e088  jmp     short loc_18000E0E9
0x18000e08a  mov     rcx, [rcx]; hKey
0x18000e08d  test    rcx, rcx
0x18000e090  jz      short loc_18000E09F
0x18000e092  call    cs:__imp_RegCloseKey
0x18000e098  mov     qword ptr [rsi], 0
0x18000e09f  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000e0a5  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000e0ac  mov     [rsp+268h+var_248], rdi
0x18000e0b1  test    al, al
0x18000e0b3  lea     r9, aOsdataSoftware_2; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000e0ba  lea     r8, aSS_0; "%s\\%s"
0x18000e0c1  mov     edx, 104h; unsigned __int64
0x18000e0c6  cmovz   r9, rcx
0x18000e0ca  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18000e0cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e0d4  mov     ebx, eax
0x18000e0d6  test    eax, eax
0x18000e0d8  js      short loc_18000E0E9
0x18000e0da  mov     rdx, rsi; struct ATL::CRegKey *
0x18000e0dd  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18000e0e2  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000e0e7  mov     ebx, eax
0x18000e0e9  mov     eax, cs:dword_180048E90
0x18000e0ef  cmp     eax, 5
0x18000e0f2  jbe     short loc_18000E12B
0x18000e0f4  test    rdi, rdi
0x18000e0f7  mov     [rsp+268h+var_238], ebx
0x18000e0fb  lea     rax, String2
0x18000e102  cmovz   rdi, rax
0x18000e106  lea     rdx, byte_18003F777
0x18000e10d  lea     rax, [rsp+268h+var_238]
0x18000e112  mov     [rsp+268h+var_230], rdi
0x18000e117  mov     [rsp+268h+var_240], rax
0x18000e11c  lea     rax, [rsp+268h+var_230]
0x18000e121  mov     [rsp+268h+var_248], rax
0x18000e126  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e12b  mov     eax, ebx
0x18000e12d  mov     rcx, [rsp+268h+var_18]
0x18000e135  xor     rcx, rsp; StackCookie
0x18000e138  call    __security_check_cookie
0x18000e13d  lea     r11, [rsp+268h+var_8]
0x18000e145  mov     rbx, [r11+20h]
0x18000e149  mov     rsi, [r11+28h]
0x18000e14d  mov     rsp, r11
0x18000e150  pop     rdi
0x18000e151  retn
```
