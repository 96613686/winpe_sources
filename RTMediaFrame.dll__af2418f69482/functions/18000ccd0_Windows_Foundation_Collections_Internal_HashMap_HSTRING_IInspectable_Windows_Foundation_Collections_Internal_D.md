# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Clear(void)

- ea: `0x18000ccd0`
- end: `0x18000cef6`
- name: `?Clear@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJXZ`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000dc6c`
- `0x18000dfc8`

## callees

- `0x18000ca48`
- `0x18000ca64`
- `0x18000ccd0`
- `0x18000cefc`
- `0x18000d1b0`
- `0x18000dde0`
- `0x18003d210`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cec0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cec0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Clear(
        __int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // rbp
  unsigned int v4; // esi
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // r12
  unsigned int i; // eax
  __int64 j; // rbx
  __int64 v9; // r14
  __int64 v10; // rdx
  void *v11; // rcx
  __int64 result; // rax
  __int64 v13; // [rsp+30h] [rbp-98h] BYREF
  __int64 v14; // [rsp+38h] [rbp-90h]
  __int64 v15; // [rsp+40h] [rbp-88h]
  int v16; // [rsp+48h] [rbp-80h]
  int v17; // [rsp+4Ch] [rbp-7Ch]
  int v18; // [rsp+50h] [rbp-78h]
  int v19; // [rsp+54h] [rbp-74h]
  __int64 v20; // [rsp+58h] [rbp-70h]
  __int64 v21; // [rsp+60h] [rbp-68h]
  int v22; // [rsp+68h] [rbp-60h]
  int v23; // [rsp+6Ch] [rbp-5Ch]
  __int128 v24; // [rsp+70h] [rbp-58h]
  unsigned __int8 v25; // [rsp+D0h] [rbp+8h] BYREF

  if ( *(_BYTE *)(a1 + 184) )
  {
    v13 = a1;
    v2 = 0;
    v14 = 0;
    v3 = 0;
    v15 = 0;
    v4 = 17;
    v16 = 17;
    v22 = 0;
    v23 = 10;
    v24 = 0;
    v17 = 1061158912;
    v18 = 1048576000;
    v19 = 1074790400;
    v20 = 38;
    v21 = 0;
    v5 = (RTL_SRWLOCK *)(a1 + 168);
    if ( *(_DWORD *)(a1 + 160) == 1 )
    {
      if ( !LODWORD(v5->Ptr) )
        LODWORD(v5->Ptr) = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v25, *(unsigned __int8 *)(a1 + 186), a1 + 188);
    v6 = *(_QWORD *)(a1 + 88);
    if ( *(_BYTE *)(a1 + 184) )
    {
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
      XWinRT::FakeStl::swap<XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>>(
        &v13,
        a1 + 72);
      v4 = v16;
      v3 = v15;
      v2 = v14;
    }
    if ( *(_DWORD *)(a1 + 160) == 1 )
      LODWORD(v5->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v5);
    if ( v3 )
    {
      for ( i = 0; i < v4; ++i )
      {
        if ( *(_QWORD *)(v2 + 8LL * i) )
        {
          _mm_lfence();
          for ( j = *(_QWORD *)(v2 + 8LL * i); j; *(_QWORD *)(v9 + 8) = 0 )
          {
            v9 = j;
            if ( *(_QWORD *)(j + 24) )
            {
              j = *(_QWORD *)(j + 24);
            }
            else
            {
              LODWORD(v10) = *(_DWORD *)(j + 32) % v4;
              do
              {
                v10 = (unsigned int)(v10 + 1);
                j = 0;
                if ( (unsigned int)v10 >= v4 )
                  break;
                j = *(_QWORD *)(v2 + 8 * v10);
              }
              while ( !j );
            }
            WindowsDeleteString(*(HSTRING *)v9);
            *(_QWORD *)v9 = 0;
            v11 = *(void **)(v9 + 8);
            if ( *(_BYTE *)(v9 + 16) )
            {
              XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v11);
            }
            else if ( v11 )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
            }
            *(_BYTE *)(v9 + 16) = 0;
          }
          break;
        }
      }
    }
    XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::RemoveAll(&v13);
    XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::RemoveAll(&v13);
    result = 0;
    if ( v6 )
      return Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
               v25,
               *(unsigned __int8 *)(a1 + 185),
               a1,
               0,
               0);
  }
  else
  {
    RoOriginateError(2147549183LL, 0);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ccd0  mov     rax, rsp
0x18000ccd3  push    rbx
0x18000ccd4  push    rbp
0x18000ccd5  push    rsi
0x18000ccd6  push    rdi
0x18000ccd7  push    r12
0x18000ccd9  push    r13
0x18000ccdb  push    r14
0x18000ccdd  push    r15
0x18000ccdf  sub     rsp, 88h
0x18000cce6  mov     rdi, rcx
0x18000cce9  cmp     byte ptr [rcx+0B8h], 0
0x18000ccf0  jz      loc_18000CEB9
0x18000ccf6  mov     [rsp+0C8h+var_98], rcx
0x18000ccfb  xor     r13d, r13d
0x18000ccfe  mov     r15d, r13d
0x18000cd01  mov     [rsp+0C8h+var_90], r13
0x18000cd06  mov     ebp, r13d
0x18000cd09  mov     [rsp+0C8h+var_88], r13
0x18000cd0e  mov     esi, 11h
0x18000cd13  mov     [rax-80h], esi
0x18000cd16  mov     [rax-60h], r13d
0x18000cd1a  mov     dword ptr [rax-5Ch], 0Ah
0x18000cd21  xorps   xmm0, xmm0
0x18000cd24  movdqa  xmmword ptr [rax-58h], xmm0
0x18000cd29  mov     dword ptr [rax-7Ch], 3F400000h
0x18000cd30  mov     dword ptr [rax-78h], 3E800000h
0x18000cd37  mov     dword ptr [rax-74h], 40100000h
0x18000cd3e  mov     qword ptr [rax-70h], 26h ; '&'
0x18000cd46  mov     [rax-68h], r13
0x18000cd4a  lea     rbx, [rcx+0A8h]
0x18000cd51  cmp     dword ptr [rcx+0A0h], 1
0x18000cd58  jz      loc_18000CECD
0x18000cd5e  mov     rcx, rbx; SRWLock
0x18000cd61  call    cs:__imp_AcquireSRWLockExclusive
0x18000cd67  lea     r8, [rdi+0BCh]
0x18000cd6e  movzx   edx, byte ptr [rdi+0BAh]
0x18000cd75  lea     rcx, [rsp+0C8h+arg_0]
0x18000cd7d  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18000cd82  mov     r12, [rdi+58h]
0x18000cd86  cmp     [rdi+0B8h], bpl
0x18000cd8d  jz      short loc_18000CDB7
0x18000cd8f  lea     rcx, [rdi+0B0h]; this
0x18000cd96  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18000cd9b  lea     rdx, [rdi+48h]
0x18000cd9f  lea     rcx, [rsp+0C8h+var_98]
0x18000cda4  call    ??$swap@V?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@@FakeStl@XWinRT@@YAXAEAV?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@1@0@Z; XWinRT::FakeStl::swap<XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>>(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>> &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>> &)
0x18000cda9  mov     esi, [rsp+0C8h+var_80]
0x18000cdad  mov     rbp, [rsp+0C8h+var_88]
0x18000cdb2  mov     r15, [rsp+0C8h+var_90]
0x18000cdb7  cmp     dword ptr [rdi+0A0h], 1
0x18000cdbe  jz      loc_18000CEE0
0x18000cdc4  mov     rcx, rbx; SRWLock
0x18000cdc7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdcd  test    rbp, rbp
0x18000cdd0  jz      loc_18000CE63
0x18000cdd6  mov     eax, r13d
0x18000cdd9  cmp     eax, esi
0x18000cddb  jnb     loc_18000CE63
0x18000cde1  mov     ebx, eax
0x18000cde3  cmp     [r15+rbx*8], r13
0x18000cde7  jnz     short loc_18000CDED
0x18000cde9  inc     eax
0x18000cdeb  jmp     short loc_18000CDD9
0x18000cded  lfence
0x18000cdf0  mov     rbx, [r15+rbx*8]
0x18000cdf4  test    rbx, rbx
0x18000cdf7  jz      short loc_18000CE63
0x18000cdf9  nop     dword ptr [rax+00000000h]
0x18000ce00  lea     r14, [rbx]
0x18000ce03  mov     rax, [rbx+18h]
0x18000ce07  test    rax, rax
0x18000ce0a  jnz     loc_18000CE93
0x18000ce10  xor     edx, edx
0x18000ce12  mov     eax, [rbx+20h]
0x18000ce15  div     esi
0x18000ce17  inc     edx
0x18000ce19  mov     rbx, r13
0x18000ce1c  cmp     edx, esi
0x18000ce1e  jnb     short loc_18000CE29
0x18000ce20  mov     rbx, [r15+rdx*8]
0x18000ce24  test    rbx, rbx
0x18000ce27  jz      short loc_18000CE17
0x18000ce29  mov     rcx, [r14]; string
0x18000ce2c  call    cs:__imp_WindowsDeleteString
0x18000ce32  mov     [r14], r13
0x18000ce35  mov     rcx, [r14+8]; void *
0x18000ce39  cmp     byte ptr [r14+10h], 0
0x18000ce3e  jnz     loc_18000CEEB
0x18000ce44  test    rcx, rcx
0x18000ce47  jz      short loc_18000CE55
0x18000ce49  mov     rax, [rcx]
0x18000ce4c  mov     rax, [rax+10h]
0x18000ce50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce55  mov     byte ptr [r14+10h], 0
0x18000ce5a  mov     [r14+8], r13
0x18000ce5e  test    rbx, rbx
0x18000ce61  jnz     short loc_18000CE00
0x18000ce63  lea     rcx, [rsp+0C8h+var_98]
0x18000ce68  call    ?RemoveAll@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJXZ; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::RemoveAll(void)
0x18000ce6d  lea     rcx, [rsp+0C8h+var_98]
0x18000ce72  call    ?RemoveAll@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJXZ; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::RemoveAll(void)
0x18000ce77  mov     eax, r13d
0x18000ce7a  test    r12, r12
0x18000ce7d  jnz     short loc_18000CE98
0x18000ce7f  add     rsp, 88h
0x18000ce86  pop     r15
0x18000ce88  pop     r14
0x18000ce8a  pop     r13
0x18000ce8c  pop     r12
0x18000ce8e  pop     rdi
0x18000ce8f  pop     rsi
0x18000ce90  pop     rbp
0x18000ce91  pop     rbx
0x18000ce92  retn
0x18000ce93  mov     rbx, rax
0x18000ce96  jmp     short loc_18000CE29
0x18000ce98  mov     [rsp+0C8h+var_A8], r13
0x18000ce9d  xor     r9d, r9d
0x18000cea0  mov     r8, rdi
0x18000cea3  movzx   edx, byte ptr [rdi+0B9h]
0x18000ceaa  movzx   ecx, [rsp+0C8h+arg_0]
0x18000ceb2  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18000ceb7  jmp     short loc_18000CE7F
0x18000ceb9  xor     edx, edx
0x18000cebb  mov     ecx, 8000FFFFh
0x18000cec0  call    cs:__imp_RoOriginateError
0x18000cec6  mov     eax, 8000FFFFh
0x18000cecb  jmp     short loc_18000CE7F
0x18000cecd  cmp     [rbx], ebp
0x18000cecf  jnz     loc_18000CD67
0x18000ced5  mov     dword ptr [rbx], 0F0000000h
0x18000cedb  jmp     loc_18000CD67
0x18000cee0  add     dword ptr [rbx], 10000000h
0x18000cee6  jmp     loc_18000CDCD
0x18000ceeb  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18000cef0  jmp     loc_18000CE55
```
