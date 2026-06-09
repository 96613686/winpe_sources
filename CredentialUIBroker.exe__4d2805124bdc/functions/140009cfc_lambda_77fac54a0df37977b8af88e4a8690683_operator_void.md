# _lambda_77fac54a0df37977b8af88e4a8690683_::operator()(void)

- ea: `0x140009cfc`
- end: `0x140009e47`
- name: `??R_lambda_77fac54a0df37977b8af88e4a8690683_@@QEBAJXZ`
- size: `331`
- prototype: `__int64 __fastcall(_DWORD **, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ee08`

## callees

- `0x140004e50`
- `0x140006028`
- `0x140008f10`
- `0x140009064`
- `0x1400090a8`
- `0x140009cfc`
- `0x1400136fc`
- `0x14001d1ec`
- `0x14001d20c`

## import_xrefs

- `KERNEL32!GetProcessId` at `0x140009d31`
- `KERNEL32!GetProcessId` at `0x140009d31`
- `KERNEL32!CloseHandle` at `0x140009d50`
- `KERNEL32!CloseHandle` at `0x140009d50`

## string_xrefs

- `0x140009d5e`: `pcshell\shell\auth\creduibroker\exe\CredUIBrokerTelemetry.h`
- `0x140009db4`: `pcshell\shell\auth\creduibroker\exe\CredUIBrokerTelemetry.h`
- `0x140009de9`: `pcshell\shell\auth\creduibroker\exe\CredUIBrokerTelemetry.h`

## pseudocode

```c
__int64 __fastcall _lambda_77fac54a0df37977b8af88e4a8690683_::operator()(_DWORD **a1, __int64 a2)
{
  int CallingProcessHandle; // ebx
  void **v4; // r8
  char *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+28h] [rbp-28h] BYREF
  __int64 *v11; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v12[2]; // [rsp+38h] [rbp-18h] BYREF
  char v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD ProcessId; // [rsp+78h] [rbp+28h] BYREF
  HANDLE Process; // [rsp+80h] [rbp+30h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  ProcessId = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(0x1000u, a2, &Process);
  if ( CallingProcessHandle >= 0 )
    ProcessId = GetProcessId(Process);
  v5 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( CallingProcessHandle >= 0 )
  {
    v9 = 0;
    v11 = &v9;
    *(_QWORD *)v12 = 0;
    v13 = 1;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x1000, (unsigned int)v12, v4);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v11);
    if ( CallingProcessHandle >= 0 )
    {
      v17 = 0;
      v7 = wil::QueryFullProcessImageNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
             v9,
             v6,
             &v17);
      CallingProcessHandle = v7;
      if ( v7 >= 0 )
      {
        LODWORD(Process) = **a1;
        v10 = v17;
        CredUIBrokerTelemetry::BadOwnerWindowSpecified<unsigned short *,unsigned long &,unsigned int>(
          &v10,
          (int *)&ProcessId,
          (int *)&Process);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        CallingProcessHandle = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\CredUIBrokerTelemetry.h",
          (const char *)(unsigned int)v7,
          v9);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\CredUIBrokerTelemetry.h",
        (const char *)(unsigned int)CallingProcessHandle,
        v9);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\CredUIBrokerTelemetry.h",
      (const char *)(unsigned int)CallingProcessHandle,
      v9);
  }
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x140009cfc  push    rbp
0x140009cfe  push    rbx
0x140009cff  push    rdi
0x140009d00  mov     rbp, rsp
0x140009d03  sub     rsp, 50h
0x140009d07  mov     rdi, rcx
0x140009d0a  mov     [rbp+arg_8], 0
0x140009d11  mov     ecx, 1000h
0x140009d16  mov     [rbp+Process], 0
0x140009d1e  lea     r8, [rbp+Process]
0x140009d22  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x140009d27  mov     ebx, eax
0x140009d29  test    eax, eax
0x140009d2b  js      short loc_140009D3A
0x140009d2d  mov     rcx, [rbp+Process]; Process
0x140009d31  call    cs:__imp_GetProcessId
0x140009d37  mov     [rbp+arg_8], eax
0x140009d3a  mov     rcx, [rbp+Process]; hObject
0x140009d3e  mov     [rbp+Process], 0
0x140009d46  lea     rdx, [rcx-1]
0x140009d4a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140009d4e  ja      short loc_140009D56
0x140009d50  call    cs:__imp_CloseHandle
0x140009d56  test    ebx, ebx
0x140009d58  jns     short loc_140009D77
0x140009d5a  mov     rcx, [rbp+18h]; this
0x140009d5e  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140009d65  mov     r9d, ebx; char *
0x140009d68  mov     edx, 4Ch ; 'L'; void *
0x140009d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009d72  jmp     loc_140009E3D
0x140009d77  lea     rax, [rbp+var_30]
0x140009d7b  mov     [rbp+var_30], 0
0x140009d83  lea     rdx, [rbp+var_18]; unsigned int
0x140009d87  mov     [rbp+var_20], rax
0x140009d8b  mov     ecx, 1000h; this
0x140009d90  mov     qword ptr [rbp+var_18], 0
0x140009d98  mov     [rbp+var_10], 1
0x140009d9c  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x140009da1  lea     rcx, [rbp+var_20]
0x140009da5  mov     ebx, eax
0x140009da7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x140009dac  test    ebx, ebx
0x140009dae  jns     short loc_140009DCA
0x140009db0  mov     rcx, [rbp+18h]; this
0x140009db4  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140009dbb  mov     r9d, ebx; char *
0x140009dbe  mov     edx, 4Fh ; 'O'; void *
0x140009dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009dc8  jmp     short loc_140009E34
0x140009dca  mov     rcx, [rbp+var_30]
0x140009dce  lea     r8, [rbp+arg_18]
0x140009dd2  mov     [rbp+arg_18], 0
0x140009dda  call    ??$QueryFullProcessImageNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::QueryFullProcessImageNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140009ddf  mov     ebx, eax
0x140009de1  test    eax, eax
0x140009de3  jns     short loc_140009E08
0x140009de5  mov     rcx, [rbp+18h]; this
0x140009de9  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x140009df0  mov     r9d, eax; char *
0x140009df3  mov     edx, 52h ; 'R'; void *
0x140009df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009dfd  lea     rcx, [rbp+arg_18]
0x140009e01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140009e06  jmp     short loc_140009E34
0x140009e08  mov     rax, [rdi]
0x140009e0b  lea     r8, [rbp+Process]
0x140009e0f  lea     rdx, [rbp+arg_8]
0x140009e13  mov     ecx, [rax]
0x140009e15  mov     rax, [rbp+arg_18]
0x140009e19  mov     dword ptr [rbp+Process], ecx
0x140009e1c  lea     rcx, [rbp+var_28]
0x140009e20  mov     [rbp+var_28], rax
0x140009e24  call    ??$BadOwnerWindowSpecified@PEAGAEAKI@CredUIBrokerTelemetry@@SAX$$QEAPEAGAEAK$$QEAI@Z; CredUIBrokerTelemetry::BadOwnerWindowSpecified<ushort *,ulong &,uint>(ushort * &&,ulong &,uint &&)
0x140009e29  lea     rcx, [rbp+arg_18]
0x140009e2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140009e32  xor     ebx, ebx
0x140009e34  lea     rcx, [rbp+var_30]
0x140009e38  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140009e3d  mov     eax, ebx
0x140009e3f  add     rsp, 50h
0x140009e43  pop     rdi
0x140009e44  pop     rbx
0x140009e45  pop     rbp
0x140009e46  retn
```
