# PCPKspFreeProvider

- ea: `0x18001fa10`
- end: `0x18001fba1`
- name: `PCPKspFreeProvider`
- size: `401`
- prototype: `__int64 __fastcall(struct PCPStorageProvider *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x1800133c4`
- `0x18001e100`
- `0x18001edb0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f2f0`
- `0x18001fa10`
- `0x18001fba8`
- `0x18001fed4`
- `0x1800764d0`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fadd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fadd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PCPKspFreeProvider(struct PCPStorageProvider *a1)
{
  int v2; // eax
  unsigned int v3; // edi
  int v5; // [rsp+20h] [rbp-178h]
  _QWORD v6[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v6);
  v6[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  KspDebugProvider::KspDebugActivity::StartActivity((KspDebugProvider::KspDebugActivity *)v6, "PCPKspFreeProvider");
  KspTransactionLogging::TransactionHandleOnly(L"PCPKspFreeProvider", a1, 0);
  if ( a1 )
  {
    v2 = PCPStorageProvider::ValidateObject(a1);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v2,
        v5);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v6);
      return v3;
    }
    else
    {
      if ( (*((_DWORD *)a1 + 3) & 1) == 0 )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
      if ( (*((_DWORD *)a1 + 3) & 1) == 0 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
      *(_QWORD *)a1 = &PCPStorageProvider::`vftable';
      PCPStorageProvider::Teardown(a1);
      *(_QWORD *)a1 = &TpmObject::`vftable';
      if ( (*((_DWORD *)a1 + 3) & 1) == 0 )
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
      *(_QWORD *)a1 = &ObjectWithProperties::`vftable';
      operator delete(a1, (const struct std::nothrow_t *)0xC8);
      KspDebugProvider::KspDebugActivity::Stop((KspDebugProvider::KspDebugActivity *)v6, "PCPKspFreeProvider");
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v6);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45A,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      v5);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v6);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x18001fa10  mov     [rsp+arg_8], rbx
0x18001fa15  push    rdi
0x18001fa16  sub     rsp, 190h
0x18001fa1d  mov     rax, cs:__security_cookie
0x18001fa24  xor     rax, rsp
0x18001fa27  mov     [rsp+198h+var_18], rax
0x18001fa2f  mov     rbx, rcx
0x18001fa32  lea     rcx, [rsp+198h+var_168]
0x18001fa37  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fa3c  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x18001fa43  mov     [rsp+198h+var_168], rax
0x18001fa48  lea     rdx, aPcpkspfreeprov_0; "PCPKspFreeProvider"
0x18001fa4f  lea     rcx, [rsp+198h+var_168]; this
0x18001fa54  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x18001fa59  nop
0x18001fa5a  xor     r8d, r8d; struct PCPStorageProviderKey *
0x18001fa5d  mov     rdx, rbx; struct PCPStorageProvider *
0x18001fa60  lea     rcx, aPcpkspfreeprov; "PCPKspFreeProvider"
0x18001fa67  call    ?TransactionHandleOnly@KspTransactionLogging@@SAXPEBGPEBVPCPStorageProvider@@PEBVPCPStorageProviderKey@@@Z; KspTransactionLogging::TransactionHandleOnly(ushort const *,PCPStorageProvider const *,PCPStorageProviderKey const *)
0x18001fa6c  test    rbx, rbx
0x18001fa6f  jz      loc_18001FB69
0x18001fa75  mov     rcx, rbx; this
0x18001fa78  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x18001fa7d  mov     edi, eax
0x18001fa7f  test    eax, eax
0x18001fa81  js      loc_18001FB3F
0x18001fa87  lea     rdi, [rbx+10h]
0x18001fa8b  mov     eax, [rbx+0Ch]
0x18001fa8e  test    al, 1
0x18001fa90  jnz     short loc_18001FAA1
0x18001fa92  mov     rcx, rdi; lpCriticalSection
0x18001fa95  call    cs:__imp_EnterCriticalSection
0x18001fa9c  nop     dword ptr [rax+rax+00h]
0x18001faa1  mov     eax, [rbx+0Ch]
0x18001faa4  test    al, 1
0x18001faa6  jnz     short loc_18001FAB7
0x18001faa8  mov     rcx, rdi; lpCriticalSection
0x18001faab  call    cs:__imp_LeaveCriticalSection
0x18001fab2  nop     dword ptr [rax+rax+00h]
0x18001fab7  lea     rax, ??_7PCPStorageProvider@@6B@; const PCPStorageProvider::`vftable'
0x18001fabe  mov     [rbx], rax
0x18001fac1  mov     rcx, rbx; this
0x18001fac4  call    ?Teardown@PCPStorageProvider@@QEAAJXZ; PCPStorageProvider::Teardown(void)
0x18001fac9  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x18001fad0  mov     [rbx], rax
0x18001fad3  mov     eax, [rbx+0Ch]
0x18001fad6  test    al, 1
0x18001fad8  jnz     short loc_18001FAE9
0x18001fada  mov     rcx, rdi; lpCriticalSection
0x18001fadd  call    cs:__imp_DeleteCriticalSection
0x18001fae4  nop     dword ptr [rax+rax+00h]
0x18001fae9  lea     rax, ??_7ObjectWithProperties@@6B@; const ObjectWithProperties::`vftable'
0x18001faf0  mov     [rbx], rax
0x18001faf3  mov     edx, 0C8h; struct std::nothrow_t *
0x18001faf8  mov     rcx, rbx; void *
0x18001fafb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fb00  lea     rdx, aPcpkspfreeprov_0; "PCPKspFreeProvider"
0x18001fb07  lea     rcx, [rsp+198h+var_168]; this
0x18001fb0c  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x18001fb11  lea     rcx, [rsp+198h+var_168]; this
0x18001fb16  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001fb1b  xor     eax, eax
0x18001fb1d  mov     rcx, [rsp+198h+var_18]
0x18001fb25  xor     rcx, rsp; StackCookie
0x18001fb28  call    __security_check_cookie
0x18001fb2d  mov     rbx, [rsp+198h+arg_8]
0x18001fb35  add     rsp, 190h
0x18001fb3c  pop     rdi
0x18001fb3d  retn
0x18001fb3f  mov     rcx, [rsp+198h]; this
0x18001fb47  mov     r9d, edi; char *
0x18001fb4a  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001fb51  mov     edx, 45Dh; void *
0x18001fb56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb5b  lea     rcx, [rsp+198h+var_168]; this
0x18001fb60  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001fb65  mov     eax, edi
0x18001fb67  jmp     short loc_18001FB1D
0x18001fb69  mov     rcx, [rsp+198h]; this
0x18001fb71  mov     ebx, 80090026h
0x18001fb76  mov     r9d, ebx; char *
0x18001fb79  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001fb80  mov     edx, 45Ah; void *
0x18001fb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb8a  lea     rcx, [rsp+198h+var_168]; this
0x18001fb8f  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18001fb94  mov     eax, ebx
0x18001fb96  jmp     short loc_18001FB1D
0x18001fb98  mov     eax, [rsp+198h+var_178]
0x18001fb9c  jmp     loc_18001FB1D
```
