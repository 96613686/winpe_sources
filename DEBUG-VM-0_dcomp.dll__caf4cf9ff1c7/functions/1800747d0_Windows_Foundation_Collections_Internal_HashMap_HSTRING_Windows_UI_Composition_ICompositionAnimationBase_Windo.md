# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,uchar *)

- ea: `0x1800747d0`
- end: `0x180074a02`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@5@PEAE@Z`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800746a0`

## callees

- `0x180073d90`
- `0x1800747d0`
- `0x180074fa4`
- `0x180074fd4`
- `0x180075074`
- `0x180075090`
- `0x1800750e4`
- `0x1800751d0`
- `0x18013d240`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007485e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007485e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800748de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800748de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074958`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  char v4; // r15
  _BYTE *v5; // r14
  HSTRING v7; // r12
  HRESULT v9; // ebx
  _DWORD *v10; // r14
  void *v11; // r12
  char v12; // r13
  void *v13; // rdi
  _BYTE v15[8]; // [rsp+30h] [rbp-30h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  __int128 v18; // [rsp+48h] [rbp-18h] BYREF

  v4 = 0;
  v5 = a4;
  *a4 = 0;
  v7 = a2;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  newString = 0;
  v9 = WindowsDuplicateString(v7, &newString);
  if ( v9 < 0 )
    goto LABEL_19;
  *(_QWORD *)&v18 = 0;
  BYTE8(v18) = 0;
  v9 = XWinRT::InterfaceLifetimeTraits::Construct<Windows::UI::Composition::ICompositionAnimationBase>(&v18, a3);
  if ( v9 >= 0 )
  {
    v10 = (_DWORD *)(a1 + 168);
    v11 = 0;
    v12 = 0;
    if ( *(_DWORD *)(a1 + 160) == 1 )
    {
      if ( !*v10 )
        *v10 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(v15, *(unsigned __int8 *)(a1 + 186), a1 + 188);
    XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
    v17 = 0;
    v9 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::Lookup(
           a1 + 72,
           &newString,
           &v17);
    if ( v9 >= 0 )
    {
      if ( v17 )
      {
        v11 = *(void **)(v17 + 8);
        v13 = 0;
        v12 = *(_BYTE *)(v17 + 16);
        *(_OWORD *)(v17 + 8) = v18;
        *a4 = 1;
LABEL_8:
        if ( *(_DWORD *)(a1 + 160) == 1 )
          *v10 += 0x10000000;
        else
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
        if ( v12 )
        {
          XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(v11);
        }
        else if ( v11 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
        }
        v5 = a4;
        v7 = a2;
        goto LABEL_14;
      }
      if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
      {
        v9 = -2147024882;
      }
      else
      {
        v17 = 0;
        v9 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::SetAt(
               a1 + 72,
               &newString,
               &v18,
               &v17);
        if ( v9 >= 0 )
        {
          newString = 0;
          v13 = 0;
          goto LABEL_8;
        }
      }
    }
    v4 = BYTE8(v18);
    v13 = (void *)v18;
    goto LABEL_8;
  }
  v13 = 0;
LABEL_14:
  if ( v4 )
  {
    XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(v13);
  }
  else if ( v13 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v9 >= 0 )
    v9 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)a4,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           *v5 != 0 ? 3 : 1,
           v7);
LABEL_19:
  WindowsDeleteString(newString);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800747d0  mov     [rsp-38h+arg_0], rbx
0x1800747d5  mov     [rsp-38h+arg_18], r9
0x1800747da  mov     [rsp-38h+arg_8], rdx
0x1800747df  push    rbp
0x1800747e0  push    rsi
0x1800747e1  push    rdi
0x1800747e2  push    r12
0x1800747e4  push    r13
0x1800747e6  push    r14
0x1800747e8  push    r15
0x1800747ea  mov     rbp, rsp
0x1800747ed  sub     rsp, 60h
0x1800747f1  xor     r15d, r15d
0x1800747f4  mov     r14, r9
0x1800747f7  mov     [r9], r15b
0x1800747fa  mov     rdi, r8
0x1800747fd  mov     r12, rdx
0x180074800  mov     rsi, rcx
0x180074803  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x180074808  lea     rdx, [rbp+newString]; newString
0x18007480c  mov     [rbp+newString], r15
0x180074810  mov     rcx, r12; string
0x180074813  call    cs:__imp_WindowsDuplicateString
0x180074819  mov     ebx, eax
0x18007481b  test    eax, eax
0x18007481d  js      loc_180074954
0x180074823  mov     rdx, rdi
0x180074826  mov     qword ptr [rbp+var_18], r15
0x18007482a  lea     rcx, [rbp+var_18]
0x18007482e  mov     byte ptr [rbp+var_18+8], r15b
0x180074832  call    ??$Construct@UICompositionAnimationBase@Composition@UI@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAJPEAV?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@1@PEAUICompositionAnimationBase@Composition@UI@Windows@@@Z; XWinRT::InterfaceLifetimeTraits::Construct<Windows::UI::Composition::ICompositionAnimationBase>(XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase> *,Windows::UI::Composition::ICompositionAnimationBase *)
0x180074837  mov     ebx, eax
0x180074839  test    eax, eax
0x18007483b  js      loc_1800749CE
0x180074841  cmp     dword ptr [rsi+0A0h], 1
0x180074848  lea     r14, [rsi+0A8h]
0x18007484f  mov     r12d, r15d
0x180074852  mov     r13b, r15b
0x180074855  jz      loc_1800749AD
0x18007485b  mov     rcx, r14; SRWLock
0x18007485e  call    cs:__imp_AcquireSRWLockExclusive
0x180074864  movzx   edx, byte ptr [rsi+0BAh]
0x18007486b  lea     r8, [rsi+0BCh]
0x180074872  lea     rcx, [rbp+var_30]
0x180074876  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18007487b  lea     rcx, [rsi+0B0h]; this
0x180074882  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180074887  lea     r8, [rbp+var_20]
0x18007488b  mov     [rbp+var_20], r15
0x18007488f  lea     rdx, [rbp+newString]
0x180074893  lea     rcx, [rsi+48h]
0x180074897  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::CPair * *)
0x18007489c  mov     ebx, eax
0x18007489e  test    eax, eax
0x1800748a0  js      loc_1800749DB
0x1800748a6  mov     rax, [rbp+var_20]
0x1800748aa  test    rax, rax
0x1800748ad  jz      loc_180074978
0x1800748b3  mov     r12, [rax+8]
0x1800748b7  mov     rdi, r15
0x1800748ba  mov     r13b, [rax+10h]
0x1800748be  movups  xmm0, [rbp+var_18]
0x1800748c2  movdqu  xmmword ptr [rax+8], xmm0
0x1800748c7  mov     rax, [rbp+arg_18]
0x1800748cb  mov     byte ptr [rax], 1
0x1800748ce  cmp     dword ptr [rsi+0A0h], 1
0x1800748d5  jz      loc_1800749C2
0x1800748db  mov     rcx, r14; SRWLock
0x1800748de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800748e4  test    r13b, r13b
0x1800748e7  jnz     loc_1800749E8
0x1800748ed  test    r12, r12
0x1800748f0  jz      short loc_180074902
0x1800748f2  mov     rax, [r12]
0x1800748f6  mov     rcx, r12
0x1800748f9  mov     rax, [rax+10h]
0x1800748fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074902  mov     r14, [rbp+arg_18]
0x180074906  mov     r12, [rbp+arg_8]
0x18007490a  test    r15b, r15b
0x18007490d  jnz     loc_1800749F5
0x180074913  test    rdi, rdi
0x180074916  jz      short loc_180074927
0x180074918  mov     rax, [rdi]
0x18007491b  mov     rcx, rdi
0x18007491e  mov     rax, [rax+10h]
0x180074922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074927  test    ebx, ebx
0x180074929  js      short loc_180074954
0x18007492b  mov     al, [r14]
0x18007492e  mov     r8, rsi
0x180074931  movzx   edx, byte ptr [rsi+0B9h]
0x180074938  neg     al
0x18007493a  movzx   ecx, byte ptr [rbp+arg_18]
0x18007493e  sbb     r9d, r9d
0x180074941  mov     [rsp+60h+var_40], r12
0x180074946  and     r9d, 2
0x18007494a  inc     r9d
0x18007494d  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180074952  mov     ebx, eax
0x180074954  mov     rcx, [rbp+newString]; string
0x180074958  call    cs:__imp_WindowsDeleteString
0x18007495e  mov     eax, ebx
0x180074960  mov     rbx, [rsp+60h+arg_0]
0x180074968  add     rsp, 60h
0x18007496c  pop     r15
0x18007496e  pop     r14
0x180074970  pop     r13
0x180074972  pop     r12
0x180074974  pop     rdi
0x180074975  pop     rsi
0x180074976  pop     rbp
0x180074977  retn
0x180074978  cmp     qword ptr [rsi+58h], 7FFFFFFFh
0x180074980  jz      short loc_1800749D6
0x180074982  lea     r9, [rbp+var_20]
0x180074986  mov     [rbp+var_20], r15
0x18007498a  lea     r8, [rbp+var_18]
0x18007498e  lea     rdx, [rbp+newString]
0x180074992  lea     rcx, [rsi+48h]
0x180074996  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@2@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>>>::SetAt(HSTRING__ * const &,XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase> const &,XWinRT::TXPOSITION * *)
0x18007499b  mov     ebx, eax
0x18007499d  test    eax, eax
0x18007499f  js      short loc_1800749DB
0x1800749a1  mov     [rbp+newString], r15
0x1800749a5  mov     rdi, r15
0x1800749a8  jmp     loc_1800748CE
0x1800749ad  cmp     [r14], r15d
0x1800749b0  jnz     loc_180074864
0x1800749b6  mov     dword ptr [r14], 0F0000000h
0x1800749bd  jmp     loc_180074864
0x1800749c2  add     dword ptr [r14], 10000000h
0x1800749c9  jmp     loc_1800748E4
0x1800749ce  mov     rdi, r15
0x1800749d1  jmp     loc_18007490A
0x1800749d6  mov     ebx, 8007000Eh
0x1800749db  mov     r15b, byte ptr [rbp+var_18+8]
0x1800749df  mov     rdi, qword ptr [rbp+var_18]
0x1800749e3  jmp     loc_1800748CE
0x1800749e8  mov     rcx, r12; void *
0x1800749eb  call    ?Release@ReferencedGitCookie@?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(void)
0x1800749f0  jmp     loc_180074902
0x1800749f5  mov     rcx, rdi; void *
0x1800749f8  call    ?Release@ReferencedGitCookie@?$GitStorageType@UICompositionAnimationBase@Composition@UI@Windows@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<Windows::UI::Composition::ICompositionAnimationBase>::ReferencedGitCookie::Release(void)
0x1800749fd  jmp     loc_180074927
```
