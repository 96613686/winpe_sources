# Streaming::StrmPostQueryInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140001870`
- end: `0x1400018c3`
- name: `?StrmPostQueryInfo@Streaming@@YA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `83`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(Streaming *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001870`

## import_xrefs

- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400018a9`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400018a9`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPostQueryInfo(
        struct _FLT_CALLBACK_DATA *this,
        const struct _FLT_RELATED_OBJECTS *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        void *a4)
{
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+40h] [rbp+8h] BYREF

  if ( !this || !a2 || !a2->FileObject || ((unsigned __int8)a4 & 1) != 0 )
    return 0;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  FltDoCompletionProcessingWhenSafe(
    this,
    a2,
    a3,
    (unsigned __int8)a4,
    Streaming::StrmPostQueryInfoWorker,
    &RetPostOperationStatus);
  return (unsigned int)RetPostOperationStatus;
}

```

## disassembly

```asm
0x140001870  sub     rsp, 38h
0x140001874  test    rcx, rcx
0x140001877  jz      short loc_1400018BB
0x140001879  test    rdx, rdx
0x14000187c  jz      short loc_1400018BB
0x14000187e  cmp     qword ptr [rdx+20h], 0
0x140001883  jz      short loc_1400018BB
0x140001885  test    r9b, 1
0x140001889  jnz     short loc_1400018BB
0x14000188b  lea     rax, [rsp+38h+arg_0]
0x140001890  mov     [rsp+38h+arg_0], 0
0x140001898  mov     [rsp+38h+RetPostOperationStatus], rax; RetPostOperationStatus
0x14000189d  lea     rax, ?StrmPostQueryInfoWorker@Streaming@@YA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z; Streaming::StrmPostQueryInfoWorker(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)
0x1400018a4  mov     [rsp+38h+SafePostCallback], rax; SafePostCallback
0x1400018a9  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400018b0  nop     dword ptr [rax+rax+00h]
0x1400018b5  mov     eax, [rsp+38h+arg_0]
0x1400018b9  jmp     short loc_1400018BD
0x1400018bb  xor     eax, eax
0x1400018bd  add     rsp, 38h
0x1400018c1  retn
```
