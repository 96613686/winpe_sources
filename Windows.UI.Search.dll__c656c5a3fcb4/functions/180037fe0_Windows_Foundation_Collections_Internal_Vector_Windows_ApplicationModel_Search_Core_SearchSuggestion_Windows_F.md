# Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::SetAt(uint,Windows::ApplicationModel::Search::Core::ISearchSuggestion *)

- ea: `0x180037fe0`
- end: `0x1800381e3`
- name: `?SetAt@?$Vector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@7895@U?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUISearchSuggestion@Core@Search@ApplicationModel@5@@Z`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18001c7d0`
- `0x18001d104`
- `0x1800310f0`
- `0x180032d7c`
- `0x1800338e4`
- `0x180037124`
- `0x180037fe0`
- `0x1800399d4`
- `0x18007b010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800380ca`
- `msvcrt!memmove_s` at `0x1800380ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003813a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003813a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180038069`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800380dd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180038069`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800380dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Search::Core::SearchSuggestion *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>>::SetAt(
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
  XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>(
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
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v13);
  }
  else if ( (_QWORD)v13 )
  {
    (*(void (**)(void))(*(_QWORD *)v13 + 16LL))();
  }
  if ( v6 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v5);
  }
  else if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(
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
0x180037fe0  mov     [rsp-28h+arg_0], rbx
0x180037fe5  mov     [rsp-28h+arg_8], rsi
0x180037fea  mov     [rsp-28h+arg_10], r8
0x180037fef  push    rbp
0x180037ff0  push    rdi
0x180037ff1  push    r12
0x180037ff3  push    r14
0x180037ff5  push    r15
0x180037ff7  mov     rbp, rsp
0x180037ffa  sub     rsp, 70h
0x180037ffe  mov     r12d, edx
0x180038001  mov     rdi, rcx
0x180038004  mov     [rbp+arg_18], 0
0x18003800b  mov     [rbp+var_28], 80000015h
0x180038012  mov     [rbp+var_20], 0
0x18003801a  xor     esi, esi
0x18003801c  xor     r15b, r15b
0x18003801f  lea     r8, [rbp+arg_18]
0x180038023  lea     rdx, [rbp+arg_10]
0x180038027  lea     rcx, [rbp+var_38]
0x18003802b  call    ??$?0PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@?$AutoValue@V?$GitStorageType@UISearchSuggestion@Core@Search@ApplicationModel@Windows@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::ApplicationModel::Search::Core::ISearchSuggestion>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>(Windows::ApplicationModel::Search::Core::ISearchSuggestion * const &,long *)
0x180038030  mov     ebx, [rbp+arg_18]
0x180038033  test    ebx, ebx
0x180038035  js      loc_180038141
0x18003803b  lea     rdx, [rdi+80h]
0x180038042  lea     r8, [rbp+arg_18]
0x180038046  lea     rcx, [rbp+var_40]
0x18003804a  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18003804f  mov     ebx, [rbp+arg_18]
0x180038052  test    ebx, ebx
0x180038054  js      loc_180038120
0x18003805a  cmp     r12d, [rdi+60h]
0x18003805e  jb      short loc_18003806F
0x180038060  xor     edx, edx
0x180038062  mov     ebx, 8000000Bh
0x180038067  mov     ecx, ebx
0x180038069  call    cs:__imp_RoOriginateError
0x18003806f  test    ebx, ebx
0x180038071  js      loc_180038120
0x180038077  lea     r8, [rdi+0B4h]
0x18003807e  mov     edx, [rdi+0B0h]
0x180038084  lea     rcx, [rbp+Destination]
0x180038088  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18003808d  mov     rdx, rax
0x180038090  lea     rcx, [rbp+var_28]
0x180038094  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180038099  lea     rcx, [rbp+var_28]
0x18003809d  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x1800380a2  mov     ebx, eax
0x1800380a4  test    eax, eax
0x1800380a6  js      short loc_180038120
0x1800380a8  mov     [rbp+Destination], rsi
0x1800380ac  mov     [rbp+var_10], sil
0x1800380b0  mov     r14, r12
0x1800380b3  shl     r14, 4
0x1800380b7  mov     r8, [rdi+70h]
0x1800380bb  add     r8, r14; Source
0x1800380be  mov     edx, 10h; DestinationSize
0x1800380c3  mov     r9d, edx; SourceSize
0x1800380c6  lea     rcx, [rbp+Destination]; Destination
0x1800380ca  call    cs:__imp_memmove_s
0x1800380d0  test    eax, eax
0x1800380d2  jz      short loc_1800380E5
0x1800380d4  xor     edx, edx
0x1800380d6  mov     ebx, 8000FFFFh
0x1800380db  mov     ecx, ebx
0x1800380dd  call    cs:__imp_RoOriginateError
0x1800380e3  jmp     short loc_180038120
0x1800380e5  mov     rax, [rdi+70h]
0x1800380e9  movups  xmm0, [rbp+var_38]
0x1800380ed  movdqu  xmmword ptr [r14+rax], xmm0
0x1800380f3  mov     qword ptr [rbp+var_38], rsi
0x1800380f7  mov     byte ptr [rbp+var_38+8], sil
0x1800380fb  inc     dword ptr [rdi+90h]
0x180038101  mov     rsi, [rbp+Destination]
0x180038105  mov     r15b, [rbp+var_10]
0x180038109  mov     rax, [rdi+70h]
0x18003810d  cmp     byte ptr [r14+rax+8], 0
0x180038113  jz      short loc_180038118
0x180038115  inc     dword ptr [rdi+68h]
0x180038118  test    r15b, r15b
0x18003811b  jz      short loc_180038120
0x18003811d  dec     dword ptr [rdi+68h]
0x180038120  mov     rax, [rbp+var_40]
0x180038124  test    rax, rax
0x180038127  jz      short loc_180038141
0x180038129  lea     rcx, [rax+8]; SRWLock
0x18003812d  cmp     dword ptr [rax], 1
0x180038130  jnz     short loc_18003813A
0x180038132  add     dword ptr [rcx], 10000000h
0x180038138  jmp     short loc_180038141
0x18003813a  call    cs:__imp_ReleaseSRWLockExclusive
0x180038140  nop
0x180038141  mov     rcx, qword ptr [rbp+var_38]
0x180038145  cmp     byte ptr [rbp+var_38+8], 0
0x180038149  jz      short loc_180038152
0x18003814b  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x180038150  jmp     short loc_180038164
0x180038152  test    rcx, rcx
0x180038155  jz      short loc_180038164
0x180038157  mov     rax, [rcx]
0x18003815a  mov     rax, [rax+10h]
0x18003815e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038163  nop
0x180038164  test    r15b, r15b
0x180038167  jz      short loc_180038173
0x180038169  mov     rcx, rsi
0x18003816c  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x180038171  jmp     short loc_180038188
0x180038173  test    rsi, rsi
0x180038176  jz      short loc_180038188
0x180038178  mov     rax, [rsi]
0x18003817b  mov     rcx, rsi
0x18003817e  mov     rax, [rax+10h]
0x180038182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038187  nop
0x180038188  test    ebx, ebx
0x18003818a  js      short loc_1800381B9
0x18003818c  mov     rax, rdi
0x18003818f  lea     rcx, [rdi+10h]
0x180038193  neg     rax
0x180038196  sbb     r8, r8
0x180038199  and     r8, rcx
0x18003819c  lea     rdx, [rdi+98h]
0x1800381a3  mov     [rsp+70h+var_50], r12d
0x1800381a8  mov     r9d, 3
0x1800381ae  lea     rcx, [rbp+var_28]
0x1800381b2  call    ?RaiseEvent@?$VectorOptions@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<Windows::ApplicationModel::Search::Core::SearchSuggestion *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<Windows::ApplicationModel::Search::Core::SearchSuggestion *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x1800381b7  mov     ebx, eax
0x1800381b9  mov     rax, [rbp+var_20]
0x1800381bd  test    rax, rax
0x1800381c0  jz      short loc_1800381C8
0x1800381c2  mov     dword ptr [rax], 0
0x1800381c8  mov     eax, ebx
0x1800381ca  lea     r11, [rsp+70h+var_s0]
0x1800381cf  mov     rbx, [r11+30h]
0x1800381d3  mov     rsi, [r11+38h]
0x1800381d7  mov     rsp, r11
0x1800381da  pop     r15
0x1800381dc  pop     r14
0x1800381de  pop     r12
0x1800381e0  pop     rdi
0x1800381e1  pop     rbp
0x1800381e2  retn
```
