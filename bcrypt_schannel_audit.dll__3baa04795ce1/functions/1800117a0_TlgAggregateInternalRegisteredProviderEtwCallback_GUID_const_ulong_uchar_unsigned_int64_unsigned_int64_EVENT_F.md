# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800117a0`
- end: `0x180011813`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800117a0`
- `0x18001181c`
- `0x18001b070`
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
0x1800117a0  mov     [rsp+arg_0], rbx
0x1800117a5  push    rdi
0x1800117a6  sub     rsp, 40h
0x1800117aa  mov     rbx, [rsp+48h+arg_30]
0x1800117b2  mov     r11b, r8b
0x1800117b5  mov     edi, edx
0x1800117b7  mov     rax, [rbx+138h]
0x1800117be  test    rax, rax
0x1800117c1  jz      short loc_1800117EB
0x1800117c3  mov     r10, [rbx+140h]
0x1800117ca  mov     r8, [rsp+48h+arg_20]
0x1800117cf  mov     [rsp+48h+var_18], r10
0x1800117d4  mov     r10, [rsp+48h+arg_28]
0x1800117d9  mov     [rsp+48h+var_20], r10
0x1800117de  mov     [rsp+48h+var_28], r8
0x1800117e3  mov     r8b, r11b
0x1800117e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117eb  cmp     edi, 1
0x1800117ee  jnz     short loc_1800117FA
0x1800117f0  mov     rcx, rbx
0x1800117f3  call    LookUpTableFlushComplete
0x1800117f8  jmp     short loc_180011807
0x1800117fa  cmp     edi, 2
0x1800117fd  jnz     short loc_180011807
0x1800117ff  mov     rcx, rbx
0x180011802  call    LookUpTableFlushPartial
0x180011807  mov     rbx, [rsp+48h+arg_0]
0x18001180c  add     rsp, 40h
0x180011810  pop     rdi
0x180011811  retn
```
