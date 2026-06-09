# AtlAssignNoThrow(ATL::CComVariant &,ushort const *)

- ea: `0x180011eb8`
- end: `0x180011f5f`
- name: `?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z`
- size: `167`
- prototype: `void __fastcall(VARIANTARG *Destination, OLECHAR *psz)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d2c4`
- `0x1800125a4`
- `0x180013280`

## callees

- `0x18000201c`
- `0x180011eb8`
- `0x180011f68`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011eee`
- `OLEAUT32!__imp_SysAllocString` at `0x180011eee`
- `OLEAUT32!__imp_VariantClear` at `0x180011ec8`
- `OLEAUT32!__imp_VariantClear` at `0x180011efc`
- `OLEAUT32!__imp_VariantClear` at `0x180011ec8`
- `OLEAUT32!__imp_VariantClear` at `0x180011efc`

## pseudocode

```c
void __fastcall AtlAssignNoThrow(VARIANTARG *Destination, OLECHAR *psz)
{
  errno_t v4; // eax
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( VariantClear(Destination) >= 0 )
  {
    Source[2] = 0;
    Source[0] = 8;
    Source[1] = SysAllocString(psz);
    if ( VariantClear(Destination) >= 0 )
    {
      v4 = memcpy_s(Destination, 0x18u, Source, 0x18u);
      if ( v4 )
      {
        if ( v4 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v4 == 22 || v4 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v4 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
    }
  }
}

```

## disassembly

```asm
0x180011eb8  mov     [rsp+arg_0], rbx
0x180011ebd  push    rdi
0x180011ebe  sub     rsp, 40h
0x180011ec2  mov     rdi, rdx
0x180011ec5  mov     rbx, rcx
0x180011ec8  call    cs:__imp_VariantClear
0x180011ece  test    eax, eax
0x180011ed0  js      short loc_180011F33
0x180011ed2  xor     eax, eax
0x180011ed4  xorps   xmm0, xmm0
0x180011ed7  mov     [rsp+48h+var_18], rax
0x180011edc  mov     rcx, rdi; psz
0x180011edf  mov     eax, 8
0x180011ee4  movups  [rsp+48h+Source], xmm0
0x180011ee9  mov     word ptr [rsp+48h+Source], ax
0x180011eee  call    cs:__imp_SysAllocString
0x180011ef4  mov     rcx, rbx; pvarg
0x180011ef7  mov     qword ptr [rsp+48h+Source+8], rax
0x180011efc  call    cs:__imp_VariantClear
0x180011f02  test    eax, eax
0x180011f04  js      short loc_180011F33
0x180011f06  mov     edx, 18h; DestinationSize
0x180011f0b  lea     r8, [rsp+48h+Source]; Source
0x180011f10  mov     r9d, edx; SourceSize
0x180011f13  mov     rcx, rbx; Destination
0x180011f16  call    memcpy_s
0x180011f1b  test    eax, eax
0x180011f1d  jz      short loc_180011F33
0x180011f1f  cmp     eax, 0Ch
0x180011f22  jz      short loc_180011F54
0x180011f24  cmp     eax, 16h
0x180011f27  jz      short loc_180011F49
0x180011f29  cmp     eax, 22h ; '"'
0x180011f2c  jz      short loc_180011F49
0x180011f2e  cmp     eax, 50h ; 'P'
0x180011f31  jnz     short loc_180011F3E
0x180011f33  mov     rbx, [rsp+48h+arg_0]
0x180011f38  add     rsp, 40h
0x180011f3c  pop     rdi
0x180011f3d  retn
0x180011f3e  mov     ecx, 80004005h; int
0x180011f43  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011f49  mov     ecx, 80070057h; int
0x180011f4e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011f54  mov     ecx, 8007000Eh; int
0x180011f59  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
