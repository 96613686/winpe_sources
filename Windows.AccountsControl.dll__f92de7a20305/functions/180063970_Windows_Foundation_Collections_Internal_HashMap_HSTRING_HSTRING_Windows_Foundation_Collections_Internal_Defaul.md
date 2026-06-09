# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180063970`
- end: `0x180063b02`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18001c848`
- `0x18001d4a8`
- `0x18001d798`
- `0x18001e1a0`
- `0x18001f8f8`
- `0x180020560`
- `0x180021274`
- `0x180063970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063aaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063aaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ac2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180063a07`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180063a07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  HSTRING v4; // rbx
  HSTRING v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rcx
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF
  __int64 v14; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v15; // [rsp+88h] [rbp+58h] BYREF

  v13 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    v5 = 0;
    LODWORD(v14) = 0;
    XWinRT::SerializingLockPolicy::Write(&v15, a1 + 128, &v14);
    v3 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v14 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
             a1 + 40,
             &v13,
             &v14);
      if ( v3 >= 0 )
      {
        v6 = v14;
        if ( v14 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v6;
            WindowsDeleteString(0);
            v5 = *(HSTRING *)(v6 + 8);
            WindowsDeleteString(0);
            if ( v6 )
            {
              v7 = (unsigned int)(*(_DWORD *)(v6 + 24) % *(_DWORD *)(a1 + 64));
              v8 = *(_QWORD *)(a1 + 48);
              v9 = *(_QWORD *)(v8 + 8 * v7);
              if ( v6 == v9 )
              {
                v9 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v9 + 16) != v6 )
                  v9 = *(_QWORD *)(v9 + 16);
              }
              v10 = *(_QWORD *)(v6 + 16);
              if ( v9 )
                *(_QWORD *)(v9 + 16) = v10;
              else
                *(_QWORD *)(v8 + 8 * v7) = v10;
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
                a1 + 40,
                v6);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
              v5 = 0;
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
    if ( v15 )
    {
      v11 = v15 + 1;
      if ( LODWORD(v15->Ptr) == 1 )
        LODWORD(v11->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
    WindowsDeleteString(v5);
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v14,
                           *(unsigned __int8 *)(a1 + 153),
                           a1,
                           2,
                           v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180063970  mov     [rsp-38h+arg_8], rdx
0x180063975  push    rbp
0x180063976  push    rbx
0x180063977  push    rsi
0x180063978  push    rdi
0x180063979  push    r13
0x18006397b  push    r14
0x18006397d  push    r15
0x18006397f  mov     rbp, rsp
0x180063982  sub     rsp, 30h
0x180063986  mov     r15, rcx
0x180063989  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x18006398e  mov     esi, eax
0x180063990  test    eax, eax
0x180063992  js      loc_180063AC8
0x180063998  xor     ebx, ebx
0x18006399a  xor     edi, edi
0x18006399c  mov     dword ptr [rbp+arg_10], ebx
0x18006399f  lea     rdx, [r15+80h]
0x1800639a6  lea     r8, [rbp+arg_10]
0x1800639aa  lea     rcx, [rbp+arg_18]
0x1800639ae  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800639b3  mov     esi, dword ptr [rbp+arg_10]
0x1800639b6  test    esi, esi
0x1800639b8  js      loc_180063A95
0x1800639be  lea     r8, [r15+9Ch]
0x1800639c5  movzx   edx, byte ptr [r15+9Ah]
0x1800639cd  lea     rcx, [rbp+arg_10]
0x1800639d1  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800639d6  mov     [rbp+arg_10], rbx
0x1800639da  lea     r8, [rbp+arg_10]
0x1800639de  lea     rdx, [rbp+arg_8]
0x1800639e2  lea     rcx, [r15+28h]
0x1800639e6  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x1800639eb  mov     esi, eax
0x1800639ed  test    eax, eax
0x1800639ef  js      loc_180063A95
0x1800639f5  mov     r14, [rbp+arg_10]
0x1800639f9  test    r14, r14
0x1800639fc  jnz     short loc_180063A13
0x1800639fe  xor     edx, edx
0x180063a00  mov     esi, 8000000Bh
0x180063a05  mov     ecx, esi
0x180063a07  call    cs:__imp_RoOriginateError
0x180063a0d  nop
0x180063a0e  jmp     loc_180063A95
0x180063a13  lea     rcx, [r15+90h]; this
0x180063a1a  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180063a1f  mov     esi, eax
0x180063a21  test    eax, eax
0x180063a23  js      short loc_180063A95
0x180063a25  mov     rbx, [r14]
0x180063a28  xor     ecx, ecx; string
0x180063a2a  call    cs:__imp_WindowsDeleteString
0x180063a30  mov     rdi, [r14+8]
0x180063a34  xor     ecx, ecx; string
0x180063a36  call    cs:__imp_WindowsDeleteString
0x180063a3c  test    r14, r14
0x180063a3f  jz      short loc_180063A8C
0x180063a41  xor     edx, edx
0x180063a43  mov     eax, [r14+18h]
0x180063a47  div     dword ptr [r15+40h]
0x180063a4b  mov     r8d, edx
0x180063a4e  mov     rdx, [r15+30h]
0x180063a52  mov     rax, [rdx+r8*8]
0x180063a56  cmp     r14, rax
0x180063a59  jnz     short loc_180063A63
0x180063a5b  xor     eax, eax
0x180063a5d  jmp     short loc_180063A69
0x180063a5f  mov     rax, [rax+10h]
0x180063a63  cmp     [rax+10h], r14
0x180063a67  jnz     short loc_180063A5F
0x180063a69  mov     rcx, [r14+10h]
0x180063a6d  test    rax, rax
0x180063a70  jnz     short loc_180063A78
0x180063a72  mov     [rdx+r8*8], rcx
0x180063a76  jmp     short loc_180063A7C
0x180063a78  mov     [rax+10h], rcx
0x180063a7c  mov     rdx, r14
0x180063a7f  lea     rcx, [r15+28h]
0x180063a83  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x180063a88  xor     esi, esi
0x180063a8a  jmp     short loc_180063A95
0x180063a8c  mov     esi, 8000FFFFh
0x180063a91  xor     ebx, ebx
0x180063a93  xor     edi, edi
0x180063a95  mov     rax, [rbp+arg_18]
0x180063a99  test    rax, rax
0x180063a9c  jz      short loc_180063AB6
0x180063a9e  lea     rcx, [rax+8]; SRWLock
0x180063aa2  cmp     dword ptr [rax], 1
0x180063aa5  jnz     short loc_180063AAF
0x180063aa7  add     dword ptr [rcx], 10000000h
0x180063aad  jmp     short loc_180063AB6
0x180063aaf  call    cs:__imp_ReleaseSRWLockExclusive
0x180063ab5  nop
0x180063ab6  mov     rcx, rdi; string
0x180063ab9  call    cs:__imp_WindowsDeleteString
0x180063abf  mov     rcx, rbx; string
0x180063ac2  call    cs:__imp_WindowsDeleteString
0x180063ac8  test    esi, esi
0x180063aca  js      short loc_180063AF1
0x180063acc  mov     rax, [rbp+arg_8]
0x180063ad0  mov     [rsp+30h+var_10], rax
0x180063ad5  mov     r9d, 2
0x180063adb  mov     r8, r15
0x180063ade  movzx   edx, byte ptr [r15+99h]
0x180063ae6  movzx   ecx, byte ptr [rbp+arg_10]
0x180063aea  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x180063aef  mov     esi, eax
0x180063af1  mov     eax, esi
0x180063af3  add     rsp, 30h
0x180063af7  pop     r15
0x180063af9  pop     r14
0x180063afb  pop     r13
0x180063afd  pop     rdi
0x180063afe  pop     rsi
0x180063aff  pop     rbx
0x180063b00  pop     rbp
0x180063b01  retn
```
