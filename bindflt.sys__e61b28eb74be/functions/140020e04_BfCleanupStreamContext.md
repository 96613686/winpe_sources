# BfCleanupStreamContext

- ea: `0x140020e04`
- end: `0x140020ee3`
- name: `BfCleanupStreamContext`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140020ae0`

## callees

- `0x140020e04`
- `0x140020eec`

## import_xrefs

- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140020e22`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140020e22`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020e4f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020e4f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020e39`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020e39`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020e8f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020e8f`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140020e62`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140020e62`
- `FLTMGR!FltReleaseResource` at `0x140020e80`
- `FLTMGR!FltReleaseResource` at `0x140020e80`

## pseudocode

```c
NTSTATUS __fastcall BfCleanupStreamContext(__int64 a1)
{
  PVOID *v1; // rbx
  _QWORD *v3; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx

  v1 = *(PVOID **)(a1 + 112);
  if ( v1 )
  {
    FsRtlTeardownPerStreamContexts(*(PFSRTL_ADVANCED_FCB_HEADER *)(a1 + 112));
    ExFreeToNPagedLookasideList(&stru_14000B300, v1[15]);
    ExFreeToPagedLookasideList(&stru_14000B280, v1);
  }
  FltAcquireResourceExclusive((PERESOURCE)(a1 + 8));
  v3 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v5 = (_QWORD *)*v3;
        if ( !*v3 )
          break;
        v6 = v3;
LABEL_10:
        v3 = v5;
        *v6 = 0;
      }
      v6 = v3 + 1;
      v5 = (_QWORD *)v3[1];
      if ( v5 )
        goto LABEL_10;
      v7 = v3[2];
      BfCachedWalkContextAvlDeleteFunction();
      v8 = v7 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( !v8 )
        break;
      v3 = (_QWORD *)v8;
    }
  }
  *(_QWORD *)a1 = 0;
  FltReleaseResource((PERESOURCE)(a1 + 8));
  return ExDeleteResourceLite((PERESOURCE)(a1 + 8));
}

```

## disassembly

```asm
0x140020e04  mov     [rsp+arg_0], rbx
0x140020e09  mov     [rsp+arg_8], rsi
0x140020e0e  push    rdi
0x140020e0f  sub     rsp, 20h
0x140020e13  mov     rbx, [rcx+70h]
0x140020e17  mov     rdi, rcx
0x140020e1a  test    rbx, rbx
0x140020e1d  jz      short loc_140020E5B
0x140020e1f  mov     rcx, rbx; AdvancedHeader
0x140020e22  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140020e29  nop     dword ptr [rax+rax+00h]
0x140020e2e  mov     rdx, [rbx+78h]; Entry
0x140020e32  lea     rcx, stru_14000B300; Lookaside
0x140020e39  call    cs:__imp_ExFreeToNPagedLookasideList
0x140020e40  nop     dword ptr [rax+rax+00h]
0x140020e45  mov     rdx, rbx; Entry
0x140020e48  lea     rcx, stru_14000B280; Lookaside
0x140020e4f  call    cs:__imp_ExFreeToPagedLookasideList
0x140020e56  nop     dword ptr [rax+rax+00h]
0x140020e5b  lea     rsi, [rdi+8]
0x140020e5f  mov     rcx, rsi; Resource
0x140020e62  call    cs:__imp_FltAcquireResourceExclusive
0x140020e69  nop     dword ptr [rax+rax+00h]
0x140020e6e  mov     rcx, [rdi]
0x140020e71  test    rcx, rcx
0x140020e74  jnz     short loc_140020EAC
0x140020e76  mov     rcx, rsi; Resource
0x140020e79  mov     qword ptr [rdi], 0
0x140020e80  call    cs:__imp_FltReleaseResource
0x140020e87  nop     dword ptr [rax+rax+00h]
0x140020e8c  mov     rcx, rsi; Resource
0x140020e8f  call    cs:__imp_ExDeleteResourceLite
0x140020e96  nop     dword ptr [rax+rax+00h]
0x140020e9b  mov     rbx, [rsp+28h+arg_0]
0x140020ea0  mov     rsi, [rsp+28h+arg_8]
0x140020ea5  add     rsp, 20h
0x140020ea9  pop     rdi
0x140020eaa  retn
0x140020eac  mov     rdx, [rcx]
0x140020eaf  test    rdx, rdx
0x140020eb2  jnz     short loc_140020ED4
0x140020eb4  lea     rax, [rcx+8]
0x140020eb8  mov     rdx, [rax]
0x140020ebb  test    rdx, rdx
0x140020ebe  jnz     short loc_140020ED7
0x140020ec0  mov     rbx, [rcx+10h]
0x140020ec4  call    BfCachedWalkContextAvlDeleteFunction
0x140020ec9  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140020ecd  jz      short loc_140020E76
0x140020ecf  mov     rcx, rbx
0x140020ed2  jmp     short loc_140020EAC
0x140020ed4  mov     rax, rcx
0x140020ed7  mov     rcx, rdx
0x140020eda  mov     qword ptr [rax], 0
0x140020ee1  jmp     short loc_140020EAC
```
