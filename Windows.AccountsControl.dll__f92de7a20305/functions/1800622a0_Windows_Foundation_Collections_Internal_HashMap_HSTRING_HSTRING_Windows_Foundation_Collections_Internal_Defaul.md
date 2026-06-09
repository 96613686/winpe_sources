# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x1800622a0`
- end: `0x180062453`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18001b828`
- `0x18001c848`
- `0x18001d4a8`
- `0x18001d798`
- `0x18001f8f8`
- `0x180020560`
- `0x180020dbc`
- `0x180021274`
- `0x1800622a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800623e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800623e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006237a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006237a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800623fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800622dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800622dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  HRESULT v7; // ebx
  HSTRING v8; // rdi
  __int64 v9; // r14
  RTL_SRWLOCK *v10; // rcx
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v14; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+58h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  v7 = WindowsDuplicateString(a2, &newString);
  LODWORD(v15) = v7;
  if ( v7 >= 0 )
  {
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
    v8 = 0;
    v7 = v15;
    if ( (int)v15 >= 0 )
    {
      XWinRT::SerializingLockPolicy::Write(&v14, a1 + 128, &v15);
      v7 = v15;
      if ( (int)v15 >= 0 )
      {
        XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 154), a1 + 156);
        XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
        v15 = 0;
        v7 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
               a1 + 40,
               &newString,
               &v15);
        if ( v7 >= 0 )
        {
          v9 = v15;
          if ( v15 )
          {
            v8 = *(HSTRING *)(v15 + 8);
            WindowsDeleteString(0);
            *(_QWORD *)(v9 + 8) = string;
            string = 0;
            *a4 = 1;
          }
          else if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
          {
            v7 = -2147024882;
          }
          else
          {
            v15 = 0;
            v7 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(
                   a1 + 40,
                   &newString,
                   &string,
                   &v15);
            if ( v7 >= 0 )
            {
              newString = 0;
              string = 0;
            }
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
    }
    WindowsDeleteString(v8);
    WindowsDeleteString(string);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
           (unsigned __int8)v15,
           *(unsigned __int8 *)(a1 + 153),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800622a0  mov     [rsp-38h+arg_0], rbx
0x1800622a5  mov     [rsp-38h+arg_10], r8
0x1800622aa  push    rbp
0x1800622ab  push    rsi
0x1800622ac  push    rdi
0x1800622ad  push    r12
0x1800622af  push    r13
0x1800622b1  push    r14
0x1800622b3  push    r15
0x1800622b5  mov     rbp, rsp
0x1800622b8  sub     rsp, 50h
0x1800622bc  mov     r15, r9
0x1800622bf  mov     r13, rdx
0x1800622c2  mov     rsi, rcx
0x1800622c5  mov     byte ptr [r9], 0
0x1800622c9  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800622ce  mov     [rbp+newString], 0
0x1800622d6  lea     rdx, [rbp+newString]; newString
0x1800622da  mov     rcx, r13; string
0x1800622dd  call    cs:__imp_WindowsDuplicateString
0x1800622e3  mov     ebx, eax
0x1800622e5  mov     dword ptr [rbp+arg_18], eax
0x1800622e8  test    eax, eax
0x1800622ea  js      loc_180062402
0x1800622f0  lea     r8, [rbp+arg_18]
0x1800622f4  lea     rdx, [rbp+arg_10]
0x1800622f8  lea     rcx, [rbp+string]; newString
0x1800622fc  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x180062301  xor     edi, edi
0x180062303  mov     ebx, dword ptr [rbp+arg_18]
0x180062306  test    ebx, ebx
0x180062308  js      loc_1800623EF
0x18006230e  lea     rdx, [rsi+80h]
0x180062315  lea     r8, [rbp+arg_18]
0x180062319  lea     rcx, [rbp+var_10]
0x18006231d  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180062322  mov     ebx, dword ptr [rbp+arg_18]
0x180062325  test    ebx, ebx
0x180062327  js      loc_1800623CE
0x18006232d  lea     r8, [rsi+9Ch]
0x180062334  movzx   edx, byte ptr [rsi+9Ah]
0x18006233b  lea     rcx, [rbp+arg_18]
0x18006233f  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180062344  lea     rcx, [rsi+90h]; this
0x18006234b  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180062350  mov     [rbp+arg_18], rdi
0x180062354  lea     r8, [rbp+arg_18]
0x180062358  lea     rdx, [rbp+newString]
0x18006235c  lea     rcx, [rsi+28h]
0x180062360  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x180062365  mov     ebx, eax
0x180062367  test    eax, eax
0x180062369  js      short loc_1800623CE
0x18006236b  mov     r14, [rbp+arg_18]
0x18006236f  test    r14, r14
0x180062372  jz      short loc_180062396
0x180062374  mov     rdi, [r14+8]
0x180062378  xor     ecx, ecx; string
0x18006237a  call    cs:__imp_WindowsDeleteString
0x180062380  mov     rax, [rbp+string]
0x180062384  mov     [r14+8], rax
0x180062388  mov     [rbp+string], 0
0x180062390  mov     byte ptr [r15], 1
0x180062394  jmp     short loc_1800623CE
0x180062396  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x18006239e  jnz     short loc_1800623A7
0x1800623a0  mov     ebx, 8007000Eh
0x1800623a5  jmp     short loc_1800623CE
0x1800623a7  mov     [rbp+arg_18], rdi
0x1800623ab  lea     r9, [rbp+arg_18]
0x1800623af  lea     r8, [rbp+string]
0x1800623b3  lea     rdx, [rbp+newString]
0x1800623b7  lea     rcx, [rsi+28h]
0x1800623bb  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(HSTRING__ * const &,IInspectable * const &,XWinRT::TXPOSITION * *)
0x1800623c0  mov     ebx, eax
0x1800623c2  test    eax, eax
0x1800623c4  js      short loc_1800623CE
0x1800623c6  mov     [rbp+newString], rdi
0x1800623ca  mov     [rbp+string], rdi
0x1800623ce  mov     rax, [rbp+var_10]
0x1800623d2  test    rax, rax
0x1800623d5  jz      short loc_1800623EF
0x1800623d7  lea     rcx, [rax+8]; SRWLock
0x1800623db  cmp     dword ptr [rax], 1
0x1800623de  jnz     short loc_1800623E8
0x1800623e0  add     dword ptr [rcx], 10000000h
0x1800623e6  jmp     short loc_1800623EF
0x1800623e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800623ee  nop
0x1800623ef  mov     rcx, rdi; string
0x1800623f2  call    cs:__imp_WindowsDeleteString
0x1800623f8  mov     rcx, [rbp+string]; string
0x1800623fc  call    cs:__imp_WindowsDeleteString
0x180062402  test    ebx, ebx
0x180062404  js      short loc_18006242F
0x180062406  mov     al, [r15]
0x180062409  neg     al
0x18006240b  sbb     r9d, r9d
0x18006240e  and     r9d, 2
0x180062412  inc     r9d
0x180062415  mov     [rsp+50h+var_30], r13
0x18006241a  mov     r8, rsi
0x18006241d  movzx   edx, byte ptr [rsi+99h]
0x180062424  movzx   ecx, byte ptr [rbp+arg_18]
0x180062428  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18006242d  mov     ebx, eax
0x18006242f  mov     rcx, [rbp+newString]; string
0x180062433  call    cs:__imp_WindowsDeleteString
0x180062439  mov     eax, ebx
0x18006243b  mov     rbx, [rsp+50h+arg_0]
0x180062443  add     rsp, 50h
0x180062447  pop     r15
0x180062449  pop     r14
0x18006244b  pop     r13
0x18006244d  pop     r12
0x18006244f  pop     rdi
0x180062450  pop     rsi
0x180062451  pop     rbp
0x180062452  retn
```
