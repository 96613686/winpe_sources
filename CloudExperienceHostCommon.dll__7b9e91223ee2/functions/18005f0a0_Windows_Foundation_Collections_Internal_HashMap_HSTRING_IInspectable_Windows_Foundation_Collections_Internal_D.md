# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x18005f0a0`
- end: `0x18005f25c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x18005a3bc`
- `0x18005b224`
- `0x18005b4b4`
- `0x18005bab4`
- `0x18005da54`
- `0x18005eaa0`
- `0x18005f030`
- `0x18005f0a0`
- `0x18005f914`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f1e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f1e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f216`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005f141`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005f141`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  void *v5; // r15
  char v6; // r12
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  RTL_SRWLOCK *v12; // rcx
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF
  __int64 v15; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v16; // [rsp+88h] [rbp+58h] BYREF

  v14 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    v5 = 0;
    v6 = 0;
    LODWORD(v15) = 0;
    XWinRT::SerializingLockPolicy::Write(&v16, a1 + 160, &v15);
    v3 = v15;
    if ( (int)v15 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      v15 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
             a1 + 72,
             &v14,
             &v15);
      if ( v3 >= 0 )
      {
        v7 = v15;
        if ( v15 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v7;
            WindowsDeleteString(0);
            if ( v7 )
            {
              v5 = *(void **)(v7 + 8);
              v6 = *(_BYTE *)(v7 + 16);
              v8 = (unsigned int)(*(_DWORD *)(v7 + 32) % *(_DWORD *)(a1 + 96));
              v9 = *(_QWORD *)(a1 + 80);
              v10 = *(_QWORD *)(v9 + 8 * v8);
              if ( v7 == v10 )
              {
                v10 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v10 + 24) != v7 )
                  v10 = *(_QWORD *)(v10 + 24);
              }
              v11 = *(_QWORD *)(v7 + 24);
              if ( v10 )
                *(_QWORD *)(v10 + 24) = v11;
              else
                *(_QWORD *)(v9 + 8 * v8) = v11;
              XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(
                a1 + 72,
                v7);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
              v5 = 0;
              v6 = 0;
            }
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL, 0);
        }
      }
    }
    if ( v16 )
    {
      v12 = v16 + 1;
      if ( LODWORD(v16->Ptr) == 1 )
        LODWORD(v12->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v12);
    }
    if ( v6 )
    {
      XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v5);
    }
    else if ( v5 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v15,
                           *(unsigned __int8 *)(a1 + 185),
                           a1,
                           2,
                           v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005f0a0  mov     [rsp-38h+arg_0], rbx
0x18005f0a5  mov     [rsp-38h+arg_8], rdx
0x18005f0aa  push    rbp
0x18005f0ab  push    rsi
0x18005f0ac  push    rdi
0x18005f0ad  push    r12
0x18005f0af  push    r13
0x18005f0b1  push    r14
0x18005f0b3  push    r15
0x18005f0b5  mov     rbp, rsp
0x18005f0b8  sub     rsp, 30h
0x18005f0bc  mov     r14, rcx
0x18005f0bf  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18005f0c4  mov     edi, eax
0x18005f0c6  test    eax, eax
0x18005f0c8  js      loc_18005F21C
0x18005f0ce  xor     ebx, ebx
0x18005f0d0  xor     r15d, r15d
0x18005f0d3  xor     r12b, r12b
0x18005f0d6  mov     dword ptr [rbp+arg_10], ebx
0x18005f0d9  lea     rdx, [r14+0A0h]
0x18005f0e0  lea     r8, [rbp+arg_10]
0x18005f0e4  lea     rcx, [rbp+arg_18]
0x18005f0e8  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18005f0ed  mov     edi, dword ptr [rbp+arg_10]
0x18005f0f0  test    edi, edi
0x18005f0f2  js      loc_18005F1CE
0x18005f0f8  lea     r8, [r14+0BCh]
0x18005f0ff  movzx   edx, byte ptr [r14+0BAh]
0x18005f107  lea     rcx, [rbp+arg_10]
0x18005f10b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18005f110  mov     [rbp+arg_10], rbx
0x18005f114  lea     r8, [rbp+arg_10]
0x18005f118  lea     rdx, [rbp+arg_8]
0x18005f11c  lea     rcx, [r14+48h]
0x18005f120  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18005f125  mov     edi, eax
0x18005f127  test    eax, eax
0x18005f129  js      loc_18005F1CE
0x18005f12f  mov     rsi, [rbp+arg_10]
0x18005f133  test    rsi, rsi
0x18005f136  jnz     short loc_18005F14C
0x18005f138  xor     edx, edx
0x18005f13a  mov     edi, 8000000Bh
0x18005f13f  mov     ecx, edi
0x18005f141  call    cs:__imp_RoOriginateError
0x18005f147  jmp     loc_18005F1CE
0x18005f14c  lea     rcx, [r14+0B0h]; this
0x18005f153  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18005f158  mov     edi, eax
0x18005f15a  test    eax, eax
0x18005f15c  js      short loc_18005F1CE
0x18005f15e  mov     rbx, [rsi]
0x18005f161  xor     ecx, ecx; string
0x18005f163  call    cs:__imp_WindowsDeleteString
0x18005f169  nop
0x18005f16a  test    rsi, rsi
0x18005f16d  jz      short loc_18005F1C1
0x18005f16f  mov     r15, [rsi+8]
0x18005f173  mov     r12b, [rsi+10h]
0x18005f177  xor     edx, edx
0x18005f179  mov     eax, [rsi+20h]
0x18005f17c  div     dword ptr [r14+60h]
0x18005f180  mov     r8d, edx
0x18005f183  mov     rdx, [r14+50h]
0x18005f187  mov     rax, [rdx+r8*8]
0x18005f18b  cmp     rsi, rax
0x18005f18e  jnz     short loc_18005F198
0x18005f190  xor     eax, eax
0x18005f192  jmp     short loc_18005F19E
0x18005f194  mov     rax, [rax+18h]
0x18005f198  cmp     [rax+18h], rsi
0x18005f19c  jnz     short loc_18005F194
0x18005f19e  mov     rcx, [rsi+18h]
0x18005f1a2  test    rax, rax
0x18005f1a5  jnz     short loc_18005F1AD
0x18005f1a7  mov     [rdx+r8*8], rcx
0x18005f1ab  jmp     short loc_18005F1B1
0x18005f1ad  mov     [rax+18h], rcx
0x18005f1b1  mov     rdx, rsi
0x18005f1b4  lea     rcx, [r14+48h]
0x18005f1b8  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CNode *)
0x18005f1bd  xor     edi, edi
0x18005f1bf  jmp     short loc_18005F1CE
0x18005f1c1  mov     edi, 8000FFFFh
0x18005f1c6  xor     ebx, ebx
0x18005f1c8  xor     r15d, r15d
0x18005f1cb  xor     r12b, r12b
0x18005f1ce  mov     rax, [rbp+arg_18]
0x18005f1d2  test    rax, rax
0x18005f1d5  jz      short loc_18005F1EF
0x18005f1d7  lea     rcx, [rax+8]; SRWLock
0x18005f1db  cmp     dword ptr [rax], 1
0x18005f1de  jnz     short loc_18005F1E8
0x18005f1e0  add     dword ptr [rcx], 10000000h
0x18005f1e6  jmp     short loc_18005F1EF
0x18005f1e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18005f1ee  nop
0x18005f1ef  test    r12b, r12b
0x18005f1f2  jz      short loc_18005F1FE
0x18005f1f4  mov     rcx, r15; void *
0x18005f1f7  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18005f1fc  jmp     short loc_18005F213
0x18005f1fe  test    r15, r15
0x18005f201  jz      short loc_18005F213
0x18005f203  mov     rax, [r15]
0x18005f206  mov     rcx, r15
0x18005f209  mov     rax, [rax+10h]
0x18005f20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f212  nop
0x18005f213  mov     rcx, rbx; string
0x18005f216  call    cs:__imp_WindowsDeleteString
0x18005f21c  test    edi, edi
0x18005f21e  js      short loc_18005F245
0x18005f220  mov     rax, [rbp+arg_8]
0x18005f224  mov     [rsp+30h+var_10], rax
0x18005f229  mov     r9d, 2
0x18005f22f  mov     r8, r14
0x18005f232  movzx   edx, byte ptr [r14+0B9h]
0x18005f23a  movzx   ecx, byte ptr [rbp+arg_10]
0x18005f23e  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18005f243  mov     edi, eax
0x18005f245  mov     eax, edi
0x18005f247  mov     rbx, [rsp+30h+arg_0]
0x18005f24c  add     rsp, 30h
0x18005f250  pop     r15
0x18005f252  pop     r14
0x18005f254  pop     r13
0x18005f256  pop     r12
0x18005f258  pop     rdi
0x18005f259  pop     rsi
0x18005f25a  pop     rbp
0x18005f25b  retn
```
