# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::GetMany(uint,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * * const,uint *)

- ea: `0x180016ed0`
- end: `0x180017061`
- name: `?GetMany@Iterator@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJIQEAPEAU?$IKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@456@PEAI@Z`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004814`
- `0x18000c6c8`
- `0x180015cb0`
- `0x180016ed0`
- `0x180017068`
- `0x180018224`
- `0x1800186d4`
- `0x180019440`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017041`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017041`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::GetMany(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int *a4)
{
  unsigned int v7; // r14d
  int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // r15
  __int64 v11; // rbx
  __int64 v12; // rsi
  RTL_SRWLOCK *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h] BYREF
  RTL_SRWLOCK *v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+80h] [rbp+40h] BYREF
  int v19; // [rsp+88h] [rbp+48h] BYREF
  unsigned int *v20; // [rsp+98h] [rbp+58h]

  v20 = a4;
  v19 = 0;
  v7 = 0;
  *a4 = 0;
  if ( a2 )
    memset_0(a3, 0, 8LL * a2);
  XWinRT::SerializingLockPolicy::Read(&v17, *(_QWORD *)(a1 + 64) + 160LL, &v19);
  v8 = v19;
  if ( v19 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::EnsureVersionMatches(a1);
  v9 = *(_QWORD *)(a1 + 72);
  v15 = v9;
  v10 = 0;
  while ( v8 >= 0 )
  {
    if ( (unsigned int)v10 >= a2 || !v9 )
      goto LABEL_15;
    v18 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(&v18);
    v8 = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::Make(
           (HSTRING *)v9,
           (int *)(v9 + 8),
           &v18);
    if ( v8 >= 0 )
    {
      v11 = v18;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      v16 = 0;
      *((_QWORD *)a3 + v10) = v11;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
      XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetNext(
        *(_QWORD *)(a1 + 64) + 72LL,
        &v15);
      ++v7;
      v9 = v15;
      if ( !v15 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(&v18);
LABEL_15:
        *(_QWORD *)(a1 + 72) = v9;
        *v20 = v7;
        goto LABEL_19;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(&v18);
    v10 = (unsigned int)(v10 + 1);
  }
  if ( v7 )
  {
    v12 = 0;
    do
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + v12) + 16LL))(*((_QWORD *)a3 + v12));
      *((_QWORD *)a3 + v12) = 0;
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < v7 );
  }
LABEL_19:
  if ( v17 )
  {
    v13 = v17 + 1;
    if ( LODWORD(v17->Ptr) == 1 )
      --LODWORD(v13->Ptr);
    else
      ReleaseSRWLockShared(v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016ed0  mov     [rsp-38h+arg_10], rbx
0x180016ed5  mov     [rsp-38h+arg_18], r9
0x180016eda  push    rbp
0x180016edb  push    rsi
0x180016edc  push    rdi
0x180016edd  push    r12
0x180016edf  push    r13
0x180016ee1  push    r14
0x180016ee3  push    r15
0x180016ee5  mov     rbp, rsp
0x180016ee8  sub     rsp, 40h
0x180016eec  mov     r13, r8
0x180016eef  mov     r12d, edx
0x180016ef2  mov     rsi, rcx
0x180016ef5  mov     [rbp+arg_8], 0
0x180016efc  xor     r14d, r14d
0x180016eff  mov     [r9], r14d
0x180016f02  test    edx, edx
0x180016f04  jz      short loc_180016F17
0x180016f06  mov     r8d, r12d
0x180016f09  shl     r8, 3; Size
0x180016f0d  xor     edx, edx; Val
0x180016f0f  mov     rcx, r13; void *
0x180016f12  call    memset_0
0x180016f17  mov     rdx, [rsi+40h]
0x180016f1b  add     rdx, 0A0h
0x180016f22  lea     r8, [rbp+arg_8]
0x180016f26  lea     rcx, [rbp+var_10]
0x180016f2a  call    ?Read@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireRead@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Read(XWinRT::ComLock &,long *)
0x180016f2f  mov     edi, [rbp+arg_8]
0x180016f32  test    edi, edi
0x180016f34  js      short loc_180016F40
0x180016f36  mov     rcx, rsi
0x180016f39  call    ?EnsureVersionMatches@Iterator@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@AEAAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::EnsureVersionMatches(void)
0x180016f3e  mov     edi, eax
0x180016f40  mov     rbx, [rsi+48h]
0x180016f44  mov     [rbp+var_20], rbx
0x180016f48  xor     r15d, r15d
0x180016f4b  test    edi, edi
0x180016f4d  js      loc_180017003
0x180016f53  cmp     r15d, r12d
0x180016f56  jnb     loc_180016FF2
0x180016f5c  test    rbx, rbx
0x180016f5f  jz      loc_180016FF2
0x180016f65  mov     [rbp+arg_0], 0
0x180016f6d  lea     rcx, [rbp+arg_0]
0x180016f71  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(void)
0x180016f76  lea     rdx, [rbx+8]
0x180016f7a  lea     r8, [rbp+arg_0]
0x180016f7e  mov     rcx, rbx
0x180016f81  call    ?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@5@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::Make(HSTRING__ * const &,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1> * *)
0x180016f86  mov     edi, eax
0x180016f88  test    eax, eax
0x180016f8a  js      short loc_180016FD8
0x180016f8c  mov     rbx, [rbp+arg_0]
0x180016f90  test    rbx, rbx
0x180016f93  jz      short loc_180016FA5
0x180016f95  mov     rax, [rbx]
0x180016f98  mov     rcx, rbx
0x180016f9b  mov     rax, [rax+8]
0x180016f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa4  nop
0x180016fa5  mov     [rbp+var_18], 0
0x180016fad  mov     [r13+r15*8+0], rbx
0x180016fb2  lea     rcx, [rbp+var_18]
0x180016fb6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016fbb  mov     rcx, [rsi+40h]
0x180016fbf  add     rcx, 48h ; 'H'
0x180016fc3  lea     rdx, [rbp+var_20]
0x180016fc7  call    ?GetNext@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEAAPEAVCPair@12@AEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetNext(XWinRT::TXPOSITION * &)
0x180016fcc  inc     r14d
0x180016fcf  mov     rbx, [rbp+var_20]
0x180016fd3  test    rbx, rbx
0x180016fd6  jz      short loc_180016FE9
0x180016fd8  lea     rcx, [rbp+arg_0]
0x180016fdc  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(void)
0x180016fe1  inc     r15d
0x180016fe4  jmp     loc_180016F4B
0x180016fe9  lea     rcx, [rbp+arg_0]
0x180016fed  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(void)
0x180016ff2  test    edi, edi
0x180016ff4  js      short loc_180017003
0x180016ff6  mov     [rsi+48h], rbx
0x180016ffa  mov     rax, [rbp+arg_18]
0x180016ffe  mov     [rax], r14d
0x180017001  jmp     short loc_18001702B
0x180017003  test    r14d, r14d
0x180017006  jz      short loc_18001702B
0x180017008  xor     esi, esi
0x18001700a  mov     rcx, [r13+rsi*8+0]
0x18001700f  mov     rax, [rcx]
0x180017012  mov     rax, [rax+10h]
0x180017016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701b  mov     qword ptr [r13+rsi*8+0], 0
0x180017024  inc     esi
0x180017026  cmp     esi, r14d
0x180017029  jb      short loc_18001700A
0x18001702b  mov     rax, [rbp+var_10]
0x18001702f  test    rax, rax
0x180017032  jz      short loc_180017047
0x180017034  lea     rcx, [rax+8]; SRWLock
0x180017038  cmp     dword ptr [rax], 1
0x18001703b  jnz     short loc_180017041
0x18001703d  dec     dword ptr [rcx]
0x18001703f  jmp     short loc_180017047
0x180017041  call    cs:__imp_ReleaseSRWLockShared
0x180017047  mov     eax, edi
0x180017049  mov     rbx, [rsp+40h+arg_10]
0x180017051  add     rsp, 40h
0x180017055  pop     r15
0x180017057  pop     r14
0x180017059  pop     r13
0x18001705b  pop     r12
0x18001705d  pop     rdi
0x18001705e  pop     rsi
0x18001705f  pop     rbp
0x180017060  retn
```
