# RetailDemoUserAgent::CloseAppByAumid(ushort const *)

- ea: `0x180039a40`
- end: `0x180039b6b`
- name: `?CloseAppByAumid@RetailDemoUserAgent@@UEAAJPEBG@Z`
- size: `299`
- prototype: `int(RetailDemoUserAgent *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x180022ad8`
- `0x180039a40`
- `0x18003d934`
- `0x18004181c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039b31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039b31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180039b40`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180039b40`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039b06`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039b06`
- `USER32!GetWindowThreadProcessId` at `0x180039af4`
- `USER32!GetWindowThreadProcessId` at `0x180039af4`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180039b23`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180039b23`

## string_xrefs

- `0x180039a8a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180039aca`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoUserAgent::CloseAppByAumid(
        RetailDemoUserAgent *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  RetailDemoUserAgent *v4; // rcx
  int ViewForAumid; // eax
  RetailDemoUserAgent *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 result; // rax
  int HwndForView; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  HANDLE v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  HANDLE v19[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD dwProcessId; // [rsp+40h] [rbp+8h] BYREF
  int v22; // [rsp+44h] [rbp+Ch]
  struct IApplicationView *v23; // [rsp+50h] [rbp+18h] BYREF
  HWND hWnd; // [rsp+58h] [rbp+20h] BYREF

  v22 = HIDWORD(this);
  v23 = 0;
  hWnd = 0;
  dwProcessId = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, a2, a3);
  try
  {
    ViewForAumid = RetailDemoUserAgent::TryGetViewForAumid(v4, a2, &v23);
    v7 = ViewForAumid;
    if ( ViewForAumid >= 0 )
    {
      HwndForView = RetailDemoUserAgent::GetHwndForView(v6, v23, &hWnd);
      v13 = HwndForView;
      if ( HwndForView >= 0 )
      {
        GetWindowThreadProcessId(hWnd, &dwProcessId);
        v16 = OpenProcess(0x100401u, 0, dwProcessId);
        v19[0] = v16;
        PostMessageW(hWnd, 0x10u, 0, 0);
        if ( WaitForSingleObject(v16, 0x3E8u) )
          TerminateProcess(v16, 0);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v17, v18);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x502,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)HwndForView,
          (int)v19[0]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v14, v15);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x501,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)ViewForAumid,
        (int)v19[0]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v8, v9);
      result = v7;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x512,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v10);
    return 2147944027LL;
  }
  return result;
}

```

## disassembly

```asm
0x180039a40  mov     rax, rsp
0x180039a43  mov     [rax+8], rcx
0x180039a47  push    rbx
0x180039a48  sub     rsp, 30h
0x180039a4c  mov     rbx, rdx
0x180039a4f  mov     qword ptr [rax+18h], 0
0x180039a57  mov     qword ptr [rax+20h], 0
0x180039a5f  mov     dword ptr [rax+8], 0
0x180039a66  lea     rcx, [rax+18h]
0x180039a6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039a6f  lea     r8, [rsp+38h+arg_10]; struct IApplicationView **
0x180039a74  mov     rdx, rbx; unsigned __int16 *
0x180039a77  call    ?TryGetViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z; RetailDemoUserAgent::TryGetViewForAumid(ushort const *,IApplicationView * *)
0x180039a7c  mov     ebx, eax
0x180039a7e  test    eax, eax
0x180039a80  jns     short loc_180039AAD
0x180039a82  mov     rcx, [rsp+38h]; this
0x180039a87  mov     r9d, eax; char *
0x180039a8a  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180039a91  mov     edx, 501h; void *
0x180039a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a9b  nop
0x180039a9c  lea     rcx, [rsp+38h+arg_10]
0x180039aa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039aa6  mov     eax, ebx
0x180039aa8  jmp     loc_180039B64
0x180039aad  lea     r8, [rsp+38h+hWnd]; HWND *
0x180039ab2  mov     rdx, [rsp+38h+arg_10]; struct IApplicationView *
0x180039ab7  call    ?GetHwndForView@RetailDemoUserAgent@@AEAAJPEAUIApplicationView@@PEAPEAUHWND__@@@Z; RetailDemoUserAgent::GetHwndForView(IApplicationView *,HWND__ * *)
0x180039abc  mov     ebx, eax
0x180039abe  test    eax, eax
0x180039ac0  jns     short loc_180039AEA
0x180039ac2  mov     rcx, [rsp+38h]; this
0x180039ac7  mov     r9d, eax; char *
0x180039aca  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180039ad1  mov     edx, 502h; void *
0x180039ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039adb  nop
0x180039adc  lea     rcx, [rsp+38h+arg_10]
0x180039ae1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039ae6  mov     eax, ebx
0x180039ae8  jmp     short loc_180039B64
0x180039aea  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x180039aef  mov     rcx, [rsp+38h+hWnd]; hWnd
0x180039af4  call    cs:__imp_GetWindowThreadProcessId
0x180039afa  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x180039aff  xor     edx, edx; bInheritHandle
0x180039b01  mov     ecx, 100401h; dwDesiredAccess
0x180039b06  call    cs:__imp_OpenProcess
0x180039b0c  mov     rbx, rax
0x180039b0f  mov     [rsp+38h+var_18], rax
0x180039b14  xor     r9d, r9d; lParam
0x180039b17  xor     r8d, r8d; wParam
0x180039b1a  lea     edx, [r9+10h]; Msg
0x180039b1e  mov     rcx, [rsp+38h+hWnd]; hWnd
0x180039b23  call    cs:__imp_PostMessageW
0x180039b29  mov     edx, 3E8h; dwMilliseconds
0x180039b2e  mov     rcx, rbx; hHandle
0x180039b31  call    cs:__imp_WaitForSingleObject
0x180039b37  test    eax, eax
0x180039b39  jz      short loc_180039B46
0x180039b3b  xor     edx, edx; uExitCode
0x180039b3d  mov     rcx, rbx; hProcess
0x180039b40  call    cs:__imp_TerminateProcess
0x180039b46  lea     rcx, [rsp+38h+var_18]
0x180039b4b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039b50  nop
0x180039b51  lea     rcx, [rsp+38h+arg_10]
0x180039b56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039b5b  xor     eax, eax
0x180039b5d  jmp     short loc_180039B64
0x180039b5f  mov     eax, 8007065Bh
0x180039b64  add     rsp, 30h
0x180039b68  pop     rbx
0x180039b69  retn
```
