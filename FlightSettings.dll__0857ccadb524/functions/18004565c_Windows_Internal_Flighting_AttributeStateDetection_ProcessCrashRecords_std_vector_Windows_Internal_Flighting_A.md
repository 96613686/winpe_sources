# Windows::Internal::Flighting::AttributeStateDetection::ProcessCrashRecords(std::vector<Windows::Internal::Flighting::AttributeStateDetection::CrashRecordEntry,std::allocator<Windows::Internal::Flighting::AttributeStateDetection::CrashRecordEntry>>)

- ea: `0x18004565c`
- end: `0x180045883`
- name: `?ProcessCrashRecords@AttributeStateDetection@Flighting@Internal@Windows@@AEAAJV?$vector@UCrashRecordEntry@AttributeStateDetection@Flighting@Internal@Windows@@V?$allocator@UCrashRecordEntry@AttributeStateDetection@Flighting@Internal@Windows@@@std@@@std@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(Windows::Internal::Flighting::AttributeStateDetection *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045994`

## callees

- `0x18000cc8c`
- `0x1800175b4`
- `0x18001cff8`
- `0x180023fa8`
- `0x1800443e8`
- `0x180044c84`
- `0x18004565c`
- `0x180046380`
- `0x180046560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045747`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045747`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800457a4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800457a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004581a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004581a`

## string_xrefs

- `0x1800456a1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x1800456ee`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180045761`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x1800457d9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::AttributeStateDetection::ProcessCrashRecords(
        Windows::Internal::Flighting::AttributeStateDetection *this,
        __int64 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const WCHAR *v6; // rdx
  HKEY v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  char v11; // r15
  int ValueW; // eax
  CTAC::Utils::Time *v13; // rcx
  bool v14; // sf
  __int64 v15; // rsi
  __int64 i; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  const WCHAR *v20; // rax
  LSTATUS v21; // eax
  unsigned __int64 v22; // r9
  LSTATUS v23; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  int pdwTypea; // [rsp+20h] [rbp-30h]
  HKEY hkey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD pvData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Data; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  hkey[0] = 0;
  v4 = wil::reg::open_unique_key_nothrow(*((HKEY *)this + 33), *((LPCWSTR *)this + 9));
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)v4,
      pdwType);
    goto LABEL_27;
  }
  v6 = (const WCHAR *)*((_QWORD *)this + 12);
  v7 = (HKEY)*((_QWORD *)this + 33);
  hKey = 0;
  v8 = wil::reg::open_unique_key_nothrow(v7, v6);
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = (unsigned int)v8;
    v10 = 451;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)v9,
      pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_27;
  }
  pvData = 0;
  v11 = 0;
  Data = 4;
  ValueW = RegGetValueW(hkey[0], 0, L"CrashCount", 0x10u, 0, &pvData, &Data);
  v14 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v14 = ValueW < 0;
  }
  if ( v14 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)ValueW,
      pdwTypea);
  v15 = a2[1];
  for ( i = *a2; i != v15; i += 40 )
  {
    if ( CTAC::Utils::Time::GetCurrentTimeInMilliseconds(v13) - *(_QWORD *)(i + 32) >= 0x7D0 )
    {
      ++pvData;
      v11 = 1;
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i, v17, v18, v19);
      v21 = RegDeleteValueW(hKey, v20);
      v22 = (unsigned int)v21;
      if ( v21 )
      {
        if ( v21 > 0 )
          v22 = (unsigned __int16)v21 | 0x80070000;
        if ( (int)v22 <= -2147024895 || (unsigned int)(v22 + 2147024892) <= 0x7FF8FFFB )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1E7,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
            (const char *)v22,
            pdwTypea);
      }
    }
  }
  Data = pvData;
  v23 = RegSetKeyValueW(hkey[0], 0, L"CrashCount", 4u, &Data, 4u);
  v5 = v23;
  if ( v23 > 0 )
    v5 = (unsigned __int16)v23 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    v9 = v5;
    v10 = 495;
    goto LABEL_5;
  }
  if ( v11 )
    Windows::Internal::Flighting::AttributeStateDetection::EvaluateDisableAfterCrash(this, hkey[0]);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v5 = 0;
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
  std::vector<Windows::Internal::Flighting::AttributeStateDetection::CrashRecordEntry>::_Tidy(a2);
  return v5;
}

```

## disassembly

```asm
0x18004565c  mov     [rsp-28h+arg_8], rbx
0x180045661  push    rbp
0x180045662  push    rsi
0x180045663  push    rdi
0x180045664  push    r14
0x180045666  push    r15
0x180045668  mov     rbp, rsp
0x18004566b  sub     rsp, 50h
0x18004566f  mov     r14, rdx
0x180045672  mov     [rbp+hkey], 0
0x18004567a  mov     rdx, [rcx+48h]; lpSubKey
0x18004567e  lea     r8, [rbp+hkey]
0x180045682  mov     rdi, rcx
0x180045685  mov     r9d, 1
0x18004568b  mov     rcx, [rcx+108h]; hKey
0x180045692  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180045697  mov     ebx, eax
0x180045699  test    eax, eax
0x18004569b  jns     short loc_1800456BA
0x18004569d  mov     rcx, [rbp+28h]; this
0x1800456a1  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800456a8  mov     r9d, eax; char *
0x1800456ab  mov     edx, 1BBh; void *
0x1800456b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800456b5  jmp     loc_18004585C
0x1800456ba  mov     rdx, [rdi+60h]; lpSubKey
0x1800456be  lea     r8, [rbp+hKey]
0x1800456c2  mov     rcx, [rdi+108h]; hKey
0x1800456c9  mov     r9d, 1
0x1800456cf  mov     [rbp+hKey], 0
0x1800456d7  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x1800456dc  mov     ebx, eax
0x1800456de  test    eax, eax
0x1800456e0  jns     short loc_180045708
0x1800456e2  mov     r9d, eax; char *
0x1800456e5  mov     edx, 1C3h; void *
0x1800456ea  mov     rcx, [rbp+28h]; this
0x1800456ee  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800456f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800456fa  lea     rcx, [rbp+hKey]
0x1800456fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180045703  jmp     loc_18004585C
0x180045708  mov     rcx, [rbp+hkey]; hkey
0x18004570c  lea     rax, [rbp+Data]
0x180045710  mov     [rsp+50h+pcbData], rax; pcbData
0x180045715  lea     r8, Value; "CrashCount"
0x18004571c  lea     rax, [rbp+arg_0]
0x180045720  mov     [rbp+arg_0], 0
0x180045727  mov     [rsp+50h+pvData], rax; pvData
0x18004572c  mov     r9d, 10h; dwFlags
0x180045732  xor     edx, edx; lpSubKey
0x180045734  mov     [rsp+50h+pdwType], 0; int
0x18004573d  xor     r15b, r15b
0x180045740  mov     [rbp+Data], 4
0x180045747  call    cs:__imp_RegGetValueW
0x18004574d  test    eax, eax
0x18004574f  jle     short loc_18004575B
0x180045751  movzx   eax, ax
0x180045754  or      eax, 80070000h
0x180045759  test    eax, eax
0x18004575b  jns     short loc_180045775
0x18004575d  mov     rcx, [rbp+28h]; this
0x180045761  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180045768  mov     r9d, eax; char *
0x18004576b  mov     edx, 1CDh; void *
0x180045770  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045775  mov     rsi, [r14+8]
0x180045779  mov     rbx, [r14]
0x18004577c  jmp     short loc_1800457EE
0x18004577e  call    ?GetCurrentTimeInMilliseconds@Time@Utils@CTAC@@YA_KXZ; CTAC::Utils::Time::GetCurrentTimeInMilliseconds(void)
0x180045783  sub     rax, [rbx+20h]
0x180045787  cmp     rax, 7D0h
0x18004578d  jb      short loc_1800457EA
0x18004578f  inc     [rbp+arg_0]
0x180045792  mov     rcx, rbx
0x180045795  mov     r15b, 1
0x180045798  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004579d  mov     rcx, [rbp+hKey]; hKey
0x1800457a1  mov     rdx, rax; lpValueName
0x1800457a4  call    cs:__imp_RegDeleteValueW
0x1800457aa  mov     r9d, eax
0x1800457ad  test    eax, eax
0x1800457af  jz      short loc_1800457EA
0x1800457b1  jle     short loc_1800457BE
0x1800457b3  movzx   r9d, ax
0x1800457b7  or      r9d, 80070000h; char *
0x1800457be  cmp     r9d, 80070001h
0x1800457c5  jle     short loc_1800457D5
0x1800457c7  lea     eax, [r9+7FF8FFFCh]
0x1800457ce  cmp     eax, 7FF8FFFBh
0x1800457d3  ja      short loc_1800457EA
0x1800457d5  mov     rcx, [rbp+28h]; this
0x1800457d9  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x1800457e0  mov     edx, 1E7h; void *
0x1800457e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800457ea  add     rbx, 28h ; '('
0x1800457ee  cmp     rbx, rsi
0x1800457f1  jnz     short loc_18004577E
0x1800457f3  mov     eax, [rbp+arg_0]
0x1800457f6  lea     r8, Value; "CrashCount"
0x1800457fd  mov     rcx, [rbp+hkey]; hKey
0x180045801  mov     r9d, 4; dwType
0x180045807  mov     [rbp+Data], eax
0x18004580a  xor     edx, edx; lpSubKey
0x18004580c  lea     rax, [rbp+Data]
0x180045810  mov     dword ptr [rsp+50h+pvData], r9d; cbData
0x180045815  mov     [rsp+50h+pdwType], rax; lpData
0x18004581a  call    cs:__imp_RegSetKeyValueW
0x180045820  mov     ebx, eax
0x180045822  test    eax, eax
0x180045824  jle     short loc_18004582F
0x180045826  movzx   ebx, ax
0x180045829  or      ebx, 80070000h
0x18004582f  test    ebx, ebx
0x180045831  jns     short loc_180045840
0x180045833  mov     r9d, ebx
0x180045836  mov     edx, 1EFh
0x18004583b  jmp     loc_1800456EA
0x180045840  test    r15b, r15b
0x180045843  jz      short loc_180045851
0x180045845  mov     rdx, [rbp+hkey]; HKEY
0x180045849  mov     rcx, rdi; this
0x18004584c  call    ?EvaluateDisableAfterCrash@AttributeStateDetection@Flighting@Internal@Windows@@QEAAJPEAUHKEY__@@@Z; Windows::Internal::Flighting::AttributeStateDetection::EvaluateDisableAfterCrash(HKEY__ *)
0x180045851  lea     rcx, [rbp+hKey]
0x180045855  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004585a  xor     ebx, ebx
0x18004585c  lea     rcx, [rbp+hkey]
0x180045860  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180045865  mov     rcx, r14
0x180045868  call    ?_Tidy@?$vector@UCrashRecordEntry@AttributeStateDetection@Flighting@Internal@Windows@@V?$allocator@UCrashRecordEntry@AttributeStateDetection@Flighting@Internal@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Internal::Flighting::AttributeStateDetection::CrashRecordEntry>::_Tidy(void)
0x18004586d  mov     eax, ebx
0x18004586f  mov     rbx, [rsp+50h+arg_8]
0x180045877  add     rsp, 50h
0x18004587b  pop     r15
0x18004587d  pop     r14
0x18004587f  pop     rdi
0x180045880  pop     rsi
0x180045881  pop     rbp
0x180045882  retn
```
