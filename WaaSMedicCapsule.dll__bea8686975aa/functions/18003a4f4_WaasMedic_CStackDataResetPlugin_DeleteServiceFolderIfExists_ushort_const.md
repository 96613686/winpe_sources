# WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(ushort const *)

- ea: `0x18003a4f4`
- end: `0x18003a647`
- name: `?DeleteServiceFolderIfExists@CStackDataResetPlugin@WaasMedic@@AEAAJPEBG@Z`
- size: `339`
- prototype: `int(WaasMedic::CStackDataResetPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x18003b8c0`

## callees

- `0x1800024a4`
- `0x180003bb0`
- `0x180004708`
- `0x180016c9c`
- `0x18002543c`
- `0x18002aa74`
- `0x18003a4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a542`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003a538`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003a538`

## string_xrefs

- `0x18003a557`: `Failed to expand path %s! hr = 0x%08x`
- `0x18003a5a1`: `Failed to delete %s, hr = 0x%08X.`
- `0x18003a57c`: `Failed to expand path %s due to insufficient buffer! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(
        WaasMedic::CStackDataResetPlugin *this,
        const unsigned __int16 *a2)
{
  DWORD v3; // eax
  const unsigned __int16 *v4; // rdx
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // eax
  const struct _tlgProvider_t *v8; // rax
  int v9; // r9d
  unsigned int v11; // [rsp+40h] [rbp-248h] BYREF
  WCHAR *v12; // [rsp+48h] [rbp-240h] BYREF
  __int64 v13; // [rsp+50h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  v3 = ExpandEnvironmentStringsW(a2, Dst, 0x104u);
  if ( v3 )
  {
    if ( v3 <= 0x104 )
    {
      v7 = WaasMedic::DeleteDirectoryWithRenameIfExists((WaasMedic *)Dst, v4);
      v6 = v7;
      if ( v7 < 0 )
      {
        LogLevelW(2u, L"Failed to delete %s, hr = 0x%08X.", Dst, (unsigned int)v7);
        v8 = WaasMedic::TelemetryProvider::Provider();
        if ( *(_DWORD *)v8 > 5u
          && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
        {
          v11 = v6;
          v12 = Dst;
          v13 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v8,
            (unsigned int)&word_180089776,
            0,
            v9,
            (__int64)&v13,
            (__int64)&v12,
            (__int64)&v11);
        }
      }
    }
    else
    {
      v6 = -2147024774;
      LogLevelW(2u, L"Failed to expand path %s due to insufficient buffer! hr = 0x%08x", a2, 2147942522LL);
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to expand path %s! hr = 0x%08x", a2, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18003a4f4  mov     [rsp+arg_0], rbx
0x18003a4f9  push    rdi
0x18003a4fa  sub     rsp, 280h
0x18003a501  mov     rax, cs:__security_cookie
0x18003a508  xor     rax, rsp
0x18003a50b  mov     [rsp+288h+var_18], rax
0x18003a513  mov     rdi, rdx
0x18003a516  lea     rcx, [rsp+288h+Dst]; void *
0x18003a51b  xor     edx, edx; Val
0x18003a51d  mov     r8d, 208h; Size
0x18003a523  call    memset_0
0x18003a528  mov     ebx, 104h
0x18003a52d  lea     rdx, [rsp+288h+Dst]; lpDst
0x18003a532  mov     r8d, ebx; nSize
0x18003a535  mov     rcx, rdi; lpSrc
0x18003a538  call    cs:__imp_ExpandEnvironmentStringsW
0x18003a53e  test    eax, eax
0x18003a540  jnz     short loc_18003A573
0x18003a542  call    cs:__imp_GetLastError
0x18003a548  mov     ebx, eax
0x18003a54a  test    eax, eax
0x18003a54c  jle     short loc_18003A557
0x18003a54e  movzx   ebx, ax
0x18003a551  or      ebx, 80070000h
0x18003a557  lea     rdx, aFailedToExpand_1; "Failed to expand path %s! hr = 0x%08x"
0x18003a55e  mov     r8, rdi
0x18003a561  mov     r9d, ebx
0x18003a564  mov     ecx, 2; unsigned __int8
0x18003a569  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a56e  jmp     loc_18003A624
0x18003a573  cmp     eax, ebx
0x18003a575  jbe     short loc_18003A585
0x18003a577  mov     ebx, 8007007Ah
0x18003a57c  lea     rdx, aFailedToExpand_3; "Failed to expand path %s due to insuffi"...
0x18003a583  jmp     short loc_18003A55E
0x18003a585  lea     rcx, [rsp+288h+Dst]; this
0x18003a58a  call    ?DeleteDirectoryWithRenameIfExists@WaasMedic@@YAJPEBG_N@Z; WaasMedic::DeleteDirectoryWithRenameIfExists(ushort const *,bool)
0x18003a58f  mov     ebx, eax
0x18003a591  test    eax, eax
0x18003a593  jns     loc_18003A624
0x18003a599  mov     r9d, eax
0x18003a59c  lea     r8, [rsp+288h+Dst]
0x18003a5a1  lea     rdx, aFailedToDelete_0; "Failed to delete %s, hr = 0x%08X."
0x18003a5a8  mov     ecx, 2; unsigned __int8
0x18003a5ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a5b2  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18003a5b7  mov     ecx, [rax]
0x18003a5b9  cmp     ecx, 5
0x18003a5bc  jbe     short loc_18003A624
0x18003a5be  mov     rdx, [rax+18h]
0x18003a5c2  mov     r8, 400000000000h
0x18003a5cc  mov     rcx, [rax+10h]
0x18003a5d0  test    r8, rcx
0x18003a5d3  jz      short loc_18003A624
0x18003a5d5  mov     rcx, rdx
0x18003a5d8  and     rcx, r8
0x18003a5db  cmp     rcx, rdx
0x18003a5de  jnz     short loc_18003A624
0x18003a5e0  lea     rcx, [rsp+288h+Dst]
0x18003a5e5  mov     [rsp+288h+var_248], ebx
0x18003a5e9  mov     [rsp+288h+var_240], rcx
0x18003a5ee  lea     rdx, word_180089776
0x18003a5f5  lea     rcx, [rsp+288h+var_248]
0x18003a5fa  mov     [rsp+288h+var_238], 1000000h
0x18003a603  mov     [rsp+288h+var_258], rcx
0x18003a608  lea     rcx, [rsp+288h+var_240]
0x18003a60d  mov     [rsp+288h+var_260], rcx
0x18003a612  lea     rcx, [rsp+288h+var_238]
0x18003a617  mov     [rsp+288h+var_268], rcx
0x18003a61c  mov     rcx, rax
0x18003a61f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003a624  mov     eax, ebx
0x18003a626  mov     rcx, [rsp+288h+var_18]
0x18003a62e  xor     rcx, rsp; StackCookie
0x18003a631  call    __security_check_cookie
0x18003a636  mov     rbx, [rsp+288h+arg_0]
0x18003a63e  add     rsp, 280h
0x18003a645  pop     rdi
0x18003a646  retn
```
