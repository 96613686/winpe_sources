# ViewActivator::RemoveRequestForSuccess(unsigned __int64,unsigned __int64,uint *,AAMActivationPerfStats *)

- ea: `0x18001ef20`
- end: `0x18001f30f`
- name: `?RemoveRequestForSuccess@ViewActivator@@UEAAX_K0PEAIPEAUAAMActivationPerfStats@@@Z`
- size: `1007`
- prototype: `void __fastcall(ViewActivator *__hidden this, unsigned __int64, unsigned __int64, unsigned int *, struct AAMActivationPerfStats *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001ba70`
- `0x18001e484`
- `0x18001ef20`
- `0x180031c60`
- `0x180031d14`
- `0x18003210c`
- `0x18004498c`
- `0x18005b33c`
- `0x18007ac88`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001efe5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001efe5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ef4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ef4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f189`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f189`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001eff2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001eff2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f082`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f082`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ViewActivator::RemoveRequestForSuccess(
        RTL_SRWLOCK *this,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        struct AAMActivationPerfStats *a5)
{
  __int64 v9; // rbx
  RTL_SRWLOCK *v10; // rsi
  const char *v11; // r9
  _QWORD ***Ptr; // rax
  _QWORD **i; // rdi
  _QWORD *v14; // r14
  char v15; // al
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 v18; // rsi
  PVOID v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rax
  _QWORD *v22; // rdi
  _QWORD *v23; // r14
  _QWORD *v24; // r13
  __int64 v25; // r12
  __int64 j; // r15
  __int64 v27; // rcx
  __int64 v28; // rcx
  Microsoft::BamoImpl::BaseBamoConnectionImpl *v29; // rax
  const char *v30; // r9
  __int64 v31; // rsi
  __int64 v32; // rsi
  __int64 v33; // rbp
  int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rdx
  char v37; // al
  int v38; // eax
  int v39; // [rsp+20h] [rbp-68h]
  __int64 v40; // [rsp+30h] [rbp-58h] BYREF
  bool v41; // [rsp+38h] [rbp-50h]
  char v42; // [rsp+39h] [rbp-4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v9 = 0;
  v10 = this + 11;
  AcquireSRWLockExclusive(this + 11);
  Ptr = (_QWORD ***)this[12].Ptr;
  for ( i = *Ptr; ; i = (_QWORD **)*i )
  {
    v14 = i + 2;
    if ( i == Ptr )
    {
      v15 = 1;
      goto LABEL_7;
    }
    if ( *(_QWORD *)(*v14 + 40LL) == a2 && *(_QWORD *)(*v14 + 48LL) == a3 )
      break;
  }
  v15 = 0;
LABEL_7:
  if ( v15 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      v11);
  v16 = *v14;
  if ( *v14 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 8LL))(*v14);
    v9 = v16;
  }
  *i[1] = *i;
  (*i)[1] = i[1];
  --this[13].Ptr;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(i + 2);
  operator delete(i, (const struct std::nothrow_t *)0x18);
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  AcquireSRWLockShared((PSRWLOCK)(v9 + 112));
  if ( *(int *)(v9 + 248) < 0 )
  {
    *a4 = *(_DWORD *)(v9 + 120);
    v17 = 0;
  }
  else
  {
    *a4 = *(_DWORD *)(v9 + 180);
    v17 = *(_QWORD *)(v9 + 136);
  }
  if ( *(int *)(v9 + 160) < 0 )
    v18 = 0;
  else
    v18 = *(_QWORD *)(v9 + 144);
  if ( v9 != -112 )
    ReleaseSRWLockShared((PSRWLOCK)(v9 + 112));
  if ( a5 )
  {
    *((_DWORD *)a5 + 10) = 1000 * v17 / *(_QWORD *)a5;
    *((_DWORD *)a5 + 11) = 1000 * v18 / *(_QWORD *)a5;
  }
  if ( Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(a5) )
  {
    v19 = this[17].Ptr;
    v40 = 0;
    v20 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v19 + 56LL))(v19);
    v21 = *(_QWORD *)(v20 + 96);
    v40 = v21;
    if ( v21 )
      _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
    v41 = *(_DWORD *)(v20 + 184) == GetCurrentThreadId();
    v42 = 0;
    if ( !v41 )
    {
      Microsoft::BamoImpl::BaseBamoConnectionImpl::EnterLock((Microsoft::BamoImpl::BaseBamoConnectionImpl *)v20);
      v37 = 0;
      if ( *(_QWORD *)(v20 + 64) )
      {
        v38 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 56) + 96LL))(*(_QWORD *)(v20 + 56));
        if ( v38 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xA05,
            (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
            (const char *)(unsigned int)v38,
            v39);
        v37 = 1;
      }
      v42 = v37;
    }
    ++*(_DWORD *)(v20 + 188);
    v22 = *(_QWORD **)(v9 + 96);
    if ( v22 )
    {
      (*(void (__fastcall **)(_QWORD *))*v22)(v22);
      v22[19] = 0;
      v23 = (_QWORD *)*((_QWORD *)this[17].Ptr + 31);
      if ( v23 )
        (*(void (__fastcall **)(_QWORD *))*v23)(v23);
      v24 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v23[1] + 24LL))(v23 + 1);
      v25 = (__int64)(v24[8] - v24[7]) >> 3;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= (unsigned int)v25 )
        {
          if ( (_DWORD)j != (_DWORD)v25 )
            goto LABEL_30;
          v35 = 2147943568LL;
          v36 = 46;
          goto LABEL_55;
        }
        v27 = *(_QWORD *)(v24[4] + 32LL);
        if ( *(int *)(v27 + 8) > 0 )
          v28 = *(_QWORD *)(v27 + 16);
        else
          v28 = 0;
        v29 = (Microsoft::BamoImpl::BaseBamoConnectionImpl *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 56LL))(v28);
        Microsoft::BamoImpl::BaseBamoConnectionImpl::VerifyLockHeldIfOffThread(v29);
        v31 = v24[7];
        if ( (unsigned int)j >= (unsigned __int64)((v24[8] - v31) >> 3) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x49,
            (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoList.inl",
            v30);
        v32 = *(_QWORD *)(v31 + 8 * j);
        v33 = (*(__int64 (__fastcall **)(_QWORD *))(v22[1] + 40LL))(v22 + 1);
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v32 + 8) + 40LL))(v32 + 8) == v33 )
          break;
      }
      v34 = Microsoft::Bamo::ListPrincipalCommon<Microsoft::Bamo::Lib::ApplicationActivation_AutoBamos::BamoList_Windows_ApplicationModel_Activation_Private_ActivationRequestPrincipal_Principal,ApplicationActivation_AutoBamos::BamoConnection,wil::com_ptr_t<Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal,wil::err_returncode_policy>>::RemoveAt(
              v24,
              (unsigned int)j);
      if ( v34 >= 0 )
        goto LABEL_30;
      v35 = (unsigned int)v34;
      v36 = 39;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\applicationactivationwatcher\\server\\activationrequeststatics.cpp",
        (const char *)v35,
        (int)v22);
LABEL_30:
      if ( v23 )
        (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
    }
    if ( v22 )
      (*(void (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
    Microsoft::Bamo::Lock::~Lock((Microsoft::Bamo::Lock *)&v40);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
}

```

## disassembly

```asm
0x18001ef20  mov     rax, rsp
0x18001ef23  push    rbx
0x18001ef24  push    rbp
0x18001ef25  push    rsi
0x18001ef26  push    rdi
0x18001ef27  push    r12
0x18001ef29  push    r13
0x18001ef2b  push    r14
0x18001ef2d  push    r15
0x18001ef2f  sub     rsp, 48h
0x18001ef33  mov     r13, r9
0x18001ef36  mov     r15, r8
0x18001ef39  mov     r12, rdx
0x18001ef3c  mov     rbp, rcx
0x18001ef3f  xor     ebx, ebx
0x18001ef41  mov     [rax+8], rbx
0x18001ef45  lea     rsi, [rcx+58h]
0x18001ef49  mov     rcx, rsi; SRWLock
0x18001ef4c  call    cs:__imp_AcquireSRWLockExclusive
0x18001ef52  mov     rax, [rbp+60h]
0x18001ef56  mov     rdi, [rax]
0x18001ef59  lea     r14, [rdi+10h]
0x18001ef5d  cmp     rdi, rax
0x18001ef60  jz      short loc_18001EF7A
0x18001ef62  mov     rcx, [r14]
0x18001ef65  cmp     [rcx+28h], r12
0x18001ef69  jnz     short loc_18001EF75
0x18001ef6b  cmp     [rcx+30h], r15
0x18001ef6f  jz      loc_18001F17F
0x18001ef75  mov     rdi, [rdi]
0x18001ef78  jmp     short loc_18001EF59
0x18001ef7a  mov     al, 1
0x18001ef7c  mov     rcx, [rsp+88h]; this
0x18001ef84  test    al, al
0x18001ef86  jnz     loc_18001F2A9
0x18001ef8c  mov     r15, [r14]
0x18001ef8f  test    r15, r15
0x18001ef92  jz      short loc_18001EFAF
0x18001ef94  mov     rax, [r15]
0x18001ef97  mov     rcx, r15
0x18001ef9a  mov     rax, [rax+8]
0x18001ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efa3  nop
0x18001efa4  mov     rbx, r15
0x18001efa7  mov     [rsp+88h+arg_0], rbx
0x18001efaf  mov     rdx, [rdi+8]
0x18001efb3  mov     rax, [rdi]
0x18001efb6  mov     [rdx], rax
0x18001efb9  mov     rdx, [rdi]
0x18001efbc  mov     rax, [rdi+8]
0x18001efc0  mov     [rdx+8], rax
0x18001efc4  dec     qword ptr [rbp+68h]
0x18001efc8  mov     rcx, r14
0x18001efcb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001efd0  mov     edx, 18h; struct std::nothrow_t *
0x18001efd5  mov     rcx, rdi; void *
0x18001efd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001efdd  test    rsi, rsi
0x18001efe0  jz      short loc_18001EFEB
0x18001efe2  mov     rcx, rsi; SRWLock
0x18001efe5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001efeb  lea     rdi, [rbx+70h]
0x18001efef  mov     rcx, rdi; SRWLock
0x18001eff2  call    cs:__imp_AcquireSRWLockShared
0x18001eff8  cmp     dword ptr [rbx+0F8h], 0
0x18001efff  jl      loc_18001F194
0x18001f005  mov     eax, [rbx+0B4h]
0x18001f00b  mov     [r13+0], eax
0x18001f00f  mov     r14, [rbx+88h]
0x18001f016  cmp     dword ptr [rbx+0A0h], 0
0x18001f01d  jl      loc_18001F1A3
0x18001f023  mov     rsi, [rbx+90h]
0x18001f02a  test    rdi, rdi
0x18001f02d  jnz     loc_18001F186
0x18001f033  mov     rcx, [rsp+88h+arg_20]; this
0x18001f03b  test    rcx, rcx
0x18001f03e  jnz     loc_18001F1AA
0x18001f044  call    ?IsViewManagerPhaseoutEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(void)
0x18001f049  test    al, al
0x18001f04b  jz      loc_18001F15E
0x18001f051  mov     rcx, [rbp+88h]
0x18001f058  mov     [rsp+88h+var_58], 0
0x18001f061  mov     rax, [rcx]
0x18001f064  mov     rax, [rax+38h]
0x18001f068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f06d  mov     rdi, rax
0x18001f070  mov     rax, [rax+60h]
0x18001f074  mov     [rsp+88h+var_58], rax
0x18001f079  test    rax, rax
0x18001f07c  jz      short loc_18001F082
0x18001f07e  lock inc dword ptr [rax+8]
0x18001f082  call    cs:__imp_GetCurrentThreadId
0x18001f088  cmp     [rdi+0B8h], eax
0x18001f08e  setz    [rsp+88h+var_50]
0x18001f093  mov     [rsp+88h+var_4F], 0
0x18001f098  jnz     loc_18001F271
0x18001f09e  inc     dword ptr [rdi+0BCh]
0x18001f0a4  mov     rdi, [rbx+60h]
0x18001f0a8  mov     qword ptr [rsp+88h+var_68], rdi; int
0x18001f0ad  test    rdi, rdi
0x18001f0b0  jz      short loc_18001F0C1
0x18001f0b2  mov     rax, [rdi]
0x18001f0b5  mov     rcx, rdi
0x18001f0b8  mov     rax, [rax]
0x18001f0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0c0  nop
0x18001f0c1  test    rdi, rdi
0x18001f0c4  jz      short loc_18001F13E
0x18001f0c6  mov     qword ptr [rdi+98h], 0
0x18001f0d1  mov     rax, [rbp+88h]
0x18001f0d8  mov     r14, [rax+0F8h]
0x18001f0df  mov     [rsp+88h+var_60], r14
0x18001f0e4  test    r14, r14
0x18001f0e7  jz      short loc_18001F0F8
0x18001f0e9  mov     rax, [r14]
0x18001f0ec  mov     rcx, r14
0x18001f0ef  mov     rax, [rax]
0x18001f0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0f7  nop
0x18001f0f8  lea     rcx, [r14+8]
0x18001f0fc  mov     rax, [rcx]
0x18001f0ff  mov     rax, [rax+18h]
0x18001f103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f108  mov     r13, rax
0x18001f10b  mov     r12, [rax+40h]
0x18001f10f  sub     r12, [rax+38h]
0x18001f113  sar     r12, 3
0x18001f117  xor     r15d, r15d
0x18001f11a  cmp     r15d, r12d
0x18001f11d  jb      loc_18001F1CD
0x18001f123  jz      loc_18001F2EA
0x18001f129  test    r14, r14
0x18001f12c  jz      short loc_18001F13E
0x18001f12e  mov     rax, [r14]
0x18001f131  mov     rcx, r14
0x18001f134  mov     rax, [rax+8]
0x18001f138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f13d  nop
0x18001f13e  test    rdi, rdi
0x18001f141  jz      short loc_18001F153
0x18001f143  mov     rax, [rdi]
0x18001f146  mov     rcx, rdi
0x18001f149  mov     rax, [rax+8]
0x18001f14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f152  nop
0x18001f153  lea     rcx, [rsp+88h+var_58]; this
0x18001f158  call    ??1Lock@Bamo@Microsoft@@QEAA@XZ; Microsoft::Bamo::Lock::~Lock(void)
0x18001f15d  nop
0x18001f15e  mov     rax, [rbx]
0x18001f161  mov     rcx, rbx
0x18001f164  mov     rax, [rax+10h]
0x18001f168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f16d  nop
0x18001f16e  add     rsp, 48h
0x18001f172  pop     r15
0x18001f174  pop     r14
0x18001f176  pop     r13
0x18001f178  pop     r12
0x18001f17a  pop     rdi
0x18001f17b  pop     rsi
0x18001f17c  pop     rbp
0x18001f17d  pop     rbx
0x18001f17e  retn
0x18001f17f  xor     al, al
0x18001f181  jmp     loc_18001EF7C
0x18001f186  mov     rcx, rdi; SRWLock
0x18001f189  call    cs:__imp_ReleaseSRWLockShared
0x18001f18f  jmp     loc_18001F033
0x18001f194  mov     eax, [rbx+78h]
0x18001f197  mov     [r13+0], eax
0x18001f19b  xor     r14d, r14d
0x18001f19e  jmp     loc_18001F016
0x18001f1a3  xor     esi, esi
0x18001f1a5  jmp     loc_18001F02A
0x18001f1aa  imul    rax, r14, 3E8h
0x18001f1b1  cqo
0x18001f1b3  idiv    qword ptr [rcx]
0x18001f1b6  mov     [rcx+28h], eax
0x18001f1b9  imul    rax, rsi, 3E8h
0x18001f1c0  cqo
0x18001f1c2  idiv    qword ptr [rcx]
0x18001f1c5  mov     [rcx+2Ch], eax
0x18001f1c8  jmp     loc_18001F044
0x18001f1cd  mov     rax, [r13+20h]
0x18001f1d1  mov     rcx, [rax+20h]
0x18001f1d5  cmp     dword ptr [rcx+8], 0
0x18001f1d9  jg      loc_18001F268
0x18001f1df  xor     ecx, ecx
0x18001f1e1  mov     rax, [rcx]
0x18001f1e4  mov     rax, [rax+38h]
0x18001f1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1ed  mov     rcx, rax; this
0x18001f1f0  call    ?VerifyLockHeldIfOffThread@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEBAXXZ; Microsoft::BamoImpl::BaseBamoConnectionImpl::VerifyLockHeldIfOffThread(void)
0x18001f1f5  mov     rsi, [r13+38h]
0x18001f1f9  mov     edx, r15d
0x18001f1fc  mov     rcx, [rsp+88h]; this
0x18001f204  mov     rax, [r13+40h]
0x18001f208  sub     rax, rsi
0x18001f20b  sar     rax, 3
0x18001f20f  cmp     rdx, rax
0x18001f212  jnb     loc_18001F2BB
0x18001f218  mov     rsi, [rsi+r15*8]
0x18001f21c  lea     rcx, [rdi+8]
0x18001f220  mov     rax, [rcx]
0x18001f223  mov     rax, [rax+28h]
0x18001f227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f22c  mov     rbp, rax
0x18001f22f  lea     rcx, [rsi+8]
0x18001f233  mov     rdx, [rcx]
0x18001f236  mov     rax, [rdx+28h]
0x18001f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f23f  cmp     rax, rbp
0x18001f242  jnz     loc_18001F2E2
0x18001f248  mov     edx, r15d
0x18001f24b  mov     rcx, r13
0x18001f24e  call    ?RemoveAt@?$ListPrincipalCommon@VBamoList_Windows_ApplicationModel_Activation_Private_ActivationRequestPrincipal_Principal@ApplicationActivation_AutoBamos@Lib@Bamo@Microsoft@@VBamoConnection@2@V?$com_ptr_t@VBamoActivationRequestPrincipal@Private@Activation@ApplicationModel@Windows@@Uerr_returncode_policy@wil@@@wil@@@Bamo@Microsoft@@QEAAJI@Z; Microsoft::Bamo::ListPrincipalCommon<Microsoft::Bamo::Lib::ApplicationActivation_AutoBamos::BamoList_Windows_ApplicationModel_Activation_Private_ActivationRequestPrincipal_Principal,ApplicationActivation_AutoBamos::BamoConnection,wil::com_ptr_t<Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal,wil::err_returncode_policy>>::RemoveAt(uint)
0x18001f253  test    eax, eax
0x18001f255  jns     loc_18001F129
0x18001f25b  mov     r9d, eax
0x18001f25e  mov     edx, 27h ; '''
0x18001f263  jmp     loc_18001F2F5
0x18001f268  mov     rcx, [rcx+10h]
0x18001f26c  jmp     loc_18001F1E1
0x18001f271  mov     rcx, rdi; this
0x18001f274  call    ?EnterLock@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEAAXXZ; Microsoft::BamoImpl::BaseBamoConnectionImpl::EnterLock(void)
0x18001f279  xor     al, al
0x18001f27b  cmp     qword ptr [rdi+40h], 0
0x18001f280  jz      short loc_18001F2A0
0x18001f282  mov     rcx, [rdi+38h]
0x18001f286  mov     rax, [rcx]
0x18001f289  mov     rax, [rax+60h]
0x18001f28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f292  mov     rcx, [rsp+88h]; this
0x18001f29a  test    eax, eax
0x18001f29c  js      short loc_18001F2CD
0x18001f29e  mov     al, 1
0x18001f2a0  mov     [rsp+88h+var_4F], al
0x18001f2a4  jmp     loc_18001F09E
0x18001f2a9  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001f2b0  mov     edx, 208h; void *
0x18001f2b5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001f2bb  lea     r8, aDOsToolsBamoco_1; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoLi"...
0x18001f2c2  mov     edx, 49h ; 'I'; void *
0x18001f2c7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001f2cd  mov     r9d, eax; char *
0x18001f2d0  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18001f2d7  mov     edx, 0A05h; void *
0x18001f2dc  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18001f2e2  inc     r15d
0x18001f2e5  jmp     loc_18001F11A
0x18001f2ea  mov     r9d, 80070490h; char *
0x18001f2f0  mov     edx, 2Eh ; '.'; void *
0x18001f2f5  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001f2fc  mov     rcx, [rsp+88h]; this
0x18001f304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f309  jmp     loc_18001F129
```
