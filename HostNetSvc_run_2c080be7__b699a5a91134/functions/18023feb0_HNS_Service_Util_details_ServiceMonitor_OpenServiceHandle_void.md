# HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(void)

- ea: `0x18023feb0`
- end: `0x18023ff9f`
- name: `?OpenServiceHandle@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ`
- size: `239`
- prototype: `void __fastcall(HNS::Service::Util::details::ServiceMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18023efe4`
- `0x1802404c8`

## callees

- `0x1800860d0`
- `0x1800883e8`
- `0x18023feb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18023ff2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18023ff2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023ff1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023ff1a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18023ff09`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18023ff09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18023fed6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18023fed6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023ff25`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023ff6e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023ff25`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023ff6e`

## string_xrefs

- `0x18023ff86`: `Failed to connect to service control manager`
- `0x18023ff4a`: `Failed to open service: %ws.`
- `0x18023ff59`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`
- `0x18023ff8d`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(
        HNS::Service::Util::details::ServiceMonitor *this)
{
  SC_HANDLE *v2; // r14
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rdx
  SC_HANDLE v7; // r15
  SC_HANDLE v8; // rbp
  DWORD LastError; // edi
  const char *v10; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (SC_HANDLE *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
  {
    v3 = OpenSCManagerW(0, 0, 1u);
    v4 = v3;
    if ( !v3 )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
        "Failed to connect to service control manager",
        v10);
    v5 = (const WCHAR *)((char *)this + 32);
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v6 = v5;
    else
      v6 = *(const WCHAR **)v5;
    v7 = OpenServiceW(v3, v6, 0x15u);
    v8 = *v2;
    if ( *v2 )
    {
      LastError = GetLastError();
      CloseServiceHandle(v8);
      SetLastError(LastError);
    }
    *v2 = v7;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const WCHAR **)v5;
    wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
      (int)retaddr,
      245,
      (int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
      (int)v2,
      "Failed to open service: %ws.",
      (char)v5);
    CloseServiceHandle(v4);
  }
}

```

## disassembly

```asm
0x18023feb0  push    rbx
0x18023feb2  push    rbp
0x18023feb3  push    rsi
0x18023feb4  push    rdi
0x18023feb5  push    r14
0x18023feb7  push    r15
0x18023feb9  sub     rsp, 38h
0x18023febd  mov     rsi, rcx
0x18023fec0  lea     r14, [rcx+8]
0x18023fec4  cmp     qword ptr [r14], 0
0x18023fec8  jnz     loc_18023FF74
0x18023fece  xor     edx, edx; lpDatabaseName
0x18023fed0  xor     ecx, ecx; lpMachineName
0x18023fed2  lea     r8d, [rdx+1]; dwDesiredAccess
0x18023fed6  call    cs:__imp_OpenSCManagerW
0x18023fedc  mov     rbx, rax
0x18023fedf  mov     [rsp+68h+arg_0], rax
0x18023fee4  test    rax, rax
0x18023fee7  jz      loc_18023FF81
0x18023feed  add     rsi, 20h ; ' '
0x18023fef1  cmp     qword ptr [rsi+18h], 7
0x18023fef6  jbe     short loc_18023FEFD
0x18023fef8  mov     rdx, [rsi]
0x18023fefb  jmp     short loc_18023FF00
0x18023fefd  mov     rdx, rsi; lpServiceName
0x18023ff00  mov     r8d, 15h; dwDesiredAccess
0x18023ff06  mov     rcx, rbx; hSCManager
0x18023ff09  call    cs:__imp_OpenServiceW
0x18023ff0f  mov     r15, rax
0x18023ff12  mov     rbp, [r14]
0x18023ff15  test    rbp, rbp
0x18023ff18  jz      short loc_18023FF33
0x18023ff1a  call    cs:__imp_GetLastError
0x18023ff20  mov     edi, eax
0x18023ff22  mov     rcx, rbp; hSCObject
0x18023ff25  call    cs:__imp_CloseServiceHandle
0x18023ff2b  mov     ecx, edi; dwErrCode
0x18023ff2d  call    cs:__imp_SetLastError
0x18023ff33  mov     [r14], r15
0x18023ff36  cmp     qword ptr [rsi+18h], 7
0x18023ff3b  jbe     short loc_18023FF40
0x18023ff3d  mov     rsi, [rsi]
0x18023ff40  mov     rcx, [rsp+68h]; int
0x18023ff45  mov     qword ptr [rsp+68h+var_40], rsi; char
0x18023ff4a  lea     rax, aFailedToOpenSe; "Failed to open service: %ws."
0x18023ff51  mov     [rsp+68h+var_48], rax; void *
0x18023ff56  mov     r9, r14; int
0x18023ff59  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18023ff60  mov     edx, 0F5h; int
0x18023ff65  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x18023ff6a  nop
0x18023ff6b  mov     rcx, rbx; hSCObject
0x18023ff6e  call    cs:__imp_CloseServiceHandle
0x18023ff74  add     rsp, 38h
0x18023ff78  pop     r15
0x18023ff7a  pop     r14
0x18023ff7c  pop     rdi
0x18023ff7d  pop     rsi
0x18023ff7e  pop     rbp
0x18023ff7f  pop     rbx
0x18023ff80  retn
0x18023ff81  mov     rcx, [rsp+68h]; this
0x18023ff86  lea     r9, aFailedToConnec; "Failed to connect to service control ma"...
0x18023ff8d  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18023ff94  mov     edx, 0ECh; void *
0x18023ff99  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
