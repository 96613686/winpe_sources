# Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::InsertAtInternal(uint,PhoneInternal::Experiences::Sync::PartnershipType,bool)

- ea: `0x180059e70`
- end: `0x180059ffb`
- name: `?InsertAtInternal@?$Vector@W4PartnershipType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4PartnershipType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4PartnershipType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4PartnershipType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@AEAAJIW4PartnershipType@Sync@Experiences@PhoneInternal@@_N@Z`
- size: `395`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180058a50`
- `0x180059e60`
- `0x18005cfcc`
- `0x18005dc00`

## callees

- `0x18001c848`
- `0x180020560`
- `0x180021274`
- `0x180059e70`
- `0x18005be20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059fbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059fbe`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059f6a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059f87`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059f6a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059f87`
- `msvcrt!memmove_s` at `0x180059f57`
- `msvcrt!memmove_s` at `0x180059f57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<enum PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<enum PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::InsertAtInternal(
        __int64 a1,
        unsigned int a2,
        int a3,
        char a4)
{
  int v8; // ebx
  unsigned int *v9; // r14
  unsigned int v10; // eax
  unsigned int v11; // r9d
  int v12; // edx
  RTL_SRWLOCK *v13; // rcx
  RTL_SRWLOCK *v15; // [rsp+30h] [rbp-48h] BYREF
  int v16; // [rsp+90h] [rbp+18h] BYREF

  v16 = 0;
  XWinRT::SerializingLockPolicy::Write(&v15, a1 + 112, &v16);
  v8 = v16;
  if ( v16 >= 0 )
  {
    v9 = (unsigned int *)(a1 + 80);
    if ( a4 )
    {
      a2 = *v9;
      v10 = *v9;
    }
    else
    {
      v10 = *v9;
      if ( a2 > *v9 )
      {
        v8 = -2147483637;
        RoOriginateError(2147483659LL, 0);
        goto LABEL_17;
      }
    }
    if ( v10 >= 0x7FFFFFFF )
      v8 = -2147024882;
    if ( v8 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v16, *(unsigned __int8 *)(a1 + 133), a1 + 136);
      v8 = 0;
      v11 = *(_DWORD *)(a1 + 84);
      if ( *v9 + 1 <= v11 )
        goto LABEL_26;
      v12 = 1;
      if ( v11 + 1 <= (v11 >> 1) + v11 )
        v12 = v11 >> 1;
      v8 = Windows::Foundation::Collections::Internal::Vector<enum PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<enum PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::ResizeStorage(
             a1,
             v11 + v12);
      if ( v8 >= 0 )
      {
LABEL_26:
        if ( a2 < *v9
          && memmove_s(
               (void *const)(*(_QWORD *)(a1 + 96) + 4LL * (a2 + 1)),
               4LL * (*(_DWORD *)(a1 + 84) - a2 - 1),
               (const void *const)(*(_QWORD *)(a1 + 96) + 4LL * a2),
               4LL * (*v9 - a2)) )
        {
          v8 = -2147418113;
          RoOriginateError(2147549183LL, 0);
        }
        else
        {
          *(_DWORD *)(*(_QWORD *)(a1 + 96) + 4LL * a2) = a3;
          ++*v9;
          ++*(_DWORD *)(a1 + 128);
        }
      }
    }
  }
LABEL_17:
  if ( v15 )
  {
    v13 = v15 + 1;
    if ( LODWORD(v15->Ptr) == 1 )
      LODWORD(v13->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v13);
  }
  if ( v8 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v16,
                           *(unsigned __int8 *)(a1 + 132),
                           a1,
                           1,
                           a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180059e70  mov     rax, rsp
0x180059e73  push    rbx
0x180059e74  push    rbp
0x180059e75  push    rsi
0x180059e76  push    rdi
0x180059e77  push    r14
0x180059e79  push    r15
0x180059e7b  sub     rsp, 48h
0x180059e7f  mov     bpl, r9b
0x180059e82  mov     r15d, r8d
0x180059e85  mov     esi, edx
0x180059e87  mov     rdi, rcx
0x180059e8a  mov     dword ptr [rax+18h], 0
0x180059e91  lea     rdx, [rcx+70h]
0x180059e95  lea     r8, [rax+18h]
0x180059e99  lea     rcx, [rax-48h]
0x180059e9d  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180059ea2  mov     ebx, [rsp+78h+arg_10]
0x180059ea9  test    ebx, ebx
0x180059eab  js      loc_180059FA3
0x180059eb1  lea     r14, [rdi+50h]
0x180059eb5  test    bpl, bpl
0x180059eb8  jz      loc_180059F73
0x180059ebe  mov     esi, [r14]
0x180059ec1  mov     eax, esi
0x180059ec3  mov     ecx, 8007000Eh
0x180059ec8  cmp     eax, 7FFFFFFFh
0x180059ecd  cmovnb  ebx, ecx
0x180059ed0  test    ebx, ebx
0x180059ed2  js      loc_180059FA3
0x180059ed8  lea     r8, [rdi+88h]
0x180059edf  movzx   edx, byte ptr [rdi+85h]
0x180059ee6  lea     rcx, [rsp+78h+arg_10]
0x180059eee  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180059ef3  xor     ebx, ebx
0x180059ef5  mov     r9d, [rdi+54h]
0x180059ef9  mov     eax, [r14]
0x180059efc  inc     eax
0x180059efe  cmp     eax, r9d
0x180059f01  jbe     short loc_180059F2B
0x180059f03  mov     r8d, r9d
0x180059f06  shr     r8d, 1
0x180059f09  lea     ecx, [r8+r9]
0x180059f0d  lea     eax, [r9+1]
0x180059f11  lea     edx, [rbx+1]
0x180059f14  cmp     eax, ecx
0x180059f16  cmovbe  edx, r8d
0x180059f1a  add     edx, r9d
0x180059f1d  mov     rcx, rdi
0x180059f20  call    ?ResizeStorage@?$Vector@W4PartnershipType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4PartnershipType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4PartnershipType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4PartnershipType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::PartnershipType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::PartnershipType,0,1,0>>::ResizeStorage(uint)
0x180059f25  mov     ebx, eax
0x180059f27  test    eax, eax
0x180059f29  js      short loc_180059FA3
0x180059f2b  mov     eax, [r14]
0x180059f2e  cmp     esi, eax
0x180059f30  jnb     short loc_180059F90
0x180059f32  mov     r10, [rdi+60h]
0x180059f36  sub     eax, esi
0x180059f38  mov     r9d, eax
0x180059f3b  shl     r9, 2; SourceSize
0x180059f3f  mov     eax, esi
0x180059f41  lea     r8, [r10+rax*4]; Source
0x180059f45  mov     edx, [rdi+54h]
0x180059f48  sub     edx, esi
0x180059f4a  dec     edx
0x180059f4c  shl     rdx, 2; DestinationSize
0x180059f50  lea     eax, [rsi+1]
0x180059f53  lea     rcx, [r10+rax*4]; Destination
0x180059f57  call    cs:__imp_memmove_s
0x180059f5d  test    eax, eax
0x180059f5f  jz      short loc_180059F90
0x180059f61  xor     edx, edx
0x180059f63  mov     ebx, 8000FFFFh
0x180059f68  mov     ecx, ebx
0x180059f6a  call    cs:__imp_RoOriginateError
0x180059f70  nop
0x180059f71  jmp     short loc_180059FA3
0x180059f73  mov     eax, [r14]
0x180059f76  cmp     esi, eax
0x180059f78  jbe     loc_180059EC3
0x180059f7e  xor     edx, edx
0x180059f80  mov     ebx, 8000000Bh
0x180059f85  mov     ecx, ebx
0x180059f87  call    cs:__imp_RoOriginateError
0x180059f8d  nop
0x180059f8e  jmp     short loc_180059FA3
0x180059f90  mov     ecx, esi
0x180059f92  mov     rax, [rdi+60h]
0x180059f96  mov     [rax+rcx*4], r15d
0x180059f9a  inc     dword ptr [r14]
0x180059f9d  inc     dword ptr [rdi+80h]
0x180059fa3  mov     rax, [rsp+78h+var_48]
0x180059fa8  test    rax, rax
0x180059fab  jz      short loc_180059FC5
0x180059fad  lea     rcx, [rax+8]; SRWLock
0x180059fb1  cmp     dword ptr [rax], 1
0x180059fb4  jnz     short loc_180059FBE
0x180059fb6  add     dword ptr [rcx], 10000000h
0x180059fbc  jmp     short loc_180059FC5
0x180059fbe  call    cs:__imp_ReleaseSRWLockExclusive
0x180059fc4  nop
0x180059fc5  test    ebx, ebx
0x180059fc7  js      short loc_180059FEC
0x180059fc9  mov     [rsp+78h+var_58], esi
0x180059fcd  mov     r9d, 1
0x180059fd3  mov     r8, rdi
0x180059fd6  movzx   edx, byte ptr [rdi+84h]
0x180059fdd  movzx   ecx, byte ptr [rsp+78h+arg_10]
0x180059fe5  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x180059fea  mov     ebx, eax
0x180059fec  mov     eax, ebx
0x180059fee  add     rsp, 48h
0x180059ff2  pop     r15
0x180059ff4  pop     r14
0x180059ff6  pop     rdi
0x180059ff7  pop     rsi
0x180059ff8  pop     rbp
0x180059ff9  pop     rbx
0x180059ffa  retn
```
