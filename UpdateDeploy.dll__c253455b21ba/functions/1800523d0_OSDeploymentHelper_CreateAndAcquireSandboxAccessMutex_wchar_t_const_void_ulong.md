# OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t const *,void * *,ulong)

- ea: `0x1800523d0`
- end: `0x18005268e`
- name: `?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJPEB_WPEAPEAXK@Z`
- size: `702`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, void **, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180042654`
- `0x180052248`
- `0x180052774`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x180008ab8`
- `0x18000a1d4`
- `0x18000dce4`
- `0x180049ff8`
- `0x1800523d0`
- `0x180052b14`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800525ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800525ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800525cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800525cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052624`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800524e3`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800524e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t *this, wchar_t *a2, void **a3)
{
  DWORD v3; // r13d
  unsigned int v6; // ebx
  __int64 v7; // rdx
  WCHAR *v8; // rdi
  void *v9; // rsi
  int CombinedPath; // r15d
  LPWSTR v11; // r14
  __int64 v12; // rdx
  wchar_t *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdi
  int v16; // eax
  HANDLE v17; // rax
  const char *v18; // r9
  HANDLE v19; // rbx
  __int64 v20; // rdx
  DWORD v21; // eax
  LPCWSTR lpName; // [rsp+20h] [rbp-40h] BYREF
  LPWSTR lpsz[2]; // [rsp+28h] [rbp-38h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v3 = (unsigned int)a3;
  if ( !this || !*this )
  {
    v6 = -2147024809;
    v7 = 257;
    goto LABEL_42;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = 258;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)v6,
      (int)lpName);
    return v6;
  }
  lpsz[0] = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  v8 = 0;
  lpName = 0;
  v9 = 0;
  lpsz[1] = 0;
  CombinedPath = AllocAbsoluteSDFromString(L"O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x1013ffff;;;BA)", lpsz);
  v11 = lpsz[0];
  if ( CombinedPath < 0 )
  {
    v12 = 266;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)(unsigned int)CombinedPath,
      (int)lpName);
    goto LABEL_34;
  }
  if ( !lpsz[0] )
  {
    CombinedPath = -2145120257;
    v12 = 267;
    goto LABEL_32;
  }
  MutexAttributes.nLength = 24;
  MutexAttributes.lpSecurityDescriptor = lpsz[0];
  MutexAttributes.bInheritHandle = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UAMutexSynchronization>::GetImpl'::`2'::impl) )
  {
    lpsz[0] = 0;
    CombinedPath = DuplicateString<wchar_t const *,wchar_t *>(this, lpsz);
    v13 = lpsz[0];
    if ( CombinedPath < 0 )
    {
      v14 = 276;
      goto LABEL_18;
    }
    v15 = -1;
    do
      ++v15;
    while ( lpsz[0][v15] );
    if ( CharUpperBuffW(lpsz[0], v15) != (_DWORD)v15 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)lpName);
    CombinedPath = CreateCombinedPath(L"Global", v13, (wchar_t **)&lpName);
    if ( CombinedPath < 0 )
    {
      v14 = 281;
      v8 = (WCHAR *)lpName;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)(unsigned int)CombinedPath,
        (int)lpName);
      if ( v13 )
        SusFree(v13);
      goto LABEL_34;
    }
    CombinedPath = 0;
    if ( v13 )
      SusFree(v13);
  }
  else
  {
    v16 = CreateCombinedPath(L"Global", this, (wchar_t **)&lpName);
    CombinedPath = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)(unsigned int)v16,
        (int)lpName);
      v8 = (WCHAR *)lpName;
      goto LABEL_34;
    }
    CombinedPath = 0;
  }
  v8 = (WCHAR *)lpName;
  v17 = CreateMutexW(&MutexAttributes, 0, lpName);
  v19 = v17;
  v9 = v17;
  if ( v17 )
  {
    v21 = WaitForSingleObject(v17, v3);
    if ( v21 != -1 )
    {
      if ( v21 != 258 )
      {
        v9 = 0;
        *(_QWORD *)a2 = v19;
        goto LABEL_34;
      }
      CombinedPath = -2147024638;
      v12 = 294;
      goto LABEL_32;
    }
    v20 = 293;
  }
  else
  {
    v20 = 289;
  }
  CombinedPath = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)v20,
                   (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
                   v18);
LABEL_34:
  if ( v9 )
    CloseHandle(v9);
  if ( v8 )
    SusFree(v8);
  if ( v11 )
    SusFree(v11);
  return (unsigned int)CombinedPath;
}

```

## disassembly

```asm
0x1800523d0  mov     [rsp-38h+arg_18], rbx
0x1800523d5  push    rbp
0x1800523d6  push    rsi
0x1800523d7  push    rdi
0x1800523d8  push    r12
0x1800523da  push    r13
0x1800523dc  push    r14
0x1800523de  push    r15
0x1800523e0  mov     rbp, rsp
0x1800523e3  sub     rsp, 60h
0x1800523e7  mov     rax, cs:__security_cookie
0x1800523ee  xor     rax, rsp
0x1800523f1  mov     [rbp+var_10], rax
0x1800523f5  mov     r13d, r8d
0x1800523f8  mov     r12, rdx
0x1800523fb  mov     rbx, rcx
0x1800523fe  xor     ecx, ecx
0x180052400  test    rbx, rbx
0x180052403  jz      loc_18005264B
0x180052409  cmp     [rbx], cx
0x18005240c  jz      loc_18005264B
0x180052412  test    rdx, rdx
0x180052415  jnz     short loc_180052426
0x180052417  mov     ebx, 80004003h
0x18005241c  mov     edx, 102h
0x180052421  jmp     loc_180052655
0x180052426  mov     [rbp+lpsz], rcx
0x18005242a  xorps   xmm0, xmm0
0x18005242d  xor     eax, eax
0x18005242f  movups  xmmword ptr [rbp+MutexAttributes.nLength], xmm0
0x180052433  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], rax
0x180052437  mov     rdi, rcx
0x18005243a  mov     [rbp+lpName], rcx
0x18005243e  mov     rsi, rcx
0x180052441  mov     [rbp+var_30], rcx
0x180052445  lea     rdx, [rbp+lpsz]
0x180052449  lea     rcx, aOBagBadA0x1013_0; "O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x101"...
0x180052450  call    AllocAbsoluteSDFromString
0x180052455  mov     r15d, eax
0x180052458  mov     r14, [rbp+lpsz]
0x18005245c  test    eax, eax
0x18005245e  jns     short loc_18005246A
0x180052460  mov     edx, 10Ah
0x180052465  jmp     loc_180052600
0x18005246a  xor     r15d, r15d
0x18005246d  test    r14, r14
0x180052470  jnz     short loc_180052482
0x180052472  mov     r15d, 80240FFFh
0x180052478  mov     edx, 10Bh
0x18005247d  jmp     loc_180052600
0x180052482  mov     [rbp+MutexAttributes.nLength], 18h
0x180052489  mov     [rbp+MutexAttributes.lpSecurityDescriptor], r14
0x18005248d  mov     [rbp+MutexAttributes.bInheritHandle], 1
0x180052494  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization> `wil::Feature<__WilFeatureTraits_Feature_UAMutexSynchronization>::GetImpl(void)'::`2'::impl
0x18005249b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization>::__private_IsEnabled(void)
0x1800524a0  test    al, al
0x1800524a2  jz      loc_180052565
0x1800524a8  mov     [rbp+lpsz], r15
0x1800524ac  lea     rdx, [rbp+lpsz]
0x1800524b0  mov     rcx, rbx
0x1800524b3  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1800524b8  mov     r15d, eax
0x1800524bb  mov     rbx, [rbp+lpsz]
0x1800524bf  xor     eax, eax
0x1800524c1  test    r15d, r15d
0x1800524c4  jns     short loc_1800524CD
0x1800524c6  mov     edx, 114h
0x1800524cb  jmp     short loc_18005252A
0x1800524cd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800524d1  inc     rdi
0x1800524d4  cmp     [rbx+rdi*2], ax
0x1800524d8  jnz     short loc_1800524D1
0x1800524da  mov     r15, [rbp+38h]
0x1800524de  mov     edx, edi; cchLength
0x1800524e0  mov     rcx, rbx; lpsz
0x1800524e3  call    cs:__imp_CharUpperBuffW
0x1800524e9  cmp     eax, edi
0x1800524eb  jz      short loc_180052507
0x1800524ed  mov     r9d, 8000FFFFh; char *
0x1800524f3  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800524fa  mov     edx, 116h; void *
0x1800524ff  mov     rcx, r15; this
0x180052502  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180052507  lea     r8, [rbp+lpName]; wchar_t **
0x18005250b  mov     rdx, rbx; wchar_t *
0x18005250e  lea     rcx, aGlobal; "Global"
0x180052515  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18005251a  mov     r15d, eax
0x18005251d  test    eax, eax
0x18005251f  jns     short loc_180052553
0x180052521  mov     edx, 119h; void *
0x180052526  mov     rdi, [rbp+lpName]
0x18005252a  mov     rcx, [rbp+38h]; this
0x18005252e  mov     r9d, r15d; char *
0x180052531  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180052538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005253d  test    rbx, rbx
0x180052540  jz      loc_18005261C
0x180052546  mov     rcx, rbx; lpMem
0x180052549  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005254e  jmp     loc_18005261C
0x180052553  xor     r15d, r15d
0x180052556  test    rbx, rbx
0x180052559  jz      short loc_1800525A0
0x18005255b  mov     rcx, rbx; lpMem
0x18005255e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180052563  jmp     short loc_1800525A0
0x180052565  lea     r8, [rbp+lpName]; wchar_t **
0x180052569  mov     rdx, rbx; wchar_t *
0x18005256c  lea     rcx, aGlobal; "Global"
0x180052573  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180052578  mov     r15d, eax
0x18005257b  test    eax, eax
0x18005257d  jns     short loc_18005259D
0x18005257f  mov     rcx, [rbp+38h]; this
0x180052583  mov     r9d, eax; char *
0x180052586  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18005258d  mov     edx, 11Dh; void *
0x180052592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052597  mov     rdi, [rbp+lpName]
0x18005259b  jmp     short loc_18005261C
0x18005259d  xor     r15d, r15d
0x1800525a0  mov     rdi, [rbp+lpName]
0x1800525a4  mov     r8, rdi; lpName
0x1800525a7  xor     edx, edx; bInitialOwner
0x1800525a9  lea     rcx, [rbp+MutexAttributes]; lpMutexAttributes
0x1800525ad  call    cs:__imp_CreateMutexW
0x1800525b3  mov     rbx, rax
0x1800525b6  mov     rsi, rax
0x1800525b9  test    rax, rax
0x1800525bc  jnz     short loc_1800525C5
0x1800525be  mov     edx, 121h
0x1800525c3  jmp     short loc_1800525DB
0x1800525c5  mov     edx, r13d; dwMilliseconds
0x1800525c8  mov     rcx, rbx; hHandle
0x1800525cb  call    cs:__imp_WaitForSingleObject
0x1800525d1  cmp     eax, 0FFFFFFFFh
0x1800525d4  jnz     short loc_1800525F0
0x1800525d6  mov     edx, 125h; void *
0x1800525db  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800525e2  mov     rcx, [rbp+38h]; this
0x1800525e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800525eb  mov     r15d, eax
0x1800525ee  jmp     short loc_18005261C
0x1800525f0  cmp     eax, 102h
0x1800525f5  jnz     short loc_180052615
0x1800525f7  mov     r15d, 80070102h
0x1800525fd  lea     edx, [rax+24h]; void *
0x180052600  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180052607  mov     r9d, r15d; char *
0x18005260a  mov     rcx, [rbp+38h]; this
0x18005260e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052613  jmp     short loc_18005261C
0x180052615  mov     rsi, r15
0x180052618  mov     [r12], rbx
0x18005261c  test    rsi, rsi
0x18005261f  jz      short loc_18005262B
0x180052621  mov     rcx, rsi; hObject
0x180052624  call    cs:__imp_CloseHandle
0x18005262a  nop
0x18005262b  test    rdi, rdi
0x18005262e  jz      short loc_180052639
0x180052630  mov     rcx, rdi; lpMem
0x180052633  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180052638  nop
0x180052639  test    r14, r14
0x18005263c  jz      short loc_180052646
0x18005263e  mov     rcx, r14; lpMem
0x180052641  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180052646  mov     eax, r15d
0x180052649  jmp     short loc_18005266A
0x18005264b  mov     ebx, 80070057h
0x180052650  mov     edx, 101h; void *
0x180052655  mov     r9d, ebx; char *
0x180052658  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18005265f  mov     rcx, [rbp+38h]; this
0x180052663  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052668  mov     eax, ebx
0x18005266a  mov     rcx, [rbp+var_10]
0x18005266e  xor     rcx, rsp; StackCookie
0x180052671  call    __security_check_cookie
0x180052676  mov     rbx, [rsp+60h+arg_18]
0x18005267e  add     rsp, 60h
0x180052682  pop     r15
0x180052684  pop     r14
0x180052686  pop     r13
0x180052688  pop     r12
0x18005268a  pop     rdi
0x18005268b  pop     rsi
0x18005268c  pop     rbp
0x18005268d  retn
```
