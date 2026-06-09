# UnionFs::UfsRegistryWatcher::AllocAndInit(_UNICODE_STRING const &,wistd::function<long (UnionFs::UfsRegistryReader &,UnionFs::StackEventTracer &)>,utl::unique_ptr<UnionFs::UfsRegistryWatcher,utl::default_delete<UnionFs::UfsRegistryWatcher>> &,UnionFs::StackEventTracer &)

- ea: `0x1400551cc`
- end: `0x14005543f`
- name: `?AllocAndInit@UfsRegistryWatcher@UnionFs@@SAJAEBU_UNICODE_STRING@@V?$function@$$A6AJAEAVUfsRegistryReader@UnionFs@@AEAVStackEventTracer@2@@Z@wistd@@AEAV?$unique_ptr@VUfsRegistryWatcher@UnionFs@@U?$default_delete@VUfsRegistryWatcher@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14003e10c`

## callees

- `0x140005574`
- `0x140054c18`
- `0x1400550b8`
- `0x1400551cc`
- `0x14005563c`
- `0x140056ac4`
- `0x140056afc`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400552ea`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400552ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400552b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005534e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400553c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400552b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005534e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400553c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400551f6`
- `ntoskrnl!ExAllocatePool2` at `0x1400551f6`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055302`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055302`

## string_xrefs

- `0x1400553ea`: `ORIGIN: Allocating UfsRegistryWatcher`
- `0x140055295`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x14005532b`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x140055392`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x1400553fb`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x140055284`: `PUSH: Allocating watcher's reader`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsRegistryWatcher::AllocAndInit(
        __int64 a1,
        __int64 a2,
        UnionFs::UfsRegistryWatcher **a3,
        struct UnionFs::StackEventTracer *a4)
{
  __int64 Pool2; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rcx
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v16; // rcx
  PEX_RUNDOWN_REF_CACHE_AWARE v17; // rbx
  __int64 v18; // rcx
  void (*v19)(void); // rax
  UnionFs::UfsRegistryWatcher *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  const char *v23; // [rsp+28h] [rbp-C0h]
  _BYTE v24[184]; // [rsp+30h] [rbp-B8h] BYREF

  Pool2 = ExAllocatePool2(64, 168, 1735542357);
  if ( !Pool2 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x591001A0028LL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::AllocAndInit",
      "ORIGIN: Allocating UfsRegistryWatcher",
      v23);
    v22 = *(_QWORD *)(a2 + 112);
    if ( v22 )
    {
      v19 = *(void (**)(void))(*(_QWORD *)v22 + 24LL);
      goto LABEL_23;
    }
    return 3221225626LL;
  }
  v9 = wistd::function<void (bool)>::function<void (bool)>(v24, a2);
  *(_OWORD *)Pool2 = 0;
  v10 = v9;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_QWORD *)(Pool2 + 40) = 0;
  wistd::function<void (bool)>::function<void (bool)>(Pool2 + 48, v9);
  *(_QWORD *)(Pool2 + 24) = Pool2;
  *(_QWORD *)(Pool2 + 16) = UnionFs::UfsRegistryWatcher::ProcessChanges;
  *(_QWORD *)Pool2 = 0;
  v11 = *(_QWORD *)(v10 + 112);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
  v12 = UnionFs::UfsRegistryReader::AllocAndInit(a1, Pool2 + 40, a4);
  if ( v12 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v12,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x592001A002ELL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::AllocAndInit",
      "PUSH: Allocating watcher's reader",
      v23);
LABEL_6:
    UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher((UnionFs::UfsRegistryWatcher *)Pool2);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    v13 = *(_QWORD *)(a2 + 112);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    return (unsigned int)v12;
  }
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x67724655u);
  v16 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(Pool2 + 32);
  v17 = CacheAwareRundownProtection;
  if ( v16 )
    ExFreeCacheAwareRundownProtection(v16);
  *(_QWORD *)(Pool2 + 32) = v17;
  if ( !v17 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x593001A0037LL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::AllocAndInit",
      "ORIGIN: Allocating rundown",
      v23);
    UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher((UnionFs::UfsRegistryWatcher *)Pool2);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    v18 = *(_QWORD *)(a2 + 112);
    if ( v18 )
    {
      v19 = *(void (**)(void))(*(_QWORD *)v18 + 24LL);
LABEL_23:
      v19();
      return 3221225626LL;
    }
    return 3221225626LL;
  }
  v12 = UnionFs::UfsRegistryWatcher::RegisterForChangeNotifications((PIO_APC_ROUTINE)Pool2, a4);
  if ( v12 < 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)(unsigned int)v12,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x594001A003DLL,
      (unsigned __int64)"UnionFs::UfsRegistryWatcher::AllocAndInit",
      "ORIGIN: Registering for change notifications",
      v23);
    goto LABEL_6;
  }
  v20 = *a3;
  *a3 = (UnionFs::UfsRegistryWatcher *)Pool2;
  if ( v20 )
  {
    UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(v20);
    ExFreePoolWithTag(v20, 0);
  }
  v21 = *(_QWORD *)(a2 + 112);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
  return 0;
}

```

## disassembly

```asm
0x1400551cc  push    rbx
0x1400551ce  push    rbp
0x1400551cf  push    rsi
0x1400551d0  push    rdi
0x1400551d1  push    r14
0x1400551d3  push    r15
0x1400551d5  sub     rsp, 0B8h
0x1400551dc  mov     rbp, rdx
0x1400551df  mov     r14, r8
0x1400551e2  mov     edx, 0A8h
0x1400551e7  mov     r15, rcx
0x1400551ea  mov     r8d, 67724655h
0x1400551f0  mov     rsi, r9
0x1400551f3  lea     ecx, [rdx-68h]
0x1400551f6  call    cs:__imp_ExAllocatePool2
0x1400551fd  nop     dword ptr [rax+rax+00h]
0x140055202  mov     rdi, rax
0x140055205  test    rax, rax
0x140055208  jz      loc_1400553EA
0x14005520e  mov     rdx, rbp
0x140055211  lea     rcx, [rsp+0E8h+var_B8]
0x140055216  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14005521b  xorps   xmm0, xmm0
0x14005521e  lea     rcx, [rdi+30h]
0x140055222  movups  xmmword ptr [rdi], xmm0
0x140055225  mov     rdx, rax
0x140055228  mov     rbx, rax
0x14005522b  movups  xmmword ptr [rdi+10h], xmm0
0x14005522f  mov     qword ptr [rdi+20h], 0
0x140055237  mov     qword ptr [rdi+28h], 0
0x14005523f  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x140055244  lea     rax, ?ProcessChanges@UfsRegistryWatcher@UnionFs@@SAXPEAX@Z; UnionFs::UfsRegistryWatcher::ProcessChanges(void *)
0x14005524b  mov     [rdi+18h], rdi
0x14005524f  mov     [rdi+10h], rax
0x140055253  mov     qword ptr [rdi], 0
0x14005525a  mov     rcx, [rbx+70h]
0x14005525e  test    rcx, rcx
0x140055261  jz      short loc_14005526F
0x140055263  mov     rax, [rcx]
0x140055266  mov     rax, [rax+18h]
0x14005526a  call    _guard_dispatch_icall
0x14005526f  lea     rdx, [rdi+28h]
0x140055273  mov     r8, rsi
0x140055276  mov     rcx, r15
0x140055279  call    ?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)
0x14005527e  mov     ebx, eax
0x140055280  test    eax, eax
0x140055282  jns     short loc_1400552E0
0x140055284  lea     rax, aPushAllocating; "PUSH: Allocating watcher's reader"
0x14005528b  mov     r8, 592001A002Eh; struct UnionFs::StackEventTracer *
0x140055295  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x14005529c  mov     [rsp+0E8h+var_C8], rax; char *
0x1400552a1  mov     rdx, rsi; int
0x1400552a4  mov     ecx, ebx; this
0x1400552a6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400552ab  mov     rcx, rdi; this
0x1400552ae  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x1400552b3  xor     edx, edx; Tag
0x1400552b5  mov     rcx, rdi; P
0x1400552b8  call    cs:__imp_ExFreePoolWithTag
0x1400552bf  nop     dword ptr [rax+rax+00h]
0x1400552c4  mov     rcx, [rbp+70h]
0x1400552c8  test    rcx, rcx
0x1400552cb  jz      short loc_1400552D9
0x1400552cd  mov     rax, [rcx]
0x1400552d0  mov     rax, [rax+18h]
0x1400552d4  call    _guard_dispatch_icall
0x1400552d9  mov     eax, ebx
0x1400552db  jmp     loc_14005542E
0x1400552e0  mov     edx, 67724655h; PoolTag
0x1400552e5  mov     ecx, 200h; PoolType
0x1400552ea  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1400552f1  nop     dword ptr [rax+rax+00h]
0x1400552f6  mov     rcx, [rdi+20h]; RunRefCacheAware
0x1400552fa  mov     rbx, rax
0x1400552fd  test    rcx, rcx
0x140055300  jz      short loc_14005530E
0x140055302  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140055309  nop     dword ptr [rax+rax+00h]
0x14005530e  mov     [rdi+20h], rbx
0x140055312  mov     rdx, rsi; struct UnionFs::StackEventTracer *
0x140055315  test    rbx, rbx
0x140055318  jnz     short loc_140055373
0x14005531a  lea     rax, aOriginAllocati_75; "ORIGIN: Allocating rundown"
0x140055321  mov     r8, 593001A0037h; struct UnionFs::StackEventTracer *
0x14005532b  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x140055332  mov     [rsp+0E8h+var_C8], rax; char *
0x140055337  mov     ecx, 0C000009Ah; this
0x14005533c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140055341  mov     rcx, rdi; this
0x140055344  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x140055349  xor     edx, edx; Tag
0x14005534b  mov     rcx, rdi; P
0x14005534e  call    cs:__imp_ExFreePoolWithTag
0x140055355  nop     dword ptr [rax+rax+00h]
0x14005535a  mov     rcx, [rbp+70h]
0x14005535e  test    rcx, rcx
0x140055361  jz      loc_140055429
0x140055367  mov     rax, [rcx]
0x14005536a  mov     rax, [rax+18h]
0x14005536e  jmp     loc_140055424
0x140055373  mov     rcx, rdi; ApcRoutine
0x140055376  call    ?RegisterForChangeNotifications@UfsRegistryWatcher@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryWatcher::RegisterForChangeNotifications(UnionFs::StackEventTracer &)
0x14005537b  mov     ebx, eax
0x14005537d  test    eax, eax
0x14005537f  jns     short loc_1400553AD
0x140055381  lea     rax, aOriginRegister; "ORIGIN: Registering for change notifica"...
0x140055388  mov     r8, 594001A003Dh; struct UnionFs::StackEventTracer *
0x140055392  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x140055399  mov     [rsp+0E8h+var_C8], rax; char *
0x14005539e  mov     rdx, rsi; int
0x1400553a1  mov     ecx, ebx; this
0x1400553a3  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400553a8  jmp     loc_1400552AB
0x1400553ad  mov     rbx, [r14]
0x1400553b0  mov     [r14], rdi
0x1400553b3  test    rbx, rbx
0x1400553b6  jz      short loc_1400553D1
0x1400553b8  mov     rcx, rbx; this
0x1400553bb  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x1400553c0  xor     edx, edx; Tag
0x1400553c2  mov     rcx, rbx; P
0x1400553c5  call    cs:__imp_ExFreePoolWithTag
0x1400553cc  nop     dword ptr [rax+rax+00h]
0x1400553d1  mov     rcx, [rbp+70h]
0x1400553d5  test    rcx, rcx
0x1400553d8  jz      short loc_1400553E6
0x1400553da  mov     rax, [rcx]
0x1400553dd  mov     rax, [rax+18h]
0x1400553e1  call    _guard_dispatch_icall
0x1400553e6  xor     eax, eax
0x1400553e8  jmp     short loc_14005542E
0x1400553ea  lea     rax, aOriginAllocati_65; "ORIGIN: Allocating UfsRegistryWatcher"
0x1400553f1  mov     r8, 591001A0028h; struct UnionFs::StackEventTracer *
0x1400553fb  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x140055402  mov     [rsp+0E8h+var_C8], rax; char *
0x140055407  mov     rdx, rsi; int
0x14005540a  mov     ecx, 0C000009Ah; this
0x14005540f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140055414  mov     rcx, [rbp+70h]
0x140055418  test    rcx, rcx
0x14005541b  jz      short loc_140055429
0x14005541d  mov     rdx, [rcx]
0x140055420  mov     rax, [rdx+18h]
0x140055424  call    _guard_dispatch_icall
0x140055429  mov     eax, 0C000009Ah
0x14005542e  add     rsp, 0B8h
0x140055435  pop     r15
0x140055437  pop     r14
0x140055439  pop     rdi
0x14005543a  pop     rsi
0x14005543b  pop     rbp
0x14005543c  pop     rbx
0x14005543d  retn
```
