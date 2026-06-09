# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::ReplaceAll(uint,IInspectable * *)

- ea: `0x180027700`
- end: `0x180027905`
- name: `?ReplaceAll@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800188ec`
- `0x18001aff8`
- `0x180023450`
- `0x180025f80`
- `0x1800271ec`
- `0x180027700`
- `0x18002a724`
- `0x18002c540`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800278a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800278a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027748`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027748`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027847`

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
  void *v20; // rcx
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
        v20 = (void *)v8[2 * v19];
        if ( LOBYTE(v8[2 * v19 + 1]) )
        {
          XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(v20);
        }
        else if ( v20 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
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
           (unsigned int)&v23,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           0,
           0);
  if ( v6 )
    *v6 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027700  mov     [rsp-38h+arg_0], rbx
0x180027705  mov     [rsp-38h+arg_10], r8
0x18002770a  push    rbp
0x18002770b  push    rsi
0x18002770c  push    rdi
0x18002770d  push    r12
0x18002770f  push    r13
0x180027711  push    r14
0x180027713  push    r15
0x180027715  mov     rbp, rsp
0x180027718  sub     rsp, 60h
0x18002771c  mov     rsi, r8
0x18002771f  mov     r14d, edx
0x180027722  mov     rdi, rcx
0x180027725  mov     [rbp+arg_18], 0
0x18002772c  mov     [rbp+var_28], 80000015h
0x180027733  xor     r12d, r12d
0x180027736  mov     [rbp+var_20], r12
0x18002773a  xor     r13d, r13d
0x18002773d  test    edx, edx
0x18002773f  jz      short loc_1800277B2
0x180027741  mov     ecx, r14d
0x180027744  shl     rcx, 4; Size
0x180027748  call    cs:__imp_malloc
0x18002774e  mov     rbx, rax
0x180027751  test    rax, rax
0x180027754  jnz     short loc_180027760
0x180027756  mov     esi, 8007000Eh
0x18002775b  jmp     loc_1800278AD
0x180027760  xor     r15d, r15d
0x180027763  mov     eax, r15d
0x180027766  mov     rdx, [rsi+r15*8]
0x18002776a  shl     rax, 4
0x18002776e  add     rax, rbx
0x180027771  mov     [rbp+var_30], rax
0x180027775  mov     [rax], r12
0x180027778  mov     [rax+8], r12b
0x18002777c  mov     rcx, rax
0x18002777f  call    ?Initialize@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAJPEAUIInspectable@@@Z; XWinRT::detail::GitStorageType<IInspectable>::Initialize(IInspectable *)
0x180027784  mov     esi, eax
0x180027786  mov     [rbp+arg_18], eax
0x180027789  test    eax, eax
0x18002778b  js      loc_18002784D
0x180027791  lea     eax, [r13+1]
0x180027795  mov     rcx, [rbp+var_30]
0x180027799  cmp     [rcx+8], r12b
0x18002779d  cmovz   eax, r13d
0x1800277a1  mov     r13d, eax
0x1800277a4  inc     r15d
0x1800277a7  cmp     r15d, r14d
0x1800277aa  mov     rsi, [rbp+arg_10]
0x1800277ae  jb      short loc_180027763
0x1800277b0  jmp     short loc_1800277BA
0x1800277b2  xor     r15d, r15d
0x1800277b5  xor     ebx, ebx
0x1800277b7  xor     r14d, r14d
0x1800277ba  lea     rdx, [rdi+80h]
0x1800277c1  lea     r8, [rbp+arg_18]
0x1800277c5  lea     rcx, [rbp+var_30]
0x1800277c9  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800277ce  mov     esi, [rbp+arg_18]
0x1800277d1  test    esi, esi
0x1800277d3  js      short loc_18002782D
0x1800277d5  lea     r8, [rdi+0B4h]
0x1800277dc  mov     edx, [rdi+0B0h]
0x1800277e2  lea     rcx, [rbp+var_18]
0x1800277e6  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x1800277eb  mov     rdx, rax
0x1800277ee  lea     rcx, [rbp+var_28]
0x1800277f2  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x1800277f7  lea     rcx, [rbp+var_28]
0x1800277fb  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x180027800  mov     esi, eax
0x180027802  mov     r12, [rbp+var_20]
0x180027806  test    eax, eax
0x180027808  js      short loc_18002782D
0x18002780a  mov     eax, [rdi+60h]
0x18002780d  mov     [rdi+60h], r15d
0x180027811  mov     r15d, eax
0x180027814  mov     [rdi+64h], r14d
0x180027818  mov     [rdi+68h], r13d
0x18002781c  mov     rax, [rdi+70h]
0x180027820  mov     [rdi+70h], rbx
0x180027824  mov     rbx, rax
0x180027827  inc     dword ptr [rdi+90h]
0x18002782d  mov     rax, [rbp+var_30]
0x180027831  test    rax, rax
0x180027834  jz      short loc_18002784D
0x180027836  lea     rcx, [rax+8]; SRWLock
0x18002783a  cmp     dword ptr [rax], 1
0x18002783d  jnz     short loc_180027847
0x18002783f  add     dword ptr [rcx], 10000000h
0x180027845  jmp     short loc_18002784D
0x180027847  call    cs:__imp_ReleaseSRWLockExclusive
0x18002784d  test    rbx, rbx
0x180027850  jz      short loc_1800278AD
0x180027852  xor     r13d, r13d
0x180027855  test    r15d, r15d
0x180027858  jz      short loc_1800278A4
0x18002785a  xor     r12d, r12d
0x18002785d  mov     r14, r12
0x180027860  add     r14, r14
0x180027863  mov     rcx, [rbx+r14*8]; void *
0x180027867  cmp     byte ptr [rbx+r14*8+8], 0
0x18002786d  jz      short loc_180027876
0x18002786f  call    ?Release@ReferencedGitCookie@?$GitStorageType@UISettingItem@DataModel@SystemSettings@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<SystemSettings::DataModel::ISettingItem>::ReferencedGitCookie::Release(void)
0x180027874  jmp     short loc_180027887
0x180027876  test    rcx, rcx
0x180027879  jz      short loc_180027887
0x18002787b  mov     rax, [rcx]
0x18002787e  mov     rax, [rax+10h]
0x180027882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027887  mov     byte ptr [rbx+r14*8+8], 0
0x18002788d  mov     qword ptr [rbx+r14*8], 0
0x180027895  inc     r13d
0x180027898  inc     r12
0x18002789b  cmp     r13d, r15d
0x18002789e  jb      short loc_18002785D
0x1800278a0  mov     r12, [rbp+var_20]
0x1800278a4  mov     rcx, rbx; Block
0x1800278a7  call    cs:__imp_free
0x1800278ad  test    esi, esi
0x1800278af  js      short loc_1800278DE
0x1800278b1  mov     rax, rdi
0x1800278b4  lea     rcx, [rdi+10h]
0x1800278b8  neg     rax
0x1800278bb  sbb     r8, r8
0x1800278be  and     r8, rcx
0x1800278c1  lea     rdx, [rdi+98h]
0x1800278c8  mov     [rsp+60h+var_40], 0
0x1800278d0  xor     r9d, r9d
0x1800278d3  lea     rcx, [rbp+var_28]
0x1800278d7  call    ?RaiseEvent@?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x1800278dc  mov     esi, eax
0x1800278de  test    r12, r12
0x1800278e1  jz      short loc_1800278EB
0x1800278e3  mov     dword ptr [r12], 0
0x1800278eb  mov     eax, esi
0x1800278ed  mov     rbx, [rsp+60h+arg_0]
0x1800278f5  add     rsp, 60h
0x1800278f9  pop     r15
0x1800278fb  pop     r14
0x1800278fd  pop     r13
0x1800278ff  pop     r12
0x180027901  pop     rdi
0x180027902  pop     rsi
0x180027903  pop     rbp
0x180027904  retn
```
