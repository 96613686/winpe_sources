# CAutoInitCopyAccelerator::Initialize(void)

- ea: `0x14001d700`
- end: `0x14001d9dd`
- name: `?Initialize@CAutoInitCopyAccelerator@@QEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001dba4`

## callees

- `0x140003ba8`
- `0x140005c20`
- `0x140005c40`
- `0x14001d464`
- `0x14001d700`
- `0x14001da70`
- `0x14001e9dc`
- `0x140020800`
- `0x1400208f4`
- `0x140021424`
- `0x140022568`
- `0x14002380c`
- `0x140023d3c`
- `0x140024148`
- `0x140024c40`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x14001d91e`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001d91e`
- `MpClient!MpConfigRegisterForNotifications` at `0x14001d944`
- `MpClient!MpConfigRegisterForNotifications` at `0x14001d944`
- `MpClient!MpClientUtilExportFunctions` at `0x14001d7a5`
- `MpClient!MpClientUtilExportFunctions` at `0x14001d7ec`
- `MpClient!MpClientUtilExportFunctions` at `0x14001d7a5`
- `MpClient!MpClientUtilExportFunctions` at `0x14001d7ec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001d8a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001d8a7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001d8eb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001d900`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001d8eb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001d900`

## string_xrefs

- `0x14001d738`: `MpCopyAccelerator.log`
- `0x14001d7b1`: `MpCopyAcceleratorProcessMitigationPolicyFlags`
- `0x14001d84e`: `CheckParentProcessIdentity failed: hr = %#lx\n`
- `0x14001d878`: `CopyAccelerator is launched by an unverified process, so failing initialization\n`
- `0x14001d894`: `InitCopyAcceleratorRpc failed to initialize asimov telemetry: hr = %#lx\n`
- `0x14001d8f1`: `InitCopyAcceleratorRpc failed: hr = %#lx\n`
- `0x14001d97a`: `CopyAcceleratorFeatures init failed: hr = %#lx\n`

## pseudocode

```c
__int64 __fastcall CAutoInitCopyAccelerator::Initialize(RTL_SRWLOCK *this, __int64 a2, const wchar_t *a3)
{
  int TempPath; // eax
  const wchar_t *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edx
  unsigned int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  CAutoInitCopyAccelerator *v12; // rcx
  int inited; // ebx
  unsigned __int64 v14; // rdx
  unsigned __int64 v16; // rdx
  int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  struct CopyAcceleratorFeatures *Instance; // rdi
  _QWORD *v21; // rbx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned __int64 v24; // rdx
  int v25; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *v26; // [rsp+38h] [rbp-18h] BYREF
  int v27; // [rsp+40h] [rbp-10h] BYREF

  this->Ptr = (PVOID)((unsigned __int64)this->Ptr | 1);
  v26 = 0;
  TempPath = CommonUtil::UtilGetTempPath((CommonUtil *)&v26, (wchar_t **)L"MpCopyAccelerator.log", a3);
  if ( TempPath < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
        (unsigned int)TempPath);
  }
  else
  {
    InitializeLogEx(v5, v26);
    if ( qword_14003DBC8 )
      CLogHandle::Flush(qword_14003DBC8);
  }
  this->Ptr = (PVOID)((unsigned __int64)this->Ptr | 2);
  v6 = 5;
  v25 = 5;
  v7 = MpClientUtilExportFunctions();
  if ( (*(int (__fastcall **)(const wchar_t *, __int64, int *))(v7 + 160))(
         L"MpCopyAcceleratorProcessMitigationPolicyFlags",
         5,
         &v25) >= 0 )
    v6 = v25;
  v9 = CommonUtil::MpEnsureProcessMitigationPolicy((CommonUtil *)v6, v8);
  MpCmdLogPrintf(L"MpEnsureProcessMitigationPolicy(%#lx): hr = %#lx\n", v6, v9);
  v27 = 0;
  v10 = MpClientUtilExportFunctions();
  v11 = (*(__int64 (__fastcall **)(int *))(v10 + 152))(&v27);
  if ( v11 < 0 )
  {
    v12 = (CAutoInitCopyAccelerator *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
        (unsigned int)v11);
  }
  if ( !v27 )
  {
    v25 = 0;
    inited = CheckParentProcessIdentity((unsigned int)v12, &v25);
    if ( inited < 0 )
    {
      MpCmdLogPrintf(L"CheckParentProcessIdentity failed: hr = %#lx\n", (unsigned int)inited);
LABEL_16:
      if ( v26 )
        operator delete(v26, v14);
      return (unsigned int)inited;
    }
    if ( !v25 )
    {
      MpCmdLogPrintf(L"CopyAccelerator is launched by an unverified process, so failing initialization\n");
LABEL_35:
      if ( v26 )
        operator delete(v26, v16);
      return 2147500037LL;
    }
  }
  inited = CAutoInitCopyAccelerator::InitAsimov(v12);
  if ( inited < 0 )
  {
    MpCmdLogPrintf(L"InitCopyAcceleratorRpc failed to initialize asimov telemetry: hr = %#lx\n", (unsigned int)inited);
    goto LABEL_16;
  }
  v17 = v27;
  AcquireSRWLockExclusive(this + 6);
  v18 = CopyAcceleratorRpc::InitUnsafe((CopyAcceleratorRpc *)&this[1], v17);
  v19 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
        (unsigned int)v18);
    ReleaseSRWLockExclusive(this + 6);
    MpCmdLogPrintf(L"InitCopyAcceleratorRpc failed: hr = %#lx\n", v19);
    goto LABEL_35;
  }
  ReleaseSRWLockExclusive(this + 6);
  this->Ptr = (PVOID)((unsigned __int64)this->Ptr | 4);
  Instance = CopyAcceleratorFeatures::GetInstance();
  v21 = (_QWORD *)((char *)Instance + 8);
  if ( *((_QWORD *)Instance + 1) )
  {
    MpConfigUnregisterNotifications();
    *v21 = 0;
  }
  v22 = MpConfigRegisterForNotifications(
          L"Features",
          Instance,
          &CopyAcceleratorFeatures::FeaturesNotificationCallback,
          0,
          v21);
  v23 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_30f9c55aabed343523773b84d16d3470_Traceguids,
        (unsigned int)v22);
    MpCmdLogPrintf(L"CopyAcceleratorFeatures init failed: hr = %#lx\n", v23);
    goto LABEL_35;
  }
  CopyAcceleratorFeatures::UpdateCancellableCopySupport(Instance);
  if ( v26 )
    operator delete(v26, v24);
  return 0;
}

```

## disassembly

```asm
0x14001d700  mov     [rsp-18h+arg_8], rbx
0x14001d705  mov     [rsp-18h+arg_10], rsi
0x14001d70a  mov     [rsp-18h+arg_18], rdi
0x14001d70f  push    rbp
0x14001d710  push    r12
0x14001d712  push    r14
0x14001d714  mov     rbp, rsp
0x14001d717  sub     rsp, 50h
0x14001d71b  mov     rax, cs:__security_cookie
0x14001d722  xor     rax, rsp
0x14001d725  mov     [rbp+var_8], rax
0x14001d729  mov     rsi, rcx
0x14001d72c  or      qword ptr [rcx], 1
0x14001d730  mov     [rbp+var_18], 0
0x14001d738  lea     rdx, aMpcopyaccelera_0; "MpCopyAccelerator.log"
0x14001d73f  lea     rcx, [rbp+var_18]; this
0x14001d743  call    ?UtilGetTempPath@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilGetTempPath(wchar_t * *,wchar_t const *)
0x14001d748  lea     r12, WPP_GLOBAL_Control
0x14001d74f  test    eax, eax
0x14001d751  js      short loc_14001D76F
0x14001d753  mov     rdx, [rbp+var_18]; wchar_t *
0x14001d757  call    ?InitializeLogEx@@YAXPEB_W0@Z; InitializeLogEx(wchar_t const *,wchar_t const *)
0x14001d75c  mov     rcx, cs:qword_14003DBC8; this
0x14001d763  test    rcx, rcx
0x14001d766  jz      short loc_14001D799
0x14001d768  call    ?Flush@CLogHandle@@QEAAJXZ; CLogHandle::Flush(void)
0x14001d76d  jmp     short loc_14001D799
0x14001d76f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d776  cmp     rcx, r12
0x14001d779  jz      short loc_14001D799
0x14001d77b  test    byte ptr [rcx+1Ch], 1
0x14001d77f  jz      short loc_14001D799
0x14001d781  mov     edx, 0Ah
0x14001d786  mov     r9d, eax
0x14001d789  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001d790  mov     rcx, [rcx+10h]
0x14001d794  call    WPP_SF_d
0x14001d799  or      qword ptr [rsi], 2
0x14001d79d  mov     ebx, 5
0x14001d7a2  mov     [rbp+var_20], ebx
0x14001d7a5  call    cs:__imp_MpClientUtilExportFunctions
0x14001d7ab  lea     r8, [rbp+var_20]
0x14001d7af  mov     edx, ebx
0x14001d7b1  lea     rcx, aMpcopyaccelera_1; "MpCopyAcceleratorProcessMitigationPolic"...
0x14001d7b8  mov     rax, [rax+0A0h]
0x14001d7bf  call    cs:__guard_dispatch_icall_fptr
0x14001d7c5  nop
0x14001d7c6  test    eax, eax
0x14001d7c8  js      short loc_14001D7CD
0x14001d7ca  mov     ebx, [rbp+var_20]
0x14001d7cd  mov     ecx, ebx; this
0x14001d7cf  call    ?MpEnsureProcessMitigationPolicy@CommonUtil@@YAJK@Z; CommonUtil::MpEnsureProcessMitigationPolicy(ulong)
0x14001d7d4  mov     r8d, eax
0x14001d7d7  mov     edx, ebx
0x14001d7d9  lea     rcx, aMpensureproces; "MpEnsureProcessMitigationPolicy(%#lx): "...
0x14001d7e0  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001d7e5  mov     [rbp+var_10], 0
0x14001d7ec  call    cs:__imp_MpClientUtilExportFunctions
0x14001d7f2  lea     rcx, [rbp+var_10]
0x14001d7f6  mov     rax, [rax+98h]
0x14001d7fd  call    cs:__guard_dispatch_icall_fptr
0x14001d803  nop
0x14001d804  test    eax, eax
0x14001d806  jns     short loc_14001D832
0x14001d808  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d80f  cmp     rcx, r12
0x14001d812  jz      short loc_14001D832
0x14001d814  test    byte ptr [rcx+1Ch], 1
0x14001d818  jz      short loc_14001D832
0x14001d81a  mov     edx, 0Bh
0x14001d81f  mov     r9d, eax
0x14001d822  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001d829  mov     rcx, [rcx+10h]
0x14001d82d  call    WPP_SF_d
0x14001d832  cmp     [rbp+var_10], 0
0x14001d836  jnz     short loc_14001D889
0x14001d838  mov     [rbp+var_20], 0
0x14001d83f  lea     rdx, [rbp+var_20]; int *
0x14001d843  call    ?CheckParentProcessIdentity@@YAJKPEAH@Z; CheckParentProcessIdentity(ulong,int *)
0x14001d848  mov     ebx, eax
0x14001d84a  test    eax, eax
0x14001d84c  jns     short loc_14001D872
0x14001d84e  lea     rcx, aCheckparentpro; "CheckParentProcessIdentity failed: hr ="...
0x14001d855  mov     edx, ebx
0x14001d857  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001d85c  nop
0x14001d85d  mov     rcx, [rbp+var_18]; void *
0x14001d861  test    rcx, rcx
0x14001d864  jz      short loc_14001D86B
0x14001d866  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d86b  mov     eax, ebx
0x14001d86d  jmp     loc_14001D9B7
0x14001d872  cmp     [rbp+var_20], 0
0x14001d876  jnz     short loc_14001D889
0x14001d878  lea     rcx, aCopyaccelerato_0; "CopyAccelerator is launched by an unver"...
0x14001d87f  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001d884  jmp     loc_14001D989
0x14001d889  call    ?InitAsimov@CAutoInitCopyAccelerator@@AEAAJXZ; CAutoInitCopyAccelerator::InitAsimov(void)
0x14001d88e  mov     ebx, eax
0x14001d890  test    eax, eax
0x14001d892  jns     short loc_14001D89D
0x14001d894  lea     rcx, aInitcopyaccele_0; "InitCopyAcceleratorRpc failed to initia"...
0x14001d89b  jmp     short loc_14001D855
0x14001d89d  mov     ebx, [rbp+var_10]
0x14001d8a0  lea     r14, [rsi+30h]
0x14001d8a4  mov     rcx, r14; SRWLock
0x14001d8a7  call    cs:__imp_AcquireSRWLockExclusive
0x14001d8ad  mov     edx, ebx; int
0x14001d8af  lea     rcx, [rsi+8]; this
0x14001d8b3  call    ?InitUnsafe@CopyAcceleratorRpc@@AEAAJH@Z; CopyAcceleratorRpc::InitUnsafe(int)
0x14001d8b8  mov     ebx, eax
0x14001d8ba  test    eax, eax
0x14001d8bc  jns     short loc_14001D8FD
0x14001d8be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8c5  cmp     rcx, r12
0x14001d8c8  jz      short loc_14001D8E8
0x14001d8ca  test    byte ptr [rcx+1Ch], 1
0x14001d8ce  jz      short loc_14001D8E8
0x14001d8d0  mov     edx, 0Fh
0x14001d8d5  mov     r9d, eax
0x14001d8d8  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001d8df  mov     rcx, [rcx+10h]
0x14001d8e3  call    WPP_SF_d
0x14001d8e8  mov     rcx, r14; SRWLock
0x14001d8eb  call    cs:__imp_ReleaseSRWLockExclusive
0x14001d8f1  lea     rcx, aInitcopyaccele; "InitCopyAcceleratorRpc failed: hr = %#l"...
0x14001d8f8  jmp     loc_14001D981
0x14001d8fd  mov     rcx, r14; SRWLock
0x14001d900  call    cs:__imp_ReleaseSRWLockExclusive
0x14001d906  or      qword ptr [rsi], 4
0x14001d90a  call    ?GetInstance@CopyAcceleratorFeatures@@SAAEAV1@XZ; CopyAcceleratorFeatures::GetInstance(void)
0x14001d90f  mov     rdi, rax
0x14001d912  lea     rbx, [rax+8]
0x14001d916  mov     rcx, [rbx]
0x14001d919  test    rcx, rcx
0x14001d91c  jz      short loc_14001D92B
0x14001d91e  call    cs:__imp_MpConfigUnregisterNotifications
0x14001d924  mov     qword ptr [rbx], 0
0x14001d92b  mov     [rsp+50h+var_30], rbx
0x14001d930  xor     r9d, r9d
0x14001d933  lea     r8, ?FeaturesNotificationCallback@CopyAcceleratorFeatures@@CAXPEAXW4tagMP_CONFIG_ORIGIN@@@Z; CopyAcceleratorFeatures::FeaturesNotificationCallback(void *,tagMP_CONFIG_ORIGIN)
0x14001d93a  mov     rdx, rdi
0x14001d93d  lea     rcx, aFeatures; "Features"
0x14001d944  call    cs:__imp_MpConfigRegisterForNotifications
0x14001d94a  mov     ebx, eax
0x14001d94c  test    eax, eax
0x14001d94e  jns     short loc_14001D99E
0x14001d950  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d957  cmp     rcx, r12
0x14001d95a  jz      short loc_14001D97A
0x14001d95c  test    byte ptr [rcx+1Ch], 1
0x14001d960  jz      short loc_14001D97A
0x14001d962  mov     edx, 0Ch
0x14001d967  mov     r9d, eax
0x14001d96a  lea     r8, WPP_30f9c55aabed343523773b84d16d3470_Traceguids
0x14001d971  mov     rcx, [rcx+10h]
0x14001d975  call    WPP_SF_d
0x14001d97a  lea     rcx, aCopyaccelerato; "CopyAcceleratorFeatures init failed: hr"...
0x14001d981  mov     edx, ebx
0x14001d983  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001d988  nop
0x14001d989  mov     rcx, [rbp+var_18]; void *
0x14001d98d  test    rcx, rcx
0x14001d990  jz      short loc_14001D997
0x14001d992  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d997  mov     eax, 80004005h
0x14001d99c  jmp     short loc_14001D9B7
0x14001d99e  mov     rcx, rdi; this
0x14001d9a1  call    ?UpdateCancellableCopySupport@CopyAcceleratorFeatures@@AEAAXXZ; CopyAcceleratorFeatures::UpdateCancellableCopySupport(void)
0x14001d9a6  nop
0x14001d9a7  mov     rcx, [rbp+var_18]; void *
0x14001d9ab  test    rcx, rcx
0x14001d9ae  jz      short loc_14001D9B5
0x14001d9b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d9b5  xor     eax, eax
0x14001d9b7  mov     rcx, [rbp+var_8]
0x14001d9bb  xor     rcx, rsp; StackCookie
0x14001d9be  call    __security_check_cookie
0x14001d9c3  lea     r11, [rsp+50h+var_s0]
0x14001d9c8  mov     rbx, [r11+28h]
0x14001d9cc  mov     rsi, [r11+30h]
0x14001d9d0  mov     rdi, [r11+38h]
0x14001d9d4  mov     rsp, r11
0x14001d9d7  pop     r14
0x14001d9d9  pop     r12
0x14001d9db  pop     rbp
0x14001d9dc  retn
```
