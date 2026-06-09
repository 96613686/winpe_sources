# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x18001bd20`
- end: `0x18001bf34`
- name: `?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `532`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001bd00`
- `0x18001bd10`

## callees

- `0x18000ee54`
- `0x180011468`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001bd20`
- `0x18001c670`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001be27`
- `msvcrt!memmove_s` at `0x18001be27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bea8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001bd98`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001be40`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001bd98`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001be40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
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
0x18001bd20  mov     [rsp-38h+arg_8], rbx
0x18001bd25  push    rbp
0x18001bd26  push    rsi
0x18001bd27  push    rdi
0x18001bd28  push    r12
0x18001bd2a  push    r13
0x18001bd2c  push    r14
0x18001bd2e  push    r15
0x18001bd30  mov     rbp, rsp
0x18001bd33  sub     rsp, 50h
0x18001bd37  mov     r13b, r8b
0x18001bd3a  mov     r14d, edx
0x18001bd3d  mov     rbx, rcx
0x18001bd40  mov     [rbp+arg_0], 0
0x18001bd47  mov     [rbp+var_20], 80000015h
0x18001bd4e  mov     [rbp+var_18], 0
0x18001bd56  xor     r15d, r15d
0x18001bd59  xor     r12b, r12b
0x18001bd5c  lea     rdx, [rcx+80h]
0x18001bd63  lea     r8, [rbp+arg_0]
0x18001bd67  lea     rcx, [rbp+arg_18]
0x18001bd6b  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001bd70  mov     edi, [rbp+arg_0]
0x18001bd73  test    edi, edi
0x18001bd75  js      loc_18001BE8E
0x18001bd7b  lea     rsi, [rbx+60h]
0x18001bd7f  test    r13b, r13b
0x18001bd82  jz      short loc_18001BD8A
0x18001bd84  mov     r14d, [rsi]
0x18001bd87  dec     r14d
0x18001bd8a  cmp     r14d, [rsi]
0x18001bd8d  jb      short loc_18001BDA4
0x18001bd8f  xor     edx, edx
0x18001bd91  mov     edi, 8000000Bh
0x18001bd96  mov     ecx, edi
0x18001bd98  call    cs:__imp_RoOriginateError
0x18001bd9f  nop     dword ptr [rax+rax+00h]
0x18001bda4  test    edi, edi
0x18001bda6  js      loc_18001BE8E
0x18001bdac  lea     r8, [rbx+0B4h]
0x18001bdb3  mov     edx, [rbx+0B0h]
0x18001bdb9  lea     rcx, [rbp+var_10]
0x18001bdbd  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001bdc2  mov     rdx, rax
0x18001bdc5  lea     rcx, [rbp+var_20]
0x18001bdc9  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18001bdce  lea     rcx, [rbp+var_20]
0x18001bdd2  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001bdd7  mov     edi, eax
0x18001bdd9  test    eax, eax
0x18001bddb  js      loc_18001BE8E
0x18001bde1  mov     r9, [rbx+70h]
0x18001bde5  mov     ecx, r14d
0x18001bde8  shl     rcx, 4
0x18001bdec  add     rcx, r9; Destination
0x18001bdef  or      r13d, 0FFFFFFFFh
0x18001bdf3  cmp     [rcx+8], r12b
0x18001bdf7  jz      short loc_18001BDFD
0x18001bdf9  add     [rbx+68h], r13d
0x18001bdfd  mov     r15, [rcx]
0x18001be00  mov     r12b, [rcx+8]
0x18001be04  mov     edx, [rsi]
0x18001be06  lea     eax, [rdx-1]
0x18001be09  cmp     r14d, eax
0x18001be0c  jnb     short loc_18001BE4E
0x18001be0e  mov     eax, r14d
0x18001be11  not     eax
0x18001be13  add     edx, eax
0x18001be15  shl     rdx, 4; DestinationSize
0x18001be19  lea     r8d, [r14+1]
0x18001be1d  shl     r8, 4
0x18001be21  add     r8, r9; Source
0x18001be24  mov     r9, rdx; SourceSize
0x18001be27  call    cs:__imp_memmove_s
0x18001be2e  nop     dword ptr [rax+rax+00h]
0x18001be33  test    eax, eax
0x18001be35  jz      short loc_18001BE4E
0x18001be37  xor     edx, edx
0x18001be39  mov     edi, 8000FFFFh
0x18001be3e  mov     ecx, edi
0x18001be40  call    cs:__imp_RoOriginateError
0x18001be47  nop     dword ptr [rax+rax+00h]
0x18001be4c  jmp     short loc_18001BE8E
0x18001be4e  inc     dword ptr [rbx+90h]
0x18001be54  add     [rsi], r13d
0x18001be57  mov     r9d, [rbx+64h]
0x18001be5b  mov     eax, 0AAAAAAABh
0x18001be60  mul     r9d
0x18001be63  shr     edx, 1
0x18001be65  cmp     [rsi], edx
0x18001be67  jnb     short loc_18001BE8E
0x18001be69  mov     ecx, r9d
0x18001be6c  sub     ecx, edx
0x18001be6e  lea     eax, [r9-1]
0x18001be72  mov     r8d, 1
0x18001be78  cmp     eax, ecx
0x18001be7a  cmovnb  r8d, edx
0x18001be7e  sub     r9d, r8d
0x18001be81  mov     edx, r9d
0x18001be84  mov     rcx, rbx
0x18001be87  call    ?ResizeStorage@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(uint)
0x18001be8c  mov     edi, eax
0x18001be8e  mov     rax, [rbp+arg_18]
0x18001be92  test    rax, rax
0x18001be95  jz      short loc_18001BEB5
0x18001be97  lea     rcx, [rax+8]; SRWLock
0x18001be9b  cmp     dword ptr [rax], 1
0x18001be9e  jnz     short loc_18001BEA8
0x18001bea0  add     dword ptr [rcx], 10000000h
0x18001bea6  jmp     short loc_18001BEB5
0x18001bea8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001beaf  nop     dword ptr [rax+rax+00h]
0x18001beb4  nop
0x18001beb5  test    r12b, r12b
0x18001beb8  jz      short loc_18001BEC4
0x18001beba  mov     rcx, r15
0x18001bebd  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001bec2  jmp     short loc_18001BED9
0x18001bec4  test    r15, r15
0x18001bec7  jz      short loc_18001BED9
0x18001bec9  mov     rax, [r15]
0x18001becc  mov     rcx, r15
0x18001becf  mov     rax, [rax+10h]
0x18001bed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed8  nop
0x18001bed9  test    edi, edi
0x18001bedb  js      short loc_18001BF0A
0x18001bedd  mov     rax, rbx
0x18001bee0  lea     rcx, [rbx+10h]
0x18001bee4  neg     rax
0x18001bee7  sbb     r8, r8
0x18001beea  and     r8, rcx
0x18001beed  lea     rdx, [rbx+98h]
0x18001bef4  mov     [rsp+50h+var_30], r14d
0x18001bef9  mov     r9d, 2
0x18001beff  lea     rcx, [rbp+var_20]
0x18001bf03  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001bf08  mov     edi, eax
0x18001bf0a  mov     rax, [rbp+var_18]
0x18001bf0e  test    rax, rax
0x18001bf11  jz      short loc_18001BF19
0x18001bf13  mov     dword ptr [rax], 0
0x18001bf19  mov     eax, edi
0x18001bf1b  mov     rbx, [rsp+50h+arg_8]
0x18001bf23  add     rsp, 50h
0x18001bf27  pop     r15
0x18001bf29  pop     r14
0x18001bf2b  pop     r13
0x18001bf2d  pop     r12
0x18001bf2f  pop     rdi
0x18001bf30  pop     rsi
0x18001bf31  pop     rbp
0x18001bf32  retn
```
