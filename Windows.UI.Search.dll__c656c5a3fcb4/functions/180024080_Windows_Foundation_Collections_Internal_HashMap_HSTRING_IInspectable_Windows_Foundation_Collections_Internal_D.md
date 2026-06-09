# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180024080`
- end: `0x18002421c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180017708`
- `0x180018268`
- `0x1800195d4`
- `0x18001c248`
- `0x18001d104`
- `0x180020f44`
- `0x180021428`
- `0x180023198`
- `0x180024080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800241c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800241c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002413d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800241da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002413d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800241da`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002411b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002411b`

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
0x180024080  mov     [rsp-28h+arg_0], rbx
0x180024085  mov     [rsp-28h+arg_8], rdx
0x18002408a  push    rbp
0x18002408b  push    rsi
0x18002408c  push    rdi
0x18002408d  push    r14
0x18002408f  push    r15
0x180024091  mov     rbp, rsp
0x180024094  sub     rsp, 40h
0x180024098  mov     r14, rcx
0x18002409b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800240a0  mov     edi, eax
0x1800240a2  test    eax, eax
0x1800240a4  js      loc_1800241E0
0x1800240aa  xor     ebx, ebx
0x1800240ac  lea     rdx, [r14+80h]
0x1800240b3  lea     r8, [rbp+arg_10]
0x1800240b7  mov     [rbp+arg_18], rbx
0x1800240bb  lea     rcx, [rbp+var_10]
0x1800240bf  mov     dword ptr [rbp+arg_10], ebx
0x1800240c2  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800240c7  mov     edi, dword ptr [rbp+arg_10]
0x1800240ca  test    edi, edi
0x1800240cc  js      loc_1800241AE
0x1800240d2  movzx   edx, byte ptr [r14+9Ah]
0x1800240da  lea     r8, [r14+9Ch]
0x1800240e1  lea     rcx, [rbp+arg_10]
0x1800240e5  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800240ea  lea     r8, [rbp+arg_10]
0x1800240ee  mov     [rbp+arg_10], rbx
0x1800240f2  lea     rdx, [rbp+arg_8]
0x1800240f6  lea     rcx, [r14+28h]
0x1800240fa  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x1800240ff  mov     edi, eax
0x180024101  test    eax, eax
0x180024103  js      loc_1800241AE
0x180024109  mov     rsi, [rbp+arg_10]
0x18002410d  test    rsi, rsi
0x180024110  jnz     short loc_180024126
0x180024112  mov     edi, 8000000Bh
0x180024117  xor     edx, edx
0x180024119  mov     ecx, edi
0x18002411b  call    cs:__imp_RoOriginateError
0x180024121  jmp     loc_1800241AE
0x180024126  lea     rcx, [r14+90h]; this
0x18002412d  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180024132  mov     edi, eax
0x180024134  test    eax, eax
0x180024136  js      short loc_1800241AE
0x180024138  mov     rbx, [rsi]
0x18002413b  xor     ecx, ecx; string
0x18002413d  call    cs:__imp_WindowsDeleteString
0x180024143  mov     rdi, [rsi+8]
0x180024147  lea     rcx, [rbp+arg_18]
0x18002414b  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180024150  mov     [rbp+arg_18], rdi
0x180024154  test    rsi, rsi
0x180024157  jz      short loc_1800241A3
0x180024159  mov     eax, [rsi+18h]
0x18002415c  xor     edx, edx
0x18002415e  div     dword ptr [r14+40h]
0x180024162  mov     r8d, edx
0x180024165  mov     rdx, [r14+30h]
0x180024169  mov     rax, [rdx+r8*8]
0x18002416d  cmp     rsi, rax
0x180024170  jnz     short loc_18002417A
0x180024172  xor     eax, eax
0x180024174  jmp     short loc_180024180
0x180024176  mov     rax, [rax+10h]
0x18002417a  cmp     [rax+10h], rsi
0x18002417e  jnz     short loc_180024176
0x180024180  mov     rcx, [rsi+10h]
0x180024184  test    rax, rax
0x180024187  jnz     short loc_18002418F
0x180024189  mov     [rdx+r8*8], rcx
0x18002418d  jmp     short loc_180024193
0x18002418f  mov     [rax+10h], rcx
0x180024193  mov     rdx, rsi
0x180024196  lea     rcx, [r14+28h]
0x18002419a  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CNode *)
0x18002419f  xor     edi, edi
0x1800241a1  jmp     short loc_1800241AE
0x1800241a3  xor     ebx, ebx
0x1800241a5  mov     edi, 8000FFFFh
0x1800241aa  mov     [rbp+arg_18], rbx
0x1800241ae  mov     rax, [rbp+var_10]
0x1800241b2  test    rax, rax
0x1800241b5  jz      short loc_1800241CE
0x1800241b7  cmp     dword ptr [rax], 1
0x1800241ba  lea     rcx, [rax+8]; SRWLock
0x1800241be  jnz     short loc_1800241C8
0x1800241c0  add     dword ptr [rcx], 10000000h
0x1800241c6  jmp     short loc_1800241CE
0x1800241c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800241ce  lea     rcx, [rbp+arg_18]
0x1800241d2  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x1800241d7  mov     rcx, rbx; string
0x1800241da  call    cs:__imp_WindowsDeleteString
0x1800241e0  test    edi, edi
0x1800241e2  js      short loc_180024209
0x1800241e4  mov     rax, [rbp+arg_8]
0x1800241e8  mov     r9d, 2
0x1800241ee  movzx   edx, byte ptr [r14+99h]
0x1800241f6  mov     r8, r14
0x1800241f9  movzx   ecx, byte ptr [rbp+arg_10]
0x1800241fd  mov     [rsp+40h+var_20], rax
0x180024202  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180024207  mov     edi, eax
0x180024209  mov     rbx, [rsp+40h+arg_0]
0x18002420e  mov     eax, edi
0x180024210  add     rsp, 40h
0x180024214  pop     r15
0x180024216  pop     r14
0x180024218  pop     rdi
0x180024219  pop     rsi
0x18002421a  pop     rbp
0x18002421b  retn
```
