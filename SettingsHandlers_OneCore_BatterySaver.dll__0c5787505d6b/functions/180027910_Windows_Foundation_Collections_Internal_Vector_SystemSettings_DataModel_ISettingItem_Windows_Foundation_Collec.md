# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(uint,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x180027910`
- end: `0x180027b15`
- name: `?ReplaceAll@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800188ec`
- `0x18001aff8`
- `0x180023548`
- `0x180025f80`
- `0x1800271ec`
- `0x180027910`
- `0x18002a724`
- `0x18002c540`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ab7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ab7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027958`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027958`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027a57`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v4; // r14d
  _DWORD *v6; // r12
  int v7; // r13d
  _QWORD *v8; // rbx
  int v9; // esi
  __int64 v10; // r15
  __int64 v11; // rdx
  char *v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rax
  RTL_SRWLOCK *v17; // rcx
  unsigned int v18; // r13d
  __int64 v19; // r12
  void *v20; // rcx
  char *v22; // [rsp+30h] [rbp-30h] BYREF
  int v23; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v24; // [rsp+40h] [rbp-20h]
  char v25[24]; // [rsp+48h] [rbp-18h] BYREF
  int v27; // [rsp+B8h] [rbp+58h] BYREF

  v3 = a3;
  v4 = a2;
  v27 = 0;
  v23 = -2147483627;
  v6 = 0;
  v24 = 0;
  v7 = 0;
  if ( a2 )
  {
    v8 = malloc(16LL * a2);
    if ( !v8 )
    {
      v9 = -2147024882;
      goto LABEL_28;
    }
    v10 = 0;
    while ( 1 )
    {
      v11 = *(_QWORD *)(v3 + 8 * v10);
      v12 = (char *)&v8[2 * (unsigned int)v10];
      v22 = v12;
      *(_QWORD *)v12 = 0;
      v12[8] = 0;
      v9 = XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::Initialize(v12, v11);
      v27 = v9;
      if ( v9 < 0 )
        break;
      v13 = v7 + 1;
      if ( !v22[8] )
        v13 = v7;
      v7 = v13;
      v10 = (unsigned int)(v10 + 1);
      v3 = a3;
      if ( (unsigned int)v10 >= v4 )
        goto LABEL_11;
    }
  }
  else
  {
    LODWORD(v10) = 0;
    v8 = 0;
    v4 = 0;
LABEL_11:
    XWinRT::SerializingLockPolicy::Write(&v22, a1 + 128, &v27);
    v9 = v27;
    if ( v27 >= 0 )
    {
      v14 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(v25, *(unsigned int *)(a1 + 176), a1 + 180);
      XWinRT::detail::ReentrancyGuard<1>::operator=(&v23, v14);
      v9 = XWinRT::detail::ReentrancyGuard<1>::hr(&v23);
      v6 = v24;
      if ( v9 >= 0 )
      {
        v15 = *(_DWORD *)(a1 + 96);
        *(_DWORD *)(a1 + 96) = v10;
        LODWORD(v10) = v15;
        *(_DWORD *)(a1 + 100) = v4;
        *(_DWORD *)(a1 + 104) = v7;
        v16 = *(_QWORD **)(a1 + 112);
        *(_QWORD *)(a1 + 112) = v8;
        v8 = v16;
        ++*(_DWORD *)(a1 + 144);
      }
    }
    if ( v22 )
    {
      v17 = (RTL_SRWLOCK *)(v22 + 8);
      if ( *(_DWORD *)v22 == 1 )
        LODWORD(v17->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v17);
    }
  }
  if ( v8 )
  {
    v18 = 0;
    if ( (_DWORD)v10 )
    {
      v19 = 0;
      do
      {
        v20 = (void *)v8[2 * v19];
        if ( LOBYTE(v8[2 * v19 + 1]) )
        {
          XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v20);
        }
        else if ( v20 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
        }
        LOBYTE(v8[2 * v19 + 1]) = 0;
        v8[2 * v19] = 0;
        ++v18;
        ++v19;
      }
      while ( v18 < (unsigned int)v10 );
      v6 = v24;
    }
    free(v8);
  }
LABEL_28:
  if ( v9 >= 0 )
    v9 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           (unsigned int)&v23,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           0,
           0);
  if ( v6 )
    *v6 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027910  mov     [rsp-38h+arg_0], rbx
0x180027915  mov     [rsp-38h+arg_10], r8
0x18002791a  push    rbp
0x18002791b  push    rsi
0x18002791c  push    rdi
0x18002791d  push    r12
0x18002791f  push    r13
0x180027921  push    r14
0x180027923  push    r15
0x180027925  mov     rbp, rsp
0x180027928  sub     rsp, 60h
0x18002792c  mov     rsi, r8
0x18002792f  mov     r14d, edx
0x180027932  mov     rdi, rcx
0x180027935  mov     [rbp+arg_18], 0
0x18002793c  mov     [rbp+var_28], 80000015h
0x180027943  xor     r12d, r12d
0x180027946  mov     [rbp+var_20], r12
0x18002794a  xor     r13d, r13d
0x18002794d  test    edx, edx
0x18002794f  jz      short loc_1800279C2
0x180027951  mov     ecx, r14d
0x180027954  shl     rcx, 4; Size
0x180027958  call    cs:__imp_malloc
0x18002795e  mov     rbx, rax
0x180027961  test    rax, rax
0x180027964  jnz     short loc_180027970
0x180027966  mov     esi, 8007000Eh
0x18002796b  jmp     loc_180027ABD
0x180027970  xor     r15d, r15d
0x180027973  mov     eax, r15d
0x180027976  mov     rdx, [rsi+r15*8]
0x18002797a  shl     rax, 4
0x18002797e  add     rax, rbx
0x180027981  mov     [rbp+var_30], rax
0x180027985  mov     [rax], r12
0x180027988  mov     [rax+8], r12b
0x18002798c  mov     rcx, rax
0x18002798f  call    ?Initialize@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAJPEAUISettingItem@DataModel@SystemSettings@@@Z; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::Initialize(SystemSettings::DataModel::ISettingItem *)
0x180027994  mov     esi, eax
0x180027996  mov     [rbp+arg_18], eax
0x180027999  test    eax, eax
0x18002799b  js      loc_180027A5D
0x1800279a1  lea     eax, [r13+1]
0x1800279a5  mov     rcx, [rbp+var_30]
0x1800279a9  cmp     [rcx+8], r12b
0x1800279ad  cmovz   eax, r13d
0x1800279b1  mov     r13d, eax
0x1800279b4  inc     r15d
0x1800279b7  cmp     r15d, r14d
0x1800279ba  mov     rsi, [rbp+arg_10]
0x1800279be  jb      short loc_180027973
0x1800279c0  jmp     short loc_1800279CA
0x1800279c2  xor     r15d, r15d
0x1800279c5  xor     ebx, ebx
0x1800279c7  xor     r14d, r14d
0x1800279ca  lea     rdx, [rdi+80h]
0x1800279d1  lea     r8, [rbp+arg_18]
0x1800279d5  lea     rcx, [rbp+var_30]
0x1800279d9  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800279de  mov     esi, [rbp+arg_18]
0x1800279e1  test    esi, esi
0x1800279e3  js      short loc_180027A3D
0x1800279e5  lea     r8, [rdi+0B4h]
0x1800279ec  mov     edx, [rdi+0B0h]
0x1800279f2  lea     rcx, [rbp+var_18]
0x1800279f6  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x1800279fb  mov     rdx, rax
0x1800279fe  lea     rcx, [rbp+var_28]
0x180027a02  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x180027a07  lea     rcx, [rbp+var_28]
0x180027a0b  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x180027a10  mov     esi, eax
0x180027a12  mov     r12, [rbp+var_20]
0x180027a16  test    eax, eax
0x180027a18  js      short loc_180027A3D
0x180027a1a  mov     eax, [rdi+60h]
0x180027a1d  mov     [rdi+60h], r15d
0x180027a21  mov     r15d, eax
0x180027a24  mov     [rdi+64h], r14d
0x180027a28  mov     [rdi+68h], r13d
0x180027a2c  mov     rax, [rdi+70h]
0x180027a30  mov     [rdi+70h], rbx
0x180027a34  mov     rbx, rax
0x180027a37  inc     dword ptr [rdi+90h]
0x180027a3d  mov     rax, [rbp+var_30]
0x180027a41  test    rax, rax
0x180027a44  jz      short loc_180027A5D
0x180027a46  lea     rcx, [rax+8]; SRWLock
0x180027a4a  cmp     dword ptr [rax], 1
0x180027a4d  jnz     short loc_180027A57
0x180027a4f  add     dword ptr [rcx], 10000000h
0x180027a55  jmp     short loc_180027A5D
0x180027a57  call    cs:__imp_ReleaseSRWLockExclusive
0x180027a5d  test    rbx, rbx
0x180027a60  jz      short loc_180027ABD
0x180027a62  xor     r13d, r13d
0x180027a65  test    r15d, r15d
0x180027a68  jz      short loc_180027AB4
0x180027a6a  xor     r12d, r12d
0x180027a6d  mov     r14, r12
0x180027a70  add     r14, r14
0x180027a73  mov     rcx, [rbx+r14*8]; void *
0x180027a77  cmp     byte ptr [rbx+r14*8+8], 0
0x180027a7d  jz      short loc_180027A86
0x180027a7f  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x180027a84  jmp     short loc_180027A97
0x180027a86  test    rcx, rcx
0x180027a89  jz      short loc_180027A97
0x180027a8b  mov     rax, [rcx]
0x180027a8e  mov     rax, [rax+10h]
0x180027a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a97  mov     byte ptr [rbx+r14*8+8], 0
0x180027a9d  mov     qword ptr [rbx+r14*8], 0
0x180027aa5  inc     r13d
0x180027aa8  inc     r12
0x180027aab  cmp     r13d, r15d
0x180027aae  jb      short loc_180027A6D
0x180027ab0  mov     r12, [rbp+var_20]
0x180027ab4  mov     rcx, rbx; Block
0x180027ab7  call    cs:__imp_free
0x180027abd  test    esi, esi
0x180027abf  js      short loc_180027AEE
0x180027ac1  mov     rax, rdi
0x180027ac4  lea     rcx, [rdi+10h]
0x180027ac8  neg     rax
0x180027acb  sbb     r8, r8
0x180027ace  and     r8, rcx
0x180027ad1  lea     rdx, [rdi+98h]
0x180027ad8  mov     [rsp+60h+var_40], 0
0x180027ae0  xor     r9d, r9d
0x180027ae3  lea     rcx, [rbp+var_28]
0x180027ae7  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x180027aec  mov     esi, eax
0x180027aee  test    r12, r12
0x180027af1  jz      short loc_180027AFB
0x180027af3  mov     dword ptr [r12], 0
0x180027afb  mov     eax, esi
0x180027afd  mov     rbx, [rsp+60h+arg_0]
0x180027b05  add     rsp, 60h
0x180027b09  pop     r15
0x180027b0b  pop     r14
0x180027b0d  pop     r13
0x180027b0f  pop     r12
0x180027b11  pop     rdi
0x180027b12  pop     rsi
0x180027b13  pop     rbp
0x180027b14  retn
```
