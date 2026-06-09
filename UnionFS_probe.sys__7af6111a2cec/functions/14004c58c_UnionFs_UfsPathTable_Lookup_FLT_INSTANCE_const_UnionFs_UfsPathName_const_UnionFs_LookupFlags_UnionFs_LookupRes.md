# UnionFs::UfsPathTable::Lookup(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)

- ea: `0x14004c58c`
- end: `0x14004c745`
- name: `?Lookup@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct UnionFs::StackEventTracer *, int, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140023a3c`
- `0x14003ce70`
- `0x14004dd90`
- `0x140055e68`

## callees

- `0x14004c58c`
- `0x14004c74c`
- `0x140056a50`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x14004c5c5`
- `ntoskrnl!IoGetStackLimits` at `0x14004c5c5`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14004c690`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14004c690`

## string_xrefs

- `0x14004c707`: `PUSH: UfsPathTable::LookupPrivOnNewStack`
- `0x14004c718`: `UnionFs::UfsPathTable::Lookup`
- `0x14004c61e`: `PUSH: UfsPathTable::LookupPriv`
- `0x14004c6c1`: `UnionFs::UfsPathTable::LookupPrivOnNewStack`
- `0x14004c6f1`: `UnionFs::UfsPathTable::LookupPrivOnNewStack`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Lookup(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int *a5,
        struct _UNICODE_STRING *a6,
        int a7,
        struct _ERESOURCE *a8)
{
  unsigned int v12; // ebx
  const char *v13; // rax
  __int64 v14; // r8
  NTSTATUS v15; // eax
  struct UnionFs::StackEventTracer *v17; // [rsp+28h] [rbp-71h]
  struct UnionFs::StackEventTracer *v18; // [rsp+28h] [rbp-71h]
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 LowLimit; // [rsp+48h] [rbp-51h] BYREF
  _QWORD Parameter[3]; // [rsp+50h] [rbp-49h] BYREF
  int v22; // [rsp+68h] [rbp-31h]
  int v23; // [rsp+6Ch] [rbp-2Dh]
  int *v24; // [rsp+70h] [rbp-29h]
  struct _UNICODE_STRING *v25; // [rsp+78h] [rbp-21h]
  int v26; // [rsp+80h] [rbp-19h]
  int v27; // [rsp+84h] [rbp-15h]
  struct _ERESOURCE *v28; // [rsp+88h] [rbp-11h]
  UnionFs *v29[2]; // [rsp+90h] [rbp-9h]

  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit <= 0x2400 )
  {
    v24 = a5;
    v26 = a7;
    v28 = a8;
    v23 = 0;
    v27 = 0;
    *(_OWORD *)v29 = 0;
    Parameter[0] = a1;
    Parameter[1] = a2;
    Parameter[2] = a3;
    v22 = a4;
    v25 = a6;
    v15 = KeExpandKernelStackAndCalloutEx(UnionFs::UfsPathTable::LookupPrivCallout, Parameter, 0x6000u, 0, 0);
    v12 = v15;
    if ( v15 == -1073741801 )
    {
      v12 = -1073741670;
    }
    else if ( v15 >= 0 )
    {
      v12 = (unsigned int)v29[1];
      if ( SLODWORD(v29[1]) >= 0 )
        return 0;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)LODWORD(v29[1]),
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3DD00140AE6LL,
        (unsigned __int64)"UnionFs::UfsPathTable::LookupPrivOnNewStack",
        "PUSH: LookupPriv",
        (const char *)v17);
LABEL_10:
      v13 = "PUSH: UfsPathTable::LookupPrivOnNewStack";
      v14 = 0x3D70014088DLL;
      goto LABEL_11;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v12,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x3DA00140AE3LL,
      (unsigned __int64)"UnionFs::UfsPathTable::LookupPrivOnNewStack",
      "API: KeExpandKernelStackAndCalloutEx",
      (const char *)v17);
    goto LABEL_10;
  }
  v12 = UnionFs::UfsPathTable::LookupPriv(a1, a2, a3, a4, a5, a6, a7, a8);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = "PUSH: UfsPathTable::LookupPriv";
    v14 = 0x3D800140894LL;
LABEL_11:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v12,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v14,
      (unsigned __int64)"UnionFs::UfsPathTable::Lookup",
      v13,
      (const char *)v18);
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x14004c58c  push    rbp
0x14004c58e  push    rbx
0x14004c58f  push    rsi
0x14004c590  push    rdi
0x14004c591  push    r14
0x14004c593  push    r15
0x14004c595  lea     rbp, [rsp-0Fh]
0x14004c59a  sub     rsp, 0A8h
0x14004c5a1  mov     r14, rdx
0x14004c5a4  mov     [rbp+37h+HighLimit], 0
0x14004c5ac  mov     r15, rcx
0x14004c5af  mov     [rbp+37h+LowLimit], 0
0x14004c5b7  lea     rdx, [rbp+37h+HighLimit]; HighLimit
0x14004c5bb  mov     ebx, r9d
0x14004c5be  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x14004c5c2  mov     rsi, r8
0x14004c5c5  call    cs:__imp_IoGetStackLimits
0x14004c5cc  nop     dword ptr [rax+rax+00h]
0x14004c5d1  mov     rdi, [rbp+37h+arg_28]
0x14004c5d5  lea     rax, [rbp+37h+HighLimit]
0x14004c5d9  sub     rax, [rbp+37h+LowLimit]
0x14004c5dd  cmp     rax, 2400h
0x14004c5e3  jbe     short loc_14004C634
0x14004c5e5  mov     rax, [rbp+37h+arg_38]
0x14004c5e9  mov     r9d, ebx; int
0x14004c5ec  mov     [rsp+0D0h+var_98], rax; __int64
0x14004c5f1  mov     r8, rsi; int
0x14004c5f4  mov     eax, [rbp+37h+arg_30]
0x14004c5f7  mov     rdx, r14; int
0x14004c5fa  mov     [rsp+0D0h+var_A0], eax; int
0x14004c5fe  mov     rcx, r15; int
0x14004c601  mov     rax, [rbp+37h+arg_20]
0x14004c605  mov     [rsp+0D0h+var_A8], rdi; struct UnionFs::StackEventTracer *
0x14004c60a  mov     [rsp+0D0h+Context], rax; __int64
0x14004c60f  call    ?LookupPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z; UnionFs::UfsPathTable::LookupPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)
0x14004c614  mov     ebx, eax
0x14004c616  test    eax, eax
0x14004c618  jns     loc_14004C732
0x14004c61e  lea     rax, aPushUfspathtab_0; "PUSH: UfsPathTable::LookupPriv"
0x14004c625  mov     r8, 3D800140894h
0x14004c62f  jmp     loc_14004C718
0x14004c634  mov     rax, [rbp+37h+arg_20]
0x14004c638  lea     rdx, [rbp+37h+Parameter]; Parameter
0x14004c63c  mov     [rbp+37h+var_60], rax
0x14004c640  lea     rcx, ?LookupPrivCallout@UfsPathTable@UnionFs@@CAXPEAUUFS_CALLOUT_PARAMETERS@2@@Z; Callout
0x14004c647  mov     eax, [rbp+37h+arg_30]
0x14004c64a  xorps   xmm0, xmm0
0x14004c64d  mov     [rbp+37h+var_50], eax
0x14004c650  xor     r9d, r9d; Wait
0x14004c653  mov     rax, [rbp+37h+arg_38]
0x14004c657  mov     r8d, 6000h; Size
0x14004c65d  mov     [rbp+37h+var_48], rax
0x14004c661  mov     [rbp+37h+var_64], 0
0x14004c668  mov     [rbp+37h+var_4C], 0
0x14004c66f  movdqa  xmmword ptr [rbp+37h+var_40], xmm0
0x14004c674  mov     [rbp+37h+Parameter], r15
0x14004c678  mov     [rbp+37h+var_78], r14
0x14004c67c  mov     [rbp+37h+var_70], rsi
0x14004c680  mov     [rbp+37h+var_68], ebx
0x14004c683  mov     [rbp+37h+var_58], rdi
0x14004c687  mov     [rsp+0D0h+Context], 0; Context
0x14004c690  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14004c697  nop     dword ptr [rax+rax+00h]
0x14004c69c  mov     ebx, eax
0x14004c69e  cmp     eax, 0C0000017h
0x14004c6a3  jnz     short loc_14004C6AC
0x14004c6a5  mov     ebx, 0C000009Ah
0x14004c6aa  jmp     short loc_14004C6B0
0x14004c6ac  test    eax, eax
0x14004c6ae  jns     short loc_14004C6D9
0x14004c6b0  lea     rax, aApiKeexpandker; "API: KeExpandKernelStackAndCalloutEx"
0x14004c6b7  mov     r8, 3DA00140AE3h; struct UnionFs::StackEventTracer *
0x14004c6c1  lea     r9, aUnionfsUfspath_2; "UnionFs::UfsPathTable::LookupPrivOnNewS"...
0x14004c6c8  mov     [rsp+0D0h+Context], rax; char *
0x14004c6cd  mov     rdx, rdi; int
0x14004c6d0  mov     ecx, ebx; this
0x14004c6d2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004c6d7  jmp     short loc_14004C707
0x14004c6d9  mov     ebx, dword ptr [rbp+37h+var_40+8]
0x14004c6dc  test    ebx, ebx
0x14004c6de  jns     short loc_14004C732
0x14004c6e0  lea     rax, aPushLookuppriv; "PUSH: LookupPriv"
0x14004c6e7  mov     r8, 3DD00140AE6h; struct UnionFs::StackEventTracer *
0x14004c6f1  lea     r9, aUnionfsUfspath_2; "UnionFs::UfsPathTable::LookupPrivOnNewS"...
0x14004c6f8  mov     [rsp+0D0h+Context], rax; char *
0x14004c6fd  mov     rdx, rdi; int
0x14004c700  mov     ecx, ebx; this
0x14004c702  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004c707  lea     rax, aPushUfspathtab_2; "PUSH: UfsPathTable::LookupPrivOnNewStac"...
0x14004c70e  mov     r8, 3D70014088Dh; struct UnionFs::StackEventTracer *
0x14004c718  lea     r9, aUnionfsUfspath_10; "UnionFs::UfsPathTable::Lookup"
0x14004c71f  mov     [rsp+0D0h+Context], rax; char *
0x14004c724  mov     rdx, rdi; int
0x14004c727  mov     ecx, ebx; this
0x14004c729  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004c72e  mov     eax, ebx
0x14004c730  jmp     short loc_14004C734
0x14004c732  xor     eax, eax
0x14004c734  add     rsp, 0A8h
0x14004c73b  pop     r15
0x14004c73d  pop     r14
0x14004c73f  pop     rdi
0x14004c740  pop     rsi
0x14004c741  pop     rbx
0x14004c742  pop     rbp
0x14004c743  retn
```
