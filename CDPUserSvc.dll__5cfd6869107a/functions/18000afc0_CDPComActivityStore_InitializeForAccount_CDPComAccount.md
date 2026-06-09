# CDPComActivityStore::InitializeForAccount(CDPComAccount *)

- ea: `0x18000afc0`
- end: `0x18000b0f4`
- name: `?InitializeForAccount@CDPComActivityStore@@UEAAJPEAUCDPComAccount@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(CDPComActivityStore *__hidden this, struct CDPComAccount *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003678`
- `0x18000a2c0`
- `0x18000afc0`
- `0x18000b328`
- `0x180023b70`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b020`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b020`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b057`
- `cdp!CDPCreateAccountInternalForUser` at `0x18000b00b`
- `cdp!CDPCreateAccountInternalForUser` at `0x18000b00b`
- `cdp!CDPGetActivityStoreForAccountInternal` at `0x18000b03e`
- `cdp!CDPGetActivityStoreForAccountInternal` at `0x18000b03e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComActivityStore::InitializeForAccount(
        RTL_SRWLOCK *this,
        struct CDPComAccount *a2,
        __int64 a3,
        __int64 a4)
{
  int CurrentUserContextToken; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  RTL_SRWLOCK *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+28h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v18 = -2147024809;
    v19 = 34;
LABEL_10:
    Log<long &,char const (&)[27],int>((__int64)this, (__int64)a2, &v18, a4, &v19);
    return v18;
  }
  CurrentUserContextToken = cdp::GetCurrentUserContextToken((cdp *)&v16, (unsigned __int64 *)a2);
  if ( CurrentUserContextToken < 0 )
  {
    v18 = CurrentUserContextToken;
    v19 = 37;
    goto LABEL_10;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v7 = CDPCreateAccountInternalForUser(*(_QWORD *)a2, *((unsigned __int16 *)a2 + 4), v16, &v20);
  if ( v7 < 0 )
  {
    v18 = v7;
    v19 = 40;
    Log<long &,char const (&)[27],int>(v9, v8, &v18, v10, &v19);
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v18;
  }
  v11 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  v17[1] = this + 2;
  v17[0] = 0;
  v12 = CDPGetActivityStoreForAccountInternal(v20, v17);
  cdp::detail::address_of<ICDPActivityStore>::~address_of<ICDPActivityStore>(v17);
  if ( v11 )
    ReleaseSRWLockExclusive(v11);
  v13 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x18000afc0  push    rbp
0x18000afc2  push    rbx
0x18000afc3  push    rdi
0x18000afc4  mov     rbp, rsp
0x18000afc7  sub     rsp, 50h
0x18000afcb  mov     rbx, rdx
0x18000afce  mov     rdi, rcx
0x18000afd1  test    rdx, rdx
0x18000afd4  jz      loc_18000B086
0x18000afda  lea     rcx, [rbp+var_20]; this
0x18000afde  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x18000afe3  test    eax, eax
0x18000afe5  js      loc_18000B0E8
0x18000afeb  mov     [rbp+arg_18], 0
0x18000aff3  lea     rcx, [rbp+arg_18]
0x18000aff7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000affc  lea     r9, [rbp+arg_18]
0x18000b000  mov     r8, [rbp+var_20]
0x18000b004  movzx   edx, word ptr [rbx+8]
0x18000b008  mov     rcx, [rbx]
0x18000b00b  call    cs:__imp_CDPCreateAccountInternalForUser
0x18000b011  test    eax, eax
0x18000b013  js      loc_18000B0AB
0x18000b019  lea     rbx, [rdi+20h]
0x18000b01d  mov     rcx, rbx; SRWLock
0x18000b020  call    cs:__imp_AcquireSRWLockExclusive
0x18000b026  lea     rax, [rdi+10h]
0x18000b02a  mov     [rbp+var_10], rax
0x18000b02e  mov     [rbp+var_18], 0
0x18000b036  lea     rdx, [rbp+var_18]
0x18000b03a  mov     rcx, [rbp+arg_18]
0x18000b03e  call    cs:__imp_CDPGetActivityStoreForAccountInternal
0x18000b044  mov     edi, eax
0x18000b046  lea     rcx, [rbp+var_18]
0x18000b04a  call    ??1?$address_of@VICDPActivityStore@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityStore>::~address_of<ICDPActivityStore>(void)
0x18000b04f  test    rbx, rbx
0x18000b052  jz      short loc_18000B05E
0x18000b054  mov     rcx, rbx; SRWLock
0x18000b057  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b05d  nop
0x18000b05e  mov     rcx, [rbp+arg_18]
0x18000b062  test    rcx, rcx
0x18000b065  jz      short loc_18000B07C
0x18000b067  mov     [rbp+arg_18], 0
0x18000b06f  mov     rax, [rcx]
0x18000b072  mov     rax, [rax+10h]
0x18000b076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b07b  nop
0x18000b07c  mov     eax, edi
0x18000b07e  add     rsp, 50h
0x18000b082  pop     rdi
0x18000b083  pop     rbx
0x18000b084  pop     rbp
0x18000b085  retn
0x18000b086  mov     [rbp+arg_8], 80070057h
0x18000b08d  mov     [rbp+arg_10], 22h ; '"'
0x18000b094  lea     rax, [rbp+arg_10]
0x18000b098  mov     [rsp+50h+var_30], rax
0x18000b09d  lea     r8, [rbp+arg_8]
0x18000b0a1  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18000b0a6  mov     eax, [rbp+arg_8]
0x18000b0a9  jmp     short loc_18000B07E
0x18000b0ab  mov     [rbp+arg_8], eax
0x18000b0ae  mov     [rbp+arg_10], 28h ; '('
0x18000b0b5  lea     rax, [rbp+arg_10]
0x18000b0b9  mov     [rsp+50h+var_30], rax
0x18000b0be  lea     r8, [rbp+arg_8]
0x18000b0c2  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18000b0c7  nop
0x18000b0c8  mov     rcx, [rbp+arg_18]
0x18000b0cc  test    rcx, rcx
0x18000b0cf  jz      short loc_18000B0E6
0x18000b0d1  mov     [rbp+arg_18], 0
0x18000b0d9  mov     rdx, [rcx]
0x18000b0dc  mov     rax, [rdx+10h]
0x18000b0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e5  nop
0x18000b0e6  jmp     short loc_18000B0A6
0x18000b0e8  mov     [rbp+arg_8], eax
0x18000b0eb  mov     [rbp+arg_10], 25h ; '%'
0x18000b0f2  jmp     short loc_18000B094
```
