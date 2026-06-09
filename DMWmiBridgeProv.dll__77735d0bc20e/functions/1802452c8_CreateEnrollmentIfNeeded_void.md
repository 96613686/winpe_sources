# CreateEnrollmentIfNeeded(void)

- ea: `0x1802452c8`
- end: `0x1802454ab`
- name: `?CreateEnrollmentIfNeeded@@YA?AW4_MI_Result@@XZ`
- size: `483`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180241bdc`

## callees

- `0x18000104c`
- `0x180001308`
- `0x1800013b0`
- `0x18000143c`
- `0x180009af8`
- `0x1802452c8`
- `0x1802458b8`
- `0x180245a44`
- `0x18024d160`

## import_xrefs

- `dmEnrollEngine!BeginEnrollmentScope` at `0x180245394`
- `dmEnrollEngine!BeginEnrollmentScope` at `0x180245394`
- `dmEnrollEngine!__imp_SetProviderID` at `0x1802453b8`
- `dmEnrollEngine!__imp_SetProviderID` at `0x1802453b8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180245331`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180245331`

## pseudocode

```c
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
0x1802452c8  mov     [rsp-8+arg_0], rbx
0x1802452cd  push    rbp
0x1802452ce  lea     rbp, [rsp-57h]
0x1802452d3  sub     rsp, 90h
0x1802452da  mov     rax, cs:__security_cookie
0x1802452e1  xor     rax, rsp
0x1802452e4  mov     [rbp+57h+var_10], rax
0x1802452e8  mov     [rbp+57h+var_18], 7
0x1802452f0  mov     [rbp+57h+var_20], 0
0x1802452f8  xor     eax, eax
0x1802452fa  mov     word ptr [rbp+57h+lpsz], ax
0x1802452fe  xorps   xmm0, xmm0
0x180245301  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180245305  lea     rcx, [rbp+57h+lpsz]
0x180245309  call    ?GetWmiBridgeEnrollmentId@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWmiBridgeEnrollmentId(std::wstring &)
0x18024530e  mov     ebx, eax
0x180245310  test    eax, eax
0x180245312  js      loc_180245424
0x180245318  cmp     [rbp+57h+var_20], 0
0x18024531d  jz      short loc_18024533C
0x18024531f  lea     rcx, [rbp+57h+lpsz]
0x180245323  cmp     [rbp+57h+var_18], 8
0x180245328  cmovnb  rcx, [rbp+57h+lpsz]; lpsz
0x18024532d  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180245331  call    cs:__imp_CLSIDFromString
0x180245337  jmp     loc_1802453BE
0x18024533c  mov     eax, cs:dword_180380B68
0x180245342  cmp     eax, 4
0x180245345  jbe     short loc_18024538B
0x180245347  mov     rdx, 200000000000h
0x180245351  lea     rcx, dword_180380B68
0x180245358  call    _tlgKeywordOn
0x18024535d  test    al, al
0x18024535f  jz      short loc_18024538B
0x180245361  lea     rax, aBeginWmibridge; "Begin WMIBridge enrollment"
0x180245368  mov     [rbp+57h+var_60], rax
0x18024536c  lea     rax, [rbp+57h+var_60]
0x180245370  mov     [rsp+90h+var_70], rax
0x180245375  xor     r8d, r8d
0x180245378  lea     rdx, dword_1803707D4
0x18024537f  lea     rcx, dword_180380B68
0x180245386  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18024538b  lea     rdx, [rbp+57h+pclsid]
0x18024538f  mov     ecx, 0Ch
0x180245394  call    cs:__imp_BeginEnrollmentScope
0x18024539a  mov     ebx, eax
0x18024539c  test    eax, eax
0x18024539e  js      loc_180245424
0x1802453a4  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x1802453a8  movdqa  [rbp+57h+var_50], xmm0
0x1802453ad  lea     rdx, aWmiBridgeSccmS; "WMI_Bridge_SCCM_Server"
0x1802453b4  lea     rcx, [rbp+57h+var_50]
0x1802453b8  call    cs:__imp_SetProviderID
0x1802453be  mov     ebx, eax
0x1802453c0  test    eax, eax
0x1802453c2  js      short loc_180245424
0x1802453c4  mov     eax, cs:dword_180380B68
0x1802453ca  cmp     eax, 4
0x1802453cd  jbe     loc_180245475
0x1802453d3  mov     rdx, 200000000000h
0x1802453dd  lea     rcx, dword_180380B68
0x1802453e4  call    _tlgKeywordOn
0x1802453e9  test    al, al
0x1802453eb  jz      loc_180245475
0x1802453f1  lea     rax, [rbp+57h+pclsid]
0x1802453f5  mov     [rbp+57h+var_60], rax
0x1802453f9  lea     rax, aCurrentEnrollm; "Current enrollment id"
0x180245400  mov     qword ptr [rbp+57h+var_50], rax
0x180245404  lea     rax, [rbp+57h+var_60]
0x180245408  mov     [rsp+90h+var_68], rax
0x18024540d  lea     rax, [rbp+57h+var_50]
0x180245411  mov     [rsp+90h+var_70], rax
0x180245416  lea     rdx, dword_1803708C4
0x18024541d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180245422  jmp     short loc_180245475
0x180245424  mov     eax, cs:dword_180380B68
0x18024542a  cmp     eax, 2
0x18024542d  jbe     short loc_180245475
0x18024542f  mov     rdx, 200000000000h
0x180245439  lea     rcx, dword_180380B68
0x180245440  call    _tlgKeywordOn
0x180245445  test    al, al
0x180245447  jz      short loc_180245475
0x180245449  mov     dword ptr [rbp+57h+var_60], ebx
0x18024544c  lea     rax, aInit; "Init"
0x180245453  mov     qword ptr [rbp+57h+var_50], rax
0x180245457  lea     rax, [rbp+57h+var_60]
0x18024545b  mov     [rsp+90h+var_68], rax
0x180245460  lea     rax, [rbp+57h+var_50]
0x180245464  mov     [rsp+90h+var_70], rax
0x180245469  lea     rdx, dword_18037080C
0x180245470  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180245475  mov     ecx, ebx; int
0x180245477  call    ?HResultToMIResult@@YA?AW4_MI_Result@@J@Z; HResultToMIResult(long)
0x18024547c  mov     ebx, eax
0x18024547e  xor     r8d, r8d
0x180245481  mov     dl, 1
0x180245483  lea     rcx, [rbp+57h+lpsz]
0x180245487  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18024548c  mov     eax, ebx
0x18024548e  mov     rcx, [rbp+57h+var_10]
0x180245492  xor     rcx, rsp; StackCookie
0x180245495  call    __security_check_cookie
0x18024549a  mov     rbx, [rsp+90h+arg_0]
0x1802454a2  add     rsp, 90h
0x1802454a9  pop     rbp
0x1802454aa  retn
```
