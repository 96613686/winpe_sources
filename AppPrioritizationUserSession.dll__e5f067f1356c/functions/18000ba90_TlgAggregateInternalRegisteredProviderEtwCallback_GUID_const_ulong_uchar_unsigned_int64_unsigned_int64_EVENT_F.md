# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000ba90`
- end: `0x18000bb02`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000b5b0`
- `0x18000b994`
- `0x18000ba90`
- `0x18000d010`

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
0x18000ba90  mov     [rsp+arg_0], rbx
0x18000ba95  push    rdi
0x18000ba96  sub     rsp, 40h
0x18000ba9a  mov     rbx, [rsp+48h+arg_30]
0x18000baa2  mov     r11b, r8b
0x18000baa5  mov     edi, edx
0x18000baa7  mov     rax, [rbx+138h]
0x18000baae  test    rax, rax
0x18000bab1  jz      short loc_18000BADB
0x18000bab3  mov     r10, [rbx+140h]
0x18000baba  mov     r8, [rsp+48h+arg_20]
0x18000babf  mov     [rsp+48h+var_18], r10
0x18000bac4  mov     r10, [rsp+48h+arg_28]
0x18000bac9  mov     [rsp+48h+var_20], r10
0x18000bace  mov     [rsp+48h+var_28], r8
0x18000bad3  mov     r8b, r11b
0x18000bad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000badb  cmp     edi, 1
0x18000bade  jnz     short loc_18000BAEA
0x18000bae0  mov     rcx, rbx
0x18000bae3  call    LookUpTableFlushComplete
0x18000bae8  jmp     short loc_18000BAF7
0x18000baea  cmp     edi, 2
0x18000baed  jnz     short loc_18000BAF7
0x18000baef  mov     rcx, rbx
0x18000baf2  call    LookUpTableFlushPartial
0x18000baf7  mov     rbx, [rsp+48h+arg_0]
0x18000bafc  add     rsp, 40h
0x18000bb00  pop     rdi
0x18000bb01  retn
```
