# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(uint,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18001e670`
- end: `0x18001e83a`
- name: `?ReplaceAll@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000f15c`
- `0x18000f604`
- `0x18001d5d0`
- `0x18001e670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e7e4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e7e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e6ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e6ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e732`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e732`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7b7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e771`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e771`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::ReplaceAll(
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
    v8 = XWinRT::InterfaceLifetimeTraits::Construct<SystemSettings::DataModel::ISettingItem>(
           v10,
           *(_QWORD *)(a3 + 8 * v9));
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
0x18001e670  push    rbx
0x18001e672  push    rbp
0x18001e673  push    rsi
0x18001e674  push    rdi
0x18001e675  push    r12
0x18001e677  push    r13
0x18001e679  push    r14
0x18001e67b  push    r15
0x18001e67d  sub     rsp, 48h
0x18001e681  xor     esi, esi
0x18001e683  mov     r12d, edx
0x18001e686  mov     [rsp+88h+var_58], 80000015h
0x18001e68e  mov     r13, r8
0x18001e691  mov     [rsp+88h+var_50], rsi
0x18001e696  mov     rdi, rcx
0x18001e699  mov     [rsp+88h+arg_18], esi
0x18001e6a0  test    edx, edx
0x18001e6a2  jz      short loc_18001E709
0x18001e6a4  mov     ecx, r12d
0x18001e6a7  shl     rcx, 4; Size
0x18001e6ab  call    cs:__imp_malloc
0x18001e6b1  mov     rbp, rax
0x18001e6b4  test    rax, rax
0x18001e6b7  jnz     short loc_18001E6C3
0x18001e6b9  mov     ebx, 8007000Eh
0x18001e6be  jmp     loc_18001E827
0x18001e6c3  xor     r15d, r15d
0x18001e6c6  mov     rdx, [r13+r15*8+0]
0x18001e6cb  mov     r14d, r15d
0x18001e6ce  shl     r14, 4
0x18001e6d2  add     r14, rbp
0x18001e6d5  mov     rcx, r14
0x18001e6d8  call    ??$Construct@UISettingItem@DataModel@SystemSettings@@@InterfaceLifetimeTraits@XWinRT@@SAJPEAV?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@1@PEAUISettingItem@DataModel@SystemSettings@@@Z; XWinRT::InterfaceLifetimeTraits::Construct<SystemSettings::DataModel::ISettingItem>(XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem> *,SystemSettings::DataModel::ISettingItem *)
0x18001e6dd  mov     ebx, eax
0x18001e6df  test    eax, eax
0x18001e6e1  js      loc_18001E7BD
0x18001e6e7  mov     ecx, [rsp+88h+arg_18]
0x18001e6ee  inc     r15d
0x18001e6f1  cmp     [r14+8], sil
0x18001e6f5  lea     eax, [rcx+1]
0x18001e6f8  cmovz   eax, ecx
0x18001e6fb  mov     [rsp+88h+arg_18], eax
0x18001e702  cmp     r15d, r12d
0x18001e705  jb      short loc_18001E6C6
0x18001e707  jmp     short loc_18001E711
0x18001e709  xor     r15d, r15d
0x18001e70c  xor     ebp, ebp
0x18001e70e  xor     r12d, r12d
0x18001e711  cmp     dword ptr [rdi+80h], 1
0x18001e718  lea     r14, [rdi+88h]
0x18001e71f  jnz     short loc_18001E72F
0x18001e721  cmp     [r14], esi
0x18001e724  jnz     short loc_18001E738
0x18001e726  mov     dword ptr [r14], 0F0000000h
0x18001e72d  jmp     short loc_18001E738
0x18001e72f  mov     rcx, r14; SRWLock
0x18001e732  call    cs:__imp_AcquireSRWLockExclusive
0x18001e738  mov     ecx, [rdi+0B0h]
0x18001e73e  lea     rsi, [rdi+0B4h]
0x18001e745  mov     eax, [rsi]
0x18001e747  test    eax, eax
0x18001e749  jnz     short loc_18001E759
0x18001e74b  xor     ebx, ebx
0x18001e74d  test    ecx, ecx
0x18001e74f  jle     short loc_18001E75E
0x18001e751  mov     dword ptr [rsi], 1
0x18001e757  jmp     short loc_18001E760
0x18001e759  mov     ebx, 80000015h
0x18001e75e  xor     esi, esi
0x18001e760  mov     [rsp+88h+var_50], rsi
0x18001e765  mov     [rsp+88h+var_58], ebx
0x18001e769  test    ebx, ebx
0x18001e76b  jns     short loc_18001E779
0x18001e76d  xor     edx, edx
0x18001e76f  mov     ecx, ebx
0x18001e771  call    cs:__imp_RoOriginateError
0x18001e777  jmp     short loc_18001E7A2
0x18001e779  mov     eax, [rdi+60h]
0x18001e77c  inc     dword ptr [rdi+90h]
0x18001e782  mov     [rdi+60h], r15d
0x18001e786  mov     r15d, eax
0x18001e789  mov     eax, [rsp+88h+arg_18]
0x18001e790  mov     [rdi+68h], eax
0x18001e793  mov     rax, [rdi+70h]
0x18001e797  mov     [rdi+70h], rbp
0x18001e79b  mov     rbp, rax
0x18001e79e  mov     [rdi+64h], r12d
0x18001e7a2  cmp     dword ptr [rdi+80h], 1
0x18001e7a9  jnz     short loc_18001E7B4
0x18001e7ab  add     dword ptr [r14], 10000000h
0x18001e7b2  jmp     short loc_18001E7BD
0x18001e7b4  mov     rcx, r14; SRWLock
0x18001e7b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e7bd  test    rbp, rbp
0x18001e7c0  jz      short loc_18001E7EA
0x18001e7c2  xor     r14d, r14d
0x18001e7c5  test    r15d, r15d
0x18001e7c8  jz      short loc_18001E7E1
0x18001e7ca  mov     ecx, r14d
0x18001e7cd  shl     rcx, 4
0x18001e7d1  add     rcx, rbp
0x18001e7d4  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIInspectable@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *)
0x18001e7d9  inc     r14d
0x18001e7dc  cmp     r14d, r15d
0x18001e7df  jb      short loc_18001E7CA
0x18001e7e1  mov     rcx, rbp; Block
0x18001e7e4  call    cs:__imp_free
0x18001e7ea  test    ebx, ebx
0x18001e7ec  js      short loc_18001E81C
0x18001e7ee  lea     rcx, [rdi+10h]
0x18001e7f2  mov     [rsp+88h+var_68], 0
0x18001e7fa  mov     rax, rdi
0x18001e7fd  lea     rdx, [rdi+98h]
0x18001e804  neg     rax
0x18001e807  sbb     r8, r8
0x18001e80a  xor     r9d, r9d
0x18001e80d  and     r8, rcx
0x18001e810  lea     rcx, [rsp+88h+var_58]
0x18001e815  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001e81a  mov     ebx, eax
0x18001e81c  test    rsi, rsi
0x18001e81f  jz      short loc_18001E827
0x18001e821  mov     dword ptr [rsi], 0
0x18001e827  mov     eax, ebx
0x18001e829  add     rsp, 48h
0x18001e82d  pop     r15
0x18001e82f  pop     r14
0x18001e831  pop     r13
0x18001e833  pop     r12
0x18001e835  pop     rdi
0x18001e836  pop     rsi
0x18001e837  pop     rbp
0x18001e838  pop     rbx
0x18001e839  retn
```
