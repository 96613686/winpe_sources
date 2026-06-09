# LaunchIdleAppTask::Execute(void)

- ea: `0x18001ec40`
- end: `0x18001ee4e`
- name: `?Execute@LaunchIdleAppTask@@MEAAXXZ`
- size: `526`
- prototype: `void __fastcall(LaunchIdleAppTask *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18001094c`
- `0x180013988`
- `0x180014930`
- `0x18001d8ac`
- `0x18001e5f8`
- `0x18001eb10`
- `0x18001ec40`
- `0x18001ee54`
- `0x18001f8d4`
- `0x18001f910`
- `0x18001ff9c`
- `0x18002e5b8`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ecb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ecb6`

## string_xrefs

- `0x18001eca8`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18001edbb`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18001ed38`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001ed93`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001eddc`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LaunchIdleAppTask::Execute(LaunchIdleAppTask *this)
{
  __int64 v2; // r8
  char v3; // di
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *UserAgent; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v16; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  pvData = 0;
  pcbData[0] = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
         L"IdleTimeoutInSeconds",
         0x20000010u,
         0,
         &pvData,
         pcbData) )
  {
    pvData = 120;
  }
  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v18);
  v18[0] = &RetailDemoTelemetry::LaunchIdleApplication::`vftable';
  RetailDemoTelemetry::LaunchIdleApplication::StartActivity(
    (RetailDemoTelemetry::LaunchIdleApplication *)v18,
    *((_BYTE *)this + 144),
    pvData);
  v3 = 1;
  if ( (*((_BYTE *)this + 128) & 1) == 0 )
  {
    LaunchAppAsUserTaskBase::GetRetailDemoAppsController((__int64)this, &v16, v2);
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 32LL))(v16, *((_QWORD *)this + 11));
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v4,
        pdwType);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16, v5, v6);
  }
  v15 = 0;
  UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(&v16, 0);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(*(_QWORD *)*UserAgent + 192LL))(*UserAgent, 2, &v15);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v8,
      pdwType);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16, v9, v10);
  v11 = SHRegSetDWORD(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
          L"ActiveScreenTopology",
          v15);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v11,
      pdwType);
  LaunchAppAsUserTaskBase::Execute(this);
  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, 0);
  if ( !*((_BYTE *)this + 144) && !*((_BYTE *)this + 145) )
    v3 = 0;
  LOBYTE(v12) = v3;
  RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<11,long,bool>(0, v12);
  RetailDemoTelemetry::LaunchIdleApplication::~LaunchIdleApplication((RetailDemoTelemetry::LaunchIdleApplication *)v18);
}

```

## disassembly

```asm
0x18001ec40  mov     [rsp-8+arg_8], rbx
0x18001ec45  mov     [rsp-8+arg_10], rdi
0x18001ec4a  push    rbp
0x18001ec4b  lea     rbp, [rsp-0C0h]
0x18001ec53  sub     rsp, 1C0h
0x18001ec5a  mov     rax, cs:__security_cookie
0x18001ec61  xor     rax, rsp
0x18001ec64  mov     [rbp+0C0h+var_10], rax
0x18001ec6b  mov     rbx, rcx
0x18001ec6e  mov     [rsp+1C0h+var_180], 0
0x18001ec76  mov     [rsp+1C0h+var_170], 4
0x18001ec7e  lea     rax, [rsp+1C0h+var_170]
0x18001ec83  mov     [rsp+1C0h+pcbData], rax; pcbData
0x18001ec88  lea     rax, [rsp+1C0h+var_180]
0x18001ec8d  mov     [rsp+1C0h+pvData], rax; pvData
0x18001ec92  mov     [rsp+1C0h+pdwType], 0; int
0x18001ec9b  mov     r9d, 20000010h; dwFlags
0x18001eca1  lea     r8, ?c_retailDemoValueIdleTimeout@@3QBGB; "IdleTimeoutInSeconds"
0x18001eca8  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001ecaf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ecb6  call    cs:__imp_RegGetValueW
0x18001ecbc  test    eax, eax
0x18001ecbe  jz      short loc_18001ECC8
0x18001ecc0  mov     [rsp+1C0h+var_180], 78h ; 'x'
0x18001ecc8  lea     rdx, aLaunchidleappl; "LaunchIdleApplication"
0x18001eccf  lea     rcx, [rsp+1C0h+var_160]; struct wil::details::IFailureCallback *
0x18001ecd4  call    ??0?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ecd9  lea     rax, ??_7LaunchIdleApplication@RetailDemoTelemetry@@6B@; const RetailDemoTelemetry::LaunchIdleApplication::`vftable'
0x18001ece0  mov     [rsp+1C0h+var_160], rax
0x18001ece5  mov     r8d, [rsp+1C0h+var_180]; unsigned int
0x18001ecea  mov     dl, [rbx+90h]; bool
0x18001ecf0  lea     rcx, [rsp+1C0h+var_160]; this
0x18001ecf5  call    ?StartActivity@LaunchIdleApplication@RetailDemoTelemetry@@QEAAX_NK@Z; RetailDemoTelemetry::LaunchIdleApplication::StartActivity(bool,ulong)
0x18001ecfa  nop
0x18001ecfb  mov     dil, 1
0x18001ecfe  test    [rbx+80h], dil
0x18001ed05  jnz     short loc_18001ED54
0x18001ed07  lea     rdx, [rsp+1C0h+var_178]
0x18001ed0c  mov     rcx, rbx
0x18001ed0f  call    ?GetRetailDemoAppsController@LaunchAppAsUserTaskBase@@IEAA?AV?$ComPtr@UIRetailDemoAppsController@@@WRL@Microsoft@@XZ; LaunchAppAsUserTaskBase::GetRetailDemoAppsController(void)
0x18001ed14  nop
0x18001ed15  mov     rcx, [rsp+1C0h+var_178]
0x18001ed1a  mov     rax, [rcx]
0x18001ed1d  mov     rdx, [rbx+58h]
0x18001ed21  mov     rax, [rax+20h]
0x18001ed25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed2a  mov     rcx, [rbp+0C8h]; this
0x18001ed31  test    eax, eax
0x18001ed33  jns     short loc_18001ED4A
0x18001ed35  mov     r9d, eax; char *
0x18001ed38  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001ed3f  mov     edx, 71h ; 'q'; void *
0x18001ed44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ed4a  lea     rcx, [rsp+1C0h+var_178]
0x18001ed4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ed54  mov     [rsp+1C0h+var_17C], 0
0x18001ed5c  xor     edx, edx
0x18001ed5e  lea     rcx, [rsp+1C0h+var_178]
0x18001ed63  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x18001ed68  nop
0x18001ed69  mov     rcx, [rax]
0x18001ed6c  mov     rax, [rcx]
0x18001ed6f  lea     r8, [rsp+1C0h+var_17C]
0x18001ed74  mov     edx, 2
0x18001ed79  mov     rax, [rax+0C0h]
0x18001ed80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed85  mov     rcx, [rbp+0C8h]; this
0x18001ed8c  test    eax, eax
0x18001ed8e  jns     short loc_18001EDA5
0x18001ed90  mov     r9d, eax; char *
0x18001ed93  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001ed9a  mov     edx, 76h ; 'v'; void *
0x18001ed9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001eda4  nop
0x18001eda5  lea     rcx, [rsp+1C0h+var_178]
0x18001edaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001edaf  mov     r9d, [rsp+1C0h+var_17C]; unsigned int
0x18001edb4  lea     r8, ?c_retailDemoValueActiveScreenTopology@@3QBGB; "ActiveScreenTopology"
0x18001edbb  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001edc2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001edc9  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001edce  mov     rcx, [rbp+0C8h]; this
0x18001edd5  test    eax, eax
0x18001edd7  jns     short loc_18001EDED
0x18001edd9  mov     r9d, eax; char *
0x18001eddc  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001ede3  mov     edx, 77h ; 'w'; void *
0x18001ede8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001eded  mov     rcx, rbx; this
0x18001edf0  call    ?Execute@LaunchAppAsUserTaskBase@@MEAAXXZ; LaunchAppAsUserTaskBase::Execute(void)
0x18001edf5  xor     edx, edx
0x18001edf7  lea     rcx, [rsp+1C0h+var_160]
0x18001edfc  call    ?Stop@?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ee01  cmp     byte ptr [rbx+90h], 0
0x18001ee08  jnz     short loc_18001EE15
0x18001ee0a  cmp     byte ptr [rbx+91h], 0
0x18001ee11  jnz     short loc_18001EE15
0x18001ee13  xor     edi, edi
0x18001ee15  mov     dl, dil
0x18001ee18  xor     ecx, ecx
0x18001ee1a  call    ??$HandleEvent@$0L@J_N@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAXJ_N@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<11,long,bool>(long,bool)
0x18001ee1f  nop
0x18001ee20  lea     rcx, [rsp+1C0h+var_160]; this
0x18001ee25  call    ??1LaunchIdleApplication@RetailDemoTelemetry@@QEAA@XZ; RetailDemoTelemetry::LaunchIdleApplication::~LaunchIdleApplication(void)
0x18001ee2a  mov     rcx, [rbp+0C0h+var_10]
0x18001ee31  xor     rcx, rsp; StackCookie
0x18001ee34  call    __security_check_cookie
0x18001ee39  lea     r11, [rsp+1C0h+var_s0]
0x18001ee41  mov     rbx, [r11+18h]
0x18001ee45  mov     rdi, [r11+20h]
0x18001ee49  mov     rsp, r11
0x18001ee4c  pop     rbp
0x18001ee4d  retn
```
