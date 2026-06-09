# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,uchar *)

- ea: `0x180017ff0`
- end: `0x180018168`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@5@PEAE@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a224`

## callees

- `0x180013804`
- `0x180015328`
- `0x180015c54`
- `0x180017ff0`
- `0x18001845c`
- `0x180019424`
- `0x18001a8a8`
- `0x18001b0cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001802d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001802d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018147`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        int a3,
        _BYTE *a4)
{
  HRESULT v8; // ebx
  RTL_SRWLOCK *v9; // rcx
  int v11; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+98h] [rbp+48h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  newString = 0;
  v8 = WindowsDuplicateString(a2, &newString);
  if ( v8 >= 0 )
  {
    v11 = a3;
    LODWORD(v14) = 0;
    XWinRT::SerializingLockPolicy::Write(&v13, a1 + 160, &v14);
    v8 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
      v14 = 0;
      v8 = XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::Lookup(
             a1 + 72,
             &newString,
             &v14);
      if ( v8 >= 0 )
      {
        if ( v14 )
        {
          *(_DWORD *)(v14 + 8) = a3;
          *a4 = 1;
        }
        else if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
        {
          v8 = -2147024882;
        }
        else
        {
          v14 = 0;
          v8 = XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::SetAt(
                 a1 + 72,
                 &newString,
                 &v11,
                 &v14);
          if ( v8 >= 0 )
            newString = 0;
        }
      }
    }
    if ( v13 )
    {
      v9 = v13 + 1;
      if ( LODWORD(v13->Ptr) == 1 )
        LODWORD(v9->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v9);
    }
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v14,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017ff0  mov     [rsp-28h+arg_0], rbx
0x180017ff5  mov     [rsp-28h+arg_8], rsi
0x180017ffa  push    rbp
0x180017ffb  push    rdi
0x180017ffc  push    r12
0x180017ffe  push    r14
0x180018000  push    r15
0x180018002  mov     rbp, rsp
0x180018005  sub     rsp, 50h
0x180018009  mov     r14, r9
0x18001800c  mov     byte ptr [r9], 0
0x180018010  mov     esi, r8d
0x180018013  mov     r12, rdx
0x180018016  mov     rdi, rcx
0x180018019  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18001801e  lea     rdx, [rbp+newString]; newString
0x180018022  mov     [rbp+newString], 0
0x18001802a  mov     rcx, r12; string
0x18001802d  call    cs:__imp_WindowsDuplicateString
0x180018033  mov     ebx, eax
0x180018035  test    eax, eax
0x180018037  js      loc_180018116
0x18001803d  lea     rdx, [rdi+0A0h]
0x180018044  mov     [rbp+var_20], esi
0x180018047  lea     r8, [rbp+arg_18]
0x18001804b  mov     dword ptr [rbp+arg_18], 0
0x180018052  lea     rcx, [rbp+var_10]
0x180018056  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001805b  mov     ebx, dword ptr [rbp+arg_18]
0x18001805e  test    ebx, ebx
0x180018060  js      loc_1800180F6
0x180018066  movzx   edx, byte ptr [rdi+0BAh]
0x18001806d  lea     r8, [rdi+0BCh]
0x180018074  lea     rcx, [rbp+arg_18]
0x180018078  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001807d  lea     rcx, [rdi+0B0h]; this
0x180018084  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180018089  lea     r8, [rbp+arg_18]
0x18001808d  mov     [rbp+arg_18], 0
0x180018095  lea     rdx, [rbp+newString]
0x180018099  lea     rcx, [rdi+48h]
0x18001809d  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::CPair * *)
0x1800180a2  mov     ebx, eax
0x1800180a4  test    eax, eax
0x1800180a6  js      short loc_1800180F6
0x1800180a8  mov     rax, [rbp+arg_18]
0x1800180ac  test    rax, rax
0x1800180af  jz      short loc_1800180BA
0x1800180b1  mov     [rax+8], esi
0x1800180b4  mov     byte ptr [r14], 1
0x1800180b8  jmp     short loc_1800180F6
0x1800180ba  cmp     qword ptr [rdi+58h], 7FFFFFFFh
0x1800180c2  jnz     short loc_1800180CB
0x1800180c4  mov     ebx, 8007000Eh
0x1800180c9  jmp     short loc_1800180F6
0x1800180cb  lea     r9, [rbp+arg_18]
0x1800180cf  mov     [rbp+arg_18], 0
0x1800180d7  lea     r8, [rbp+var_20]
0x1800180db  lea     rdx, [rbp+newString]
0x1800180df  lea     rcx, [rdi+48h]
0x1800180e3  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::SetAt(HSTRING__ * const &,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus const &,XWinRT::TXPOSITION * *)
0x1800180e8  mov     ebx, eax
0x1800180ea  test    eax, eax
0x1800180ec  js      short loc_1800180F6
0x1800180ee  mov     [rbp+newString], 0
0x1800180f6  mov     rax, [rbp+var_10]
0x1800180fa  test    rax, rax
0x1800180fd  jz      short loc_180018116
0x1800180ff  cmp     dword ptr [rax], 1
0x180018102  lea     rcx, [rax+8]; SRWLock
0x180018106  jnz     short loc_180018110
0x180018108  add     dword ptr [rcx], 10000000h
0x18001810e  jmp     short loc_180018116
0x180018110  call    cs:__imp_ReleaseSRWLockExclusive
0x180018116  test    ebx, ebx
0x180018118  js      short loc_180018143
0x18001811a  mov     al, [r14]
0x18001811d  mov     r8, rdi
0x180018120  movzx   edx, byte ptr [rdi+0B9h]
0x180018127  neg     al
0x180018129  movzx   ecx, byte ptr [rbp+arg_18]
0x18001812d  sbb     r9d, r9d
0x180018130  mov     [rsp+50h+var_30], r12
0x180018135  and     r9d, 2
0x180018139  inc     r9d
0x18001813c  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180018141  mov     ebx, eax
0x180018143  mov     rcx, [rbp+newString]; string
0x180018147  call    cs:__imp_WindowsDeleteString
0x18001814d  lea     r11, [rsp+50h+var_s0]
0x180018152  mov     eax, ebx
0x180018154  mov     rbx, [r11+30h]
0x180018158  mov     rsi, [r11+38h]
0x18001815c  mov     rsp, r11
0x18001815f  pop     r15
0x180018161  pop     r14
0x180018163  pop     r12
0x180018165  pop     rdi
0x180018166  pop     rbp
0x180018167  retn
```
