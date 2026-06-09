# PCPKspDeleteKey

- ea: `0x180059ea0`
- end: `0x18005a1e9`
- name: `PCPKspDeleteKey`
- size: `841`
- prototype: `__int64 __fastcall(struct PCPStorageProvider *, struct PCPStorageProviderKey *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1800133c4`
- `0x18001b8ac`
- `0x18001c308`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001edb0`
- `0x18001efe4`
- `0x18001f0f0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f294`
- `0x18001f2c0`
- `0x18001fba8`
- `0x1800388a0`
- `0x180059ea0`
- `0x1800764d0`
- `0x18007ee74`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180059f24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180059f24`

## string_xrefs

- `0x180059ee4`: `PCPKspDeleteKey`
- `0x18005a152`: `PCPKspDeleteKey`
- `0x180059f15`: `PCPKspDeleteKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PCPKspDeleteKey(struct PCPStorageProvider *a1, struct PCPStorageProviderKey *a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  PCPStorageProviderKey *v12; // rcx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  int v17; // [rsp+20h] [rbp-1D8h] BYREF
  int v18; // [rsp+28h] [rbp-1D0h] BYREF
  PCPStorageProviderKey *v19; // [rsp+30h] [rbp-1C8h] BYREF
  PCPStorageProvider *v20; // [rsp+38h] [rbp-1C0h] BYREF
  _QWORD v21[7]; // [rsp+40h] [rbp-1B8h] BYREF
  DWORD TickCount; // [rsp+78h] [rbp-180h]
  char v23; // [rsp+7Ch] [rbp-17Ch]
  _QWORD v24[42]; // [rsp+80h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v18 = a3;
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v24);
  v24[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  KspDebugProvider::KspDebugActivity::StartActivity((KspDebugProvider::KspDebugActivity *)v24, "PCPKspDeleteKey");
  v17 = 0;
  v20 = a1;
  v19 = 0;
  KspTransactionLogging::TransactionHandleOnly(L"PCPKspDeleteKey", a1, a2);
  v21[0] = L"PCPKspDeleteKey";
  v21[1] = &v20;
  v21[2] = &v19;
  v21[3] = 0;
  v21[4] = &v17;
  v21[5] = &v18;
  v21[6] = 0;
  TickCount = GetTickCount();
  v23 = 0;
  if ( a1 && a2 )
  {
    if ( v18 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x433,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090009LL,
        -2146893815);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
      return 2148073481LL;
    }
    v6 = PCPStorageProvider::ValidateObject(v20);
    v7 = v6;
    v17 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x436,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v6,
        v17);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
      return v7;
    }
    v19 = a2;
    v8 = ValidateProviderKeyHandle(a2);
    v9 = v8;
    v17 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x439,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v8,
        v17);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
      return v9;
    }
    v10 = PCPStorageProviderKey::ValidateObject(v19);
    v11 = v10;
    v17 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43A,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v10,
        v17);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
      return v11;
    }
    PCPStorageProviderKey::LockProvider(v19);
    PCPStorageProviderKey::UnLockProvider(v19);
    v12 = v19;
    if ( *((_QWORD *)v19 + 10) && *((_BYTE *)v19 + 708) )
    {
      v13 = PCPStorageProviderKey::DeleteKey((const WCHAR *)v19);
      v14 = SecurityStatusFromHResult(v13);
      v15 = v14;
      v17 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x444,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)v14,
          v17);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
        return v15;
      }
      v12 = v19;
    }
    if ( v12 )
    {
      PCPStorageProviderKey::`scalar deleting destructor'(v12);
      v19 = 0;
    }
    KspDebugProvider::KspDebugActivity::StopWithResult<char const (&)[21]>((KspDebugProvider::KspDebugActivity *)v24);
    v16 = v17;
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
    return v16;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x430,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      -2146893786);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v21);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v24);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x180059ea0  push    rbx
0x180059ea2  push    rsi
0x180059ea3  push    rdi
0x180059ea4  sub     rsp, 1E0h
0x180059eab  mov     rax, cs:__security_cookie
0x180059eb2  xor     rax, rsp
0x180059eb5  mov     [rsp+1F8h+var_28], rax
0x180059ebd  mov     rdi, rdx
0x180059ec0  mov     rbx, rcx
0x180059ec3  mov     [rsp+1F8h+var_1D0], r8d
0x180059ec8  lea     rcx, [rsp+1F8h+var_178]
0x180059ed0  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180059ed5  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x180059edc  mov     [rsp+1F8h+var_178], rax
0x180059ee4  lea     rdx, aPcpkspdeleteke_0; "PCPKspDeleteKey"
0x180059eeb  lea     rcx, [rsp+1F8h+var_178]; this
0x180059ef3  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x180059ef8  nop
0x180059ef9  mov     [rsp+1F8h+var_1D8], 0
0x180059f01  mov     [rsp+1F8h+var_1C0], rbx
0x180059f06  mov     [rsp+1F8h+var_1C8], 0
0x180059f0f  mov     r8, rdi; struct PCPStorageProviderKey *
0x180059f12  mov     rdx, rbx; struct PCPStorageProvider *
0x180059f15  lea     rsi, aPcpkspdeleteke; "PCPKspDeleteKey"
0x180059f1c  mov     rcx, rsi; unsigned __int16 *
0x180059f1f  call    ?TransactionHandleOnly@KspTransactionLogging@@SAXPEBGPEBVPCPStorageProvider@@PEBVPCPStorageProviderKey@@@Z; KspTransactionLogging::TransactionHandleOnly(ushort const *,PCPStorageProvider const *,PCPStorageProviderKey const *)
0x180059f24  call    cs:__imp_GetTickCount
0x180059f2b  nop     dword ptr [rax+rax+00h]
0x180059f30  mov     [rsp+1F8h+var_1B8], rsi
0x180059f35  lea     rcx, [rsp+1F8h+var_1C0]
0x180059f3a  mov     [rsp+1F8h+var_1B0], rcx
0x180059f3f  lea     rcx, [rsp+1F8h+var_1C8]
0x180059f44  mov     [rsp+1F8h+var_1A8], rcx
0x180059f49  mov     [rsp+1F8h+var_1A0], 0
0x180059f52  lea     rcx, [rsp+1F8h+var_1D8]
0x180059f57  mov     [rsp+1F8h+var_198], rcx
0x180059f5c  lea     rcx, [rsp+1F8h+var_1D0]
0x180059f61  mov     [rsp+1F8h+var_190], rcx
0x180059f66  mov     [rsp+1F8h+var_188], 0
0x180059f6f  mov     [rsp+1F8h+var_180], eax
0x180059f73  mov     [rsp+1F8h+var_17C], 0
0x180059f78  test    rbx, rbx
0x180059f7b  jz      loc_18005A189
0x180059f81  test    rdi, rdi
0x180059f84  jz      loc_18005A189
0x180059f8a  cmp     [rsp+1F8h+var_1D0], 0
0x180059f8f  jz      short loc_180059FD4
0x180059f91  mov     ebx, 80090009h
0x180059f96  mov     [rsp+1F8h+var_1D8], ebx; int
0x180059f9a  mov     rcx, [rsp+1F8h]; this
0x180059fa2  mov     r9d, ebx; char *
0x180059fa5  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180059fac  mov     edx, 433h; void *
0x180059fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059fb6  lea     rcx, [rsp+1F8h+var_1B8]; this
0x180059fbb  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180059fc0  lea     rcx, [rsp+1F8h+var_178]; this
0x180059fc8  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180059fcd  mov     eax, ebx
0x180059fcf  jmp     loc_18005A1CD
0x180059fd4  mov     rcx, [rsp+1F8h+var_1C0]; this
0x180059fd9  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x180059fde  mov     ebx, eax
0x180059fe0  mov     [rsp+1F8h+var_1D8], eax; int
0x180059fe4  test    eax, eax
0x180059fe6  jns     short loc_18005A022
0x180059fe8  mov     rcx, [rsp+1F8h]; this
0x180059ff0  mov     r9d, eax; char *
0x180059ff3  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180059ffa  mov     edx, 436h; void *
0x180059fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a004  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a009  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a00e  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a016  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a01b  mov     eax, ebx
0x18005a01d  jmp     loc_18005A1CD
0x18005a022  mov     [rsp+1F8h+var_1C8], rdi
0x18005a027  mov     rcx, rdi; struct PCPStorageProviderKey *
0x18005a02a  call    ?ValidateProviderKeyHandle@@YAJPEBVPCPStorageProviderKey@@@Z; ValidateProviderKeyHandle(PCPStorageProviderKey const *)
0x18005a02f  mov     ebx, eax
0x18005a031  mov     [rsp+1F8h+var_1D8], eax; int
0x18005a035  test    eax, eax
0x18005a037  jns     short loc_18005A073
0x18005a039  mov     rcx, [rsp+1F8h]; this
0x18005a041  mov     r9d, eax; char *
0x18005a044  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a04b  mov     edx, 439h; void *
0x18005a050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a055  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a05a  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a05f  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a067  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a06c  mov     eax, ebx
0x18005a06e  jmp     loc_18005A1CD
0x18005a073  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18005a078  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x18005a07d  mov     ebx, eax
0x18005a07f  mov     [rsp+1F8h+var_1D8], eax; int
0x18005a083  test    eax, eax
0x18005a085  jns     short loc_18005A0C1
0x18005a087  mov     rcx, [rsp+1F8h]; this
0x18005a08f  mov     r9d, eax; char *
0x18005a092  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a099  mov     edx, 43Ah; void *
0x18005a09e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a0a3  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a0a8  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a0ad  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a0b5  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a0ba  mov     eax, ebx
0x18005a0bc  jmp     loc_18005A1CD
0x18005a0c1  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18005a0c6  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x18005a0cb  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18005a0d0  call    ?UnLockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::UnLockProvider(void)
0x18005a0d5  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18005a0da  cmp     qword ptr [rcx+50h], 0
0x18005a0df  jz      short loc_18005A13F
0x18005a0e1  cmp     byte ptr [rcx+2C4h], 0
0x18005a0e8  jz      short loc_18005A13F
0x18005a0ea  call    ?DeleteKey@PCPStorageProviderKey@@QEAAJK@Z; PCPStorageProviderKey::DeleteKey(ulong)
0x18005a0ef  mov     ecx, eax; int
0x18005a0f1  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18005a0f6  mov     ebx, eax
0x18005a0f8  mov     [rsp+1F8h+var_1D8], eax; int
0x18005a0fc  test    eax, eax
0x18005a0fe  jns     short loc_18005A13A
0x18005a100  mov     rcx, [rsp+1F8h]; this
0x18005a108  mov     r9d, eax; char *
0x18005a10b  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a112  mov     edx, 444h; void *
0x18005a117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a11c  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a121  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a126  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a12e  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a133  mov     eax, ebx
0x18005a135  jmp     loc_18005A1CD
0x18005a13a  mov     rcx, [rsp+1F8h+var_1C8]; this
0x18005a13f  test    rcx, rcx
0x18005a142  jz      short loc_18005A152
0x18005a144  call    ??_GPCPStorageProviderKey@@QEAAPEAXI@Z; PCPStorageProviderKey::`scalar deleting destructor'(uint)
0x18005a149  mov     [rsp+1F8h+var_1C8], 0
0x18005a152  lea     r8, aPcpkspdeleteke_0; "PCPKspDeleteKey"
0x18005a159  mov     edx, [rsp+1F8h+var_1D8]
0x18005a15d  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a165  call    ??$StopWithResult@AEAY0BF@$$CBD@KspDebugActivity@KspDebugProvider@@QEAAXJAEAY0BF@$$CBD@Z; KspDebugProvider::KspDebugActivity::StopWithResult<char const (&)[21]>(long,char const (&)[21])
0x18005a16a  mov     ebx, [rsp+1F8h+var_1D8]
0x18005a16e  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a173  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a178  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a180  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a185  mov     eax, ebx
0x18005a187  jmp     short loc_18005A1CD
0x18005a189  mov     ebx, 80090026h
0x18005a18e  mov     [rsp+1F8h+var_1D8], ebx; int
0x18005a192  mov     rcx, [rsp+1F8h]; this
0x18005a19a  mov     r9d, ebx; char *
0x18005a19d  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a1a4  mov     edx, 430h; void *
0x18005a1a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a1ae  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18005a1b3  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18005a1b8  lea     rcx, [rsp+1F8h+var_178]; this
0x18005a1c0  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005a1c5  mov     eax, ebx
0x18005a1c7  jmp     short loc_18005A1CD
0x18005a1c9  mov     eax, [rsp+1F8h+var_1D0]
0x18005a1cd  mov     rcx, [rsp+1F8h+var_28]
0x18005a1d5  xor     rcx, rsp; StackCookie
0x18005a1d8  call    __security_check_cookie
0x18005a1dd  add     rsp, 1E0h
0x18005a1e4  pop     rdi
0x18005a1e5  pop     rsi
0x18005a1e6  pop     rbx
0x18005a1e7  retn
```
