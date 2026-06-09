# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000c070`
- end: `0x18000c0e2`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000bb9c`
- `0x18000bf80`
- `0x18000c070`
- `0x18000e010`

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
0x18000c070  mov     [rsp+arg_0], rbx
0x18000c075  push    rdi
0x18000c076  sub     rsp, 40h
0x18000c07a  mov     rbx, [rsp+48h+arg_30]
0x18000c082  mov     r11b, r8b
0x18000c085  mov     edi, edx
0x18000c087  mov     rax, [rbx+138h]
0x18000c08e  test    rax, rax
0x18000c091  jz      short loc_18000C0BB
0x18000c093  mov     r10, [rbx+140h]
0x18000c09a  mov     r8, [rsp+48h+arg_20]
0x18000c09f  mov     [rsp+48h+var_18], r10
0x18000c0a4  mov     r10, [rsp+48h+arg_28]
0x18000c0a9  mov     [rsp+48h+var_20], r10
0x18000c0ae  mov     [rsp+48h+var_28], r8
0x18000c0b3  mov     r8b, r11b
0x18000c0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0bb  cmp     edi, 1
0x18000c0be  jnz     short loc_18000C0CA
0x18000c0c0  mov     rcx, rbx
0x18000c0c3  call    LookUpTableFlushComplete
0x18000c0c8  jmp     short loc_18000C0D7
0x18000c0ca  cmp     edi, 2
0x18000c0cd  jnz     short loc_18000C0D7
0x18000c0cf  mov     rcx, rbx
0x18000c0d2  call    LookUpTableFlushPartial
0x18000c0d7  mov     rbx, [rsp+48h+arg_0]
0x18000c0dc  add     rsp, 40h
0x18000c0e0  pop     rdi
0x18000c0e1  retn
```
