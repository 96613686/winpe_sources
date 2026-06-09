# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x1800e7e00`
- end: `0x1800e7f90`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180016e24`
- `0x180016e40`
- `0x180016ee4`
- `0x180017000`
- `0x18003e060`
- `0x180049a24`
- `0x18004b734`
- `0x1800e7e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e7f3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e7f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7f50`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e7e97`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e7e97`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
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
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v14) = 0;
    v5 = 0;
    XWinRT::SerializingLockPolicy::Write(&v15, a1 + 160, &v14);
    v3 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      v14 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
             a1 + 72,
             &v13,
             &v14);
      if ( v3 >= 0 )
      {
        v6 = v14;
        if ( v14 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v6;
            WindowsDeleteString(0);
            v5 = *(HSTRING *)(v6 + 8);
            WindowsDeleteString(0);
            if ( v6 )
            {
              v7 = (unsigned int)(*(_DWORD *)(v6 + 24) % *(_DWORD *)(a1 + 96));
              v8 = *(_QWORD *)(a1 + 80);
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
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
                a1 + 72,
                v6);
              v3 = 0;
            }
            else
            {
              v4 = 0;
              v3 = -2147418113;
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
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v14,
                           *(unsigned __int8 *)(a1 + 185),
                           a1,
                           2,
                           v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800e7e00  mov     [rsp-38h+arg_8], rdx
0x1800e7e05  push    rbp
0x1800e7e06  push    rbx
0x1800e7e07  push    rsi
0x1800e7e08  push    rdi
0x1800e7e09  push    r13
0x1800e7e0b  push    r14
0x1800e7e0d  push    r15
0x1800e7e0f  mov     rbp, rsp
0x1800e7e12  sub     rsp, 30h
0x1800e7e16  mov     r15, rcx
0x1800e7e19  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x1800e7e1e  mov     esi, eax
0x1800e7e20  test    eax, eax
0x1800e7e22  js      loc_1800E7F56
0x1800e7e28  xor     ebx, ebx
0x1800e7e2a  lea     rdx, [r15+0A0h]
0x1800e7e31  lea     r8, [rbp+arg_10]
0x1800e7e35  mov     dword ptr [rbp+arg_10], ebx
0x1800e7e38  lea     rcx, [rbp+arg_18]
0x1800e7e3c  xor     edi, edi
0x1800e7e3e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800e7e43  mov     esi, dword ptr [rbp+arg_10]
0x1800e7e46  test    esi, esi
0x1800e7e48  js      loc_1800E7F24
0x1800e7e4e  movzx   edx, byte ptr [r15+0BAh]
0x1800e7e56  lea     r8, [r15+0BCh]
0x1800e7e5d  lea     rcx, [rbp+arg_10]
0x1800e7e61  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800e7e66  lea     r8, [rbp+arg_10]
0x1800e7e6a  mov     [rbp+arg_10], rbx
0x1800e7e6e  lea     rdx, [rbp+arg_8]
0x1800e7e72  lea     rcx, [r15+48h]
0x1800e7e76  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x1800e7e7b  mov     esi, eax
0x1800e7e7d  test    eax, eax
0x1800e7e7f  js      loc_1800E7F24
0x1800e7e85  mov     r14, [rbp+arg_10]
0x1800e7e89  test    r14, r14
0x1800e7e8c  jnz     short loc_1800E7EA2
0x1800e7e8e  mov     esi, 8000000Bh
0x1800e7e93  xor     edx, edx
0x1800e7e95  mov     ecx, esi
0x1800e7e97  call    cs:__imp_RoOriginateError
0x1800e7e9d  jmp     loc_1800E7F24
0x1800e7ea2  lea     rcx, [r15+0B0h]; this
0x1800e7ea9  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800e7eae  mov     esi, eax
0x1800e7eb0  test    eax, eax
0x1800e7eb2  js      short loc_1800E7F24
0x1800e7eb4  mov     rbx, [r14]
0x1800e7eb7  xor     ecx, ecx; string
0x1800e7eb9  call    cs:__imp_WindowsDeleteString
0x1800e7ebf  mov     rdi, [r14+8]
0x1800e7ec3  xor     ecx, ecx; string
0x1800e7ec5  call    cs:__imp_WindowsDeleteString
0x1800e7ecb  test    r14, r14
0x1800e7ece  jz      short loc_1800E7F1B
0x1800e7ed0  mov     eax, [r14+18h]
0x1800e7ed4  xor     edx, edx
0x1800e7ed6  div     dword ptr [r15+60h]
0x1800e7eda  mov     r8d, edx
0x1800e7edd  mov     rdx, [r15+50h]
0x1800e7ee1  mov     rax, [rdx+r8*8]
0x1800e7ee5  cmp     r14, rax
0x1800e7ee8  jnz     short loc_1800E7EF2
0x1800e7eea  xor     eax, eax
0x1800e7eec  jmp     short loc_1800E7EF8
0x1800e7eee  mov     rax, [rax+10h]
0x1800e7ef2  cmp     [rax+10h], r14
0x1800e7ef6  jnz     short loc_1800E7EEE
0x1800e7ef8  mov     rcx, [r14+10h]
0x1800e7efc  test    rax, rax
0x1800e7eff  jnz     short loc_1800E7F07
0x1800e7f01  mov     [rdx+r8*8], rcx
0x1800e7f05  jmp     short loc_1800E7F0B
0x1800e7f07  mov     [rax+10h], rcx
0x1800e7f0b  mov     rdx, r14
0x1800e7f0e  lea     rcx, [r15+48h]
0x1800e7f12  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x1800e7f17  xor     esi, esi
0x1800e7f19  jmp     short loc_1800E7F24
0x1800e7f1b  xor     ebx, ebx
0x1800e7f1d  mov     esi, 8000FFFFh
0x1800e7f22  xor     edi, edi
0x1800e7f24  mov     rax, [rbp+arg_18]
0x1800e7f28  test    rax, rax
0x1800e7f2b  jz      short loc_1800E7F44
0x1800e7f2d  cmp     dword ptr [rax], 1
0x1800e7f30  lea     rcx, [rax+8]; SRWLock
0x1800e7f34  jnz     short loc_1800E7F3E
0x1800e7f36  add     dword ptr [rcx], 10000000h
0x1800e7f3c  jmp     short loc_1800E7F44
0x1800e7f3e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e7f44  mov     rcx, rdi; string
0x1800e7f47  call    cs:__imp_WindowsDeleteString
0x1800e7f4d  mov     rcx, rbx; string
0x1800e7f50  call    cs:__imp_WindowsDeleteString
0x1800e7f56  test    esi, esi
0x1800e7f58  js      short loc_1800E7F7F
0x1800e7f5a  mov     rax, [rbp+arg_8]
0x1800e7f5e  mov     r9d, 2
0x1800e7f64  movzx   edx, byte ptr [r15+0B9h]
0x1800e7f6c  mov     r8, r15
0x1800e7f6f  movzx   ecx, byte ptr [rbp+arg_10]
0x1800e7f73  mov     [rsp+30h+var_10], rax
0x1800e7f78  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x1800e7f7d  mov     esi, eax
0x1800e7f7f  mov     eax, esi
0x1800e7f81  add     rsp, 30h
0x1800e7f85  pop     r15
0x1800e7f87  pop     r14
0x1800e7f89  pop     r13
0x1800e7f8b  pop     rdi
0x1800e7f8c  pop     rsi
0x1800e7f8d  pop     rbx
0x1800e7f8e  pop     rbp
0x1800e7f8f  retn
```
