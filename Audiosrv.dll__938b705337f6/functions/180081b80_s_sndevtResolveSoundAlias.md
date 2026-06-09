# s_sndevtResolveSoundAlias

- ea: `0x180081b80`
- end: `0x180081fb0`
- name: `s_sndevtResolveSoundAlias`
- size: `1072`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, LPHANDLE lpTargetHandle, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x18000af90`
- `0x18001b3d0`
- `0x180059730`
- `0x180061368`
- `0x180081b80`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081ed8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081ee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081ee8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081f6b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081f0c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081f0c`
- `RPCRT4!RpcImpersonateClient` at `0x180081d68`
- `RPCRT4!RpcImpersonateClient` at `0x180081d68`
- `RPCRT4!RpcRevertToSelf` at `0x180081ec4`
- `RPCRT4!RpcRevertToSelf` at `0x180081f45`
- `RPCRT4!RpcRevertToSelf` at `0x180081ec4`
- `RPCRT4!RpcRevertToSelf` at `0x180081f45`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180081ea2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180081ea2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180081d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180081d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081de1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081e48`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081e48`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180081ebb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180081ebb`

## pseudocode

```c
__int64 __fastcall s_sndevtResolveSoundAlias(
        RPC_BINDING_HANDLE BindingHandle,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD a4,
        LPHANDLE lpTargetHandle,
        wchar_t **a6)
{
  struct _FILETIME v6; // rbx
  RPC_BINDING_HANDLE v7; // rdi
  char *v8; // r14
  char *v9; // r13
  void *v10; // rsi
  __int64 v11; // rax
  void *v12; // rsi
  __int64 v13; // rax
  int v14; // esi
  DWORD LastError; // edi
  __int64 v16; // rax
  size_t v17; // rbx
  wchar_t *v18; // rax
  int v19; // esi
  const unsigned __int16 *v20; // rcx
  int SoundAlias; // ebx
  HANDLE CurrentProcess; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char *FileW; // [rsp+48h] [rbp-B8h]
  char v26; // [rsp+50h] [rbp-B0h]
  unsigned int Pid; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int dwLowDateTime; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v34; // [rsp+88h] [rbp-78h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF

  v6.dwLowDateTime = a4;
  v7 = BindingHandle;
  v34 = a3;
  v31 = a2;
  Binding = BindingHandle;
  v26 = a4;
  phkResult = 0;
  memset_0(FileName, 0, 0x208u);
  dwLowDateTime = v6.dwLowDateTime;
  v8 = 0;
  FileW = 0;
  v9 = 0;
  Pid = 0;
  v33 = 0;
  v32 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v10 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = 0;
    if ( v10 )
    {
      v6 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v11 = CWatchdogTimer<1>::CWatchdogTimer<1>(v10, v6);
      LOBYTE(v6.dwLowDateTime) = v26;
      v7 = Binding;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v33, v11);
  }
  else
  {
    v12 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = 0;
    if ( v12 )
    {
      v6 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v13 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v12, v6);
      LOBYTE(v6.dwLowDateTime) = v26;
      v7 = Binding;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v32, v13);
  }
  v14 = 0;
  if ( !v31 )
  {
    LastError = -2147418096;
    goto LABEL_10;
  }
  if ( !lpTargetHandle )
  {
    if ( !a6 )
    {
      LastError = -2147418096;
      goto LABEL_62;
    }
    goto LABEL_20;
  }
  *lpTargetHandle = (HANDLE)-1LL;
  if ( a6 )
LABEL_20:
    *a6 = 0;
  LastError = RpcImpersonateClient(v7);
  if ( LastError )
    goto LABEL_10;
LABEL_22:
  v19 = v6.dwLowDateTime & 2;
  while ( 1 )
  {
    FileName[0] = 0;
    LastError = RegOpenCurrentUser(1u, &phkResult);
    if ( LastError )
      goto LABEL_40;
    v20 = v31;
    if ( (_DWORD)v8 )
      v20 = szSystemDefaultSound;
    SoundAlias = _GetSoundAlias(v20, FileName, 0, &dwLowDateTime, dwCreationDisposition, phkResult, v34);
    RegCloseKey(phkResult);
    if ( !SoundAlias )
    {
      LOBYTE(v6.dwLowDateTime) = v26;
      if ( (v26 & 2) == 0 && (_DWORD)v8 != 1 )
      {
        LODWORD(v8) = 1;
        goto LABEL_22;
      }
      LastError = 1168;
      goto LABEL_40;
    }
    if ( FileName[0] )
      break;
    if ( v19 || (_DWORD)v8 == 1 )
    {
      LastError = 2;
LABEL_40:
      v8 = FileW;
      v14 = 1;
      goto LABEL_10;
    }
LABEL_38:
    LODWORD(v8) = 1;
  }
  if ( !lpTargetHandle )
    goto LABEL_40;
  FileW = (char *)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x60000080u, 0);
  if ( FileW == (char *)-1LL )
  {
    if ( !v19 && (_DWORD)v8 != 1 )
      goto LABEL_38;
    LastError = GetLastError();
LABEL_42:
    v14 = 1;
    v8 = FileW;
    goto LABEL_10;
  }
  LastError = I_RpcBindingInqLocalClientPID(Binding, &Pid);
  if ( LastError )
    goto LABEL_42;
  v9 = (char *)OpenProcess(0x40u, 0, Pid);
  LastError = RpcRevertToSelf();
  if ( LastError )
    goto LABEL_42;
  v14 = 0;
  if ( !v9
    || (CurrentProcess = GetCurrentProcess(), !DuplicateHandle(CurrentProcess, FileW, v9, lpTargetHandle, 0, 0, 2u)) )
  {
    LastError = GetLastError();
  }
  v8 = FileW;
LABEL_10:
  if ( a6 )
  {
    v16 = -1;
    do
      ++v16;
    while ( FileName[v16] );
    v17 = 2 * v16 + 2;
    v18 = (wchar_t *)MIDL_user_allocate(v17);
    *a6 = v18;
    if ( v18 )
    {
      StringCbCopyExW(v18, v17, FileName, 0, 0, 0x600u);
      if ( LastError )
        goto LABEL_52;
    }
    else if ( LastError )
    {
      LastError = 14;
LABEL_52:
      if ( lpTargetHandle )
      {
        if ( (char *)*lpTargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(*lpTargetHandle);
        *lpTargetHandle = (HANDLE)-1LL;
      }
    }
  }
  if ( v14 == 1 )
    RpcRevertToSelf();
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
LABEL_62:
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v32);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v33);
  return LastError;
}

```

## disassembly

```asm
0x180081b80  mov     [rsp-8+arg_18], rbx
0x180081b85  push    rbp
0x180081b86  push    rsi
0x180081b87  push    rdi
0x180081b88  push    r12
0x180081b8a  push    r13
0x180081b8c  push    r14
0x180081b8e  push    r15
0x180081b90  lea     rbp, [rsp-1B0h]
0x180081b98  sub     rsp, 2B0h
0x180081b9f  mov     rax, cs:__security_cookie
0x180081ba6  xor     rax, rsp
0x180081ba9  mov     [rbp+1E0h+var_40], rax
0x180081bb0  mov     r15, [rbp+1E0h+lpTargetHandle]
0x180081bb7  mov     ebx, r9d
0x180081bba  mov     r12, [rbp+1E0h+arg_28]
0x180081bc1  mov     rdi, rcx
0x180081bc4  mov     [rbp+1E0h+var_258], r8
0x180081bc8  xor     esi, esi
0x180081bca  mov     [rsp+2E0h+var_270], rdx
0x180081bcf  mov     r8d, 208h; Size
0x180081bd5  mov     [rsp+2E0h+Binding], rcx
0x180081bda  xor     edx, edx; Val
0x180081bdc  lea     rcx, [rbp+1E0h+FileName]; void *
0x180081be0  mov     [rsp+2E0h+var_290], ebx
0x180081be4  mov     [rsp+2E0h+phkResult], rsi
0x180081be9  call    memset_0
0x180081bee  mov     [rsp+2E0h+var_288], ebx
0x180081bf2  mov     r14d, esi
0x180081bf5  mov     [rsp+2E0h+var_298], rsi
0x180081bfa  mov     r13d, esi
0x180081bfd  mov     [rsp+2E0h+Pid], esi
0x180081c01  mov     [rbp+1E0h+var_260], rsi
0x180081c05  mov     [rsp+2E0h+var_268], rsi
0x180081c0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180081c11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180081c16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081c1d  lea     ecx, [rsi+38h]; unsigned __int64
0x180081c20  test    al, al
0x180081c22  jz      short loc_180081C77
0x180081c24  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180081c29  mov     rsi, rax
0x180081c2c  xor     eax, eax
0x180081c2e  test    rsi, rsi
0x180081c31  jz      short loc_180081C69
0x180081c33  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180081c3a  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180081c40  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180081c45  lea     r9, aSSndevtresolve; "s_sndevtResolveSoundAlias"
0x180081c4c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx; pftDueTime
0x180081c51  mov     r8d, edi
0x180081c54  mov     rcx, rsi; pv
0x180081c57  mov     rdx, [rax+8]
0x180081c5b  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180081c60  mov     ebx, [rsp+2E0h+var_290]
0x180081c64  mov     rdi, [rsp+2E0h+Binding]
0x180081c69  mov     rdx, rax
0x180081c6c  lea     rcx, [rbp+1E0h+var_260]
0x180081c70  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180081c75  jmp     short loc_180081CC9
0x180081c77  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180081c7c  mov     rsi, rax
0x180081c7f  xor     eax, eax
0x180081c81  test    rsi, rsi
0x180081c84  jz      short loc_180081CBC
0x180081c86  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180081c8d  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180081c93  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180081c98  lea     r9, aSSndevtresolve; "s_sndevtResolveSoundAlias"
0x180081c9f  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx; int
0x180081ca4  mov     r8d, edi
0x180081ca7  mov     rcx, rsi; pv
0x180081caa  mov     rdx, [rax+8]
0x180081cae  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180081cb3  mov     ebx, [rsp+2E0h+var_290]
0x180081cb7  mov     rdi, [rsp+2E0h+Binding]
0x180081cbc  mov     rdx, rax
0x180081cbf  lea     rcx, [rsp+2E0h+var_268]
0x180081cc4  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180081cc9  xor     esi, esi
0x180081ccb  cmp     [rsp+2E0h+var_270], rsi
0x180081cd0  jnz     short loc_180081D41
0x180081cd2  mov     edi, 80010010h
0x180081cd7  xor     r8d, r8d
0x180081cda  test    r12, r12
0x180081cdd  jz      loc_180081F40
0x180081ce3  lea     rcx, [rbp+1E0h+FileName]
0x180081ce7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180081ceb  inc     rax
0x180081cee  cmp     [rcx+rax*2], r8w
0x180081cf3  jnz     short loc_180081CEB
0x180081cf5  lea     rbx, ds:2[rax*2]
0x180081cfd  mov     rcx, rbx; size
0x180081d00  call    MIDL_user_allocate
0x180081d05  mov     [r12], rax
0x180081d09  xor     r12d, r12d
0x180081d0c  test    rax, rax
0x180081d0f  jz      loc_180081F18
0x180081d15  mov     [rsp+2E0h+dwFlagsAndAttributes], 600h; unsigned int
0x180081d1d  lea     r8, [rbp+1E0h+FileName]; unsigned __int16 *
0x180081d21  xor     r9d, r9d; unsigned __int16 **
0x180081d24  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r12; unsigned __int64 *
0x180081d29  mov     rdx, rbx; cbDest
0x180081d2c  mov     rcx, rax; pszDest
0x180081d2f  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180081d34  test    edi, edi
0x180081d36  jz      loc_180081F40
0x180081d3c  jmp     loc_180081F21
0x180081d41  test    r15, r15
0x180081d44  jnz     short loc_180081D55
0x180081d46  test    r12, r12
0x180081d49  jnz     short loc_180081D61
0x180081d4b  mov     edi, 80010010h
0x180081d50  jmp     loc_180081F71
0x180081d55  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180081d5c  test    r12, r12
0x180081d5f  jz      short loc_180081D65
0x180081d61  mov     [r12], rsi
0x180081d65  mov     rcx, rdi; BindingHandle
0x180081d68  call    cs:__imp_RpcImpersonateClient
0x180081d6e  mov     edi, eax
0x180081d70  test    eax, eax
0x180081d72  jnz     loc_180081CD7
0x180081d78  mov     [rsp+2E0h+var_2A0], 1
0x180081d80  mov     esi, ebx
0x180081d82  and     esi, 2
0x180081d85  xor     eax, eax
0x180081d87  lea     rdx, [rsp+2E0h+phkResult]; phkResult
0x180081d8c  mov     [rbp+1E0h+FileName], ax
0x180081d90  lea     ecx, [rax+1]; samDesired
0x180081d93  call    cs:__imp_RegOpenCurrentUser
0x180081d99  xor     r8d, r8d; unsigned __int64
0x180081d9c  mov     edi, eax
0x180081d9e  test    eax, eax
0x180081da0  jnz     loc_180081E76
0x180081da6  mov     rax, [rsp+2E0h+phkResult]
0x180081dab  lea     rdx, ?szSystemDefaultSound@@3PAGA; ".Default"
0x180081db2  mov     rcx, [rsp+2E0h+var_270]
0x180081db7  lea     r9, [rsp+2E0h+var_288]; unsigned int *
0x180081dbc  test    r14d, r14d
0x180081dbf  cmovnz  rcx, rdx; unsigned __int16 *
0x180081dc3  mov     rdx, [rbp+1E0h+var_258]
0x180081dc7  mov     [rsp+2E0h+hTemplateFile], rdx; unsigned __int16 *
0x180081dcc  lea     rdx, [rbp+1E0h+FileName]; unsigned __int16 *
0x180081dd0  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; HKEY
0x180081dd5  call    ?_GetSoundAlias@@YAHPEBGPEAG_KAEAKHPEAUHKEY__@@0@Z; _GetSoundAlias(ushort const *,ushort *,unsigned __int64,ulong &,int,HKEY__ *,ushort const *)
0x180081dda  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180081ddf  mov     ebx, eax
0x180081de1  call    cs:__imp_RegCloseKey
0x180081de7  xor     r8d, r8d
0x180081dea  test    ebx, ebx
0x180081dec  jnz     short loc_180081E06
0x180081dee  mov     ebx, [rsp+2E0h+var_290]
0x180081df2  test    bl, 2
0x180081df5  jnz     short loc_180081E71
0x180081df7  cmp     r14d, 1
0x180081dfb  jz      short loc_180081E71
0x180081dfd  lea     r14d, [rdi+1]
0x180081e01  jmp     loc_180081D80
0x180081e06  cmp     [rbp+1E0h+FileName], r8w
0x180081e0b  jnz     short loc_180081E1E
0x180081e0d  test    esi, esi
0x180081e0f  jnz     short loc_180081E17
0x180081e11  cmp     r14d, 1
0x180081e15  jnz     short loc_180081E66
0x180081e17  mov     edi, 2
0x180081e1c  jmp     short loc_180081E76
0x180081e1e  test    r15, r15
0x180081e21  jz      short loc_180081E76
0x180081e23  mov     [rsp+2E0h+hTemplateFile], r8; hTemplateFile
0x180081e28  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x180081e2c  mov     eax, 3
0x180081e31  mov     [rsp+2E0h+dwFlagsAndAttributes], 60000080h; dwFlagsAndAttributes
0x180081e39  mov     r8d, eax; dwShareMode
0x180081e3c  mov     [rsp+2E0h+dwCreationDisposition], eax; dwCreationDisposition
0x180081e40  xor     r9d, r9d; lpSecurityAttributes
0x180081e43  mov     edx, 80000000h; dwDesiredAccess
0x180081e48  call    cs:__imp_CreateFileW
0x180081e4e  mov     [rsp+2E0h+var_298], rax
0x180081e53  mov     rbx, rax
0x180081e56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180081e5a  jnz     short loc_180081E98
0x180081e5c  test    esi, esi
0x180081e5e  jnz     short loc_180081E84
0x180081e60  cmp     r14d, 1
0x180081e64  jz      short loc_180081E84
0x180081e66  mov     r14d, 1
0x180081e6c  jmp     loc_180081D85
0x180081e71  mov     edi, 490h
0x180081e76  mov     r14, [rsp+2E0h+var_298]
0x180081e7b  mov     esi, [rsp+2E0h+var_2A0]
0x180081e7f  jmp     loc_180081CDA
0x180081e84  call    cs:__imp_GetLastError
0x180081e8a  mov     edi, eax
0x180081e8c  mov     esi, [rsp+2E0h+var_2A0]
0x180081e90  mov     r14, rbx
0x180081e93  jmp     loc_180081CD7
0x180081e98  mov     rcx, [rsp+2E0h+Binding]; Binding
0x180081e9d  lea     rdx, [rsp+2E0h+Pid]; Pid
0x180081ea2  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180081ea8  xor     r14d, r14d
0x180081eab  mov     edi, eax
0x180081ead  test    eax, eax
0x180081eaf  jnz     short loc_180081E8C
0x180081eb1  mov     r8d, [rsp+2E0h+Pid]; dwProcessId
0x180081eb6  lea     ecx, [rax+40h]; dwDesiredAccess
0x180081eb9  xor     edx, edx; bInheritHandle
0x180081ebb  call    cs:__imp_OpenProcess
0x180081ec1  mov     r13, rax
0x180081ec4  call    cs:__imp_RpcRevertToSelf
0x180081eca  mov     edi, eax
0x180081ecc  test    eax, eax
0x180081ece  jnz     short loc_180081E8C
0x180081ed0  mov     esi, r14d
0x180081ed3  test    r13, r13
0x180081ed6  jnz     short loc_180081EE8
0x180081ed8  call    cs:__imp_GetLastError
0x180081ede  mov     edi, eax
0x180081ee0  mov     r14, rbx
0x180081ee3  jmp     loc_180081CD7
0x180081ee8  call    cs:__imp_GetCurrentProcess
0x180081eee  mov     dword ptr [rsp+2E0h+hTemplateFile], 2; dwOptions
0x180081ef6  mov     r9, r15; lpTargetHandle
0x180081ef9  mov     rcx, rax; hSourceProcessHandle
0x180081efc  mov     [rsp+2E0h+dwFlagsAndAttributes], r14d; bInheritHandle
0x180081f01  mov     r8, r13; hTargetProcessHandle
0x180081f04  mov     [rsp+2E0h+dwCreationDisposition], r14d; dwDesiredAccess
0x180081f09  mov     rdx, rbx; hSourceHandle
0x180081f0c  call    cs:__imp_DuplicateHandle
0x180081f12  test    eax, eax
0x180081f14  jnz     short loc_180081EE0
0x180081f16  jmp     short loc_180081ED8
0x180081f18  test    edi, edi
0x180081f1a  jz      short loc_180081F40
0x180081f1c  mov     edi, 0Eh
0x180081f21  test    r15, r15
0x180081f24  jz      short loc_180081F40
0x180081f26  mov     rcx, [r15]; hObject
0x180081f29  lea     rax, [rcx-1]
0x180081f2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081f31  ja      short loc_180081F39
0x180081f33  call    cs:__imp_CloseHandle
0x180081f39  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180081f40  cmp     esi, 1
0x180081f43  jnz     short loc_180081F4B
0x180081f45  call    cs:__imp_RpcRevertToSelf
0x180081f4b  lea     rax, [r14-1]
0x180081f4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081f53  ja      short loc_180081F5E
0x180081f55  mov     rcx, r14; hObject
0x180081f58  call    cs:__imp_CloseHandle
0x180081f5e  lea     rax, [r13-1]
0x180081f62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081f66  ja      short loc_180081F71
0x180081f68  mov     rcx, r13; hObject
0x180081f6b  call    cs:__imp_CloseHandle
0x180081f71  lea     rcx, [rsp+2E0h+var_268]
0x180081f76  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180081f7b  lea     rcx, [rbp+1E0h+var_260]
0x180081f7f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180081f84  mov     eax, edi
0x180081f86  mov     rcx, [rbp+1E0h+var_40]
0x180081f8d  xor     rcx, rsp; StackCookie
0x180081f90  call    __security_check_cookie
0x180081f95  mov     rbx, [rsp+2E0h+arg_18]
0x180081f9d  add     rsp, 2B0h
0x180081fa4  pop     r15
0x180081fa6  pop     r14
0x180081fa8  pop     r13
0x180081faa  pop     r12
0x180081fac  pop     rdi
0x180081fad  pop     rsi
0x180081fae  pop     rbp
0x180081faf  retn
```
