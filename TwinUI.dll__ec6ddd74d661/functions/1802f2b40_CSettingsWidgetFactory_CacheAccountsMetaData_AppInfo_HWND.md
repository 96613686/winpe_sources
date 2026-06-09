# CSettingsWidgetFactory::CacheAccountsMetaData(AppInfo *,HWND__ * *)

- ea: `0x1802f2b40`
- end: `0x1802f2da7`
- name: `?CacheAccountsMetaData@CSettingsWidgetFactory@@SAJPEAVAppInfo@@PEAPEAUHWND__@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(struct AppInfo *, HWND *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802f0198`

## callees

- `0x180009dd0`
- `0x18002fc18`
- `0x1800831f0`
- `0x1800a0f20`
- `0x1802f29fc`
- `0x1802f2b40`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f2c16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f2c16`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802f2d36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802f2d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802f2c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802f2c8d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802f2cbe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802f2cbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802f2bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802f2d15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802f2bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802f2d15`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802f2c6a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802f2c6a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802f2c55`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802f2c55`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1802f2b8d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1802f2b8d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802f2b6e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802f2b6e`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802f2be8`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802f2be8`

## pseudocode

```c
__int64 __fastcall CSettingsWidgetFactory::CacheAccountsMetaData(struct AppInfo *a1, HWND *a2)
{
  int Error; // esi
  bool v4; // zf
  HWND Ancestor; // rax
  DWORD TickCount; // r12d
  void *v8; // rbx
  HANDLE EventW; // r15
  HWND v10; // rcx
  void *v11; // rdi
  HANDLE CurrentProcess; // rax
  DWORD v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  LPARAM lParam; // [rsp+40h] [rbp-30h] BYREF
  HWND v18; // [rsp+48h] [rbp-28h]
  _BYTE Parameter[32]; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwProcessId; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE v21; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+50h] BYREF
  HANDLE TargetHandle; // [rsp+C8h] [rbp+58h] BYREF

  Error = 0;
  v4 = *((_DWORD *)a1 + 4) == 1;
  *a2 = 0;
  if ( v4 )
  {
    Ancestor = GetAncestor(*((HWND *)a1 + 3), 2u);
    v18 = 0;
    lParam = (LPARAM)Ancestor;
    EnumWindows(CheckForWABWindows, (LPARAM)&lParam);
    if ( v18 )
    {
      *a2 = v18;
      return (unsigned int)Error;
    }
    CImmersiveDebuggerAwareRPCTimeout::CImmersiveDebuggerAwareRPCTimeout(
      Parameter,
      *((const unsigned __int16 **)a1 + 22),
      0x3A98u);
    v22 = 0;
    TickCount = GetTickCount();
    Error = CoreQueryWindowService(
              *((_QWORD *)a1 + 3),
              &IID_IImmersiveAccountsSettings,
              &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
              &v22);
    if ( Error < 0 )
      goto LABEL_25;
    v8 = 0;
    TargetHandle = (HANDLE)-1LL;
    v21 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      CAutoHandle<void *>::~CAutoHandle<void *>(&v21);
      v10 = (HWND)*((_QWORD *)a1 + 3);
      v8 = EventW;
      dwProcessId = 0;
      v21 = EventW;
      GetWindowThreadProcessId(v10, &dwProcessId);
      lParam = (LPARAM)OpenProcess(0x40u, 0, dwProcessId);
      v11 = (void *)lParam;
      if ( lParam )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, EventW, v11, &TargetHandle, 2u, 0, 0) )
        Error = ResultFromKnownLastError();
      CAutoHandle<void *>::~CAutoHandle<void *>(&lParam);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    if ( Error >= 0 )
    {
      dwProcessId = 0;
      Error = (*(__int64 (__fastcall **)(__int64, _QWORD, DWORD *))(*(_QWORD *)v22 + 24LL))(
                v22,
                (unsigned int)TargetHandle,
                &dwProcessId);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)Parameter);
      if ( !dwProcessId )
      {
        v13 = GetTickCount();
        if ( Error >= 0 )
        {
          v14 = v13 - TickCount;
          if ( v14 >= 0x3A98 )
          {
LABEL_23:
            Error = -2147023436;
            goto LABEL_24;
          }
          v15 = WaitForSingleObject(v8, 15000 - v14);
          if ( v15 )
          {
            if ( v15 != 128 )
            {
              if ( v15 != 258 )
              {
                if ( v15 == -1 )
                  Error = ResultFromKnownLastError();
                else
                  Error = -2147418113;
                goto LABEL_24;
              }
              goto LABEL_23;
            }
            Error = -2147024161;
          }
        }
      }
    }
LABEL_24:
    CAutoHandle<void *>::~CAutoHandle<void *>(&v21);
LABEL_25:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)Parameter);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802f2b40  push    rbp
0x1802f2b42  push    rbx
0x1802f2b43  push    rsi
0x1802f2b44  push    rdi
0x1802f2b45  push    r12
0x1802f2b47  push    r14
0x1802f2b49  push    r15
0x1802f2b4b  mov     rbp, rsp
0x1802f2b4e  sub     rsp, 70h
0x1802f2b52  xor     esi, esi
0x1802f2b54  mov     rbx, rdx
0x1802f2b57  cmp     dword ptr [rcx+10h], 1
0x1802f2b5b  mov     rdi, rcx
0x1802f2b5e  mov     [rdx], rsi
0x1802f2b61  jnz     loc_1802F2D95
0x1802f2b67  mov     rcx, [rcx+18h]; hwnd
0x1802f2b6b  lea     edx, [rsi+2]; gaFlags
0x1802f2b6e  call    cs:__imp_GetAncestor
0x1802f2b75  nop     dword ptr [rax+rax+00h]
0x1802f2b7a  lea     rdx, [rbp+lParam]; lParam
0x1802f2b7e  mov     [rbp+var_28], rsi
0x1802f2b82  lea     rcx, CheckForWABWindows; lpEnumFunc
0x1802f2b89  mov     [rbp+lParam], rax
0x1802f2b8d  call    cs:__imp_EnumWindows
0x1802f2b94  nop     dword ptr [rax+rax+00h]
0x1802f2b99  mov     rax, [rbp+var_28]
0x1802f2b9d  test    rax, rax
0x1802f2ba0  jnz     loc_1802F2D92
0x1802f2ba6  mov     rdx, [rdi+0B0h]; unsigned __int16 *
0x1802f2bad  lea     rcx, [rbp+Parameter]; Parameter
0x1802f2bb1  mov     r14d, 3A98h
0x1802f2bb7  mov     r8d, r14d; unsigned int
0x1802f2bba  call    ??0CImmersiveDebuggerAwareRPCTimeout@@QEAA@PEBGK@Z; CImmersiveDebuggerAwareRPCTimeout::CImmersiveDebuggerAwareRPCTimeout(ushort const *,ulong)
0x1802f2bbf  mov     [rbp+arg_10], rsi
0x1802f2bc3  call    cs:__imp_GetTickCount
0x1802f2bca  nop     dword ptr [rax+rax+00h]
0x1802f2bcf  mov     rcx, [rdi+18h]
0x1802f2bd3  lea     r9, [rbp+arg_10]
0x1802f2bd7  lea     r8, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x1802f2bde  mov     r12d, eax
0x1802f2be1  lea     rdx, IID_IImmersiveAccountsSettings
0x1802f2be8  call    cs:__imp_CoreQueryWindowService
0x1802f2bef  nop     dword ptr [rax+rax+00h]
0x1802f2bf4  mov     esi, eax
0x1802f2bf6  test    eax, eax
0x1802f2bf8  js      loc_1802F2D7E
0x1802f2bfe  xor     ebx, ebx
0x1802f2c00  mov     [rbp+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x1802f2c08  xor     r9d, r9d; lpName
0x1802f2c0b  mov     [rbp+arg_8], rbx
0x1802f2c0f  xor     r8d, r8d; bInitialState
0x1802f2c12  xor     edx, edx; bManualReset
0x1802f2c14  xor     ecx, ecx; lpEventAttributes
0x1802f2c16  call    cs:__imp_CreateEventW
0x1802f2c1d  nop     dword ptr [rax+rax+00h]
0x1802f2c22  mov     r15, rax
0x1802f2c25  test    rax, rax
0x1802f2c28  jnz     short loc_1802F2C36
0x1802f2c2a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802f2c2f  mov     esi, eax
0x1802f2c31  jmp     loc_1802F2CDE
0x1802f2c36  lea     rcx, [rbp+arg_8]
0x1802f2c3a  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802f2c3f  mov     rcx, [rdi+18h]; hWnd
0x1802f2c43  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1802f2c47  mov     rbx, r15
0x1802f2c4a  mov     [rbp+dwProcessId], 0
0x1802f2c51  mov     [rbp+arg_8], rbx
0x1802f2c55  call    cs:__imp_GetWindowThreadProcessId
0x1802f2c5c  nop     dword ptr [rax+rax+00h]
0x1802f2c61  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1802f2c65  xor     edx, edx; bInheritHandle
0x1802f2c67  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1802f2c6a  call    cs:__imp_OpenProcess
0x1802f2c71  nop     dword ptr [rax+rax+00h]
0x1802f2c76  mov     [rbp+lParam], rax
0x1802f2c7a  mov     rdi, rax
0x1802f2c7d  test    rax, rax
0x1802f2c80  jz      short loc_1802F2C86
0x1802f2c82  xor     esi, esi
0x1802f2c84  jmp     short loc_1802F2C8D
0x1802f2c86  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802f2c8b  mov     esi, eax
0x1802f2c8d  call    cs:__imp_GetCurrentProcess
0x1802f2c94  nop     dword ptr [rax+rax+00h]
0x1802f2c99  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1802f2ca1  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1802f2ca5  mov     rcx, rax; hSourceProcessHandle
0x1802f2ca8  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x1802f2cb0  mov     r8, rdi; hTargetProcessHandle
0x1802f2cb3  mov     [rsp+70h+dwDesiredAccess], 2; dwDesiredAccess
0x1802f2cbb  mov     rdx, r15; hSourceHandle
0x1802f2cbe  call    cs:__imp_DuplicateHandle
0x1802f2cc5  nop     dword ptr [rax+rax+00h]
0x1802f2cca  test    eax, eax
0x1802f2ccc  jnz     short loc_1802F2CD5
0x1802f2cce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802f2cd3  mov     esi, eax
0x1802f2cd5  lea     rcx, [rbp+lParam]
0x1802f2cd9  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802f2cde  test    esi, esi
0x1802f2ce0  js      loc_1802F2D75
0x1802f2ce6  mov     rcx, [rbp+arg_10]
0x1802f2cea  lea     r8, [rbp+dwProcessId]
0x1802f2cee  mov     edx, dword ptr [rbp+TargetHandle]
0x1802f2cf1  mov     [rbp+dwProcessId], 0
0x1802f2cf8  mov     rax, [rcx]
0x1802f2cfb  mov     rax, [rax+18h]
0x1802f2cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f2d04  lea     rcx, [rbp+Parameter]; this
0x1802f2d08  mov     esi, eax
0x1802f2d0a  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1802f2d0f  cmp     [rbp+dwProcessId], 0
0x1802f2d13  jnz     short loc_1802F2D75
0x1802f2d15  call    cs:__imp_GetTickCount
0x1802f2d1c  nop     dword ptr [rax+rax+00h]
0x1802f2d21  test    esi, esi
0x1802f2d23  js      short loc_1802F2D75
0x1802f2d25  sub     eax, r12d
0x1802f2d28  cmp     eax, r14d
0x1802f2d2b  jnb     short loc_1802F2D70
0x1802f2d2d  sub     r14d, eax
0x1802f2d30  mov     rcx, rbx; hHandle
0x1802f2d33  mov     edx, r14d; dwMilliseconds
0x1802f2d36  call    cs:__imp_WaitForSingleObject
0x1802f2d3d  nop     dword ptr [rax+rax+00h]
0x1802f2d42  test    eax, eax
0x1802f2d44  jz      short loc_1802F2D75
0x1802f2d46  cmp     eax, 80h
0x1802f2d4b  jz      short loc_1802F2D69
0x1802f2d4d  cmp     eax, 102h
0x1802f2d52  jz      short loc_1802F2D70
0x1802f2d54  cmp     eax, 0FFFFFFFFh
0x1802f2d57  jz      short loc_1802F2D60
0x1802f2d59  mov     esi, 8000FFFFh
0x1802f2d5e  jmp     short loc_1802F2D75
0x1802f2d60  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802f2d65  mov     esi, eax
0x1802f2d67  jmp     short loc_1802F2D75
0x1802f2d69  mov     esi, 800702DFh
0x1802f2d6e  jmp     short loc_1802F2D75
0x1802f2d70  mov     esi, 800705B4h
0x1802f2d75  lea     rcx, [rbp+arg_8]
0x1802f2d79  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802f2d7e  lea     rcx, [rbp+arg_10]
0x1802f2d82  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802f2d87  lea     rcx, [rbp+Parameter]; this
0x1802f2d8b  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1802f2d90  jmp     short loc_1802F2D95
0x1802f2d92  mov     [rbx], rax
0x1802f2d95  mov     eax, esi
0x1802f2d97  add     rsp, 70h
0x1802f2d9b  pop     r15
0x1802f2d9d  pop     r14
0x1802f2d9f  pop     r12
0x1802f2da1  pop     rdi
0x1802f2da2  pop     rsi
0x1802f2da3  pop     rbx
0x1802f2da4  pop     rbp
0x1802f2da5  retn
```
