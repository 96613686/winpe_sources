# WpW32TimeSetServiceStartType(ulong)

- ea: `0x180010068`
- end: `0x1800101b0`
- name: `?WpW32TimeSetServiceStartType@@YAJK@Z`
- size: `328`
- prototype: `__int64 __fastcall(DWORD dwStartType)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800061ac`
- `0x180010800`

## callees

- `0x180001218`
- `0x1800012f0`
- `0x180005820`
- `0x180009174`
- `0x180010068`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800100bf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800100bf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800100ff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800100ff`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001017e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001017e`

## string_xrefs

- `0x1800100d7`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x180010119`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 __fastcall WpW32TimeSetServiceStartType(DWORD dwStartType)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  SC_HANDLE v10; // [rsp+78h] [rbp+10h] BYREF
  SC_HANDLE v11; // [rsp+80h] [rbp+18h] BYREF

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
  {
    LODWORD(v10) = dwStartType;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)&word_1800178BE,
      0,
      0);
  }
  v2 = OpenSCManagerW(0, 0, 1u);
  v11 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"W32Time", 2u);
    v10 = v5;
    if ( v5 )
    {
      if ( ChangeServiceConfigW(v5, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
        LastError = 0;
        goto LABEL_12;
      }
      v7 = 346;
    }
    else
    {
      v7 = 333;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                  v6);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x14A,
                  (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                  v3);
  }
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x180010068  push    rbx
0x18001006a  sub     rsp, 60h
0x18001006e  mov     eax, cs:dword_18001C010
0x180010074  mov     ebx, ecx
0x180010076  cmp     eax, 4
0x180010079  jbe     short loc_1800100B7
0x18001007b  mov     edx, 200h
0x180010080  lea     rcx, dword_18001C010
0x180010087  call    _tlgKeywordOn
0x18001008c  test    al, al
0x18001008e  jz      short loc_1800100B7
0x180010090  lea     rax, [rsp+68h+arg_8]
0x180010095  mov     dword ptr [rsp+68h+arg_8], ebx
0x180010099  xor     r9d, r9d
0x18001009c  mov     [rsp+68h+lpBinaryPathName], rax
0x1800100a1  xor     r8d, r8d
0x1800100a4  lea     rdx, word_1800178BE
0x1800100ab  lea     rcx, dword_18001C010
0x1800100b2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800100b7  xor     edx, edx; lpDatabaseName
0x1800100b9  xor     ecx, ecx; lpMachineName
0x1800100bb  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800100bf  call    cs:__imp_OpenSCManagerW
0x1800100c5  mov     [rsp+68h+arg_10], rax
0x1800100cd  test    rax, rax
0x1800100d0  jnz     short loc_1800100EF
0x1800100d2  mov     rcx, [rsp+68h]; this
0x1800100d7  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800100de  mov     edx, 14Ah; void *
0x1800100e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800100e8  mov     ebx, eax
0x1800100ea  jmp     loc_18001019B
0x1800100ef  mov     r8d, 2; dwDesiredAccess
0x1800100f5  lea     rdx, aW32time; "W32Time"
0x1800100fc  mov     rcx, rax; hSCManager
0x1800100ff  call    cs:__imp_OpenServiceW
0x180010105  mov     [rsp+68h+arg_8], rax
0x18001010a  test    rax, rax
0x18001010d  jnz     short loc_180010133
0x18001010f  mov     edx, 14Dh; void *
0x180010114  mov     rcx, [rsp+68h]; this
0x180010119  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010120  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010125  lea     rcx, [rsp+68h+arg_8]
0x18001012a  mov     ebx, eax
0x18001012c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010131  jmp     short loc_18001019B
0x180010133  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18001013c  or      edx, 0FFFFFFFFh; dwServiceType
0x18001013f  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180010148  mov     r9d, edx; dwErrorControl
0x18001014b  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180010154  mov     r8d, ebx; dwStartType
0x180010157  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x180010160  mov     rcx, rax; hService
0x180010163  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18001016c  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180010175  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18001017e  call    cs:__imp_ChangeServiceConfigW
0x180010184  test    eax, eax
0x180010186  jnz     short loc_18001018F
0x180010188  mov     edx, 15Ah
0x18001018d  jmp     short loc_180010114
0x18001018f  lea     rcx, [rsp+68h+arg_8]
0x180010194  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010199  xor     ebx, ebx
0x18001019b  lea     rcx, [rsp+68h+arg_10]
0x1800101a3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800101a8  mov     eax, ebx
0x1800101aa  add     rsp, 60h
0x1800101ae  pop     rbx
0x1800101af  retn
```
