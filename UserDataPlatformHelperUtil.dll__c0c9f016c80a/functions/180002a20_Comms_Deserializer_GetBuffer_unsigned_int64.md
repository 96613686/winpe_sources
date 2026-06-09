# Comms::Deserializer::GetBuffer(unsigned __int64)

- ea: `0x180002a20`
- end: `0x180002a7c`
- name: `?GetBuffer@Deserializer@Comms@@QEAAPEAX_K@Z`
- size: `92`
- prototype: `void *__fastcall(Comms::Deserializer *this, size_t)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002744`
- `0x180002a20`

## import_xrefs

- `msvcrt!free` at `0x180002a67`
- `msvcrt!free` at `0x180002a67`
- `msvcrt!malloc` at `0x180002a2c`
- `msvcrt!malloc` at `0x180002a2c`

## pseudocode

```c
void *__fastcall Comms::Deserializer::GetBuffer(Comms::Deserializer *this, size_t a2)
{
  void *result; // rax
  _QWORD *v4; // rdx
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  result = malloc(a2);
  Block = result;
  if ( result )
  {
    v4 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v4 == *((_QWORD **)this + 5) )
    {
      if ( utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>((__int64)this + 24, (char *)&Block) )
      {
        return Block;
      }
      else
      {
        free(Block);
        return 0;
      }
    }
    else
    {
      *v4 = result;
      *((_QWORD *)this + 4) += 8LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002a20  push    rbx
0x180002a22  sub     rsp, 20h
0x180002a26  mov     rbx, rcx
0x180002a29  mov     rcx, rdx; Size
0x180002a2c  call    cs:__imp_malloc
0x180002a32  mov     [rsp+28h+Block], rax
0x180002a37  test    rax, rax
0x180002a3a  jz      short loc_180002A76
0x180002a3c  lea     rcx, [rbx+18h]
0x180002a40  mov     rdx, [rcx+8]
0x180002a44  cmp     rdx, [rcx+10h]
0x180002a48  jz      short loc_180002A54
0x180002a4a  mov     [rdx], rax
0x180002a4d  add     qword ptr [rcx+8], 8
0x180002a52  jmp     short loc_180002A76
0x180002a54  lea     rdx, [rsp+28h+Block]
0x180002a59  call    ??$_PushBackOne2@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_NAEBQEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(void * const &)
0x180002a5e  test    al, al
0x180002a60  jnz     short loc_180002A71
0x180002a62  mov     rcx, [rsp+28h+Block]; Block
0x180002a67  call    cs:__imp_free
0x180002a6d  xor     eax, eax
0x180002a6f  jmp     short loc_180002A76
0x180002a71  mov     rax, [rsp+28h+Block]
0x180002a76  add     rsp, 20h
0x180002a7a  pop     rbx
0x180002a7b  retn
```
