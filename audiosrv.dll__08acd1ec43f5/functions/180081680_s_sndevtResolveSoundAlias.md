# s_sndevtResolveSoundAlias

- ea: `0x180081680`
- end: `0x180081ab0`
- name: `s_sndevtResolveSoundAlias`
- size: `1072`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, LPHANDLE lpTargetHandle, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x18000b0e0`
- `0x18001b520`
- `0x1800592a0`
- `0x180060ed8`
- `0x180081680`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800819d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800819d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800819e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800819e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081a6b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081a0c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081a0c`
- `RPCRT4!RpcImpersonateClient` at `0x180081868`
- `RPCRT4!RpcImpersonateClient` at `0x180081868`
- `RPCRT4!RpcRevertToSelf` at `0x1800819c4`
- `RPCRT4!RpcRevertToSelf` at `0x180081a45`
- `RPCRT4!RpcRevertToSelf` at `0x1800819c4`
- `RPCRT4!RpcRevertToSelf` at `0x180081a45`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800819a2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800819a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180081893`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180081893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800818e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800818e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081948`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180081948`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800819bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800819bb`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x180081680  mov     [rsp-8+arg_18], rbx
0x180081685  push    rbp
0x180081686  push    rsi
0x180081687  push    rdi
0x180081688  push    r12
0x18008168a  push    r13
0x18008168c  push    r14
0x18008168e  push    r15
0x180081690  lea     rbp, [rsp-1B0h]
0x180081698  sub     rsp, 2B0h
0x18008169f  mov     rax, cs:__security_cookie
0x1800816a6  xor     rax, rsp
0x1800816a9  mov     [rbp+1E0h+var_40], rax
0x1800816b0  mov     r15, [rbp+1E0h+lpTargetHandle]
0x1800816b7  mov     ebx, r9d
0x1800816ba  mov     r12, [rbp+1E0h+arg_28]
0x1800816c1  mov     rdi, rcx
0x1800816c4  mov     [rbp+1E0h+var_258], r8
0x1800816c8  xor     esi, esi
0x1800816ca  mov     [rsp+2E0h+var_270], rdx
0x1800816cf  mov     r8d, 208h; Size
0x1800816d5  mov     [rsp+2E0h+Binding], rcx
0x1800816da  xor     edx, edx; Val
0x1800816dc  lea     rcx, [rbp+1E0h+FileName]; void *
0x1800816e0  mov     [rsp+2E0h+var_290], ebx
0x1800816e4  mov     [rsp+2E0h+phkResult], rsi
0x1800816e9  call    memset_0
0x1800816ee  mov     [rsp+2E0h+var_288], ebx
0x1800816f2  mov     r14d, esi
0x1800816f5  mov     [rsp+2E0h+var_298], rsi
0x1800816fa  mov     r13d, esi
0x1800816fd  mov     [rsp+2E0h+Pid], esi
0x180081701  mov     [rbp+1E0h+var_260], rsi
0x180081705  mov     [rsp+2E0h+var_268], rsi
0x18008170a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180081711  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180081716  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008171d  lea     ecx, [rsi+38h]; unsigned __int64
0x180081720  test    al, al
0x180081722  jz      short loc_180081777
0x180081724  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180081729  mov     rsi, rax
0x18008172c  xor     eax, eax
0x18008172e  test    rsi, rsi
0x180081731  jz      short loc_180081769
0x180081733  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18008173a  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180081740  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180081745  lea     r9, aSSndevtresolve; "s_sndevtResolveSoundAlias"
0x18008174c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx; pftDueTime
0x180081751  mov     r8d, edi
0x180081754  mov     rcx, rsi; pv
0x180081757  mov     rdx, [rax+8]
0x18008175b  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180081760  mov     ebx, [rsp+2E0h+var_290]
0x180081764  mov     rdi, [rsp+2E0h+Binding]
0x180081769  mov     rdx, rax
0x18008176c  lea     rcx, [rbp+1E0h+var_260]
0x180081770  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180081775  jmp     short loc_1800817C9
0x180081777  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008177c  mov     rsi, rax
0x18008177f  xor     eax, eax
0x180081781  test    rsi, rsi
0x180081784  jz      short loc_1800817BC
0x180081786  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x18008178d  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180081793  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180081798  lea     r9, aSSndevtresolve; "s_sndevtResolveSoundAlias"
0x18008179f  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rbx; int
0x1800817a4  mov     r8d, edi
0x1800817a7  mov     rcx, rsi; pv
0x1800817aa  mov     rdx, [rax+8]
0x1800817ae  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x1800817b3  mov     ebx, [rsp+2E0h+var_290]
0x1800817b7  mov     rdi, [rsp+2E0h+Binding]
0x1800817bc  mov     rdx, rax
0x1800817bf  lea     rcx, [rsp+2E0h+var_268]
0x1800817c4  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x1800817c9  xor     esi, esi
0x1800817cb  cmp     [rsp+2E0h+var_270], rsi
0x1800817d0  jnz     short loc_180081841
0x1800817d2  mov     edi, 80010010h
0x1800817d7  xor     r8d, r8d
0x1800817da  test    r12, r12
0x1800817dd  jz      loc_180081A40
0x1800817e3  lea     rcx, [rbp+1E0h+FileName]
0x1800817e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800817eb  inc     rax
0x1800817ee  cmp     [rcx+rax*2], r8w
0x1800817f3  jnz     short loc_1800817EB
0x1800817f5  lea     rbx, ds:2[rax*2]
0x1800817fd  mov     rcx, rbx; size
0x180081800  call    MIDL_user_allocate
0x180081805  mov     [r12], rax
0x180081809  xor     r12d, r12d
0x18008180c  test    rax, rax
0x18008180f  jz      loc_180081A18
0x180081815  mov     [rsp+2E0h+dwFlagsAndAttributes], 600h; unsigned int
0x18008181d  lea     r8, [rbp+1E0h+FileName]; unsigned __int16 *
0x180081821  xor     r9d, r9d; unsigned __int16 **
0x180081824  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r12; unsigned __int64 *
0x180081829  mov     rdx, rbx; cbDest
0x18008182c  mov     rcx, rax; pszDest
0x18008182f  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180081834  test    edi, edi
0x180081836  jz      loc_180081A40
0x18008183c  jmp     loc_180081A21
0x180081841  test    r15, r15
0x180081844  jnz     short loc_180081855
0x180081846  test    r12, r12
0x180081849  jnz     short loc_180081861
0x18008184b  mov     edi, 80010010h
0x180081850  jmp     loc_180081A71
0x180081855  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18008185c  test    r12, r12
0x18008185f  jz      short loc_180081865
0x180081861  mov     [r12], rsi
0x180081865  mov     rcx, rdi; BindingHandle
0x180081868  call    cs:__imp_RpcImpersonateClient
0x18008186e  mov     edi, eax
0x180081870  test    eax, eax
0x180081872  jnz     loc_1800817D7
0x180081878  mov     [rsp+2E0h+var_2A0], 1
0x180081880  mov     esi, ebx
0x180081882  and     esi, 2
0x180081885  xor     eax, eax
0x180081887  lea     rdx, [rsp+2E0h+phkResult]; phkResult
0x18008188c  mov     [rbp+1E0h+FileName], ax
0x180081890  lea     ecx, [rax+1]; samDesired
0x180081893  call    cs:__imp_RegOpenCurrentUser
0x180081899  xor     r8d, r8d; unsigned __int64
0x18008189c  mov     edi, eax
0x18008189e  test    eax, eax
0x1800818a0  jnz     loc_180081976
0x1800818a6  mov     rax, [rsp+2E0h+phkResult]
0x1800818ab  lea     rdx, ?szSystemDefaultSound@@3PAGA; ".Default"
0x1800818b2  mov     rcx, [rsp+2E0h+var_270]
0x1800818b7  lea     r9, [rsp+2E0h+var_288]; unsigned int *
0x1800818bc  test    r14d, r14d
0x1800818bf  cmovnz  rcx, rdx; unsigned __int16 *
0x1800818c3  mov     rdx, [rbp+1E0h+var_258]
0x1800818c7  mov     [rsp+2E0h+hTemplateFile], rdx; unsigned __int16 *
0x1800818cc  lea     rdx, [rbp+1E0h+FileName]; unsigned __int16 *
0x1800818d0  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; HKEY
0x1800818d5  call    ?_GetSoundAlias@@YAHPEBGPEAG_KAEAKHPEAUHKEY__@@0@Z; _GetSoundAlias(ushort const *,ushort *,unsigned __int64,ulong &,int,HKEY__ *,ushort const *)
0x1800818da  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800818df  mov     ebx, eax
0x1800818e1  call    cs:__imp_RegCloseKey
0x1800818e7  xor     r8d, r8d
0x1800818ea  test    ebx, ebx
0x1800818ec  jnz     short loc_180081906
0x1800818ee  mov     ebx, [rsp+2E0h+var_290]
0x1800818f2  test    bl, 2
0x1800818f5  jnz     short loc_180081971
0x1800818f7  cmp     r14d, 1
0x1800818fb  jz      short loc_180081971
0x1800818fd  lea     r14d, [rdi+1]
0x180081901  jmp     loc_180081880
0x180081906  cmp     [rbp+1E0h+FileName], r8w
0x18008190b  jnz     short loc_18008191E
0x18008190d  test    esi, esi
0x18008190f  jnz     short loc_180081917
0x180081911  cmp     r14d, 1
0x180081915  jnz     short loc_180081966
0x180081917  mov     edi, 2
0x18008191c  jmp     short loc_180081976
0x18008191e  test    r15, r15
0x180081921  jz      short loc_180081976
0x180081923  mov     [rsp+2E0h+hTemplateFile], r8; hTemplateFile
0x180081928  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x18008192c  mov     eax, 3
0x180081931  mov     [rsp+2E0h+dwFlagsAndAttributes], 60000080h; dwFlagsAndAttributes
0x180081939  mov     r8d, eax; dwShareMode
0x18008193c  mov     [rsp+2E0h+dwCreationDisposition], eax; dwCreationDisposition
0x180081940  xor     r9d, r9d; lpSecurityAttributes
0x180081943  mov     edx, 80000000h; dwDesiredAccess
0x180081948  call    cs:__imp_CreateFileW
0x18008194e  mov     [rsp+2E0h+var_298], rax
0x180081953  mov     rbx, rax
0x180081956  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008195a  jnz     short loc_180081998
0x18008195c  test    esi, esi
0x18008195e  jnz     short loc_180081984
0x180081960  cmp     r14d, 1
0x180081964  jz      short loc_180081984
0x180081966  mov     r14d, 1
0x18008196c  jmp     loc_180081885
0x180081971  mov     edi, 490h
0x180081976  mov     r14, [rsp+2E0h+var_298]
0x18008197b  mov     esi, [rsp+2E0h+var_2A0]
0x18008197f  jmp     loc_1800817DA
0x180081984  call    cs:__imp_GetLastError
0x18008198a  mov     edi, eax
0x18008198c  mov     esi, [rsp+2E0h+var_2A0]
0x180081990  mov     r14, rbx
0x180081993  jmp     loc_1800817D7
0x180081998  mov     rcx, [rsp+2E0h+Binding]; Binding
0x18008199d  lea     rdx, [rsp+2E0h+Pid]; Pid
0x1800819a2  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800819a8  xor     r14d, r14d
0x1800819ab  mov     edi, eax
0x1800819ad  test    eax, eax
0x1800819af  jnz     short loc_18008198C
0x1800819b1  mov     r8d, [rsp+2E0h+Pid]; dwProcessId
0x1800819b6  lea     ecx, [rax+40h]; dwDesiredAccess
0x1800819b9  xor     edx, edx; bInheritHandle
0x1800819bb  call    cs:__imp_OpenProcess
0x1800819c1  mov     r13, rax
0x1800819c4  call    cs:__imp_RpcRevertToSelf
0x1800819ca  mov     edi, eax
0x1800819cc  test    eax, eax
0x1800819ce  jnz     short loc_18008198C
0x1800819d0  mov     esi, r14d
0x1800819d3  test    r13, r13
0x1800819d6  jnz     short loc_1800819E8
0x1800819d8  call    cs:__imp_GetLastError
0x1800819de  mov     edi, eax
0x1800819e0  mov     r14, rbx
0x1800819e3  jmp     loc_1800817D7
0x1800819e8  call    cs:__imp_GetCurrentProcess
0x1800819ee  mov     dword ptr [rsp+2E0h+hTemplateFile], 2; dwOptions
0x1800819f6  mov     r9, r15; lpTargetHandle
0x1800819f9  mov     rcx, rax; hSourceProcessHandle
0x1800819fc  mov     [rsp+2E0h+dwFlagsAndAttributes], r14d; bInheritHandle
0x180081a01  mov     r8, r13; hTargetProcessHandle
0x180081a04  mov     [rsp+2E0h+dwCreationDisposition], r14d; dwDesiredAccess
0x180081a09  mov     rdx, rbx; hSourceHandle
0x180081a0c  call    cs:__imp_DuplicateHandle
0x180081a12  test    eax, eax
0x180081a14  jnz     short loc_1800819E0
0x180081a16  jmp     short loc_1800819D8
0x180081a18  test    edi, edi
0x180081a1a  jz      short loc_180081A40
0x180081a1c  mov     edi, 0Eh
0x180081a21  test    r15, r15
0x180081a24  jz      short loc_180081A40
0x180081a26  mov     rcx, [r15]; hObject
0x180081a29  lea     rax, [rcx-1]
0x180081a2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081a31  ja      short loc_180081A39
0x180081a33  call    cs:__imp_CloseHandle
0x180081a39  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180081a40  cmp     esi, 1
0x180081a43  jnz     short loc_180081A4B
0x180081a45  call    cs:__imp_RpcRevertToSelf
0x180081a4b  lea     rax, [r14-1]
0x180081a4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081a53  ja      short loc_180081A5E
0x180081a55  mov     rcx, r14; hObject
0x180081a58  call    cs:__imp_CloseHandle
0x180081a5e  lea     rax, [r13-1]
0x180081a62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081a66  ja      short loc_180081A71
0x180081a68  mov     rcx, r13; hObject
0x180081a6b  call    cs:__imp_CloseHandle
0x180081a71  lea     rcx, [rsp+2E0h+var_268]
0x180081a76  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180081a7b  lea     rcx, [rbp+1E0h+var_260]
0x180081a7f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180081a84  mov     eax, edi
0x180081a86  mov     rcx, [rbp+1E0h+var_40]
0x180081a8d  xor     rcx, rsp; StackCookie
0x180081a90  call    __security_check_cookie
0x180081a95  mov     rbx, [rsp+2E0h+arg_18]
0x180081a9d  add     rsp, 2B0h
0x180081aa4  pop     r15
0x180081aa6  pop     r14
0x180081aa8  pop     r13
0x180081aaa  pop     r12
0x180081aac  pop     rdi
0x180081aad  pop     rsi
0x180081aae  pop     rbp
0x180081aaf  retn
```
