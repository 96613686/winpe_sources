# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000bfc0`
- end: `0x18000c032`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000be00`
- `0x18000bfc0`
- `0x18000c038`
- `0x18001c010`

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
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[39];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete(a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x18000bfc0  mov     [rsp+arg_0], rbx
0x18000bfc5  push    rdi
0x18000bfc6  sub     rsp, 40h
0x18000bfca  mov     rbx, [rsp+48h+arg_30]
0x18000bfd2  mov     r11b, r8b
0x18000bfd5  mov     edi, edx
0x18000bfd7  mov     rax, [rbx+138h]
0x18000bfde  test    rax, rax
0x18000bfe1  jz      short loc_18000C00B
0x18000bfe3  mov     r10, [rbx+140h]
0x18000bfea  mov     r8, [rsp+48h+arg_20]
0x18000bfef  mov     [rsp+48h+var_18], r10
0x18000bff4  mov     r10, [rsp+48h+arg_28]
0x18000bff9  mov     [rsp+48h+var_20], r10
0x18000bffe  mov     [rsp+48h+var_28], r8
0x18000c003  mov     r8b, r11b
0x18000c006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c00b  cmp     edi, 1
0x18000c00e  jnz     short loc_18000C01A
0x18000c010  mov     rcx, rbx
0x18000c013  call    LookUpTableFlushComplete
0x18000c018  jmp     short loc_18000C027
0x18000c01a  cmp     edi, 2
0x18000c01d  jnz     short loc_18000C027
0x18000c01f  mov     rcx, rbx
0x18000c022  call    LookUpTableFlushPartial
0x18000c027  mov     rbx, [rsp+48h+arg_0]
0x18000c02c  add     rsp, 40h
0x18000c030  pop     rdi
0x18000c031  retn
```
