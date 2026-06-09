# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x1800aca50`
- end: `0x1800acbc7`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180022ac8`
- `0x1800a1690`
- `0x1800a2830`
- `0x1800a3138`
- `0x1800a47d4`
- `0x1800ab67c`
- `0x1800ac4e0`
- `0x1800aca50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800acb7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800acb7c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800acae7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800acae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acb85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acb85`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  RTL_SRWLOCK *v10; // rcx
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF
  __int64 v13; // [rsp+70h] [rbp+40h] BYREF
  RTL_SRWLOCK *v14; // [rsp+78h] [rbp+48h] BYREF

  v12 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v13) = 0;
    XWinRT::SerializingLockPolicy::Write(&v14, a1 + 128, &v13);
    v3 = v13;
    if ( (int)v13 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v13 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned int>>::Lookup(
             a1 + 40,
             &v12,
             &v13);
      if ( v3 >= 0 )
      {
        v5 = v13;
        if ( v13 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v5;
            WindowsDeleteString(0);
            if ( v5 )
            {
              v6 = (unsigned int)(*(_DWORD *)(v5 + 24) % *(_DWORD *)(a1 + 64));
              v7 = *(_QWORD *)(a1 + 48);
              v8 = *(_QWORD *)(v7 + 8 * v6);
              if ( v5 == v8 )
              {
                v8 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v8 + 16) != v5 )
                  v8 = *(_QWORD *)(v8 + 16);
              }
              v9 = *(_QWORD *)(v5 + 16);
              if ( v8 )
                *(_QWORD *)(v8 + 16) = v9;
              else
                *(_QWORD *)(v7 + 8 * v6) = v9;
              XWinRT::XHashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned int>>::FreeNode(
                a1 + 40,
                v5);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
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
    if ( v14 )
    {
      v10 = v14 + 1;
      if ( LODWORD(v14->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v13,
                           *(unsigned __int8 *)(a1 + 153),
                           a1,
                           2,
                           v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800aca50  mov     [rsp-28h+arg_0], rbx
0x1800aca55  mov     [rsp-28h+arg_8], rdx
0x1800aca5a  push    rbp
0x1800aca5b  push    rsi
0x1800aca5c  push    rdi
0x1800aca5d  push    r14
0x1800aca5f  push    r15
0x1800aca61  mov     rbp, rsp
0x1800aca64  sub     rsp, 30h
0x1800aca68  mov     r14, rcx
0x1800aca6b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800aca70  mov     edi, eax
0x1800aca72  test    eax, eax
0x1800aca74  js      loc_1800ACB8B
0x1800aca7a  xor     ebx, ebx
0x1800aca7c  lea     rdx, [r14+80h]
0x1800aca83  lea     r8, [rbp+arg_10]
0x1800aca87  mov     dword ptr [rbp+arg_10], ebx
0x1800aca8a  lea     rcx, [rbp+arg_18]
0x1800aca8e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800aca93  mov     edi, dword ptr [rbp+arg_10]
0x1800aca96  test    edi, edi
0x1800aca98  js      loc_1800ACB62
0x1800aca9e  movzx   edx, byte ptr [r14+9Ah]
0x1800acaa6  lea     r8, [r14+9Ch]
0x1800acaad  lea     rcx, [rbp+arg_10]
0x1800acab1  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800acab6  lea     r8, [rbp+arg_10]
0x1800acaba  mov     [rbp+arg_10], rbx
0x1800acabe  lea     rdx, [rbp+arg_8]
0x1800acac2  lea     rcx, [r14+28h]
0x1800acac6  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@IUKeyTraits@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@I@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uint>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uint>>::CPair * *)
0x1800acacb  mov     edi, eax
0x1800acacd  test    eax, eax
0x1800acacf  js      loc_1800ACB62
0x1800acad5  mov     rsi, [rbp+arg_10]
0x1800acad9  test    rsi, rsi
0x1800acadc  jnz     short loc_1800ACAEF
0x1800acade  mov     edi, 8000000Bh
0x1800acae3  xor     edx, edx
0x1800acae5  mov     ecx, edi
0x1800acae7  call    cs:__imp_RoOriginateError
0x1800acaed  jmp     short loc_1800ACB62
0x1800acaef  lea     rcx, [r14+90h]; this
0x1800acaf6  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800acafb  mov     edi, eax
0x1800acafd  test    eax, eax
0x1800acaff  js      short loc_1800ACB62
0x1800acb01  mov     rbx, [rsi]
0x1800acb04  xor     ecx, ecx; string
0x1800acb06  call    cs:__imp_WindowsDeleteString
0x1800acb0c  test    rsi, rsi
0x1800acb0f  jz      short loc_1800ACB5B
0x1800acb11  mov     eax, [rsi+18h]
0x1800acb14  xor     edx, edx
0x1800acb16  div     dword ptr [r14+40h]
0x1800acb1a  mov     r8d, edx
0x1800acb1d  mov     rdx, [r14+30h]
0x1800acb21  mov     rax, [rdx+r8*8]
0x1800acb25  cmp     rsi, rax
0x1800acb28  jnz     short loc_1800ACB32
0x1800acb2a  xor     eax, eax
0x1800acb2c  jmp     short loc_1800ACB38
0x1800acb2e  mov     rax, [rax+10h]
0x1800acb32  cmp     [rax+10h], rsi
0x1800acb36  jnz     short loc_1800ACB2E
0x1800acb38  mov     rcx, [rsi+10h]
0x1800acb3c  test    rax, rax
0x1800acb3f  jnz     short loc_1800ACB47
0x1800acb41  mov     [rdx+r8*8], rcx
0x1800acb45  jmp     short loc_1800ACB4B
0x1800acb47  mov     [rax+10h], rcx
0x1800acb4b  mov     rdx, rsi
0x1800acb4e  lea     rcx, [r14+28h]
0x1800acb52  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@IUKeyTraits@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@I@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uint>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uint>>::CNode *)
0x1800acb57  xor     edi, edi
0x1800acb59  jmp     short loc_1800ACB62
0x1800acb5b  mov     edi, 8000FFFFh
0x1800acb60  xor     ebx, ebx
0x1800acb62  mov     rax, [rbp+arg_18]
0x1800acb66  test    rax, rax
0x1800acb69  jz      short loc_1800ACB82
0x1800acb6b  cmp     dword ptr [rax], 1
0x1800acb6e  lea     rcx, [rax+8]; SRWLock
0x1800acb72  jnz     short loc_1800ACB7C
0x1800acb74  add     dword ptr [rcx], 10000000h
0x1800acb7a  jmp     short loc_1800ACB82
0x1800acb7c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800acb82  mov     rcx, rbx; string
0x1800acb85  call    cs:__imp_WindowsDeleteString
0x1800acb8b  test    edi, edi
0x1800acb8d  js      short loc_1800ACBB4
0x1800acb8f  mov     rax, [rbp+arg_8]
0x1800acb93  mov     r9d, 2
0x1800acb99  movzx   edx, byte ptr [r14+99h]
0x1800acba1  mov     r8, r14
0x1800acba4  movzx   ecx, byte ptr [rbp+arg_10]
0x1800acba8  mov     [rsp+30h+var_10], rax
0x1800acbad  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x1800acbb2  mov     edi, eax
0x1800acbb4  mov     rbx, [rsp+30h+arg_0]
0x1800acbb9  mov     eax, edi
0x1800acbbb  add     rsp, 30h
0x1800acbbf  pop     r15
0x1800acbc1  pop     r14
0x1800acbc3  pop     rdi
0x1800acbc4  pop     rsi
0x1800acbc5  pop     rbp
0x1800acbc6  retn
```
