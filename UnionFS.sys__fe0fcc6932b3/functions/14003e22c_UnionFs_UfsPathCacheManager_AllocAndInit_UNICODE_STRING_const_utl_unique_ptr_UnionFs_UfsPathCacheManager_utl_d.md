# UnionFs::UfsPathCacheManager::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsPathCacheManager,utl::default_delete<UnionFs::UfsPathCacheManager>> &,UnionFs::StackEventTracer &)

- ea: `0x14003e22c`
- end: `0x14003e4f4`
- name: `?AllocAndInit@UfsPathCacheManager@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsPathCacheManager@UnionFs@@U?$default_delete@VUfsPathCacheManager@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x14000701c`

## callees

- `0x140005574`
- `0x14003dc14`
- `0x14003dc24`
- `0x14003df70`
- `0x14003e22c`
- `0x14003eb78`
- `0x140055350`
- `0x140056c44`
- `0x140056c7c`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e491`
- `ntoskrnl!ExAllocatePool2` at `0x14003e265`
- `ntoskrnl!ExAllocatePool2` at `0x14003e265`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e2a9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e326`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e2a9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003e326`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e28e`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e30b`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e28e`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14003e30b`

## string_xrefs

- `0x14003e4a1`: `ORIGIN: Allocating UfsPathCacheManager`
- `0x14003e2de`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e420`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e4b4`: `UnionFs::UfsPathCacheManager::AllocAndInit`
- `0x14003e3a5`: `PUSH: Allocating RegistryWatcher`
- `0x14003e40f`: `PUSH: Reading initial value of trimmer threshold`
- `0x14003e3f9`: `UnionFs::UfsRegistryWatcher::InvokeCallbackNow`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCacheManager::AllocAndInit(
        __int64 a1,
        UnionFs::UfsPathCacheManager **a2,
        struct UnionFs::StackEventTracer *a3)
{
  UnionFs::UfsPathCacheManager *Pool2; // rax
  __int64 v7; // rbx
  PFLT_GENERIC_WORKITEM GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v9; // rcx
  PFLT_GENERIC_WORKITEM v10; // rdi
  const char *v11; // rax
  __int64 v12; // r8
  int v13; // edi
  PFLT_GENERIC_WORKITEM v14; // rax
  struct _FLT_GENERIC_WORKITEM *v15; // rcx
  PFLT_GENERIC_WORKITEM v16; // rdi
  __int64 v17; // rax
  const char *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  UnionFs::UfsPathCacheManager *v23; // rdi
  const char *v25; // [rsp+28h] [rbp-130h]
  _BYTE v26[120]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v27[8]; // [rsp+A8h] [rbp-B0h] BYREF
  _QWORD v28[13]; // [rsp+B0h] [rbp-A8h] BYREF
  _QWORD *v29; // [rsp+118h] [rbp-40h]

  Pool2 = (UnionFs::UfsPathCacheManager *)ExAllocatePool2(64, 416, 1835222613);
  if ( !Pool2 || (v7 = UnionFs::UfsPathCacheManager::UfsPathCacheManager(Pool2)) == 0 )
  {
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x5C900110027LL,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      "ORIGIN: Allocating UfsPathCacheManager",
      v25);
    return (unsigned int)v13;
  }
  GenericWorkItem = FltAllocateGenericWorkItem();
  v9 = *(struct _FLT_GENERIC_WORKITEM **)(v7 + 224);
  v10 = GenericWorkItem;
  if ( v9 )
    FltFreeGenericWorkItem(v9);
  *(_QWORD *)(v7 + 224) = v10;
  if ( !v10 )
  {
    v11 = "ORIGIN: Allocating RemovalWorkItem";
    v12 = 0x4330011002FLL;
LABEL_7:
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a3,
      (struct UnionFs::StackEventTracer *)v12,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      v11,
      v25);
LABEL_8:
    UnionFs::UfsPathCacheManager::~UfsPathCacheManager((UnionFs::UfsPathCacheManager *)v7);
    ExFreePoolWithTag((PVOID)v7, 0);
    return (unsigned int)v13;
  }
  v14 = FltAllocateGenericWorkItem();
  v15 = *(struct _FLT_GENERIC_WORKITEM **)(v7 + 272);
  v16 = v14;
  if ( v15 )
    FltFreeGenericWorkItem(v15);
  *(_QWORD *)(v7 + 272) = v16;
  if ( !v16 )
  {
    v11 = "ORIGIN: Allocating TrimmerWorkItem";
    v12 = 0x41500110037LL;
    goto LABEL_7;
  }
  v28[1] = v7;
  v28[0] = off_14007EA08;
  v29 = v28;
  v17 = wistd::function<void (bool)>::function<void (bool)>(v26, v27);
  v13 = UnionFs::UfsRegistryWatcher::AllocAndInit(a1, v17, (UnionFs::UfsRegistryWatcher **)(v7 + 408), a3);
  if ( v13 < 0 )
  {
    v18 = "PUSH: Allocating RegistryWatcher";
    v19 = 0x5BC00110075LL;
    goto LABEL_18;
  }
  v20 = *(_QWORD *)(v7 + 408);
  v21 = *(_QWORD *)(v20 + 160);
  if ( !v21 )
    wistd::__throw_bad_function_call(0);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct UnionFs::StackEventTracer *))(*(_QWORD *)v21 + 32LL))(
          v21,
          *(_QWORD *)(v20 + 40),
          a3);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x598001A0073LL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::InvokeCallbackNow",
      "PUSH: Invoking callback on demand",
      v25);
    v18 = "PUSH: Reading initial value of trimmer threshold";
    v19 = 0x5000011007BLL;
LABEL_18:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a3,
      (struct UnionFs::StackEventTracer *)v19,
      (unsigned __int64)"UnionFs::UfsPathCacheManager::AllocAndInit",
      v18,
      v25);
    if ( v29 )
      (*(void (__fastcall **)(_QWORD *))(*v29 + 24LL))(v29);
    goto LABEL_8;
  }
  UnionFs::UfsPathCacheManager::SetRemovalTimer((UnionFs::UfsPathCacheManager *)v7);
  v22 = v29;
  v23 = *a2;
  *a2 = (UnionFs::UfsPathCacheManager *)v7;
  if ( v22 )
    (*(void (__fastcall **)(_QWORD *))(*v22 + 24LL))(v22);
  if ( v23 )
  {
    UnionFs::UfsPathCacheManager::~UfsPathCacheManager(v23);
    ExFreePoolWithTag(v23, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14003e22c  push    rbx
0x14003e22e  push    rbp
0x14003e22f  push    rsi
0x14003e230  push    rdi
0x14003e231  push    r14
0x14003e233  sub     rsp, 130h
0x14003e23a  mov     rax, cs:__security_cookie
0x14003e241  xor     rax, rsp
0x14003e244  mov     [rsp+158h+var_38], rax
0x14003e24c  mov     rsi, r8
0x14003e24f  mov     r14, rdx
0x14003e252  mov     rbp, rcx
0x14003e255  mov     edx, 1A0h
0x14003e25a  mov     ecx, 40h ; '@'
0x14003e25f  mov     r8d, 6D634655h
0x14003e265  call    cs:__imp_ExAllocatePool2
0x14003e26c  nop     dword ptr [rax+rax+00h]
0x14003e271  test    rax, rax
0x14003e274  jz      loc_14003E4A1
0x14003e27a  mov     rcx, rax; this
0x14003e27d  call    ??0UfsPathCacheManager@UnionFs@@AEAA@XZ; UnionFs::UfsPathCacheManager::UfsPathCacheManager(void)
0x14003e282  mov     rbx, rax
0x14003e285  test    rax, rax
0x14003e288  jz      loc_14003E4A1
0x14003e28e  call    cs:__imp_FltAllocateGenericWorkItem
0x14003e295  nop     dword ptr [rax+rax+00h]
0x14003e29a  mov     rcx, [rbx+0E0h]; FltWorkItem
0x14003e2a1  mov     rdi, rax
0x14003e2a4  test    rcx, rcx
0x14003e2a7  jz      short loc_14003E2B5
0x14003e2a9  call    cs:__imp_FltFreeGenericWorkItem
0x14003e2b0  nop     dword ptr [rax+rax+00h]
0x14003e2b5  mov     [rbx+0E0h], rdi
0x14003e2bc  test    rdi, rdi
0x14003e2bf  jnz     short loc_14003E30B
0x14003e2c1  lea     rax, aOriginAllocati_83; "ORIGIN: Allocating RemovalWorkItem"
0x14003e2c8  mov     r8, 4330011002Fh; struct UnionFs::StackEventTracer *
0x14003e2d2  mov     edi, 0C000009Ah
0x14003e2d7  mov     [rsp+158h+var_138], rax; char *
0x14003e2dc  mov     ecx, edi; this
0x14003e2de  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e2e5  mov     rdx, rsi; int
0x14003e2e8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e2ed  mov     rcx, rbx; this
0x14003e2f0  call    ??1UfsPathCacheManager@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheManager::~UfsPathCacheManager(void)
0x14003e2f5  xor     edx, edx; Tag
0x14003e2f7  mov     rcx, rbx; P
0x14003e2fa  call    cs:__imp_ExFreePoolWithTag
0x14003e301  nop     dword ptr [rax+rax+00h]
0x14003e306  jmp     loc_14003E4CD
0x14003e30b  call    cs:__imp_FltAllocateGenericWorkItem
0x14003e312  nop     dword ptr [rax+rax+00h]
0x14003e317  mov     rcx, [rbx+110h]; FltWorkItem
0x14003e31e  mov     rdi, rax
0x14003e321  test    rcx, rcx
0x14003e324  jz      short loc_14003E332
0x14003e326  call    cs:__imp_FltFreeGenericWorkItem
0x14003e32d  nop     dword ptr [rax+rax+00h]
0x14003e332  mov     [rbx+110h], rdi
0x14003e339  test    rdi, rdi
0x14003e33c  jnz     short loc_14003E351
0x14003e33e  lea     rax, aOriginAllocati_26; "ORIGIN: Allocating TrimmerWorkItem"
0x14003e345  mov     r8, 41500110037h
0x14003e34f  jmp     short loc_14003E2D2
0x14003e351  lea     rax, off_14007EA08
0x14003e358  mov     [rsp+158h+var_A0], rbx
0x14003e360  mov     [rsp+158h+var_A8], rax
0x14003e368  lea     rdx, [rsp+158h+var_B0]
0x14003e370  lea     rax, [rsp+158h+var_A8]
0x14003e378  lea     rcx, [rsp+158h+var_128]
0x14003e37d  mov     [rsp+158h+var_40], rax
0x14003e385  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003e38a  lea     r8, [rbx+198h]
0x14003e391  mov     r9, rsi
0x14003e394  mov     rdx, rax
0x14003e397  mov     rcx, rbp
0x14003e39a  call    ?AllocAndInit@UfsRegistryWatcher@UnionFs@@SAJAEBU_UNICODE_STRING@@V?$function@$$A6AJAEAVUfsRegistryReader@UnionFs@@AEAVStackEventTracer@2@@Z@wistd@@AEAV?$unique_ptr@VUfsRegistryWatcher@UnionFs@@U?$default_delete@VUfsRegistryWatcher@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryWatcher::AllocAndInit(_UNICODE_STRING const &,wistd::function<long (UnionFs::UfsRegistryReader &,UnionFs::StackEventTracer &)>,utl::unique_ptr<UnionFs::UfsRegistryWatcher,utl::default_delete<UnionFs::UfsRegistryWatcher>> &,UnionFs::StackEventTracer &)
0x14003e39f  mov     edi, eax
0x14003e3a1  test    eax, eax
0x14003e3a3  jns     short loc_14003E3B8
0x14003e3a5  lea     rax, aPushAllocating_8; "PUSH: Allocating RegistryWatcher"
0x14003e3ac  mov     r8, 5BC00110075h
0x14003e3b6  jmp     short loc_14003E420
0x14003e3b8  mov     rdx, [rbx+198h]
0x14003e3bf  mov     rcx, [rdx+0A0h]; this
0x14003e3c6  test    rcx, rcx
0x14003e3c9  jz      loc_14003E4EE
0x14003e3cf  mov     rax, [rcx]
0x14003e3d2  mov     r8, rsi
0x14003e3d5  mov     rdx, [rdx+28h]
0x14003e3d9  mov     rax, [rax+20h]
0x14003e3dd  call    _guard_dispatch_icall
0x14003e3e2  mov     edi, eax
0x14003e3e4  test    eax, eax
0x14003e3e6  jns     short loc_14003E458
0x14003e3e8  lea     rax, aPushInvokingCa; "PUSH: Invoking callback on demand"
0x14003e3ef  mov     r8, 598001A0073h; struct UnionFs::StackEventTracer *
0x14003e3f9  lea     r9, aUnionfsUfsregi_4; "UnionFs::UfsRegistryWatcher::InvokeCall"...
0x14003e400  mov     [rsp+158h+var_138], rax; char *
0x14003e405  mov     rdx, rsi; int
0x14003e408  mov     ecx, edi; this
0x14003e40a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e40f  lea     rax, aPushReadingIni; "PUSH: Reading initial value of trimmer "...
0x14003e416  mov     r8, 5000011007Bh; struct UnionFs::StackEventTracer *
0x14003e420  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e427  mov     [rsp+158h+var_138], rax; char *
0x14003e42c  mov     rdx, rsi; int
0x14003e42f  mov     ecx, edi; this
0x14003e431  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e436  mov     rcx, [rsp+158h+var_40]
0x14003e43e  test    rcx, rcx
0x14003e441  jz      loc_14003E2ED
0x14003e447  mov     rax, [rcx]
0x14003e44a  mov     rax, [rax+18h]
0x14003e44e  call    _guard_dispatch_icall
0x14003e453  jmp     loc_14003E2ED
0x14003e458  mov     rcx, rbx; this
0x14003e45b  call    ?SetRemovalTimer@UfsPathCacheManager@UnionFs@@AEAAXXZ; UnionFs::UfsPathCacheManager::SetRemovalTimer(void)
0x14003e460  mov     rcx, [rsp+158h+var_40]
0x14003e468  mov     rdi, [r14]
0x14003e46b  mov     [r14], rbx
0x14003e46e  test    rcx, rcx
0x14003e471  jz      short loc_14003E47F
0x14003e473  mov     rax, [rcx]
0x14003e476  mov     rax, [rax+18h]
0x14003e47a  call    _guard_dispatch_icall
0x14003e47f  test    rdi, rdi
0x14003e482  jz      short loc_14003E49D
0x14003e484  mov     rcx, rdi; this
0x14003e487  call    ??1UfsPathCacheManager@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheManager::~UfsPathCacheManager(void)
0x14003e48c  xor     edx, edx; Tag
0x14003e48e  mov     rcx, rdi; P
0x14003e491  call    cs:__imp_ExFreePoolWithTag
0x14003e498  nop     dword ptr [rax+rax+00h]
0x14003e49d  xor     eax, eax
0x14003e49f  jmp     short loc_14003E4CF
0x14003e4a1  lea     rax, aOriginAllocati_72; "ORIGIN: Allocating UfsPathCacheManager"
0x14003e4a8  mov     edi, 0C000009Ah
0x14003e4ad  mov     ecx, edi; this
0x14003e4af  mov     [rsp+158h+var_138], rax; char *
0x14003e4b4  lea     r9, aUnionfsUfspath_56; "UnionFs::UfsPathCacheManager::AllocAndI"...
0x14003e4bb  mov     r8, 5C900110027h; struct UnionFs::StackEventTracer *
0x14003e4c5  mov     rdx, rsi; int
0x14003e4c8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e4cd  mov     eax, edi
0x14003e4cf  mov     rcx, [rsp+158h+var_38]
0x14003e4d7  xor     rcx, rsp; StackCookie
0x14003e4da  call    __security_check_cookie
0x14003e4df  add     rsp, 130h
0x14003e4e6  pop     r14
0x14003e4e8  pop     rdi
0x14003e4e9  pop     rsi
0x14003e4ea  pop     rbp
0x14003e4eb  pop     rbx
0x14003e4ec  retn
0x14003e4ee  call    ?__throw_bad_function_call@wistd@@YAXXZ; wistd::__throw_bad_function_call(void)
```
