# CreateEnrollmentIfNeeded(void)

- ea: `0x180244704`
- end: `0x1802448fa`
- name: `?CreateEnrollmentIfNeeded@@YA?AW4_MI_Result@@XZ`
- size: `502`
- prototype: `enum _MI_Result(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180240f0c`

## callees

- `0x18000104c`
- `0x180001310`
- `0x1800013b8`
- `0x180001444`
- `0x180009f1c`
- `0x180244704`
- `0x180244d34`
- `0x180244ed8`
- `0x18024cd20`

## import_xrefs

- `dmEnrollEngine!BeginEnrollmentScope` at `0x1802447d6`
- `dmEnrollEngine!BeginEnrollmentScope` at `0x1802447d6`
- `dmEnrollEngine!__imp_SetProviderID` at `0x180244800`
- `dmEnrollEngine!__imp_SetProviderID` at `0x180244800`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18024476d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18024476d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CreateEnrollmentIfNeeded(void)
{
  int WmiBridgeEnrollmentId; // ebx
  const OLECHAR *v1; // rcx
  HRESULT v2; // eax
  int v3; // r9d
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  enum _MI_Result v10; // ebx
  __int64 v11; // rdx
  _QWORD v13[2]; // [rsp+30h] [rbp-9h] BYREF
  CLSID v14; // [rsp+40h] [rbp+7h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp+17h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+60h] [rbp+27h] BYREF
  __int64 v17; // [rsp+70h] [rbp+37h]
  unsigned __int64 v18; // [rsp+78h] [rbp+3Fh]

  v18 = 7;
  v17 = 0;
  LOWORD(lpsz[0]) = 0;
  pclsid = 0;
  WmiBridgeEnrollmentId = GetWmiBridgeEnrollmentId(lpsz);
  if ( WmiBridgeEnrollmentId >= 0 )
  {
    if ( v17 )
    {
      v1 = (const OLECHAR *)lpsz;
      if ( v18 >= 8 )
        v1 = lpsz[0];
      v2 = CLSIDFromString(v1, &pclsid);
    }
    else
    {
      if ( (unsigned int)dword_180380B68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
      {
        v13[0] = "Begin WMIBridge enrollment";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_180380B68,
          (unsigned int)&dword_1803707D4,
          0,
          v3,
          (__int64)v13);
      }
      WmiBridgeEnrollmentId = BeginEnrollmentScope(12, &pclsid);
      if ( WmiBridgeEnrollmentId < 0 )
        goto LABEL_15;
      v14 = pclsid;
      v2 = SetProviderID(&v14, L"WMI_Bridge_SCCM_Server");
    }
    WmiBridgeEnrollmentId = v2;
    if ( v2 >= 0 )
    {
      if ( (unsigned int)dword_180380B68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
      {
        v13[0] = &pclsid;
        *(_QWORD *)&v14.Data1 = "Current enrollment id";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
          v4,
          (unsigned int)&dword_1803708C4,
          v5,
          v6,
          (__int64)&v14,
          (__int64)v13);
      }
      goto LABEL_18;
    }
  }
LABEL_15:
  if ( (unsigned int)dword_180380B68 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    LODWORD(v13[0]) = WmiBridgeEnrollmentId;
    *(_QWORD *)&v14.Data1 = "Init";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&dword_18037080C,
      v8,
      v9,
      (__int64)&v14,
      (__int64)v13);
  }
LABEL_18:
  v10 = HResultToMIResult(WmiBridgeEnrollmentId);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(lpsz, v11, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180244704  mov     [rsp-8+arg_0], rbx
0x180244709  push    rbp
0x18024470a  lea     rbp, [rsp-57h]
0x18024470f  sub     rsp, 90h
0x180244716  mov     rax, cs:__security_cookie
0x18024471d  xor     rax, rsp
0x180244720  mov     [rbp+57h+var_10], rax
0x180244724  mov     [rbp+57h+var_18], 7
0x18024472c  mov     [rbp+57h+var_20], 0
0x180244734  xor     eax, eax
0x180244736  mov     word ptr [rbp+57h+lpsz], ax
0x18024473a  xorps   xmm0, xmm0
0x18024473d  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180244741  lea     rcx, [rbp+57h+lpsz]
0x180244745  call    ?GetWmiBridgeEnrollmentId@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWmiBridgeEnrollmentId(std::wstring &)
0x18024474a  mov     ebx, eax
0x18024474c  test    eax, eax
0x18024474e  js      loc_180244872
0x180244754  cmp     [rbp+57h+var_20], 0
0x180244759  jz      short loc_18024477E
0x18024475b  lea     rcx, [rbp+57h+lpsz]
0x18024475f  cmp     [rbp+57h+var_18], 8
0x180244764  cmovnb  rcx, [rbp+57h+lpsz]; lpsz
0x180244769  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18024476d  call    cs:__imp_CLSIDFromString
0x180244774  nop     dword ptr [rax+rax+00h]
0x180244779  jmp     loc_18024480C
0x18024477e  mov     eax, cs:dword_180380B68
0x180244784  cmp     eax, 4
0x180244787  jbe     short loc_1802447CD
0x180244789  mov     rdx, 200000000000h
0x180244793  lea     rcx, dword_180380B68
0x18024479a  call    _tlgKeywordOn
0x18024479f  test    al, al
0x1802447a1  jz      short loc_1802447CD
0x1802447a3  lea     rax, aBeginWmibridge; "Begin WMIBridge enrollment"
0x1802447aa  mov     [rbp+57h+var_60], rax
0x1802447ae  lea     rax, [rbp+57h+var_60]
0x1802447b2  mov     [rsp+90h+var_70], rax
0x1802447b7  xor     r8d, r8d
0x1802447ba  lea     rdx, dword_1803707D4
0x1802447c1  lea     rcx, dword_180380B68
0x1802447c8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1802447cd  lea     rdx, [rbp+57h+pclsid]
0x1802447d1  mov     ecx, 0Ch
0x1802447d6  call    cs:__imp_BeginEnrollmentScope
0x1802447dd  nop     dword ptr [rax+rax+00h]
0x1802447e2  mov     ebx, eax
0x1802447e4  test    eax, eax
0x1802447e6  js      loc_180244872
0x1802447ec  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x1802447f0  movdqa  [rbp+57h+var_50], xmm0
0x1802447f5  lea     rdx, aWmiBridgeSccmS; "WMI_Bridge_SCCM_Server"
0x1802447fc  lea     rcx, [rbp+57h+var_50]
0x180244800  call    cs:__imp_SetProviderID
0x180244807  nop     dword ptr [rax+rax+00h]
0x18024480c  mov     ebx, eax
0x18024480e  test    eax, eax
0x180244810  js      short loc_180244872
0x180244812  mov     eax, cs:dword_180380B68
0x180244818  cmp     eax, 4
0x18024481b  jbe     loc_1802448C3
0x180244821  mov     rdx, 200000000000h
0x18024482b  lea     rcx, dword_180380B68
0x180244832  call    _tlgKeywordOn
0x180244837  test    al, al
0x180244839  jz      loc_1802448C3
0x18024483f  lea     rax, [rbp+57h+pclsid]
0x180244843  mov     [rbp+57h+var_60], rax
0x180244847  lea     rax, aCurrentEnrollm; "Current enrollment id"
0x18024484e  mov     qword ptr [rbp+57h+var_50], rax
0x180244852  lea     rax, [rbp+57h+var_60]
0x180244856  mov     [rsp+90h+var_68], rax
0x18024485b  lea     rax, [rbp+57h+var_50]
0x18024485f  mov     [rsp+90h+var_70], rax
0x180244864  lea     rdx, dword_1803708C4
0x18024486b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180244870  jmp     short loc_1802448C3
0x180244872  mov     eax, cs:dword_180380B68
0x180244878  cmp     eax, 2
0x18024487b  jbe     short loc_1802448C3
0x18024487d  mov     rdx, 200000000000h
0x180244887  lea     rcx, dword_180380B68
0x18024488e  call    _tlgKeywordOn
0x180244893  test    al, al
0x180244895  jz      short loc_1802448C3
0x180244897  mov     dword ptr [rbp+57h+var_60], ebx
0x18024489a  lea     rax, aInit; "Init"
0x1802448a1  mov     qword ptr [rbp+57h+var_50], rax
0x1802448a5  lea     rax, [rbp+57h+var_60]
0x1802448a9  mov     [rsp+90h+var_68], rax
0x1802448ae  lea     rax, [rbp+57h+var_50]
0x1802448b2  mov     [rsp+90h+var_70], rax
0x1802448b7  lea     rdx, dword_18037080C
0x1802448be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1802448c3  mov     ecx, ebx; int
0x1802448c5  call    ?HResultToMIResult@@YA?AW4_MI_Result@@J@Z; HResultToMIResult(long)
0x1802448ca  mov     ebx, eax
0x1802448cc  xor     r8d, r8d
0x1802448cf  mov     dl, 1
0x1802448d1  lea     rcx, [rbp+57h+lpsz]
0x1802448d5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1802448da  mov     eax, ebx
0x1802448dc  mov     rcx, [rbp+57h+var_10]
0x1802448e0  xor     rcx, rsp; StackCookie
0x1802448e3  call    __security_check_cookie
0x1802448e8  mov     rbx, [rsp+90h+arg_0]
0x1802448f0  add     rsp, 90h
0x1802448f7  pop     rbp
0x1802448f8  retn
```
