# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x18003d3d0`
- end: `0x18003d58c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18002449c`

## callees

- `0x18000ca48`
- `0x18000ca64`
- `0x18000dde0`
- `0x1800167b0`
- `0x1800167e0`
- `0x180017440`
- `0x180018480`
- `0x18003d210`
- `0x18003d3d0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d471`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d471`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d518`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d546`

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
0x18003d3d0  mov     [rsp-38h+arg_0], rbx
0x18003d3d5  mov     [rsp-38h+arg_8], rdx
0x18003d3da  push    rbp
0x18003d3db  push    rsi
0x18003d3dc  push    rdi
0x18003d3dd  push    r12
0x18003d3df  push    r13
0x18003d3e1  push    r14
0x18003d3e3  push    r15
0x18003d3e5  mov     rbp, rsp
0x18003d3e8  sub     rsp, 30h
0x18003d3ec  mov     r14, rcx
0x18003d3ef  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18003d3f4  mov     edi, eax
0x18003d3f6  test    eax, eax
0x18003d3f8  js      loc_18003D54C
0x18003d3fe  xor     ebx, ebx
0x18003d400  xor     r15d, r15d
0x18003d403  xor     r12b, r12b
0x18003d406  mov     dword ptr [rbp+arg_10], ebx
0x18003d409  lea     rdx, [r14+0A0h]
0x18003d410  lea     r8, [rbp+arg_10]
0x18003d414  lea     rcx, [rbp+arg_18]
0x18003d418  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18003d41d  mov     edi, dword ptr [rbp+arg_10]
0x18003d420  test    edi, edi
0x18003d422  js      loc_18003D4FE
0x18003d428  lea     r8, [r14+0BCh]
0x18003d42f  movzx   edx, byte ptr [r14+0BAh]
0x18003d437  lea     rcx, [rbp+arg_10]
0x18003d43b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18003d440  mov     [rbp+arg_10], rbx
0x18003d444  lea     r8, [rbp+arg_10]
0x18003d448  lea     rdx, [rbp+arg_8]
0x18003d44c  lea     rcx, [r14+48h]
0x18003d450  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18003d455  mov     edi, eax
0x18003d457  test    eax, eax
0x18003d459  js      loc_18003D4FE
0x18003d45f  mov     rsi, [rbp+arg_10]
0x18003d463  test    rsi, rsi
0x18003d466  jnz     short loc_18003D47C
0x18003d468  xor     edx, edx
0x18003d46a  mov     edi, 8000000Bh
0x18003d46f  mov     ecx, edi
0x18003d471  call    cs:__imp_RoOriginateError
0x18003d477  jmp     loc_18003D4FE
0x18003d47c  lea     rcx, [r14+0B0h]; this
0x18003d483  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18003d488  mov     edi, eax
0x18003d48a  test    eax, eax
0x18003d48c  js      short loc_18003D4FE
0x18003d48e  mov     rbx, [rsi]
0x18003d491  xor     ecx, ecx; string
0x18003d493  call    cs:__imp_WindowsDeleteString
0x18003d499  nop
0x18003d49a  test    rsi, rsi
0x18003d49d  jz      short loc_18003D4F1
0x18003d49f  mov     r15, [rsi+8]
0x18003d4a3  mov     r12b, [rsi+10h]
0x18003d4a7  xor     edx, edx
0x18003d4a9  mov     eax, [rsi+20h]
0x18003d4ac  div     dword ptr [r14+60h]
0x18003d4b0  mov     r8d, edx
0x18003d4b3  mov     rdx, [r14+50h]
0x18003d4b7  mov     rax, [rdx+r8*8]
0x18003d4bb  cmp     rsi, rax
0x18003d4be  jnz     short loc_18003D4C8
0x18003d4c0  xor     eax, eax
0x18003d4c2  jmp     short loc_18003D4CE
0x18003d4c4  mov     rax, [rax+18h]
0x18003d4c8  cmp     [rax+18h], rsi
0x18003d4cc  jnz     short loc_18003D4C4
0x18003d4ce  mov     rcx, [rsi+18h]
0x18003d4d2  test    rax, rax
0x18003d4d5  jnz     short loc_18003D4DD
0x18003d4d7  mov     [rdx+r8*8], rcx
0x18003d4db  jmp     short loc_18003D4E1
0x18003d4dd  mov     [rax+18h], rcx
0x18003d4e1  mov     rdx, rsi
0x18003d4e4  lea     rcx, [r14+48h]
0x18003d4e8  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CNode *)
0x18003d4ed  xor     edi, edi
0x18003d4ef  jmp     short loc_18003D4FE
0x18003d4f1  mov     edi, 8000FFFFh
0x18003d4f6  xor     ebx, ebx
0x18003d4f8  xor     r15d, r15d
0x18003d4fb  xor     r12b, r12b
0x18003d4fe  mov     rax, [rbp+arg_18]
0x18003d502  test    rax, rax
0x18003d505  jz      short loc_18003D51F
0x18003d507  lea     rcx, [rax+8]; SRWLock
0x18003d50b  cmp     dword ptr [rax], 1
0x18003d50e  jnz     short loc_18003D518
0x18003d510  add     dword ptr [rcx], 10000000h
0x18003d516  jmp     short loc_18003D51F
0x18003d518  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d51e  nop
0x18003d51f  test    r12b, r12b
0x18003d522  jz      short loc_18003D52E
0x18003d524  mov     rcx, r15; void *
0x18003d527  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18003d52c  jmp     short loc_18003D543
0x18003d52e  test    r15, r15
0x18003d531  jz      short loc_18003D543
0x18003d533  mov     rax, [r15]
0x18003d536  mov     rcx, r15
0x18003d539  mov     rax, [rax+10h]
0x18003d53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d542  nop
0x18003d543  mov     rcx, rbx; string
0x18003d546  call    cs:__imp_WindowsDeleteString
0x18003d54c  test    edi, edi
0x18003d54e  js      short loc_18003D575
0x18003d550  mov     rax, [rbp+arg_8]
0x18003d554  mov     [rsp+30h+var_10], rax
0x18003d559  mov     r9d, 2
0x18003d55f  mov     r8, r14
0x18003d562  movzx   edx, byte ptr [r14+0B9h]
0x18003d56a  movzx   ecx, byte ptr [rbp+arg_10]
0x18003d56e  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18003d573  mov     edi, eax
0x18003d575  mov     eax, edi
0x18003d577  mov     rbx, [rsp+30h+arg_0]
0x18003d57c  add     rsp, 30h
0x18003d580  pop     r15
0x18003d582  pop     r14
0x18003d584  pop     r13
0x18003d586  pop     r12
0x18003d588  pop     rdi
0x18003d589  pop     rsi
0x18003d58a  pop     rbp
0x18003d58b  retn
```
