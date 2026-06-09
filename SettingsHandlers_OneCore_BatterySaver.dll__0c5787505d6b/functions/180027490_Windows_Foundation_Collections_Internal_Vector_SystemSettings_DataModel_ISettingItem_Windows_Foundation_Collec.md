# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x180027490`
- end: `0x18002768a`
- name: `?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180027470`
- `0x180027480`

## callees

- `0x1800188ec`
- `0x18001aff8`
- `0x180025f80`
- `0x1800271ec`
- `0x180027490`
- `0x180027e20`
- `0x18002a724`
- `0x18002c540`
- `0x18002ca30`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027605`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027605`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027508`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800275a3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027508`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800275a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  void *v6; // r15
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
        v6 = *(void **)v12;
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
            v8 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(
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
    XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v6);
  }
  else if ( v6 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           (unsigned int)&v17,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           2,
           a2);
  if ( v18 )
    *v18 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027490  mov     [rsp-38h+arg_8], rbx
0x180027495  push    rbp
0x180027496  push    rsi
0x180027497  push    rdi
0x180027498  push    r12
0x18002749a  push    r13
0x18002749c  push    r14
0x18002749e  push    r15
0x1800274a0  mov     rbp, rsp
0x1800274a3  sub     rsp, 50h
0x1800274a7  mov     r13b, r8b
0x1800274aa  mov     r14d, edx
0x1800274ad  mov     rbx, rcx
0x1800274b0  mov     [rbp+arg_0], 0
0x1800274b7  mov     [rbp+var_20], 80000015h
0x1800274be  mov     [rbp+var_18], 0
0x1800274c6  xor     r15d, r15d
0x1800274c9  xor     r12b, r12b
0x1800274cc  lea     rdx, [rcx+80h]
0x1800274d3  lea     r8, [rbp+arg_0]
0x1800274d7  lea     rcx, [rbp+arg_18]
0x1800274db  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800274e0  mov     edi, [rbp+arg_0]
0x1800274e3  test    edi, edi
0x1800274e5  js      loc_1800275EB
0x1800274eb  lea     rsi, [rbx+60h]
0x1800274ef  test    r13b, r13b
0x1800274f2  jz      short loc_1800274FA
0x1800274f4  mov     r14d, [rsi]
0x1800274f7  dec     r14d
0x1800274fa  cmp     r14d, [rsi]
0x1800274fd  jb      short loc_18002750E
0x1800274ff  xor     edx, edx
0x180027501  mov     edi, 8000000Bh
0x180027506  mov     ecx, edi
0x180027508  call    cs:__imp_RoOriginateError
0x18002750e  test    edi, edi
0x180027510  js      loc_1800275EB
0x180027516  lea     r8, [rbx+0B4h]
0x18002751d  mov     edx, [rbx+0B0h]
0x180027523  lea     rcx, [rbp+var_10]
0x180027527  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18002752c  mov     rdx, rax
0x18002752f  lea     rcx, [rbp+var_20]
0x180027533  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180027538  lea     rcx, [rbp+var_20]
0x18002753c  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x180027541  mov     edi, eax
0x180027543  test    eax, eax
0x180027545  js      loc_1800275EB
0x18002754b  mov     r9, [rbx+70h]
0x18002754f  mov     ecx, r14d
0x180027552  shl     rcx, 4
0x180027556  add     rcx, r9; Destination
0x180027559  or      r13d, 0FFFFFFFFh
0x18002755d  cmp     [rcx+8], r12b
0x180027561  jz      short loc_180027567
0x180027563  add     [rbx+68h], r13d
0x180027567  mov     r15, [rcx]
0x18002756a  mov     r12b, [rcx+8]
0x18002756e  mov     edx, [rsi]
0x180027570  lea     eax, [rdx-1]
0x180027573  cmp     r14d, eax
0x180027576  jnb     short loc_1800275AB
0x180027578  mov     eax, r14d
0x18002757b  not     eax
0x18002757d  add     edx, eax
0x18002757f  shl     rdx, 4; DestinationSize
0x180027583  lea     r8d, [r14+1]
0x180027587  shl     r8, 4
0x18002758b  add     r8, r9; Source
0x18002758e  mov     r9, rdx; SourceSize
0x180027591  call    memmove_s
0x180027596  test    eax, eax
0x180027598  jz      short loc_1800275AB
0x18002759a  xor     edx, edx
0x18002759c  mov     edi, 8000FFFFh
0x1800275a1  mov     ecx, edi
0x1800275a3  call    cs:__imp_RoOriginateError
0x1800275a9  jmp     short loc_1800275EB
0x1800275ab  inc     dword ptr [rbx+90h]
0x1800275b1  add     [rsi], r13d
0x1800275b4  mov     r9d, [rbx+64h]
0x1800275b8  mov     eax, 0AAAAAAABh
0x1800275bd  mul     r9d
0x1800275c0  shr     edx, 1
0x1800275c2  cmp     [rsi], edx
0x1800275c4  jnb     short loc_1800275EB
0x1800275c6  mov     ecx, r9d
0x1800275c9  sub     ecx, edx
0x1800275cb  lea     eax, [r9-1]
0x1800275cf  mov     r8d, 1
0x1800275d5  cmp     eax, ecx
0x1800275d7  cmovnb  r8d, edx
0x1800275db  sub     r9d, r8d
0x1800275de  mov     edx, r9d
0x1800275e1  mov     rcx, rbx
0x1800275e4  call    ?ResizeStorage@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(uint)
0x1800275e9  mov     edi, eax
0x1800275eb  mov     rax, [rbp+arg_18]
0x1800275ef  test    rax, rax
0x1800275f2  jz      short loc_18002760C
0x1800275f4  lea     rcx, [rax+8]; SRWLock
0x1800275f8  cmp     dword ptr [rax], 1
0x1800275fb  jnz     short loc_180027605
0x1800275fd  add     dword ptr [rcx], 10000000h
0x180027603  jmp     short loc_18002760C
0x180027605  call    cs:__imp_ReleaseSRWLockExclusive
0x18002760b  nop
0x18002760c  test    r12b, r12b
0x18002760f  jz      short loc_18002761B
0x180027611  mov     rcx, r15; void *
0x180027614  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x180027619  jmp     short loc_180027630
0x18002761b  test    r15, r15
0x18002761e  jz      short loc_180027630
0x180027620  mov     rax, [r15]
0x180027623  mov     rcx, r15
0x180027626  mov     rax, [rax+10h]
0x18002762a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002762f  nop
0x180027630  test    edi, edi
0x180027632  js      short loc_180027661
0x180027634  mov     rax, rbx
0x180027637  lea     rcx, [rbx+10h]
0x18002763b  neg     rax
0x18002763e  sbb     r8, r8
0x180027641  and     r8, rcx
0x180027644  lea     rdx, [rbx+98h]
0x18002764b  mov     [rsp+50h+var_30], r14d
0x180027650  mov     r9d, 2
0x180027656  lea     rcx, [rbp+var_20]
0x18002765a  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18002765f  mov     edi, eax
0x180027661  mov     rax, [rbp+var_18]
0x180027665  test    rax, rax
0x180027668  jz      short loc_180027670
0x18002766a  mov     dword ptr [rax], 0
0x180027670  mov     eax, edi
0x180027672  mov     rbx, [rsp+50h+arg_8]
0x18002767a  add     rsp, 50h
0x18002767e  pop     r15
0x180027680  pop     r14
0x180027682  pop     r13
0x180027684  pop     r12
0x180027686  pop     rdi
0x180027687  pop     rsi
0x180027688  pop     rbp
0x180027689  retn
```
