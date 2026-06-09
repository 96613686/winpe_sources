# GetHostInfoForActivation(IApplicationInstanceManager *,HostResolverRequest const &,ACTIVATION_PHASE *,ActivationHostInfo *)

- ea: `0x180023f20`
- end: `0x180024473`
- name: `?GetHostInfoForActivation@@YAJPEAUIApplicationInstanceManager@@AEBUHostResolverRequest@@PEAW4ACTIVATION_PHASE@@PEAUActivationHostInfo@@@Z`
- size: `1363`
- prototype: `int(struct IApplicationInstanceManager *, const struct HostResolverRequest *, enum ACTIVATION_PHASE *, struct ActivationHostInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180023f20`
- `0x180024480`
- `0x180027ce8`
- `0x180044408`
- `0x180044514`
- `0x180054bb4`
- `0x18005ae90`
- `0x18005ba40`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002441b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002441b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002442e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002442e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002426d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002427a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002426d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002427a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800242a0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800242a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800242f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002445d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800242f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002445d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024468`
- `ntdll!NtQueryInformationToken` at `0x180023f9b`
- `ntdll!NtQueryInformationToken` at `0x180023f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800240e0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180023f6a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180023f6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetHostInfoForActivation(
        struct IApplicationInstanceManager *a1,
        const struct HostResolverRequest *a2,
        enum ACTIVATION_PHASE *a3,
        struct ActivationHostInfo *a4)
{
  unsigned int HostInfo; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rbx
  __int64 v11; // r15
  __int64 v12; // r8
  void *v13; // rdi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r14
  int v16; // edi
  _WORD *v18; // rax
  _WORD *v19; // r10
  unsigned __int16 *v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int16 *v22; // r8
  __int64 v23; // r9
  unsigned __int16 v24; // ax
  __int64 v25; // r14
  bool v26; // cf
  __int64 v27; // rdx
  HANDLE v28; // rcx
  HANDLE CurrentProcess; // rbx
  void *v30; // rdi
  HANDLE v31; // rax
  BOOL v32; // ebx
  const char *v33; // r9
  int v34; // eax
  int AppSelectedHostInfo; // eax
  DWORD LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthc; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v42[2]; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TargetHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v44; // [rsp+70h] [rbp-90h]
  ULONG v45; // [rsp+80h] [rbp-80h] BYREF
  int v46[3]; // [rsp+84h] [rbp-7Ch] BYREF
  GUID pguid; // [rsp+90h] [rbp-70h] BYREF
  __int64 TokenInformation[12]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v49[232]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  TokenHandle = 0;
  HostInfo = UMgrQueryUserToken(*((_QWORD *)a2 + 1), &TokenHandle);
  if ( (HostInfo & 0x80000000) != 0 )
  {
    v27 = 201;
    goto LABEL_34;
  }
  v45 = 0;
  v9 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &v45);
  if ( v9 < 0 )
  {
    HostInfo = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0xCD,
                 (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
                 (const char *)(unsigned int)v9,
                 ReturnLengtha);
LABEL_35:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v28 = TokenHandle;
LABEL_48:
      CloseHandle(v28);
    }
    return HostInfo;
  }
  v10 = *((_QWORD *)a2 + 9);
  if ( v10 != -1 && *((_DWORD *)a2 + 15) != 4 && (*((_DWORD *)a2 + 14) & 0x600000) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
      (const char *)0x80070057LL,
      ReturnLengtha);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 2147942487LL;
  }
  v11 = TokenInformation[0];
  memset_0(v49, 0, sizeof(v49));
  v46[0] = 464;
  *(_QWORD *)v42 = v10;
  pguid = (GUID)*((_OWORD *)a2 + 5);
  *(_DWORD *)a3 = 36;
  HostInfo = GetHostInfo((__int64)a2, v11, v12, (unsigned __int64 *)v42, &pguid, (__int64)v46, v49);
  if ( (HostInfo & 0x80000000) != 0 )
  {
    v27 = 225;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
      (const char *)HostInfo,
      ReturnLength);
    goto LABEL_35;
  }
  *(_DWORD *)a3 = 0;
  if ( *((_DWORD *)a2 + 15) == 1 )
    goto LABEL_6;
  v34 = (*(__int64 (__fastcall **)(struct IApplicationInstanceManager *, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(
          a1,
          *(_QWORD *)v42,
          *((_QWORD *)a2 + 8));
  HostInfo = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
      (const char *)(unsigned int)v34,
      ReturnLength);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
      (const char *)HostInfo,
      ReturnLengthc);
    v28 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_48;
    return HostInfo;
  }
  if ( *((_DWORD *)a2 + 15) != 1 )
  {
    LODWORD(TargetHandle[0]) = 0;
    (*(void (__fastcall **)(struct IApplicationInstanceManager *, _QWORD, _QWORD, HANDLE *))(*(_QWORD *)a1 + 24LL))(
      a1,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 3),
      TargetHandle);
    if ( LODWORD(TargetHandle[0]) )
    {
      *(GUID *)TargetHandle = pguid;
      AppSelectedHostInfo = GetAppSelectedHostInfo(
                              (_DWORD)a1,
                              (_DWORD)a2,
                              v11,
                              v42[0],
                              (__int64)TargetHandle,
                              (__int64)v49,
                              *((_QWORD *)a2 + 12),
                              (__int64)a3,
                              (__int64)a4);
      HostInfo = AppSelectedHostInfo;
      if ( AppSelectedHostInfo < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
          (const char *)(unsigned int)AppSelectedHostInfo,
          ReturnLengthb);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return HostInfo;
      }
      goto LABEL_30;
    }
  }
LABEL_6:
  *(_QWORD *)a4 = *(_QWORD *)v42;
  *(GUID *)((char *)a4 + 8) = pguid;
  if ( *((_QWORD *)a2 + 12) )
  {
    TargetHandle[0] = (char *)a4 + 32;
    TargetHandle[1] = 0;
    v44 = 1;
    CurrentProcess = GetCurrentProcess();
    v30 = (void *)*((_QWORD *)a2 + 12);
    v31 = GetCurrentProcess();
    v32 = DuplicateHandle(v31, v30, CurrentProcess, &TargetHandle[1], 0x100400u, 0, 0);
    if ( v44 )
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        TargetHandle[0],
        TargetHandle[1]);
    if ( !v32 )
    {
      HostInfo = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0xF3,
                   (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
                   v33);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return HostInfo;
    }
  }
  v13 = (void *)*((_QWORD *)a4 + 3);
  if ( v13 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v13);
    SetLastError(LastError);
  }
  v14 = -1;
  do
    ++v14;
  while ( v49[v14] );
  *((_QWORD *)a4 + 3) = 0;
  v15 = v14 + 1;
  if ( v14 + 1 < v14 || !is_mul_ok(v15, 2u) )
  {
    v16 = -2147024362;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
      (const char *)(unsigned int)v16,
      ReturnLength);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)v16;
  }
  v18 = CoTaskMemAlloc(2 * v15);
  v19 = v18;
  *((_QWORD *)a4 + 3) = v18;
  v16 = -2147024882;
  if ( v18 )
    v16 = 0;
  if ( v16 < 0 )
    goto LABEL_13;
  if ( (v18 || v14 == -1) && v15 <= 0x7FFFFFFF )
  {
    if ( v14 >= 0x7FFFFFFF )
    {
      if ( v14 != -1 )
        *v18 = 0;
    }
    else
    {
      v20 = v49;
      v21 = v14 + 1;
      v22 = v18;
      v23 = 0;
      while ( v14 )
      {
        v24 = *v20;
        if ( !*v20 )
        {
          if ( !v21 )
          {
LABEL_27:
            *(v22 - 1) = 0;
            goto LABEL_30;
          }
          break;
        }
        ++v20;
        *v22++ = v24;
        --v14;
        ++v23;
        if ( !--v21 )
          goto LABEL_27;
      }
      *v22 = 0;
      v26 = v15 == v23;
      v25 = v15 - v23;
      if ( !v26 && v25 != 1 && (unsigned __int64)(2 * v25) > 2 )
        memset_0(&v19[v23 + 1], 0, 2 * v25 - 2);
    }
  }
  else
  {
    *v18 = 0;
  }
LABEL_30:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180023f20  push    rbp
0x180023f22  push    rbx
0x180023f23  push    rsi
0x180023f24  push    rdi
0x180023f25  push    r12
0x180023f27  push    r13
0x180023f29  push    r14
0x180023f2b  push    r15
0x180023f2d  lea     rbp, [rsp-1E8h]
0x180023f35  sub     rsp, 2E8h
0x180023f3c  mov     rax, cs:__security_cookie
0x180023f43  xor     rax, rsp
0x180023f46  mov     [rbp+220h+var_50], rax
0x180023f4d  mov     rsi, r9
0x180023f50  mov     r14, r8
0x180023f53  mov     rdi, rdx
0x180023f56  mov     r12, rcx
0x180023f59  xor     r13d, r13d
0x180023f5c  mov     [rsp+320h+TokenHandle], r13
0x180023f61  lea     rdx, [rsp+320h+TokenHandle]
0x180023f66  mov     rcx, [rdi+8]
0x180023f6a  call    cs:__imp_UMgrQueryUserToken
0x180023f70  mov     ebx, eax
0x180023f72  test    eax, eax
0x180023f74  js      loc_1800241E3
0x180023f7a  mov     [rbp+220h+var_2A0], r13d
0x180023f7e  lea     rax, [rbp+220h+var_2A0]
0x180023f82  mov     [rsp+320h+ReturnLength], rax; int
0x180023f87  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180023f8d  lea     r8, [rbp+220h+TokenInformation]; TokenInformation
0x180023f91  mov     edx, 1; TokenInformationClass
0x180023f96  mov     rcx, [rsp+320h+TokenHandle]; TokenHandle
0x180023f9b  call    cs:__imp_NtQueryInformationToken
0x180023fa1  test    eax, eax
0x180023fa3  js      loc_1800241C4
0x180023fa9  mov     rbx, [rdi+48h]
0x180023fad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180023fb1  jnz     loc_1800242FD
0x180023fb7  mov     r15, [rbp+220h+TokenInformation]
0x180023fbb  xor     edx, edx; Val
0x180023fbd  mov     r8d, 1D0h; Size
0x180023fc3  lea     rcx, [rbp+220h+var_220]; void *
0x180023fc7  call    memset_0
0x180023fcc  mov     [rbp+220h+var_29C], 1D0h
0x180023fd3  mov     qword ptr [rsp+320h+var_2C8], rbx
0x180023fd8  movups  xmm0, xmmword ptr [rdi+50h]
0x180023fdc  movaps  xmmword ptr [rbp+220h+pguid.Data1], xmm0
0x180023fe0  mov     dword ptr [r14], 24h ; '$'
0x180023fe7  lea     rax, [rbp+220h+var_220]
0x180023feb  mov     qword ptr [rsp+320h+dwOptions], rax; unsigned __int16 *
0x180023ff0  lea     rax, [rbp+220h+var_29C]
0x180023ff4  mov     qword ptr [rsp+320h+bInheritHandle], rax; int
0x180023ff9  lea     rax, [rbp+220h+pguid]
0x180023ffd  mov     [rsp+320h+ReturnLength], rax; int
0x180024002  lea     r9, [rsp+320h+var_2C8]; int
0x180024007  mov     rdx, r15; int
0x18002400a  mov     rcx, rdi; int
0x18002400d  call    GetHostInfo
0x180024012  mov     ebx, eax
0x180024014  test    eax, eax
0x180024016  js      loc_18002418E
0x18002401c  mov     [r14], r13d
0x18002401f  mov     eax, [rdi+3Ch]
0x180024022  cmp     eax, 1
0x180024025  jnz     loc_180024347
0x18002402b  mov     rax, qword ptr [rsp+320h+var_2C8]
0x180024030  mov     [rsi], rax
0x180024033  movaps  xmm0, xmmword ptr [rbp+220h+pguid.Data1]
0x180024037  movups  xmmword ptr [rsi+8], xmm0
0x18002403b  cmp     [rdi+60h], r13
0x18002403f  jnz     loc_18002425A
0x180024045  mov     rdi, [rsi+18h]
0x180024049  test    rdi, rdi
0x18002404c  jnz     loc_18002441B
0x180024052  lea     rax, [rbp+220h+var_220]
0x180024056  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002405d  nop     dword ptr [rax]
0x180024060  inc     rbx
0x180024063  cmp     [rax+rbx*2], r13w
0x180024068  jnz     short loc_180024060
0x18002406a  mov     [rsi+18h], r13
0x18002406e  lea     r14, [rbx+1]
0x180024072  cmp     r14, rbx
0x180024075  jnb     short loc_1800240D0
0x180024077  mov     edi, 80070216h
0x18002407c  mov     rcx, [rbp+228h]; this
0x180024083  mov     r9d, edi; char *
0x180024086  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002408d  mov     edx, 0F5h; void *
0x180024092  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024097  nop
0x180024098  mov     rcx, [rsp+320h+TokenHandle]; hObject
0x18002409d  lea     rdx, [rcx-1]
0x1800240a1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800240a5  jbe     loc_180024468
0x1800240ab  mov     eax, edi
0x1800240ad  mov     rcx, [rbp+220h+var_50]
0x1800240b4  xor     rcx, rsp; StackCookie
0x1800240b7  call    __security_check_cookie
0x1800240bc  add     rsp, 2E8h
0x1800240c3  pop     r15
0x1800240c5  pop     r14
0x1800240c7  pop     r13
0x1800240c9  pop     r12
0x1800240cb  pop     rdi
0x1800240cc  pop     rsi
0x1800240cd  pop     rbx
0x1800240ce  pop     rbp
0x1800240cf  retn
0x1800240d0  mov     eax, 2
0x1800240d5  mul     r14
0x1800240d8  test    rdx, rdx
0x1800240db  jnz     short loc_180024077
0x1800240dd  mov     rcx, rax; cb
0x1800240e0  call    cs:__imp_CoTaskMemAlloc
0x1800240e6  mov     r10, rax
0x1800240e9  mov     [rsi+18h], rax
0x1800240ed  mov     edi, 8007000Eh
0x1800240f2  test    rax, rax
0x1800240f5  cmovnz  edi, r13d
0x1800240f9  test    edi, edi
0x1800240fb  js      loc_18002407C
0x180024101  test    rax, rax
0x180024104  jz      loc_180024439
0x18002410a  cmp     r14, 7FFFFFFFh
0x180024111  ja      loc_180024442
0x180024117  cmp     rbx, 7FFFFFFFh
0x18002411e  jnb     loc_18002444B
0x180024124  test    r14, r14
0x180024127  jz      short loc_180024174
0x180024129  lea     rcx, [rbp+220h+var_220]
0x18002412d  mov     rdx, r14
0x180024130  mov     r8, r10
0x180024133  mov     r9, r13
0x180024136  test    rbx, rbx
0x180024139  jz      short loc_180024167
0x18002413b  movzx   eax, word ptr [rcx]
0x18002413e  test    ax, ax
0x180024141  jz      short loc_180024162
0x180024143  add     rcx, 2
0x180024147  mov     [r8], ax
0x18002414b  add     r8, 2
0x18002414f  dec     rbx
0x180024152  inc     r9
0x180024155  sub     rdx, 1
0x180024159  jnz     short loc_180024136
0x18002415b  mov     [r8-2], r13w
0x180024160  jmp     short loc_180024174
0x180024162  test    rdx, rdx
0x180024165  jz      short loc_18002415B
0x180024167  mov     [r8], r13w
0x18002416b  sub     r14, r9
0x18002416e  cmp     r14, 1
0x180024172  ja      short loc_1800241EA
0x180024174  mov     rcx, [rsp+320h+TokenHandle]; hObject
0x180024179  lea     rax, [rcx-1]
0x18002417d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024181  jbe     loc_18002445D
0x180024187  xor     eax, eax
0x180024189  jmp     loc_1800240AD
0x18002418e  mov     edx, 0E1h; void *
0x180024193  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002419a  mov     r9d, ebx; char *
0x18002419d  mov     rcx, [rbp+228h]; this
0x1800241a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800241a9  nop
0x1800241aa  mov     rax, [rsp+320h+TokenHandle]
0x1800241af  lea     rcx, [rax-1]
0x1800241b3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800241b7  jbe     loc_1800242EF
0x1800241bd  mov     eax, ebx
0x1800241bf  jmp     loc_1800240AD
0x1800241c4  mov     rcx, [rbp+228h]; this
0x1800241cb  mov     r9d, eax; char *
0x1800241ce  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800241d5  mov     edx, 0CDh; void *
0x1800241da  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800241df  mov     ebx, eax
0x1800241e1  jmp     short loc_1800241AA
0x1800241e3  mov     edx, 0C9h
0x1800241e8  jmp     short loc_180024193
0x1800241ea  lea     r8, [r14+r14]
0x1800241ee  cmp     r8, 2
0x1800241f2  jbe     short loc_180024174
0x1800241f4  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800241f8  inc     r9
0x1800241fb  lea     rcx, [r10+r9*2]; void *
0x1800241ff  xor     edx, edx; Val
0x180024201  call    memset_0
0x180024206  jmp     loc_180024174
0x18002420b  mov     rcx, [rbp+228h]; this
0x180024212  mov     r9d, ebx; char *
0x180024215  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002421c  mov     edx, 0BBh; void *
0x180024221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024226  mov     rcx, [rbp+228h]; this
0x18002422d  mov     r9d, ebx; char *
0x180024230  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024237  mov     edx, 0E4h; void *
0x18002423c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024241  nop
0x180024242  mov     rcx, [rsp+320h+TokenHandle]
0x180024247  lea     rax, [rcx-1]
0x18002424b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002424f  ja      loc_1800241BD
0x180024255  jmp     loc_1800242F2
0x18002425a  lea     rax, [rsi+20h]
0x18002425e  mov     [rsp+320h+TargetHandle], rax
0x180024263  mov     [rsp+320h+TargetHandle+8], r13
0x180024268  mov     [rsp+320h+var_2B0], 1
0x18002426d  call    cs:__imp_GetCurrentProcess
0x180024273  mov     rbx, rax
0x180024276  mov     rdi, [rdi+60h]
0x18002427a  call    cs:__imp_GetCurrentProcess
0x180024280  mov     [rsp+320h+dwOptions], r13d; dwOptions
0x180024285  mov     [rsp+320h+bInheritHandle], r13d; bInheritHandle
0x18002428a  mov     dword ptr [rsp+320h+ReturnLength], 100400h; dwDesiredAccess
0x180024292  lea     r9, [rsp+320h+TargetHandle+8]; lpTargetHandle
0x180024297  mov     r8, rbx; hTargetProcessHandle
0x18002429a  mov     rdx, rdi; hSourceHandle
0x18002429d  mov     rcx, rax; hSourceProcessHandle
0x1800242a0  call    cs:__imp_DuplicateHandle
0x1800242a6  mov     ebx, eax
0x1800242a8  cmp     [rsp+320h+var_2B0], r13b
0x1800242ad  jz      short loc_1800242BE
0x1800242af  mov     rdx, [rsp+320h+TargetHandle+8]
0x1800242b4  mov     rcx, [rsp+320h+TargetHandle]
0x1800242b9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800242be  test    ebx, ebx
0x1800242c0  jnz     loc_180024045
0x1800242c6  mov     rcx, [rbp+228h]; this
0x1800242cd  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800242d4  mov     edx, 0F3h; void *
0x1800242d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800242de  mov     ebx, eax
0x1800242e0  lea     rcx, [rsp+320h+TokenHandle]
0x1800242e5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800242ea  jmp     loc_1800241BD
0x1800242ef  mov     rcx, rax; hObject
0x1800242f2  call    cs:__imp_CloseHandle
0x1800242f8  jmp     loc_1800241BD
0x1800242fd  cmp     dword ptr [rdi+3Ch], 4
0x180024301  jz      loc_180023FB7
0x180024307  test    dword ptr [rdi+38h], 600000h
0x18002430e  jnz     loc_180023FB7
0x180024314  mov     rcx, [rbp+228h]; this
0x18002431b  mov     r9d, 80070057h; char *
0x180024321  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024328  mov     edx, 0D6h; void *
0x18002432d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024332  nop
0x180024333  lea     rcx, [rsp+320h+TokenHandle]
0x180024338  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002433d  mov     eax, 80070057h
0x180024342  jmp     loc_1800240AD
0x180024347  mov     rax, [r12]
0x18002434b  mov     r8, [rdi+40h]
0x18002434f  mov     rdx, qword ptr [rsp+320h+var_2C8]
0x180024354  mov     rcx, r12
0x180024357  mov     rax, [rax+30h]
0x18002435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024360  mov     ebx, eax
0x180024362  test    eax, eax
0x180024364  js      loc_18002420B
0x18002436a  mov     eax, [rdi+3Ch]
0x18002436d  cmp     eax, 1
0x180024370  jz      loc_18002402B
0x180024376  mov     dword ptr [rsp+320h+TargetHandle], r13d
0x18002437b  mov     rax, [r12]
0x18002437f  lea     r9, [rsp+320h+TargetHandle]
0x180024384  mov     r8, [rdi+18h]
0x180024388  mov     rdx, [rdi+8]
0x18002438c  mov     rcx, r12
0x18002438f  mov     rax, [rax+18h]
0x180024393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024398  cmp     dword ptr [rsp+320h+TargetHandle], r13d
0x18002439d  jz      loc_18002402B
0x1800243a3  movaps  xmm0, xmmword ptr [rbp+220h+pguid.Data1]
0x1800243a7  movdqa  xmmword ptr [rsp+320h+TargetHandle], xmm0
0x1800243ad  mov     [rsp+320h+var_2E0], rsi
0x1800243b2  mov     [rsp+320h+var_2E8], r14
0x1800243b7  mov     rax, [rdi+60h]
0x1800243bb  mov     qword ptr [rsp+320h+dwOptions], rax
0x1800243c0  lea     rax, [rbp+220h+var_220]
0x1800243c4  mov     qword ptr [rsp+320h+bInheritHandle], rax
0x1800243c9  lea     rax, [rsp+320h+TargetHandle]
0x1800243ce  mov     [rsp+320h+ReturnLength], rax; int
0x1800243d3  mov     r9, qword ptr [rsp+320h+var_2C8]
0x1800243d8  mov     r8, r15
0x1800243db  mov     rdx, rdi
0x1800243de  mov     rcx, r12
0x1800243e1  call    GetAppSelectedHostInfo
0x1800243e6  mov     ebx, eax
0x1800243e8  test    eax, eax
0x1800243ea  jns     loc_180024174
0x1800243f0  mov     rcx, [rbp+228h]; this
0x1800243f7  mov     r9d, eax; char *
0x1800243fa  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024401  mov     edx, 101h; void *
0x180024406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
