# ResetWindowsHelloDemoDataTask::Execute(void)

- ea: `0x1800263e0`
- end: `0x18002658d`
- name: `?Execute@ResetWindowsHelloDemoDataTask@@MEAAXXZ`
- size: `429`
- prototype: `void __fastcall(ResetWindowsHelloDemoDataTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x180014d04`
- `0x18001ff9c`
- `0x1800263e0`
- `0x18002e5b8`
- `0x18002fc68`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026445`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026445`
- `samcli!NetUserSetInfo` at `0x1800264bf`
- `samcli!NetUserSetInfo` at `0x1800264bf`

## string_xrefs

- `0x180026437`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180026476`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetwindowshellodemodata.cpp`
- `0x1800264c9`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetwindowshellodemodata.cpp`
- `0x180026551`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetwindowshellodemodata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ResetWindowsHelloDemoDataTask::Execute(ResetWindowsHelloDemoDataTask *this)
{
  LSTATUS ValueW; // eax
  unsigned __int64 v2; // r9
  char v3; // bl
  unsigned __int64 *v4; // rdx
  const char *v5; // r9
  _QWORD *v6; // rdx
  _QWORD *UserAgent; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD parm_err; // [rsp+40h] [rbp-C0h] BYREF
  BYTE buf[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v15[7]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v16; // [rsp+88h] [rbp-78h]
  WCHAR username[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  parm_err = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Account",
             2u,
             0,
             username,
             &parm_err);
  v2 = (unsigned int)ValueW;
  if ( ValueW )
  {
    username[0] = 0;
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( (v2 & 0x80000000) == 0LL )
  {
    *(_QWORD *)buf = &qword_180057BE0;
    parm_err = 0;
    if ( NetUserSetInfo(0, username, 0x3F3u, buf, &parm_err) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x26,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetwindowshellodemodata.cpp",
        v5);
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetwindowshellodemodata.cpp",
      (const char *)v2,
      pdwType);
  }
  v15[0] = off_180052B18;
  v16 = v15;
  RetailDemoUtil::ExecuteAsDemoUser((__int64)v15, v4);
  if ( v16 )
  {
    v6 = v15;
    LOBYTE(v6) = v16 != v15;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v6);
  }
  if ( v3 )
  {
    UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(buf, 0);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*UserAgent + 176LL))(*UserAgent);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetwindowshellodemodata.cpp",
        (const char *)(unsigned int)v8,
        pdwTypea);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(buf, v9, v10);
  }
}

```

## disassembly

```asm
0x1800263e0  mov     [rsp-8+arg_0], rbx
0x1800263e5  push    rbp
0x1800263e6  lea     rbp, [rsp-1B0h]
0x1800263ee  sub     rsp, 2B0h
0x1800263f5  mov     rax, cs:__security_cookie
0x1800263fc  xor     rax, rsp
0x1800263ff  mov     [rbp+1B0h+var_10], rax
0x180026406  mov     [rsp+2B0h+parm_err], 202h
0x18002640e  lea     rax, [rsp+2B0h+parm_err]
0x180026413  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180026418  lea     rax, [rbp+1B0h+username]
0x18002641c  mov     [rsp+2B0h+pvData], rax; pvData
0x180026421  mov     [rsp+2B0h+pdwType], 0; int
0x18002642a  mov     r9d, 2; dwFlags
0x180026430  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x180026437  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002643e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180026445  call    cs:__imp_RegGetValueW
0x18002644b  mov     r9d, eax
0x18002644e  test    eax, eax
0x180026450  jz      short loc_180026468
0x180026452  xor     eax, eax
0x180026454  mov     [rbp+1B0h+username], ax
0x180026458  test    r9d, r9d
0x18002645b  jle     short loc_180026468
0x18002645d  movzx   r9d, r9w
0x180026461  or      r9d, 80070000h; char *
0x180026468  mov     rcx, [rbp+1B8h]; this
0x18002646f  test    r9d, r9d
0x180026472  jns     short loc_180026489
0x180026474  xor     bl, bl
0x180026476  lea     r8, aPcshellShellRe_27; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002647d  mov     edx, 21h ; '!'; void *
0x180026482  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026487  jmp     short loc_1800264E0
0x180026489  lea     rax, qword_180057BE0
0x180026490  mov     qword ptr [rsp+2B0h+buf], rax
0x180026495  mov     [rsp+2B0h+parm_err], 0
0x18002649d  mov     rbx, [rbp+1B8h]
0x1800264a4  lea     rax, [rsp+2B0h+parm_err]
0x1800264a9  mov     [rsp+2B0h+pdwType], rax; int
0x1800264ae  lea     r9, [rsp+2B0h+buf]; buf
0x1800264b3  mov     r8d, 3F3h; level
0x1800264b9  lea     rdx, [rbp+1B0h+username]; username
0x1800264bd  xor     ecx, ecx; servername
0x1800264bf  call    cs:__imp_NetUserSetInfo
0x1800264c5  test    eax, eax
0x1800264c7  jz      short loc_1800264DE
0x1800264c9  lea     r8, aPcshellShellRe_27; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800264d0  mov     edx, 26h ; '&'; void *
0x1800264d5  mov     rcx, rbx; this
0x1800264d8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800264de  mov     bl, 1
0x1800264e0  lea     rax, off_180052B18
0x1800264e7  mov     [rsp+2B0h+var_260], rax
0x1800264ec  lea     rax, [rsp+2B0h+var_260]
0x1800264f1  mov     [rbp+1B0h+var_228], rax
0x1800264f5  lea     rcx, [rsp+2B0h+var_260]
0x1800264fa  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x1800264ff  nop
0x180026500  mov     rcx, [rbp+1B0h+var_228]
0x180026504  test    rcx, rcx
0x180026507  jz      short loc_180026520
0x180026509  mov     rax, [rcx]
0x18002650c  lea     rdx, [rsp+2B0h+var_260]
0x180026511  cmp     rcx, rdx
0x180026514  setnz   dl
0x180026517  mov     rax, [rax+20h]
0x18002651b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026520  test    bl, bl
0x180026522  jz      short loc_18002656D
0x180026524  xor     edx, edx
0x180026526  lea     rcx, [rsp+2B0h+buf]
0x18002652b  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x180026530  nop
0x180026531  mov     rcx, [rax]
0x180026534  mov     rax, [rcx]
0x180026537  mov     rax, [rax+0B0h]
0x18002653e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026543  mov     rcx, [rbp+1B8h]; this
0x18002654a  test    eax, eax
0x18002654c  jns     short loc_180026563
0x18002654e  mov     r9d, eax; char *
0x180026551  lea     r8, aPcshellShellRe_27; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026558  mov     edx, 37h ; '7'; void *
0x18002655d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026562  nop
0x180026563  lea     rcx, [rsp+2B0h+buf]
0x180026568  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002656d  mov     rcx, [rbp+1B0h+var_10]
0x180026574  xor     rcx, rsp; StackCookie
0x180026577  call    __security_check_cookie
0x18002657c  mov     rbx, [rsp+2B0h+arg_0]
0x180026584  add     rsp, 2B0h
0x18002658b  pop     rbp
0x18002658c  retn
```
