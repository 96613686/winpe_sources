# Comms::DeserializeObject(Comms::Deserializer &,ushort * &)

- ea: `0x180003050`
- end: `0x18000313f`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAPEAG@Z`
- size: `239`
- prototype: `char __fastcall(void ***this, struct Comms::Deserializer *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003160`

## callees

- `0x180002744`
- `0x180002e90`
- `0x180003050`

## import_xrefs

- `msvcrt!free` at `0x1800030f3`
- `msvcrt!free` at `0x1800030f3`
- `msvcrt!malloc` at `0x1800030b5`
- `msvcrt!malloc` at `0x1800030b5`

## pseudocode

```c
char __fastcall Comms::DeserializeObject(void ***this, struct Comms::Deserializer *a2, unsigned __int16 **a3)
{
  size_t v5; // rsi
  char *v6; // rbx
  void **v7; // rax
  void *Block; // [rsp+50h] [rbp+18h] BYREF

  Block = 0;
  if ( !Comms::Deserializer::CopyBytesOut(
          (Comms::Deserializer *)this,
          &Block,
          8u,
          (const struct type_info *)&unsigned __int64 `RTTI Type Descriptor')
    || (char *)Block - 1 > (char *)0x7FFFFFFFFFFFFFFDLL
    || (unsigned __int64)Block > (unsigned __int64)((char *)this[1] - (char *)*this) >> 1 )
  {
    return 0;
  }
  v5 = 2LL * (_QWORD)Block;
  Block = malloc(2LL * (_QWORD)Block);
  v6 = (char *)Block;
  if ( Block )
  {
    v7 = this[4];
    if ( v7 == this[5] )
    {
      if ( !utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(
              (__int64)(this + 3),
              (char *)&Block) )
      {
        free(Block);
        return 0;
      }
      v6 = (char *)Block;
    }
    else
    {
      *v7 = Block;
      ++this[4];
    }
  }
  if ( !v6
    || !Comms::Deserializer::CopyBytesOut(
          (Comms::Deserializer *)this,
          v6,
          v5,
          (const struct type_info *)&unsigned short * `RTTI Type Descriptor')
    || *(_WORD *)&v6[v5 - 2] )
  {
    return 0;
  }
  *(_QWORD *)a2 = v6;
  return 1;
}

```

## disassembly

```asm
0x180003050  mov     rax, rsp
0x180003053  mov     [rax+8], rbx
0x180003057  mov     [rax+10h], rbp
0x18000305b  push    rsi
0x18000305c  push    rdi
0x18000305d  push    r14
0x18000305f  sub     rsp, 20h
0x180003063  xor     ebp, ebp
0x180003065  lea     r9, ??_R0_K@8; struct type_info *
0x18000306c  mov     r14, rdx
0x18000306f  mov     [rax+18h], rbp
0x180003073  lea     rdx, [rax+18h]; void *
0x180003077  mov     rdi, rcx
0x18000307a  lea     r8d, [rbp+8]; unsigned __int64
0x18000307e  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x180003083  test    al, al
0x180003085  jz      short loc_1800030F9
0x180003087  mov     rdx, [rsp+38h+Block]
0x18000308c  mov     rcx, 7FFFFFFFFFFFFFFDh
0x180003096  lea     rax, [rdx-1]
0x18000309a  cmp     rax, rcx
0x18000309d  ja      short loc_1800030F9
0x18000309f  mov     rax, [rdi+8]
0x1800030a3  sub     rax, [rdi]
0x1800030a6  shr     rax, 1
0x1800030a9  cmp     rdx, rax
0x1800030ac  ja      short loc_1800030F9
0x1800030ae  lea     rsi, [rdx+rdx]
0x1800030b2  mov     rcx, rsi; Size
0x1800030b5  call    cs:__imp_malloc
0x1800030bb  mov     [rsp+38h+Block], rax
0x1800030c0  mov     rbx, rax
0x1800030c3  test    rax, rax
0x1800030c6  jz      short loc_180003113
0x1800030c8  lea     rcx, [rdi+18h]
0x1800030cc  mov     rax, [rcx+8]
0x1800030d0  cmp     rax, [rcx+10h]
0x1800030d4  jz      short loc_1800030E0
0x1800030d6  mov     [rax], rbx
0x1800030d9  add     qword ptr [rcx+8], 8
0x1800030de  jmp     short loc_180003113
0x1800030e0  lea     rdx, [rsp+38h+Block]
0x1800030e5  call    ??$_PushBackOne2@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_NAEBQEAX@Z; utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(void * const &)
0x1800030ea  test    al, al
0x1800030ec  jnz     short loc_18000310E
0x1800030ee  mov     rcx, [rsp+38h+Block]; Block
0x1800030f3  call    cs:__imp_free
0x1800030f9  xor     al, al
0x1800030fb  mov     rbx, [rsp+38h+arg_0]
0x180003100  mov     rbp, [rsp+38h+arg_8]
0x180003105  add     rsp, 20h
0x180003109  pop     r14
0x18000310b  pop     rdi
0x18000310c  pop     rsi
0x18000310d  retn
0x18000310e  mov     rbx, [rsp+38h+Block]
0x180003113  test    rbx, rbx
0x180003116  jz      short loc_1800030F9
0x180003118  lea     r9, ??_R0PEAG@8; struct type_info *
0x18000311f  mov     r8, rsi; unsigned __int64
0x180003122  mov     rdx, rbx; void *
0x180003125  mov     rcx, rdi; this
0x180003128  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x18000312d  test    al, al
0x18000312f  jz      short loc_1800030F9
0x180003131  cmp     [rsi+rbx-2], bp
0x180003136  jnz     short loc_1800030F9
0x180003138  mov     [r14], rbx
0x18000313b  mov     al, 1
0x18000313d  jmp     short loc_1800030FB
```
