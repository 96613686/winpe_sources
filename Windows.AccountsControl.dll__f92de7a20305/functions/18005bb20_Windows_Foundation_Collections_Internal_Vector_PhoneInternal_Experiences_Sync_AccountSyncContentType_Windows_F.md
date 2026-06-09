# Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::AccountSyncContentType,0,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x18005bb20`
- end: `0x18005bc7f`
- name: `?RemoveAtInternal@?$Vector@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005bb00`
- `0x18005bb10`

## callees

- `0x18001c848`
- `0x180020560`
- `0x180021274`
- `0x18005bb20`
- `0x18005be20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005bc3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005bc3f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005bb79`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005bbdc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005bb79`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005bbdc`
- `msvcrt!memmove_s` at `0x18005bbc9`
- `msvcrt!memmove_s` at `0x18005bbc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<enum PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::VectorOptions<enum PhoneInternal::Experiences::Sync::AccountSyncContentType,0,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  int v6; // ebx
  unsigned int *v7; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  RTL_SRWLOCK *v10; // rcx
  int v12; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  XWinRT::SerializingLockPolicy::Write(&v13, a1 + 112, &v12);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v7 = (unsigned int *)(a1 + 80);
    if ( a3 )
      a2 = *v7 - 1;
    if ( a2 >= *v7 )
    {
      v6 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
    if ( v6 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v12, *(unsigned __int8 *)(a1 + 133), a1 + 136);
      v6 = 0;
      if ( a2 < *v7 - 1
        && memmove_s(
             (void *const)(*(_QWORD *)(a1 + 96) + 4LL * a2),
             4LL * (*v7 + ~a2),
             (const void *const)(*(_QWORD *)(a1 + 96) + 4LL * (a2 + 1)),
             4LL * (*v7 + ~a2)) )
      {
        v6 = -2147418113;
        RoOriginateError(2147549183LL, 0);
      }
      else
      {
        ++*(_DWORD *)(a1 + 128);
        --*v7;
        v8 = *(_DWORD *)(a1 + 84);
        if ( *v7 < v8 / 3 )
        {
          v9 = 1;
          if ( v8 - 1 >= v8 - v8 / 3 )
            v9 = v8 / 3;
          v6 = Windows::Foundation::Collections::Internal::Vector<enum PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<enum PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::ResizeStorage(
                 a1,
                 v8 - v9);
        }
      }
    }
  }
  if ( v13 )
  {
    v10 = v13 + 1;
    if ( LODWORD(v13->Ptr) == 1 )
      LODWORD(v10->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v10);
  }
  if ( v6 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v12,
                           *(unsigned __int8 *)(a1 + 132),
                           a1,
                           2,
                           a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005bb20  mov     rax, rsp
0x18005bb23  mov     [rax+10h], rbx
0x18005bb27  mov     [rax+18h], rbp
0x18005bb2b  push    rsi
0x18005bb2c  push    rdi
0x18005bb2d  push    r14
0x18005bb2f  sub     rsp, 30h
0x18005bb33  mov     r14b, r8b
0x18005bb36  mov     ebp, edx
0x18005bb38  mov     rdi, rcx
0x18005bb3b  mov     dword ptr [rax+8], 0
0x18005bb42  lea     rdx, [rcx+70h]
0x18005bb46  lea     r8, [rax+8]
0x18005bb4a  lea     rcx, [rax+20h]
0x18005bb4e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18005bb53  mov     ebx, [rsp+48h+arg_0]
0x18005bb57  test    ebx, ebx
0x18005bb59  js      loc_18005BC24
0x18005bb5f  lea     rsi, [rdi+50h]
0x18005bb63  test    r14b, r14b
0x18005bb66  jz      short loc_18005BB6C
0x18005bb68  mov     ebp, [rsi]
0x18005bb6a  dec     ebp
0x18005bb6c  cmp     ebp, [rsi]
0x18005bb6e  jb      short loc_18005BB80
0x18005bb70  xor     edx, edx
0x18005bb72  mov     ebx, 8000000Bh
0x18005bb77  mov     ecx, ebx
0x18005bb79  call    cs:__imp_RoOriginateError
0x18005bb7f  nop
0x18005bb80  test    ebx, ebx
0x18005bb82  js      loc_18005BC24
0x18005bb88  lea     r8, [rdi+88h]
0x18005bb8f  movzx   edx, byte ptr [rdi+85h]
0x18005bb96  lea     rcx, [rsp+48h+arg_0]
0x18005bb9b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18005bba0  xor     ebx, ebx
0x18005bba2  mov     ecx, [rsi]
0x18005bba4  lea     eax, [rcx-1]
0x18005bba7  cmp     ebp, eax
0x18005bba9  jnb     short loc_18005BBE5
0x18005bbab  mov     edx, ebp
0x18005bbad  not     edx
0x18005bbaf  add     edx, ecx
0x18005bbb1  shl     rdx, 2; DestinationSize
0x18005bbb5  mov     r9, [rdi+60h]
0x18005bbb9  lea     eax, [rbp+1]
0x18005bbbc  lea     r8, [r9+rax*4]; Source
0x18005bbc0  mov     eax, ebp
0x18005bbc2  lea     rcx, [r9+rax*4]; Destination
0x18005bbc6  mov     r9, rdx; SourceSize
0x18005bbc9  call    cs:__imp_memmove_s
0x18005bbcf  test    eax, eax
0x18005bbd1  jz      short loc_18005BBE5
0x18005bbd3  xor     edx, edx
0x18005bbd5  mov     ebx, 8000FFFFh
0x18005bbda  mov     ecx, ebx
0x18005bbdc  call    cs:__imp_RoOriginateError
0x18005bbe2  nop
0x18005bbe3  jmp     short loc_18005BC24
0x18005bbe5  inc     dword ptr [rdi+80h]
0x18005bbeb  dec     dword ptr [rsi]
0x18005bbed  mov     r9d, [rdi+54h]
0x18005bbf1  mov     eax, 0AAAAAAABh
0x18005bbf6  mul     r9d
0x18005bbf9  shr     edx, 1
0x18005bbfb  cmp     [rsi], edx
0x18005bbfd  jnb     short loc_18005BC24
0x18005bbff  mov     ecx, r9d
0x18005bc02  sub     ecx, edx
0x18005bc04  lea     eax, [r9-1]
0x18005bc08  mov     r8d, 1
0x18005bc0e  cmp     eax, ecx
0x18005bc10  cmovnb  r8d, edx
0x18005bc14  sub     r9d, r8d
0x18005bc17  mov     edx, r9d
0x18005bc1a  mov     rcx, rdi
0x18005bc1d  call    ?ResizeStorage@?$Vector@W4PartnershipType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4PartnershipType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4PartnershipType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4PartnershipType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::ResizeStorage(uint)
0x18005bc22  mov     ebx, eax
0x18005bc24  mov     rax, [rsp+48h+arg_18]
0x18005bc29  test    rax, rax
0x18005bc2c  jz      short loc_18005BC46
0x18005bc2e  lea     rcx, [rax+8]; SRWLock
0x18005bc32  cmp     dword ptr [rax], 1
0x18005bc35  jnz     short loc_18005BC3F
0x18005bc37  add     dword ptr [rcx], 10000000h
0x18005bc3d  jmp     short loc_18005BC46
0x18005bc3f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005bc45  nop
0x18005bc46  test    ebx, ebx
0x18005bc48  js      short loc_18005BC6A
0x18005bc4a  mov     [rsp+48h+var_28], ebp
0x18005bc4e  mov     r9d, 2
0x18005bc54  mov     r8, rdi
0x18005bc57  movzx   edx, byte ptr [rdi+84h]
0x18005bc5e  movzx   ecx, byte ptr [rsp+48h+arg_0]
0x18005bc63  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18005bc68  mov     ebx, eax
0x18005bc6a  mov     eax, ebx
0x18005bc6c  mov     rbx, [rsp+48h+arg_8]
0x18005bc71  mov     rbp, [rsp+48h+arg_10]
0x18005bc76  add     rsp, 30h
0x18005bc7a  pop     r14
0x18005bc7c  pop     rdi
0x18005bc7d  pop     rsi
0x18005bc7e  retn
```
