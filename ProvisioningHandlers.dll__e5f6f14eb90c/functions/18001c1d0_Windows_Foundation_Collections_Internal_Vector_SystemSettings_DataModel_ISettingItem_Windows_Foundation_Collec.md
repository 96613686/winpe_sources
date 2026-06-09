# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(uint,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18001c1d0`
- end: `0x18001c3e8`
- name: `?ReplaceAll@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000ee54`
- `0x180011468`
- `0x180019538`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001c1d0`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!malloc` at `0x18001c218`
- `msvcrt!malloc` at `0x18001c218`
- `msvcrt!free` at `0x18001c383`
- `msvcrt!free` at `0x18001c383`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c31d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c31d`

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
  __int64 v20; // rcx
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
        v20 = v8[2 * v19];
        if ( LOBYTE(v8[2 * v19 + 1]) )
        {
          XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v20);
        }
        else if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
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
           &v23,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           0,
           0);
  if ( v6 )
    *v6 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c1d0  mov     [rsp-38h+arg_0], rbx
0x18001c1d5  mov     [rsp-38h+arg_10], r8
0x18001c1da  push    rbp
0x18001c1db  push    rsi
0x18001c1dc  push    rdi
0x18001c1dd  push    r12
0x18001c1df  push    r13
0x18001c1e1  push    r14
0x18001c1e3  push    r15
0x18001c1e5  mov     rbp, rsp
0x18001c1e8  sub     rsp, 60h
0x18001c1ec  mov     rsi, r8
0x18001c1ef  mov     r14d, edx
0x18001c1f2  mov     rdi, rcx
0x18001c1f5  mov     [rbp+arg_18], 0
0x18001c1fc  mov     [rbp+var_28], 80000015h
0x18001c203  xor     r12d, r12d
0x18001c206  mov     [rbp+var_20], r12
0x18001c20a  xor     r13d, r13d
0x18001c20d  test    edx, edx
0x18001c20f  jz      short loc_18001C288
0x18001c211  mov     ecx, r14d
0x18001c214  shl     rcx, 4; Size
0x18001c218  call    cs:__imp_malloc
0x18001c21f  nop     dword ptr [rax+rax+00h]
0x18001c224  mov     rbx, rax
0x18001c227  test    rax, rax
0x18001c22a  jnz     short loc_18001C236
0x18001c22c  mov     esi, 8007000Eh
0x18001c231  jmp     loc_18001C38F
0x18001c236  xor     r15d, r15d
0x18001c239  mov     eax, r15d
0x18001c23c  mov     rdx, [rsi+r15*8]
0x18001c240  shl     rax, 4
0x18001c244  add     rax, rbx
0x18001c247  mov     [rbp+var_30], rax
0x18001c24b  mov     [rax], r12
0x18001c24e  mov     [rax+8], r12b
0x18001c252  mov     rcx, rax
0x18001c255  call    ?Initialize@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAJPEAUISettingItem@DataModel@SystemSettings@@@Z; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::Initialize(SystemSettings::DataModel::ISettingItem *)
0x18001c25a  mov     esi, eax
0x18001c25c  mov     [rbp+arg_18], eax
0x18001c25f  test    eax, eax
0x18001c261  js      loc_18001C329
0x18001c267  lea     eax, [r13+1]
0x18001c26b  mov     rcx, [rbp+var_30]
0x18001c26f  cmp     [rcx+8], r12b
0x18001c273  cmovz   eax, r13d
0x18001c277  mov     r13d, eax
0x18001c27a  inc     r15d
0x18001c27d  cmp     r15d, r14d
0x18001c280  mov     rsi, [rbp+arg_10]
0x18001c284  jb      short loc_18001C239
0x18001c286  jmp     short loc_18001C290
0x18001c288  xor     r15d, r15d
0x18001c28b  xor     ebx, ebx
0x18001c28d  xor     r14d, r14d
0x18001c290  lea     rdx, [rdi+80h]
0x18001c297  lea     r8, [rbp+arg_18]
0x18001c29b  lea     rcx, [rbp+var_30]
0x18001c29f  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001c2a4  mov     esi, [rbp+arg_18]
0x18001c2a7  test    esi, esi
0x18001c2a9  js      short loc_18001C303
0x18001c2ab  lea     r8, [rdi+0B4h]
0x18001c2b2  mov     edx, [rdi+0B0h]
0x18001c2b8  lea     rcx, [rbp+var_18]
0x18001c2bc  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001c2c1  mov     rdx, rax
0x18001c2c4  lea     rcx, [rbp+var_28]
0x18001c2c8  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18001c2cd  lea     rcx, [rbp+var_28]
0x18001c2d1  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001c2d6  mov     esi, eax
0x18001c2d8  mov     r12, [rbp+var_20]
0x18001c2dc  test    eax, eax
0x18001c2de  js      short loc_18001C303
0x18001c2e0  mov     eax, [rdi+60h]
0x18001c2e3  mov     [rdi+60h], r15d
0x18001c2e7  mov     r15d, eax
0x18001c2ea  mov     [rdi+64h], r14d
0x18001c2ee  mov     [rdi+68h], r13d
0x18001c2f2  mov     rax, [rdi+70h]
0x18001c2f6  mov     [rdi+70h], rbx
0x18001c2fa  mov     rbx, rax
0x18001c2fd  inc     dword ptr [rdi+90h]
0x18001c303  mov     rax, [rbp+var_30]
0x18001c307  test    rax, rax
0x18001c30a  jz      short loc_18001C329
0x18001c30c  lea     rcx, [rax+8]; SRWLock
0x18001c310  cmp     dword ptr [rax], 1
0x18001c313  jnz     short loc_18001C31D
0x18001c315  add     dword ptr [rcx], 10000000h
0x18001c31b  jmp     short loc_18001C329
0x18001c31d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c324  nop     dword ptr [rax+rax+00h]
0x18001c329  test    rbx, rbx
0x18001c32c  jz      short loc_18001C38F
0x18001c32e  xor     r13d, r13d
0x18001c331  test    r15d, r15d
0x18001c334  jz      short loc_18001C380
0x18001c336  xor     r12d, r12d
0x18001c339  mov     r14, r12
0x18001c33c  add     r14, r14
0x18001c33f  mov     rcx, [rbx+r14*8]
0x18001c343  cmp     byte ptr [rbx+r14*8+8], 0
0x18001c349  jz      short loc_18001C352
0x18001c34b  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001c350  jmp     short loc_18001C363
0x18001c352  test    rcx, rcx
0x18001c355  jz      short loc_18001C363
0x18001c357  mov     rax, [rcx]
0x18001c35a  mov     rax, [rax+10h]
0x18001c35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c363  mov     byte ptr [rbx+r14*8+8], 0
0x18001c369  mov     qword ptr [rbx+r14*8], 0
0x18001c371  inc     r13d
0x18001c374  inc     r12
0x18001c377  cmp     r13d, r15d
0x18001c37a  jb      short loc_18001C339
0x18001c37c  mov     r12, [rbp+var_20]
0x18001c380  mov     rcx, rbx; Block
0x18001c383  call    cs:__imp_free
0x18001c38a  nop     dword ptr [rax+rax+00h]
0x18001c38f  test    esi, esi
0x18001c391  js      short loc_18001C3C0
0x18001c393  mov     rax, rdi
0x18001c396  lea     rcx, [rdi+10h]
0x18001c39a  neg     rax
0x18001c39d  sbb     r8, r8
0x18001c3a0  and     r8, rcx
0x18001c3a3  lea     rdx, [rdi+98h]
0x18001c3aa  mov     [rsp+60h+var_40], 0
0x18001c3b2  xor     r9d, r9d
0x18001c3b5  lea     rcx, [rbp+var_28]
0x18001c3b9  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001c3be  mov     esi, eax
0x18001c3c0  test    r12, r12
0x18001c3c3  jz      short loc_18001C3CD
0x18001c3c5  mov     dword ptr [r12], 0
0x18001c3cd  mov     eax, esi
0x18001c3cf  mov     rbx, [rsp+60h+arg_0]
0x18001c3d7  add     rsp, 60h
0x18001c3db  pop     r15
0x18001c3dd  pop     r14
0x18001c3df  pop     r13
0x18001c3e1  pop     r12
0x18001c3e3  pop     rdi
0x18001c3e4  pop     rsi
0x18001c3e5  pop     rbp
0x18001c3e6  retn
```
