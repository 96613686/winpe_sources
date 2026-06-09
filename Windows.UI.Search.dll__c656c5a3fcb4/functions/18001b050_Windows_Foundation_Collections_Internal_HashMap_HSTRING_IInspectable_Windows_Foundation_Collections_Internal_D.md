# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18001b050`
- end: `0x18001b24f`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001b260`

## callees

- `0x180018268`
- `0x1800195d4`
- `0x180019964`
- `0x18001abc0`
- `0x18001b050`
- `0x18001b6b8`
- `0x18001c248`
- `0x18001c7d0`
- `0x18001cd6c`
- `0x18001d104`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b22f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b22f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b090`

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
  __int64 v10; // rdi
  __int64 v11; // r14
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
          v11 = *(_QWORD *)(v19 + 8);
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
    v10 = v17;
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v9 )
  {
    XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v10);
  }
  else if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
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
0x18001b050  mov     [rsp-38h+arg_0], rbx
0x18001b055  mov     [rsp-38h+arg_8], rdx
0x18001b05a  push    rbp
0x18001b05b  push    rsi
0x18001b05c  push    rdi
0x18001b05d  push    r12
0x18001b05f  push    r13
0x18001b061  push    r14
0x18001b063  push    r15
0x18001b065  mov     rbp, rsp
0x18001b068  sub     rsp, 50h
0x18001b06c  mov     r13, r9
0x18001b06f  mov     rdi, r8
0x18001b072  mov     rsi, rdx
0x18001b075  mov     r15, rcx
0x18001b078  mov     byte ptr [r9], 0
0x18001b07c  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18001b081  mov     [rbp+newString], 0
0x18001b089  lea     rdx, [rbp+newString]; newString
0x18001b08d  mov     rcx, rsi; string
0x18001b090  call    cs:__imp_WindowsDuplicateString
0x18001b096  mov     ebx, eax
0x18001b098  test    eax, eax
0x18001b09a  js      loc_18001B1FC
0x18001b0a0  xor     esi, esi
0x18001b0a2  mov     qword ptr [rbp+var_10], rsi
0x18001b0a6  mov     byte ptr [rbp+var_10+8], sil
0x18001b0aa  mov     rdx, rdi
0x18001b0ad  lea     rcx, [rbp+var_10]
0x18001b0b1  call    ?Initialize@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAJPEAUIInspectable@@@Z; XWinRT::detail::GitStorageType<IInspectable>::Initialize(IInspectable *)
0x18001b0b6  mov     ebx, eax
0x18001b0b8  mov     dword ptr [rbp+arg_18], eax
0x18001b0bb  test    eax, eax
0x18001b0bd  jns     short loc_18001B0CC
0x18001b0bf  mov     edi, esi
0x18001b0c1  xor     r14d, r14d
0x18001b0c4  xor     r12b, r12b
0x18001b0c7  jmp     loc_18001B1B0
0x18001b0cc  mov     r14, rsi
0x18001b0cf  mov     r12b, sil
0x18001b0d2  lea     rdx, [r15+0A0h]
0x18001b0d9  lea     r8, [rbp+arg_18]
0x18001b0dd  lea     rcx, [rbp+var_18]
0x18001b0e1  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001b0e6  mov     ebx, dword ptr [rbp+arg_18]
0x18001b0e9  test    ebx, ebx
0x18001b0eb  js      short loc_18001B15F
0x18001b0ed  lea     r8, [r15+0BCh]
0x18001b0f4  movzx   edx, byte ptr [r15+0BAh]
0x18001b0fc  lea     rcx, [rbp+arg_18]
0x18001b100  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001b105  lea     rcx, [r15+0B0h]; this
0x18001b10c  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18001b111  mov     [rbp+arg_18], rsi
0x18001b115  lea     r8, [rbp+arg_18]
0x18001b119  lea     rdx, [rbp+newString]
0x18001b11d  lea     rcx, [r15+48h]
0x18001b121  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18001b126  mov     ebx, eax
0x18001b128  test    eax, eax
0x18001b12a  js      short loc_18001B15F
0x18001b12c  mov     rax, [rbp+arg_18]
0x18001b130  test    rax, rax
0x18001b133  jz      short loc_18001B150
0x18001b135  mov     r14, [rax+8]
0x18001b139  mov     r12b, [rax+10h]
0x18001b13d  movups  xmm0, [rbp+var_10]
0x18001b141  movdqu  xmmword ptr [rax+8], xmm0
0x18001b146  mov     rdi, rsi
0x18001b149  mov     byte ptr [r13+0], 1
0x18001b14e  jmp     short loc_18001B167
0x18001b150  cmp     qword ptr [r15+58h], 7FFFFFFFh
0x18001b158  jnz     short loc_18001B181
0x18001b15a  mov     ebx, 8007000Eh
0x18001b15f  mov     rdi, qword ptr [rbp+var_10]
0x18001b163  mov     sil, byte ptr [rbp+var_10+8]
0x18001b167  mov     rax, [rbp+var_18]
0x18001b16b  test    rax, rax
0x18001b16e  jz      short loc_18001B1B0
0x18001b170  lea     rcx, [rax+8]; SRWLock
0x18001b174  cmp     dword ptr [rax], 1
0x18001b177  jnz     short loc_18001B1A9
0x18001b179  add     dword ptr [rcx], 10000000h
0x18001b17f  jmp     short loc_18001B1B0
0x18001b181  mov     [rbp+arg_18], rsi
0x18001b185  lea     r9, [rbp+arg_18]
0x18001b189  lea     r8, [rbp+var_10]
0x18001b18d  lea     rdx, [rbp+newString]
0x18001b191  lea     rcx, [r15+48h]
0x18001b195  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIInspectable@@@detail@2@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::SetAt(HSTRING__ * const &,XWinRT::detail::GitStorageType<IInspectable> const &,XWinRT::TXPOSITION * *)
0x18001b19a  mov     ebx, eax
0x18001b19c  test    eax, eax
0x18001b19e  js      short loc_18001B15F
0x18001b1a0  mov     [rbp+newString], rsi
0x18001b1a4  mov     rdi, rsi
0x18001b1a7  jmp     short loc_18001B167
0x18001b1a9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b1af  nop
0x18001b1b0  test    r12b, r12b
0x18001b1b3  jz      short loc_18001B1BF
0x18001b1b5  mov     rcx, r14
0x18001b1b8  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18001b1bd  jmp     short loc_18001B1D4
0x18001b1bf  test    r14, r14
0x18001b1c2  jz      short loc_18001B1D4
0x18001b1c4  mov     rax, [r14]
0x18001b1c7  mov     rcx, r14
0x18001b1ca  mov     rax, [rax+10h]
0x18001b1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1d3  nop
0x18001b1d4  test    sil, sil
0x18001b1d7  jz      short loc_18001B1E3
0x18001b1d9  mov     rcx, rdi
0x18001b1dc  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18001b1e1  jmp     short loc_18001B1F8
0x18001b1e3  test    rdi, rdi
0x18001b1e6  jz      short loc_18001B1F8
0x18001b1e8  mov     rax, [rdi]
0x18001b1eb  mov     rcx, rdi
0x18001b1ee  mov     rax, [rax+10h]
0x18001b1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f7  nop
0x18001b1f8  mov     rsi, [rbp+arg_8]
0x18001b1fc  test    ebx, ebx
0x18001b1fe  js      short loc_18001B22B
0x18001b200  mov     al, [r13+0]
0x18001b204  neg     al
0x18001b206  sbb     r9d, r9d
0x18001b209  and     r9d, 2
0x18001b20d  inc     r9d
0x18001b210  mov     [rsp+50h+var_30], rsi
0x18001b215  mov     r8, r15
0x18001b218  movzx   edx, byte ptr [r15+0B9h]
0x18001b220  movzx   ecx, byte ptr [rbp+arg_18]
0x18001b224  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18001b229  mov     ebx, eax
0x18001b22b  mov     rcx, [rbp+newString]; string
0x18001b22f  call    cs:__imp_WindowsDeleteString
0x18001b235  mov     eax, ebx
0x18001b237  mov     rbx, [rsp+50h+arg_0]
0x18001b23f  add     rsp, 50h
0x18001b243  pop     r15
0x18001b245  pop     r14
0x18001b247  pop     r13
0x18001b249  pop     r12
0x18001b24b  pop     rdi
0x18001b24c  pop     rsi
0x18001b24d  pop     rbp
0x18001b24e  retn
```
