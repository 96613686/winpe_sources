# DrvStrokePath

- ea: `0x18000af70`
- end: `0x18000b206`
- name: `DrvStrokePath`
- size: `662`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, LINEATTRS *plineattrs, MIX mix)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001f20`
- `0x18000a81c`
- `0x18000af70`
- `0x180012200`
- `0x1800129f0`
- `0x180012a50`
- `0x180012c30`
- `0x180012e18`
- `0x1800166c0`
- `0x1800170a0`
- `0x18001758c`
- `0x180019e10`
- `0x18005f010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000b123`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000b123`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000b10a`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000b10a`

## pseudocode

```c
BOOL __stdcall DrvStrokePath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        LINEATTRS *plineattrs,
        MIX mix)
{
  DHPDEV dhpdev; // rbx
  __int64 v12; // r11
  int v13; // eax
  BOOL result; // eax
  ULONG Xform; // edi
  struct _RECTFX prectfx; // [rsp+50h] [rbp-31h] BYREF
  XFORML pxform; // [rsp+60h] [rbp-21h] BYREF

  dhpdev = pso->dhpdev;
  prectfx = 0;
  if ( *(_DWORD *)(*((_QWORD *)dhpdev + 12) + 124LL) == 2 && *((_DWORD *)dhpdev + 543) > 1u
    || ((_DWORD)dhpdev[538] & 0xC0000000) != 0
    || *((_DWORD *)dhpdev + 176) == 3 )
  {
    return 1;
  }
  v12 = *((_QWORD *)dhpdev + 434);
  if ( v12 && *(_QWORD *)(v12 + 176) && (v13 = *((_DWORD *)dhpdev + 870), (v13 & 1) == 0) )
  {
    *((_DWORD *)dhpdev + 870) = v13 | 1;
    *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v12 + 184) + 32LL);
    *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v12 + 184) + 40LL);
    *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v12 + 184) + 56LL);
    result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *))(v12 + 176))(pso, ppo);
    *((_DWORD *)dhpdev + 870) &= ~1u;
  }
  else if ( *((_DWORD *)dhpdev + 542) == 3 && (unsigned int)BDoMSEpsHackRect((__int64)dhpdev, (__int64)pco, ppo) )
  {
    *((_DWORD *)dhpdev + 542) = 2;
    return 1;
  }
  else
  {
    result = SMChangeState((__int64)dhpdev, 5);
    if ( result )
    {
      PSProcsetSend(dhpdev, 16);
      if ( *((int *)dhpdev + 539) > 0 || mix == 2827 )
      {
        return GBSendPath((__int64)dhpdev, ppo);
      }
      else
      {
        if ( (plineattrs->fl & 1) != 0 )
        {
          memset(&pxform, 0, sizeof(pxform));
          Xform = XFORMOBJ_iGetXform(pxo, &pxform);
        }
        else
        {
          Xform = 0;
        }
        PATHOBJ_vGetBounds(ppo, &prectfx);
        LODWORD(pxform.eM11) = prectfx.xLeft >> 4;
        LODWORD(pxform.eM12) = prectfx.yTop >> 4;
        LODWORD(pxform.eM21) = (prectfx.xRight + 16) >> 4;
        LODWORD(pxform.eM22) = (prectfx.yBottom + 16) >> 4;
        GSSendAttributes((__int64)dhpdev, -1, (__int64)pbo, (__int64)plineattrs, (__int64)pco, &pxform);
        GBSendPath((__int64)dhpdev, ppo);
        if ( Xform )
        {
          GSSendGsave((__int64)dhpdev);
          GSSendXForm((__int64)dhpdev, pxo);
        }
        OPSendOperator((__int64)dhpdev, 0x1Bu);
        OPRawPortWrite((__int64)dhpdev, "\r\n", 2u);
        if ( Xform )
          GSSendGrestore((__int64)dhpdev);
        return *((_DWORD *)dhpdev + 860) == 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000af70  push    rbp
0x18000af72  push    rbx
0x18000af73  push    rsi
0x18000af74  push    rdi
0x18000af75  push    r12
0x18000af77  push    r13
0x18000af79  push    r14
0x18000af7b  push    r15
0x18000af7d  lea     rbp, [rsp-7]
0x18000af82  sub     rsp, 88h
0x18000af89  mov     rax, cs:__security_cookie
0x18000af90  xor     rax, rsp
0x18000af93  mov     [rbp+3Fh+var_48], rax
0x18000af97  mov     rbx, [rcx+10h]
0x18000af9b  xorps   xmm0, xmm0
0x18000af9e  mov     r15, [rbp+3Fh+plineattrs]
0x18000afa2  mov     rsi, rdx
0x18000afa5  mov     r13, [rbp+3Fh+pbo]
0x18000afa9  mov     rdi, rcx
0x18000afac  mov     rdx, [rbp+3Fh+pptlBrushOrg]
0x18000afb0  mov     r14, r9
0x18000afb3  movups  xmmword ptr [rbp+3Fh+prectfx.xLeft], xmm0
0x18000afb7  mov     rax, [rbx+60h]
0x18000afbb  mov     r12, r8
0x18000afbe  mov     ecx, 1
0x18000afc3  cmp     dword ptr [rax+7Ch], 2
0x18000afc7  jnz     short loc_18000AFD5
0x18000afc9  cmp     [rbx+87Ch], ecx
0x18000afcf  ja      loc_18000B1E3
0x18000afd5  test    dword ptr [rbx+868h], 0C0000000h
0x18000afdf  jnz     loc_18000B1E3
0x18000afe5  cmp     dword ptr [rbx+2C0h], 3
0x18000afec  jz      loc_18000B1E3
0x18000aff2  mov     r11, [rbx+0D90h]
0x18000aff9  test    r11, r11
0x18000affc  jz      loc_18000B082
0x18000b002  cmp     qword ptr [r11+0B0h], 0
0x18000b00a  jz      short loc_18000B082
0x18000b00c  mov     eax, [rbx+0D98h]
0x18000b012  test    cl, al
0x18000b014  jnz     short loc_18000B082
0x18000b016  or      eax, ecx
0x18000b018  mov     [rbx+0D98h], eax
0x18000b01e  mov     rax, [r11+0B8h]
0x18000b025  mov     rcx, [rax+20h]
0x18000b029  mov     [rbx+20h], rcx
0x18000b02d  mov     rcx, rdi
0x18000b030  mov     rax, [r11+0B8h]
0x18000b037  mov     r10, [rax+28h]
0x18000b03b  mov     [rbx+8], r10
0x18000b03f  mov     rax, [r11+0B8h]
0x18000b046  mov     r10, [rax+38h]
0x18000b04a  mov     eax, [rbp+3Fh+mix]
0x18000b050  mov     [rsp+0C0h+var_88], eax
0x18000b054  mov     [rsp+0C0h+var_90], r15
0x18000b059  mov     [rsp+0C0h+var_98], rdx
0x18000b05e  mov     rdx, rsi
0x18000b061  mov     [rbx+30h], r10
0x18000b065  mov     rax, [r11+0B0h]
0x18000b06c  mov     [rsp+0C0h+var_A0], r13
0x18000b071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b076  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000b07d  jmp     loc_18000B1E5
0x18000b082  cmp     dword ptr [rbx+878h], 3
0x18000b089  jnz     short loc_18000B0B1
0x18000b08b  mov     r8, rsi
0x18000b08e  mov     rdx, r12
0x18000b091  mov     rcx, rbx
0x18000b094  call    BDoMSEpsHackRect
0x18000b099  test    eax, eax
0x18000b09b  jz      short loc_18000B0B1
0x18000b09d  mov     dword ptr [rbx+878h], 2
0x18000b0a7  mov     eax, 1
0x18000b0ac  jmp     loc_18000B1E5
0x18000b0b1  mov     edx, 5
0x18000b0b6  mov     rcx, rbx
0x18000b0b9  call    SMChangeState
0x18000b0be  test    eax, eax
0x18000b0c0  jz      loc_18000B1E5
0x18000b0c6  mov     edx, 10h
0x18000b0cb  mov     rcx, rbx
0x18000b0ce  call    PSProcsetSend
0x18000b0d3  cmp     dword ptr [rbx+86Ch], 0
0x18000b0da  jg      loc_18000B1D6
0x18000b0e0  cmp     [rbp+3Fh+mix], 0B0Bh
0x18000b0ea  jz      loc_18000B1D6
0x18000b0f0  test    byte ptr [r15], 1
0x18000b0f4  jz      short loc_18000B11A
0x18000b0f6  xorps   xmm0, xmm0
0x18000b0f9  lea     rdx, [rbp+3Fh+pxform]; pxform
0x18000b0fd  xor     eax, eax
0x18000b0ff  mov     rcx, r14; pxo
0x18000b102  movups  xmmword ptr [rbp+3Fh+pxform.eM11], xmm0
0x18000b106  mov     qword ptr [rbp+3Fh+pxform.eDx], rax
0x18000b10a  call    cs:__imp_XFORMOBJ_iGetXform
0x18000b111  nop     dword ptr [rax+rax+00h]
0x18000b116  mov     edi, eax
0x18000b118  jmp     short loc_18000B11C
0x18000b11a  xor     edi, edi
0x18000b11c  lea     rdx, [rbp+3Fh+prectfx]; prectfx
0x18000b120  mov     rcx, rsi; ppo
0x18000b123  call    cs:__imp_PATHOBJ_vGetBounds
0x18000b12a  nop     dword ptr [rax+rax+00h]
0x18000b12f  mov     eax, [rbp+3Fh+prectfx.xLeft]
0x18000b132  mov     r9, r15
0x18000b135  sar     eax, 4
0x18000b138  mov     r8, r13
0x18000b13b  mov     [rbp+3Fh+pxform.eM11], eax
0x18000b13e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b142  mov     eax, [rbp+3Fh+prectfx.yTop]
0x18000b145  mov     rcx, rbx
0x18000b148  sar     eax, 4
0x18000b14b  mov     [rbp+3Fh+pxform.eM12], eax
0x18000b14e  mov     eax, [rbp+3Fh+prectfx.xRight]
0x18000b151  add     eax, 10h
0x18000b154  sar     eax, 4
0x18000b157  mov     [rbp+3Fh+pxform.eM21], eax
0x18000b15a  mov     eax, [rbp+3Fh+prectfx.yBottom]
0x18000b15d  add     eax, 10h
0x18000b160  sar     eax, 4
0x18000b163  mov     [rbp+3Fh+pxform.eM22], eax
0x18000b166  lea     rax, [rbp+3Fh+pxform]
0x18000b16a  mov     [rsp+0C0h+var_98], rax
0x18000b16f  mov     [rsp+0C0h+var_A0], r12
0x18000b174  call    GSSendAttributes
0x18000b179  mov     rdx, rsi
0x18000b17c  mov     rcx, rbx
0x18000b17f  call    GBSendPath
0x18000b184  test    edi, edi
0x18000b186  jz      short loc_18000B19B
0x18000b188  mov     rcx, rbx
0x18000b18b  call    GSSendGsave
0x18000b190  mov     rdx, r14
0x18000b193  mov     rcx, rbx
0x18000b196  call    GSSendXForm
0x18000b19b  mov     edx, 1Bh
0x18000b1a0  mov     rcx, rbx
0x18000b1a3  call    OPSendOperator
0x18000b1a8  mov     r8d, 2
0x18000b1ae  lea     rdx, gstrCRLF; "\r\n"
0x18000b1b5  mov     rcx, rbx
0x18000b1b8  call    OPRawPortWrite
0x18000b1bd  test    edi, edi
0x18000b1bf  jz      short loc_18000B1C9
0x18000b1c1  mov     rcx, rbx
0x18000b1c4  call    GSSendGrestore
0x18000b1c9  xor     eax, eax
0x18000b1cb  cmp     [rbx+0D70h], eax
0x18000b1d1  setz    al
0x18000b1d4  jmp     short loc_18000B1E5
0x18000b1d6  mov     rdx, rsi
0x18000b1d9  mov     rcx, rbx
0x18000b1dc  call    GBSendPath
0x18000b1e1  jmp     short loc_18000B1E5
0x18000b1e3  mov     eax, ecx
0x18000b1e5  mov     rcx, [rbp+3Fh+var_48]
0x18000b1e9  xor     rcx, rsp; StackCookie
0x18000b1ec  call    __security_check_cookie
0x18000b1f1  add     rsp, 88h
0x18000b1f8  pop     r15
0x18000b1fa  pop     r14
0x18000b1fc  pop     r13
0x18000b1fe  pop     r12
0x18000b200  pop     rdi
0x18000b201  pop     rsi
0x18000b202  pop     rbx
0x18000b203  pop     rbp
0x18000b204  retn
```
