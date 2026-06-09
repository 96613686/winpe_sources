# CBrowserBrokerInstance::LaunchIE(ushort const *,int,int *,ulong *,HWND__ * *)

- ea: `0x18000a7e0`
- end: `0x18000aaba`
- name: `?LaunchIE@CBrowserBrokerInstance@@UEAAJPEBGHPEAHPEAKPEAPEAUHWND__@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, int, int *, unsigned int *, HWND *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002cc4`
- `0x180002ce0`
- `0x180002d3c`
- `0x1800037ac`
- `0x18000a2dc`
- `0x18000a7e0`
- `0x18000d17c`
- `0x18000d1c0`
- `0x18000e428`
- `0x1800245ec`
- `0x180024cf0`
- `0x18002b4e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa5e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000aa48`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000aa48`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000aa28`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000aa28`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000a9be`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000a9be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18000a8ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18000aa35`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18000a8ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18000aa35`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowExW` at `0x18000a8e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowExW` at `0x18000a8e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18000a906`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18000a906`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000a8bc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000a8bc`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::LaunchIE(
        CBrowserBrokerInstance *this,
        unsigned __int16 *a2,
        int a3,
        int *a4,
        unsigned int *a5,
        HWND *a6)
{
  BOOL v6; // esi
  HWND v7; // r14
  int v9; // edi
  unsigned int v10; // edx
  int PIC; // ebx
  unsigned __int16 *v12; // rdi
  HWND v13; // rdi
  HWND Window; // rax
  const wchar_t *v15; // rax
  DWORD v16; // eax
  DWORD dwProcessId; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Data; // [rsp+54h] [rbp-ACh] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  HWND v21; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v22; // [rsp+68h] [rbp-98h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR CommandLine[2360]; // [rsp+310h] [rbp+210h] BYREF

  v6 = 0;
  v7 = 0;
  v22 = a2;
  v20 = a3;
  dwProcessId = 0;
  v9 = a3;
  v21 = 0;
  Data = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &Data);
  if ( PIC >= 0 )
  {
    if ( v9 )
    {
      PIC = -2147467263;
    }
    else
    {
      v12 = (unsigned __int16 *)operator new(0x104Cu);
      PIC = StringCchCopyW(v12, 0x824u, v22);
      if ( PIC >= 0 )
      {
        PIC = _QueueNavigationToFrame((const struct tagDDENAVIGATESTRUCT *)v12, &v21);
        if ( PIC < 0 )
          PIC = -2144927487;
        operator delete(v12);
        v7 = v21;
      }
      if ( PIC >= 0 )
      {
        GetWindowThreadProcessId(v7, &dwProcessId);
        if ( dwProcessId )
          LOBYTE(v6) = !AllowSetForegroundWindow(dwProcessId);
        v13 = 0;
        while ( 1 )
        {
          Window = FindWindowExW(0, v13, L"IEFrame", 0);
          PIC = 0;
          v13 = Window;
          if ( !Window )
            break;
          if ( !PostMessageW(Window, 0x705u, 1u, 0) )
          {
            PIC = -2147467259;
            break;
          }
        }
        if ( PIC >= 0 )
          goto LABEL_24;
      }
      v9 = v20;
    }
    if ( GetIEPathFromCsidlW(v25, v10, 0x26u, 1) )
    {
      v15 = L"-private";
      if ( !v9 )
        v15 = &pszSubkey;
      PIC = StringCchPrintfW(CommandLine, 0x935u, L"\"%s\" %s %s", v25, v15, v22);
      if ( PIC >= 0 )
      {
        Data = 1;
        RegSetKeyValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Internet Explorer\\Main",
          L"IE10TourNoShow",
          4u,
          &Data,
          4u);
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        if ( CreateProcessW(0, CommandLine, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          v6 = !AllowSetForegroundWindow(ProcessInformation.dwProcessId);
          ResumeThread(ProcessInformation.hThread);
          CloseHandle(ProcessInformation.hProcess);
          CloseHandle(ProcessInformation.hThread);
          v16 = ProcessInformation.dwProcessId;
          goto LABEL_25;
        }
        PIC = HRESULTFromLastErrorError();
      }
    }
  }
LABEL_24:
  v16 = dwProcessId;
LABEL_25:
  if ( a4 )
    *a4 = v6;
  if ( a5 )
    *a5 = v16;
  if ( a6 )
    *a6 = v7;
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000a7e0  mov     [rsp-8+arg_0], rbx
0x18000a7e5  push    rbp
0x18000a7e6  push    rsi
0x18000a7e7  push    rdi
0x18000a7e8  push    r12
0x18000a7ea  push    r13
0x18000a7ec  push    r14
0x18000a7ee  push    r15
0x18000a7f0  lea     rbp, [rsp-1490h]
0x18000a7f8  mov     eax, 1590h
0x18000a7fd  call    _alloca_probe
0x18000a802  sub     rsp, rax
0x18000a805  mov     rax, cs:__security_cookie
0x18000a80c  xor     rax, rsp
0x18000a80f  mov     [rbp+14C0h+var_40], rax
0x18000a816  mov     r12, [rbp+14C0h+arg_20]
0x18000a81d  xor     esi, esi
0x18000a81f  mov     r15, [rbp+14C0h+arg_28]
0x18000a826  xor     r14d, r14d
0x18000a829  mov     [rsp+15C0h+var_1558], rdx
0x18000a82e  mov     r13, r9
0x18000a831  lea     rdx, [rsp+15C0h+Data]; unsigned int *
0x18000a836  mov     [rsp+15C0h+var_1568], r8d
0x18000a83b  lea     ecx, [rsi+1]; unsigned int
0x18000a83e  mov     [rsp+15C0h+dwProcessId], esi
0x18000a842  mov     edi, r8d
0x18000a845  mov     [rsp+15C0h+var_1560], r14
0x18000a84a  mov     [rsp+15C0h+Data], esi
0x18000a84e  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000a853  mov     ebx, eax
0x18000a855  test    eax, eax
0x18000a857  js      loc_18000AA70
0x18000a85d  test    edi, edi
0x18000a85f  jnz     loc_18000A923
0x18000a865  mov     ecx, 104Ch; Size
0x18000a86a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a86f  mov     r8, [rsp+15C0h+var_1558]; unsigned __int16 *
0x18000a874  mov     edx, 824h; unsigned __int64
0x18000a879  mov     rcx, rax; unsigned __int16 *
0x18000a87c  mov     rdi, rax
0x18000a87f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a884  mov     ebx, eax
0x18000a886  test    eax, eax
0x18000a888  js      short loc_18000A8B0
0x18000a88a  lea     rdx, [rsp+15C0h+var_1560]; HWND *
0x18000a88f  mov     rcx, rdi; struct tagDDENAVIGATESTRUCT *
0x18000a892  call    ?_QueueNavigationToFrame@@YAJPEBUtagDDENAVIGATESTRUCT@@PEAPEAUHWND__@@@Z; _QueueNavigationToFrame(tagDDENAVIGATESTRUCT const *,HWND__ * *)
0x18000a897  mov     ebx, eax
0x18000a899  mov     rcx, rdi; Block
0x18000a89c  test    ebx, ebx
0x18000a89e  mov     eax, 80270101h
0x18000a8a3  cmovs   ebx, eax
0x18000a8a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a8ab  mov     r14, [rsp+15C0h+var_1560]
0x18000a8b0  test    ebx, ebx
0x18000a8b2  js      short loc_18000A91D
0x18000a8b4  lea     rdx, [rsp+15C0h+dwProcessId]; lpdwProcessId
0x18000a8b9  mov     rcx, r14; hWnd
0x18000a8bc  call    cs:__imp_GetWindowThreadProcessId
0x18000a8c2  mov     ecx, [rsp+15C0h+dwProcessId]; dwProcessId
0x18000a8c6  test    ecx, ecx
0x18000a8c8  jz      short loc_18000A8D6
0x18000a8ca  call    cs:__imp_AllowSetForegroundWindow
0x18000a8d0  test    eax, eax
0x18000a8d2  setz    sil
0x18000a8d6  xor     edi, edi
0x18000a8d8  xor     r9d, r9d; lpszWindow
0x18000a8db  lea     r8, szClass; "IEFrame"
0x18000a8e2  mov     rdx, rdi; hWndChildAfter
0x18000a8e5  xor     ecx, ecx; hWndParent
0x18000a8e7  call    cs:__imp_FindWindowExW
0x18000a8ed  xor     ebx, ebx
0x18000a8ef  mov     rdi, rax
0x18000a8f2  test    rax, rax
0x18000a8f5  jz      short loc_18000A915
0x18000a8f7  xor     r9d, r9d; lParam
0x18000a8fa  lea     r8d, [rbx+1]; wParam
0x18000a8fe  mov     edx, 705h; Msg
0x18000a903  mov     rcx, rax; hWnd
0x18000a906  call    cs:__imp_PostMessageW
0x18000a90c  test    eax, eax
0x18000a90e  jnz     short loc_18000A8D8
0x18000a910  mov     ebx, 80004005h
0x18000a915  test    ebx, ebx
0x18000a917  jns     loc_18000AA70
0x18000a91d  mov     edi, [rsp+15C0h+var_1568]
0x18000a921  jmp     short loc_18000A928
0x18000a923  mov     ebx, 80004001h
0x18000a928  mov     r9b, 1; bool
0x18000a92b  lea     rcx, [rbp+14C0h+var_14C0]; unsigned __int16 *
0x18000a92f  mov     r8d, 26h ; '&'; unsigned int
0x18000a935  call    ?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z; GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)
0x18000a93a  test    al, al
0x18000a93c  jz      loc_18000AA70
0x18000a942  lea     rcx, pszSubkey
0x18000a949  test    edi, edi
0x18000a94b  lea     rax, aPrivate; "-private"
0x18000a952  mov     edx, 935h; unsigned __int64
0x18000a957  cmovz   rax, rcx
0x18000a95b  lea     r9, [rbp+14C0h+var_14C0]
0x18000a95f  mov     rcx, [rsp+15C0h+var_1558]
0x18000a964  lea     r8, aSSS_0; "\"%s\" %s %s"
0x18000a96b  mov     qword ptr [rsp+15C0h+cbData], rcx
0x18000a970  lea     rcx, [rbp+14C0h+CommandLine]; unsigned __int16 *
0x18000a977  mov     [rsp+15C0h+lpData], rax
0x18000a97c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a981  mov     ebx, eax
0x18000a983  test    eax, eax
0x18000a985  js      loc_18000AA70
0x18000a98b  mov     edi, 4
0x18000a990  mov     [rsp+15C0h+Data], 1
0x18000a998  lea     rax, [rsp+15C0h+Data]
0x18000a99d  mov     [rsp+15C0h+cbData], edi; cbData
0x18000a9a1  mov     r9d, edi; dwType
0x18000a9a4  mov     [rsp+15C0h+lpData], rax; lpData
0x18000a9a9  lea     r8, ValueName; "IE10TourNoShow"
0x18000a9b0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a9b7  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x18000a9be  call    cs:__imp_RegSetKeyValueW
0x18000a9c4  xor     edx, edx; Val
0x18000a9c6  lea     r8d, [rdi+60h]; Size
0x18000a9ca  lea     rcx, [rbp+14C0h+StartupInfo+4]; void *
0x18000a9ce  call    memset_0
0x18000a9d3  xor     eax, eax
0x18000a9d5  mov     [rbp+14C0h+StartupInfo.cb], 68h ; 'h'
0x18000a9dc  mov     qword ptr [rbp+14C0h+ProcessInformation.dwProcessId], rax
0x18000a9e0  lea     rdx, [rbp+14C0h+CommandLine]; lpCommandLine
0x18000a9e7  lea     rax, [rsp+15C0h+ProcessInformation]
0x18000a9ec  xorps   xmm0, xmm0
0x18000a9ef  mov     [rsp+15C0h+lpProcessInformation], rax; lpProcessInformation
0x18000a9f4  xor     r9d, r9d; lpThreadAttributes
0x18000a9f7  lea     rax, [rbp+14C0h+StartupInfo]
0x18000a9fb  xor     r8d, r8d; lpProcessAttributes
0x18000a9fe  mov     [rsp+15C0h+lpStartupInfo], rax; lpStartupInfo
0x18000aa03  xor     ecx, ecx; lpApplicationName
0x18000aa05  mov     [rsp+15C0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000aa0e  mov     [rsp+15C0h+lpEnvironment], 0; lpEnvironment
0x18000aa17  mov     [rsp+15C0h+cbData], edi; dwCreationFlags
0x18000aa1b  mov     dword ptr [rsp+15C0h+lpData], 0; bInheritHandles
0x18000aa23  movups  xmmword ptr [rsp+15C0h+ProcessInformation.hProcess], xmm0
0x18000aa28  call    cs:__imp_CreateProcessW
0x18000aa2e  test    eax, eax
0x18000aa30  jz      short loc_18000AA69
0x18000aa32  mov     ecx, [rbp+14C0h+ProcessInformation.dwProcessId]; dwProcessId
0x18000aa35  call    cs:__imp_AllowSetForegroundWindow
0x18000aa3b  mov     rcx, [rsp+15C0h+ProcessInformation.hThread]; hThread
0x18000aa40  xor     esi, esi
0x18000aa42  test    eax, eax
0x18000aa44  setz    sil
0x18000aa48  call    cs:__imp_ResumeThread
0x18000aa4e  mov     rcx, [rsp+15C0h+ProcessInformation.hProcess]; hObject
0x18000aa53  call    cs:__imp_CloseHandle
0x18000aa59  mov     rcx, [rsp+15C0h+ProcessInformation.hThread]; hObject
0x18000aa5e  call    cs:__imp_CloseHandle
0x18000aa64  mov     eax, [rbp+14C0h+ProcessInformation.dwProcessId]
0x18000aa67  jmp     short loc_18000AA74
0x18000aa69  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18000aa6e  mov     ebx, eax
0x18000aa70  mov     eax, [rsp+15C0h+dwProcessId]
0x18000aa74  test    r13, r13
0x18000aa77  jz      short loc_18000AA7D
0x18000aa79  mov     [r13+0], esi
0x18000aa7d  test    r12, r12
0x18000aa80  jz      short loc_18000AA86
0x18000aa82  mov     [r12], eax
0x18000aa86  test    r15, r15
0x18000aa89  jz      short loc_18000AA8E
0x18000aa8b  mov     [r15], r14
0x18000aa8e  mov     eax, ebx
0x18000aa90  mov     rcx, [rbp+14C0h+var_40]
0x18000aa97  xor     rcx, rsp; StackCookie
0x18000aa9a  call    __security_check_cookie
0x18000aa9f  mov     rbx, [rsp+15C0h+arg_0]
0x18000aaa7  add     rsp, 1590h
0x18000aaae  pop     r15
0x18000aab0  pop     r14
0x18000aab2  pop     r13
0x18000aab4  pop     r12
0x18000aab6  pop     rdi
0x18000aab7  pop     rsi
0x18000aab8  pop     rbp
0x18000aab9  retn
```
