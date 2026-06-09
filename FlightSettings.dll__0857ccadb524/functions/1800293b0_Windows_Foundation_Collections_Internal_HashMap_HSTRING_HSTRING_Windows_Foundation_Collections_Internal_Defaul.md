# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x1800293b0`
- end: `0x180029540`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180025210`
- `0x180025f6c`
- `0x1800265c8`
- `0x180026abc`
- `0x180027fa8`
- `0x180028eac`
- `0x1800293b0`
- `0x18002a068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800294ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800294ee`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029447`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180029447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029500`

## pseudocode

```c
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
    LODWORD(v14) = 0;
    v5 = 0;
    XWinRT::SerializingLockPolicy::Write(&v15, a1 + 128, &v14);
    v3 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v14 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
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
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(
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
0x1800293b0  mov     [rsp-38h+arg_8], rdx
0x1800293b5  push    rbp
0x1800293b6  push    rbx
0x1800293b7  push    rsi
0x1800293b8  push    rdi
0x1800293b9  push    r13
0x1800293bb  push    r14
0x1800293bd  push    r15
0x1800293bf  mov     rbp, rsp
0x1800293c2  sub     rsp, 30h
0x1800293c6  mov     r15, rcx
0x1800293c9  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800293ce  mov     esi, eax
0x1800293d0  test    eax, eax
0x1800293d2  js      loc_180029506
0x1800293d8  xor     ebx, ebx
0x1800293da  lea     rdx, [r15+80h]
0x1800293e1  lea     r8, [rbp+arg_10]
0x1800293e5  mov     dword ptr [rbp+arg_10], ebx
0x1800293e8  lea     rcx, [rbp+arg_18]
0x1800293ec  xor     edi, edi
0x1800293ee  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800293f3  mov     esi, dword ptr [rbp+arg_10]
0x1800293f6  test    esi, esi
0x1800293f8  js      loc_1800294D4
0x1800293fe  movzx   edx, byte ptr [r15+9Ah]
0x180029406  lea     r8, [r15+9Ch]
0x18002940d  lea     rcx, [rbp+arg_10]
0x180029411  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180029416  lea     r8, [rbp+arg_10]
0x18002941a  mov     [rbp+arg_10], rbx
0x18002941e  lea     rdx, [rbp+arg_8]
0x180029422  lea     rcx, [r15+28h]
0x180029426  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x18002942b  mov     esi, eax
0x18002942d  test    eax, eax
0x18002942f  js      loc_1800294D4
0x180029435  mov     r14, [rbp+arg_10]
0x180029439  test    r14, r14
0x18002943c  jnz     short loc_180029452
0x18002943e  mov     esi, 8000000Bh
0x180029443  xor     edx, edx
0x180029445  mov     ecx, esi
0x180029447  call    cs:__imp_RoOriginateError
0x18002944d  jmp     loc_1800294D4
0x180029452  lea     rcx, [r15+90h]; this
0x180029459  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18002945e  mov     esi, eax
0x180029460  test    eax, eax
0x180029462  js      short loc_1800294D4
0x180029464  mov     rbx, [r14]
0x180029467  xor     ecx, ecx; string
0x180029469  call    cs:__imp_WindowsDeleteString
0x18002946f  mov     rdi, [r14+8]
0x180029473  xor     ecx, ecx; string
0x180029475  call    cs:__imp_WindowsDeleteString
0x18002947b  test    r14, r14
0x18002947e  jz      short loc_1800294CB
0x180029480  mov     eax, [r14+18h]
0x180029484  xor     edx, edx
0x180029486  div     dword ptr [r15+40h]
0x18002948a  mov     r8d, edx
0x18002948d  mov     rdx, [r15+30h]
0x180029491  mov     rax, [rdx+r8*8]
0x180029495  cmp     r14, rax
0x180029498  jnz     short loc_1800294A2
0x18002949a  xor     eax, eax
0x18002949c  jmp     short loc_1800294A8
0x18002949e  mov     rax, [rax+10h]
0x1800294a2  cmp     [rax+10h], r14
0x1800294a6  jnz     short loc_18002949E
0x1800294a8  mov     rcx, [r14+10h]
0x1800294ac  test    rax, rax
0x1800294af  jnz     short loc_1800294B7
0x1800294b1  mov     [rdx+r8*8], rcx
0x1800294b5  jmp     short loc_1800294BB
0x1800294b7  mov     [rax+10h], rcx
0x1800294bb  mov     rdx, r14
0x1800294be  lea     rcx, [r15+28h]
0x1800294c2  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x1800294c7  xor     esi, esi
0x1800294c9  jmp     short loc_1800294D4
0x1800294cb  xor     ebx, ebx
0x1800294cd  mov     esi, 8000FFFFh
0x1800294d2  xor     edi, edi
0x1800294d4  mov     rax, [rbp+arg_18]
0x1800294d8  test    rax, rax
0x1800294db  jz      short loc_1800294F4
0x1800294dd  cmp     dword ptr [rax], 1
0x1800294e0  lea     rcx, [rax+8]; SRWLock
0x1800294e4  jnz     short loc_1800294EE
0x1800294e6  add     dword ptr [rcx], 10000000h
0x1800294ec  jmp     short loc_1800294F4
0x1800294ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800294f4  mov     rcx, rdi; string
0x1800294f7  call    cs:__imp_WindowsDeleteString
0x1800294fd  mov     rcx, rbx; string
0x180029500  call    cs:__imp_WindowsDeleteString
0x180029506  test    esi, esi
0x180029508  js      short loc_18002952F
0x18002950a  mov     rax, [rbp+arg_8]
0x18002950e  mov     r9d, 2
0x180029514  movzx   edx, byte ptr [r15+99h]
0x18002951c  mov     r8, r15
0x18002951f  movzx   ecx, byte ptr [rbp+arg_10]
0x180029523  mov     [rsp+30h+var_10], rax
0x180029528  call    ?RaiseEvent@?$VectorOptions@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(...)
0x18002952d  mov     esi, eax
0x18002952f  mov     eax, esi
0x180029531  add     rsp, 30h
0x180029535  pop     r15
0x180029537  pop     r14
0x180029539  pop     r13
0x18002953b  pop     rdi
0x18002953c  pop     rsi
0x18002953d  pop     rbx
0x18002953e  pop     rbp
0x18002953f  retn
```
