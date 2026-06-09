# UnionFs::UfsPathCachePayloadNP::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP,utl::default_delete<UnionFs::UfsPathCachePayloadNP>> &,UnionFs::StackEventTracer &)

- ea: `0x140040020`
- end: `0x140040108`
- name: `?AllocAndInit@UfsPathCachePayloadNP@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCachePayloadNP@UnionFs@@U?$default_delete@VUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140040110`
- `0x140040ff4`

## callees

- `0x14003f9d0`
- `0x14003fef8`
- `0x140040020`
- `0x140056c44`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004005d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400400b9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004005d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400400b9`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040077`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040077`

## string_xrefs

- `0x1400400c9`: `ORIGIN: Allocating non-paged path cache payload`
- `0x1400400dc`: `UnionFs::UfsPathCachePayloadNP::AllocAndInit`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayloadNP::AllocAndInit(UnionFs::UfsPathCachePayloadNP **a1, int a2)
{
  UnionFs::UfsPathCachePayloadNP *v2; // rdi
  UnionFs::UfsPathCachePayloadNP *v5; // rax
  __int64 v6; // rax
  UnionFs::UfsPathCachePayloadNP *v7; // rdi
  const char *v9; // [rsp+28h] [rbp-10h]

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
  {
    UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v2);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v2);
  }
  v5 = (UnionFs::UfsPathCachePayloadNP *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState
                                                                                          + 1568));
  if ( v5 && (v6 = UnionFs::UfsPathCachePayloadNP::UfsPathCachePayloadNP(v5)) != 0 )
  {
    v7 = *a1;
    *a1 = (UnionFs::UfsPathCachePayloadNP *)v6;
    if ( v7 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v7);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v7);
    }
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a2,
      (struct UnionFs::StackEventTracer *)0x30C00120028LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayloadNP::AllocAndInit",
      "ORIGIN: Allocating non-paged path cache payload",
      v9);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140040020  mov     [rsp+arg_0], rbx
0x140040025  mov     [rsp+arg_8], rsi
0x14004002a  push    rdi
0x14004002b  sub     rsp, 30h
0x14004002f  mov     rdi, [rcx]
0x140040032  mov     rsi, rdx
0x140040035  mov     qword ptr [rcx], 0
0x14004003c  mov     rbx, rcx
0x14004003f  test    rdi, rdi
0x140040042  jz      short loc_140040069
0x140040044  mov     rcx, rdi; this
0x140040047  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14004004c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140040053  mov     rdx, rdi; Entry
0x140040056  add     rcx, 620h; Lookaside
0x14004005d  call    cs:__imp_ExFreeToLookasideListEx
0x140040064  nop     dword ptr [rax+rax+00h]
0x140040069  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140040070  add     rcx, 620h; Lookaside
0x140040077  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004007e  nop     dword ptr [rax+rax+00h]
0x140040083  test    rax, rax
0x140040086  jz      short loc_1400400C9
0x140040088  mov     rcx, rax; this
0x14004008b  call    ??0UfsPathCachePayloadNP@UnionFs@@AEAA@XZ; UnionFs::UfsPathCachePayloadNP::UfsPathCachePayloadNP(void)
0x140040090  test    rax, rax
0x140040093  jz      short loc_1400400C9
0x140040095  mov     rdi, [rbx]
0x140040098  mov     [rbx], rax
0x14004009b  test    rdi, rdi
0x14004009e  jz      short loc_1400400C5
0x1400400a0  mov     rcx, rdi; this
0x1400400a3  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x1400400a8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400400af  mov     rdx, rdi; Entry
0x1400400b2  add     rcx, 620h; Lookaside
0x1400400b9  call    cs:__imp_ExFreeToLookasideListEx
0x1400400c0  nop     dword ptr [rax+rax+00h]
0x1400400c5  xor     eax, eax
0x1400400c7  jmp     short loc_1400400F7
0x1400400c9  lea     rax, aOriginAllocati_31; "ORIGIN: Allocating non-paged path cache"...
0x1400400d0  mov     ebx, 0C000009Ah
0x1400400d5  mov     ecx, ebx; this
0x1400400d7  mov     [rsp+38h+var_18], rax; char *
0x1400400dc  lea     r9, aUnionfsUfspath_55; "UnionFs::UfsPathCachePayloadNP::AllocAn"...
0x1400400e3  mov     r8, 30C00120028h; struct UnionFs::StackEventTracer *
0x1400400ed  mov     rdx, rsi; int
0x1400400f0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400400f5  mov     eax, ebx
0x1400400f7  mov     rbx, [rsp+38h+arg_0]
0x1400400fc  mov     rsi, [rsp+38h+arg_8]
0x140040101  add     rsp, 30h
0x140040105  pop     rdi
0x140040106  retn
```
