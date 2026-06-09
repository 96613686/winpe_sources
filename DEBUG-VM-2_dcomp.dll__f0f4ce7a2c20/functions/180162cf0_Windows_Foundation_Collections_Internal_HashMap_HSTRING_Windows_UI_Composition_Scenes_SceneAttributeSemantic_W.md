# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x180162cf0`
- end: `0x180162e67`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180162e70`

## callees

- `0x180075074`
- `0x180075090`
- `0x1800751d0`
- `0x1800bb3a0`
- `0x180160e18`
- `0x180161324`
- `0x18016229c`
- `0x180162cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180162e1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180162e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162e25`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180162d87`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180162d87`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
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
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v13) = 0;
    XWinRT::SerializingLockPolicy::Write(&v14, a1 + 160, &v13);
    v3 = v13;
    if ( (int)v13 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      v13 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::Lookup(
             a1 + 72,
             &v12,
             &v13);
      if ( v3 >= 0 )
      {
        v5 = v13;
        if ( v13 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v5;
            WindowsDeleteString(0);
            if ( v5 )
            {
              v6 = (unsigned int)(*(_DWORD *)(v5 + 24) % *(_DWORD *)(a1 + 96));
              v7 = *(_QWORD *)(a1 + 80);
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
              XWinRT::XHashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::FreeNode(
                a1 + 72,
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
          RoOriginateError(2147483659LL);
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
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v13,
                           *(unsigned __int8 *)(a1 + 185),
                           a1,
                           2,
                           v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180162cf0  mov     [rsp-28h+arg_0], rbx
0x180162cf5  mov     [rsp-28h+arg_8], rdx
0x180162cfa  push    rbp
0x180162cfb  push    rsi
0x180162cfc  push    rdi
0x180162cfd  push    r14
0x180162cff  push    r15
0x180162d01  mov     rbp, rsp
0x180162d04  sub     rsp, 30h
0x180162d08  mov     r14, rcx
0x180162d0b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x180162d10  mov     edi, eax
0x180162d12  test    eax, eax
0x180162d14  js      loc_180162E2B
0x180162d1a  xor     ebx, ebx
0x180162d1c  lea     rdx, [r14+0A0h]
0x180162d23  lea     r8, [rbp+arg_10]
0x180162d27  mov     dword ptr [rbp+arg_10], ebx
0x180162d2a  lea     rcx, [rbp+arg_18]
0x180162d2e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180162d33  mov     edi, dword ptr [rbp+arg_10]
0x180162d36  test    edi, edi
0x180162d38  js      loc_180162E02
0x180162d3e  movzx   edx, byte ptr [r14+0BAh]
0x180162d46  lea     r8, [r14+0BCh]
0x180162d4d  lea     rcx, [rbp+arg_10]
0x180162d51  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180162d56  lea     r8, [rbp+arg_10]
0x180162d5a  mov     [rbp+arg_10], rbx
0x180162d5e  lea     rdx, [rbp+arg_8]
0x180162d62  lea     rcx, [r14+48h]
0x180162d66  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::CPair * *)
0x180162d6b  mov     edi, eax
0x180162d6d  test    eax, eax
0x180162d6f  js      loc_180162E02
0x180162d75  mov     rsi, [rbp+arg_10]
0x180162d79  test    rsi, rsi
0x180162d7c  jnz     short loc_180162D8F
0x180162d7e  mov     edi, 8000000Bh
0x180162d83  xor     edx, edx
0x180162d85  mov     ecx, edi
0x180162d87  call    cs:__imp_RoOriginateError
0x180162d8d  jmp     short loc_180162E02
0x180162d8f  lea     rcx, [r14+0B0h]; this
0x180162d96  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180162d9b  mov     edi, eax
0x180162d9d  test    eax, eax
0x180162d9f  js      short loc_180162E02
0x180162da1  mov     rbx, [rsi]
0x180162da4  xor     ecx, ecx; string
0x180162da6  call    cs:__imp_WindowsDeleteString
0x180162dac  test    rsi, rsi
0x180162daf  jz      short loc_180162DFB
0x180162db1  mov     eax, [rsi+18h]
0x180162db4  xor     edx, edx
0x180162db6  div     dword ptr [r14+60h]
0x180162dba  mov     r8d, edx
0x180162dbd  mov     rdx, [r14+50h]
0x180162dc1  mov     rax, [rdx+r8*8]
0x180162dc5  cmp     rsi, rax
0x180162dc8  jnz     short loc_180162DD2
0x180162dca  xor     eax, eax
0x180162dcc  jmp     short loc_180162DD8
0x180162dce  mov     rax, [rax+10h]
0x180162dd2  cmp     [rax+10h], rsi
0x180162dd6  jnz     short loc_180162DCE
0x180162dd8  mov     rcx, [rsi+10h]
0x180162ddc  test    rax, rax
0x180162ddf  jnz     short loc_180162DE7
0x180162de1  mov     [rdx+r8*8], rcx
0x180162de5  jmp     short loc_180162DEB
0x180162de7  mov     [rax+10h], rcx
0x180162deb  mov     rdx, rsi
0x180162dee  lea     rcx, [r14+48h]
0x180162df2  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::UI::Composition::Scenes::SceneAttributeSemantic>>::CNode *)
0x180162df7  xor     edi, edi
0x180162df9  jmp     short loc_180162E02
0x180162dfb  mov     edi, 8000FFFFh
0x180162e00  xor     ebx, ebx
0x180162e02  mov     rax, [rbp+arg_18]
0x180162e06  test    rax, rax
0x180162e09  jz      short loc_180162E22
0x180162e0b  cmp     dword ptr [rax], 1
0x180162e0e  lea     rcx, [rax+8]; SRWLock
0x180162e12  jnz     short loc_180162E1C
0x180162e14  add     dword ptr [rcx], 10000000h
0x180162e1a  jmp     short loc_180162E22
0x180162e1c  call    cs:__imp_ReleaseSRWLockExclusive
0x180162e22  mov     rcx, rbx; string
0x180162e25  call    cs:__imp_WindowsDeleteString
0x180162e2b  test    edi, edi
0x180162e2d  js      short loc_180162E54
0x180162e2f  mov     rax, [rbp+arg_8]
0x180162e33  mov     r9d, 2
0x180162e39  movzx   edx, byte ptr [r14+0B9h]
0x180162e41  mov     r8, r14
0x180162e44  movzx   ecx, byte ptr [rbp+arg_10]
0x180162e48  mov     [rsp+30h+var_10], rax
0x180162e4d  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180162e52  mov     edi, eax
0x180162e54  mov     rbx, [rsp+30h+arg_0]
0x180162e59  mov     eax, edi
0x180162e5b  add     rsp, 30h
0x180162e5f  pop     r15
0x180162e61  pop     r14
0x180162e63  pop     rdi
0x180162e64  pop     rsi
0x180162e65  pop     rbp
0x180162e66  retn
```
