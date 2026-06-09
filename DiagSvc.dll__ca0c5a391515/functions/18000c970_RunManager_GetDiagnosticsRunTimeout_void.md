# RunManager::GetDiagnosticsRunTimeout(void)

- ea: `0x18000c970`
- end: `0x18000cac2`
- name: `?GetDiagnosticsRunTimeout@RunManager@@MEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(RunManager *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180001720`
- `0x180001fec`
- `0x18000c970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c9c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c9c7`

## string_xrefs

- `0x18000c9b9`: `SYSTEM\CurrentControlSet\Services\diagsvc\Settings`

## pseudocode

```c
__int64 __fastcall RunManager::GetDiagnosticsRunTimeout(RunManager *this)
{
  unsigned int ValueW; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // ecx
  signed int v6; // r8d
  int v7; // r9d
  int v9; // [rsp+68h] [rbp+27h] BYREF
  signed int v10; // [rsp+6Ch] [rbp+2Bh] BYREF
  char *v11; // [rsp+70h] [rbp+2Fh] BYREF
  const char *v12; // [rsp+78h] [rbp+37h] BYREF
  const char *v13; // [rsp+80h] [rbp+3Fh] BYREF
  const char *v14; // [rsp+88h] [rbp+47h] BYREF
  char *v15; // [rsp+90h] [rbp+4Fh] BYREF
  unsigned int v16; // [rsp+B0h] [rbp+6Fh] BYREF
  DWORD v17; // [rsp+B8h] [rbp+77h] BYREF
  int v18; // [rsp+C0h] [rbp+7Fh] BYREF

  v16 = 0;
  v17 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\diagsvc\\Settings",
             L"TimeoutMs",
             0x10u,
             0,
             &v16,
             &v17);
  if ( !ValueW )
  {
    v4 = v16;
    if ( v16 - 1 <= 0x493DF )
      *((_DWORD *)this + 96) = v16;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, ValueW) )
  {
    v18 = *((_DWORD *)this + 96);
    v11 = (char *)this + 112;
    v12 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v13 = "RunManager::GetDiagnosticsRunTimeout";
    v14 = "Get Diagnostic Run Timeout";
    v9 = 174;
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v10 = v6;
    v15 = (char *)this + 241;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&unk_18002FFF8,
      v6,
      v7,
      (__int64)&v15,
      (__int64)&v10,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v9,
      (__int64)&v11,
      (__int64)&v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c970  mov     r11, rsp
0x18000c973  mov     [r11+8], rbx
0x18000c977  push    rbp
0x18000c978  lea     rbp, [r11-5Fh]
0x18000c97c  sub     rsp, 90h
0x18000c983  lea     rax, [rbp+57h+arg_10]
0x18000c987  mov     [rbp+57h+arg_8], 0
0x18000c98e  mov     [r11-68h], rax
0x18000c992  lea     r8, Value; "TimeoutMs"
0x18000c999  lea     rax, [rbp+57h+arg_8]
0x18000c99d  mov     [rbp+57h+arg_10], 4
0x18000c9a4  mov     rbx, rcx
0x18000c9a7  mov     [r11-70h], rax
0x18000c9ab  mov     r9d, 10h; dwFlags
0x18000c9b1  mov     qword ptr [r11-78h], 0
0x18000c9b9  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\di"...
0x18000c9c0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c9c7  call    cs:__imp_RegGetValueW
0x18000c9cd  mov     r8d, eax
0x18000c9d0  test    eax, eax
0x18000c9d2  jnz     short loc_18000C9E7
0x18000c9d4  mov     ecx, [rbp+57h+arg_8]
0x18000c9d7  lea     eax, [rcx-1]
0x18000c9da  cmp     eax, 493DFh
0x18000c9df  ja      short loc_18000C9E7
0x18000c9e1  mov     [rbx+180h], ecx
0x18000c9e7  mov     eax, cs:dword_180039000
0x18000c9ed  cmp     eax, 5
0x18000c9f0  jbe     loc_18000CAAF
0x18000c9f6  call    _tlgKeywordOn
0x18000c9fb  test    al, al
0x18000c9fd  jz      loc_18000CAAF
0x18000ca03  mov     eax, [rbx+180h]
0x18000ca09  mov     [rbp+57h+arg_18], eax
0x18000ca0c  lea     rax, [rbx+70h]
0x18000ca10  mov     [rbp+57h+var_28], rax
0x18000ca14  lea     rax, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000ca1b  mov     [rbp+57h+var_20], rax
0x18000ca1f  lea     rax, aRunmanagerGetd_0; "RunManager::GetDiagnosticsRunTimeout"
0x18000ca26  mov     [rbp+57h+var_18], rax
0x18000ca2a  lea     rax, aGetDiagnosticR; "Get Diagnostic Run Timeout"
0x18000ca31  mov     [rbp+57h+var_10], rax
0x18000ca35  mov     [rbp+57h+var_30], 0AEh
0x18000ca3c  test    r8d, r8d
0x18000ca3f  jle     short loc_18000CA4C
0x18000ca41  movzx   r8d, r8w
0x18000ca45  or      r8d, 80070000h
0x18000ca4c  lea     rax, [rbx+0F1h]
0x18000ca53  mov     [rbp+57h+var_2C], r8d
0x18000ca57  mov     [rbp+57h+var_8], rax
0x18000ca5b  lea     rdx, unk_18002FFF8
0x18000ca62  lea     rax, [rbp+57h+arg_18]
0x18000ca66  mov     [rsp+58h], rax
0x18000ca6b  lea     rax, [rbp+57h+var_28]
0x18000ca6f  mov     [rsp+90h+var_40], rax
0x18000ca74  lea     rax, [rbp+57h+var_30]
0x18000ca78  mov     [rsp+90h+var_48], rax
0x18000ca7d  lea     rax, [rbp+57h+var_20]
0x18000ca81  mov     [rsp+90h+var_50], rax
0x18000ca86  lea     rax, [rbp+57h+var_18]
0x18000ca8a  mov     [rsp+90h+var_58], rax
0x18000ca8f  lea     rax, [rbp+57h+var_10]
0x18000ca93  mov     [rsp+90h+var_60], rax
0x18000ca98  lea     rax, [rbp+57h+var_2C]
0x18000ca9c  mov     [rsp+90h+var_68], rax
0x18000caa1  lea     rax, [rbp+57h+var_8]
0x18000caa5  mov     [rsp+90h+var_70], rax
0x18000caaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000caaf  mov     rbx, [rsp+90h+arg_0]
0x18000cab7  xor     eax, eax
0x18000cab9  add     rsp, 90h
0x18000cac0  pop     rbp
0x18000cac1  retn
```
