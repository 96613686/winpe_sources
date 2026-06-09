# Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x180037610`
- end: `0x18003780b`
- name: `?RemoveAtInternal@?$Vector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@7895@U?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800375c0`
- `0x180037600`

## callees

- `0x18001c7d0`
- `0x18001d104`
- `0x180032d7c`
- `0x1800338e4`
- `0x180037124`
- `0x180037610`
- `0x180037cc8`
- `0x1800399d4`
- `0x18007b010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180037711`
- `msvcrt!memmove_s` at `0x180037711`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037786`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180037688`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180037724`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180037688`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180037724`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  __int64 v6; // r15
  char v7; // r12
  int v8; // edi
  unsigned int *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // r9
  _BYTE *v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // r8d
  RTL_SRWLOCK *v15; // rcx
  int v17; // [rsp+30h] [rbp-20h] BYREF
  _DWORD *v18; // [rsp+38h] [rbp-18h]
  _BYTE v19[16]; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+90h] [rbp+40h] BYREF
  RTL_SRWLOCK *v21; // [rsp+A8h] [rbp+58h] BYREF

  v20 = 0;
  v17 = -2147483627;
  v18 = 0;
  v6 = 0;
  v7 = 0;
  XWinRT::SerializingLockPolicy::Write(&v21, a1 + 128, &v20);
  v8 = v20;
  if ( v20 >= 0 )
  {
    v9 = (unsigned int *)(a1 + 96);
    if ( a3 )
      a2 = *v9 - 1;
    if ( a2 >= *v9 )
    {
      v8 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
    if ( v8 >= 0 )
    {
      v10 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(v19, *(unsigned int *)(a1 + 176), a1 + 180);
      XWinRT::detail::ReentrancyGuard<1>::operator=(&v17, v10);
      v8 = XWinRT::detail::ReentrancyGuard<1>::hr(&v17);
      if ( v8 >= 0 )
      {
        v11 = *(_QWORD *)(a1 + 112);
        v12 = (_BYTE *)(v11 + 16LL * a2);
        if ( v12[8] )
          --*(_DWORD *)(a1 + 104);
        v6 = *(_QWORD *)v12;
        v7 = v12[8];
        if ( a2 < *v9 - 1
          && memmove_s(v12, 16LL * (~a2 + *v9), (const void *const)(v11 + 16LL * (a2 + 1)), 16LL * (~a2 + *v9)) )
        {
          v8 = -2147418113;
          RoOriginateError(2147549183LL, 0);
        }
        else
        {
          ++*(_DWORD *)(a1 + 144);
          --*v9;
          v13 = *(_DWORD *)(a1 + 100);
          if ( *v9 < v13 / 3 )
          {
            v14 = 1;
            if ( v13 - 1 >= v13 - v13 / 3 )
              v14 = v13 / 3;
            v8 = Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::ResizeStorage(
                   a1,
                   v13 - v14);
          }
        }
      }
    }
  }
  if ( v21 )
  {
    v15 = v21 + 1;
    if ( LODWORD(v21->Ptr) == 1 )
      LODWORD(v15->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v15);
  }
  if ( v7 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v6);
  }
  else if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(
           &v17,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           2,
           a2);
  if ( v18 )
    *v18 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037610  mov     [rsp-38h+arg_8], rbx
0x180037615  push    rbp
0x180037616  push    rsi
0x180037617  push    rdi
0x180037618  push    r12
0x18003761a  push    r13
0x18003761c  push    r14
0x18003761e  push    r15
0x180037620  mov     rbp, rsp
0x180037623  sub     rsp, 50h
0x180037627  mov     r13b, r8b
0x18003762a  mov     r14d, edx
0x18003762d  mov     rbx, rcx
0x180037630  mov     [rbp+arg_0], 0
0x180037637  mov     [rbp+var_20], 80000015h
0x18003763e  mov     [rbp+var_18], 0
0x180037646  xor     r15d, r15d
0x180037649  xor     r12b, r12b
0x18003764c  lea     rdx, [rcx+80h]
0x180037653  lea     r8, [rbp+arg_0]
0x180037657  lea     rcx, [rbp+arg_18]
0x18003765b  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180037660  mov     edi, [rbp+arg_0]
0x180037663  test    edi, edi
0x180037665  js      loc_18003776C
0x18003766b  lea     rsi, [rbx+60h]
0x18003766f  test    r13b, r13b
0x180037672  jz      short loc_18003767A
0x180037674  mov     r14d, [rsi]
0x180037677  dec     r14d
0x18003767a  cmp     r14d, [rsi]
0x18003767d  jb      short loc_18003768E
0x18003767f  xor     edx, edx
0x180037681  mov     edi, 8000000Bh
0x180037686  mov     ecx, edi
0x180037688  call    cs:__imp_RoOriginateError
0x18003768e  test    edi, edi
0x180037690  js      loc_18003776C
0x180037696  lea     r8, [rbx+0B4h]
0x18003769d  mov     edx, [rbx+0B0h]
0x1800376a3  lea     rcx, [rbp+var_10]
0x1800376a7  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x1800376ac  mov     rdx, rax
0x1800376af  lea     rcx, [rbp+var_20]
0x1800376b3  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x1800376b8  lea     rcx, [rbp+var_20]
0x1800376bc  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x1800376c1  mov     edi, eax
0x1800376c3  test    eax, eax
0x1800376c5  js      loc_18003776C
0x1800376cb  mov     r9, [rbx+70h]
0x1800376cf  mov     ecx, r14d
0x1800376d2  shl     rcx, 4
0x1800376d6  add     rcx, r9; Destination
0x1800376d9  or      r13d, 0FFFFFFFFh
0x1800376dd  cmp     [rcx+8], r12b
0x1800376e1  jz      short loc_1800376E7
0x1800376e3  add     [rbx+68h], r13d
0x1800376e7  mov     r15, [rcx]
0x1800376ea  mov     r12b, [rcx+8]
0x1800376ee  mov     edx, [rsi]
0x1800376f0  lea     eax, [rdx-1]
0x1800376f3  cmp     r14d, eax
0x1800376f6  jnb     short loc_18003772C
0x1800376f8  mov     eax, r14d
0x1800376fb  not     eax
0x1800376fd  add     edx, eax
0x1800376ff  shl     rdx, 4; DestinationSize
0x180037703  lea     r8d, [r14+1]
0x180037707  shl     r8, 4
0x18003770b  add     r8, r9; Source
0x18003770e  mov     r9, rdx; SourceSize
0x180037711  call    cs:__imp_memmove_s
0x180037717  test    eax, eax
0x180037719  jz      short loc_18003772C
0x18003771b  xor     edx, edx
0x18003771d  mov     edi, 8000FFFFh
0x180037722  mov     ecx, edi
0x180037724  call    cs:__imp_RoOriginateError
0x18003772a  jmp     short loc_18003776C
0x18003772c  inc     dword ptr [rbx+90h]
0x180037732  add     [rsi], r13d
0x180037735  mov     r9d, [rbx+64h]
0x180037739  mov     eax, 0AAAAAAABh
0x18003773e  mul     r9d
0x180037741  shr     edx, 1
0x180037743  cmp     [rsi], edx
0x180037745  jnb     short loc_18003776C
0x180037747  mov     ecx, r9d
0x18003774a  sub     ecx, edx
0x18003774c  lea     eax, [r9-1]
0x180037750  mov     r8d, 1
0x180037756  cmp     eax, ecx
0x180037758  cmovnb  r8d, edx
0x18003775c  sub     r9d, r8d
0x18003775f  mov     edx, r9d
0x180037762  mov     rcx, rbx
0x180037765  call    ?ResizeStorage@?$Vector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@7895@U?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::ResizeStorage(uint)
0x18003776a  mov     edi, eax
0x18003776c  mov     rax, [rbp+arg_18]
0x180037770  test    rax, rax
0x180037773  jz      short loc_18003778D
0x180037775  lea     rcx, [rax+8]; SRWLock
0x180037779  cmp     dword ptr [rax], 1
0x18003777c  jnz     short loc_180037786
0x18003777e  add     dword ptr [rcx], 10000000h
0x180037784  jmp     short loc_18003778D
0x180037786  call    cs:__imp_ReleaseSRWLockExclusive
0x18003778c  nop
0x18003778d  test    r12b, r12b
0x180037790  jz      short loc_18003779C
0x180037792  mov     rcx, r15
0x180037795  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18003779a  jmp     short loc_1800377B1
0x18003779c  test    r15, r15
0x18003779f  jz      short loc_1800377B1
0x1800377a1  mov     rax, [r15]
0x1800377a4  mov     rcx, r15
0x1800377a7  mov     rax, [rax+10h]
0x1800377ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377b0  nop
0x1800377b1  test    edi, edi
0x1800377b3  js      short loc_1800377E2
0x1800377b5  mov     rax, rbx
0x1800377b8  lea     rcx, [rbx+10h]
0x1800377bc  neg     rax
0x1800377bf  sbb     r8, r8
0x1800377c2  and     r8, rcx
0x1800377c5  lea     rdx, [rbx+98h]
0x1800377cc  mov     [rsp+50h+var_30], r14d
0x1800377d1  mov     r9d, 2
0x1800377d7  lea     rcx, [rbp+var_20]
0x1800377db  call    ?RaiseEvent@?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<Windows::ApplicationModel::Search::Core::SearchSuggestion *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x1800377e0  mov     edi, eax
0x1800377e2  mov     rax, [rbp+var_18]
0x1800377e6  test    rax, rax
0x1800377e9  jz      short loc_1800377F1
0x1800377eb  mov     dword ptr [rax], 0
0x1800377f1  mov     eax, edi
0x1800377f3  mov     rbx, [rsp+50h+arg_8]
0x1800377fb  add     rsp, 50h
0x1800377ff  pop     r15
0x180037801  pop     r14
0x180037803  pop     r13
0x180037805  pop     r12
0x180037807  pop     rdi
0x180037808  pop     rsi
0x180037809  pop     rbp
0x18003780a  retn
```
