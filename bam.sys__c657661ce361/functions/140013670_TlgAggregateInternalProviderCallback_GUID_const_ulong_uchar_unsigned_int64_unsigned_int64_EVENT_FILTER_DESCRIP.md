# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140013670`
- end: `0x1400136d4`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `100`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400132ac`
- `0x140013670`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400136c1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400136c1`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14001368b`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14001368b`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&qword_140007478, 0) )
  {
    for ( i = qword_140007480; i; i = *(_QWORD *)(i + 352) )
      LookUpTableFlushComplete(i);
    ExReleasePushLockExclusiveEx(&qword_140007478, 0);
  }
}

```

## disassembly

```asm
0x140013670  cmp     edx, 2
0x140013673  jz      short loc_140013677
0x140013675  retn
0x140013677  push    rbx
0x140013678  sub     rsp, 20h
0x14001367c  cmp     r9, 20h ; ' '
0x140013680  jnz     short loc_1400136CD
0x140013682  xor     edx, edx
0x140013684  lea     rcx, qword_140007478
0x14001368b  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x140013692  nop     dword ptr [rax+rax+00h]
0x140013697  test    al, al
0x140013699  jz      short loc_1400136CD
0x14001369b  mov     rbx, cs:qword_140007480
0x1400136a2  jmp     short loc_1400136B3
0x1400136a4  mov     rcx, rbx
0x1400136a7  call    LookUpTableFlushComplete
0x1400136ac  mov     rbx, [rbx+160h]
0x1400136b3  test    rbx, rbx
0x1400136b6  jnz     short loc_1400136A4
0x1400136b8  xor     edx, edx
0x1400136ba  lea     rcx, qword_140007478
0x1400136c1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400136c8  nop     dword ptr [rax+rax+00h]
0x1400136cd  add     rsp, 20h
0x1400136d1  pop     rbx
0x1400136d2  retn
```
