# GBSendPath

- ea: `0x1800195a4`
- end: `0x18001971e`
- name: `GBSendPath`
- size: `378`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a660`
- `0x18000a8a0`
- `0x18000abb0`
- `0x180011ebc`

## callees

- `0x180016940`
- `0x180016bdc`
- `0x180016e24`
- `0x1800195a4`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x1800195e1`
- `GDI32!PATHOBJ_bEnum` at `0x1800195e1`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800195d3`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800195d3`

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
    OPSendOperator(a1, 15);
  PATHOBJ_vEnumStart(a2);
  do
  {
    v5 = PATHOBJ_bEnum(a2, &ppd);
    pptfx = ppd.pptfx;
    count = ppd.count;
    if ( (ppd.flags & 1) != 0 )
    {
      OPSendInt(a1, (unsigned int)(ppd.pptfx->x >> 4));
      OPSendInt(a1, (unsigned int)(pptfx->y >> 4));
      OPSendOperator(a1, 14);
      ++pptfx;
      --count;
    }
    if ( count > 0 )
    {
      if ( (ppd.flags & 0x10) != 0 )
      {
        do
        {
          OPSendInt(a1, (unsigned int)(pptfx->x >> 4));
          OPSendInt(a1, (unsigned int)(pptfx->y >> 4));
          OPSendInt(a1, (unsigned int)(pptfx[1].x >> 4));
          OPSendInt(a1, (unsigned int)(pptfx[1].y >> 4));
          OPSendInt(a1, (unsigned int)(pptfx[2].x >> 4));
          OPSendInt(a1, (unsigned int)(pptfx[2].y >> 4));
          pptfx += 3;
          OPSendOperator(a1, 6);
          count -= 3;
        }
        while ( count > 0 );
      }
      else
      {
        do
        {
          OPSendInt(a1, (unsigned int)(pptfx->x >> 4));
          OPSendInt(a1, (unsigned int)(pptfx->y >> 4));
          OPSendOperator(a1, 13);
          --count;
          ++pptfx;
        }
        while ( count > 0 );
      }
    }
    if ( (ppd.flags & 8) != 0 )
    {
      OPSendOperator(a1, 5);
      OPRawPortWrite(a1, "\r\n", 2);
    }
  }
  while ( v5 );
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x1800195a4  push    rbx
0x1800195a6  push    rbp
0x1800195a7  push    rsi
0x1800195a8  push    rdi
0x1800195a9  push    r14
0x1800195ab  sub     rsp, 30h
0x1800195af  cmp     dword ptr [rcx+86Ch], 0
0x1800195b6  xorps   xmm0, xmm0
0x1800195b9  movups  xmmword ptr [rsp+58h+ppd.flags], xmm0
0x1800195be  mov     rbp, rdx
0x1800195c1  mov     rbx, rcx
0x1800195c4  jnz     short loc_1800195D0
0x1800195c6  mov     edx, 0Fh
0x1800195cb  call    OPSendOperator
0x1800195d0  mov     rcx, rbp; ppo
0x1800195d3  call    cs:__imp_PATHOBJ_vEnumStart
0x1800195d9  lea     rdx, [rsp+58h+ppd]; ppd
0x1800195de  mov     rcx, rbp; ppo
0x1800195e1  call    cs:__imp_PATHOBJ_bEnum
0x1800195e7  test    byte ptr [rsp+58h+ppd.flags], 1
0x1800195ec  mov     r14d, eax
0x1800195ef  mov     rdi, [rsp+58h+ppd.pptfx]
0x1800195f4  mov     esi, [rsp+58h+ppd.count]
0x1800195f8  jz      short loc_180019628
0x1800195fa  mov     edx, [rdi]
0x1800195fc  mov     rcx, rbx
0x1800195ff  sar     edx, 4
0x180019602  call    OPSendInt
0x180019607  mov     edx, [rdi+4]
0x18001960a  mov     rcx, rbx
0x18001960d  sar     edx, 4
0x180019610  call    OPSendInt
0x180019615  mov     edx, 0Eh
0x18001961a  mov     rcx, rbx
0x18001961d  call    OPSendOperator
0x180019622  add     rdi, 8
0x180019626  dec     esi
0x180019628  test    esi, esi
0x18001962a  jle     loc_1800196D6
0x180019630  test    byte ptr [rsp+58h+ppd.flags], 10h
0x180019635  jz      short loc_1800196A4
0x180019637  mov     edx, [rdi]
0x180019639  mov     rcx, rbx
0x18001963c  sar     edx, 4
0x18001963f  call    OPSendInt
0x180019644  mov     edx, [rdi+4]
0x180019647  mov     rcx, rbx
0x18001964a  sar     edx, 4
0x18001964d  call    OPSendInt
0x180019652  mov     edx, [rdi+8]
0x180019655  mov     rcx, rbx
0x180019658  sar     edx, 4
0x18001965b  call    OPSendInt
0x180019660  mov     edx, [rdi+0Ch]
0x180019663  mov     rcx, rbx
0x180019666  sar     edx, 4
0x180019669  call    OPSendInt
0x18001966e  mov     edx, [rdi+10h]
0x180019671  mov     rcx, rbx
0x180019674  sar     edx, 4
0x180019677  call    OPSendInt
0x18001967c  mov     edx, [rdi+14h]
0x18001967f  mov     rcx, rbx
0x180019682  sar     edx, 4
0x180019685  call    OPSendInt
0x18001968a  mov     edx, 6
0x18001968f  lea     rdi, [rdi+18h]
0x180019693  mov     rcx, rbx
0x180019696  call    OPSendOperator
0x18001969b  sub     esi, 3
0x18001969e  test    esi, esi
0x1800196a0  jg      short loc_180019637
0x1800196a2  jmp     short loc_1800196D6
0x1800196a4  mov     edx, [rdi]
0x1800196a6  mov     rcx, rbx
0x1800196a9  sar     edx, 4
0x1800196ac  call    OPSendInt
0x1800196b1  mov     edx, [rdi+4]
0x1800196b4  mov     rcx, rbx
0x1800196b7  sar     edx, 4
0x1800196ba  call    OPSendInt
0x1800196bf  mov     edx, 0Dh
0x1800196c4  mov     rcx, rbx
0x1800196c7  call    OPSendOperator
0x1800196cc  dec     esi
0x1800196ce  lea     rdi, [rdi+8]
0x1800196d2  test    esi, esi
0x1800196d4  jg      short loc_1800196A4
0x1800196d6  test    byte ptr [rsp+58h+ppd.flags], 8
0x1800196db  jz      short loc_1800196FF
0x1800196dd  mov     edx, 5
0x1800196e2  mov     rcx, rbx
0x1800196e5  call    OPSendOperator
0x1800196ea  mov     r8d, 2
0x1800196f0  lea     rdx, gstrCRLF; "\r\n"
0x1800196f7  mov     rcx, rbx
0x1800196fa  call    OPRawPortWrite
0x1800196ff  test    r14d, r14d
0x180019702  jnz     loc_1800195D9
0x180019708  xor     eax, eax
0x18001970a  cmp     [rbx+0D70h], eax
0x180019710  setz    al
0x180019713  add     rsp, 30h
0x180019717  pop     r14
0x180019719  pop     rdi
0x18001971a  pop     rsi
0x18001971b  pop     rbp
0x18001971c  pop     rbx
0x18001971d  retn
```
