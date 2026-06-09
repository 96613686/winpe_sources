# Comms::DeserializeObject(Comms::Deserializer &,char * &)

- ea: `0x180002f70`
- end: `0x180003043`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAD@Z`
- size: `211`
- prototype: `char __fastcall(size_t **this, struct Comms::Deserializer *, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180002744`
- `0x180002e90`
- `0x180002f70`

## import_xrefs

- `msvcrt!free` at `0x180003000`
- `msvcrt!free` at `0x180003000`
- `msvcrt!malloc` at `0x180002fc2`
- `msvcrt!malloc` at `0x180002fc2`

## pseudocode

```c
char __fastcall Comms::DeserializeObject(size_t **this, struct Comms::Deserializer *a2, char **a3)
{
  size_t v5; // rdi
  char *v6; // rbx
  size_t *v7; // rax
  size_t Size; // [rsp+60h] [rbp+18h] BYREF

  Size = 0;
  if ( !Comms::Deserializer::CopyBytesOut(
          (Comms::Deserializer *)this,
          &Size,
          8u,
          (const struct type_info *)&unsigned __int64 `RTTI Type Descriptor') )
    return 0;
  v5 = Size;
  if ( Size - 1 > 0xFFFFFFFFFFFFFFFDuLL || Size > (char *)this[1] - (char *)*this )
    return 0;
  Size = (size_t)malloc(Size);
  v6 = (char *)Size;
  if ( Size )
  {
    v7 = this[4];
    if ( v7 == this[5] )
    {
      if ( !utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(
              (__int64)(this + 3),
              (char *)&Size) )
      {
        free((void *)Size);
        return 0;
      }
      v6 = (char *)Size;
    }
    else
    {
      *v7 = Size;
      ++this[4];
    }
  }
  if ( !v6
    || !Comms::Deserializer::CopyBytesOut(
          (Comms::Deserializer *)this,
          v6,
          v5,
          (const struct type_info *)&char * `RTTI Type Descriptor')
    || v6[v5 - 1] )
  {
    return 0;
  }
  *(_QWORD *)a2 = v6;
  return 1;
}

```

## disassembly

```asm
0x180002f70  push    rbx
0x180002f72  push    rsi
0x180002f73  push    rdi
0x180002f74  push    r14
0x180002f76  sub     rsp, 28h
0x180002f7a  mov     r14, rdx
0x180002f7d  mov     [rsp+48h+Size], 0
0x180002f86  lea     rdx, [rsp+48h+Size]; void *
0x180002f8b  mov     r8d, 8; unsigned __int64
0x180002f91  lea     r9, ??_R0_K@8; struct type_info *
0x180002f98  mov     rsi, rcx
0x180002f9b  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x180002fa0  test    al, al
0x180002fa2  jz      short loc_180003006
0x180002fa4  mov     rdi, [rsp+48h+Size]
0x180002fa9  lea     rax, [rdi-1]
0x180002fad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002fb1  ja      short loc_180003006
0x180002fb3  mov     rax, [rsi+8]
0x180002fb7  sub     rax, [rsi]
0x180002fba  cmp     rdi, rax
0x180002fbd  ja      short loc_180003006
0x180002fbf  mov     rcx, rdi; Size
0x180002fc2  call    cs:__imp_malloc
0x180002fc8  mov     [rsp+48h+Size], rax
0x180002fcd  mov     rbx, rax
0x180002fd0  test    rax, rax
0x180002fd3  jz      short loc_180003017
0x180002fd5  lea     rcx, [rsi+18h]
0x180002fd9  mov     rax, [rcx+8]
0x180002fdd  cmp     rax, [rcx+10h]
0x180002fe1  jz      short loc_180002FED
0x180002fe3  mov     [rax], rbx
0x180002fe6  add     qword ptr [rcx+8], 8
0x180002feb  jmp     short loc_180003017
0x180002fed  lea     rdx, [rsp+48h+Size]
0x180002ff2  call    ??$_PushBackOne2@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_NAEBQEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(void * const &)
0x180002ff7  test    al, al
0x180002ff9  jnz     short loc_180003012
0x180002ffb  mov     rcx, [rsp+48h+Size]; Block
0x180003000  call    cs:__imp_free
0x180003006  xor     al, al
0x180003008  add     rsp, 28h
0x18000300c  pop     r14
0x18000300e  pop     rdi
0x18000300f  pop     rsi
0x180003010  pop     rbx
0x180003011  retn
0x180003012  mov     rbx, [rsp+48h+Size]
0x180003017  test    rbx, rbx
0x18000301a  jz      short loc_180003006
0x18000301c  lea     r9, ??_R0PEAD@8; struct type_info *
0x180003023  mov     r8, rdi; unsigned __int64
0x180003026  mov     rdx, rbx; void *
0x180003029  mov     rcx, rsi; this
0x18000302c  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x180003031  test    al, al
0x180003033  jz      short loc_180003006
0x180003035  cmp     byte ptr [rbx+rdi-1], 0
0x18000303a  jnz     short loc_180003006
0x18000303c  mov     [r14], rbx
0x18000303f  mov     al, 1
0x180003041  jmp     short loc_180003008
```
