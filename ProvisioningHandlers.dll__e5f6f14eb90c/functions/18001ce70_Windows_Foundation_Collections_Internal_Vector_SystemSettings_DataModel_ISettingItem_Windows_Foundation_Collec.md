# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::SetAt(uint,SystemSettings::DataModel::ISettingItem *)

- ea: `0x18001ce70`
- end: `0x18001d090`
- name: `?SetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUISettingItem@DataModel@SystemSettings@@@Z`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000b420`
- `0x18000ee54`
- `0x180011468`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001ce70`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001cf64`
- `msvcrt!memmove_s` at `0x18001cf64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cfe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cfe0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cef9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cf7d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cef9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cf7d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::SetAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r12
  __int64 v5; // rsi
  char v6; // r15
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // r14
  RTL_SRWLOCK *v10; // rcx
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+38h] [rbp-38h] BYREF
  int v14; // [rsp+48h] [rbp-28h] BYREF
  _DWORD *v15; // [rsp+50h] [rbp-20h]
  __int64 Destination; // [rsp+58h] [rbp-18h] BYREF
  char v17; // [rsp+60h] [rbp-10h]
  __int64 v18; // [rsp+B0h] [rbp+40h] BYREF
  int v19; // [rsp+B8h] [rbp+48h] BYREF

  v18 = a3;
  v3 = a2;
  v19 = 0;
  v14 = -2147483627;
  v15 = 0;
  v5 = 0;
  v6 = 0;
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>(
    &v13,
    &v18,
    &v19);
  v7 = v19;
  if ( v19 >= 0 )
  {
    XWinRT::SerializingLockPolicy::Write(&v12, a1 + 128, &v19);
    v7 = v19;
    if ( v19 >= 0 )
    {
      if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 96) )
      {
        v7 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
      if ( v7 >= 0 )
      {
        v8 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(&Destination, *(unsigned int *)(a1 + 176), a1 + 180);
        XWinRT::detail::ReentrancyGuard<1>::operator=(&v14, v8);
        v7 = XWinRT::detail::ReentrancyGuard<1>::hr(&v14);
        if ( v7 >= 0 )
        {
          Destination = 0;
          v17 = 0;
          v9 = 16 * v3;
          if ( memmove_s(&Destination, 0x10u, (const void *const)(16 * v3 + *(_QWORD *)(a1 + 112)), 0x10u) )
          {
            v7 = -2147418113;
            RoOriginateError(2147549183LL, 0);
          }
          else
          {
            *(_OWORD *)(v9 + *(_QWORD *)(a1 + 112)) = v13;
            *(_QWORD *)&v13 = 0;
            BYTE8(v13) = 0;
            ++*(_DWORD *)(a1 + 144);
            v5 = Destination;
            v6 = v17;
            if ( *(_BYTE *)(v9 + *(_QWORD *)(a1 + 112) + 8) )
              ++*(_DWORD *)(a1 + 104);
            if ( v6 )
              --*(_DWORD *)(a1 + 104);
          }
        }
      }
    }
    if ( v12 )
    {
      v10 = v12 + 1;
      if ( LODWORD(v12->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
  }
  if ( BYTE8(v13) )
  {
    XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v13);
  }
  else if ( (_QWORD)v13 )
  {
    (*(void (**)(void))(*(_QWORD *)v13 + 16LL))();
  }
  if ( v6 )
  {
    XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v5);
  }
  else if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           &v14,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           3,
           v3);
  if ( v15 )
    *v15 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ce70  mov     [rsp-28h+arg_0], rbx
0x18001ce75  mov     [rsp-28h+arg_8], rsi
0x18001ce7a  mov     [rsp-28h+arg_10], r8
0x18001ce7f  push    rbp
0x18001ce80  push    rdi
0x18001ce81  push    r12
0x18001ce83  push    r14
0x18001ce85  push    r15
0x18001ce87  mov     rbp, rsp
0x18001ce8a  sub     rsp, 70h
0x18001ce8e  mov     r12d, edx
0x18001ce91  mov     rdi, rcx
0x18001ce94  mov     [rbp+arg_18], 0
0x18001ce9b  mov     [rbp+var_28], 80000015h
0x18001cea2  mov     [rbp+var_20], 0
0x18001ceaa  xor     esi, esi
0x18001ceac  xor     r15b, r15b
0x18001ceaf  lea     r8, [rbp+arg_18]
0x18001ceb3  lea     rdx, [rbp+arg_10]
0x18001ceb7  lea     rcx, [rbp+var_38]
0x18001cebb  call    ??$?0PEAUISettingItem@DataModel@SystemSettings@@@?$AutoValue@V?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUISettingItem@DataModel@SystemSettings@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>::AutoValue<XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>(SystemSettings::DataModel::ISettingItem * const &,long *)
0x18001cec0  mov     ebx, [rbp+arg_18]
0x18001cec3  test    ebx, ebx
0x18001cec5  js      loc_18001CFED
0x18001cecb  lea     rdx, [rdi+80h]
0x18001ced2  lea     r8, [rbp+arg_18]
0x18001ced6  lea     rcx, [rbp+var_40]
0x18001ceda  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001cedf  mov     ebx, [rbp+arg_18]
0x18001cee2  test    ebx, ebx
0x18001cee4  js      loc_18001CFC6
0x18001ceea  cmp     r12d, [rdi+60h]
0x18001ceee  jb      short loc_18001CF05
0x18001cef0  xor     edx, edx
0x18001cef2  mov     ebx, 8000000Bh
0x18001cef7  mov     ecx, ebx
0x18001cef9  call    cs:__imp_RoOriginateError
0x18001cf00  nop     dword ptr [rax+rax+00h]
0x18001cf05  test    ebx, ebx
0x18001cf07  js      loc_18001CFC6
0x18001cf0d  lea     r8, [rdi+0B4h]
0x18001cf14  mov     edx, [rdi+0B0h]
0x18001cf1a  lea     rcx, [rbp+Destination]
0x18001cf1e  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001cf23  mov     rdx, rax
0x18001cf26  lea     rcx, [rbp+var_28]
0x18001cf2a  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18001cf2f  lea     rcx, [rbp+var_28]
0x18001cf33  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001cf38  mov     ebx, eax
0x18001cf3a  test    eax, eax
0x18001cf3c  js      loc_18001CFC6
0x18001cf42  mov     [rbp+Destination], rsi
0x18001cf46  mov     [rbp+var_10], sil
0x18001cf4a  mov     r14, r12
0x18001cf4d  shl     r14, 4
0x18001cf51  mov     r8, [rdi+70h]
0x18001cf55  add     r8, r14; Source
0x18001cf58  mov     edx, 10h; DestinationSize
0x18001cf5d  mov     r9d, edx; SourceSize
0x18001cf60  lea     rcx, [rbp+Destination]; Destination
0x18001cf64  call    cs:__imp_memmove_s
0x18001cf6b  nop     dword ptr [rax+rax+00h]
0x18001cf70  test    eax, eax
0x18001cf72  jz      short loc_18001CF8B
0x18001cf74  xor     edx, edx
0x18001cf76  mov     ebx, 8000FFFFh
0x18001cf7b  mov     ecx, ebx
0x18001cf7d  call    cs:__imp_RoOriginateError
0x18001cf84  nop     dword ptr [rax+rax+00h]
0x18001cf89  jmp     short loc_18001CFC6
0x18001cf8b  mov     rax, [rdi+70h]
0x18001cf8f  movups  xmm0, [rbp+var_38]
0x18001cf93  movdqu  xmmword ptr [r14+rax], xmm0
0x18001cf99  mov     qword ptr [rbp+var_38], rsi
0x18001cf9d  mov     byte ptr [rbp+var_38+8], sil
0x18001cfa1  inc     dword ptr [rdi+90h]
0x18001cfa7  mov     rsi, [rbp+Destination]
0x18001cfab  mov     r15b, [rbp+var_10]
0x18001cfaf  mov     rax, [rdi+70h]
0x18001cfb3  cmp     byte ptr [r14+rax+8], 0
0x18001cfb9  jz      short loc_18001CFBE
0x18001cfbb  inc     dword ptr [rdi+68h]
0x18001cfbe  test    r15b, r15b
0x18001cfc1  jz      short loc_18001CFC6
0x18001cfc3  dec     dword ptr [rdi+68h]
0x18001cfc6  mov     rax, [rbp+var_40]
0x18001cfca  test    rax, rax
0x18001cfcd  jz      short loc_18001CFED
0x18001cfcf  lea     rcx, [rax+8]; SRWLock
0x18001cfd3  cmp     dword ptr [rax], 1
0x18001cfd6  jnz     short loc_18001CFE0
0x18001cfd8  add     dword ptr [rcx], 10000000h
0x18001cfde  jmp     short loc_18001CFED
0x18001cfe0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cfe7  nop     dword ptr [rax+rax+00h]
0x18001cfec  nop
0x18001cfed  mov     rcx, qword ptr [rbp+var_38]
0x18001cff1  cmp     byte ptr [rbp+var_38+8], 0
0x18001cff5  jz      short loc_18001CFFE
0x18001cff7  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001cffc  jmp     short loc_18001D010
0x18001cffe  test    rcx, rcx
0x18001d001  jz      short loc_18001D010
0x18001d003  mov     rax, [rcx]
0x18001d006  mov     rax, [rax+10h]
0x18001d00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d00f  nop
0x18001d010  test    r15b, r15b
0x18001d013  jz      short loc_18001D01F
0x18001d015  mov     rcx, rsi
0x18001d018  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001d01d  jmp     short loc_18001D034
0x18001d01f  test    rsi, rsi
0x18001d022  jz      short loc_18001D034
0x18001d024  mov     rax, [rsi]
0x18001d027  mov     rcx, rsi
0x18001d02a  mov     rax, [rax+10h]
0x18001d02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d033  nop
0x18001d034  test    ebx, ebx
0x18001d036  js      short loc_18001D065
0x18001d038  mov     rax, rdi
0x18001d03b  lea     rcx, [rdi+10h]
0x18001d03f  neg     rax
0x18001d042  sbb     r8, r8
0x18001d045  and     r8, rcx
0x18001d048  lea     rdx, [rdi+98h]
0x18001d04f  mov     [rsp+70h+var_50], r12d
0x18001d054  mov     r9d, 3
0x18001d05a  lea     rcx, [rbp+var_28]
0x18001d05e  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001d063  mov     ebx, eax
0x18001d065  mov     rax, [rbp+var_20]
0x18001d069  test    rax, rax
0x18001d06c  jz      short loc_18001D074
0x18001d06e  mov     dword ptr [rax], 0
0x18001d074  mov     eax, ebx
0x18001d076  lea     r11, [rsp+70h+var_s0]
0x18001d07b  mov     rbx, [r11+30h]
0x18001d07f  mov     rsi, [r11+38h]
0x18001d083  mov     rsp, r11
0x18001d086  pop     r15
0x18001d088  pop     r14
0x18001d08a  pop     r12
0x18001d08c  pop     rdi
0x18001d08d  pop     rbp
0x18001d08e  retn
```
