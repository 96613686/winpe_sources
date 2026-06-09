# UnionFs::UfsRegistryWatcher::AllocAndInit(_UNICODE_STRING const &,wistd::function<long (UnionFs::UfsRegistryReader &,UnionFs::StackEventTracer &)>,utl::unique_ptr<UnionFs::UfsRegistryWatcher,utl::default_delete<UnionFs::UfsRegistryWatcher>> &,UnionFs::StackEventTracer &)

- ea: `0x140055350`
- end: `0x1400555c3`
- name: `?AllocAndInit@UfsRegistryWatcher@UnionFs@@SAJAEBU_UNICODE_STRING@@V?$function@$$A6AJAEAVUfsRegistryReader@UnionFs@@AEAVStackEventTracer@2@@Z@wistd@@AEAV?$unique_ptr@VUfsRegistryWatcher@UnionFs@@U?$default_delete@VUfsRegistryWatcher@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14003e22c`

## callees

- `0x140005574`
- `0x140054d9c`
- `0x14005523c`
- `0x140055350`
- `0x1400557bc`
- `0x140056c44`
- `0x140056c7c`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14005546e`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14005546e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005543c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400554d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055549`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005543c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400554d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055549`
- `ntoskrnl!ExAllocatePool2` at `0x14005537a`
- `ntoskrnl!ExAllocatePool2` at `0x14005537a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055486`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140055486`

## string_xrefs

- `0x14005556e`: `ORIGIN: Allocating UfsRegistryWatcher`
- `0x140055419`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x1400554af`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x140055516`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x14005557f`: `UnionFs::UfsRegistryWatcher::AllocAndInit`
- `0x140055408`: `PUSH: Allocating watcher's reader`

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
0x140055350  push    rbx
0x140055352  push    rbp
0x140055353  push    rsi
0x140055354  push    rdi
0x140055355  push    r14
0x140055357  push    r15
0x140055359  sub     rsp, 0B8h
0x140055360  mov     rbp, rdx
0x140055363  mov     r14, r8
0x140055366  mov     edx, 0A8h
0x14005536b  mov     r15, rcx
0x14005536e  mov     r8d, 67724655h
0x140055374  mov     rsi, r9
0x140055377  lea     ecx, [rdx-68h]
0x14005537a  call    cs:__imp_ExAllocatePool2
0x140055381  nop     dword ptr [rax+rax+00h]
0x140055386  mov     rdi, rax
0x140055389  test    rax, rax
0x14005538c  jz      loc_14005556E
0x140055392  mov     rdx, rbp
0x140055395  lea     rcx, [rsp+0E8h+var_B8]
0x14005539a  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14005539f  xorps   xmm0, xmm0
0x1400553a2  lea     rcx, [rdi+30h]
0x1400553a6  movups  xmmword ptr [rdi], xmm0
0x1400553a9  mov     rdx, rax
0x1400553ac  mov     rbx, rax
0x1400553af  movups  xmmword ptr [rdi+10h], xmm0
0x1400553b3  mov     qword ptr [rdi+20h], 0
0x1400553bb  mov     qword ptr [rdi+28h], 0
0x1400553c3  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x1400553c8  lea     rax, ?ProcessChanges@UfsRegistryWatcher@UnionFs@@SAXPEAX@Z; UnionFs::UfsRegistryWatcher::ProcessChanges(void *)
0x1400553cf  mov     [rdi+18h], rdi
0x1400553d3  mov     [rdi+10h], rax
0x1400553d7  mov     qword ptr [rdi], 0
0x1400553de  mov     rcx, [rbx+70h]
0x1400553e2  test    rcx, rcx
0x1400553e5  jz      short loc_1400553F3
0x1400553e7  mov     rax, [rcx]
0x1400553ea  mov     rax, [rax+18h]
0x1400553ee  call    _guard_dispatch_icall
0x1400553f3  lea     rdx, [rdi+28h]
0x1400553f7  mov     r8, rsi
0x1400553fa  mov     rcx, r15
0x1400553fd  call    ?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)
0x140055402  mov     ebx, eax
0x140055404  test    eax, eax
0x140055406  jns     short loc_140055464
0x140055408  lea     rax, aPushAllocating; "PUSH: Allocating watcher's reader"
0x14005540f  mov     r8, 592001A002Eh; struct UnionFs::StackEventTracer *
0x140055419  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x140055420  mov     [rsp+0E8h+var_C8], rax; char *
0x140055425  mov     rdx, rsi; int
0x140055428  mov     ecx, ebx; this
0x14005542a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005542f  mov     rcx, rdi; this
0x140055432  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x140055437  xor     edx, edx; Tag
0x140055439  mov     rcx, rdi; P
0x14005543c  call    cs:__imp_ExFreePoolWithTag
0x140055443  nop     dword ptr [rax+rax+00h]
0x140055448  mov     rcx, [rbp+70h]
0x14005544c  test    rcx, rcx
0x14005544f  jz      short loc_14005545D
0x140055451  mov     rax, [rcx]
0x140055454  mov     rax, [rax+18h]
0x140055458  call    _guard_dispatch_icall
0x14005545d  mov     eax, ebx
0x14005545f  jmp     loc_1400555B2
0x140055464  mov     edx, 67724655h; PoolTag
0x140055469  mov     ecx, 200h; PoolType
0x14005546e  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140055475  nop     dword ptr [rax+rax+00h]
0x14005547a  mov     rcx, [rdi+20h]; RunRefCacheAware
0x14005547e  mov     rbx, rax
0x140055481  test    rcx, rcx
0x140055484  jz      short loc_140055492
0x140055486  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005548d  nop     dword ptr [rax+rax+00h]
0x140055492  mov     [rdi+20h], rbx
0x140055496  mov     rdx, rsi; struct UnionFs::StackEventTracer *
0x140055499  test    rbx, rbx
0x14005549c  jnz     short loc_1400554F7
0x14005549e  lea     rax, aOriginAllocati_76; "ORIGIN: Allocating rundown"
0x1400554a5  mov     r8, 593001A0037h; struct UnionFs::StackEventTracer *
0x1400554af  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x1400554b6  mov     [rsp+0E8h+var_C8], rax; char *
0x1400554bb  mov     ecx, 0C000009Ah; this
0x1400554c0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400554c5  mov     rcx, rdi; this
0x1400554c8  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x1400554cd  xor     edx, edx; Tag
0x1400554cf  mov     rcx, rdi; P
0x1400554d2  call    cs:__imp_ExFreePoolWithTag
0x1400554d9  nop     dword ptr [rax+rax+00h]
0x1400554de  mov     rcx, [rbp+70h]
0x1400554e2  test    rcx, rcx
0x1400554e5  jz      loc_1400555AD
0x1400554eb  mov     rax, [rcx]
0x1400554ee  mov     rax, [rax+18h]
0x1400554f2  jmp     loc_1400555A8
0x1400554f7  mov     rcx, rdi; ApcRoutine
0x1400554fa  call    ?RegisterForChangeNotifications@UfsRegistryWatcher@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryWatcher::RegisterForChangeNotifications(UnionFs::StackEventTracer &)
0x1400554ff  mov     ebx, eax
0x140055501  test    eax, eax
0x140055503  jns     short loc_140055531
0x140055505  lea     rax, aOriginRegister; "ORIGIN: Registering for change notifica"...
0x14005550c  mov     r8, 594001A003Dh; struct UnionFs::StackEventTracer *
0x140055516  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x14005551d  mov     [rsp+0E8h+var_C8], rax; char *
0x140055522  mov     rdx, rsi; int
0x140055525  mov     ecx, ebx; this
0x140055527  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005552c  jmp     loc_14005542F
0x140055531  mov     rbx, [r14]
0x140055534  mov     [r14], rdi
0x140055537  test    rbx, rbx
0x14005553a  jz      short loc_140055555
0x14005553c  mov     rcx, rbx; this
0x14005553f  call    ??1UfsRegistryWatcher@UnionFs@@QEAA@XZ; UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)
0x140055544  xor     edx, edx; Tag
0x140055546  mov     rcx, rbx; P
0x140055549  call    cs:__imp_ExFreePoolWithTag
0x140055550  nop     dword ptr [rax+rax+00h]
0x140055555  mov     rcx, [rbp+70h]
0x140055559  test    rcx, rcx
0x14005555c  jz      short loc_14005556A
0x14005555e  mov     rax, [rcx]
0x140055561  mov     rax, [rax+18h]
0x140055565  call    _guard_dispatch_icall
0x14005556a  xor     eax, eax
0x14005556c  jmp     short loc_1400555B2
0x14005556e  lea     rax, aOriginAllocati_66; "ORIGIN: Allocating UfsRegistryWatcher"
0x140055575  mov     r8, 591001A0028h; struct UnionFs::StackEventTracer *
0x14005557f  lea     r9, aUnionfsUfsregi_3; "UnionFs::UfsRegistryWatcher::AllocAndIn"...
0x140055586  mov     [rsp+0E8h+var_C8], rax; char *
0x14005558b  mov     rdx, rsi; int
0x14005558e  mov     ecx, 0C000009Ah; this
0x140055593  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140055598  mov     rcx, [rbp+70h]
0x14005559c  test    rcx, rcx
0x14005559f  jz      short loc_1400555AD
0x1400555a1  mov     rdx, [rcx]
0x1400555a4  mov     rax, [rdx+18h]
0x1400555a8  call    _guard_dispatch_icall
0x1400555ad  mov     eax, 0C000009Ah
0x1400555b2  add     rsp, 0B8h
0x1400555b9  pop     r15
0x1400555bb  pop     r14
0x1400555bd  pop     rdi
0x1400555be  pop     rsi
0x1400555bf  pop     rbp
0x1400555c0  pop     rbx
0x1400555c1  retn
```
