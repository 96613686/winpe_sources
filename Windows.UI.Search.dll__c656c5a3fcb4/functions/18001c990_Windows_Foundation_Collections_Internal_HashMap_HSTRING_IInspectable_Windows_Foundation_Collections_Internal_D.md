# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x18001c990`
- end: `0x18001cb4c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18001cb60`

## callees

- `0x180018268`
- `0x1800195d4`
- `0x180019964`
- `0x180019ee0`
- `0x18001b6b8`
- `0x18001c248`
- `0x18001c7d0`
- `0x18001c990`
- `0x18001d104`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cad8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ca53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ca53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb06`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001ca31`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001ca31`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  __int64 v5; // r15
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
              v5 = *(_QWORD *)(v7 + 8);
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
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
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
0x18001c990  mov     [rsp-38h+arg_0], rbx
0x18001c995  mov     [rsp-38h+arg_8], rdx
0x18001c99a  push    rbp
0x18001c99b  push    rsi
0x18001c99c  push    rdi
0x18001c99d  push    r12
0x18001c99f  push    r13
0x18001c9a1  push    r14
0x18001c9a3  push    r15
0x18001c9a5  mov     rbp, rsp
0x18001c9a8  sub     rsp, 30h
0x18001c9ac  mov     r14, rcx
0x18001c9af  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18001c9b4  mov     edi, eax
0x18001c9b6  test    eax, eax
0x18001c9b8  js      loc_18001CB0C
0x18001c9be  xor     ebx, ebx
0x18001c9c0  xor     r15d, r15d
0x18001c9c3  xor     r12b, r12b
0x18001c9c6  mov     dword ptr [rbp+arg_10], ebx
0x18001c9c9  lea     rdx, [r14+0A0h]
0x18001c9d0  lea     r8, [rbp+arg_10]
0x18001c9d4  lea     rcx, [rbp+arg_18]
0x18001c9d8  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001c9dd  mov     edi, dword ptr [rbp+arg_10]
0x18001c9e0  test    edi, edi
0x18001c9e2  js      loc_18001CABE
0x18001c9e8  lea     r8, [r14+0BCh]
0x18001c9ef  movzx   edx, byte ptr [r14+0BAh]
0x18001c9f7  lea     rcx, [rbp+arg_10]
0x18001c9fb  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001ca00  mov     [rbp+arg_10], rbx
0x18001ca04  lea     r8, [rbp+arg_10]
0x18001ca08  lea     rdx, [rbp+arg_8]
0x18001ca0c  lea     rcx, [r14+48h]
0x18001ca10  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18001ca15  mov     edi, eax
0x18001ca17  test    eax, eax
0x18001ca19  js      loc_18001CABE
0x18001ca1f  mov     rsi, [rbp+arg_10]
0x18001ca23  test    rsi, rsi
0x18001ca26  jnz     short loc_18001CA3C
0x18001ca28  xor     edx, edx
0x18001ca2a  mov     edi, 8000000Bh
0x18001ca2f  mov     ecx, edi
0x18001ca31  call    cs:__imp_RoOriginateError
0x18001ca37  jmp     loc_18001CABE
0x18001ca3c  lea     rcx, [r14+0B0h]; this
0x18001ca43  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18001ca48  mov     edi, eax
0x18001ca4a  test    eax, eax
0x18001ca4c  js      short loc_18001CABE
0x18001ca4e  mov     rbx, [rsi]
0x18001ca51  xor     ecx, ecx; string
0x18001ca53  call    cs:__imp_WindowsDeleteString
0x18001ca59  nop
0x18001ca5a  test    rsi, rsi
0x18001ca5d  jz      short loc_18001CAB1
0x18001ca5f  mov     r15, [rsi+8]
0x18001ca63  mov     r12b, [rsi+10h]
0x18001ca67  xor     edx, edx
0x18001ca69  mov     eax, [rsi+20h]
0x18001ca6c  div     dword ptr [r14+60h]
0x18001ca70  mov     r8d, edx
0x18001ca73  mov     rdx, [r14+50h]
0x18001ca77  mov     rax, [rdx+r8*8]
0x18001ca7b  cmp     rsi, rax
0x18001ca7e  jnz     short loc_18001CA88
0x18001ca80  xor     eax, eax
0x18001ca82  jmp     short loc_18001CA8E
0x18001ca84  mov     rax, [rax+18h]
0x18001ca88  cmp     [rax+18h], rsi
0x18001ca8c  jnz     short loc_18001CA84
0x18001ca8e  mov     rcx, [rsi+18h]
0x18001ca92  test    rax, rax
0x18001ca95  jnz     short loc_18001CA9D
0x18001ca97  mov     [rdx+r8*8], rcx
0x18001ca9b  jmp     short loc_18001CAA1
0x18001ca9d  mov     [rax+18h], rcx
0x18001caa1  mov     rdx, rsi
0x18001caa4  lea     rcx, [r14+48h]
0x18001caa8  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CNode *)
0x18001caad  xor     edi, edi
0x18001caaf  jmp     short loc_18001CABE
0x18001cab1  mov     edi, 8000FFFFh
0x18001cab6  xor     ebx, ebx
0x18001cab8  xor     r15d, r15d
0x18001cabb  xor     r12b, r12b
0x18001cabe  mov     rax, [rbp+arg_18]
0x18001cac2  test    rax, rax
0x18001cac5  jz      short loc_18001CADF
0x18001cac7  lea     rcx, [rax+8]; SRWLock
0x18001cacb  cmp     dword ptr [rax], 1
0x18001cace  jnz     short loc_18001CAD8
0x18001cad0  add     dword ptr [rcx], 10000000h
0x18001cad6  jmp     short loc_18001CADF
0x18001cad8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cade  nop
0x18001cadf  test    r12b, r12b
0x18001cae2  jz      short loc_18001CAEE
0x18001cae4  mov     rcx, r15
0x18001cae7  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18001caec  jmp     short loc_18001CB03
0x18001caee  test    r15, r15
0x18001caf1  jz      short loc_18001CB03
0x18001caf3  mov     rax, [r15]
0x18001caf6  mov     rcx, r15
0x18001caf9  mov     rax, [rax+10h]
0x18001cafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb02  nop
0x18001cb03  mov     rcx, rbx; string
0x18001cb06  call    cs:__imp_WindowsDeleteString
0x18001cb0c  test    edi, edi
0x18001cb0e  js      short loc_18001CB35
0x18001cb10  mov     rax, [rbp+arg_8]
0x18001cb14  mov     [rsp+30h+var_10], rax
0x18001cb19  mov     r9d, 2
0x18001cb1f  mov     r8, r14
0x18001cb22  movzx   edx, byte ptr [r14+0B9h]
0x18001cb2a  movzx   ecx, byte ptr [rbp+arg_10]
0x18001cb2e  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18001cb33  mov     edi, eax
0x18001cb35  mov     eax, edi
0x18001cb37  mov     rbx, [rsp+30h+arg_0]
0x18001cb3c  add     rsp, 30h
0x18001cb40  pop     r15
0x18001cb42  pop     r14
0x18001cb44  pop     r13
0x18001cb46  pop     r12
0x18001cb48  pop     rdi
0x18001cb49  pop     rsi
0x18001cb4a  pop     rbp
0x18001cb4b  retn
```
