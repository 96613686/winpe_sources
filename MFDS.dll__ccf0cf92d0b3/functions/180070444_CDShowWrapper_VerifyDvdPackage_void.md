# CDShowWrapper::VerifyDvdPackage(void)

- ea: `0x180070444`
- end: `0x180070776`
- name: `?VerifyDvdPackage@CDShowWrapper@@IEAAJXZ`
- size: `818`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180085fb0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x180070444`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800705de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007060b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800705de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007060b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x180070480`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x180070480`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800706ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800706ab`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::VerifyDvdPackage(CDShowWrapper *this)
{
  unsigned int v2; // ebx
  LONG CurrentPackageFamilyName; // esi
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 *v7; // rax
  __int128 v8; // xmm0
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rdi
  int v14; // ebx
  __int128 *v15; // rax
  __int128 v16; // xmm0
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _BYTE v20[4]; // [rsp+30h] [rbp-79h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+34h] [rbp-75h] BYREF
  _BYTE v22[24]; // [rsp+38h] [rbp-71h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+50h] [rbp-59h] BYREF

  packageFamilyNameLength = 65;
  v2 = 0;
  CurrentPackageFamilyName = GetCurrentPackageFamilyName(&packageFamilyNameLength, packageFamilyName);
  if ( CurrentPackageFamilyName )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CDShowWrapper::VerifyDvdPackage", 2847);
    v4 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
      v7 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                         *((_QWORD *)this + 60),
                         v22);
      v4 = CallStackTracing::s_wpInstance;
      v8 = *v7;
      *((_DWORD *)ThreadRelativeContext + 504) = v6;
      *((_OWORD *)ThreadRelativeContext + 125) = v8;
    }
    if ( CurrentPackageFamilyName > 0 )
      v2 = (unsigned __int16)CurrentPackageFamilyName | 0x80070000;
    else
      v2 = CurrentPackageFamilyName;
    if ( !v4 )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)v10 + 499) != v2 )
        CallStackContext::TraceFailure(v10, "CDShowWrapper::VerifyDvdPackage", 2847, v2);
    }
    if ( !g_wppLevels )
      goto LABEL_34;
    v11 = 242;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v2);
LABEL_34:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
    return v2;
  }
  if ( CompareStringOrdinal(packageFamilyName, -1, L"Microsoft.WindowsDVDPlayer_8wekyb3d8bbwe", -1, 1) != 2
    && CompareStringOrdinal(packageFamilyName, -1, L"Microsoft.WindowsDVDPlayer2_8wekyb3d8bbwe", -1, 1) != 2 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CDShowWrapper::VerifyDvdPackage", 2852);
    v12 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
      v15 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                          *((_QWORD *)this + 60),
                          v22);
      v12 = CallStackTracing::s_wpInstance;
      v16 = *v15;
      *((_DWORD *)v13 + 504) = v14;
      *((_OWORD *)v13 + 125) = v16;
    }
    v2 = -2147023728;
    if ( !v12 )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v18 + 499) != -2147023728 )
        CallStackContext::TraceFailure(v18, "CDShowWrapper::VerifyDvdPackage", 2852, -2147023728);
    }
    if ( !g_wppLevels )
      goto LABEL_34;
    v11 = 243;
    goto LABEL_33;
  }
  return v2;
}

```

## disassembly

```asm
0x180070444  mov     [rsp-8+arg_8], rbx
0x180070449  mov     [rsp-8+arg_10], rsi
0x18007044e  push    rbp
0x18007044f  push    rdi
0x180070450  push    r14
0x180070452  lea     rbp, [rsp-47h]
0x180070457  sub     rsp, 0F0h
0x18007045e  mov     rax, cs:__security_cookie
0x180070465  xor     rax, rsp
0x180070468  mov     [rbp+57h+var_20], rax
0x18007046c  mov     r14, rcx
0x18007046f  mov     [rbp+57h+packageFamilyNameLength], 41h ; 'A'
0x180070476  lea     rcx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18007047a  xor     ebx, ebx
0x18007047c  lea     rdx, [rbp+57h+packageFamilyName]; packageFamilyName
0x180070480  call    cs:__imp_GetCurrentPackageFamilyName
0x180070487  nop     dword ptr [rax+rax+00h]
0x18007048c  mov     esi, eax
0x18007048e  test    eax, eax
0x180070490  jz      loc_1800705C3
0x180070496  mov     r8d, 0B1Fh; int
0x18007049c  lea     rdx, aCdshowwrapperV; "CDShowWrapper::VerifyDvdPackage"
0x1800704a3  lea     rcx, [rbp+57h+var_D0]; this
0x1800704a7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800704ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800704b3  cmp     [rcx+8], bl
0x1800704b6  jz      short loc_180070513
0x1800704b8  cmp     [r14+1E0h], rbx
0x1800704bf  jz      short loc_180070513
0x1800704c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800704c6  mov     rcx, [r14+1E0h]
0x1800704cd  mov     rdi, rax
0x1800704d0  mov     rax, [rcx]
0x1800704d3  mov     rax, [rax+128h]
0x1800704da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704df  mov     rcx, [r14+1E0h]
0x1800704e6  lea     rdx, [rbp+57h+var_C8]
0x1800704ea  mov     ebx, eax
0x1800704ec  mov     rax, [rcx]
0x1800704ef  mov     rax, [rax+118h]
0x1800704f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070502  movups  xmm0, xmmword ptr [rax]
0x180070505  mov     [rdi+7E0h], ebx
0x18007050b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180070513  test    esi, esi
0x180070515  jg      short loc_18007051B
0x180070517  mov     ebx, esi
0x180070519  jmp     short loc_180070524
0x18007051b  movzx   ebx, si
0x18007051e  or      ebx, 80070000h
0x180070524  test    ebx, ebx
0x180070526  jns     loc_1800705BA
0x18007052c  test    rcx, rcx
0x18007052f  jnz     short loc_180070578
0x180070531  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070538  nop     dword ptr [rax+rax+00h]
0x18007053d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070544  mov     rcx, rax
0x180070547  test    rax, rax
0x18007054a  jz      short loc_18007056A
0x18007054c  mov     rax, [rax]
0x18007054f  mov     edx, 7F0h
0x180070554  mov     rax, [rax+8]
0x180070558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007055d  test    eax, eax
0x18007055f  jz      short loc_18007056A
0x180070561  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070568  jmp     short loc_180070578
0x18007056a  lea     rcx, qword_1800EB130; this
0x180070571  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070578  cmp     byte ptr [rcx+8], 0
0x18007057c  jz      short loc_1800705A3
0x18007057e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070583  cmp     [rax+7CCh], ebx
0x180070589  jz      short loc_1800705A3
0x18007058b  mov     r9d, ebx; int
0x18007058e  lea     rdx, aCdshowwrapperV; "CDShowWrapper::VerifyDvdPackage"
0x180070595  mov     r8d, 0B1Fh; int
0x18007059b  mov     rcx, rax; this
0x18007059e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800705a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800705aa  jb      loc_180070746
0x1800705b0  mov     edx, 0F2h
0x1800705b5  jmp     loc_180070728
0x1800705ba  lea     rcx, [rbp+57h+var_D0]; this
0x1800705be  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800705c3  or      edi, 0FFFFFFFFh
0x1800705c6  mov     [rsp+100h+bIgnoreCase], 1; bIgnoreCase
0x1800705ce  mov     r9d, edi; cchCount2
0x1800705d1  lea     r8, aMicrosoftWindo; "Microsoft.WindowsDVDPlayer_8wekyb3d8bbw"...
0x1800705d8  mov     edx, edi; cchCount1
0x1800705da  lea     rcx, [rbp+57h+packageFamilyName]; lpString1
0x1800705de  call    cs:__imp_CompareStringOrdinal
0x1800705e5  nop     dword ptr [rax+rax+00h]
0x1800705ea  cmp     eax, 2
0x1800705ed  jz      loc_18007074F
0x1800705f3  mov     r9d, edi; cchCount2
0x1800705f6  mov     [rsp+100h+bIgnoreCase], 1; bIgnoreCase
0x1800705fe  lea     r8, aMicrosoftWindo_0; "Microsoft.WindowsDVDPlayer2_8wekyb3d8bb"...
0x180070605  mov     edx, edi; cchCount1
0x180070607  lea     rcx, [rbp+57h+packageFamilyName]; lpString1
0x18007060b  call    cs:__imp_CompareStringOrdinal
0x180070612  nop     dword ptr [rax+rax+00h]
0x180070617  cmp     eax, 2
0x18007061a  jz      loc_18007074F
0x180070620  mov     esi, 0B24h
0x180070625  lea     rdx, aCdshowwrapperV; "CDShowWrapper::VerifyDvdPackage"
0x18007062c  mov     r8d, esi; int
0x18007062f  lea     rcx, [rbp+57h+var_D0]; this
0x180070633  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180070638  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18007063f  cmp     byte ptr [rcx+8], 0
0x180070643  jz      short loc_1800706A1
0x180070645  cmp     qword ptr [r14+1E0h], 0
0x18007064d  jz      short loc_1800706A1
0x18007064f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070654  mov     rcx, [r14+1E0h]
0x18007065b  mov     rdi, rax
0x18007065e  mov     rax, [rcx]
0x180070661  mov     rax, [rax+128h]
0x180070668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007066d  mov     rcx, [r14+1E0h]
0x180070674  lea     rdx, [rbp+57h+var_C8]
0x180070678  mov     ebx, eax
0x18007067a  mov     rax, [rcx]
0x18007067d  mov     rax, [rax+118h]
0x180070684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070689  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070690  movups  xmm0, xmmword ptr [rax]
0x180070693  mov     [rdi+7E0h], ebx
0x180070699  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800706a1  mov     ebx, 80070490h
0x1800706a6  test    rcx, rcx
0x1800706a9  jnz     short loc_1800706F2
0x1800706ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800706b2  nop     dword ptr [rax+rax+00h]
0x1800706b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800706be  mov     rcx, rax
0x1800706c1  test    rax, rax
0x1800706c4  jz      short loc_1800706E4
0x1800706c6  mov     rax, [rax]
0x1800706c9  mov     edx, 7F0h
0x1800706ce  mov     rax, [rax+8]
0x1800706d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800706d7  test    eax, eax
0x1800706d9  jz      short loc_1800706E4
0x1800706db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800706e2  jmp     short loc_1800706F2
0x1800706e4  lea     rcx, qword_1800EB130; this
0x1800706eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800706f2  cmp     byte ptr [rcx+8], 0
0x1800706f6  jz      short loc_18007071A
0x1800706f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800706fd  cmp     [rax+7CCh], ebx
0x180070703  jz      short loc_18007071A
0x180070705  mov     r9d, ebx; int
0x180070708  lea     rdx, aCdshowwrapperV; "CDShowWrapper::VerifyDvdPackage"
0x18007070f  mov     r8d, esi; int
0x180070712  mov     rcx, rax; this
0x180070715  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007071a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070721  jb      short loc_180070746
0x180070723  mov     edx, 0F3h
0x180070728  mov     rcx, cs:WPP_GLOBAL_Control
0x18007072f  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180070736  mov     r9, r14
0x180070739  mov     [rsp+100h+bIgnoreCase], ebx
0x18007073d  mov     rcx, [rcx+10h]
0x180070741  call    WPP_SF_qD
0x180070746  lea     rcx, [rbp+57h+var_D0]; this
0x18007074a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007074f  mov     eax, ebx
0x180070751  mov     rcx, [rbp+57h+var_20]
0x180070755  xor     rcx, rsp; StackCookie
0x180070758  call    __security_check_cookie
0x18007075d  lea     r11, [rsp+100h+var_10]
0x180070765  mov     rbx, [r11+28h]
0x180070769  mov     rsi, [r11+30h]
0x18007076d  mov     rsp, r11
0x180070770  pop     r14
0x180070772  pop     rdi
0x180070773  pop     rbp
0x180070774  retn
```
