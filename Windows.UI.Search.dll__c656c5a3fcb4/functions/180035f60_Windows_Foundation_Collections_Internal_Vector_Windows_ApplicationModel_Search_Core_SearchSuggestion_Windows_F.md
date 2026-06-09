# Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::InsertAtInternal(uint,Windows::ApplicationModel::Search::Core::ISearchSuggestion *,bool)

- ea: `0x180035f60`
- end: `0x180036193`
- name: `?InsertAtInternal@?$Vector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@7895@U?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISearchSuggestion@Core@Search@ApplicationModel@5@_N@Z`
- size: `563`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180033f70`
- `0x180035f50`

## callees

- `0x18001c7d0`
- `0x18001d104`
- `0x1800310f0`
- `0x180032d7c`
- `0x1800338e4`
- `0x180035f60`
- `0x180037124`
- `0x180037cc8`
- `0x1800399d4`
- `0x18007b010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180036098`
- `msvcrt!memmove_s` at `0x180036098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036114`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036114`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800360bd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800360bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::InsertAtInternal(
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
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>(
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
      v7 = Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::ResizeStorage(
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
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(
           &v18,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           1,
           a2);
LABEL_27:
  if ( BYTE8(v17) )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v17);
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
0x180035f60  mov     [rsp-18h+arg_0], rbx
0x180035f65  mov     [rsp-18h+arg_8], rsi
0x180035f6a  mov     [rsp-18h+arg_10], r8
0x180035f6f  push    rbp
0x180035f70  push    rdi
0x180035f71  push    r14
0x180035f73  mov     rbp, rsp
0x180035f76  sub     rsp, 70h
0x180035f7a  mov     r14b, r9b
0x180035f7d  mov     esi, edx
0x180035f7f  mov     rbx, rcx
0x180035f82  mov     [rbp+var_40], 0
0x180035f89  mov     [rbp+var_20], 80000015h
0x180035f90  mov     [rbp+var_18], 0
0x180035f98  lea     r8, [rbp+var_40]
0x180035f9c  lea     rdx, [rbp+arg_10]
0x180035fa0  lea     rcx, [rbp+var_30]
0x180035fa4  call    ??$?0PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@?$AutoValue@V?$GitStorageType@UISearchSuggestion@Core@Search@ApplicationModel@Windows@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>(Windows::ApplicationModel::Search::Core::ISearchSuggestion * const &,long *)
0x180035fa9  mov     edi, [rbp+var_40]
0x180035fac  test    edi, edi
0x180035fae  js      loc_18003614A
0x180035fb4  lea     rdx, [rbx+80h]
0x180035fbb  lea     r8, [rbp+var_40]
0x180035fbf  lea     rcx, [rbp+var_38]
0x180035fc3  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180035fc8  mov     edi, [rbp+var_40]
0x180035fcb  test    edi, edi
0x180035fcd  js      loc_1800360FA
0x180035fd3  test    r14b, r14b
0x180035fd6  jz      loc_1800360A9
0x180035fdc  mov     esi, [rbx+60h]
0x180035fdf  mov     eax, esi
0x180035fe1  mov     ecx, 8007000Eh
0x180035fe6  cmp     eax, 7FFFFFFFh
0x180035feb  cmovnb  edi, ecx
0x180035fee  test    edi, edi
0x180035ff0  js      loc_1800360FA
0x180035ff6  lea     r8, [rbx+0B4h]
0x180035ffd  mov     edx, [rbx+0B0h]
0x180036003  lea     rcx, [rbp+var_10]
0x180036007  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18003600c  mov     rdx, rax
0x18003600f  lea     rcx, [rbp+var_20]
0x180036013  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180036018  lea     rcx, [rbp+var_20]
0x18003601c  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x180036021  mov     edi, eax
0x180036023  test    eax, eax
0x180036025  js      loc_1800360FA
0x18003602b  mov     r9d, [rbx+64h]
0x18003602f  mov     eax, [rbx+60h]
0x180036032  inc     eax
0x180036034  cmp     eax, r9d
0x180036037  jbe     short loc_180036067
0x180036039  mov     r8d, r9d
0x18003603c  shr     r8d, 1
0x18003603f  lea     ecx, [r8+r9]
0x180036043  lea     eax, [r9+1]
0x180036047  mov     edx, 1
0x18003604c  cmp     eax, ecx
0x18003604e  cmovbe  edx, r8d
0x180036052  add     edx, r9d
0x180036055  mov     rcx, rbx
0x180036058  call    ?ResizeStorage@?$Vector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@7895@U?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::ResizeStorage(uint)
0x18003605d  mov     edi, eax
0x18003605f  test    eax, eax
0x180036061  js      loc_1800360FA
0x180036067  mov     eax, [rbx+60h]
0x18003606a  cmp     esi, eax
0x18003606c  jnb     short loc_1800360C5
0x18003606e  sub     eax, esi
0x180036070  mov     r9d, eax
0x180036073  shl     r9, 4; SourceSize
0x180036077  mov     r8d, esi
0x18003607a  shl     r8, 4
0x18003607e  add     r8, [rbx+70h]; Source
0x180036082  mov     edx, [rbx+64h]
0x180036085  sub     edx, esi
0x180036087  dec     edx
0x180036089  shl     rdx, 4; DestinationSize
0x18003608d  lea     ecx, [rsi+1]
0x180036090  shl     rcx, 4
0x180036094  add     rcx, [rbx+70h]; Destination
0x180036098  call    cs:__imp_memmove_s
0x18003609e  test    eax, eax
0x1800360a0  jz      short loc_1800360C5
0x1800360a2  mov     edi, 8000FFFFh
0x1800360a7  jmp     short loc_1800360B9
0x1800360a9  mov     eax, [rbx+60h]
0x1800360ac  cmp     esi, eax
0x1800360ae  jbe     loc_180035FE1
0x1800360b4  mov     edi, 8000000Bh
0x1800360b9  xor     edx, edx
0x1800360bb  mov     ecx, edi
0x1800360bd  call    cs:__imp_RoOriginateError
0x1800360c3  jmp     short loc_1800360FA
0x1800360c5  mov     ecx, esi
0x1800360c7  add     rcx, rcx
0x1800360ca  mov     rax, [rbx+70h]
0x1800360ce  movups  xmm0, [rbp+var_30]
0x1800360d2  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800360d7  mov     qword ptr [rbp+var_30], 0
0x1800360df  mov     byte ptr [rbp+var_30+8], 0
0x1800360e3  inc     dword ptr [rbx+60h]
0x1800360e6  inc     dword ptr [rbx+90h]
0x1800360ec  mov     rax, [rbx+70h]
0x1800360f0  cmp     byte ptr [rax+rcx*8+8], 0
0x1800360f5  jz      short loc_1800360FA
0x1800360f7  inc     dword ptr [rbx+68h]
0x1800360fa  mov     rax, [rbp+var_38]
0x1800360fe  test    rax, rax
0x180036101  jz      short loc_18003611A
0x180036103  lea     rcx, [rax+8]; SRWLock
0x180036107  cmp     dword ptr [rax], 1
0x18003610a  jnz     short loc_180036114
0x18003610c  add     dword ptr [rcx], 10000000h
0x180036112  jmp     short loc_18003611A
0x180036114  call    cs:__imp_ReleaseSRWLockExclusive
0x18003611a  test    edi, edi
0x18003611c  js      short loc_18003614A
0x18003611e  mov     rax, rbx
0x180036121  lea     rcx, [rbx+10h]
0x180036125  neg     rax
0x180036128  sbb     r8, r8
0x18003612b  and     r8, rcx
0x18003612e  lea     rdx, [rbx+98h]
0x180036135  mov     [rsp+70h+var_50], esi
0x180036139  mov     r9d, 1
0x18003613f  lea     rcx, [rbp+var_20]
0x180036143  call    ?RaiseEvent@?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<Windows::ApplicationModel::Search::Core::SearchSuggestion *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x180036148  mov     edi, eax
0x18003614a  mov     rcx, qword ptr [rbp+var_30]
0x18003614e  cmp     byte ptr [rbp+var_30+8], 0
0x180036152  jz      short loc_18003615B
0x180036154  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x180036159  jmp     short loc_18003616D
0x18003615b  test    rcx, rcx
0x18003615e  jz      short loc_18003616D
0x180036160  mov     rax, [rcx]
0x180036163  mov     rax, [rax+10h]
0x180036167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003616c  nop
0x18003616d  mov     rax, [rbp+var_18]
0x180036171  test    rax, rax
0x180036174  jz      short loc_18003617C
0x180036176  mov     dword ptr [rax], 0
0x18003617c  mov     eax, edi
0x18003617e  lea     r11, [rsp+70h+var_s0]
0x180036183  mov     rbx, [r11+20h]
0x180036187  mov     rsi, [r11+28h]
0x18003618b  mov     rsp, r11
0x18003618e  pop     r14
0x180036190  pop     rdi
0x180036191  pop     rbp
0x180036192  retn
```
