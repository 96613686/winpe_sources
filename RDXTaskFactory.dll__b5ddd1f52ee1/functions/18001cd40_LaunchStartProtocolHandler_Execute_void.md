# LaunchStartProtocolHandler::Execute(void)

- ea: `0x18001cd40`
- end: `0x18001ceef`
- name: `?Execute@LaunchStartProtocolHandler@@UEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(LaunchStartProtocolHandler *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18001cd40`
- `0x180050010`

## import_xrefs

- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001cea7`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001cea7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cd93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cdd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cd93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cdd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ce15`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ce15`

## string_xrefs

- `0x18001cdc8`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18001cd82`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18001ce28`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchstartprotocolhandler.cpp`
- `0x18001ce82`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchstartprotocolhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LaunchStartProtocolHandler::Execute(LaunchStartProtocolHandler *this)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  HRESULT Instance; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, SID *, GUID *, IUnknown **); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int pdwType; // [rsp+20h] [rbp-30h]
  LPVOID ppv[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  IUnknown *pUnk; // [rsp+88h] [rbp+38h] BYREF

  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &pvData,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &pvData,
      &pcbData);
  }
  if ( !pvData )
    return 2147500033LL;
  ppv[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv, v1, v2);
  Instance = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, ppv);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    pUnk = 0;
    v10 = ppv[0];
    v11 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, IUnknown **))(*(_QWORD *)ppv[0] + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk, v5, v6);
    v12 = v11(v10, &SID_ImmersiveLauncher, &GUID_d8d60399_a0f1_f987_5551_321fd1b49864, &pUnk);
    v7 = v12;
    if ( v12 >= 0 )
    {
      CoAllowSetForegroundWindow(pUnk, 0);
      v12 = ((__int64 (__fastcall *)(IUnknown *, __int64))pUnk->lpVtbl[1].QueryInterface)(pUnk, 12);
      v7 = v12;
      if ( v12 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk, v16, v17);
        v7 = 0;
        goto LABEL_13;
      }
      v13 = 29;
    }
    else
    {
      v13 = 27;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchstartprotocolhandler.cpp",
      (const char *)(unsigned int)v12,
      pdwType);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk, v14, v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchstartprotocolhandler.cpp",
      (const char *)(unsigned int)Instance,
      pdwType);
  }
LABEL_13:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x18001cd40  push    rbp
0x18001cd42  push    rbx
0x18001cd43  push    rdi
0x18001cd44  mov     rbp, rsp
0x18001cd47  sub     rsp, 50h
0x18001cd4b  mov     [rbp+arg_10], 0
0x18001cd52  mov     ebx, 4
0x18001cd57  mov     [rbp+arg_8], ebx
0x18001cd5a  lea     rax, [rbp+arg_8]
0x18001cd5e  mov     [rsp+50h+pcbData], rax; pcbData
0x18001cd63  lea     rax, [rbp+arg_10]
0x18001cd67  mov     [rsp+50h+pvData], rax; pvData
0x18001cd6c  mov     [rsp+50h+pdwType], 0; pdwType
0x18001cd75  mov     r9d, 10010h; dwFlags
0x18001cd7b  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18001cd82  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18001cd89  mov     rdi, 0FFFFFFFF80000002h
0x18001cd90  mov     rcx, rdi; hkey
0x18001cd93  call    cs:__imp_RegGetValueW
0x18001cd99  test    eax, eax
0x18001cd9b  jz      short loc_18001CDD8
0x18001cd9d  mov     [rbp+arg_8], ebx
0x18001cda0  lea     rax, [rbp+arg_8]
0x18001cda4  mov     [rsp+50h+pcbData], rax; pcbData
0x18001cda9  lea     rax, [rbp+arg_10]
0x18001cdad  mov     [rsp+50h+pvData], rax; pvData
0x18001cdb2  mov     [rsp+50h+pdwType], 0; pdwType
0x18001cdbb  mov     r9d, 20010010h; dwFlags
0x18001cdc1  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18001cdc8  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001cdcf  mov     rcx, rdi; hkey
0x18001cdd2  call    cs:__imp_RegGetValueW
0x18001cdd8  cmp     [rbp+arg_10], 0
0x18001cddc  jnz     short loc_18001CDE8
0x18001cdde  mov     eax, 80004001h
0x18001cde3  jmp     loc_18001CEE7
0x18001cde8  mov     [rbp+ppv], 0
0x18001cdf0  lea     rcx, [rbp+ppv]
0x18001cdf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cdf9  lea     rax, [rbp+ppv]
0x18001cdfd  mov     [rsp+50h+pdwType], rax; int
0x18001ce02  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18001ce09  mov     r8d, ebx; dwClsContext
0x18001ce0c  xor     edx, edx; pUnkOuter
0x18001ce0e  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18001ce15  call    cs:__imp_CoCreateInstance
0x18001ce1b  mov     ebx, eax
0x18001ce1d  test    eax, eax
0x18001ce1f  jns     short loc_18001CE3E
0x18001ce21  mov     rcx, [rbp+18h]; this
0x18001ce25  mov     r9d, eax; char *
0x18001ce28  lea     r8, aPcshellShellRe_17; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001ce2f  mov     edx, 19h; void *
0x18001ce34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce39  jmp     loc_18001CEDC
0x18001ce3e  mov     [rbp+pUnk], 0
0x18001ce46  mov     rdi, [rbp+ppv]
0x18001ce4a  mov     rax, [rdi]
0x18001ce4d  mov     rbx, [rax+18h]
0x18001ce51  lea     rcx, [rbp+pUnk]
0x18001ce55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ce5a  lea     r9, [rbp+pUnk]
0x18001ce5e  lea     r8, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864
0x18001ce65  lea     rdx, SID_ImmersiveLauncher
0x18001ce6c  mov     rcx, rdi
0x18001ce6f  mov     rax, rbx
0x18001ce72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce77  mov     ebx, eax
0x18001ce79  test    eax, eax
0x18001ce7b  jns     short loc_18001CEA1
0x18001ce7d  mov     edx, 1Bh; void *
0x18001ce82  lea     r8, aPcshellShellRe_17; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001ce89  mov     r9d, eax; char *
0x18001ce8c  mov     rcx, [rbp+18h]; this
0x18001ce90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ce95  nop
0x18001ce96  lea     rcx, [rbp+pUnk]
0x18001ce9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ce9f  jmp     short loc_18001CEDC
0x18001cea1  xor     edx, edx; lpvReserved
0x18001cea3  mov     rcx, [rbp+pUnk]; pUnk
0x18001cea7  call    cs:__imp_CoAllowSetForegroundWindow
0x18001cead  mov     rcx, [rbp+pUnk]
0x18001ceb1  mov     rax, [rcx]
0x18001ceb4  xor     r8d, r8d
0x18001ceb7  lea     edx, [r8+0Ch]
0x18001cebb  mov     rax, [rax+18h]
0x18001cebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec4  mov     ebx, eax
0x18001cec6  test    eax, eax
0x18001cec8  jns     short loc_18001CED1
0x18001ceca  mov     edx, 1Dh
0x18001cecf  jmp     short loc_18001CE82
0x18001ced1  lea     rcx, [rbp+pUnk]
0x18001ced5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ceda  xor     ebx, ebx
0x18001cedc  lea     rcx, [rbp+ppv]
0x18001cee0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cee5  mov     eax, ebx
0x18001cee7  add     rsp, 50h
0x18001ceeb  pop     rdi
0x18001ceec  pop     rbx
0x18001ceed  pop     rbp
0x18001ceee  retn
```
