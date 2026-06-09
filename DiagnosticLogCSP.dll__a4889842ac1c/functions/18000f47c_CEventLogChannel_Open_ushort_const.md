# CEventLogChannel::Open(ushort const *)

- ea: `0x18000f47c`
- end: `0x18000f57a`
- name: `?Open@CEventLogChannel@@QEAAJPEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008ac0`
- `0x180008dc0`
- `0x180008f70`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x18000f47c`
- `0x18001107c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000f4c7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000f4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ba`

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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v11 = v6;
    if ( !v4 )
      v4 = &String2;
    v12 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18003F935,
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
0x18000f47c  mov     [rsp+arg_10], rbx
0x18000f481  mov     [rsp+arg_18], rsi
0x18000f486  push    rdi
0x18000f487  sub     rsp, 260h
0x18000f48e  mov     rax, cs:__security_cookie
0x18000f495  xor     rax, rsp
0x18000f498  mov     [rsp+268h+var_18], rax
0x18000f4a0  mov     rdi, rdx
0x18000f4a3  mov     rsi, rcx
0x18000f4a6  test    rdx, rdx
0x18000f4a9  jnz     short loc_18000F4B2
0x18000f4ab  mov     ebx, 80070057h
0x18000f4b0  jmp     short loc_18000F511
0x18000f4b2  mov     rcx, [rcx]; hKey
0x18000f4b5  test    rcx, rcx
0x18000f4b8  jz      short loc_18000F4C7
0x18000f4ba  call    cs:__imp_RegCloseKey
0x18000f4c0  mov     qword ptr [rsi], 0
0x18000f4c7  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000f4cd  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000f4d4  mov     [rsp+268h+var_248], rdi
0x18000f4d9  test    al, al
0x18000f4db  lea     r9, aOsdataSoftware_1; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000f4e2  lea     r8, aSS_0; "%s\\%s"
0x18000f4e9  mov     edx, 104h; unsigned __int64
0x18000f4ee  cmovz   r9, rcx
0x18000f4f2  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18000f4f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f4fc  mov     ebx, eax
0x18000f4fe  test    eax, eax
0x18000f500  js      short loc_18000F511
0x18000f502  mov     rdx, rsi; struct ATL::CRegKey *
0x18000f505  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18000f50a  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000f50f  mov     ebx, eax
0x18000f511  mov     eax, cs:dword_180048E90
0x18000f517  cmp     eax, 5
0x18000f51a  jbe     short loc_18000F553
0x18000f51c  test    rdi, rdi
0x18000f51f  mov     [rsp+268h+var_238], ebx
0x18000f523  lea     rax, String2
0x18000f52a  cmovz   rdi, rax
0x18000f52e  lea     rdx, byte_18003F935
0x18000f535  lea     rax, [rsp+268h+var_238]
0x18000f53a  mov     [rsp+268h+var_230], rdi
0x18000f53f  mov     [rsp+268h+var_240], rax
0x18000f544  lea     rax, [rsp+268h+var_230]
0x18000f549  mov     [rsp+268h+var_248], rax
0x18000f54e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f553  mov     eax, ebx
0x18000f555  mov     rcx, [rsp+268h+var_18]
0x18000f55d  xor     rcx, rsp; StackCookie
0x18000f560  call    __security_check_cookie
0x18000f565  lea     r11, [rsp+268h+var_8]
0x18000f56d  mov     rbx, [r11+20h]
0x18000f571  mov     rsi, [r11+28h]
0x18000f575  mov     rsp, r11
0x18000f578  pop     rdi
0x18000f579  retn
```
