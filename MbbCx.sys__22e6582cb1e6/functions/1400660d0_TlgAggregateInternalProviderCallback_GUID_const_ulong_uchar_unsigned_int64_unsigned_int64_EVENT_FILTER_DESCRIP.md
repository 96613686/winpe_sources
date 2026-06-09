# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1400660d0`
- end: `0x140066132`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `98`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140065bc8`
- `0x1400660d0`

## import_xrefs

- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1400660e9`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1400660e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006611f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006611f`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && (unsigned __int8)ExTryAcquirePushLockExclusiveEx(&qword_14005F508, 0) )
  {
    for ( i = qword_14005F510; i; i = *(_QWORD *)(i + 352) )
      LookUpTableFlushComplete(i);
    ExReleasePushLockExclusiveEx(&qword_14005F508, 0);
  }
}

```

## disassembly

```asm
0x1400660d0  cmp     edx, 2
0x1400660d3  jnz     short locret_140066130
0x1400660d5  push    rbx
0x1400660d6  sub     rsp, 20h
0x1400660da  cmp     r9, 20h ; ' '
0x1400660de  jnz     short loc_14006612B
0x1400660e0  xor     edx, edx
0x1400660e2  lea     rcx, qword_14005F508
0x1400660e9  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1400660f0  nop     dword ptr [rax+rax+00h]
0x1400660f5  test    al, al
0x1400660f7  jz      short loc_14006612B
0x1400660f9  mov     rbx, cs:qword_14005F510
0x140066100  jmp     short loc_140066111
0x140066102  mov     rcx, rbx
0x140066105  call    LookUpTableFlushComplete
0x14006610a  mov     rbx, [rbx+160h]
0x140066111  test    rbx, rbx
0x140066114  jnz     short loc_140066102
0x140066116  xor     edx, edx
0x140066118  lea     rcx, qword_14005F508
0x14006611f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140066126  nop     dword ptr [rax+rax+00h]
0x14006612b  add     rsp, 20h
0x14006612f  pop     rbx
0x140066130  retn
```
