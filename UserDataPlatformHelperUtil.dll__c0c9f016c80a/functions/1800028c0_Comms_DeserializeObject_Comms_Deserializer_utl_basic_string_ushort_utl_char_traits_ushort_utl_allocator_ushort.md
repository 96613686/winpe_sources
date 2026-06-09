# Comms::DeserializeObject(Comms::Deserializer &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800028c0`
- end: `0x180002970`
- name: `?DeserializeObject@Comms@@YA_NAEAVDeserializer@1@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `176`
- prototype: `bool __fastcall(Comms::Deserializer *this, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000116c`
- `0x180001178`
- `0x1800028c0`
- `0x180002cb0`
- `0x180002e90`

## pseudocode

```c
bool __fastcall Comms::DeserializeObject(Comms::Deserializer *this, _QWORD *a2)
{
  __int64 v4; // r14
  _WORD *v5; // rbx
  bool v6; // di
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  if ( !Comms::Deserializer::CopyBytesOut(
          this,
          &v8,
          8u,
          (const struct type_info *)&unsigned __int64 `RTTI Type Descriptor') )
    return 0;
  v4 = v8;
  v5 = operator new[](saturated_mul(v8 + 1, 2u));
  if ( !v5 )
    return 0;
  v5[v4] = 0;
  v6 = Comms::Deserializer::CopyBytesOut(
         this,
         v5,
         2 * v4,
         (const struct type_info *)&utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> `RTTI Type Descriptor')
    && utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(a2, v5);
  operator delete(v5);
  return v6;
}

```

## disassembly

```asm
0x1800028c0  push    rbx
0x1800028c2  push    rsi
0x1800028c3  push    rdi
0x1800028c4  push    r14
0x1800028c6  sub     rsp, 28h
0x1800028ca  mov     rsi, rdx
0x1800028cd  mov     [rsp+48h+arg_10], 0
0x1800028d6  lea     rdx, [rsp+48h+arg_10]; void *
0x1800028db  mov     r8d, 8; unsigned __int64
0x1800028e1  lea     r9, ??_R0_K@8; struct type_info *
0x1800028e8  mov     rdi, rcx
0x1800028eb  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x1800028f0  test    al, al
0x1800028f2  jz      short loc_180002964
0x1800028f4  mov     r14, [rsp+48h+arg_10]
0x1800028f9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002900  mov     eax, 2
0x180002905  lea     rdx, [r14+1]
0x180002909  mul     rdx
0x18000290c  cmovb   rax, rcx
0x180002910  mov     rcx, rax; unsigned __int64
0x180002913  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002918  mov     rbx, rax
0x18000291b  test    rax, rax
0x18000291e  jz      short loc_180002964
0x180002920  lea     r8, [r14+r14]; unsigned __int64
0x180002924  xor     eax, eax
0x180002926  lea     r9, ??_R0?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@8; struct type_info *
0x18000292d  mov     [r8+rbx], ax
0x180002932  mov     rdx, rbx; void *
0x180002935  mov     rcx, rdi; this
0x180002938  call    ?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z; Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)
0x18000293d  test    al, al
0x18000293f  jz      short loc_180002955
0x180002941  mov     rdx, rbx
0x180002944  mov     rcx, rsi
0x180002947  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000294c  test    al, al
0x18000294e  jz      short loc_180002955
0x180002950  mov     dil, 1
0x180002953  jmp     short loc_180002957
0x180002955  xor     edi, edi
0x180002957  mov     rcx, rbx; Block
0x18000295a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000295f  mov     al, dil
0x180002962  jmp     short loc_180002966
0x180002964  xor     al, al
0x180002966  add     rsp, 28h
0x18000296a  pop     r14
0x18000296c  pop     rdi
0x18000296d  pop     rsi
0x18000296e  pop     rbx
0x18000296f  retn
```
