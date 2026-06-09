# CPimcManager::LoadWisptis(void)

- ea: `0x18000a49c`
- end: `0x18000a8ca`
- name: `?LoadWisptis@CPimcManager@@QEAAXXZ`
- size: `1070`
- prototype: `void __fastcall(CPimcManager *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bb20`
- `0x18000bbb0`

## callees

- `0x180001360`
- `0x18000a49c`
- `0x18000a8f0`
- `0x18000a954`
- `0x18000c198`
- `0x18000cc9c`
- `0x18000d5b8`
- `0x18000d618`
- `0x18000e0cc`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000a5f1`
- `KERNEL32!GetProcAddress` at `0x18000a604`
- `KERNEL32!GetProcAddress` at `0x18000a5f1`
- `KERNEL32!GetProcAddress` at `0x18000a604`
- `KERNEL32!GetModuleHandleW` at `0x18000a5de`
- `KERNEL32!GetModuleHandleW` at `0x18000a5de`
- `KERNEL32!WaitForSingleObject` at `0x18000a5a2`
- `KERNEL32!WaitForSingleObject` at `0x18000a6af`
- `KERNEL32!WaitForSingleObject` at `0x18000a5a2`
- `KERNEL32!WaitForSingleObject` at `0x18000a6af`
- `KERNEL32!CreateEventW` at `0x18000a555`
- `KERNEL32!CreateEventW` at `0x18000a555`
- `KERNEL32!OpenEventW` at `0x18000a519`
- `KERNEL32!OpenEventW` at `0x18000a534`
- `KERNEL32!OpenEventW` at `0x18000a519`
- `KERNEL32!OpenEventW` at `0x18000a534`
- `KERNEL32!SignalObjectAndWait` at `0x18000a57b`
- `KERNEL32!SignalObjectAndWait` at `0x18000a57b`
- `KERNEL32!IsWow64Process` at `0x18000a5cb`
- `KERNEL32!IsWow64Process` at `0x18000a5cb`
- `KERNEL32!GetCurrentProcess` at `0x18000a5be`
- `KERNEL32!GetCurrentProcess` at `0x18000a5be`
- `KERNEL32!OutputDebugStringW` at `0x18000a698`
- `KERNEL32!OutputDebugStringW` at `0x18000a698`
- `ole32!CoCreateInstance` at `0x18000a6e3`
- `ole32!CoCreateInstance` at `0x18000a785`
- `ole32!CoCreateInstance` at `0x18000a6e3`
- `ole32!CoCreateInstance` at `0x18000a785`
- `SHELL32!ShellExecuteExW` at `0x18000a664`
- `SHELL32!ShellExecuteExW` at `0x18000a664`

## string_xrefs

- `0x18000a630`: `%SystemRoot%\SYSTEM32\WISPTIS.EXE`
- `0x18000a651`: `%SystemRoot%\SYSTEM32\`

## pseudocode

```c
void __fastcall CPimcManager::LoadWisptis(CPimcManager *this)
{
  signed int v2; // ebx
  HANDLE v3; // rdi
  HANDLE EventW; // r14
  FARPROC v5; // rbx
  HANDLE CurrentProcess; // rax
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  BOOL v9; // edi
  void *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // ecx
  unsigned __int16 v13; // r8
  unsigned int v14; // r9d
  CPimcManager *v15; // rcx
  bool v16; // zf
  char v17; // al
  int v18; // [rsp+30h] [rbp-69h] BYREF
  char v19; // [rsp+34h] [rbp-65h]
  int v20; // [rsp+38h] [rbp-61h]
  char v21; // [rsp+3Ch] [rbp-5Dh]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v23[64]; // [rsp+B0h] [rbp+17h] BYREF
  void *Wow64Process; // [rsp+100h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+108h] [rbp+6Fh] BYREF
  void *v26; // [rsp+110h] [rbp+77h] BYREF

  v2 = 0;
  if ( (*((_BYTE *)this + 60) & 1) == 0 )
  {
    if ( (unsigned int)CPimcManager::IsVistaOrGreater(this) )
    {
      if ( dword_180018AD4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_180018AD4);
        if ( dword_180018AD4 == -1 )
        {
          if ( WPFUtils::OSVersionHelper::IsWindowsVersionOrGreater(v12, 2u, v13, v14)
            || (v16 = (unsigned int)CPimcManager::UserIsLocalSystem(v15) == 0, v17 = 0, v16) )
          {
            v17 = 1;
          }
          byte_180018AD8 = v17;
          Init_thread_footer(&dword_180018AD4);
        }
      }
      if ( byte_180018AD8 )
      {
        v3 = OpenEventW(2u, 0, L"{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-request");
        Wow64Process = v3;
        EventW = OpenEventW(0x100000u, 0, L"{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-running");
        v26 = EventW;
        if ( !EventW )
        {
          EventW = CreateEventW(0, 1, 0, L"{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-running");
          v26 = EventW;
        }
        if ( v3 && EventW )
          v2 = SignalObjectAndWait(v3, EventW, 0x7530u, 0) != 0 ? 0x80004005 : 0;
        SafeCloseHandle(&Wow64Process);
        if ( v2 >= 0 && EventW && WaitForSingleObject(EventW, 0) != 258 )
          goto LABEL_19;
        ppv = 0;
        LODWORD(Wow64Process) = 0;
        v5 = 0;
        CurrentProcess = GetCurrentProcess();
        IsWow64Process(CurrentProcess, (PBOOL)&Wow64Process);
        if ( (_DWORD)Wow64Process )
        {
          ModuleHandleW = GetModuleHandleW(L"KERNEL32");
          ProcAddress = GetProcAddress(ModuleHandleW, "Wow64DisableWow64FsRedirection");
          v5 = GetProcAddress(ModuleHandleW, "Wow64RevertWow64FsRedirection");
          ((void (__fastcall *)(LPVOID *))ProcAddress)(&ppv);
        }
        memset_0(&pExecInfo, 0, sizeof(pExecInfo));
        pExecInfo.cbSize = 112;
        pExecInfo.lpFile = L"%SystemRoot%\\SYSTEM32\\WISPTIS.EXE";
        pExecInfo.lpParameters = L"/ManualLaunch;";
        pExecInfo.lpVerb = 0;
        pExecInfo.fMask = 1792;
        pExecInfo.lpDirectory = L"%SystemRoot%\\SYSTEM32\\";
        pExecInfo.hInstApp = 0;
        v9 = ShellExecuteExW(&pExecInfo);
        if ( (_DWORD)Wow64Process )
          ((void (__fastcall *)(LPVOID))v5)(ppv);
        v2 = !v9 ? 0x80004005 : 0;
        if ( v9 )
        {
LABEL_19:
          if ( EventW )
            WaitForSingleObject(EventW, 0x7530u);
        }
        else
        {
          OutputDebugStringW(L"PimcManager::LoadWisptis failed to ShellExecuteEx.\r\n");
        }
        SafeCloseHandle(&v26);
        if ( v2 >= 0
          && CoCreateInstance(
               &CLSID_TabletManagerS,
               0,
               0x17u,
               &GUID_764de8aa_1867_47c1_8f6a_122445abd89a,
               (LPVOID *)this + 4) >= 0 )
        {
          ppv = &Wow64Process;
          v18 = 1;
          v19 = 0;
          v20 = 0;
          v21 = 1;
          v10 = (void *)*((_QWORD *)this + 4);
          Wow64Process = v10;
          if ( v10 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
          v11 = ComUtils::GitComLockableWrapper<ITabletManager>::GitComLockableWrapper<ITabletManager>(
                  v23,
                  &Wow64Process,
                  &v18);
          *(_OWORD *)((char *)this + 40) = *(_OWORD *)v11;
          *((_DWORD *)this + 14) = *(_DWORD *)(v11 + 16);
          if ( *((_DWORD *)this + 10) )
            *((_DWORD *)this + 15) |= 1u;
        }
      }
    }
    else
    {
      ppv = 0;
      Wow64Process = 0;
      if ( CoCreateInstance(&CLSID_PimcSurrogate2, 0, 4u, &GUID_049c5c49_baf0_429c_8b8f_2cc11f5aa422, &ppv) >= 0 )
      {
        if ( ppv )
        {
          if ( (*(int (__fastcall **)(LPVOID, void **))(*(_QWORD *)ppv + 24LL))(ppv, &Wow64Process) >= 0 )
          {
            if ( (**(int (__fastcall ***)(void *, GUID *, char *))Wow64Process)(
                   Wow64Process,
                   &IID_ITabletManager,
                   (char *)this + 32) >= 0 )
            {
              *((_DWORD *)this + 15) |= 1u;
              if ( Wow64Process )
                (*(void (__fastcall **)(void *))(*(_QWORD *)Wow64Process + 16LL))(Wow64Process);
            }
            else if ( Wow64Process )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)Wow64Process + 16LL))(Wow64Process);
            }
          }
          else if ( Wow64Process )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)Wow64Process + 16LL))(Wow64Process);
          }
        }
        else if ( Wow64Process )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)Wow64Process + 16LL))(Wow64Process);
        }
      }
      else if ( Wow64Process )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)Wow64Process + 16LL))(Wow64Process);
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x18000a49c  mov     [rsp-8+arg_18], rbx
0x18000a4a1  push    rbp
0x18000a4a2  push    rsi
0x18000a4a3  push    rdi
0x18000a4a4  push    r14
0x18000a4a6  push    r15
0x18000a4a8  lea     rbp, [rsp-37h]
0x18000a4ad  sub     rsp, 0D0h
0x18000a4b4  mov     rsi, rcx
0x18000a4b7  xor     r15d, r15d
0x18000a4ba  mov     ebx, r15d
0x18000a4bd  test    byte ptr [rcx+3Ch], 1
0x18000a4c1  jnz     loc_18000A867
0x18000a4c7  call    ?IsVistaOrGreater@CPimcManager@@QEAAHXZ; CPimcManager::IsVistaOrGreater(void)
0x18000a4cc  test    eax, eax
0x18000a4ce  jz      loc_18000A760
0x18000a4d4  mov     ecx, cs:_tls_index
0x18000a4da  mov     rax, gs:58h
0x18000a4e3  mov     r8d, 4
0x18000a4e9  mov     rdx, [rax+rcx*8]
0x18000a4ed  lea     edi, [r15+2]
0x18000a4f1  mov     eax, [r8+rdx]
0x18000a4f5  cmp     cs:dword_180018AD4, eax
0x18000a4fb  jg      loc_18000A895
0x18000a501  cmp     cs:byte_180018AD8, r15b
0x18000a508  jz      loc_18000A867
0x18000a50e  lea     r8, Name; "{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-"...
0x18000a515  xor     edx, edx; bInheritHandle
0x18000a517  mov     ecx, edi; dwDesiredAccess
0x18000a519  call    cs:__imp_OpenEventW
0x18000a51f  mov     rdi, rax
0x18000a522  mov     [rbp+57h+Wow64Process], rax
0x18000a526  lea     r8, a773f1b9a35b94e_0; "{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-"...
0x18000a52d  xor     edx, edx; bInheritHandle
0x18000a52f  mov     ecx, 100000h; dwDesiredAccess
0x18000a534  call    cs:__imp_OpenEventW
0x18000a53a  mov     r14, rax
0x18000a53d  mov     [rbp+57h+arg_10], rax
0x18000a541  test    rax, rax
0x18000a544  jnz     short loc_18000A562
0x18000a546  lea     r9, a773f1b9a35b94e_0; "{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-"...
0x18000a54d  xor     r8d, r8d; bInitialState
0x18000a550  lea     edx, [rax+1]; bManualReset
0x18000a553  xor     ecx, ecx; lpEventAttributes
0x18000a555  call    cs:__imp_CreateEventW
0x18000a55b  mov     r14, rax
0x18000a55e  mov     [rbp+57h+arg_10], rax
0x18000a562  test    rdi, rdi
0x18000a565  jz      short loc_18000A58B
0x18000a567  test    r14, r14
0x18000a56a  jz      short loc_18000A58B
0x18000a56c  xor     r9d, r9d; bAlertable
0x18000a56f  mov     r8d, 7530h; dwMilliseconds
0x18000a575  mov     rdx, r14; hObjectToWaitOn
0x18000a578  mov     rcx, rdi; hObjectToSignal
0x18000a57b  call    cs:__imp_SignalObjectAndWait
0x18000a581  neg     eax
0x18000a583  sbb     ebx, ebx
0x18000a585  and     ebx, 80004005h
0x18000a58b  lea     rcx, [rbp+57h+Wow64Process]; void **
0x18000a58f  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000a594  test    ebx, ebx
0x18000a596  js      short loc_18000A5B3
0x18000a598  test    r14, r14
0x18000a59b  jz      short loc_18000A5B3
0x18000a59d  xor     edx, edx; dwMilliseconds
0x18000a59f  mov     rcx, r14; hHandle
0x18000a5a2  call    cs:__imp_WaitForSingleObject
0x18000a5a8  cmp     eax, 102h
0x18000a5ad  jnz     loc_18000A6A2
0x18000a5b3  mov     [rbp+57h+arg_8], r15
0x18000a5b7  mov     dword ptr [rbp+57h+Wow64Process], r15d
0x18000a5bb  mov     rbx, r15
0x18000a5be  call    cs:__imp_GetCurrentProcess
0x18000a5c4  mov     rcx, rax; hProcess
0x18000a5c7  lea     rdx, [rbp+57h+Wow64Process]; Wow64Process
0x18000a5cb  call    cs:__imp_IsWow64Process
0x18000a5d1  cmp     dword ptr [rbp+57h+Wow64Process], r15d
0x18000a5d5  jz      short loc_18000A61A
0x18000a5d7  lea     rcx, aKernel32; "KERNEL32"
0x18000a5de  call    cs:__imp_GetModuleHandleW
0x18000a5e4  mov     rbx, rax
0x18000a5e7  lea     rdx, aWow64disablewo; "Wow64DisableWow64FsRedirection"
0x18000a5ee  mov     rcx, rax; hModule
0x18000a5f1  call    cs:__imp_GetProcAddress
0x18000a5f7  mov     rdi, rax
0x18000a5fa  lea     rdx, aWow64revertwow; "Wow64RevertWow64FsRedirection"
0x18000a601  mov     rcx, rbx; hModule
0x18000a604  call    cs:__imp_GetProcAddress
0x18000a60a  mov     rbx, rax
0x18000a60d  lea     rcx, [rbp+57h+arg_8]
0x18000a611  mov     rax, rdi
0x18000a614  call    cs:__guard_dispatch_icall_fptr
0x18000a61a  mov     edi, 70h ; 'p'
0x18000a61f  mov     r8d, edi; Size
0x18000a622  xor     edx, edx; Val
0x18000a624  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18000a628  call    memset_0
0x18000a62d  mov     [rbp+57h+pExecInfo.cbSize], edi
0x18000a630  lea     rax, aSystemrootSyst_0; "%SystemRoot%\\SYSTEM32\\WISPTIS.EXE"
0x18000a637  mov     [rbp+57h+pExecInfo.lpFile], rax
0x18000a63b  lea     rax, aManuallaunch; "/ManualLaunch;"
0x18000a642  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x18000a646  mov     [rbp+57h+pExecInfo.lpVerb], r15
0x18000a64a  mov     [rbp+57h+pExecInfo.fMask], 700h
0x18000a651  lea     rax, aSystemrootSyst; "%SystemRoot%\\SYSTEM32\\"
0x18000a658  mov     [rbp+57h+pExecInfo.lpDirectory], rax
0x18000a65c  mov     [rbp+57h+pExecInfo.hInstApp], r15
0x18000a660  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18000a664  call    cs:__imp_ShellExecuteExW
0x18000a66a  mov     edi, eax
0x18000a66c  cmp     dword ptr [rbp+57h+Wow64Process], r15d
0x18000a670  jz      short loc_18000A67F
0x18000a672  mov     rcx, [rbp+57h+arg_8]
0x18000a676  mov     rax, rbx
0x18000a679  call    cs:__guard_dispatch_icall_fptr
0x18000a67f  mov     ecx, edi
0x18000a681  neg     ecx
0x18000a683  sbb     ebx, ebx
0x18000a685  not     ebx
0x18000a687  and     ebx, 80004005h
0x18000a68d  test    edi, edi
0x18000a68f  jnz     short loc_18000A69E
0x18000a691  lea     rcx, OutputString; "PimcManager::LoadWisptis failed to Shel"...
0x18000a698  call    cs:__imp_OutputDebugStringW
0x18000a69e  test    ebx, ebx
0x18000a6a0  js      short loc_18000A6B5
0x18000a6a2  test    r14, r14
0x18000a6a5  jz      short loc_18000A6B5
0x18000a6a7  mov     edx, 7530h; dwMilliseconds
0x18000a6ac  mov     rcx, r14; hHandle
0x18000a6af  call    cs:__imp_WaitForSingleObject
0x18000a6b5  lea     rcx, [rbp+57h+arg_10]; void **
0x18000a6b9  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000a6be  test    ebx, ebx
0x18000a6c0  js      loc_18000A867
0x18000a6c6  lea     rbx, [rsi+20h]
0x18000a6ca  mov     [rsp+0F0h+ppv], rbx; ppv
0x18000a6cf  lea     r9, _GUID_764de8aa_1867_47c1_8f6a_122445abd89a; riid
0x18000a6d6  xor     edx, edx; pUnkOuter
0x18000a6d8  lea     r8d, [rdx+17h]; dwClsContext
0x18000a6dc  lea     rcx, CLSID_TabletManagerS; rclsid
0x18000a6e3  call    cs:__imp_CoCreateInstance
0x18000a6e9  test    eax, eax
0x18000a6eb  js      loc_18000A867
0x18000a6f1  lea     rax, [rbp+57h+Wow64Process]
0x18000a6f5  mov     [rbp+57h+arg_8], rax
0x18000a6f9  mov     dword ptr [rbp+57h+var_C0], 1
0x18000a700  mov     byte ptr [rbp+57h+var_C0+4], r15b
0x18000a704  mov     dword ptr [rbp+57h+var_C0+8], r15d
0x18000a708  mov     byte ptr [rbp+57h+var_C0+0Ch], 1
0x18000a70c  movaps  xmm0, [rbp+57h+var_C0]
0x18000a710  movdqa  [rbp+57h+var_C0], xmm0
0x18000a715  mov     rcx, [rbx]
0x18000a718  mov     [rbp+57h+Wow64Process], rcx
0x18000a71c  test    rcx, rcx
0x18000a71f  jz      short loc_18000A72F
0x18000a721  mov     rax, [rcx]
0x18000a724  mov     rax, [rax+8]
0x18000a728  call    cs:__guard_dispatch_icall_fptr
0x18000a72e  nop
0x18000a72f  lea     r8, [rbp+57h+var_C0]
0x18000a733  lea     rdx, [rbp+57h+Wow64Process]
0x18000a737  lea     rcx, [rbp+57h+var_40]
0x18000a73b  call    ??0?$GitComLockableWrapper@UITabletManager@@@ComUtils@@QEAA@V?$CComPtr@UITabletManager@@@ATL@@VComApartmentVerifier@1@@Z; ComUtils::GitComLockableWrapper<ITabletManager>::GitComLockableWrapper<ITabletManager>(ATL::CComPtr<ITabletManager>,ComUtils::ComApartmentVerifier)
0x18000a740  movups  xmm0, xmmword ptr [rax]
0x18000a743  movups  xmmword ptr [rsi+28h], xmm0
0x18000a747  mov     eax, [rax+10h]
0x18000a74a  mov     [rsi+38h], eax
0x18000a74d  cmp     [rsi+28h], r15d
0x18000a751  jz      loc_18000A867
0x18000a757  or      dword ptr [rsi+3Ch], 1
0x18000a75b  jmp     loc_18000A867
0x18000a760  mov     [rbp+57h+arg_8], r15
0x18000a764  mov     [rbp+57h+Wow64Process], r15
0x18000a768  lea     rax, [rbp+57h+arg_8]
0x18000a76c  mov     [rsp+0F0h+ppv], rax; ppv
0x18000a771  lea     r9, _GUID_049c5c49_baf0_429c_8b8f_2cc11f5aa422; riid
0x18000a778  xor     edx, edx; pUnkOuter
0x18000a77a  lea     r8d, [rdx+4]; dwClsContext
0x18000a77e  lea     rcx, CLSID_PimcSurrogate2; rclsid
0x18000a785  call    cs:__imp_CoCreateInstance
0x18000a78b  test    eax, eax
0x18000a78d  jns     short loc_18000A7AB
0x18000a78f  mov     rcx, [rbp+57h+Wow64Process]
0x18000a793  test    rcx, rcx
0x18000a796  jz      short loc_18000A7A6
0x18000a798  mov     rax, [rcx]
0x18000a79b  mov     rax, [rax+10h]
0x18000a79f  call    cs:__guard_dispatch_icall_fptr
0x18000a7a5  nop
0x18000a7a6  jmp     loc_18000A851
0x18000a7ab  mov     rcx, [rbp+57h+arg_8]
0x18000a7af  test    rcx, rcx
0x18000a7b2  jnz     short loc_18000A7D0
0x18000a7b4  mov     rcx, [rbp+57h+Wow64Process]
0x18000a7b8  test    rcx, rcx
0x18000a7bb  jz      short loc_18000A7CB
0x18000a7bd  mov     rax, [rcx]
0x18000a7c0  mov     rax, [rax+10h]
0x18000a7c4  call    cs:__guard_dispatch_icall_fptr
0x18000a7ca  nop
0x18000a7cb  jmp     loc_18000A851
0x18000a7d0  mov     rax, [rcx]
0x18000a7d3  lea     rdx, [rbp+57h+Wow64Process]
0x18000a7d7  mov     rax, [rax+18h]
0x18000a7db  call    cs:__guard_dispatch_icall_fptr
0x18000a7e1  test    eax, eax
0x18000a7e3  jns     short loc_18000A7FE
0x18000a7e5  mov     rcx, [rbp+57h+Wow64Process]
0x18000a7e9  test    rcx, rcx
0x18000a7ec  jz      short loc_18000A7FC
0x18000a7ee  mov     rax, [rcx]
0x18000a7f1  mov     rax, [rax+10h]
0x18000a7f5  call    cs:__guard_dispatch_icall_fptr
0x18000a7fb  nop
0x18000a7fc  jmp     short loc_18000A851
0x18000a7fe  mov     rcx, [rbp+57h+Wow64Process]
0x18000a802  mov     rax, [rcx]
0x18000a805  lea     r8, [rsi+20h]
0x18000a809  lea     rdx, IID_ITabletManager
0x18000a810  mov     rax, [rax]
0x18000a813  call    cs:__guard_dispatch_icall_fptr
0x18000a819  test    eax, eax
0x18000a81b  jns     short loc_18000A836
0x18000a81d  mov     rcx, [rbp+57h+Wow64Process]
0x18000a821  test    rcx, rcx
0x18000a824  jz      short loc_18000A834
0x18000a826  mov     rax, [rcx]
0x18000a829  mov     rax, [rax+10h]
0x18000a82d  call    cs:__guard_dispatch_icall_fptr
0x18000a833  nop
0x18000a834  jmp     short loc_18000A851
0x18000a836  or      dword ptr [rsi+3Ch], 1
0x18000a83a  mov     rcx, [rbp+57h+Wow64Process]
0x18000a83e  test    rcx, rcx
0x18000a841  jz      short loc_18000A851
0x18000a843  mov     rax, [rcx]
0x18000a846  mov     rax, [rax+10h]
0x18000a84a  call    cs:__guard_dispatch_icall_fptr
0x18000a850  nop
0x18000a851  mov     rcx, [rbp+57h+arg_8]
0x18000a855  test    rcx, rcx
0x18000a858  jz      short loc_18000A867
0x18000a85a  mov     rax, [rcx]
0x18000a85d  mov     rax, [rax+10h]
0x18000a861  call    cs:__guard_dispatch_icall_fptr
0x18000a867  mov     rbx, [rsp+0F0h+arg_18]
0x18000a86f  add     rsp, 0D0h
0x18000a876  pop     r15
0x18000a878  pop     r14
0x18000a87a  pop     rdi
0x18000a87b  pop     rsi
0x18000a87c  pop     rbp
0x18000a87d  retn
0x18000a87e  mov     cs:byte_180018AD8, al
0x18000a884  lea     rcx, dword_180018AD4
0x18000a88b  call    _Init_thread_footer
0x18000a890  jmp     loc_18000A501
0x18000a895  lea     rcx, dword_180018AD4
0x18000a89c  call    _Init_thread_header
0x18000a8a1  cmp     cs:dword_180018AD4, 0FFFFFFFFh
0x18000a8a8  jnz     loc_18000A501
0x18000a8ae  mov     edx, edi; unsigned int
0x18000a8b0  call    ?IsWindowsVersionOrGreater@OSVersionHelper@WPFUtils@@CA_NKKGK@Z; WPFUtils::OSVersionHelper::IsWindowsVersionOrGreater(ulong,ulong,ushort,ulong)
0x18000a8b5  test    al, al
0x18000a8b7  jnz     short loc_18000A8C5
0x18000a8b9  call    ?UserIsLocalSystem@CPimcManager@@IEAAHXZ; CPimcManager::UserIsLocalSystem(void)
0x18000a8be  test    eax, eax
0x18000a8c0  mov     al, r15b
0x18000a8c3  jnz     short loc_18000A87E
0x18000a8c5  mov     al, 1
0x18000a8c7  jmp     short loc_18000A87E
```
