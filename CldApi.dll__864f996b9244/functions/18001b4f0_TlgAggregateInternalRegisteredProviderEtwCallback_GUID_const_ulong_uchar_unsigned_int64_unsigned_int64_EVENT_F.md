# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001b4f0`
- end: `0x18001b562`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001b010`
- `0x18001b3f4`
- `0x18001b4f0`
- `0x18001c010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        char a3,
        int a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        const __m128i *a7)
{
  int v8; // edi
  void (__fastcall *v9)(const struct _GUID *, __int64, unsigned __int64); // rax

  v8 = a2;
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[19].m128i_i64[1];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete(a7, a2, a3, a4);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x18001b4f0  mov     [rsp+arg_0], rbx
0x18001b4f5  push    rdi
0x18001b4f6  sub     rsp, 40h
0x18001b4fa  mov     rbx, [rsp+48h+arg_30]
0x18001b502  mov     r11b, r8b
0x18001b505  mov     edi, edx
0x18001b507  mov     rax, [rbx+138h]
0x18001b50e  test    rax, rax
0x18001b511  jz      short loc_18001B53B
0x18001b513  mov     r10, [rbx+140h]
0x18001b51a  mov     r8, [rsp+48h+arg_20]
0x18001b51f  mov     [rsp+48h+var_18], r10
0x18001b524  mov     r10, [rsp+48h+arg_28]
0x18001b529  mov     [rsp+48h+var_20], r10
0x18001b52e  mov     [rsp+48h+var_28], r8
0x18001b533  mov     r8b, r11b
0x18001b536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b53b  cmp     edi, 1
0x18001b53e  jnz     short loc_18001B54A
0x18001b540  mov     rcx, rbx
0x18001b543  call    LookUpTableFlushComplete
0x18001b548  jmp     short loc_18001B557
0x18001b54a  cmp     edi, 2
0x18001b54d  jnz     short loc_18001B557
0x18001b54f  mov     rcx, rbx
0x18001b552  call    LookUpTableFlushPartial
0x18001b557  mov     rbx, [rsp+48h+arg_0]
0x18001b55c  add     rsp, 40h
0x18001b560  pop     rdi
0x18001b561  retn
```
