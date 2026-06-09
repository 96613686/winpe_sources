# CAPONode::operator new(unsigned __int64)

- ea: `0x14000fff4`
- end: `0x1400100dd`
- name: `??2CAPONode@@SAPEAX_K@Z`
- size: `233`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000fedc`
- `0x140047ec0`

## callees

- `0x14000faf8`
- `0x14000fff4`
- `0x14005d7bc`
- `0x140083ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14001001d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14001001d`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x140010051`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x1400100d5`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x140010051`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x1400100d5`

## pseudocode

```c
void *__fastcall CAPONode::operator new(__int64 a1)
{
  int v1; // eax
  int v2; // edx
  int v3; // ecx
  int v4; // r8d
  void *v5; // rdi
  __int64 v7; // [rsp+70h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+78h] [rbp+10h] BYREF

  v7 = a1;
  Context = 0;
  v1 = -InitOnceExecuteOnce(&gRTHeapInitOnce, AERTMemoryInitOnce, 0, &Context);
  v5 = (void *)((unsigned __int64)Context & -(__int64)(v1 != 0));
  if ( g_bSkipRTHeap )
    return operator new[](0xC0u);
  v7 = 0;
  if ( v5
    && (unsigned int)RtlAllocateMemoryBlockLookaside((unsigned __int64)Context & -(__int64)(v1 != 0), 192, &v7) == -1073741670 )
  {
    AERTAddMemoryToHeap(v5, 0x100000u);
    RtlAllocateMemoryBlockLookaside(v5, 192, &v7);
  }
  if ( (byte_1400E7E41 & 4) != 0 )
    McTemplateU0pqpqqqqqq_EventWriteTransfer(v3, v2, v4, 6, (char)v5, 192, 0, 0);
  return (void *)v7;
}

```

## disassembly

```asm
0x14000fff4  mov     [rsp+arg_0], rcx
0x14000fff9  push    rdi
0x14000fffa  sub     rsp, 60h
0x14000fffe  lea     r9, [rsp+68h+Context]; Context
0x140010003  mov     [rsp+68h+Context], 0
0x14001000c  xor     r8d, r8d; Parameter
0x14001000f  lea     rdx, ?AERTMemoryInitOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140010016  lea     rcx, ?gRTHeapInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x14001001d  call    cs:__imp_InitOnceExecuteOnce
0x140010023  neg     eax
0x140010025  sbb     rdi, rdi
0x140010028  and     rdi, [rsp+68h+Context]
0x14001002d  cmp     cs:?g_bSkipRTHeap@@3_NA, 0; bool g_bSkipRTHeap
0x140010034  jnz     short loc_140010072
0x140010036  mov     [rsp+68h+arg_0], 0
0x14001003f  test    rdi, rdi
0x140010042  jz      short loc_1400100B4
0x140010044  lea     r8, [rsp+68h+arg_0]
0x140010049  mov     edx, 0C0h
0x14001004e  mov     rcx, rdi
0x140010051  call    cs:__imp_RtlAllocateMemoryBlockLookaside
0x140010057  cmp     eax, 0C000009Ah
0x14001005c  jz      short loc_1400100BB
0x14001005e  test    cs:byte_1400E7E41, 4
0x140010065  jnz     short loc_14001007E
0x140010067  mov     rax, [rsp+68h+arg_0]
0x14001006c  add     rsp, 60h
0x140010070  pop     rdi
0x140010071  retn
0x140010072  mov     ecx, 0C0h; unsigned __int64
0x140010077  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001007c  jmp     short loc_14001006C
0x14001007e  mov     [rsp+68h+var_18], eax
0x140010082  mov     r9d, 6
0x140010088  mov     [rsp+68h+var_20], 0
0x140010090  mov     [rsp+68h+var_30], 0
0x140010098  mov     [rsp+68h+var_38], 0
0x1400100a0  mov     [rsp+68h+var_40], 0C0h
0x1400100a8  mov     [rsp+68h+var_48], rdi
0x1400100ad  call    McTemplateU0pqpqqqqqq_EventWriteTransfer
0x1400100b2  jmp     short loc_140010067
0x1400100b4  mov     eax, 0C000009Ah
0x1400100b9  jmp     short loc_14001005E
0x1400100bb  mov     edx, 100000h; unsigned __int64
0x1400100c0  mov     rcx, rdi; void *
0x1400100c3  call    ?AERTAddMemoryToHeap@@YAXPEAX_K@Z; AERTAddMemoryToHeap(void *,unsigned __int64)
0x1400100c8  lea     r8, [rsp+68h+arg_0]
0x1400100cd  mov     edx, 0C0h
0x1400100d2  mov     rcx, rdi
0x1400100d5  call    cs:__imp_RtlAllocateMemoryBlockLookaside
0x1400100db  jmp     short loc_14001005E
```
