# CCredUIBrokerForAppContainers::_VerifyWindowIsInCallingProcessOrParentAppContainer(HWND__ *)

- ea: `0x140018cf8`
- end: `0x140018e93`
- name: `?_VerifyWindowIsInCallingProcessOrParentAppContainer@CCredUIBrokerForAppContainers@@AEAAJPEAUHWND__@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(CCredUIBrokerForAppContainers *this, CallerIdentity *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140010da0`

## callees

- `0x140008f10`
- `0x140009064`
- `0x1400091b4`
- `0x1400136fc`
- `0x140018cf8`
- `0x14001d1ec`
- `0x14001d730`
- `0x14001dbe8`
- `0x14001dd70`

## import_xrefs

- `ntdll!RtlIsParentOfChildAppContainer` at `0x140018e1c`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x140018e2e`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x140018e1c`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x140018e2e`

## string_xrefs

- `0x140018d27`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x140018d7d`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x140018db5`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x140018df5`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x140018e3c`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerForAppContainers::_VerifyWindowIsInCallingProcessOrParentAppContainer(
        CCredUIBrokerForAppContainers *this,
        CallerIdentity *a2)
{
  int v3; // eax
  void **v4; // r8
  unsigned int CallingProcessHandle; // ebx
  void **v6; // r8
  int PackageSidFromProcessHandle; // eax
  void **v8; // r8
  int PackageSidFromWindow; // eax
  CallerIdentity **v11; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v12[2]; // [rsp+28h] [rbp-18h] BYREF
  char v13; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  CCredUIBrokerForAppContainers *v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF
  CallerIdentity *v17; // [rsp+78h] [rbp+38h] BYREF

  v15 = this;
  v3 = CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(a2, (HWND)a2);
  CallingProcessHandle = v3;
  if ( v3 == -2147024891 )
  {
    v17 = 0;
    v11 = &v17;
    *(_QWORD *)v12 = 0;
    v13 = 1;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x1000, (unsigned int)v12, v4);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v11);
    if ( (CallingProcessHandle & 0x80000000) == 0 )
    {
      v15 = 0;
      PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(v17, &v15, v6);
      CallingProcessHandle = PackageSidFromProcessHandle;
      if ( PackageSidFromProcessHandle >= 0 )
      {
        v16 = 0;
        PackageSidFromWindow = CallerIdentity::GetPackageSidFromWindow(a2, (HWND)&v16, v8);
        CallingProcessHandle = PackageSidFromWindow;
        if ( PackageSidFromWindow >= 0 )
        {
          if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v15, v16)
            || (unsigned __int8)RtlIsParentOfChildAppContainer(v16, v15) )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
            CallingProcessHandle = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23A,
              (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
              (const char *)0x80070005LL,
              (int)v11);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
            CallingProcessHandle = -2147024891;
          }
          goto LABEL_15;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
          (const char *)(unsigned int)PackageSidFromWindow,
          (int)v11);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
          (const char *)(unsigned int)PackageSidFromProcessHandle,
          (int)v11);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x233,
        (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
        (const char *)CallingProcessHandle,
        (int)v11);
    }
LABEL_15:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return CallingProcessHandle;
  }
  if ( v3 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
      (const char *)(unsigned int)v3,
      (int)v11);
  return CallingProcessHandle;
}

```

## disassembly

```asm
0x140018cf8  mov     [rsp-18h+arg_0], rcx
0x140018cfd  push    rbp
0x140018cfe  push    rbx
0x140018cff  push    rdi
0x140018d00  mov     rbp, rsp
0x140018d03  sub     rsp, 40h
0x140018d07  mov     rcx, rdx; this
0x140018d0a  mov     rdi, rdx
0x140018d0d  call    ?VerifyWindowIsInCallingProcessAppContainer@CallerIdentity@@YAJPEAUHWND__@@@Z; CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(HWND__ *)
0x140018d12  mov     ebx, eax
0x140018d14  cmp     eax, 80070005h
0x140018d19  jz      short loc_140018D40
0x140018d1b  test    eax, eax
0x140018d1d  jns     loc_140018E89
0x140018d23  mov     rcx, [rbp+18h]; this
0x140018d27  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140018d2e  mov     r9d, eax; char *
0x140018d31  mov     edx, 22Fh; void *
0x140018d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018d3b  jmp     loc_140018E89
0x140018d40  lea     rax, [rbp+arg_18]
0x140018d44  mov     [rbp+arg_18], 0
0x140018d4c  lea     rdx, [rbp+var_18]; unsigned int
0x140018d50  mov     [rbp+var_20], rax
0x140018d54  mov     ecx, 1000h; this
0x140018d59  mov     qword ptr [rbp+var_18], 0
0x140018d61  mov     [rbp+var_10], 1
0x140018d65  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x140018d6a  lea     rcx, [rbp+var_20]
0x140018d6e  mov     ebx, eax
0x140018d70  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x140018d75  test    ebx, ebx
0x140018d77  jns     short loc_140018D96
0x140018d79  mov     rcx, [rbp+18h]; this
0x140018d7d  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140018d84  mov     r9d, ebx; char *
0x140018d87  mov     edx, 233h; void *
0x140018d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018d91  jmp     loc_140018E80
0x140018d96  mov     rcx, [rbp+arg_18]; this
0x140018d9a  lea     rdx, [rbp+arg_0]; void *
0x140018d9e  mov     [rbp+arg_0], 0
0x140018da6  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x140018dab  mov     ebx, eax
0x140018dad  test    eax, eax
0x140018daf  jns     short loc_140018DD7
0x140018db1  mov     rcx, [rbp+18h]; this
0x140018db5  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140018dbc  mov     r9d, eax; char *
0x140018dbf  mov     edx, 235h; void *
0x140018dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018dc9  lea     rcx, [rbp+arg_0]
0x140018dcd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018dd2  jmp     loc_140018E80
0x140018dd7  lea     rdx, [rbp+arg_10]; HWND
0x140018ddb  mov     [rbp+arg_10], 0
0x140018de3  mov     rcx, rdi; this
0x140018de6  call    ?GetPackageSidFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAX@Z; CallerIdentity::GetPackageSidFromWindow(HWND__ *,void * *)
0x140018deb  mov     ebx, eax
0x140018ded  test    eax, eax
0x140018def  jns     short loc_140018E14
0x140018df1  mov     rcx, [rbp+18h]; this
0x140018df5  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140018dfc  mov     r9d, eax; char *
0x140018dff  mov     edx, 237h; void *
0x140018e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018e09  lea     rcx, [rbp+arg_10]
0x140018e0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018e12  jmp     short loc_140018DC9
0x140018e14  mov     rdx, [rbp+arg_10]
0x140018e18  mov     rcx, [rbp+arg_0]
0x140018e1c  call    cs:__imp_RtlIsParentOfChildAppContainer
0x140018e22  test    al, al
0x140018e24  jnz     short loc_140018E6C
0x140018e26  mov     rdx, [rbp+arg_0]
0x140018e2a  mov     rcx, [rbp+arg_10]
0x140018e2e  call    cs:__imp_RtlIsParentOfChildAppContainer
0x140018e34  test    al, al
0x140018e36  jnz     short loc_140018E6C
0x140018e38  mov     rcx, [rbp+18h]; this
0x140018e3c  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140018e43  mov     r9d, 80070005h; char *
0x140018e49  mov     edx, 23Ah; void *
0x140018e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018e53  lea     rcx, [rbp+arg_10]
0x140018e57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018e5c  lea     rcx, [rbp+arg_0]
0x140018e60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018e65  mov     ebx, 80070005h
0x140018e6a  jmp     short loc_140018E80
0x140018e6c  lea     rcx, [rbp+arg_10]
0x140018e70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018e75  lea     rcx, [rbp+arg_0]
0x140018e79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140018e7e  xor     ebx, ebx
0x140018e80  lea     rcx, [rbp+arg_18]
0x140018e84  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140018e89  mov     eax, ebx
0x140018e8b  add     rsp, 40h
0x140018e8f  pop     rdi
0x140018e90  pop     rbx
0x140018e91  pop     rbp
0x140018e92  retn
```
