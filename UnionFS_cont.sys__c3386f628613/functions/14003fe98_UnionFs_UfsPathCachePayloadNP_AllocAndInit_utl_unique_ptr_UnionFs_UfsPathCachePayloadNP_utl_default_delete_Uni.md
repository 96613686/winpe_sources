# UnionFs::UfsPathCachePayloadNP::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP,utl::default_delete<UnionFs::UfsPathCachePayloadNP>> &,UnionFs::StackEventTracer &)

- ea: `0x14003fe98`
- end: `0x14003ff80`
- name: `?AllocAndInit@UfsPathCachePayloadNP@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCachePayloadNP@UnionFs@@U?$default_delete@VUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14003ff88`
- `0x140040e6c`

## callees

- `0x14003f8a8`
- `0x14003fd70`
- `0x14003fe98`
- `0x140056ac4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fed5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ff31`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fed5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ff31`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003feef`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003feef`

## string_xrefs

- `0x14003ff41`: `ORIGIN: Allocating non-paged path cache payload`
- `0x14003ff54`: `UnionFs::UfsPathCachePayloadNP::AllocAndInit`

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
0x14003fe98  mov     [rsp+arg_0], rbx
0x14003fe9d  mov     [rsp+arg_8], rsi
0x14003fea2  push    rdi
0x14003fea3  sub     rsp, 30h
0x14003fea7  mov     rdi, [rcx]
0x14003feaa  mov     rsi, rdx
0x14003fead  mov     qword ptr [rcx], 0
0x14003feb4  mov     rbx, rcx
0x14003feb7  test    rdi, rdi
0x14003feba  jz      short loc_14003FEE1
0x14003febc  mov     rcx, rdi; this
0x14003febf  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14003fec4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fecb  mov     rdx, rdi; Entry
0x14003fece  add     rcx, 620h; Lookaside
0x14003fed5  call    cs:__imp_ExFreeToLookasideListEx
0x14003fedc  nop     dword ptr [rax+rax+00h]
0x14003fee1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fee8  add     rcx, 620h; Lookaside
0x14003feef  call    cs:__imp_ExAllocateFromLookasideListEx
0x14003fef6  nop     dword ptr [rax+rax+00h]
0x14003fefb  test    rax, rax
0x14003fefe  jz      short loc_14003FF41
0x14003ff00  mov     rcx, rax; this
0x14003ff03  call    ??0UfsPathCachePayloadNP@UnionFs@@AEAA@XZ; UnionFs::UfsPathCachePayloadNP::UfsPathCachePayloadNP(void)
0x14003ff08  test    rax, rax
0x14003ff0b  jz      short loc_14003FF41
0x14003ff0d  mov     rdi, [rbx]
0x14003ff10  mov     [rbx], rax
0x14003ff13  test    rdi, rdi
0x14003ff16  jz      short loc_14003FF3D
0x14003ff18  mov     rcx, rdi; this
0x14003ff1b  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14003ff20  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003ff27  mov     rdx, rdi; Entry
0x14003ff2a  add     rcx, 620h; Lookaside
0x14003ff31  call    cs:__imp_ExFreeToLookasideListEx
0x14003ff38  nop     dword ptr [rax+rax+00h]
0x14003ff3d  xor     eax, eax
0x14003ff3f  jmp     short loc_14003FF6F
0x14003ff41  lea     rax, aOriginAllocati_31; "ORIGIN: Allocating non-paged path cache"...
0x14003ff48  mov     ebx, 0C000009Ah
0x14003ff4d  mov     ecx, ebx; this
0x14003ff4f  mov     [rsp+38h+var_18], rax; char *
0x14003ff54  lea     r9, aUnionfsUfspath_55; "UnionFs::UfsPathCachePayloadNP::AllocAn"...
0x14003ff5b  mov     r8, 30C00120028h; struct UnionFs::StackEventTracer *
0x14003ff65  mov     rdx, rsi; int
0x14003ff68  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003ff6d  mov     eax, ebx
0x14003ff6f  mov     rbx, [rsp+38h+arg_0]
0x14003ff74  mov     rsi, [rsp+38h+arg_8]
0x14003ff79  add     rsp, 30h
0x14003ff7d  pop     rdi
0x14003ff7e  retn
```
