# CEtwLogCollector::Open(ushort const *)

- ea: `0x18000e744`
- end: `0x18000e84f`
- name: `?Open@CEtwLogCollector@@QEAAJPEBG@Z`
- size: `267`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007850`
- `0x180007bb0`
- `0x180007d00`
- `0x180007e30`
- `0x180008270`
- `0x180008580`
- `0x18000f228`
- `0x180012840`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x18000e744`
- `0x180011930`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e795`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e782`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e782`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v11 = v6;
    if ( !v4 )
      v4 = &String2;
    v12 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (unsigned __int8 *)byte_180041777,
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
0x18000e744  mov     [rsp+arg_10], rbx
0x18000e749  mov     [rsp+arg_18], rsi
0x18000e74e  push    rdi
0x18000e74f  sub     rsp, 260h
0x18000e756  mov     rax, cs:__security_cookie
0x18000e75d  xor     rax, rsp
0x18000e760  mov     [rsp+268h+var_18], rax
0x18000e768  mov     rdi, rdx
0x18000e76b  mov     rsi, rcx
0x18000e76e  test    rdx, rdx
0x18000e771  jnz     short loc_18000E77A
0x18000e773  mov     ebx, 80070057h
0x18000e778  jmp     short loc_18000E7E5
0x18000e77a  mov     rcx, [rcx]; hKey
0x18000e77d  test    rcx, rcx
0x18000e780  jz      short loc_18000E795
0x18000e782  call    cs:__imp_RegCloseKey
0x18000e789  nop     dword ptr [rax+rax+00h]
0x18000e78e  mov     qword ptr [rsi], 0
0x18000e795  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000e79c  nop     dword ptr [rax+rax+00h]
0x18000e7a1  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000e7a8  mov     [rsp+268h+var_248], rdi
0x18000e7ad  test    al, al
0x18000e7af  lea     r9, aOsdataSoftware_2; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000e7b6  lea     r8, aSS_0; "%s\\%s"
0x18000e7bd  mov     edx, 104h; unsigned __int64
0x18000e7c2  cmovz   r9, rcx
0x18000e7c6  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18000e7cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e7d0  mov     ebx, eax
0x18000e7d2  test    eax, eax
0x18000e7d4  js      short loc_18000E7E5
0x18000e7d6  mov     rdx, rsi; struct ATL::CRegKey *
0x18000e7d9  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18000e7de  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000e7e3  mov     ebx, eax
0x18000e7e5  mov     eax, cs:dword_18004AE90
0x18000e7eb  cmp     eax, 5
0x18000e7ee  jbe     short loc_18000E827
0x18000e7f0  test    rdi, rdi
0x18000e7f3  mov     [rsp+268h+var_238], ebx
0x18000e7f7  lea     rax, String2
0x18000e7fe  cmovz   rdi, rax
0x18000e802  lea     rdx, byte_180041777
0x18000e809  lea     rax, [rsp+268h+var_238]
0x18000e80e  mov     [rsp+268h+var_230], rdi
0x18000e813  mov     [rsp+268h+var_240], rax
0x18000e818  lea     rax, [rsp+268h+var_230]
0x18000e81d  mov     [rsp+268h+var_248], rax
0x18000e822  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e827  mov     eax, ebx
0x18000e829  mov     rcx, [rsp+268h+var_18]
0x18000e831  xor     rcx, rsp; StackCookie
0x18000e834  call    __security_check_cookie
0x18000e839  lea     r11, [rsp+268h+var_8]
0x18000e841  mov     rbx, [r11+20h]
0x18000e845  mov     rsi, [r11+28h]
0x18000e849  mov     rsp, r11
0x18000e84c  pop     rdi
0x18000e84d  retn
```
