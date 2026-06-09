# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140066140`
- end: `0x1400661b3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140047e90`
- `0x140065bc8`
- `0x140065fac`
- `0x140066140`

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
0x140066140  mov     [rsp+arg_0], rbx
0x140066145  push    rdi
0x140066146  sub     rsp, 40h
0x14006614a  mov     rbx, [rsp+48h+arg_30]
0x140066152  mov     r11b, r8b
0x140066155  mov     edi, edx
0x140066157  mov     rax, [rbx+148h]
0x14006615e  test    rax, rax
0x140066161  jz      short loc_14006618B
0x140066163  mov     r10, [rbx+150h]
0x14006616a  mov     r8, [rsp+48h+arg_20]
0x14006616f  mov     [rsp+48h+var_18], r10
0x140066174  mov     r10, [rsp+48h+arg_28]
0x140066179  mov     [rsp+48h+var_20], r10
0x14006617e  mov     [rsp+48h+var_28], r8
0x140066183  mov     r8b, r11b
0x140066186  call    _guard_dispatch_icall
0x14006618b  cmp     edi, 1
0x14006618e  jnz     short loc_14006619A
0x140066190  mov     rcx, rbx
0x140066193  call    LookUpTableFlushComplete
0x140066198  jmp     short loc_1400661A7
0x14006619a  cmp     edi, 2
0x14006619d  jnz     short loc_1400661A7
0x14006619f  mov     rcx, rbx
0x1400661a2  call    LookUpTableFlushPartial
0x1400661a7  mov     rbx, [rsp+48h+arg_0]
0x1400661ac  add     rsp, 40h
0x1400661b0  pop     rdi
0x1400661b1  retn
```
