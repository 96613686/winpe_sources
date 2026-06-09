# PCPKspFreeKey

- ea: `0x18001cf60`
- end: `0x18001d0fe`
- name: `PCPKspFreeKey`
- size: `414`
- prototype: `__int64 __fastcall(struct PCPStorageProvider *, struct PCPStorageProviderKey *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1800133c4`
- `0x18001b8f0`
- `0x18001cf60`
- `0x18001e100`
- `0x18001edb0`
- `0x18001f0f0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f294`
- `0x18001f2c0`
- `0x18001f2f0`
- `0x18001fba8`
- `0x1800764d0`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d04c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d04c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PCPKspFreeKey(struct PCPStorageProvider *a1, struct PCPStorageProviderKey *a2)
{
  int v5; // eax
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v8; // edi
  int v9; // [rsp+20h] [rbp-178h]
  _QWORD v10[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v10);
  v10[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  KspDebugProvider::KspDebugActivity::StartActivity((KspDebugProvider::KspDebugActivity *)v10, "PCPKspFreeKey");
  KspTransactionLogging::TransactionHandleOnly(L"PCPKspFreeKey", a1, a2);
  if ( !a1 || !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x478,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      v9);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v10);
    return 2148073510LL;
  }
  v5 = PCPStorageProvider::ValidateObject(a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v5,
      v9);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v10);
    return v6;
  }
  else
  {
    if ( a2 == (struct PCPStorageProviderKey *)4294967281LL )
    {
LABEL_10:
      KspDebugProvider::KspDebugActivity::Stop((KspDebugProvider::KspDebugActivity *)v10, "PCPKspFreeKey");
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v10);
      return 0;
    }
    v7 = PCPStorageProviderKey::ValidateObject(a2);
    v8 = v7;
    if ( v7 >= 0 )
    {
      PCPStorageProviderKey::LockProvider(a2);
      PCPStorageProviderKey::UnLockProvider(a2);
      PCPStorageProviderKey::Teardown(a2);
      if ( (*((_DWORD *)a2 + 1) & 1) == 0 )
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 8));
      operator delete(a2, (const struct std::nothrow_t *)0x318);
      goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47F,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v7,
      v9);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v10);
    return v8;
  }
}

```

## disassembly

```asm
0x18001cf60  mov     [rsp+arg_10], rbx
0x18001cf65  push    rdi
0x18001cf66  sub     rsp, 190h
0x18001cf6d  mov     rax, cs:__security_cookie
0x18001cf74  xor     rax, rsp
0x18001cf77  mov     [rsp+198h+var_18], rax
0x18001cf7f  mov     rbx, rdx
0x18001cf82  mov     rdi, rcx
0x18001cf85  lea     rcx, [rsp+198h+var_168]
0x18001cf8a  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001cf8f  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x18001cf96  mov     [rsp+198h+var_168], rax
0x18001cf9b  lea     rdx, aPcpkspfreekey_0; "PCPKspFreeKey"
0x18001cfa2  lea     rcx, [rsp+198h+var_168]; this
0x18001cfa7  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x18001cfac  nop
0x18001cfad  mov     r8, rbx; struct PCPStorageProviderKey *
0x18001cfb0  mov     rdx, rdi; struct PCPStorageProvider *
0x18001cfb3  lea     rcx, aPcpkspfreekey; "PCPKspFreeKey"
0x18001cfba  call    ?TransactionHandleOnly@KspTransactionLogging@@SAXPEBGPEBVPCPStorageProvider@@PEBVPCPStorageProviderKey@@@Z; KspTransactionLogging::TransactionHandleOnly(ushort const *,PCPStorageProvider const *,PCPStorageProviderKey const *)
0x18001cfbf  test    rdi, rdi
0x18001cfc2  jnz     short loc_18001CFF6
0x18001cfc4  mov     rcx, [rsp+198h]; this
0x18001cfcc  mov     ebx, 80090026h
0x18001cfd1  mov     r9d, ebx; char *
0x18001cfd4  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001cfdb  mov     edx, 478h; void *
0x18001cfe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfe5  lea     rcx, [rsp+198h+var_168]; this
0x18001cfea  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001cfef  mov     eax, ebx
0x18001cff1  jmp     loc_18001D082
0x18001cff6  test    rbx, rbx
0x18001cff9  jz      short loc_18001CFC4
0x18001cffb  mov     rcx, rdi; this
0x18001cffe  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x18001d003  mov     edi, eax
0x18001d005  test    eax, eax
0x18001d007  js      loc_18001D0A4
0x18001d00d  mov     eax, 0FFFFFFF1h
0x18001d012  cmp     rbx, rax
0x18001d015  jz      short loc_18001D065
0x18001d017  mov     rcx, rbx; this
0x18001d01a  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x18001d01f  mov     edi, eax
0x18001d021  test    eax, eax
0x18001d023  js      loc_18001D0CE
0x18001d029  mov     rcx, rbx; this
0x18001d02c  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x18001d031  mov     rcx, rbx; this
0x18001d034  call    ?UnLockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::UnLockProvider(void)
0x18001d039  mov     rcx, rbx; this
0x18001d03c  call    ?Teardown@PCPStorageProviderKey@@QEAAJXZ; PCPStorageProviderKey::Teardown(void)
0x18001d041  mov     eax, [rbx+4]
0x18001d044  test    al, 1
0x18001d046  jnz     short loc_18001D058
0x18001d048  lea     rcx, [rbx+8]; lpCriticalSection
0x18001d04c  call    cs:__imp_DeleteCriticalSection
0x18001d053  nop     dword ptr [rax+rax+00h]
0x18001d058  mov     edx, 318h; struct std::nothrow_t *
0x18001d05d  mov     rcx, rbx; void *
0x18001d060  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d065  lea     rdx, aPcpkspfreekey_0; "PCPKspFreeKey"
0x18001d06c  lea     rcx, [rsp+198h+var_168]; this
0x18001d071  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x18001d076  lea     rcx, [rsp+198h+var_168]; this
0x18001d07b  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d080  xor     eax, eax
0x18001d082  mov     rcx, [rsp+198h+var_18]
0x18001d08a  xor     rcx, rsp; StackCookie
0x18001d08d  call    __security_check_cookie
0x18001d092  mov     rbx, [rsp+198h+arg_10]
0x18001d09a  add     rsp, 190h
0x18001d0a1  pop     rdi
0x18001d0a2  retn
0x18001d0a4  mov     rcx, [rsp+198h]; this
0x18001d0ac  mov     r9d, edi; char *
0x18001d0af  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001d0b6  mov     edx, 47Bh; void *
0x18001d0bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0c0  lea     rcx, [rsp+198h+var_168]; this
0x18001d0c5  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d0ca  mov     eax, edi
0x18001d0cc  jmp     short loc_18001D082
0x18001d0ce  mov     rcx, [rsp+198h]; this
0x18001d0d6  mov     r9d, edi; char *
0x18001d0d9  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001d0e0  mov     edx, 47Fh; void *
0x18001d0e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0ea  lea     rcx, [rsp+198h+var_168]; this
0x18001d0ef  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001d0f4  mov     eax, edi
0x18001d0f6  jmp     short loc_18001D082
0x18001d0f8  mov     eax, [rsp+198h+var_178]
0x18001d0fc  jmp     short loc_18001D082
```
