# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x18001e240`
- end: `0x18001e423`
- name: `?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001e220`
- `0x18001e230`

## callees

- `0x180002e3a`
- `0x18000f604`
- `0x18001d5d0`
- `0x18001e240`
- `0x18001ebe0`
- `0x18002921c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e34a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e34a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e292`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e292`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e3c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e3c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e2b0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e2b0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  _DWORD *v3; // rsi
  bool v4; // zf
  RTL_SRWLOCK *v5; // r14
  int v6; // ebx
  __int64 v10; // rax
  __int128 v11; // xmm6
  __int64 v12; // rcx
  size_t v13; // r8
  char *v14; // rdx
  char *v15; // r9
  unsigned int v16; // r9d
  unsigned int v17; // r8d
  __int128 v19; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+40h] [rbp-58h] BYREF
  _DWORD *v21; // [rsp+48h] [rbp-50h]

  v3 = 0;
  v4 = *(_DWORD *)(a1 + 128) == 1;
  v5 = (RTL_SRWLOCK *)(a1 + 136);
  v6 = -2147483627;
  v21 = 0;
  v20 = -2147483627;
  *(_QWORD *)&v19 = 0;
  BYTE8(v19) = 0;
  if ( v4 )
  {
    if ( !LODWORD(v5->Ptr) )
      LODWORD(v5->Ptr) = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
  }
  if ( a3 )
    a2 = *(_DWORD *)(a1 + 96) - 1;
  if ( a2 >= *(_DWORD *)(a1 + 96) )
  {
    v6 = -2147483637;
LABEL_9:
    RoOriginateError((unsigned int)v6, 0);
    goto LABEL_27;
  }
  v3 = (_DWORD *)(a1 + 180);
  if ( *(_DWORD *)(a1 + 180) || (v6 = 0, *(int *)(a1 + 176) <= 0) )
    v3 = 0;
  else
    *v3 = 1;
  v21 = v3;
  v20 = v6;
  if ( v6 < 0 )
    goto LABEL_9;
  v10 = *(_QWORD *)(a1 + 112);
  if ( *(_BYTE *)(v10 + 16LL * a2 + 8) )
    --*(_DWORD *)(a1 + 104);
  v11 = *(_OWORD *)(v10 + 16LL * a2);
  XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v19);
  v12 = *(unsigned int *)(a1 + 96);
  v19 = v11;
  if ( a2 < (int)v12 - 1 )
  {
    v13 = 16LL * ((unsigned int)v12 + ~a2);
    if ( v13 )
    {
      v14 = *(char **)(a1 + 112);
      v15 = &v14[16 * a2];
      if ( !v15 || (v12 = 16LL * (a2 + 1), (v14 += v12) == 0) )
      {
        *(_DWORD *)_o__errno(v12, v14, v13) = 22;
        invalid_parameter_noinfo();
        v6 = -2147418113;
        goto LABEL_9;
      }
      memmove_0(v15, v14, v13);
    }
  }
  v16 = *(_DWORD *)(a1 + 100);
  ++*(_DWORD *)(a1 + 144);
  if ( --*(_DWORD *)(a1 + 96) < v16 / 3 )
  {
    v17 = 1;
    if ( v16 - 1 >= v16 - v16 / 3 )
      v17 = v16 / 3;
    v6 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(
           a1,
           v16 - v17);
  }
LABEL_27:
  if ( *(_DWORD *)(a1 + 128) == 1 )
    LODWORD(v5->Ptr) += 0x10000000;
  else
    ReleaseSRWLockExclusive(v5);
  XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v19);
  if ( v6 >= 0 )
    v6 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           (unsigned int)&v20,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           2,
           a2);
  if ( v3 )
    *v3 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e240  mov     rax, rsp
0x18001e243  push    rbx
0x18001e244  push    rbp
0x18001e245  push    rsi
0x18001e246  push    rdi
0x18001e247  push    r14
0x18001e249  push    r15
0x18001e24b  sub     rsp, 68h
0x18001e24f  xor     esi, esi
0x18001e251  movaps  xmmword ptr [rax-48h], xmm6
0x18001e255  cmp     dword ptr [rcx+80h], 1
0x18001e25c  lea     r14, [rcx+88h]
0x18001e263  mov     ebx, 80000015h
0x18001e268  mov     [rax-50h], rsi
0x18001e26c  mov     r15b, r8b
0x18001e26f  mov     [rax-58h], ebx
0x18001e272  mov     ebp, edx
0x18001e274  mov     [rax-68h], rsi
0x18001e278  mov     rdi, rcx
0x18001e27b  mov     [rax-60h], sil
0x18001e27f  jnz     short loc_18001E28F
0x18001e281  cmp     [r14], esi
0x18001e284  jnz     short loc_18001E298
0x18001e286  mov     dword ptr [r14], 0F0000000h
0x18001e28d  jmp     short loc_18001E298
0x18001e28f  mov     rcx, r14; SRWLock
0x18001e292  call    cs:__imp_AcquireSRWLockExclusive
0x18001e298  test    r15b, r15b
0x18001e29b  jz      short loc_18001E2A2
0x18001e29d  mov     ebp, [rdi+60h]
0x18001e2a0  dec     ebp
0x18001e2a2  cmp     ebp, [rdi+60h]
0x18001e2a5  jb      short loc_18001E2BB
0x18001e2a7  mov     ebx, 8000000Bh
0x18001e2ac  xor     edx, edx
0x18001e2ae  mov     ecx, ebx
0x18001e2b0  call    cs:__imp_RoOriginateError
0x18001e2b6  jmp     loc_18001E3AE
0x18001e2bb  mov     ecx, [rdi+0B0h]
0x18001e2c1  lea     rsi, [rdi+0B4h]
0x18001e2c8  mov     eax, [rsi]
0x18001e2ca  test    eax, eax
0x18001e2cc  jnz     short loc_18001E2DC
0x18001e2ce  xor     ebx, ebx
0x18001e2d0  test    ecx, ecx
0x18001e2d2  jle     short loc_18001E2DC
0x18001e2d4  mov     dword ptr [rsi], 1
0x18001e2da  jmp     short loc_18001E2DE
0x18001e2dc  xor     esi, esi
0x18001e2de  mov     [rsp+98h+var_50], rsi
0x18001e2e3  mov     [rsp+98h+var_58], ebx
0x18001e2e7  test    ebx, ebx
0x18001e2e9  js      short loc_18001E2AC
0x18001e2eb  mov     rax, [rdi+70h]
0x18001e2ef  mov     r15d, ebp
0x18001e2f2  add     r15, r15
0x18001e2f5  cmp     byte ptr [rax+r15*8+8], 0
0x18001e2fb  jz      short loc_18001E300
0x18001e2fd  dec     dword ptr [rdi+68h]
0x18001e300  movups  xmm6, xmmword ptr [rax+r15*8]
0x18001e305  lea     rcx, [rsp+98h+var_68]
0x18001e30a  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIInspectable@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *)
0x18001e30f  mov     ecx, [rdi+60h]
0x18001e312  movdqa  [rsp+98h+var_68], xmm6
0x18001e318  lea     eax, [rcx-1]
0x18001e31b  cmp     ebp, eax
0x18001e31d  jnb     short loc_18001E36D
0x18001e31f  mov     r8d, ebp
0x18001e322  not     r8d
0x18001e325  add     r8d, ecx
0x18001e328  shl     r8, 4; Size
0x18001e32c  test    r8, r8
0x18001e32f  jz      short loc_18001E36D
0x18001e331  mov     rdx, [rdi+70h]
0x18001e335  lea     r9, [rdx+r15*8]
0x18001e339  test    r9, r9
0x18001e33c  jz      short loc_18001E34A
0x18001e33e  lea     ecx, [rbp+1]
0x18001e341  shl     rcx, 4
0x18001e345  add     rdx, rcx; Src
0x18001e348  jnz     short loc_18001E365
0x18001e34a  call    cs:__imp__o__errno
0x18001e350  mov     dword ptr [rax], 16h
0x18001e356  call    _invalid_parameter_noinfo
0x18001e35b  mov     ebx, 8000FFFFh
0x18001e360  jmp     loc_18001E2AC
0x18001e365  mov     rcx, r9; void *
0x18001e368  call    memmove_0
0x18001e36d  mov     r9d, [rdi+64h]
0x18001e371  mov     eax, 0AAAAAAABh
0x18001e376  inc     dword ptr [rdi+90h]
0x18001e37c  dec     dword ptr [rdi+60h]
0x18001e37f  mul     r9d
0x18001e382  shr     edx, 1
0x18001e384  cmp     [rdi+60h], edx
0x18001e387  jnb     short loc_18001E3AE
0x18001e389  mov     ecx, r9d
0x18001e38c  lea     eax, [r9-1]
0x18001e390  sub     ecx, edx
0x18001e392  mov     r8d, 1
0x18001e398  cmp     eax, ecx
0x18001e39a  mov     rcx, rdi
0x18001e39d  cmovnb  r8d, edx
0x18001e3a1  sub     r9d, r8d
0x18001e3a4  mov     edx, r9d
0x18001e3a7  call    ?ResizeStorage@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ResizeStorage(uint)
0x18001e3ac  mov     ebx, eax
0x18001e3ae  cmp     dword ptr [rdi+80h], 1
0x18001e3b5  jnz     short loc_18001E3C0
0x18001e3b7  add     dword ptr [r14], 10000000h
0x18001e3be  jmp     short loc_18001E3C9
0x18001e3c0  mov     rcx, r14; SRWLock
0x18001e3c3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e3c9  lea     rcx, [rsp+98h+var_68]
0x18001e3ce  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIInspectable@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *)
0x18001e3d3  test    ebx, ebx
0x18001e3d5  js      short loc_18001E404
0x18001e3d7  lea     rcx, [rdi+10h]
0x18001e3db  mov     [rsp+98h+var_78], ebp
0x18001e3df  mov     rax, rdi
0x18001e3e2  lea     rdx, [rdi+98h]
0x18001e3e9  neg     rax
0x18001e3ec  mov     r9d, 2
0x18001e3f2  sbb     r8, r8
0x18001e3f5  and     r8, rcx
0x18001e3f8  lea     rcx, [rsp+98h+var_58]
0x18001e3fd  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001e402  mov     ebx, eax
0x18001e404  test    rsi, rsi
0x18001e407  jz      short loc_18001E40F
0x18001e409  mov     dword ptr [rsi], 0
0x18001e40f  movaps  xmm6, [rsp+98h+var_48]
0x18001e414  mov     eax, ebx
0x18001e416  add     rsp, 68h
0x18001e41a  pop     r15
0x18001e41c  pop     r14
0x18001e41e  pop     rdi
0x18001e41f  pop     rsi
0x18001e420  pop     rbp
0x18001e421  pop     rbx
0x18001e422  retn
```
