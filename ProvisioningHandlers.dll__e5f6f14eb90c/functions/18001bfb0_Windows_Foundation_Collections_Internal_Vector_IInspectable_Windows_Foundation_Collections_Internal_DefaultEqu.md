# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ReplaceAll(uint,IInspectable * *)

- ea: `0x18001bfb0`
- end: `0x18001c1c8`
- name: `?ReplaceAll@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000ee54`
- `0x180011468`
- `0x180019440`
- `0x18001aff0`
- `0x18001ba00`
- `0x18001bfb0`
- `0x18001e83c`
- `0x180021bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!malloc` at `0x18001bff8`
- `msvcrt!malloc` at `0x18001bff8`
- `msvcrt!free` at `0x18001c163`
- `msvcrt!free` at `0x18001c163`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v4; // r14d
  _DWORD *v6; // r12
  int v7; // r13d
  _QWORD *v8; // rbx
  int v9; // esi
  __int64 v10; // r15
  __int64 v11; // rdx
  char *v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rax
  RTL_SRWLOCK *v17; // rcx
  unsigned int v18; // r13d
  __int64 v19; // r12
  __int64 v20; // rcx
  char *v22; // [rsp+30h] [rbp-30h] BYREF
  int v23; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v24; // [rsp+40h] [rbp-20h]
  char v25[24]; // [rsp+48h] [rbp-18h] BYREF
  int v27; // [rsp+B8h] [rbp+58h] BYREF

  v3 = a3;
  v4 = a2;
  v27 = 0;
  v23 = -2147483627;
  v6 = 0;
  v24 = 0;
  v7 = 0;
  if ( a2 )
  {
    v8 = malloc(16LL * a2);
    if ( !v8 )
    {
      v9 = -2147024882;
      goto LABEL_28;
    }
    v10 = 0;
    while ( 1 )
    {
      v11 = *(_QWORD *)(v3 + 8 * v10);
      v12 = (char *)&v8[2 * (unsigned int)v10];
      v22 = v12;
      *(_QWORD *)v12 = 0;
      v12[8] = 0;
      v9 = XWinRT::detail::GitStorageType<IInspectable>::Initialize(v12, v11);
      v27 = v9;
      if ( v9 < 0 )
        break;
      v13 = v7 + 1;
      if ( !v22[8] )
        v13 = v7;
      v7 = v13;
      v10 = (unsigned int)(v10 + 1);
      v3 = a3;
      if ( (unsigned int)v10 >= v4 )
        goto LABEL_11;
    }
  }
  else
  {
    LODWORD(v10) = 0;
    v8 = 0;
    v4 = 0;
LABEL_11:
    XWinRT::SerializingLockPolicy::Write(&v22, a1 + 128, &v27);
    v9 = v27;
    if ( v27 >= 0 )
    {
      v14 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(v25, *(unsigned int *)(a1 + 176), a1 + 180);
      XWinRT::detail::ReentrancyGuard<1>::operator=(&v23, v14);
      v9 = XWinRT::detail::ReentrancyGuard<1>::hr(&v23);
      v6 = v24;
      if ( v9 >= 0 )
      {
        v15 = *(_DWORD *)(a1 + 96);
        *(_DWORD *)(a1 + 96) = v10;
        LODWORD(v10) = v15;
        *(_DWORD *)(a1 + 100) = v4;
        *(_DWORD *)(a1 + 104) = v7;
        v16 = *(_QWORD **)(a1 + 112);
        *(_QWORD *)(a1 + 112) = v8;
        v8 = v16;
        ++*(_DWORD *)(a1 + 144);
      }
    }
    if ( v22 )
    {
      v17 = (RTL_SRWLOCK *)(v22 + 8);
      if ( *(_DWORD *)v22 == 1 )
        LODWORD(v17->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v17);
    }
  }
  if ( v8 )
  {
    v18 = 0;
    if ( (_DWORD)v10 )
    {
      v19 = 0;
      do
      {
        v20 = v8[2 * v19];
        if ( LOBYTE(v8[2 * v19 + 1]) )
        {
          XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v20);
        }
        else if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        LOBYTE(v8[2 * v19 + 1]) = 0;
        v8[2 * v19] = 0;
        ++v18;
        ++v19;
      }
      while ( v18 < (unsigned int)v10 );
      v6 = v24;
    }
    free(v8);
  }
LABEL_28:
  if ( v9 >= 0 )
    v9 = Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(
           &v23,
           a1 + 152,
           (a1 + 16) & -(__int64)(a1 != 0),
           0,
           0);
  if ( v6 )
    *v6 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001bfb0  mov     [rsp-38h+arg_0], rbx
0x18001bfb5  mov     [rsp-38h+arg_10], r8
0x18001bfba  push    rbp
0x18001bfbb  push    rsi
0x18001bfbc  push    rdi
0x18001bfbd  push    r12
0x18001bfbf  push    r13
0x18001bfc1  push    r14
0x18001bfc3  push    r15
0x18001bfc5  mov     rbp, rsp
0x18001bfc8  sub     rsp, 60h
0x18001bfcc  mov     rsi, r8
0x18001bfcf  mov     r14d, edx
0x18001bfd2  mov     rdi, rcx
0x18001bfd5  mov     [rbp+arg_18], 0
0x18001bfdc  mov     [rbp+var_28], 80000015h
0x18001bfe3  xor     r12d, r12d
0x18001bfe6  mov     [rbp+var_20], r12
0x18001bfea  xor     r13d, r13d
0x18001bfed  test    edx, edx
0x18001bfef  jz      short loc_18001C068
0x18001bff1  mov     ecx, r14d
0x18001bff4  shl     rcx, 4; Size
0x18001bff8  call    cs:__imp_malloc
0x18001bfff  nop     dword ptr [rax+rax+00h]
0x18001c004  mov     rbx, rax
0x18001c007  test    rax, rax
0x18001c00a  jnz     short loc_18001C016
0x18001c00c  mov     esi, 8007000Eh
0x18001c011  jmp     loc_18001C16F
0x18001c016  xor     r15d, r15d
0x18001c019  mov     eax, r15d
0x18001c01c  mov     rdx, [rsi+r15*8]
0x18001c020  shl     rax, 4
0x18001c024  add     rax, rbx
0x18001c027  mov     [rbp+var_30], rax
0x18001c02b  mov     [rax], r12
0x18001c02e  mov     [rax+8], r12b
0x18001c032  mov     rcx, rax
0x18001c035  call    ?Initialize@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAJPEAUIInspectable@@@Z; XWinRT::detail::GitStorageType<IInspectable>::Initialize(IInspectable *)
0x18001c03a  mov     esi, eax
0x18001c03c  mov     [rbp+arg_18], eax
0x18001c03f  test    eax, eax
0x18001c041  js      loc_18001C109
0x18001c047  lea     eax, [r13+1]
0x18001c04b  mov     rcx, [rbp+var_30]
0x18001c04f  cmp     [rcx+8], r12b
0x18001c053  cmovz   eax, r13d
0x18001c057  mov     r13d, eax
0x18001c05a  inc     r15d
0x18001c05d  cmp     r15d, r14d
0x18001c060  mov     rsi, [rbp+arg_10]
0x18001c064  jb      short loc_18001C019
0x18001c066  jmp     short loc_18001C070
0x18001c068  xor     r15d, r15d
0x18001c06b  xor     ebx, ebx
0x18001c06d  xor     r14d, r14d
0x18001c070  lea     rdx, [rdi+80h]
0x18001c077  lea     r8, [rbp+arg_18]
0x18001c07b  lea     rcx, [rbp+var_30]
0x18001c07f  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001c084  mov     esi, [rbp+arg_18]
0x18001c087  test    esi, esi
0x18001c089  js      short loc_18001C0E3
0x18001c08b  lea     r8, [rdi+0B4h]
0x18001c092  mov     edx, [rdi+0B0h]
0x18001c098  lea     rcx, [rbp+var_18]
0x18001c09c  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18001c0a1  mov     rdx, rax
0x18001c0a4  lea     rcx, [rbp+var_28]
0x18001c0a8  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18001c0ad  lea     rcx, [rbp+var_28]
0x18001c0b1  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18001c0b6  mov     esi, eax
0x18001c0b8  mov     r12, [rbp+var_20]
0x18001c0bc  test    eax, eax
0x18001c0be  js      short loc_18001C0E3
0x18001c0c0  mov     eax, [rdi+60h]
0x18001c0c3  mov     [rdi+60h], r15d
0x18001c0c7  mov     r15d, eax
0x18001c0ca  mov     [rdi+64h], r14d
0x18001c0ce  mov     [rdi+68h], r13d
0x18001c0d2  mov     rax, [rdi+70h]
0x18001c0d6  mov     [rdi+70h], rbx
0x18001c0da  mov     rbx, rax
0x18001c0dd  inc     dword ptr [rdi+90h]
0x18001c0e3  mov     rax, [rbp+var_30]
0x18001c0e7  test    rax, rax
0x18001c0ea  jz      short loc_18001C109
0x18001c0ec  lea     rcx, [rax+8]; SRWLock
0x18001c0f0  cmp     dword ptr [rax], 1
0x18001c0f3  jnz     short loc_18001C0FD
0x18001c0f5  add     dword ptr [rcx], 10000000h
0x18001c0fb  jmp     short loc_18001C109
0x18001c0fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c104  nop     dword ptr [rax+rax+00h]
0x18001c109  test    rbx, rbx
0x18001c10c  jz      short loc_18001C16F
0x18001c10e  xor     r13d, r13d
0x18001c111  test    r15d, r15d
0x18001c114  jz      short loc_18001C160
0x18001c116  xor     r12d, r12d
0x18001c119  mov     r14, r12
0x18001c11c  add     r14, r14
0x18001c11f  mov     rcx, [rbx+r14*8]
0x18001c123  cmp     byte ptr [rbx+r14*8+8], 0
0x18001c129  jz      short loc_18001C132
0x18001c12b  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x18001c130  jmp     short loc_18001C143
0x18001c132  test    rcx, rcx
0x18001c135  jz      short loc_18001C143
0x18001c137  mov     rax, [rcx]
0x18001c13a  mov     rax, [rax+10h]
0x18001c13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c143  mov     byte ptr [rbx+r14*8+8], 0
0x18001c149  mov     qword ptr [rbx+r14*8], 0
0x18001c151  inc     r13d
0x18001c154  inc     r12
0x18001c157  cmp     r13d, r15d
0x18001c15a  jb      short loc_18001C119
0x18001c15c  mov     r12, [rbp+var_20]
0x18001c160  mov     rcx, rbx; Block
0x18001c163  call    cs:__imp_free
0x18001c16a  nop     dword ptr [rax+rax+00h]
0x18001c16f  test    esi, esi
0x18001c171  js      short loc_18001C1A0
0x18001c173  mov     rax, rdi
0x18001c176  lea     rcx, [rdi+10h]
0x18001c17a  neg     rax
0x18001c17d  sbb     r8, r8
0x18001c180  and     r8, rcx
0x18001c183  lea     rdx, [rdi+98h]
0x18001c18a  mov     [rsp+60h+var_40], 0
0x18001c192  xor     r9d, r9d
0x18001c195  lea     rcx, [rbp+var_28]
0x18001c199  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18001c19e  mov     esi, eax
0x18001c1a0  test    r12, r12
0x18001c1a3  jz      short loc_18001C1AD
0x18001c1a5  mov     dword ptr [r12], 0
0x18001c1ad  mov     eax, esi
0x18001c1af  mov     rbx, [rsp+60h+arg_0]
0x18001c1b7  add     rsp, 60h
0x18001c1bb  pop     r15
0x18001c1bd  pop     r14
0x18001c1bf  pop     r13
0x18001c1c1  pop     r12
0x18001c1c3  pop     rdi
0x18001c1c4  pop     rsi
0x18001c1c5  pop     rbp
0x18001c1c6  retn
```
