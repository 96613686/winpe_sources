# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::SetAt(uint,IInspectable *)

- ea: `0x18001cc40`
- end: `0x18001ce60`
- name: `?SetAt@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUIInspectable@@@Z`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000b3d4`
- `0x18000ee54`
- `0x180011468`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001cc40`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001cd34`
- `msvcrt!memmove_s` at `0x18001cd34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cdb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cdb0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001ccc9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cd4d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001ccc9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001cd4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::SetAt(
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
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(
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
0x18001cc40  mov     [rsp-28h+arg_0], rbx
0x18001cc45  mov     [rsp-28h+arg_8], rsi
0x18001cc4a  mov     [rsp-28h+arg_10], r8
0x18001cc4f  push    rbp
0x18001cc50  push    rdi
0x18001cc51  push    r12
0x18001cc53  push    r14
0x18001cc55  push    r15
0x18001cc57  mov     rbp, rsp
0x18001cc5a  sub     rsp, 70h
0x18001cc5e  mov     r12d, edx
0x18001cc61  mov     rdi, rcx
0x18001cc64  mov     [rbp+arg_18], 0
0x18001cc6b  mov     [rbp+var_28], 80000015h
0x18001cc72  mov     [rbp+var_20], 0
0x18001cc7a  xor     esi, esi
0x18001cc7c  xor     r15b, r15b
0x18001cc7f  lea     r8, [rbp+arg_18]
0x18001cc83  lea     rdx, [rbp+arg_10]
0x18001cc87  lea     rcx, [rbp+var_38]
0x18001cc8b  call    ??$?0PEAUIInspectable@@@?$AutoValue@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIInspectable@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(IInspectable * const &,long *)
0x18001cc90  mov     ebx, [rbp+arg_18]
0x18001cc93  test    ebx, ebx
0x18001cc95  js      loc_18001CDBD
0x18001cc9b  lea     rdx, [rdi+80h]
0x18001cca2  lea     r8, [rbp+arg_18]
0x18001cca6  lea     rcx, [rbp+var_40]
0x18001ccaa  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001ccaf  mov     ebx, [rbp+arg_18]
0x18001ccb2  test    ebx, ebx
0x18001ccb4  js      loc_18001CD96
0x18001ccba  cmp     r12d, [rdi+60h]
0x18001ccbe  jb      short loc_18001CCD5
0x18001ccc0  xor     edx, edx
0x18001ccc2  mov     ebx, 8000000Bh
0x18001ccc7  mov     ecx, ebx
0x18001ccc9  call    cs:__imp_RoOriginateError
0x18001ccd0  nop     dword ptr [rax+rax+00h]
0x18001ccd5  test    ebx, ebx
0x18001ccd7  js      loc_18001CD96
0x18001ccdd  lea     r8, [rdi+0B4h]
0x18001cce4  mov     edx, [rdi+0B0h]
0x18001ccea  lea     rcx, [rbp+Destination]
0x18001ccee  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001ccf3  mov     rdx, rax
0x18001ccf6  lea     rcx, [rbp+var_28]
0x18001ccfa  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18001ccff  lea     rcx, [rbp+var_28]
0x18001cd03  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001cd08  mov     ebx, eax
0x18001cd0a  test    eax, eax
0x18001cd0c  js      loc_18001CD96
0x18001cd12  mov     [rbp+Destination], rsi
0x18001cd16  mov     [rbp+var_10], sil
0x18001cd1a  mov     r14, r12
0x18001cd1d  shl     r14, 4
0x18001cd21  mov     r8, [rdi+70h]
0x18001cd25  add     r8, r14; Source
0x18001cd28  mov     edx, 10h; DestinationSize
0x18001cd2d  mov     r9d, edx; SourceSize
0x18001cd30  lea     rcx, [rbp+Destination]; Destination
0x18001cd34  call    cs:__imp_memmove_s
0x18001cd3b  nop     dword ptr [rax+rax+00h]
0x18001cd40  test    eax, eax
0x18001cd42  jz      short loc_18001CD5B
0x18001cd44  xor     edx, edx
0x18001cd46  mov     ebx, 8000FFFFh
0x18001cd4b  mov     ecx, ebx
0x18001cd4d  call    cs:__imp_RoOriginateError
0x18001cd54  nop     dword ptr [rax+rax+00h]
0x18001cd59  jmp     short loc_18001CD96
0x18001cd5b  mov     rax, [rdi+70h]
0x18001cd5f  movups  xmm0, [rbp+var_38]
0x18001cd63  movdqu  xmmword ptr [r14+rax], xmm0
0x18001cd69  mov     qword ptr [rbp+var_38], rsi
0x18001cd6d  mov     byte ptr [rbp+var_38+8], sil
0x18001cd71  inc     dword ptr [rdi+90h]
0x18001cd77  mov     rsi, [rbp+Destination]
0x18001cd7b  mov     r15b, [rbp+var_10]
0x18001cd7f  mov     rax, [rdi+70h]
0x18001cd83  cmp     byte ptr [r14+rax+8], 0
0x18001cd89  jz      short loc_18001CD8E
0x18001cd8b  inc     dword ptr [rdi+68h]
0x18001cd8e  test    r15b, r15b
0x18001cd91  jz      short loc_18001CD96
0x18001cd93  dec     dword ptr [rdi+68h]
0x18001cd96  mov     rax, [rbp+var_40]
0x18001cd9a  test    rax, rax
0x18001cd9d  jz      short loc_18001CDBD
0x18001cd9f  lea     rcx, [rax+8]; SRWLock
0x18001cda3  cmp     dword ptr [rax], 1
0x18001cda6  jnz     short loc_18001CDB0
0x18001cda8  add     dword ptr [rcx], 10000000h
0x18001cdae  jmp     short loc_18001CDBD
0x18001cdb0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cdb7  nop     dword ptr [rax+rax+00h]
0x18001cdbc  nop
0x18001cdbd  mov     rcx, qword ptr [rbp+var_38]
0x18001cdc1  cmp     byte ptr [rbp+var_38+8], 0
0x18001cdc5  jz      short loc_18001CDCE
0x18001cdc7  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001cdcc  jmp     short loc_18001CDE0
0x18001cdce  test    rcx, rcx
0x18001cdd1  jz      short loc_18001CDE0
0x18001cdd3  mov     rax, [rcx]
0x18001cdd6  mov     rax, [rax+10h]
0x18001cdda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cddf  nop
0x18001cde0  test    r15b, r15b
0x18001cde3  jz      short loc_18001CDEF
0x18001cde5  mov     rcx, rsi
0x18001cde8  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001cded  jmp     short loc_18001CE04
0x18001cdef  test    rsi, rsi
0x18001cdf2  jz      short loc_18001CE04
0x18001cdf4  mov     rax, [rsi]
0x18001cdf7  mov     rcx, rsi
0x18001cdfa  mov     rax, [rax+10h]
0x18001cdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce03  nop
0x18001ce04  test    ebx, ebx
0x18001ce06  js      short loc_18001CE35
0x18001ce08  mov     rax, rdi
0x18001ce0b  lea     rcx, [rdi+10h]
0x18001ce0f  neg     rax
0x18001ce12  sbb     r8, r8
0x18001ce15  and     r8, rcx
0x18001ce18  lea     rdx, [rdi+98h]
0x18001ce1f  mov     [rsp+70h+var_50], r12d
0x18001ce24  mov     r9d, 3
0x18001ce2a  lea     rcx, [rbp+var_28]
0x18001ce2e  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001ce33  mov     ebx, eax
0x18001ce35  mov     rax, [rbp+var_20]
0x18001ce39  test    rax, rax
0x18001ce3c  jz      short loc_18001CE44
0x18001ce3e  mov     dword ptr [rax], 0
0x18001ce44  mov     eax, ebx
0x18001ce46  lea     r11, [rsp+70h+var_s0]
0x18001ce4b  mov     rbx, [r11+30h]
0x18001ce4f  mov     rsi, [r11+38h]
0x18001ce53  mov     rsp, r11
0x18001ce56  pop     r15
0x18001ce58  pop     r14
0x18001ce5a  pop     r12
0x18001ce5c  pop     rdi
0x18001ce5d  pop     rbp
0x18001ce5e  retn
```
