# CUHHandlerManager::RegisterRemoteHandlerServer(IUnknown *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180017850`
- end: `0x180017b7d`
- name: `?RegisterRemoteHandlerServer@CUHHandlerManager@@UEAAJPEAUIUnknown@@PEA_K1@Z`
- size: `813`
- prototype: `int(CUHHandlerManager *__hidden this, struct IUnknown *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000b554`
- `0x18000c0ac`
- `0x1800110fc`
- `0x180017850`
- `0x180018124`
- `0x180019644`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017a75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017ac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017a75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017ac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017aca`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180017935`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180017935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800178ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800178ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b36`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017a9a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017aef`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017a9a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180017aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b58`

## string_xrefs

- `0x1800178ce`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017a44`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017b02`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUHHandlerManager::RegisterRemoteHandlerServer(
        CUHHandlerManager *this,
        struct IUnknown *a2,
        HANDLE *a3,
        HANDLE *a4)
{
  __int64 v8; // rdx
  int IsProcessILAtleastHigh; // edi
  char *v10; // rbx
  __int64 v11; // rdx
  RPC_STATUS v12; // eax
  CUHHandlerManager *v13; // rcx
  DWORD v14; // edx
  __int64 v15; // rdx
  int *v16; // r8
  void *v17; // rdi
  void *v18; // rsi
  HANDLE CurrentProcess; // rax
  const char *v20; // r9
  __int64 v21; // rdx
  void *v22; // rsi
  HANDLE v23; // rdi
  HANDLE v24; // rax
  int dwDesiredAccess; // [rsp+20h] [rbp-48h]
  int v27; // [rsp+40h] [rbp-28h] BYREF
  unsigned int Pid; // [rsp+44h] [rbp-24h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  hObject = 0;
  TargetHandle = 0;
  Pid = 0;
  v27 = 0;
  if ( !a2 )
  {
    v8 = 448;
LABEL_7:
    IsProcessILAtleastHigh = -2147467261;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)IsProcessILAtleastHigh,
      dwDesiredAccess);
    goto LABEL_50;
  }
  if ( !a3 )
  {
    v8 = 449;
    goto LABEL_7;
  }
  if ( !a4 )
  {
    v8 = 450;
    goto LABEL_7;
  }
  if ( !*((_BYTE *)this + 40) )
  {
    IsProcessILAtleastHigh = -2145124348;
    v8 = 451;
    goto LABEL_10;
  }
  v10 = (char *)this + 56;
  if ( this != (CUHHandlerManager *)-56LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_QWORD *)this + 6) )
  {
    v11 = 456;
LABEL_17:
    IsProcessILAtleastHigh = -2147024891;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)IsProcessILAtleastHigh,
      dwDesiredAccess);
    goto LABEL_48;
  }
  if ( !*((_QWORD *)this + 40) )
  {
    v11 = 457;
    goto LABEL_17;
  }
  IsProcessILAtleastHigh = CUHHandlerManager::SecurityCheck(this, (unsigned int)a2);
  if ( IsProcessILAtleastHigh < 0 )
  {
    v11 = 459;
    goto LABEL_37;
  }
  v12 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v12 == 120 )
  {
    v14 = Pid;
  }
  else
  {
    if ( v12 )
    {
      IsProcessILAtleastHigh = -2147024891;
      v11 = 467;
      goto LABEL_37;
    }
    v14 = Pid;
    if ( !Pid )
    {
      IsProcessILAtleastHigh = -2147024891;
      v11 = 468;
      goto LABEL_37;
    }
    if ( Pid != *((_DWORD *)this + 86) )
    {
      WUTrace("CUHHandlerManager::RegisterRemoteHandlerServer", 469, 32, 3, 0, L"TelemetryAssert (%ws): %ws");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      v14 = Pid;
      if ( Pid != *((_DWORD *)this + 86) )
      {
        IsProcessILAtleastHigh = -2147024891;
        v11 = 470;
        goto LABEL_37;
      }
    }
  }
  IsProcessILAtleastHigh = CUHHandlerManager::IsProcessILAtleastHigh(v13, v14, &v27);
  if ( IsProcessILAtleastHigh < 0 )
  {
    v11 = 474;
    goto LABEL_37;
  }
  if ( !v27 )
  {
    IsProcessILAtleastHigh = -2147024891;
    v11 = 476;
    goto LABEL_37;
  }
  IsProcessILAtleastHigh = SetProxyBlanketImpersonationLevel(a2, v15, v16);
  if ( IsProcessILAtleastHigh < 0 )
  {
    v11 = 487;
    goto LABEL_37;
  }
  IsProcessILAtleastHigh = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
                             a2,
                             &GUID_9920c724_c8ba_4035_9d4a_1956536dc6f9,
                             (char *)this + 48);
  if ( IsProcessILAtleastHigh < 0 )
  {
    v11 = 491;
    goto LABEL_37;
  }
  if ( hObject )
    CloseHandle(hObject);
  v17 = (void *)*((_QWORD *)this + 40);
  v18 = (void *)*((_QWORD *)this + 41);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v18, v17, &hObject, 2u, 0, 0) )
  {
    v21 = 501;
LABEL_46:
    IsProcessILAtleastHigh = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)v21,
                               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                               v20);
    goto LABEL_48;
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  v22 = (void *)*((_QWORD *)this + 40);
  v23 = GetCurrentProcess();
  v24 = GetCurrentProcess();
  if ( !DuplicateHandle(v24, v23, v22, &TargetHandle, 0x100400u, 0, 0) )
  {
    v21 = 511;
    goto LABEL_46;
  }
  IsProcessILAtleastHigh = 0;
  *a3 = hObject;
  *a4 = TargetHandle;
  hObject = 0;
  TargetHandle = 0;
LABEL_48:
  if ( v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
LABEL_50:
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)IsProcessILAtleastHigh;
}

```

## disassembly

```asm
0x180017850  push    rbp
0x180017852  push    rbx
0x180017853  push    rsi
0x180017854  push    rdi
0x180017855  push    r12
0x180017857  push    r13
0x180017859  push    r14
0x18001785b  push    r15
0x18001785d  mov     rbp, rsp
0x180017860  sub     rsp, 68h
0x180017864  mov     rax, cs:__security_cookie
0x18001786b  xor     rax, rsp
0x18001786e  mov     [rbp+var_10], rax
0x180017872  xor     r15d, r15d
0x180017875  mov     r13, r9
0x180017878  mov     [rbp+hObject], r15
0x18001787c  mov     r12, r8
0x18001787f  mov     [rbp+TargetHandle], r15
0x180017883  mov     rsi, rdx
0x180017886  mov     [rbp+Pid], r15d
0x18001788a  mov     r14, rcx
0x18001788d  mov     [rbp+var_28], r15d
0x180017891  test    rdx, rdx
0x180017894  jnz     short loc_18001789D
0x180017896  mov     edx, 1C0h
0x18001789b  jmp     short loc_1800178B3
0x18001789d  test    r12, r12
0x1800178a0  jnz     short loc_1800178A9
0x1800178a2  mov     edx, 1C1h
0x1800178a7  jmp     short loc_1800178B3
0x1800178a9  test    r13, r13
0x1800178ac  jnz     short loc_1800178BA
0x1800178ae  mov     edx, 1C2h
0x1800178b3  mov     edi, 80004003h
0x1800178b8  jmp     short loc_1800178CA
0x1800178ba  cmp     [rcx+28h], r15b
0x1800178be  jnz     short loc_1800178E2
0x1800178c0  mov     edi, 80240004h
0x1800178c5  mov     edx, 1C3h; void *
0x1800178ca  mov     rcx, [rbp+40h]; this
0x1800178ce  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800178d5  mov     r9d, edi; char *
0x1800178d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178dd  jmp     loc_180017B3C
0x1800178e2  lea     rbx, [rcx+38h]
0x1800178e6  test    rbx, rbx
0x1800178e9  jz      short loc_1800178F5
0x1800178eb  lea     rcx, [rbx+8]; lpCriticalSection
0x1800178ef  call    cs:__imp_EnterCriticalSection
0x1800178f5  cmp     [r14+30h], r15
0x1800178f9  jz      short loc_180017902
0x1800178fb  mov     edx, 1C8h
0x180017900  jmp     short loc_180017910
0x180017902  cmp     [r14+140h], r15
0x180017909  jnz     short loc_18001791A
0x18001790b  mov     edx, 1C9h
0x180017910  mov     edi, 80070005h
0x180017915  jmp     loc_180017A40
0x18001791a  call    ?SecurityCheck@CUHHandlerManager@@AEAAJK@Z; CUHHandlerManager::SecurityCheck(ulong)
0x18001791f  mov     edi, eax
0x180017921  test    eax, eax
0x180017923  jns     short loc_18001792F
0x180017925  mov     edx, 1CBh
0x18001792a  jmp     loc_180017A40
0x18001792f  lea     rdx, [rbp+Pid]; Pid
0x180017933  xor     ecx, ecx; Binding
0x180017935  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001793b  cmp     eax, 78h ; 'x'
0x18001793e  jz      loc_1800179DC
0x180017944  test    eax, eax
0x180017946  jz      short loc_180017957
0x180017948  mov     edi, 80070005h
0x18001794d  mov     edx, 1D3h
0x180017952  jmp     loc_180017A40
0x180017957  mov     edx, [rbp+Pid]
0x18001795a  test    edx, edx
0x18001795c  jnz     short loc_18001796D
0x18001795e  mov     edi, 80070005h
0x180017963  mov     edx, 1D4h
0x180017968  jmp     loc_180017A40
0x18001796d  cmp     edx, [r14+158h]
0x180017974  jz      short loc_1800179DF
0x180017976  lea     rax, aAtteptMadeToRe; "Attept made to register from unknown PI"...
0x18001797d  mov     r9d, 3
0x180017983  mov     [rsp+68h+var_30], rax
0x180017988  lea     rcx, aCuhhandlermana; "CUHHandlerManager::RegisterRemoteHandle"...
0x18001798f  lea     rax, aUlpidMUlpidrem; "ulPID == m_ulPIDRemote"
0x180017996  mov     edx, 1D5h
0x18001799b  mov     qword ptr [rsp+68h+dwOptions], rax
0x1800179a0  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x1800179a7  mov     qword ptr [rsp+68h+bInheritHandle], rax
0x1800179ac  lea     r8d, [r9+1Dh]
0x1800179b0  mov     qword ptr [rsp+68h+dwDesiredAccess], r15
0x1800179b5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800179ba  or      ecx, 0FFFFFFFFh; unsigned int
0x1800179bd  mov     edx, ecx; unsigned int
0x1800179bf  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x1800179c4  mov     edx, [rbp+Pid]
0x1800179c7  cmp     edx, [r14+158h]
0x1800179ce  jz      short loc_1800179DF
0x1800179d0  mov     edi, 80070005h
0x1800179d5  mov     edx, 1D6h
0x1800179da  jmp     short loc_180017A40
0x1800179dc  mov     edx, [rbp+Pid]; unsigned int
0x1800179df  lea     r8, [rbp+var_28]; int *
0x1800179e3  call    ?IsProcessILAtleastHigh@CUHHandlerManager@@QEAAJKPEAH@Z; CUHHandlerManager::IsProcessILAtleastHigh(ulong,int *)
0x1800179e8  mov     edi, eax
0x1800179ea  test    eax, eax
0x1800179ec  jns     short loc_1800179F5
0x1800179ee  mov     edx, 1DAh
0x1800179f3  jmp     short loc_180017A40
0x1800179f5  cmp     [rbp+var_28], r15d
0x1800179f9  jnz     short loc_180017A07
0x1800179fb  mov     edi, 80070005h
0x180017a00  mov     edx, 1DCh
0x180017a05  jmp     short loc_180017A40
0x180017a07  mov     rcx, rsi; struct IUnknown *
0x180017a0a  call    ?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z; SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)
0x180017a0f  mov     edi, eax
0x180017a11  test    eax, eax
0x180017a13  jns     short loc_180017A1C
0x180017a15  mov     edx, 1E7h
0x180017a1a  jmp     short loc_180017A40
0x180017a1c  mov     rax, [rsi]
0x180017a1f  lea     r8, [r14+30h]
0x180017a23  lea     rdx, _GUID_9920c724_c8ba_4035_9d4a_1956536dc6f9
0x180017a2a  mov     rcx, rsi
0x180017a2d  mov     rax, [rax]
0x180017a30  call    _guard_dispatch_icall
0x180017a35  mov     edi, eax
0x180017a37  test    eax, eax
0x180017a39  jns     short loc_180017A58
0x180017a3b  mov     edx, 1EBh; void *
0x180017a40  mov     rcx, [rbp+40h]; this
0x180017a44  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017a4b  mov     r9d, edi; char *
0x180017a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a53  jmp     loc_180017B2D
0x180017a58  mov     rcx, [rbp+hObject]; hObject
0x180017a5c  test    rcx, rcx
0x180017a5f  jz      short loc_180017A67
0x180017a61  call    cs:__imp_CloseHandle
0x180017a67  mov     rdi, [r14+140h]
0x180017a6e  mov     rsi, [r14+148h]
0x180017a75  call    cs:__imp_GetCurrentProcess
0x180017a7b  mov     [rsp+68h+dwOptions], r15d; dwOptions
0x180017a80  lea     r9, [rbp+hObject]; lpTargetHandle
0x180017a84  mov     rcx, rax; hSourceProcessHandle
0x180017a87  mov     [rsp+68h+bInheritHandle], r15d; bInheritHandle
0x180017a8c  mov     r8, rdi; hTargetProcessHandle
0x180017a8f  mov     [rsp+68h+dwDesiredAccess], 2; dwDesiredAccess
0x180017a97  mov     rdx, rsi; hSourceHandle
0x180017a9a  call    cs:__imp_DuplicateHandle
0x180017aa0  test    eax, eax
0x180017aa2  jnz     short loc_180017AAB
0x180017aa4  mov     edx, 1F5h
0x180017aa9  jmp     short loc_180017AFE
0x180017aab  mov     rcx, [rbp+TargetHandle]; hObject
0x180017aaf  test    rcx, rcx
0x180017ab2  jz      short loc_180017ABA
0x180017ab4  call    cs:__imp_CloseHandle
0x180017aba  mov     rsi, [r14+140h]
0x180017ac1  call    cs:__imp_GetCurrentProcess
0x180017ac7  mov     rdi, rax
0x180017aca  call    cs:__imp_GetCurrentProcess
0x180017ad0  mov     [rsp+68h+dwOptions], r15d; dwOptions
0x180017ad5  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180017ad9  mov     rcx, rax; hSourceProcessHandle
0x180017adc  mov     [rsp+68h+bInheritHandle], r15d; bInheritHandle
0x180017ae1  mov     r8, rsi; hTargetProcessHandle
0x180017ae4  mov     [rsp+68h+dwDesiredAccess], 100400h; dwDesiredAccess
0x180017aec  mov     rdx, rdi; hSourceHandle
0x180017aef  call    cs:__imp_DuplicateHandle
0x180017af5  test    eax, eax
0x180017af7  jnz     short loc_180017B12
0x180017af9  mov     edx, 1FFh; void *
0x180017afe  mov     rcx, [rbp+40h]; this
0x180017b02  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017b09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017b0e  mov     edi, eax
0x180017b10  jmp     short loc_180017B2D
0x180017b12  mov     rax, [rbp+hObject]
0x180017b16  mov     edi, r15d
0x180017b19  mov     [r12], rax
0x180017b1d  mov     rax, [rbp+TargetHandle]
0x180017b21  mov     [r13+0], rax
0x180017b25  mov     [rbp+hObject], r15
0x180017b29  mov     [rbp+TargetHandle], r15
0x180017b2d  test    rbx, rbx
0x180017b30  jz      short loc_180017B3C
0x180017b32  lea     rcx, [rbx+8]; lpCriticalSection
0x180017b36  call    cs:__imp_LeaveCriticalSection
0x180017b3c  mov     rcx, [rbp+TargetHandle]; hObject
0x180017b40  test    rcx, rcx
0x180017b43  jz      short loc_180017B4F
0x180017b45  call    cs:__imp_CloseHandle
0x180017b4b  mov     [rbp+TargetHandle], r15
0x180017b4f  mov     rcx, [rbp+hObject]; hObject
0x180017b53  test    rcx, rcx
0x180017b56  jz      short loc_180017B5E
0x180017b58  call    cs:__imp_CloseHandle
0x180017b5e  mov     eax, edi
0x180017b60  mov     rcx, [rbp+var_10]
0x180017b64  xor     rcx, rsp; StackCookie
0x180017b67  call    __security_check_cookie
0x180017b6c  add     rsp, 68h
0x180017b70  pop     r15
0x180017b72  pop     r14
0x180017b74  pop     r13
0x180017b76  pop     r12
0x180017b78  pop     rdi
0x180017b79  pop     rsi
0x180017b7a  pop     rbx
0x180017b7b  pop     rbp
0x180017b7c  retn
```
