# DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)

- ea: `0x180005768`
- end: `0x1800058e5`
- name: `?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z`
- size: `381`
- prototype: `void __fastcall(DiagnosticServer *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180005a24`
- `0x180005eac`
- `0x180005f7c`

## callees

- `0x180001570`
- `0x180001720`
- `0x180005768`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800057f7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800057f7`

## string_xrefs

- `0x18000582b`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005841`: `Report service status`

## pseudocode

```c
void __fastcall DiagnosticServer::ReportSvcStatus(DiagnosticServer *this, int a2, int a3, int a4)
{
  int v5; // eax
  int v6; // ecx
  SERVICE_STATUS_HANDLE v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+88h] [rbp-1h] BYREF
  const char *v15; // [rsp+90h] [rbp+7h] BYREF
  const char *v16; // [rsp+98h] [rbp+Fh] BYREF
  const char *v17; // [rsp+A0h] [rbp+17h] BYREF
  char *v18; // [rsp+A8h] [rbp+1Fh] BYREF

  if ( a2 == 1 )
  {
    v5 = 0;
    *((_DWORD *)this + 8) = 1025;
    v6 = 0;
  }
  else if ( a2 == 2 || a2 == 3 )
  {
    v5 = dword_1800396B8;
    *((_DWORD *)this + 8) = 0;
    v6 = v5 + 1;
  }
  else
  {
    if ( a2 == 4 )
    {
      *((_DWORD *)this + 8) = 1029;
      v5 = 0;
    }
    else
    {
      v5 = dword_1800396B8;
    }
    v6 = v5 + 1;
  }
  dword_1800396B8 = v6;
  *((_DWORD *)this + 11) = v5;
  v7 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 2);
  *((_DWORD *)this + 7) = a2;
  *((_DWORD *)this + 9) = a3;
  *((_DWORD *)this + 12) = a4;
  SetServiceStatus(v7, (LPSERVICE_STATUS)((char *)this + 24));
  if ( (unsigned int)dword_180039000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v9, v8, v10) )
    {
      v15 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
      v16 = "DiagnosticServer::ReportSvcStatus";
      v17 = "Report service status";
      v18 = (char *)this + 120;
      v14 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (__int64)&word_18002EBA6,
        v12,
        v13,
        &v18,
        (__int64)&v14,
        &v17,
        &v16,
        &v15);
    }
  }
}

```

## disassembly

```asm
0x180005768  push    rbp
0x18000576a  push    rbx
0x18000576b  push    rsi
0x18000576c  push    rdi
0x18000576d  push    r14
0x18000576f  push    r15
0x180005771  lea     rbp, [rsp-2Fh]
0x180005776  sub     rsp, 0B8h
0x18000577d  mov     eax, edx
0x18000577f  mov     r14d, r9d
0x180005782  mov     r15d, r8d
0x180005785  mov     esi, edx
0x180005787  mov     rbx, rcx
0x18000578a  sub     eax, 1
0x18000578d  jz      short loc_1800057CD
0x18000578f  sub     eax, 1
0x180005792  jz      short loc_1800057B8
0x180005794  sub     eax, 1
0x180005797  jz      short loc_1800057B8
0x180005799  cmp     eax, 1
0x18000579c  jnz     short loc_1800057A9
0x18000579e  mov     dword ptr [rcx+20h], 405h
0x1800057a5  xor     eax, eax
0x1800057a7  jmp     short loc_1800057AF
0x1800057a9  mov     eax, cs:dword_1800396B8
0x1800057af  lea     ecx, [rax+1]
0x1800057b2  lea     rdi, [rbx+20h]
0x1800057b6  jmp     short loc_1800057DB
0x1800057b8  mov     eax, cs:dword_1800396B8
0x1800057be  lea     rdi, [rcx+20h]
0x1800057c2  mov     dword ptr [rdi], 0
0x1800057c8  lea     ecx, [rax+1]
0x1800057cb  jmp     short loc_1800057DB
0x1800057cd  lea     rdi, [rcx+20h]
0x1800057d1  xor     eax, eax
0x1800057d3  mov     dword ptr [rdi], 401h
0x1800057d9  xor     ecx, ecx
0x1800057db  mov     cs:dword_1800396B8, ecx
0x1800057e1  lea     rdx, [rbx+18h]; lpServiceStatus
0x1800057e5  mov     [rbx+2Ch], eax
0x1800057e8  mov     rcx, [rbx+10h]; hServiceStatus
0x1800057ec  mov     [rdx+4], esi
0x1800057ef  mov     [rbx+24h], r15d
0x1800057f3  mov     [rbx+30h], r14d
0x1800057f7  call    cs:__imp_SetServiceStatus
0x1800057fd  mov     eax, cs:dword_180039000
0x180005803  cmp     eax, 5
0x180005806  jbe     loc_1800058D5
0x18000580c  call    _tlgKeywordOn
0x180005811  test    al, al
0x180005813  jz      loc_1800058D5
0x180005819  mov     eax, [rbx+2Ch]
0x18000581c  lea     rdx, word_18002EBA6
0x180005823  mov     [rbp+57h+arg_8], eax
0x180005826  mov     eax, [rdi]
0x180005828  mov     [rbp+57h+arg_10], eax
0x18000582b  lea     rax, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180005832  mov     [rbp+57h+var_50], rax
0x180005836  lea     rax, aDiagnosticserv_3; "DiagnosticServer::ReportSvcStatus"
0x18000583d  mov     [rbp+57h+var_48], rax
0x180005841  lea     rax, aReportServiceS; "Report service status"
0x180005848  mov     [rbp+57h+var_40], rax
0x18000584c  lea     rax, [rbx+78h]
0x180005850  mov     [rbp+57h+var_38], rax
0x180005854  lea     rax, [rbp+57h+arg_8]
0x180005858  mov     [rsp+0E0h+var_70], rax
0x18000585d  lea     rax, [rbp+57h+arg_10]
0x180005861  mov     [rsp+0E0h+var_78], rax
0x180005866  lea     rax, [rbp+57h+arg_18]
0x18000586a  mov     [rsp+0E0h+var_80], rax
0x18000586f  lea     rax, [rbp+57h+arg_0]
0x180005873  mov     [rsp+0E0h+var_88], rax
0x180005878  lea     rax, [rbp+57h+var_60]
0x18000587c  mov     [rsp+0E0h+var_90], rax
0x180005881  lea     rax, [rbp+57h+var_5C]
0x180005885  mov     [rsp+0E0h+var_98], rax
0x18000588a  lea     rax, [rbp+57h+var_50]
0x18000588e  mov     [rsp+0E0h+var_A0], rax
0x180005893  lea     rax, [rbp+57h+var_48]
0x180005897  mov     [rsp+0E0h+var_A8], rax
0x18000589c  lea     rax, [rbp+57h+var_40]
0x1800058a0  mov     [rsp+0E0h+var_B0], rax
0x1800058a5  lea     rax, [rbp+57h+var_58]
0x1800058a9  mov     [rsp+0E0h+var_B8], rax
0x1800058ae  lea     rax, [rbp+57h+var_38]
0x1800058b2  mov     [rsp+0E0h+var_C0], rax
0x1800058b7  mov     [rbp+57h+arg_18], r14d
0x1800058bb  mov     [rbp+57h+arg_0], r15d
0x1800058bf  mov     [rbp+57h+var_60], esi
0x1800058c2  mov     [rbp+57h+var_5C], 91h
0x1800058c9  mov     [rbp+57h+var_58], 0
0x1800058d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800058d5  add     rsp, 0B8h
0x1800058dc  pop     r15
0x1800058de  pop     r14
0x1800058e0  pop     rdi
0x1800058e1  pop     rsi
0x1800058e2  pop     rbx
0x1800058e3  pop     rbp
0x1800058e4  retn
```
