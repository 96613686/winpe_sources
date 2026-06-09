# UnionFs::UfsPathTable::Insert(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::InsertOptionalParams *)

- ea: `0x140048078`
- end: `0x14004823c`
- name: `?Insert@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAUInsertOptionalParams@2@@Z`
- size: `452`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400235a8`
- `0x140023784`
- `0x14003c854`
- `0x140055b58`

## callees

- `0x140048078`
- `0x140048244`
- `0x140056bd0`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x1400480b1`
- `ntoskrnl!IoGetStackLimits` at `0x1400480b1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140048187`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140048187`

## string_xrefs

- `0x1400481fe`: `PUSH: UfsPathTable::InsertPrivOnNewStack`
- `0x14004820f`: `UnionFs::UfsPathTable::Insert`
- `0x140048113`: `PUSH: UfsPathTable::InsertPriv`
- `0x1400481b8`: `UnionFs::UfsPathTable::InsertPrivOnNewStack`
- `0x1400481e8`: `UnionFs::UfsPathTable::InsertPrivOnNewStack`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Insert(
        int *a1,
        FsFltWil::Details *a2,
        UnionFs::Utils *a3,
        __int64 *a4,
        _DWORD *a5,
        struct UnionFs::StackEventTracer *a6,
        unsigned int a7,
        __int64 a8)
{
  unsigned int inserted; // ebx
  const char *v13; // rax
  __int64 v14; // r8
  NTSTATUS v15; // eax
  const char *v17; // [rsp+28h] [rbp-81h]
  const char *v18; // [rsp+28h] [rbp-81h]
  unsigned __int64 HighLimit; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 LowLimit; // [rsp+58h] [rbp-51h] BYREF
  _QWORD Parameter[6]; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v22; // [rsp+90h] [rbp-19h]
  int v23; // [rsp+94h] [rbp-15h]
  __int64 v24; // [rsp+98h] [rbp-11h]
  __int64 v25; // [rsp+A0h] [rbp-9h]
  UnionFs *v26; // [rsp+A8h] [rbp-1h]

  HighLimit = 0;
  LowLimit = 0;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (unsigned __int64)&HighLimit - LowLimit <= 0x3000 )
  {
    Parameter[4] = a5;
    v22 = a7;
    v25 = a8;
    v23 = 0;
    v26 = 0;
    Parameter[0] = a1;
    Parameter[1] = a2;
    Parameter[2] = a3;
    Parameter[3] = a4;
    Parameter[5] = a6;
    v24 = 0;
    v15 = KeExpandKernelStackAndCalloutEx(UnionFs::UfsPathTable::InsertPrivCallout, Parameter, 0x6000u, 0, 0);
    inserted = v15;
    if ( v15 == -1073741801 )
    {
      inserted = -1073741670;
    }
    else if ( v15 >= 0 )
    {
      inserted = (unsigned int)v26;
      if ( (int)v26 >= 0 )
        return 0;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x18100140593LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPrivOnNewStack",
        "PUSH: InsertPriv",
        v17);
LABEL_10:
      v13 = "PUSH: UfsPathTable::InsertPrivOnNewStack";
      v14 = 0x1940014002CLL;
      goto LABEL_11;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)inserted,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x17A00140590LL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPrivOnNewStack",
      "API: KeExpandKernelStackAndCalloutEx",
      v17);
    goto LABEL_10;
  }
  inserted = UnionFs::UfsPathTable::InsertPriv(a1, a2, a3, a4, a5, a6, a7, 0, a8);
  if ( (inserted & 0x80000000) != 0 )
  {
    v13 = "PUSH: UfsPathTable::InsertPriv";
    v14 = 0x3C800140033LL;
LABEL_11:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)inserted,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v14,
      (unsigned __int64)"UnionFs::UfsPathTable::Insert",
      v13,
      v18);
    return inserted;
  }
  return 0;
}

```

## disassembly

```asm
0x140048078  push    rbp
0x14004807a  push    rbx
0x14004807b  push    rsi
0x14004807c  push    rdi
0x14004807d  push    r14
0x14004807f  push    r15
0x140048081  lea     rbp, [rsp-0Fh]
0x140048086  sub     rsp, 0B8h
0x14004808d  mov     r14, rdx
0x140048090  mov     [rbp+37h+HighLimit], 0
0x140048098  mov     r15, rcx
0x14004809b  mov     [rbp+37h+LowLimit], 0
0x1400480a3  lea     rdx, [rbp+37h+HighLimit]; HighLimit
0x1400480a7  mov     rbx, r9
0x1400480aa  lea     rcx, [rbp+37h+LowLimit]; LowLimit
0x1400480ae  mov     rsi, r8
0x1400480b1  call    cs:__imp_IoGetStackLimits
0x1400480b8  nop     dword ptr [rax+rax+00h]
0x1400480bd  mov     rdi, [rbp+37h+arg_28]
0x1400480c1  lea     rax, [rbp+37h+HighLimit]
0x1400480c5  sub     rax, [rbp+37h+LowLimit]
0x1400480c9  cmp     rax, 3000h
0x1400480cf  jbe     short loc_140048129
0x1400480d1  mov     rax, [rbp+37h+arg_38]
0x1400480d5  mov     r9, rbx
0x1400480d8  mov     [rsp+0E0h+var_A0], rax
0x1400480dd  mov     r8, rsi
0x1400480e0  mov     eax, [rbp+37h+arg_30]
0x1400480e3  mov     rdx, r14
0x1400480e6  mov     [rsp+0E0h+var_A8], 0
0x1400480ef  mov     rcx, r15
0x1400480f2  mov     [rsp+0E0h+var_B0], eax
0x1400480f6  mov     rax, [rbp+37h+arg_20]
0x1400480fa  mov     [rsp+0E0h+var_B8], rdi
0x1400480ff  mov     [rsp+0E0h+Context], rax
0x140048104  call    ?InsertPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAU?$pair@V?$shared_ptr@VUfsPathTree@UnionFs@@@utl@@G@6@PEAUInsertOptionalParams@2@@Z; UnionFs::UfsPathTable::InsertPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,utl::pair<utl::shared_ptr<UnionFs::UfsPathTree>,ushort> *,UnionFs::InsertOptionalParams *)
0x140048109  mov     ebx, eax
0x14004810b  test    eax, eax
0x14004810d  jns     loc_140048229
0x140048113  lea     rax, aPushUfspathtab; "PUSH: UfsPathTable::InsertPriv"
0x14004811a  mov     r8, 3C800140033h
0x140048124  jmp     loc_14004820F
0x140048129  mov     rax, [rbp+37h+arg_20]
0x14004812d  lea     rdx, [rbp+37h+Parameter]; Parameter
0x140048131  mov     [rbp+37h+var_60], rax
0x140048135  lea     rcx, ?InsertPrivCallout@UfsPathTable@UnionFs@@CAXPEAUUFS_CALLOUT_PARAMETERS@2@@Z; Callout
0x14004813c  mov     eax, [rbp+37h+arg_30]
0x14004813f  xor     r9d, r9d; Wait
0x140048142  mov     [rbp+37h+var_50], eax
0x140048145  mov     r8d, 6000h; Size
0x14004814b  mov     rax, [rbp+37h+arg_38]
0x14004814f  mov     [rbp+37h+var_40], rax
0x140048153  mov     [rbp+37h+var_4C], 0
0x14004815a  mov     [rbp+37h+var_38], 0
0x140048162  mov     [rbp+37h+Parameter], r15
0x140048166  mov     [rbp+37h+var_78], r14
0x14004816a  mov     [rbp+37h+var_70], rsi
0x14004816e  mov     [rbp+37h+var_68], rbx
0x140048172  mov     [rbp+37h+var_58], rdi
0x140048176  mov     [rbp+37h+var_48], 0
0x14004817e  mov     [rsp+0E0h+Context], 0; Context
0x140048187  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14004818e  nop     dword ptr [rax+rax+00h]
0x140048193  mov     ebx, eax
0x140048195  cmp     eax, 0C0000017h
0x14004819a  jnz     short loc_1400481A3
0x14004819c  mov     ebx, 0C000009Ah
0x1400481a1  jmp     short loc_1400481A7
0x1400481a3  test    eax, eax
0x1400481a5  jns     short loc_1400481D0
0x1400481a7  lea     rax, aApiKeexpandker; "API: KeExpandKernelStackAndCalloutEx"
0x1400481ae  mov     r8, 17A00140590h; struct UnionFs::StackEventTracer *
0x1400481b8  lea     r9, aUnionfsUfspath_28; "UnionFs::UfsPathTable::InsertPrivOnNewS"...
0x1400481bf  mov     [rsp+0E0h+Context], rax; char *
0x1400481c4  mov     rdx, rdi; int
0x1400481c7  mov     ecx, ebx; this
0x1400481c9  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400481ce  jmp     short loc_1400481FE
0x1400481d0  mov     ebx, dword ptr [rbp+37h+var_38]
0x1400481d3  test    ebx, ebx
0x1400481d5  jns     short loc_140048229
0x1400481d7  lea     rax, aPushInsertpriv; "PUSH: InsertPriv"
0x1400481de  mov     r8, 18100140593h; struct UnionFs::StackEventTracer *
0x1400481e8  lea     r9, aUnionfsUfspath_28; "UnionFs::UfsPathTable::InsertPrivOnNewS"...
0x1400481ef  mov     [rsp+0E0h+Context], rax; char *
0x1400481f4  mov     rdx, rdi; int
0x1400481f7  mov     ecx, ebx; this
0x1400481f9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400481fe  lea     rax, aPushUfspathtab_1; "PUSH: UfsPathTable::InsertPrivOnNewStac"...
0x140048205  mov     r8, 1940014002Ch; struct UnionFs::StackEventTracer *
0x14004820f  lea     r9, aUnionfsUfspath_69; "UnionFs::UfsPathTable::Insert"
0x140048216  mov     [rsp+0E0h+Context], rax; char *
0x14004821b  mov     rdx, rdi; int
0x14004821e  mov     ecx, ebx; this
0x140048220  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140048225  mov     eax, ebx
0x140048227  jmp     short loc_14004822B
0x140048229  xor     eax, eax
0x14004822b  add     rsp, 0B8h
0x140048232  pop     r15
0x140048234  pop     r14
0x140048236  pop     rdi
0x140048237  pop     rsi
0x140048238  pop     rbx
0x140048239  pop     rbp
0x14004823a  retn
```
