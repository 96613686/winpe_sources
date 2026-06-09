# Comms::Deserializer::~Deserializer(void)

- ea: `0x180002860`
- end: `0x1800028ab`
- name: `??1Deserializer@Comms@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(Comms::Deserializer *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001178`
- `0x180002860`

## import_xrefs

- `msvcrt!free` at `0x18000287a`
- `msvcrt!free` at `0x18000287a`

## pseudocode

```c
void __fastcall Comms::Deserializer::~Deserializer(Comms::Deserializer *this)
{
  void **i; // rbx
  void *v3; // rcx

  for ( i = (void **)*((_QWORD *)this + 3); i != *((void ***)this + 4); ++i )
    free(*i);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 != (void *)-1LL )
  {
    *((_QWORD *)this + 4) = v3;
    operator delete(v3);
  }
}

```

## disassembly

```asm
0x180002860  mov     [rsp+arg_0], rbx
0x180002865  push    rdi
0x180002866  sub     rsp, 20h
0x18000286a  mov     rbx, [rcx+18h]
0x18000286e  mov     rdi, rcx
0x180002871  cmp     rbx, [rdi+20h]
0x180002875  jz      short loc_180002886
0x180002877  mov     rcx, [rbx]; Block
0x18000287a  call    cs:__imp_free
0x180002880  add     rbx, 8
0x180002884  jmp     short loc_180002871
0x180002886  mov     rcx, [rdi+18h]; Block
0x18000288a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000288e  jz      short loc_1800028A0
0x180002890  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180002897  mov     [rdi+20h], rcx
0x18000289b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800028a0  mov     rbx, [rsp+28h+arg_0]
0x1800028a5  add     rsp, 20h
0x1800028a9  pop     rdi
0x1800028aa  retn
```
