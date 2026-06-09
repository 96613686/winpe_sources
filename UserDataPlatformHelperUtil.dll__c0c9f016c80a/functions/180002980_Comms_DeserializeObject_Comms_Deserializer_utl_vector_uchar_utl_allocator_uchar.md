# Comms::DeserializeObject(Comms::Deserializer &,utl::vector<uchar,utl::allocator<uchar>> &)

- ea: `0x180002980`
- end: `0x180002a18`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z`
- size: `152`
- prototype: `char __fastcall(Comms::Deserializer *this, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002980`
- `0x180002d98`
- `0x180002e90`
- `0x18000a15a`

## pseudocode

```c
char __fastcall Comms::DeserializeObject(Comms::Deserializer *this, void **a2)
{
  char result; // al
  size_t v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  result = Comms::Deserializer::CopyBytesOut(
             this,
             &v7,
             8u,
             (const struct type_info *)&unsigned __int64 `RTTI Type Descriptor');
  if ( result )
  {
    v5 = v7;
    v6 = (_BYTE *)a2[1] - (_BYTE *)*a2;
    if ( v7 > v6 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(a2, v7) )
      {
        memset_0(a2[1], 0, v5 - v6);
        a2[1] = (char *)*a2 + v5;
      }
    }
    else
    {
      a2[1] = (char *)*a2 + v7;
    }
    return Comms::Deserializer::CopyBytesOut(
             this,
             *a2,
             v5,
             (const struct type_info *)&utl::vector<unsigned char,utl::allocator<unsigned char>> `RTTI Type Descriptor');
  }
  return result;
}

```

## disassembly

```asm
0x180002980  push    rbx
0x180002982  push    rbp
0x180002983  push    rsi
0x180002984  push    rdi
0x180002985  sub     rsp, 28h
0x180002989  mov     rbx, rdx
0x18000298c  mov     [rsp+48h+arg_10], 0
0x180002995  lea     rdx, [rsp+48h+arg_10]; void *
0x18000299a  mov     r8d, 8; unsigned __int64
0x1800029a0  lea     r9, ??_R0_K@8; struct type_info *
0x1800029a7  mov     rbp, rcx
0x1800029aa  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x1800029af  test    al, al
0x1800029b1  jz      short loc_180002A0F
0x1800029b3  mov     rax, [rbx]
0x1800029b6  mov     rsi, [rbx+8]
0x1800029ba  mov     rdi, [rsp+48h+arg_10]
0x1800029bf  sub     rsi, rax
0x1800029c2  cmp     rdi, rsi
0x1800029c5  ja      short loc_1800029D0
0x1800029c7  add     rax, rdi
0x1800029ca  mov     [rbx+8], rax
0x1800029ce  jmp     short loc_1800029FA
0x1800029d0  mov     rdx, rdi
0x1800029d3  mov     rcx, rbx
0x1800029d6  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1800029db  test    al, al
0x1800029dd  jz      short loc_1800029FA
0x1800029df  mov     rcx, [rbx+8]; void *
0x1800029e3  mov     r8, rdi
0x1800029e6  sub     r8, rsi; Size
0x1800029e9  xor     edx, edx; Val
0x1800029eb  call    memset_0
0x1800029f0  mov     rcx, [rbx]
0x1800029f3  add     rcx, rdi
0x1800029f6  mov     [rbx+8], rcx
0x1800029fa  mov     rdx, [rbx]; void *
0x1800029fd  lea     r9, ??_R0?AV?$vector@EV?$allocator@E@utl@@@utl@@@8; struct type_info *
0x180002a04  mov     r8, rdi; unsigned __int64
0x180002a07  mov     rcx, rbp; this
0x180002a0a  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x180002a0f  add     rsp, 28h
0x180002a13  pop     rdi
0x180002a14  pop     rsi
0x180002a15  pop     rbp
0x180002a16  pop     rbx
0x180002a17  retn
```
