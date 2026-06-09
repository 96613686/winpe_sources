# CEventLogChannel::Open(ushort const *)

- ea: `0x18000fc24`
- end: `0x18000fd2f`
- name: `?Open@CEventLogChannel@@QEAAJPEBG@Z`
- size: `267`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008cc0`
- `0x180008ff0`
- `0x1800091b0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180006498`
- `0x18000fc24`
- `0x180011930`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000fc75`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000fc75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc62`

## pseudocode

```c
__int64 __fastcall CEventLogChannel::Open(HKEY *this, const unsigned __int16 *a2, __int64 a3, __int64 a4)
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
    v9 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\EtwLog\\Registered\\Channels";
    if ( !IsStateSeparationEnabled )
      v9 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\EtwLog\\Registered\\Channels";
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
      (unsigned __int8 *)byte_180041935,
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
0x18000fc24  mov     [rsp+arg_10], rbx
0x18000fc29  mov     [rsp+arg_18], rsi
0x18000fc2e  push    rdi
0x18000fc2f  sub     rsp, 260h
0x18000fc36  mov     rax, cs:__security_cookie
0x18000fc3d  xor     rax, rsp
0x18000fc40  mov     [rsp+268h+var_18], rax
0x18000fc48  mov     rdi, rdx
0x18000fc4b  mov     rsi, rcx
0x18000fc4e  test    rdx, rdx
0x18000fc51  jnz     short loc_18000FC5A
0x18000fc53  mov     ebx, 80070057h
0x18000fc58  jmp     short loc_18000FCC5
0x18000fc5a  mov     rcx, [rcx]; hKey
0x18000fc5d  test    rcx, rcx
0x18000fc60  jz      short loc_18000FC75
0x18000fc62  call    cs:__imp_RegCloseKey
0x18000fc69  nop     dword ptr [rax+rax+00h]
0x18000fc6e  mov     qword ptr [rsi], 0
0x18000fc75  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000fc7c  nop     dword ptr [rax+rax+00h]
0x18000fc81  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000fc88  mov     [rsp+268h+var_248], rdi
0x18000fc8d  test    al, al
0x18000fc8f  lea     r9, aOsdataSoftware_1; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000fc96  lea     r8, aSS_0; "%s\\%s"
0x18000fc9d  mov     edx, 104h; unsigned __int64
0x18000fca2  cmovz   r9, rcx
0x18000fca6  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18000fcab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fcb0  mov     ebx, eax
0x18000fcb2  test    eax, eax
0x18000fcb4  js      short loc_18000FCC5
0x18000fcb6  mov     rdx, rsi; struct ATL::CRegKey *
0x18000fcb9  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18000fcbe  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000fcc3  mov     ebx, eax
0x18000fcc5  mov     eax, cs:dword_18004AE90
0x18000fccb  cmp     eax, 5
0x18000fcce  jbe     short loc_18000FD07
0x18000fcd0  test    rdi, rdi
0x18000fcd3  mov     [rsp+268h+var_238], ebx
0x18000fcd7  lea     rax, String2
0x18000fcde  cmovz   rdi, rax
0x18000fce2  lea     rdx, byte_180041935
0x18000fce9  lea     rax, [rsp+268h+var_238]
0x18000fcee  mov     [rsp+268h+var_230], rdi
0x18000fcf3  mov     [rsp+268h+var_240], rax
0x18000fcf8  lea     rax, [rsp+268h+var_230]
0x18000fcfd  mov     [rsp+268h+var_248], rax
0x18000fd02  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000fd07  mov     eax, ebx
0x18000fd09  mov     rcx, [rsp+268h+var_18]
0x18000fd11  xor     rcx, rsp; StackCookie
0x18000fd14  call    __security_check_cookie
0x18000fd19  lea     r11, [rsp+268h+var_8]
0x18000fd21  mov     rbx, [r11+20h]
0x18000fd25  mov     rsi, [r11+28h]
0x18000fd29  mov     rsp, r11
0x18000fd2c  pop     rdi
0x18000fd2d  retn
```
