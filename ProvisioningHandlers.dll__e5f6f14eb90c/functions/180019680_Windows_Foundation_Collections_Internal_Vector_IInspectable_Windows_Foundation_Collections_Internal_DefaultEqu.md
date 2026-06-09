# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)

- ea: `0x180019680`
- end: `0x1800198c6`
- name: `?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z`
- size: `582`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180012580`
- `0x180016680`
- `0x180019660`

## callees

- `0x18000b3d4`
- `0x18000ee54`
- `0x180011468`
- `0x180019680`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001c670`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800197b8`
- `msvcrt!memmove_s` at `0x1800197b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019840`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019840`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800197e3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800197e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        char a4)
{
  int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // r9d
  int v11; // edx
  unsigned int v12; // eax
  RTL_SRWLOCK *v13; // rcx
  int v15; // [rsp+30h] [rbp-40h] BYREF
  RTL_SRWLOCK *v16; // [rsp+38h] [rbp-38h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+50h] [rbp-20h] BYREF
  _DWORD *v19; // [rsp+58h] [rbp-18h]
  char v20[16]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+30h] BYREF

  v21 = a3;
  v15 = 0;
  v18 = -2147483627;
  v19 = 0;
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(
    &v17,
    &v21,
    &v15);
  v7 = v15;
  if ( v15 < 0 )
    goto LABEL_27;
  XWinRT::SerializingLockPolicy::Write(&v16, a1 + 128, &v15);
  v7 = v15;
  if ( v15 >= 0 )
  {
    if ( a4 )
    {
      a2 = *(_DWORD *)(a1 + 96);
      v8 = a2;
    }
    else
    {
      v8 = *(_DWORD *)(a1 + 96);
      if ( a2 > v8 )
      {
        v7 = -2147483637;
LABEL_18:
        RoOriginateError((unsigned int)v7, 0);
        goto LABEL_21;
      }
    }
    if ( v8 >= 0x7FFFFFFF )
      v7 = -2147024882;
    if ( v7 < 0 )
      goto LABEL_21;
    v9 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(v20, *(unsigned int *)(a1 + 176), a1 + 180);
    XWinRT::detail::ReentrancyGuard<1>::operator=(&v18, v9);
    v7 = XWinRT::detail::ReentrancyGuard<1>::hr(&v18);
    if ( v7 < 0 )
      goto LABEL_21;
    v10 = *(_DWORD *)(a1 + 100);
    if ( *(_DWORD *)(a1 + 96) + 1 > v10 )
    {
      v11 = 1;
      if ( v10 + 1 <= (v10 >> 1) + v10 )
        v11 = v10 >> 1;
      v7 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(
             a1,
             v10 + v11);
      if ( v7 < 0 )
        goto LABEL_21;
    }
    v12 = *(_DWORD *)(a1 + 96);
    if ( a2 >= v12
      || !memmove_s(
            (void *const)(*(_QWORD *)(a1 + 112) + 16LL * (a2 + 1)),
            16LL * (*(_DWORD *)(a1 + 100) - a2 - 1),
            (const void *const)(*(_QWORD *)(a1 + 112) + 16LL * a2),
            16LL * (v12 - a2)) )
    {
      *(_OWORD *)(*(_QWORD *)(a1 + 112) + 16LL * a2) = v17;
      *(_QWORD *)&v17 = 0;
      BYTE8(v17) = 0;
      ++*(_DWORD *)(a1 + 96);
      ++*(_DWORD *)(a1 + 144);
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 112) + 16LL * a2 + 8) )
        ++*(_DWORD *)(a1 + 104);
      goto LABEL_21;
    }
    v7 = -2147418113;
    goto LABEL_18;
  }
LABEL_21:
  if ( v16 )
  {
    v13 = v16 + 1;
    if ( LODWORD(v16->Ptr) == 1 )
      LODWORD(v13->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v13);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           &v18,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           1,
           a2);
LABEL_27:
  if ( BYTE8(v17) )
  {
    XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v17);
  }
  else if ( (_QWORD)v17 )
  {
    (*(void (**)(void))(*(_QWORD *)v17 + 16LL))();
  }
  if ( v19 )
    *v19 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019680  mov     [rsp-18h+arg_0], rbx
0x180019685  mov     [rsp-18h+arg_8], rsi
0x18001968a  mov     [rsp-18h+arg_10], r8
0x18001968f  push    rbp
0x180019690  push    rdi
0x180019691  push    r14
0x180019693  mov     rbp, rsp
0x180019696  sub     rsp, 70h
0x18001969a  mov     r14b, r9b
0x18001969d  mov     esi, edx
0x18001969f  mov     rbx, rcx
0x1800196a2  mov     [rbp+var_40], 0
0x1800196a9  mov     [rbp+var_20], 80000015h
0x1800196b0  mov     [rbp+var_18], 0
0x1800196b8  lea     r8, [rbp+var_40]
0x1800196bc  lea     rdx, [rbp+arg_10]
0x1800196c0  lea     rcx, [rbp+var_30]
0x1800196c4  call    ??$?0PEAUIInspectable@@@?$AutoValue@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIInspectable@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(IInspectable * const &,long *)
0x1800196c9  mov     edi, [rbp+var_40]
0x1800196cc  test    edi, edi
0x1800196ce  js      loc_18001987C
0x1800196d4  lea     rdx, [rbx+80h]
0x1800196db  lea     r8, [rbp+var_40]
0x1800196df  lea     rcx, [rbp+var_38]
0x1800196e3  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800196e8  mov     edi, [rbp+var_40]
0x1800196eb  test    edi, edi
0x1800196ed  js      loc_180019826
0x1800196f3  test    r14b, r14b
0x1800196f6  jz      loc_1800197CF
0x1800196fc  mov     esi, [rbx+60h]
0x1800196ff  mov     eax, esi
0x180019701  mov     ecx, 8007000Eh
0x180019706  cmp     eax, 7FFFFFFFh
0x18001970b  cmovnb  edi, ecx
0x18001970e  test    edi, edi
0x180019710  js      loc_180019826
0x180019716  lea     r8, [rbx+0B4h]
0x18001971d  mov     edx, [rbx+0B0h]
0x180019723  lea     rcx, [rbp+var_10]
0x180019727  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001972c  mov     rdx, rax
0x18001972f  lea     rcx, [rbp+var_20]
0x180019733  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180019738  lea     rcx, [rbp+var_20]
0x18001973c  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x180019741  mov     edi, eax
0x180019743  test    eax, eax
0x180019745  js      loc_180019826
0x18001974b  mov     r9d, [rbx+64h]
0x18001974f  mov     eax, [rbx+60h]
0x180019752  inc     eax
0x180019754  cmp     eax, r9d
0x180019757  jbe     short loc_180019787
0x180019759  mov     r8d, r9d
0x18001975c  shr     r8d, 1
0x18001975f  lea     ecx, [r8+r9]
0x180019763  lea     eax, [r9+1]
0x180019767  mov     edx, 1
0x18001976c  cmp     eax, ecx
0x18001976e  cmovbe  edx, r8d
0x180019772  add     edx, r9d
0x180019775  mov     rcx, rbx
0x180019778  call    ?ResizeStorage@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(uint)
0x18001977d  mov     edi, eax
0x18001977f  test    eax, eax
0x180019781  js      loc_180019826
0x180019787  mov     eax, [rbx+60h]
0x18001978a  cmp     esi, eax
0x18001978c  jnb     short loc_1800197F1
0x18001978e  sub     eax, esi
0x180019790  mov     r9d, eax
0x180019793  shl     r9, 4; SourceSize
0x180019797  mov     r8d, esi
0x18001979a  shl     r8, 4
0x18001979e  add     r8, [rbx+70h]; Source
0x1800197a2  mov     edx, [rbx+64h]
0x1800197a5  sub     edx, esi
0x1800197a7  dec     edx
0x1800197a9  shl     rdx, 4; DestinationSize
0x1800197ad  lea     ecx, [rsi+1]
0x1800197b0  shl     rcx, 4
0x1800197b4  add     rcx, [rbx+70h]; Destination
0x1800197b8  call    cs:__imp_memmove_s
0x1800197bf  nop     dword ptr [rax+rax+00h]
0x1800197c4  test    eax, eax
0x1800197c6  jz      short loc_1800197F1
0x1800197c8  mov     edi, 8000FFFFh
0x1800197cd  jmp     short loc_1800197DF
0x1800197cf  mov     eax, [rbx+60h]
0x1800197d2  cmp     esi, eax
0x1800197d4  jbe     loc_180019701
0x1800197da  mov     edi, 8000000Bh
0x1800197df  xor     edx, edx
0x1800197e1  mov     ecx, edi
0x1800197e3  call    cs:__imp_RoOriginateError
0x1800197ea  nop     dword ptr [rax+rax+00h]
0x1800197ef  jmp     short loc_180019826
0x1800197f1  mov     ecx, esi
0x1800197f3  add     rcx, rcx
0x1800197f6  mov     rax, [rbx+70h]
0x1800197fa  movups  xmm0, [rbp+var_30]
0x1800197fe  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180019803  mov     qword ptr [rbp+var_30], 0
0x18001980b  mov     byte ptr [rbp+var_30+8], 0
0x18001980f  inc     dword ptr [rbx+60h]
0x180019812  inc     dword ptr [rbx+90h]
0x180019818  mov     rax, [rbx+70h]
0x18001981c  cmp     byte ptr [rax+rcx*8+8], 0
0x180019821  jz      short loc_180019826
0x180019823  inc     dword ptr [rbx+68h]
0x180019826  mov     rax, [rbp+var_38]
0x18001982a  test    rax, rax
0x18001982d  jz      short loc_18001984C
0x18001982f  lea     rcx, [rax+8]; SRWLock
0x180019833  cmp     dword ptr [rax], 1
0x180019836  jnz     short loc_180019840
0x180019838  add     dword ptr [rcx], 10000000h
0x18001983e  jmp     short loc_18001984C
0x180019840  call    cs:__imp_ReleaseSRWLockExclusive
0x180019847  nop     dword ptr [rax+rax+00h]
0x18001984c  test    edi, edi
0x18001984e  js      short loc_18001987C
0x180019850  mov     rax, rbx
0x180019853  lea     rcx, [rbx+10h]
0x180019857  neg     rax
0x18001985a  sbb     r8, r8
0x18001985d  and     r8, rcx
0x180019860  lea     rdx, [rbx+98h]
0x180019867  mov     [rsp+70h+var_50], esi
0x18001986b  mov     r9d, 1
0x180019871  lea     rcx, [rbp+var_20]
0x180019875  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001987a  mov     edi, eax
0x18001987c  mov     rcx, qword ptr [rbp+var_30]
0x180019880  cmp     byte ptr [rbp+var_30+8], 0
0x180019884  jz      short loc_18001988D
0x180019886  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001988b  jmp     short loc_18001989F
0x18001988d  test    rcx, rcx
0x180019890  jz      short loc_18001989F
0x180019892  mov     rax, [rcx]
0x180019895  mov     rax, [rax+10h]
0x180019899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001989e  nop
0x18001989f  mov     rax, [rbp+var_18]
0x1800198a3  test    rax, rax
0x1800198a6  jz      short loc_1800198AE
0x1800198a8  mov     dword ptr [rax], 0
0x1800198ae  mov     eax, edi
0x1800198b0  lea     r11, [rsp+70h+var_s0]
0x1800198b5  mov     rbx, [r11+20h]
0x1800198b9  mov     rsi, [r11+28h]
0x1800198bd  mov     rsp, r11
0x1800198c0  pop     r14
0x1800198c2  pop     rdi
0x1800198c3  pop     rbp
0x1800198c4  retn
```
