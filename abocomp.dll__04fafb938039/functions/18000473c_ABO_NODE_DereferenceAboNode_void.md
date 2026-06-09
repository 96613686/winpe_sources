# ABO_NODE::DereferenceAboNode(void)

- ea: `0x18000473c`
- end: `0x1800047aa`
- name: `?DereferenceAboNode@ABO_NODE@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(ABO_NODE *__hidden this)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042dc`
- `0x180004398`
- `0x1800044e0`
- `0x180004828`
- `0x180004b80`
- `0x180004f98`
- `0x180005cf4`
- `0x180006f54`
- `0x180007148`
- `0x180007530`
- `0x1800077b0`
- `0x180007ac8`
- `0x180008050`
- `0x1800087bc`
- `0x180008f28`
- `0x180009488`
- `0x18000ae70`
- `0x18000b770`
- `0x18000baec`
- `0x18000bf00`
- `0x18000c560`
- `0x18000c990`
- `0x18000cbb0`
- `0x18000cd68`
- `0x18000ce90`
- `0x18000d040`
- `0x18000d360`
- `0x18000d8f0`
- `0x18000db80`
- `0x18000dea0`
- `0x18000e170`
- `0x18000e3e0`
- `0x18000e6e0`
- `0x18000ed00`
- `0x18000f110`
- `0x18000f390`
- `0x180010880`
- `0x180010f40`
- `0x180011dd0`
- `0x180012cb0`
- `0x180014488`
- `0x180014b90`
- `0x180016b1c`
- `0x18001a860`
- `0x180020890`
- `0x1800259c0`
- `0x180026cdc`
- `0x18002ac00`

## callees

- `0x18000473c`
- `0x18002c010`

## import_xrefs

- `iisutil!?TraceDelete@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x180004799`
- `iisutil!?TraceDelete@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x180004799`
- `iisutil!?TraceDereference@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x180004762`
- `iisutil!?TraceDereference@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x180004762`

## pseudocode

```c
void __fastcall ABO_NODE::DereferenceAboNode(ABO_NODE *this)
{
  signed __int32 v2; // edi
  BIG_REF_TRACE *v3; // rcx
  signed __int32 v4; // edi

  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
  v3 = (BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace;
  v4 = v2 - 1;
  if ( ABO_NODE::sm_pBigRefTrace )
  {
    BIG_REF_TRACE::TraceDereference((BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace, this);
    v3 = (BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace;
  }
  if ( !v4 )
  {
    if ( this )
    {
      (*(void (__fastcall **)(ABO_NODE *, __int64))(*(_QWORD *)this + 16LL))(this, 1);
      v3 = (BIG_REF_TRACE *)ABO_NODE::sm_pBigRefTrace;
    }
    if ( v3 )
      BIG_REF_TRACE::TraceDelete(v3, this);
  }
}

```

## disassembly

```asm
0x18000473c  mov     [rsp+arg_0], rbx
0x180004741  push    rdi
0x180004742  sub     rsp, 20h
0x180004746  mov     rbx, rcx
0x180004749  or      edi, 0FFFFFFFFh
0x18000474c  lock xadd [rcx+8], edi
0x180004751  mov     rcx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x180004758  dec     edi
0x18000475a  test    rcx, rcx
0x18000475d  jz      short loc_18000476F
0x18000475f  mov     rdx, rbx
0x180004762  call    cs:__imp_?TraceDereference@BIG_REF_TRACE@@QEAAJPEAX@Z; BIG_REF_TRACE::TraceDereference(void *)
0x180004768  mov     rcx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x18000476f  test    edi, edi
0x180004771  jnz     short loc_18000479F
0x180004773  test    rbx, rbx
0x180004776  jz      short loc_180004791
0x180004778  mov     rax, [rbx]
0x18000477b  lea     edx, [rdi+1]
0x18000477e  mov     rcx, rbx
0x180004781  mov     rax, [rax+10h]
0x180004785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478a  mov     rcx, cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x180004791  test    rcx, rcx
0x180004794  jz      short loc_18000479F
0x180004796  mov     rdx, rbx
0x180004799  call    cs:__imp_?TraceDelete@BIG_REF_TRACE@@QEAAJPEAX@Z; BIG_REF_TRACE::TraceDelete(void *)
0x18000479f  mov     rbx, [rsp+28h+arg_0]
0x1800047a4  add     rsp, 20h
0x1800047a8  pop     rdi
0x1800047a9  retn
```
