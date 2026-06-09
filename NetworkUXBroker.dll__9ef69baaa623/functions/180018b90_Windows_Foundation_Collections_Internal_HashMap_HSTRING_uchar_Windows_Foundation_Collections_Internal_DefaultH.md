# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180018b90`
- end: `0x180018d07`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x1800114dc`
- `0x1800138b0`
- `0x180013ca0`
- `0x1800144e4`
- `0x1800173c4`
- `0x1800184a0`
- `0x180018b90`
- `0x18001a140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018cbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018cbc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180018c27`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180018c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018cc5`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
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
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
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
      v3 = XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::Lookup(
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
              XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::FreeNode(
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
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>::RaiseEvent(
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
0x180018b90  mov     [rsp-28h+arg_0], rbx
0x180018b95  mov     [rsp-28h+arg_8], rdx
0x180018b9a  push    rbp
0x180018b9b  push    rsi
0x180018b9c  push    rdi
0x180018b9d  push    r14
0x180018b9f  push    r15
0x180018ba1  mov     rbp, rsp
0x180018ba4  sub     rsp, 30h
0x180018ba8  mov     r14, rcx
0x180018bab  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180018bb0  mov     edi, eax
0x180018bb2  test    eax, eax
0x180018bb4  js      loc_180018CCB
0x180018bba  xor     ebx, ebx
0x180018bbc  lea     rdx, [r14+80h]
0x180018bc3  lea     r8, [rbp+arg_10]
0x180018bc7  mov     dword ptr [rbp+arg_10], ebx
0x180018bca  lea     rcx, [rbp+arg_18]
0x180018bce  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180018bd3  mov     edi, dword ptr [rbp+arg_10]
0x180018bd6  test    edi, edi
0x180018bd8  js      loc_180018CA2
0x180018bde  movzx   edx, byte ptr [r14+9Ah]
0x180018be6  lea     r8, [r14+9Ch]
0x180018bed  lea     rcx, [rbp+arg_10]
0x180018bf1  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180018bf6  lea     r8, [rbp+arg_10]
0x180018bfa  mov     [rbp+arg_10], rbx
0x180018bfe  lea     rdx, [rbp+arg_8]
0x180018c02  lea     rcx, [r14+28h]
0x180018c06  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::CPair * *)
0x180018c0b  mov     edi, eax
0x180018c0d  test    eax, eax
0x180018c0f  js      loc_180018CA2
0x180018c15  mov     rsi, [rbp+arg_10]
0x180018c19  test    rsi, rsi
0x180018c1c  jnz     short loc_180018C2F
0x180018c1e  mov     edi, 8000000Bh
0x180018c23  xor     edx, edx
0x180018c25  mov     ecx, edi
0x180018c27  call    cs:__imp_RoOriginateError
0x180018c2d  jmp     short loc_180018CA2
0x180018c2f  lea     rcx, [r14+90h]; this
0x180018c36  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180018c3b  mov     edi, eax
0x180018c3d  test    eax, eax
0x180018c3f  js      short loc_180018CA2
0x180018c41  mov     rbx, [rsi]
0x180018c44  xor     ecx, ecx; string
0x180018c46  call    cs:__imp_WindowsDeleteString
0x180018c4c  test    rsi, rsi
0x180018c4f  jz      short loc_180018C9B
0x180018c51  mov     eax, [rsi+18h]
0x180018c54  xor     edx, edx
0x180018c56  div     dword ptr [r14+40h]
0x180018c5a  mov     r8d, edx
0x180018c5d  mov     rdx, [r14+30h]
0x180018c61  mov     rax, [rdx+r8*8]
0x180018c65  cmp     rsi, rax
0x180018c68  jnz     short loc_180018C72
0x180018c6a  xor     eax, eax
0x180018c6c  jmp     short loc_180018C78
0x180018c6e  mov     rax, [rax+10h]
0x180018c72  cmp     [rax+10h], rsi
0x180018c76  jnz     short loc_180018C6E
0x180018c78  mov     rcx, [rsi+10h]
0x180018c7c  test    rax, rax
0x180018c7f  jnz     short loc_180018C87
0x180018c81  mov     [rdx+r8*8], rcx
0x180018c85  jmp     short loc_180018C8B
0x180018c87  mov     [rax+10h], rcx
0x180018c8b  mov     rdx, rsi
0x180018c8e  lea     rcx, [r14+28h]
0x180018c92  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::CNode *)
0x180018c97  xor     edi, edi
0x180018c99  jmp     short loc_180018CA2
0x180018c9b  mov     edi, 8000FFFFh
0x180018ca0  xor     ebx, ebx
0x180018ca2  mov     rax, [rbp+arg_18]
0x180018ca6  test    rax, rax
0x180018ca9  jz      short loc_180018CC2
0x180018cab  cmp     dword ptr [rax], 1
0x180018cae  lea     rcx, [rax+8]; SRWLock
0x180018cb2  jnz     short loc_180018CBC
0x180018cb4  add     dword ptr [rcx], 10000000h
0x180018cba  jmp     short loc_180018CC2
0x180018cbc  call    cs:__imp_ReleaseSRWLockExclusive
0x180018cc2  mov     rcx, rbx; string
0x180018cc5  call    cs:__imp_WindowsDeleteString
0x180018ccb  test    edi, edi
0x180018ccd  js      short loc_180018CF4
0x180018ccf  mov     rax, [rbp+arg_8]
0x180018cd3  mov     r9d, 2
0x180018cd9  movzx   edx, byte ptr [r14+99h]
0x180018ce1  mov     r8, r14
0x180018ce4  movzx   ecx, byte ptr [rbp+arg_10]
0x180018ce8  mov     [rsp+30h+var_10], rax
0x180018ced  call    ?RaiseEvent@?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>::RaiseEvent(...)
0x180018cf2  mov     edi, eax
0x180018cf4  mov     rbx, [rsp+30h+arg_0]
0x180018cf9  mov     eax, edi
0x180018cfb  add     rsp, 30h
0x180018cff  pop     r15
0x180018d01  pop     r14
0x180018d03  pop     rdi
0x180018d04  pop     rsi
0x180018d05  pop     rbp
0x180018d06  retn
```
