# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140013230`
- end: `0x1400132a3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002710`
- `0x140013230`
- `0x1400132ac`
- `0x1400136dc`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        _QWORD *a7)
{
  int v8; // edi
  void (__fastcall *v9)(const struct _GUID *, __int64, unsigned __int64); // rax

  v8 = a2;
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[41];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete((__int64)a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x140013230  mov     [rsp+arg_0], rbx
0x140013235  push    rdi
0x140013236  sub     rsp, 40h
0x14001323a  mov     rbx, [rsp+48h+arg_30]
0x140013242  mov     r11b, r8b
0x140013245  mov     edi, edx
0x140013247  mov     rax, [rbx+148h]
0x14001324e  test    rax, rax
0x140013251  jz      short loc_14001327B
0x140013253  mov     r10, [rbx+150h]
0x14001325a  mov     r8, [rsp+48h+arg_20]
0x14001325f  mov     [rsp+48h+var_18], r10
0x140013264  mov     r10, [rsp+48h+arg_28]
0x140013269  mov     [rsp+48h+var_20], r10
0x14001326e  mov     [rsp+48h+var_28], r8
0x140013273  mov     r8b, r11b
0x140013276  call    _guard_dispatch_icall
0x14001327b  cmp     edi, 1
0x14001327e  jnz     short loc_140013294
0x140013280  mov     rcx, rbx
0x140013283  call    LookUpTableFlushComplete
0x140013288  mov     rbx, [rsp+48h+arg_0]
0x14001328d  add     rsp, 40h
0x140013291  pop     rdi
0x140013292  retn
0x140013294  cmp     edi, 2
0x140013297  jnz     short loc_140013288
0x140013299  mov     rcx, rbx
0x14001329c  call    LookUpTableFlushPartial
0x1400132a1  jmp     short loc_140013288
```
