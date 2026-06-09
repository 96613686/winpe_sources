# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ReplaceAll(uint,IInspectable * *)

- ea: `0x18001e4a0`
- end: `0x18001e66a`
- name: `?ReplaceAll@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000efec`
- `0x18000f604`
- `0x18001d5d0`
- `0x18001e4a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e614`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e614`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e4db`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e4db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e562`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e562`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e5e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e5e7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e5a1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e5a1`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  _DWORD *v3; // rsi
  unsigned int v4; // r12d
  char *v7; // rbp
  int v8; // ebx
  __int64 v9; // r15
  char *v10; // r14
  int v11; // eax
  _DWORD *v12; // r14
  int v13; // eax
  char *v14; // rax
  unsigned int i; // r14d
  int v17; // [rsp+30h] [rbp-58h] BYREF
  _DWORD *v18; // [rsp+38h] [rbp-50h]
  int v19; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v4 = a2;
  v17 = -2147483627;
  v18 = 0;
  v19 = 0;
  if ( !a2 )
  {
    LODWORD(v9) = 0;
    v7 = 0;
    v4 = 0;
LABEL_11:
    v12 = (_DWORD *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !*v12 )
        *v12 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    v3 = (_DWORD *)(a1 + 180);
    if ( *(_DWORD *)(a1 + 180) )
    {
      v8 = -2147483627;
    }
    else
    {
      v8 = 0;
      if ( *(int *)(a1 + 176) > 0 )
      {
        *v3 = 1;
LABEL_20:
        v18 = v3;
        v17 = v8;
        if ( v8 >= 0 )
        {
          v13 = *(_DWORD *)(a1 + 96);
          ++*(_DWORD *)(a1 + 144);
          *(_DWORD *)(a1 + 96) = v9;
          LODWORD(v9) = v13;
          *(_DWORD *)(a1 + 104) = v19;
          v14 = *(char **)(a1 + 112);
          *(_QWORD *)(a1 + 112) = v7;
          v7 = v14;
          *(_DWORD *)(a1 + 100) = v4;
        }
        else
        {
          RoOriginateError((unsigned int)v8, 0);
        }
        if ( *(_DWORD *)(a1 + 128) == 1 )
          *v12 += 0x10000000;
        else
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 136));
        goto LABEL_26;
      }
    }
    v3 = 0;
    goto LABEL_20;
  }
  v7 = (char *)malloc(16LL * a2);
  if ( !v7 )
    return (unsigned int)-2147024882;
  v9 = 0;
  while ( 1 )
  {
    v10 = &v7[16 * (unsigned int)v9];
    v8 = XWinRT::InterfaceLifetimeTraits::Construct<IInspectable>(v10, *(_QWORD *)(a3 + 8 * v9));
    if ( v8 < 0 )
      break;
    v9 = (unsigned int)(v9 + 1);
    v11 = v19 + 1;
    if ( !v10[8] )
      v11 = v19;
    v19 = v11;
    if ( (unsigned int)v9 >= v4 )
      goto LABEL_11;
  }
LABEL_26:
  if ( v7 )
  {
    for ( i = 0; i < (unsigned int)v9; ++i )
      XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v7[16 * i]);
    free(v7);
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           (unsigned int)&v17,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           0,
           0);
  if ( v3 )
    *v3 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e4a0  push    rbx
0x18001e4a2  push    rbp
0x18001e4a3  push    rsi
0x18001e4a4  push    rdi
0x18001e4a5  push    r12
0x18001e4a7  push    r13
0x18001e4a9  push    r14
0x18001e4ab  push    r15
0x18001e4ad  sub     rsp, 48h
0x18001e4b1  xor     esi, esi
0x18001e4b3  mov     r12d, edx
0x18001e4b6  mov     [rsp+88h+var_58], 80000015h
0x18001e4be  mov     r13, r8
0x18001e4c1  mov     [rsp+88h+var_50], rsi
0x18001e4c6  mov     rdi, rcx
0x18001e4c9  mov     [rsp+88h+arg_18], esi
0x18001e4d0  test    edx, edx
0x18001e4d2  jz      short loc_18001E539
0x18001e4d4  mov     ecx, r12d
0x18001e4d7  shl     rcx, 4; Size
0x18001e4db  call    cs:__imp_malloc
0x18001e4e1  mov     rbp, rax
0x18001e4e4  test    rax, rax
0x18001e4e7  jnz     short loc_18001E4F3
0x18001e4e9  mov     ebx, 8007000Eh
0x18001e4ee  jmp     loc_18001E657
0x18001e4f3  xor     r15d, r15d
0x18001e4f6  mov     rdx, [r13+r15*8+0]
0x18001e4fb  mov     r14d, r15d
0x18001e4fe  shl     r14, 4
0x18001e502  add     r14, rbp
0x18001e505  mov     rcx, r14
0x18001e508  call    ??$Construct@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAJPEAV?$GitStorageType@UIInspectable@@@detail@1@PEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Construct<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *,IInspectable *)
0x18001e50d  mov     ebx, eax
0x18001e50f  test    eax, eax
0x18001e511  js      loc_18001E5ED
0x18001e517  mov     ecx, [rsp+88h+arg_18]
0x18001e51e  inc     r15d
0x18001e521  cmp     [r14+8], sil
0x18001e525  lea     eax, [rcx+1]
0x18001e528  cmovz   eax, ecx
0x18001e52b  mov     [rsp+88h+arg_18], eax
0x18001e532  cmp     r15d, r12d
0x18001e535  jb      short loc_18001E4F6
0x18001e537  jmp     short loc_18001E541
0x18001e539  xor     r15d, r15d
0x18001e53c  xor     ebp, ebp
0x18001e53e  xor     r12d, r12d
0x18001e541  cmp     dword ptr [rdi+80h], 1
0x18001e548  lea     r14, [rdi+88h]
0x18001e54f  jnz     short loc_18001E55F
0x18001e551  cmp     [r14], esi
0x18001e554  jnz     short loc_18001E568
0x18001e556  mov     dword ptr [r14], 0F0000000h
0x18001e55d  jmp     short loc_18001E568
0x18001e55f  mov     rcx, r14; SRWLock
0x18001e562  call    cs:__imp_AcquireSRWLockExclusive
0x18001e568  mov     ecx, [rdi+0B0h]
0x18001e56e  lea     rsi, [rdi+0B4h]
0x18001e575  mov     eax, [rsi]
0x18001e577  test    eax, eax
0x18001e579  jnz     short loc_18001E589
0x18001e57b  xor     ebx, ebx
0x18001e57d  test    ecx, ecx
0x18001e57f  jle     short loc_18001E58E
0x18001e581  mov     dword ptr [rsi], 1
0x18001e587  jmp     short loc_18001E590
0x18001e589  mov     ebx, 80000015h
0x18001e58e  xor     esi, esi
0x18001e590  mov     [rsp+88h+var_50], rsi
0x18001e595  mov     [rsp+88h+var_58], ebx
0x18001e599  test    ebx, ebx
0x18001e59b  jns     short loc_18001E5A9
0x18001e59d  xor     edx, edx
0x18001e59f  mov     ecx, ebx
0x18001e5a1  call    cs:__imp_RoOriginateError
0x18001e5a7  jmp     short loc_18001E5D2
0x18001e5a9  mov     eax, [rdi+60h]
0x18001e5ac  inc     dword ptr [rdi+90h]
0x18001e5b2  mov     [rdi+60h], r15d
0x18001e5b6  mov     r15d, eax
0x18001e5b9  mov     eax, [rsp+88h+arg_18]
0x18001e5c0  mov     [rdi+68h], eax
0x18001e5c3  mov     rax, [rdi+70h]
0x18001e5c7  mov     [rdi+70h], rbp
0x18001e5cb  mov     rbp, rax
0x18001e5ce  mov     [rdi+64h], r12d
0x18001e5d2  cmp     dword ptr [rdi+80h], 1
0x18001e5d9  jnz     short loc_18001E5E4
0x18001e5db  add     dword ptr [r14], 10000000h
0x18001e5e2  jmp     short loc_18001E5ED
0x18001e5e4  mov     rcx, r14; SRWLock
0x18001e5e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e5ed  test    rbp, rbp
0x18001e5f0  jz      short loc_18001E61A
0x18001e5f2  xor     r14d, r14d
0x18001e5f5  test    r15d, r15d
0x18001e5f8  jz      short loc_18001E611
0x18001e5fa  mov     ecx, r14d
0x18001e5fd  shl     rcx, 4
0x18001e601  add     rcx, rbp
0x18001e604  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIInspectable@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *)
0x18001e609  inc     r14d
0x18001e60c  cmp     r14d, r15d
0x18001e60f  jb      short loc_18001E5FA
0x18001e611  mov     rcx, rbp; Block
0x18001e614  call    cs:__imp_free
0x18001e61a  test    ebx, ebx
0x18001e61c  js      short loc_18001E64C
0x18001e61e  lea     rcx, [rdi+10h]
0x18001e622  mov     [rsp+88h+var_68], 0
0x18001e62a  mov     rax, rdi
0x18001e62d  lea     rdx, [rdi+98h]
0x18001e634  neg     rax
0x18001e637  sbb     r8, r8
0x18001e63a  xor     r9d, r9d
0x18001e63d  and     r8, rcx
0x18001e640  lea     rcx, [rsp+88h+var_58]
0x18001e645  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001e64a  mov     ebx, eax
0x18001e64c  test    rsi, rsi
0x18001e64f  jz      short loc_18001E657
0x18001e651  mov     dword ptr [rsi], 0
0x18001e657  mov     eax, ebx
0x18001e659  add     rsp, 48h
0x18001e65d  pop     r15
0x18001e65f  pop     r14
0x18001e661  pop     r13
0x18001e663  pop     r12
0x18001e665  pop     rdi
0x18001e666  pop     rsi
0x18001e667  pop     rbp
0x18001e668  pop     rbx
0x18001e669  retn
```
