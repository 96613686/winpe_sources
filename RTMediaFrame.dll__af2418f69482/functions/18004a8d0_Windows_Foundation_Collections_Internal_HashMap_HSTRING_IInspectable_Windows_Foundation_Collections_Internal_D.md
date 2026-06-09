# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x18004a8d0`
- end: `0x18004aa6c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x18000ca48`
- `0x18000ca64`
- `0x18000dde0`
- `0x180018480`
- `0x18001cf8c`
- `0x1800457a4`
- `0x180046148`
- `0x180048ed8`
- `0x18004a8d0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004a96b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004a96b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aa18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aa18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aa2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aa2a`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rcx
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h] BYREF

  v14 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    v16 = 0;
    LODWORD(v15) = 0;
    XWinRT::SerializingLockPolicy::Write(&v13, a1 + 128, &v15);
    v3 = v15;
    if ( (int)v15 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v15 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
             a1 + 40,
             &v14,
             &v15);
      if ( v3 >= 0 )
      {
        v5 = v15;
        if ( v15 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v5;
            WindowsDeleteString(0);
            v6 = *(_QWORD *)(v5 + 8);
            XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v16);
            v16 = v6;
            if ( v5 )
            {
              v7 = (unsigned int)(*(_DWORD *)(v5 + 24) % *(_DWORD *)(a1 + 64));
              v8 = *(_QWORD *)(a1 + 48);
              v9 = *(_QWORD *)(v8 + 8 * v7);
              if ( v5 == v9 )
              {
                v9 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v9 + 16) != v5 )
                  v9 = *(_QWORD *)(v9 + 16);
              }
              v10 = *(_QWORD *)(v5 + 16);
              if ( v9 )
                *(_QWORD *)(v9 + 16) = v10;
              else
                *(_QWORD *)(v8 + 8 * v7) = v10;
              XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(
                a1 + 40,
                v5);
              v3 = 0;
            }
            else
            {
              v4 = 0;
              v3 = -2147418113;
              v16 = 0;
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
    if ( v13 )
    {
      v11 = v13 + 1;
      if ( LODWORD(v13->Ptr) == 1 )
        LODWORD(v11->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
    XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v16);
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v15,
                           *(unsigned __int8 *)(a1 + 153),
                           a1,
                           2,
                           v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004a8d0  mov     [rsp-28h+arg_0], rbx
0x18004a8d5  mov     [rsp-28h+arg_8], rdx
0x18004a8da  push    rbp
0x18004a8db  push    rsi
0x18004a8dc  push    rdi
0x18004a8dd  push    r14
0x18004a8df  push    r15
0x18004a8e1  mov     rbp, rsp
0x18004a8e4  sub     rsp, 40h
0x18004a8e8  mov     r14, rcx
0x18004a8eb  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x18004a8f0  mov     edi, eax
0x18004a8f2  test    eax, eax
0x18004a8f4  js      loc_18004AA30
0x18004a8fa  xor     ebx, ebx
0x18004a8fc  lea     rdx, [r14+80h]
0x18004a903  lea     r8, [rbp+arg_10]
0x18004a907  mov     [rbp+arg_18], rbx
0x18004a90b  lea     rcx, [rbp+var_10]
0x18004a90f  mov     dword ptr [rbp+arg_10], ebx
0x18004a912  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18004a917  mov     edi, dword ptr [rbp+arg_10]
0x18004a91a  test    edi, edi
0x18004a91c  js      loc_18004A9FE
0x18004a922  movzx   edx, byte ptr [r14+9Ah]
0x18004a92a  lea     r8, [r14+9Ch]
0x18004a931  lea     rcx, [rbp+arg_10]
0x18004a935  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18004a93a  lea     r8, [rbp+arg_10]
0x18004a93e  mov     [rbp+arg_10], rbx
0x18004a942  lea     rdx, [rbp+arg_8]
0x18004a946  lea     rcx, [r14+28h]
0x18004a94a  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x18004a94f  mov     edi, eax
0x18004a951  test    eax, eax
0x18004a953  js      loc_18004A9FE
0x18004a959  mov     rsi, [rbp+arg_10]
0x18004a95d  test    rsi, rsi
0x18004a960  jnz     short loc_18004A976
0x18004a962  mov     edi, 8000000Bh
0x18004a967  xor     edx, edx
0x18004a969  mov     ecx, edi
0x18004a96b  call    cs:__imp_RoOriginateError
0x18004a971  jmp     loc_18004A9FE
0x18004a976  lea     rcx, [r14+90h]; this
0x18004a97d  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18004a982  mov     edi, eax
0x18004a984  test    eax, eax
0x18004a986  js      short loc_18004A9FE
0x18004a988  mov     rbx, [rsi]
0x18004a98b  xor     ecx, ecx; string
0x18004a98d  call    cs:__imp_WindowsDeleteString
0x18004a993  mov     rdi, [rsi+8]
0x18004a997  lea     rcx, [rbp+arg_18]
0x18004a99b  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18004a9a0  mov     [rbp+arg_18], rdi
0x18004a9a4  test    rsi, rsi
0x18004a9a7  jz      short loc_18004A9F3
0x18004a9a9  mov     eax, [rsi+18h]
0x18004a9ac  xor     edx, edx
0x18004a9ae  div     dword ptr [r14+40h]
0x18004a9b2  mov     r8d, edx
0x18004a9b5  mov     rdx, [r14+30h]
0x18004a9b9  mov     rax, [rdx+r8*8]
0x18004a9bd  cmp     rsi, rax
0x18004a9c0  jnz     short loc_18004A9CA
0x18004a9c2  xor     eax, eax
0x18004a9c4  jmp     short loc_18004A9D0
0x18004a9c6  mov     rax, [rax+10h]
0x18004a9ca  cmp     [rax+10h], rsi
0x18004a9ce  jnz     short loc_18004A9C6
0x18004a9d0  mov     rcx, [rsi+10h]
0x18004a9d4  test    rax, rax
0x18004a9d7  jnz     short loc_18004A9DF
0x18004a9d9  mov     [rdx+r8*8], rcx
0x18004a9dd  jmp     short loc_18004A9E3
0x18004a9df  mov     [rax+10h], rcx
0x18004a9e3  mov     rdx, rsi
0x18004a9e6  lea     rcx, [r14+28h]
0x18004a9ea  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CNode *)
0x18004a9ef  xor     edi, edi
0x18004a9f1  jmp     short loc_18004A9FE
0x18004a9f3  xor     ebx, ebx
0x18004a9f5  mov     edi, 8000FFFFh
0x18004a9fa  mov     [rbp+arg_18], rbx
0x18004a9fe  mov     rax, [rbp+var_10]
0x18004aa02  test    rax, rax
0x18004aa05  jz      short loc_18004AA1E
0x18004aa07  cmp     dword ptr [rax], 1
0x18004aa0a  lea     rcx, [rax+8]; SRWLock
0x18004aa0e  jnz     short loc_18004AA18
0x18004aa10  add     dword ptr [rcx], 10000000h
0x18004aa16  jmp     short loc_18004AA1E
0x18004aa18  call    cs:__imp_ReleaseSRWLockExclusive
0x18004aa1e  lea     rcx, [rbp+arg_18]
0x18004aa22  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18004aa27  mov     rcx, rbx; string
0x18004aa2a  call    cs:__imp_WindowsDeleteString
0x18004aa30  test    edi, edi
0x18004aa32  js      short loc_18004AA59
0x18004aa34  mov     rax, [rbp+arg_8]
0x18004aa38  mov     r9d, 2
0x18004aa3e  movzx   edx, byte ptr [r14+99h]
0x18004aa46  mov     r8, r14
0x18004aa49  movzx   ecx, byte ptr [rbp+arg_10]
0x18004aa4d  mov     [rsp+40h+var_20], rax
0x18004aa52  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18004aa57  mov     edi, eax
0x18004aa59  mov     rbx, [rsp+40h+arg_0]
0x18004aa5e  mov     eax, edi
0x18004aa60  add     rsp, 40h
0x18004aa64  pop     r15
0x18004aa66  pop     r14
0x18004aa68  pop     rdi
0x18004aa69  pop     rsi
0x18004aa6a  pop     rbp
0x18004aa6b  retn
```
