# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14003d5a0`
- end: `0x14003d613`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140011640`
- `0x140026004`
- `0x14003d5a0`
- `0x14003d61c`

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
0x14003d5a0  mov     [rsp+arg_0], rbx
0x14003d5a5  push    rdi
0x14003d5a6  sub     rsp, 40h
0x14003d5aa  mov     rbx, [rsp+48h+arg_30]
0x14003d5b2  mov     r11b, r8b
0x14003d5b5  mov     edi, edx
0x14003d5b7  mov     rax, [rbx+148h]
0x14003d5be  test    rax, rax
0x14003d5c1  jz      short loc_14003D5EB
0x14003d5c3  mov     r10, [rbx+150h]
0x14003d5ca  mov     r8, [rsp+48h+arg_20]
0x14003d5cf  mov     [rsp+48h+var_18], r10
0x14003d5d4  mov     r10, [rsp+48h+arg_28]
0x14003d5d9  mov     [rsp+48h+var_20], r10
0x14003d5de  mov     [rsp+48h+var_28], r8
0x14003d5e3  mov     r8b, r11b
0x14003d5e6  call    _guard_dispatch_icall
0x14003d5eb  cmp     edi, 1
0x14003d5ee  jnz     short loc_14003D5FA
0x14003d5f0  mov     rcx, rbx
0x14003d5f3  call    LookUpTableFlushComplete
0x14003d5f8  jmp     short loc_14003D607
0x14003d5fa  cmp     edi, 2
0x14003d5fd  jnz     short loc_14003D607
0x14003d5ff  mov     rcx, rbx
0x14003d602  call    LookUpTableFlushPartial
0x14003d607  mov     rbx, [rsp+48h+arg_0]
0x14003d60c  add     rsp, 40h
0x14003d610  pop     rdi
0x14003d611  retn
```
