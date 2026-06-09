# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18005d2c0`
- end: `0x18005d4bf`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18005a3bc`
- `0x18005b224`
- `0x18005b4b4`
- `0x18005ce30`
- `0x18005d2c0`
- `0x18005da54`
- `0x18005eaa0`
- `0x18005f030`
- `0x18005f4c8`
- `0x18005f914`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d419`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d49f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d49f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  HSTRING v6; // rsi
  HRESULT v8; // ebx
  char v9; // si
  void *v10; // rdi
  void *v11; // r14
  char v12; // r12
  RTL_SRWLOCK *v13; // rcx
  HSTRING newString; // [rsp+30h] [rbp-20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+38h] [rbp-18h] BYREF
  __int128 v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+58h] BYREF

  v6 = a2;
  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  newString = 0;
  v8 = WindowsDuplicateString(v6, &newString);
  if ( v8 < 0 )
    goto LABEL_26;
  v9 = 0;
  *(_QWORD *)&v17 = 0;
  BYTE8(v17) = 0;
  v8 = XWinRT::detail::GitStorageType<IInspectable>::Initialize(&v17, a3);
  LODWORD(v19) = v8;
  if ( v8 >= 0 )
  {
    v11 = 0;
    v12 = 0;
    XWinRT::SerializingLockPolicy::Write(&v16, a1 + 160, &v19);
    v8 = v19;
    if ( (int)v19 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v19, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
      v19 = 0;
      v8 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
             a1 + 72,
             &newString,
             &v19);
      if ( v8 >= 0 )
      {
        if ( v19 )
        {
          v11 = *(void **)(v19 + 8);
          v12 = *(_BYTE *)(v19 + 16);
          *(_OWORD *)(v19 + 8) = v17;
          v10 = 0;
          *a4 = 1;
          goto LABEL_11;
        }
        if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
        {
          v8 = -2147024882;
        }
        else
        {
          v19 = 0;
          v8 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::SetAt(
                 a1 + 72,
                 &newString,
                 &v17,
                 &v19);
          if ( v8 >= 0 )
          {
            newString = 0;
            v10 = 0;
LABEL_11:
            if ( v16 )
            {
              v13 = v16 + 1;
              if ( LODWORD(v16->Ptr) == 1 )
                LODWORD(v13->Ptr) += 0x10000000;
              else
                ReleaseSRWLockExclusive(v13);
            }
            goto LABEL_17;
          }
        }
      }
    }
    v10 = (void *)v17;
    v9 = BYTE8(v17);
    goto LABEL_11;
  }
  v10 = 0;
  v11 = 0;
  v12 = 0;
LABEL_17:
  if ( v12 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v11);
  }
  else if ( v11 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v9 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v10);
  }
  else if ( v10 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v6 = a2;
LABEL_26:
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v19,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           *a4 != 0 ? 3 : 1,
           v6);
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005d2c0  mov     [rsp-38h+arg_0], rbx
0x18005d2c5  mov     [rsp-38h+arg_8], rdx
0x18005d2ca  push    rbp
0x18005d2cb  push    rsi
0x18005d2cc  push    rdi
0x18005d2cd  push    r12
0x18005d2cf  push    r13
0x18005d2d1  push    r14
0x18005d2d3  push    r15
0x18005d2d5  mov     rbp, rsp
0x18005d2d8  sub     rsp, 50h
0x18005d2dc  mov     r13, r9
0x18005d2df  mov     rdi, r8
0x18005d2e2  mov     rsi, rdx
0x18005d2e5  mov     r15, rcx
0x18005d2e8  mov     byte ptr [r9], 0
0x18005d2ec  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18005d2f1  mov     [rbp+newString], 0
0x18005d2f9  lea     rdx, [rbp+newString]; newString
0x18005d2fd  mov     rcx, rsi; string
0x18005d300  call    cs:__imp_WindowsDuplicateString
0x18005d306  mov     ebx, eax
0x18005d308  test    eax, eax
0x18005d30a  js      loc_18005D46C
0x18005d310  xor     esi, esi
0x18005d312  mov     qword ptr [rbp+var_10], rsi
0x18005d316  mov     byte ptr [rbp+var_10+8], sil
0x18005d31a  mov     rdx, rdi
0x18005d31d  lea     rcx, [rbp+var_10]
0x18005d321  call    ?Initialize@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAJPEAUIInspectable@@@Z; XWinRT::detail::GitStorageType<IInspectable>::Initialize(IInspectable *)
0x18005d326  mov     ebx, eax
0x18005d328  mov     dword ptr [rbp+arg_18], eax
0x18005d32b  test    eax, eax
0x18005d32d  jns     short loc_18005D33C
0x18005d32f  mov     edi, esi
0x18005d331  xor     r14d, r14d
0x18005d334  xor     r12b, r12b
0x18005d337  jmp     loc_18005D420
0x18005d33c  mov     r14, rsi
0x18005d33f  mov     r12b, sil
0x18005d342  lea     rdx, [r15+0A0h]
0x18005d349  lea     r8, [rbp+arg_18]
0x18005d34d  lea     rcx, [rbp+var_18]
0x18005d351  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18005d356  mov     ebx, dword ptr [rbp+arg_18]
0x18005d359  test    ebx, ebx
0x18005d35b  js      short loc_18005D3CF
0x18005d35d  lea     r8, [r15+0BCh]
0x18005d364  movzx   edx, byte ptr [r15+0BAh]
0x18005d36c  lea     rcx, [rbp+arg_18]
0x18005d370  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18005d375  lea     rcx, [r15+0B0h]; this
0x18005d37c  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18005d381  mov     [rbp+arg_18], rsi
0x18005d385  lea     r8, [rbp+arg_18]
0x18005d389  lea     rdx, [rbp+newString]
0x18005d38d  lea     rcx, [r15+48h]
0x18005d391  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18005d396  mov     ebx, eax
0x18005d398  test    eax, eax
0x18005d39a  js      short loc_18005D3CF
0x18005d39c  mov     rax, [rbp+arg_18]
0x18005d3a0  test    rax, rax
0x18005d3a3  jz      short loc_18005D3C0
0x18005d3a5  mov     r14, [rax+8]
0x18005d3a9  mov     r12b, [rax+10h]
0x18005d3ad  movups  xmm0, [rbp+var_10]
0x18005d3b1  movdqu  xmmword ptr [rax+8], xmm0
0x18005d3b6  mov     rdi, rsi
0x18005d3b9  mov     byte ptr [r13+0], 1
0x18005d3be  jmp     short loc_18005D3D7
0x18005d3c0  cmp     qword ptr [r15+58h], 7FFFFFFFh
0x18005d3c8  jnz     short loc_18005D3F1
0x18005d3ca  mov     ebx, 8007000Eh
0x18005d3cf  mov     rdi, qword ptr [rbp+var_10]
0x18005d3d3  mov     sil, byte ptr [rbp+var_10+8]
0x18005d3d7  mov     rax, [rbp+var_18]
0x18005d3db  test    rax, rax
0x18005d3de  jz      short loc_18005D420
0x18005d3e0  lea     rcx, [rax+8]; SRWLock
0x18005d3e4  cmp     dword ptr [rax], 1
0x18005d3e7  jnz     short loc_18005D419
0x18005d3e9  add     dword ptr [rcx], 10000000h
0x18005d3ef  jmp     short loc_18005D420
0x18005d3f1  mov     [rbp+arg_18], rsi
0x18005d3f5  lea     r9, [rbp+arg_18]
0x18005d3f9  lea     r8, [rbp+var_10]
0x18005d3fd  lea     rdx, [rbp+newString]
0x18005d401  lea     rcx, [r15+48h]
0x18005d405  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIInspectable@@@detail@2@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::SetAt(HSTRING__ * const &,XWinRT::detail::GitStorageType<IInspectable> const &,XWinRT::TXPOSITION * *)
0x18005d40a  mov     ebx, eax
0x18005d40c  test    eax, eax
0x18005d40e  js      short loc_18005D3CF
0x18005d410  mov     [rbp+newString], rsi
0x18005d414  mov     rdi, rsi
0x18005d417  jmp     short loc_18005D3D7
0x18005d419  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d41f  nop
0x18005d420  test    r12b, r12b
0x18005d423  jz      short loc_18005D42F
0x18005d425  mov     rcx, r14; void *
0x18005d428  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18005d42d  jmp     short loc_18005D444
0x18005d42f  test    r14, r14
0x18005d432  jz      short loc_18005D444
0x18005d434  mov     rax, [r14]
0x18005d437  mov     rcx, r14
0x18005d43a  mov     rax, [rax+10h]
0x18005d43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d443  nop
0x18005d444  test    sil, sil
0x18005d447  jz      short loc_18005D453
0x18005d449  mov     rcx, rdi; void *
0x18005d44c  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18005d451  jmp     short loc_18005D468
0x18005d453  test    rdi, rdi
0x18005d456  jz      short loc_18005D468
0x18005d458  mov     rax, [rdi]
0x18005d45b  mov     rcx, rdi
0x18005d45e  mov     rax, [rax+10h]
0x18005d462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d467  nop
0x18005d468  mov     rsi, [rbp+arg_8]
0x18005d46c  test    ebx, ebx
0x18005d46e  js      short loc_18005D49B
0x18005d470  mov     al, [r13+0]
0x18005d474  neg     al
0x18005d476  sbb     r9d, r9d
0x18005d479  and     r9d, 2
0x18005d47d  inc     r9d
0x18005d480  mov     [rsp+50h+var_30], rsi
0x18005d485  mov     r8, r15
0x18005d488  movzx   edx, byte ptr [r15+0B9h]
0x18005d490  movzx   ecx, byte ptr [rbp+arg_18]
0x18005d494  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18005d499  mov     ebx, eax
0x18005d49b  mov     rcx, [rbp+newString]; string
0x18005d49f  call    cs:__imp_WindowsDeleteString
0x18005d4a5  mov     eax, ebx
0x18005d4a7  mov     rbx, [rsp+50h+arg_0]
0x18005d4af  add     rsp, 50h
0x18005d4b3  pop     r15
0x18005d4b5  pop     r14
0x18005d4b7  pop     r13
0x18005d4b9  pop     r12
0x18005d4bb  pop     rdi
0x18005d4bc  pop     rsi
0x18005d4bd  pop     rbp
0x18005d4be  retn
```
