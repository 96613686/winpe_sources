# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180020ae0`
- end: `0x180020c7e`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x18001b9e4`
- `0x18001c848`
- `0x18001d4a8`
- `0x18001d798`
- `0x18001e1a0`
- `0x18001f8f8`
- `0x180020560`
- `0x180020ae0`
- `0x180021274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020b9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020b9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020c3c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180020b7b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180020b7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
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
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
                a1 + 40,
                v5);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
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
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
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
0x180020ae0  mov     [rsp-28h+arg_0], rbx
0x180020ae5  mov     [rsp-28h+arg_8], rdx
0x180020aea  push    rbp
0x180020aeb  push    rsi
0x180020aec  push    rdi
0x180020aed  push    r14
0x180020aef  push    r15
0x180020af1  mov     rbp, rsp
0x180020af4  sub     rsp, 40h
0x180020af8  mov     r14, rcx
0x180020afb  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180020b00  mov     edi, eax
0x180020b02  test    eax, eax
0x180020b04  js      loc_180020C42
0x180020b0a  xor     ebx, ebx
0x180020b0c  mov     [rbp+arg_18], rbx
0x180020b10  mov     dword ptr [rbp+arg_10], ebx
0x180020b13  lea     rdx, [r14+80h]
0x180020b1a  lea     r8, [rbp+arg_10]
0x180020b1e  lea     rcx, [rbp+var_10]
0x180020b22  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180020b27  mov     edi, dword ptr [rbp+arg_10]
0x180020b2a  test    edi, edi
0x180020b2c  js      loc_180020C0F
0x180020b32  lea     r8, [r14+9Ch]
0x180020b39  movzx   edx, byte ptr [r14+9Ah]
0x180020b41  lea     rcx, [rbp+arg_10]
0x180020b45  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180020b4a  mov     [rbp+arg_10], rbx
0x180020b4e  lea     r8, [rbp+arg_10]
0x180020b52  lea     rdx, [rbp+arg_8]
0x180020b56  lea     rcx, [r14+28h]
0x180020b5a  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x180020b5f  mov     edi, eax
0x180020b61  test    eax, eax
0x180020b63  js      loc_180020C0F
0x180020b69  mov     rsi, [rbp+arg_10]
0x180020b6d  test    rsi, rsi
0x180020b70  jnz     short loc_180020B87
0x180020b72  xor     edx, edx
0x180020b74  mov     edi, 8000000Bh
0x180020b79  mov     ecx, edi
0x180020b7b  call    cs:__imp_RoOriginateError
0x180020b81  nop
0x180020b82  jmp     loc_180020C0F
0x180020b87  lea     rcx, [r14+90h]; this
0x180020b8e  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180020b93  mov     edi, eax
0x180020b95  test    eax, eax
0x180020b97  js      short loc_180020C0F
0x180020b99  mov     rbx, [rsi]
0x180020b9c  xor     ecx, ecx; string
0x180020b9e  call    cs:__imp_WindowsDeleteString
0x180020ba4  mov     rdi, [rsi+8]
0x180020ba8  lea     rcx, [rbp+arg_18]
0x180020bac  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180020bb1  mov     [rbp+arg_18], rdi
0x180020bb5  test    rsi, rsi
0x180020bb8  jz      short loc_180020C04
0x180020bba  xor     edx, edx
0x180020bbc  mov     eax, [rsi+18h]
0x180020bbf  div     dword ptr [r14+40h]
0x180020bc3  mov     r8d, edx
0x180020bc6  mov     rdx, [r14+30h]
0x180020bca  mov     rax, [rdx+r8*8]
0x180020bce  cmp     rsi, rax
0x180020bd1  jnz     short loc_180020BDB
0x180020bd3  xor     eax, eax
0x180020bd5  jmp     short loc_180020BE1
0x180020bd7  mov     rax, [rax+10h]
0x180020bdb  cmp     [rax+10h], rsi
0x180020bdf  jnz     short loc_180020BD7
0x180020be1  mov     rcx, [rsi+10h]
0x180020be5  test    rax, rax
0x180020be8  jnz     short loc_180020BF0
0x180020bea  mov     [rdx+r8*8], rcx
0x180020bee  jmp     short loc_180020BF4
0x180020bf0  mov     [rax+10h], rcx
0x180020bf4  mov     rdx, rsi
0x180020bf7  lea     rcx, [r14+28h]
0x180020bfb  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x180020c00  xor     edi, edi
0x180020c02  jmp     short loc_180020C0F
0x180020c04  mov     edi, 8000FFFFh
0x180020c09  xor     ebx, ebx
0x180020c0b  mov     [rbp+arg_18], rbx
0x180020c0f  mov     rax, [rbp+var_10]
0x180020c13  test    rax, rax
0x180020c16  jz      short loc_180020C30
0x180020c18  lea     rcx, [rax+8]; SRWLock
0x180020c1c  cmp     dword ptr [rax], 1
0x180020c1f  jnz     short loc_180020C29
0x180020c21  add     dword ptr [rcx], 10000000h
0x180020c27  jmp     short loc_180020C30
0x180020c29  call    cs:__imp_ReleaseSRWLockExclusive
0x180020c2f  nop
0x180020c30  lea     rcx, [rbp+arg_18]
0x180020c34  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180020c39  mov     rcx, rbx; string
0x180020c3c  call    cs:__imp_WindowsDeleteString
0x180020c42  test    edi, edi
0x180020c44  js      short loc_180020C6B
0x180020c46  mov     rax, [rbp+arg_8]
0x180020c4a  mov     [rsp+40h+var_20], rax
0x180020c4f  mov     r9d, 2
0x180020c55  mov     r8, r14
0x180020c58  movzx   edx, byte ptr [r14+99h]
0x180020c60  movzx   ecx, byte ptr [rbp+arg_10]
0x180020c64  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x180020c69  mov     edi, eax
0x180020c6b  mov     eax, edi
0x180020c6d  mov     rbx, [rsp+40h+arg_0]
0x180020c72  add     rsp, 40h
0x180020c76  pop     r15
0x180020c78  pop     r14
0x180020c7a  pop     rdi
0x180020c7b  pop     rsi
0x180020c7c  pop     rbp
0x180020c7d  retn
```
