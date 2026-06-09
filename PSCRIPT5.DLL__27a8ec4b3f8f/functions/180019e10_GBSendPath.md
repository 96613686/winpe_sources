# GBSendPath

- ea: `0x180019e10`
- end: `0x180019f97`
- name: `GBSendPath`
- size: `391`
- prototype: `_BOOL8 __fastcall(__int64, PATHOBJ *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aa00`
- `0x18000ac50`
- `0x18000af70`
- `0x180012470`

## callees

- `0x1800170a0`
- `0x180017340`
- `0x18001758c`
- `0x180019e10`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x180019e53`
- `GDI32!PATHOBJ_bEnum` at `0x180019e53`
- `GDI32!PATHOBJ_vEnumStart` at `0x180019e3f`
- `GDI32!PATHOBJ_vEnumStart` at `0x180019e3f`

## pseudocode

```c
_BOOL8 __fastcall GBSendPath(__int64 a1, PATHOBJ *a2)
{
  bool v2; // zf
  BOOL v5; // r14d
  POINTFIX *pptfx; // rdi
  signed int count; // esi
  PATHDATA ppd; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(_DWORD *)(a1 + 2156) == 0;
  ppd = 0;
  if ( v2 )
    OPSendOperator(a1, 0xFu);
  PATHOBJ_vEnumStart(a2);
  do
  {
    v5 = PATHOBJ_bEnum(a2, &ppd);
    pptfx = ppd.pptfx;
    count = ppd.count;
    if ( (ppd.flags & 1) != 0 )
    {
      OPSendInt(a1, ppd.pptfx->x >> 4);
      OPSendInt(a1, pptfx->y >> 4);
      OPSendOperator(a1, 0xEu);
      ++pptfx;
      --count;
    }
    if ( count > 0 )
    {
      if ( (ppd.flags & 0x10) != 0 )
      {
        do
        {
          OPSendInt(a1, pptfx->x >> 4);
          OPSendInt(a1, pptfx->y >> 4);
          OPSendInt(a1, pptfx[1].x >> 4);
          OPSendInt(a1, pptfx[1].y >> 4);
          OPSendInt(a1, pptfx[2].x >> 4);
          OPSendInt(a1, pptfx[2].y >> 4);
          pptfx += 3;
          OPSendOperator(a1, 6u);
          count -= 3;
        }
        while ( count > 0 );
      }
      else
      {
        do
        {
          OPSendInt(a1, pptfx->x >> 4);
          OPSendInt(a1, pptfx->y >> 4);
          OPSendOperator(a1, 0xDu);
          --count;
          ++pptfx;
        }
        while ( count > 0 );
      }
    }
    if ( (ppd.flags & 8) != 0 )
    {
      OPSendOperator(a1, 5u);
      OPRawPortWrite(a1, "\r\n", 2u);
    }
  }
  while ( v5 );
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180019e10  push    rbx
0x180019e12  push    rbp
0x180019e13  push    rsi
0x180019e14  push    rdi
0x180019e15  push    r14
0x180019e17  sub     rsp, 30h
0x180019e1b  cmp     dword ptr [rcx+86Ch], 0
0x180019e22  xorps   xmm0, xmm0
0x180019e25  movups  xmmword ptr [rsp+58h+ppd.flags], xmm0
0x180019e2a  mov     rbp, rdx
0x180019e2d  mov     rbx, rcx
0x180019e30  jnz     short loc_180019E3C
0x180019e32  mov     edx, 0Fh
0x180019e37  call    OPSendOperator
0x180019e3c  mov     rcx, rbp; ppo
0x180019e3f  call    cs:__imp_PATHOBJ_vEnumStart
0x180019e46  nop     dword ptr [rax+rax+00h]
0x180019e4b  lea     rdx, [rsp+58h+ppd]; ppd
0x180019e50  mov     rcx, rbp; ppo
0x180019e53  call    cs:__imp_PATHOBJ_bEnum
0x180019e5a  nop     dword ptr [rax+rax+00h]
0x180019e5f  test    byte ptr [rsp+58h+ppd.flags], 1
0x180019e64  mov     r14d, eax
0x180019e67  mov     rdi, [rsp+58h+ppd.pptfx]
0x180019e6c  mov     esi, [rsp+58h+ppd.count]
0x180019e70  jz      short loc_180019EA0
0x180019e72  mov     edx, [rdi]
0x180019e74  mov     rcx, rbx
0x180019e77  sar     edx, 4
0x180019e7a  call    OPSendInt
0x180019e7f  mov     edx, [rdi+4]
0x180019e82  mov     rcx, rbx
0x180019e85  sar     edx, 4
0x180019e88  call    OPSendInt
0x180019e8d  mov     edx, 0Eh
0x180019e92  mov     rcx, rbx
0x180019e95  call    OPSendOperator
0x180019e9a  add     rdi, 8
0x180019e9e  dec     esi
0x180019ea0  test    esi, esi
0x180019ea2  jle     loc_180019F4E
0x180019ea8  test    byte ptr [rsp+58h+ppd.flags], 10h
0x180019ead  jz      short loc_180019F1C
0x180019eaf  mov     edx, [rdi]
0x180019eb1  mov     rcx, rbx
0x180019eb4  sar     edx, 4
0x180019eb7  call    OPSendInt
0x180019ebc  mov     edx, [rdi+4]
0x180019ebf  mov     rcx, rbx
0x180019ec2  sar     edx, 4
0x180019ec5  call    OPSendInt
0x180019eca  mov     edx, [rdi+8]
0x180019ecd  mov     rcx, rbx
0x180019ed0  sar     edx, 4
0x180019ed3  call    OPSendInt
0x180019ed8  mov     edx, [rdi+0Ch]
0x180019edb  mov     rcx, rbx
0x180019ede  sar     edx, 4
0x180019ee1  call    OPSendInt
0x180019ee6  mov     edx, [rdi+10h]
0x180019ee9  mov     rcx, rbx
0x180019eec  sar     edx, 4
0x180019eef  call    OPSendInt
0x180019ef4  mov     edx, [rdi+14h]
0x180019ef7  mov     rcx, rbx
0x180019efa  sar     edx, 4
0x180019efd  call    OPSendInt
0x180019f02  mov     edx, 6
0x180019f07  lea     rdi, [rdi+18h]
0x180019f0b  mov     rcx, rbx
0x180019f0e  call    OPSendOperator
0x180019f13  sub     esi, 3
0x180019f16  test    esi, esi
0x180019f18  jg      short loc_180019EAF
0x180019f1a  jmp     short loc_180019F4E
0x180019f1c  mov     edx, [rdi]
0x180019f1e  mov     rcx, rbx
0x180019f21  sar     edx, 4
0x180019f24  call    OPSendInt
0x180019f29  mov     edx, [rdi+4]
0x180019f2c  mov     rcx, rbx
0x180019f2f  sar     edx, 4
0x180019f32  call    OPSendInt
0x180019f37  mov     edx, 0Dh
0x180019f3c  mov     rcx, rbx
0x180019f3f  call    OPSendOperator
0x180019f44  dec     esi
0x180019f46  lea     rdi, [rdi+8]
0x180019f4a  test    esi, esi
0x180019f4c  jg      short loc_180019F1C
0x180019f4e  test    byte ptr [rsp+58h+ppd.flags], 8
0x180019f53  jz      short loc_180019F77
0x180019f55  mov     edx, 5
0x180019f5a  mov     rcx, rbx
0x180019f5d  call    OPSendOperator
0x180019f62  mov     r8d, 2
0x180019f68  lea     rdx, gstrCRLF; "\r\n"
0x180019f6f  mov     rcx, rbx
0x180019f72  call    OPRawPortWrite
0x180019f77  test    r14d, r14d
0x180019f7a  jnz     loc_180019E4B
0x180019f80  xor     eax, eax
0x180019f82  cmp     [rbx+0D70h], eax
0x180019f88  setz    al
0x180019f8b  add     rsp, 30h
0x180019f8f  pop     r14
0x180019f91  pop     rdi
0x180019f92  pop     rsi
0x180019f93  pop     rbp
0x180019f94  pop     rbx
0x180019f95  retn
```
