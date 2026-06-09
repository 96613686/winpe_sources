# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)

- ea: `0x1800198cc`
- end: `0x180019b12`
- name: `?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z`
- size: `582`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800125a0`
- `0x180014640`
- `0x180017c00`
- `0x180019670`
- `0x18001d764`
- `0x18001d940`
- `0x18001da3c`

## callees

- `0x18000b420`
- `0x18000ee54`
- `0x180011468`
- `0x1800198cc`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001c670`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180019a04`
- `msvcrt!memmove_s` at `0x180019a04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a8c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019a2f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019a2f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
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
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>(
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
0x1800198cc  mov     [rsp-18h+arg_0], rbx
0x1800198d1  mov     [rsp-18h+arg_8], rsi
0x1800198d6  mov     [rsp-18h+arg_10], r8
0x1800198db  push    rbp
0x1800198dc  push    rdi
0x1800198dd  push    r14
0x1800198df  mov     rbp, rsp
0x1800198e2  sub     rsp, 70h
0x1800198e6  mov     r14b, r9b
0x1800198e9  mov     esi, edx
0x1800198eb  mov     rbx, rcx
0x1800198ee  mov     [rbp+var_40], 0
0x1800198f5  mov     [rbp+var_20], 80000015h
0x1800198fc  mov     [rbp+var_18], 0
0x180019904  lea     r8, [rbp+var_40]
0x180019908  lea     rdx, [rbp+arg_10]
0x18001990c  lea     rcx, [rbp+var_30]
0x180019910  call    ??$?0PEAUISettingItem@DataModel@SystemSettings@@@?$AutoValue@V?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUISettingItem@DataModel@SystemSettings@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>(SystemSettings::DataModel::ISettingItem * const &,long *)
0x180019915  mov     edi, [rbp+var_40]
0x180019918  test    edi, edi
0x18001991a  js      loc_180019AC8
0x180019920  lea     rdx, [rbx+80h]
0x180019927  lea     r8, [rbp+var_40]
0x18001992b  lea     rcx, [rbp+var_38]
0x18001992f  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180019934  mov     edi, [rbp+var_40]
0x180019937  test    edi, edi
0x180019939  js      loc_180019A72
0x18001993f  test    r14b, r14b
0x180019942  jz      loc_180019A1B
0x180019948  mov     esi, [rbx+60h]
0x18001994b  mov     eax, esi
0x18001994d  mov     ecx, 8007000Eh
0x180019952  cmp     eax, 7FFFFFFFh
0x180019957  cmovnb  edi, ecx
0x18001995a  test    edi, edi
0x18001995c  js      loc_180019A72
0x180019962  lea     r8, [rbx+0B4h]
0x180019969  mov     edx, [rbx+0B0h]
0x18001996f  lea     rcx, [rbp+var_10]
0x180019973  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x180019978  mov     rdx, rax
0x18001997b  lea     rcx, [rbp+var_20]
0x18001997f  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180019984  lea     rcx, [rbp+var_20]
0x180019988  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001998d  mov     edi, eax
0x18001998f  test    eax, eax
0x180019991  js      loc_180019A72
0x180019997  mov     r9d, [rbx+64h]
0x18001999b  mov     eax, [rbx+60h]
0x18001999e  inc     eax
0x1800199a0  cmp     eax, r9d
0x1800199a3  jbe     short loc_1800199D3
0x1800199a5  mov     r8d, r9d
0x1800199a8  shr     r8d, 1
0x1800199ab  lea     ecx, [r8+r9]
0x1800199af  lea     eax, [r9+1]
0x1800199b3  mov     edx, 1
0x1800199b8  cmp     eax, ecx
0x1800199ba  cmovbe  edx, r8d
0x1800199be  add     edx, r9d
0x1800199c1  mov     rcx, rbx
0x1800199c4  call    ?ResizeStorage@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(uint)
0x1800199c9  mov     edi, eax
0x1800199cb  test    eax, eax
0x1800199cd  js      loc_180019A72
0x1800199d3  mov     eax, [rbx+60h]
0x1800199d6  cmp     esi, eax
0x1800199d8  jnb     short loc_180019A3D
0x1800199da  sub     eax, esi
0x1800199dc  mov     r9d, eax
0x1800199df  shl     r9, 4; SourceSize
0x1800199e3  mov     r8d, esi
0x1800199e6  shl     r8, 4
0x1800199ea  add     r8, [rbx+70h]; Source
0x1800199ee  mov     edx, [rbx+64h]
0x1800199f1  sub     edx, esi
0x1800199f3  dec     edx
0x1800199f5  shl     rdx, 4; DestinationSize
0x1800199f9  lea     ecx, [rsi+1]
0x1800199fc  shl     rcx, 4
0x180019a00  add     rcx, [rbx+70h]; Destination
0x180019a04  call    cs:__imp_memmove_s
0x180019a0b  nop     dword ptr [rax+rax+00h]
0x180019a10  test    eax, eax
0x180019a12  jz      short loc_180019A3D
0x180019a14  mov     edi, 8000FFFFh
0x180019a19  jmp     short loc_180019A2B
0x180019a1b  mov     eax, [rbx+60h]
0x180019a1e  cmp     esi, eax
0x180019a20  jbe     loc_18001994D
0x180019a26  mov     edi, 8000000Bh
0x180019a2b  xor     edx, edx
0x180019a2d  mov     ecx, edi
0x180019a2f  call    cs:__imp_RoOriginateError
0x180019a36  nop     dword ptr [rax+rax+00h]
0x180019a3b  jmp     short loc_180019A72
0x180019a3d  mov     ecx, esi
0x180019a3f  add     rcx, rcx
0x180019a42  mov     rax, [rbx+70h]
0x180019a46  movups  xmm0, [rbp+var_30]
0x180019a4a  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180019a4f  mov     qword ptr [rbp+var_30], 0
0x180019a57  mov     byte ptr [rbp+var_30+8], 0
0x180019a5b  inc     dword ptr [rbx+60h]
0x180019a5e  inc     dword ptr [rbx+90h]
0x180019a64  mov     rax, [rbx+70h]
0x180019a68  cmp     byte ptr [rax+rcx*8+8], 0
0x180019a6d  jz      short loc_180019A72
0x180019a6f  inc     dword ptr [rbx+68h]
0x180019a72  mov     rax, [rbp+var_38]
0x180019a76  test    rax, rax
0x180019a79  jz      short loc_180019A98
0x180019a7b  lea     rcx, [rax+8]; SRWLock
0x180019a7f  cmp     dword ptr [rax], 1
0x180019a82  jnz     short loc_180019A8C
0x180019a84  add     dword ptr [rcx], 10000000h
0x180019a8a  jmp     short loc_180019A98
0x180019a8c  call    cs:__imp_ReleaseSRWLockExclusive
0x180019a93  nop     dword ptr [rax+rax+00h]
0x180019a98  test    edi, edi
0x180019a9a  js      short loc_180019AC8
0x180019a9c  mov     rax, rbx
0x180019a9f  lea     rcx, [rbx+10h]
0x180019aa3  neg     rax
0x180019aa6  sbb     r8, r8
0x180019aa9  and     r8, rcx
0x180019aac  lea     rdx, [rbx+98h]
0x180019ab3  mov     [rsp+70h+var_50], esi
0x180019ab7  mov     r9d, 1
0x180019abd  lea     rcx, [rbp+var_20]
0x180019ac1  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x180019ac6  mov     edi, eax
0x180019ac8  mov     rcx, qword ptr [rbp+var_30]
0x180019acc  cmp     byte ptr [rbp+var_30+8], 0
0x180019ad0  jz      short loc_180019AD9
0x180019ad2  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x180019ad7  jmp     short loc_180019AEB
0x180019ad9  test    rcx, rcx
0x180019adc  jz      short loc_180019AEB
0x180019ade  mov     rax, [rcx]
0x180019ae1  mov     rax, [rax+10h]
0x180019ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aea  nop
0x180019aeb  mov     rax, [rbp+var_18]
0x180019aef  test    rax, rax
0x180019af2  jz      short loc_180019AFA
0x180019af4  mov     dword ptr [rax], 0
0x180019afa  mov     eax, edi
0x180019afc  lea     r11, [rsp+70h+var_s0]
0x180019b01  mov     rbx, [r11+20h]
0x180019b05  mov     rsi, [r11+28h]
0x180019b09  mov     rsp, r11
0x180019b0c  pop     r14
0x180019b0e  pop     rdi
0x180019b0f  pop     rbp
0x180019b10  retn
```
