# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x18003fca0`
- end: `0x18003fe17`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@HU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@H@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@HU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `375`
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
- `0x18002a068`
- `0x18003fca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fdcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fdcc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003fd37`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003fd37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fdd5`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
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
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
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
      v3 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
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
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
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
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(
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
0x18003fca0  mov     [rsp-28h+arg_0], rbx
0x18003fca5  mov     [rsp-28h+arg_8], rdx
0x18003fcaa  push    rbp
0x18003fcab  push    rsi
0x18003fcac  push    rdi
0x18003fcad  push    r14
0x18003fcaf  push    r15
0x18003fcb1  mov     rbp, rsp
0x18003fcb4  sub     rsp, 30h
0x18003fcb8  mov     r14, rcx
0x18003fcbb  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x18003fcc0  mov     edi, eax
0x18003fcc2  test    eax, eax
0x18003fcc4  js      loc_18003FDDB
0x18003fcca  xor     ebx, ebx
0x18003fccc  lea     rdx, [r14+80h]
0x18003fcd3  lea     r8, [rbp+arg_10]
0x18003fcd7  mov     dword ptr [rbp+arg_10], ebx
0x18003fcda  lea     rcx, [rbp+arg_18]
0x18003fcde  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18003fce3  mov     edi, dword ptr [rbp+arg_10]
0x18003fce6  test    edi, edi
0x18003fce8  js      loc_18003FDB2
0x18003fcee  movzx   edx, byte ptr [r14+9Ah]
0x18003fcf6  lea     r8, [r14+9Ch]
0x18003fcfd  lea     rcx, [rbp+arg_10]
0x18003fd01  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18003fd06  lea     r8, [rbp+arg_10]
0x18003fd0a  mov     [rbp+arg_10], rbx
0x18003fd0e  lea     rdx, [rbp+arg_8]
0x18003fd12  lea     rcx, [r14+28h]
0x18003fd16  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x18003fd1b  mov     edi, eax
0x18003fd1d  test    eax, eax
0x18003fd1f  js      loc_18003FDB2
0x18003fd25  mov     rsi, [rbp+arg_10]
0x18003fd29  test    rsi, rsi
0x18003fd2c  jnz     short loc_18003FD3F
0x18003fd2e  mov     edi, 8000000Bh
0x18003fd33  xor     edx, edx
0x18003fd35  mov     ecx, edi
0x18003fd37  call    cs:__imp_RoOriginateError
0x18003fd3d  jmp     short loc_18003FDB2
0x18003fd3f  lea     rcx, [r14+90h]; this
0x18003fd46  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18003fd4b  mov     edi, eax
0x18003fd4d  test    eax, eax
0x18003fd4f  js      short loc_18003FDB2
0x18003fd51  mov     rbx, [rsi]
0x18003fd54  xor     ecx, ecx; string
0x18003fd56  call    cs:__imp_WindowsDeleteString
0x18003fd5c  test    rsi, rsi
0x18003fd5f  jz      short loc_18003FDAB
0x18003fd61  mov     eax, [rsi+18h]
0x18003fd64  xor     edx, edx
0x18003fd66  div     dword ptr [r14+40h]
0x18003fd6a  mov     r8d, edx
0x18003fd6d  mov     rdx, [r14+30h]
0x18003fd71  mov     rax, [rdx+r8*8]
0x18003fd75  cmp     rsi, rax
0x18003fd78  jnz     short loc_18003FD82
0x18003fd7a  xor     eax, eax
0x18003fd7c  jmp     short loc_18003FD88
0x18003fd7e  mov     rax, [rax+10h]
0x18003fd82  cmp     [rax+10h], rsi
0x18003fd86  jnz     short loc_18003FD7E
0x18003fd88  mov     rcx, [rsi+10h]
0x18003fd8c  test    rax, rax
0x18003fd8f  jnz     short loc_18003FD97
0x18003fd91  mov     [rdx+r8*8], rcx
0x18003fd95  jmp     short loc_18003FD9B
0x18003fd97  mov     [rax+10h], rcx
0x18003fd9b  mov     rdx, rsi
0x18003fd9e  lea     rcx, [r14+28h]
0x18003fda2  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x18003fda7  xor     edi, edi
0x18003fda9  jmp     short loc_18003FDB2
0x18003fdab  mov     edi, 8000FFFFh
0x18003fdb0  xor     ebx, ebx
0x18003fdb2  mov     rax, [rbp+arg_18]
0x18003fdb6  test    rax, rax
0x18003fdb9  jz      short loc_18003FDD2
0x18003fdbb  cmp     dword ptr [rax], 1
0x18003fdbe  lea     rcx, [rax+8]; SRWLock
0x18003fdc2  jnz     short loc_18003FDCC
0x18003fdc4  add     dword ptr [rcx], 10000000h
0x18003fdca  jmp     short loc_18003FDD2
0x18003fdcc  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fdd2  mov     rcx, rbx; string
0x18003fdd5  call    cs:__imp_WindowsDeleteString
0x18003fddb  test    edi, edi
0x18003fddd  js      short loc_18003FE04
0x18003fddf  mov     rax, [rbp+arg_8]
0x18003fde3  mov     r9d, 2
0x18003fde9  movzx   edx, byte ptr [r14+99h]
0x18003fdf1  mov     r8, r14
0x18003fdf4  movzx   ecx, byte ptr [rbp+arg_10]
0x18003fdf8  mov     [rsp+30h+var_10], rax
0x18003fdfd  call    ?RaiseEvent@?$VectorOptions@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(...)
0x18003fe02  mov     edi, eax
0x18003fe04  mov     rbx, [rsp+30h+arg_0]
0x18003fe09  mov     eax, edi
0x18003fe0b  add     rsp, 30h
0x18003fe0f  pop     r15
0x18003fe11  pop     r14
0x18003fe13  pop     rdi
0x18003fe14  pop     rsi
0x18003fe15  pop     rbp
0x18003fe16  retn
```
