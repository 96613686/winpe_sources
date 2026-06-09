# CProcessStateManager::get_ShouldAnimateLogonBackgroundImage(uchar *)

- ea: `0x1800046d0`
- end: `0x180004b69`
- name: `?get_ShouldAnimateLogonBackgroundImage@CProcessStateManager@@UEAAJPEAE@Z`
- size: `1177`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800046d0`
- `0x180004b70`
- `0x180004c00`
- `0x18000b290`
- `0x18000ba60`
- `0x18000bac8`
- `0x18000bd70`
- `0x1800266a4`
- `0x180043c64`
- `0x18005d4e8`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800048db`
- `KERNEL32!LocalFree` at `0x1800048fb`
- `KERNEL32!LocalFree` at `0x18000492a`
- `KERNEL32!LocalFree` at `0x1800048db`
- `KERNEL32!LocalFree` at `0x1800048fb`
- `KERNEL32!LocalFree` at `0x18000492a`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800049d1`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800049d1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004a0e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004a68`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004a0e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004a68`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004a20`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004aff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004a20`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004aff`
- `KERNEL32!SetLastError` at `0x1800049e8`
- `KERNEL32!SetLastError` at `0x1800049e8`
- `KERNEL32!GetLastError` at `0x1800049b8`
- `KERNEL32!GetLastError` at `0x1800049b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004806`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800048c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800048c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004836`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004836`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004814`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004814`

## string_xrefs

- `0x180004866`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProcessStateManager::get_ShouldAnimateLogonBackgroundImage(
        HSTRING *this,
        bool *a2,
        __int64 a3,
        unsigned int a4)
{
  int v6; // edi
  unsigned __int64 i; // rcx
  signed __int32 v8; // edx
  BOOL v9; // r14d
  unsigned __int32 v10; // eax
  HSTRING v12; // rcx
  const WCHAR *StringRawBuffer; // rax
  const char *v14; // r9
  signed int v15; // ebx
  LSTATUS ValueW; // eax
  bool v17; // al
  unsigned int v18; // ebx
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  void (__fastcall *v21)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  unsigned int v22; // edx
  wil *v23; // rcx
  const char *pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v27; // [rsp+5Ch] [rbp-A4h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v30[4]; // [rsp+78h] [rbp-88h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *a2 = 0;
  v6 = *(_DWORD *)Feature_ALB__descriptor;
  if ( (*(_DWORD *)Feature_ALB__descriptor & 4) == 0 )
  {
    StringSid[0] = *(LPWSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ALB>::GetCachedFeatureEnabledState(
                                this,
                                &Sid);
    LOWORD(v6) = StringSid[0];
  }
  pcbData = 0;
  v27 = 3;
  pvData = 3;
  *(_OWORD *)v30 = 0;
  for ( i = (unsigned int)dword_1800D4420; ; i = v10 )
  {
    v8 = i | 2;
    v9 = ((unsigned int)i | 2) == i;
    if ( ((unsigned int)i | 2) != (_DWORD)i )
      v8 = i | 3;
    v10 = _InterlockedCompareExchange(&dword_1800D4420, v8, i);
    if ( (_DWORD)i == v10 )
      break;
  }
  LOBYTE(i) = (i & 1) == 0;
  if ( ((unsigned __int8)i & ((v8 & 1) != 0)) != 0
    && wil::details::g_enabledStateManager
    && !wil::ProcessShutdownInProgress((wil *)i) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      if ( !wil::ProcessShutdownInProgress(v23) )
      {
        StringSid[0] = (LPWSTR)28825948;
        StringSid[1] = (LPWSTR)&dword_1800D4420;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800D35D8, StringSid, 0x10u);
        if ( !byte_1800D35D0 )
        {
          if ( !qword_1800D35C8 )
          {
            LastError = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &qword_1800D35C8,
              ThreadpoolTimer);
            SetLastError(LastError);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&qword_1800D35C8, &byte_1800D35D0, 300000);
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v30[1] )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1B7D95C, v30[2], v30[1], a4, pdwType);
  if ( !v9 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800D3620 )
    {
      qword_1800D3620 = 0;
      v21 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v21 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v21(&qword_1800D3620, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v6 & 0x400) != 0 )
  {
    v22 = 2;
    if ( (v6 & 0x800) != 0 )
      v22 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x1B7D95C, v22, 0, a4, pdwType);
  }
  if ( !v9 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(28825948, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(28825948, &pcbData, 0, 1, &pvData, 0, 0, 1);
  }
  v12 = this[51];
  if ( !v12 )
    return 0;
  Sid = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
  if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) )
  {
    pvData = 0;
    StringSid[0] = 0;
    if ( !ConvertSidToStringSidW(Sid, StringSid) && (int)ResultFromKnownLastError() < 0 )
      goto LABEL_24;
    v15 = StringCchPrintfW(
            SubKey,
            0x104u,
            L"%s\\%s\\%s\\%s",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
            StringSid[0],
            L"AnyoneRead",
            L"LockScreen");
    if ( v15 >= 0 )
    {
      pcbData = 4;
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"BackgroundImage2", 0x10u, 0, &pvData, &pcbData);
      v15 = ValueW;
      if ( ValueW > 0 )
        v15 = (unsigned __int16)ValueW | 0x80070000;
    }
    LocalFree(StringSid[0]);
    if ( v15 >= 0 )
      v17 = pvData != 0;
    else
LABEL_24:
      v17 = 1;
    *a2 = v17;
    if ( Sid )
      LocalFree(Sid);
    return 0;
  }
  v18 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x24F,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
          v14);
  if ( Sid )
    LocalFree(Sid);
  return v18;
}

```

## disassembly

```asm
0x1800046d0  mov     [rsp-8+arg_10], rbx
0x1800046d5  mov     [rsp-8+arg_18], rsi
0x1800046da  push    rbp
0x1800046db  push    rdi
0x1800046dc  push    r13
0x1800046de  push    r14
0x1800046e0  push    r15
0x1800046e2  lea     rbp, [rsp-1B0h]
0x1800046ea  sub     rsp, 2B0h
0x1800046f1  mov     rax, cs:__security_cookie
0x1800046f8  xor     rax, rsp
0x1800046fb  mov     [rbp+1D0h+var_30], rax
0x180004702  mov     rsi, rdx
0x180004705  mov     r15, rcx
0x180004708  mov     byte ptr [rdx], 0
0x18000470b  mov     rax, cs:Feature_ALB__descriptor
0x180004712  mov     edi, [rax]
0x180004714  test    dil, 4
0x180004718  jz      loc_180004AD2
0x18000471e  xor     r13d, r13d
0x180004721  mov     [rsp+2D0h+var_278], r13d
0x180004726  mov     [rsp+2D0h+var_274], 3
0x18000472d  mov     [rsp+2D0h+var_280], 3
0x180004735  xorps   xmm0, xmm0
0x180004738  movups  xmmword ptr [rsp+2D0h+var_258], xmm0
0x18000473d  mov     ecx, cs:dword_1800D4420
0x180004743  mov     edx, ecx
0x180004745  or      edx, 2
0x180004748  mov     r14d, r13d
0x18000474b  cmp     edx, ecx
0x18000474d  setz    r14b
0x180004751  mov     eax, edx
0x180004753  or      eax, 1
0x180004756  cmp     edx, ecx
0x180004758  cmovnz  edx, eax
0x18000475b  mov     eax, ecx
0x18000475d  lock cmpxchg cs:dword_1800D4420, edx
0x180004765  jz      short loc_180004798
0x180004767  mov     ecx, eax
0x180004769  jmp     short loc_180004743
0x18000476b  xor     eax, eax
0x18000476d  mov     rcx, [rbp+1D0h+var_30]
0x180004774  xor     rcx, rsp; StackCookie
0x180004777  call    __security_check_cookie
0x18000477c  lea     r11, [rsp+2D0h+var_20]
0x180004784  mov     rbx, [r11+40h]
0x180004788  mov     rsi, [r11+48h]
0x18000478c  mov     rsp, r11
0x18000478f  pop     r15
0x180004791  pop     r14
0x180004793  pop     r13
0x180004795  pop     rdi
0x180004796  pop     rbp
0x180004797  retn
0x180004798  test    cl, 1
0x18000479b  setz    cl; this
0x18000479e  test    dl, 1
0x1800047a1  setnz   al
0x1800047a4  test    al, cl
0x1800047a6  mov     eax, r13d
0x1800047a9  setnz   al
0x1800047ac  test    eax, eax
0x1800047ae  jz      short loc_1800047BE
0x1800047b0  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800047b6  test    eax, eax
0x1800047b8  jnz     loc_180004AEB
0x1800047be  cmp     [rsp+2D0h+var_258+4], 0
0x1800047c3  ja      loc_180004B25
0x1800047c9  test    r14d, r14d
0x1800047cc  jnz     short loc_1800047DC
0x1800047ce  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800047d4  test    eax, eax
0x1800047d6  jnz     loc_180004A19
0x1800047dc  bt      edi, 0Ah
0x1800047e0  jb      loc_180004A73
0x1800047e6  test    r14d, r14d
0x1800047e9  jz      loc_180004946
0x1800047ef  mov     rcx, [r15+198h]; string
0x1800047f6  test    rcx, rcx
0x1800047f9  jz      loc_18000476B
0x1800047ff  mov     [rsp+2D0h+Sid], r13
0x180004804  xor     edx, edx; length
0x180004806  call    cs:__imp_WindowsGetStringRawBuffer
0x18000480c  lea     rdx, [rsp+2D0h+Sid]; Sid
0x180004811  mov     rcx, rax; StringSid
0x180004814  call    cs:__imp_ConvertStringSidToSidW
0x18000481a  test    eax, eax
0x18000481c  jz      loc_180004906
0x180004822  mov     [rsp+2D0h+var_280], r13d
0x180004827  mov     [rsp+2D0h+StringSid], r13
0x18000482c  lea     rdx, [rsp+2D0h+StringSid]; StringSid
0x180004831  mov     rcx, [rsp+2D0h+Sid]; Sid
0x180004836  call    cs:__imp_ConvertSidToStringSidW
0x18000483c  test    eax, eax
0x18000483e  jz      loc_180004937
0x180004844  mov     rcx, [rsp+2D0h+StringSid]
0x180004849  lea     rax, aLockscreen; "LockScreen"
0x180004850  mov     [rsp+2D0h+pcbData], rax
0x180004855  mov     rax, cs:off_18009E008; "AnyoneRead"
0x18000485c  mov     [rsp+2D0h+pvData], rax
0x180004861  mov     [rsp+2D0h+pdwType], rcx
0x180004866  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000486d  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180004874  mov     edx, 104h; unsigned __int64
0x180004879  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18000487d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004882  mov     ebx, eax
0x180004884  test    eax, eax
0x180004886  js      short loc_1800048D6
0x180004888  mov     [rsp+2D0h+var_278], 4
0x180004890  lea     rax, [rsp+2D0h+var_278]
0x180004895  mov     [rsp+2D0h+pcbData], rax; pcbData
0x18000489a  lea     rax, [rsp+2D0h+var_280]
0x18000489f  mov     [rsp+2D0h+pvData], rax; pvData
0x1800048a4  mov     [rsp+2D0h+pdwType], r13; pdwType
0x1800048a9  mov     r9d, 10h; dwFlags
0x1800048af  lea     r8, aBackgroundimag; "BackgroundImage2"
0x1800048b6  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800048ba  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800048c1  call    cs:__imp_RegGetValueW
0x1800048c7  mov     ebx, eax
0x1800048c9  test    eax, eax
0x1800048cb  jle     short loc_1800048D6
0x1800048cd  movzx   ebx, ax
0x1800048d0  or      ebx, 80070000h
0x1800048d6  mov     rcx, [rsp+2D0h+StringSid]; hMem
0x1800048db  call    cs:__imp_LocalFree
0x1800048e1  test    ebx, ebx
0x1800048e3  jns     loc_180004B5B
0x1800048e9  mov     al, 1
0x1800048eb  mov     [rsi], al
0x1800048ed  mov     rcx, [rsp+2D0h+Sid]; hMem
0x1800048f2  test    rcx, rcx
0x1800048f5  jz      loc_18000476B
0x1800048fb  call    cs:__imp_LocalFree
0x180004901  jmp     loc_18000476B
0x180004906  mov     rcx, [rbp+1D8h]; this
0x18000490d  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180004914  mov     edx, 24Fh; void *
0x180004919  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000491e  mov     ebx, eax
0x180004920  mov     rcx, [rsp+2D0h+Sid]; hMem
0x180004925  test    rcx, rcx
0x180004928  jz      short loc_180004930
0x18000492a  call    cs:__imp_LocalFree
0x180004930  mov     eax, ebx
0x180004932  jmp     loc_18000476D
0x180004937  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000493c  test    eax, eax
0x18000493e  jns     loc_180004844
0x180004944  jmp     short loc_1800048E9
0x180004946  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000494d  test    rax, rax
0x180004950  jz      short loc_180004964
0x180004952  mov     r8b, 3
0x180004955  mov     edx, 2
0x18000495a  mov     ecx, 1B7D95Ch
0x18000495f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004964  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000496b  test    rax, rax
0x18000496e  jz      loc_1800047EF
0x180004974  mov     [rsp+2D0h+var_298], 1
0x18000497d  mov     byte ptr [rsp+2D0h+pcbData], 0
0x180004982  mov     [rsp+2D0h+pvData], r13
0x180004987  lea     rdx, [rsp+2D0h+var_280]
0x18000498c  mov     [rsp+2D0h+pdwType], rdx
0x180004991  mov     r9d, 1
0x180004997  xor     r8d, r8d
0x18000499a  lea     rdx, [rsp+2D0h+var_278]
0x18000499f  mov     ecx, 1B7D95Ch
0x1800049a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a9  jmp     loc_1800047EF
0x1800049ae  cmp     cs:qword_1800D35C8, 0
0x1800049b6  jnz     short loc_1800049EE
0x1800049b8  call    cs:__imp_GetLastError
0x1800049be  mov     ebx, eax
0x1800049c0  xor     r8d, r8d; pcbe
0x1800049c3  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800049ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800049d1  call    cs:__imp_CreateThreadpoolTimer
0x1800049d7  mov     rdx, rax
0x1800049da  lea     rcx, qword_1800D35C8
0x1800049e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800049e6  mov     ecx, ebx; dwErrCode
0x1800049e8  call    cs:__imp_SetLastError
0x1800049ee  mov     r8d, 493E0h
0x1800049f4  lea     rdx, byte_1800D35D0
0x1800049fb  lea     rcx, qword_1800D35C8
0x180004a02  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180004a07  lea     rcx, SRWLock; SRWLock
0x180004a0e  call    cs:__imp_ReleaseSRWLockExclusive
0x180004a14  jmp     loc_1800047BE
0x180004a19  lea     rcx, SRWLock; SRWLock
0x180004a20  call    cs:__imp_AcquireSRWLockExclusive
0x180004a26  cmp     cs:qword_1800D3620, 0
0x180004a2e  jnz     short loc_180004A61
0x180004a30  mov     cs:qword_1800D3620, r13
0x180004a37  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004a3e  test    rax, rax
0x180004a41  jz      loc_180004B3C
0x180004a47  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004a4e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180004a55  lea     rcx, qword_1800D3620
0x180004a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a61  lea     rcx, SRWLock; SRWLock
0x180004a68  call    cs:__imp_ReleaseSRWLockExclusive
0x180004a6e  jmp     loc_1800047DC
0x180004a73  mov     edx, 2; unsigned int
0x180004a78  bt      edi, 0Bh
0x180004a7c  jb      loc_180004B51
0x180004a82  xor     r8d, r8d; unsigned int
0x180004a85  mov     ecx, 1B7D95Ch; this
0x180004a8a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004a8f  jmp     loc_1800047E6
0x180004a94  mov     [rsp+2D0h+StringSid], 1B7D95Ch
0x180004a9d  lea     rax, dword_1800D4420
0x180004aa4  mov     [rsp+2D0h+var_260], rax
0x180004aa9  mov     r8d, 10h; unsigned __int64
0x180004aaf  lea     rdx, [rsp+2D0h+StringSid]; void *
0x180004ab4  lea     rcx, qword_1800D35D8; this
0x180004abb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004ac0  cmp     cs:byte_1800D35D0, 0
0x180004ac7  jnz     loc_180004A07
0x180004acd  jmp     loc_1800049AE
0x180004ad2  lea     rdx, [rsp+2D0h+Sid]
0x180004ad7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ALB@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ALB>::GetCachedFeatureEnabledState(void)
0x180004adc  mov     rcx, [rax]
0x180004adf  mov     [rsp+2D0h+StringSid], rcx
0x180004ae4  mov     edi, ecx
0x180004ae6  jmp     loc_18000471E
0x180004aeb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004af0  test    al, al
0x180004af2  jnz     loc_1800047BE
0x180004af8  lea     rcx, SRWLock; SRWLock
0x180004aff  call    cs:__imp_AcquireSRWLockExclusive
0x180004b05  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004b0b  test    eax, eax
0x180004b0d  jz      loc_180004A07
0x180004b13  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004b18  test    al, al
0x180004b1a  jnz     loc_180004A07
0x180004b20  jmp     loc_180004A94
0x180004b25  mov     r8d, [rsp+2D0h+var_258+4]; unsigned int
0x180004b2a  mov     edx, [rbp+1D0h+var_258+8]; unsigned int
0x180004b2d  mov     ecx, 1B7D95Ch; this
0x180004b32  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004b37  jmp     loc_1800047C9
0x180004b3c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004b43  test    rax, rax
0x180004b46  jz      loc_180004A61
0x180004b4c  jmp     loc_180004A47
0x180004b51  mov     edx, 80000002h
0x180004b56  jmp     loc_180004A82
0x180004b5b  cmp     [rsp+2D0h+var_280], 0
0x180004b60  setnz   al
0x180004b63  jmp     loc_1800048EB
```
