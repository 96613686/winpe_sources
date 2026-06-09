# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180016870`
- end: `0x1800168e2`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001639c`
- `0x180016780`
- `0x180016870`
- `0x180018010`

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
0x180016870  mov     [rsp+arg_0], rbx
0x180016875  push    rdi
0x180016876  sub     rsp, 40h
0x18001687a  mov     rbx, [rsp+48h+arg_30]
0x180016882  mov     r11b, r8b
0x180016885  mov     edi, edx
0x180016887  mov     rax, [rbx+138h]
0x18001688e  test    rax, rax
0x180016891  jz      short loc_1800168BB
0x180016893  mov     r10, [rbx+140h]
0x18001689a  mov     r8, [rsp+48h+arg_20]
0x18001689f  mov     [rsp+48h+var_18], r10
0x1800168a4  mov     r10, [rsp+48h+arg_28]
0x1800168a9  mov     [rsp+48h+var_20], r10
0x1800168ae  mov     [rsp+48h+var_28], r8
0x1800168b3  mov     r8b, r11b
0x1800168b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168bb  cmp     edi, 1
0x1800168be  jnz     short loc_1800168CA
0x1800168c0  mov     rcx, rbx
0x1800168c3  call    LookUpTableFlushComplete
0x1800168c8  jmp     short loc_1800168D7
0x1800168ca  cmp     edi, 2
0x1800168cd  jnz     short loc_1800168D7
0x1800168cf  mov     rcx, rbx
0x1800168d2  call    LookUpTableFlushPartial
0x1800168d7  mov     rbx, [rsp+48h+arg_0]
0x1800168dc  add     rsp, 40h
0x1800168e0  pop     rdi
0x1800168e1  retn
```
