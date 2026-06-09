# DrvStrokeAndFillPath

- ea: `0x18000a8a0`
- end: `0x18000aba1`
- name: `DrvStrokeAndFillPath`
- size: `769`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pboStroke, LINEATTRS *plineattrs, BRUSHOBJ *pboFill, POINTL *pptlBrushOrg, MIX mixFill, FLONG flOptions)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180001ee0`
- `0x18000a488`
- `0x18000a8a0`
- `0x180011c50`
- `0x18001241c`
- `0x18001247c`
- `0x18001265c`
- `0x18001283c`
- `0x180015f84`
- `0x180016940`
- `0x180016e24`
- `0x180019094`
- `0x1800195a4`
- `0x18005d010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000aa72`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000aa72`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000aa5f`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000aa5f`

## pseudocode

```c
BOOL __stdcall DrvStrokeAndFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pboStroke,
        LINEATTRS *plineattrs,
        BRUSHOBJ *pboFill,
        POINTL *pptlBrushOrg,
        MIX mixFill,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rbx
  __int64 v14; // r11
  int v15; // eax
  BOOL result; // eax
  ULONG Xform; // edi
  struct _RECTFX prectfx; // [rsp+70h] [rbp-31h] BYREF
  XFORML pxform; // [rsp+80h] [rbp-21h] BYREF

  dhpdev = pso->dhpdev;
  prectfx = 0;
  if ( *(_DWORD *)(*((_QWORD *)dhpdev + 12) + 124LL) == 2 && *((_DWORD *)dhpdev + 543) > 1u
    || ((_DWORD)dhpdev[538] & 0xC0000000) != 0
    || *((_DWORD *)dhpdev + 176) == 3 )
  {
    return 1;
  }
  v14 = *((_QWORD *)dhpdev + 434);
  if ( v14 && *(_QWORD *)(v14 + 208) && (v15 = *((_DWORD *)dhpdev + 870), (v15 & 1) == 0) )
  {
    *((_DWORD *)dhpdev + 870) = v15 | 1;
    *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v14 + 216) + 32LL);
    *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v14 + 216) + 40LL);
    *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v14 + 216) + 56LL);
    result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *))(v14 + 208))(pso, ppo, pco);
    *((_DWORD *)dhpdev + 870) &= ~1u;
  }
  else if ( *((_DWORD *)dhpdev + 542) == 3 && (unsigned int)BDoMSEpsHackRect((__int64)dhpdev, (__int64)pco, ppo) )
  {
    *((_DWORD *)dhpdev + 542) = 2;
    return 1;
  }
  else
  {
    result = SMChangeState(dhpdev, 5);
    if ( result )
    {
      PSProcsetSend(dhpdev, 16);
      if ( *((int *)dhpdev + 539) > 0 || mixFill == 2827 )
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
        GSSendAttributes((_DWORD)dhpdev, -1, (_DWORD)pboStroke, (_DWORD)plineattrs, (__int64)pco, (__int64)&pxform);
        GBSendPath((__int64)dhpdev, ppo);
        GSSendGsave(dhpdev);
        GBPatternFill(
          dhpdev,
          pboFill,
          pptlBrushOrg,
          *((unsigned __int8 *)qword_180062928 + (mixFill & 0xF))
        | (*((unsigned __int8 *)qword_180062928 + ((mixFill >> 8) & 0xF)) << 8),
          flOptions);
        GSSendGrestore(dhpdev);
        if ( Xform )
        {
          GSSendGsave(dhpdev);
          GSSendXForm(dhpdev, pxo);
        }
        OPSendOperator(dhpdev, 27);
        OPRawPortWrite(dhpdev, "\r\n", 2);
        if ( Xform )
          GSSendGrestore(dhpdev);
        return *((_DWORD *)dhpdev + 860) == 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a8a0  push    rbp
0x18000a8a2  push    rbx
0x18000a8a3  push    rsi
0x18000a8a4  push    rdi
0x18000a8a5  push    r12
0x18000a8a7  push    r13
0x18000a8a9  push    r14
0x18000a8ab  push    r15
0x18000a8ad  lea     rbp, [rsp-7]
0x18000a8b2  sub     rsp, 0A8h
0x18000a8b9  mov     rax, cs:__security_cookie
0x18000a8c0  xor     rax, rsp
0x18000a8c3  mov     [rbp+3Fh+var_48], rax
0x18000a8c7  mov     rbx, [rcx+10h]
0x18000a8cb  xorps   xmm0, xmm0
0x18000a8ce  mov     r15, [rbp+3Fh+plineattrs]
0x18000a8d2  mov     r12, r8
0x18000a8d5  mov     r8, [rbp+3Fh+pptlBrushOrg]
0x18000a8dc  mov     rsi, rdx
0x18000a8df  mov     rdx, [rbp+3Fh+pboFill]
0x18000a8e3  mov     rdi, rcx
0x18000a8e6  mov     r13, [rbp+3Fh+pboStroke]
0x18000a8ea  mov     r14, r9
0x18000a8ed  movups  xmmword ptr [rbp+3Fh+prectfx.xLeft], xmm0
0x18000a8f1  mov     rax, [rbx+60h]
0x18000a8f5  mov     ecx, 1
0x18000a8fa  mov     [rbp+3Fh+var_78], rdx
0x18000a8fe  mov     [rbp+3Fh+var_80], r8
0x18000a902  cmp     dword ptr [rax+7Ch], 2
0x18000a906  jnz     short loc_18000A914
0x18000a908  cmp     [rbx+87Ch], ecx
0x18000a90e  ja      loc_18000AB7F
0x18000a914  test    dword ptr [rbx+868h], 0C0000000h
0x18000a91e  jnz     loc_18000AB7F
0x18000a924  cmp     dword ptr [rbx+2C0h], 3
0x18000a92b  jz      loc_18000AB7F
0x18000a931  mov     r11, [rbx+0D90h]
0x18000a938  test    r11, r11
0x18000a93b  jz      loc_18000A9D7
0x18000a941  cmp     qword ptr [r11+0D0h], 0
0x18000a949  jz      loc_18000A9D7
0x18000a94f  mov     eax, [rbx+0D98h]
0x18000a955  test    cl, al
0x18000a957  jnz     short loc_18000A9D7
0x18000a959  or      eax, ecx
0x18000a95b  mov     [rbx+0D98h], eax
0x18000a961  mov     rax, [r11+0D8h]
0x18000a968  mov     rcx, [rax+20h]
0x18000a96c  mov     [rbx+20h], rcx
0x18000a970  mov     rax, [r11+0D8h]
0x18000a977  mov     rcx, [rax+28h]
0x18000a97b  mov     [rbx+8], rcx
0x18000a97f  mov     rcx, rdi
0x18000a982  mov     rax, [r11+0D8h]
0x18000a989  mov     r10, [rax+38h]
0x18000a98d  mov     eax, [rbp+3Fh+flOptions]
0x18000a993  mov     [rsp+0E0h+var_98], eax
0x18000a997  mov     eax, [rbp+3Fh+mixFill]
0x18000a99d  mov     [rsp+0E0h+var_A0], eax
0x18000a9a1  mov     [rsp+0E0h+var_A8], r8
0x18000a9a6  mov     r8, r12
0x18000a9a9  mov     [rsp+0E0h+var_B0], rdx
0x18000a9ae  mov     rdx, rsi
0x18000a9b1  mov     [rbx+30h], r10
0x18000a9b5  mov     rax, [r11+0D0h]
0x18000a9bc  mov     [rsp+0E0h+var_B8], r15
0x18000a9c1  mov     [rsp+0E0h+var_C0], r13
0x18000a9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9cb  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000a9d2  jmp     loc_18000AB81
0x18000a9d7  cmp     dword ptr [rbx+878h], 3
0x18000a9de  jnz     short loc_18000AA06
0x18000a9e0  mov     r8, rsi
0x18000a9e3  mov     rdx, r12
0x18000a9e6  mov     rcx, rbx
0x18000a9e9  call    BDoMSEpsHackRect
0x18000a9ee  test    eax, eax
0x18000a9f0  jz      short loc_18000AA06
0x18000a9f2  mov     dword ptr [rbx+878h], 2
0x18000a9fc  mov     eax, 1
0x18000aa01  jmp     loc_18000AB81
0x18000aa06  mov     edx, 5
0x18000aa0b  mov     rcx, rbx
0x18000aa0e  call    SMChangeState
0x18000aa13  test    eax, eax
0x18000aa15  jz      loc_18000AB81
0x18000aa1b  mov     edx, 10h
0x18000aa20  mov     rcx, rbx
0x18000aa23  call    PSProcsetSend
0x18000aa28  cmp     dword ptr [rbx+86Ch], 0
0x18000aa2f  jg      loc_18000AB72
0x18000aa35  cmp     [rbp+3Fh+mixFill], 0B0Bh
0x18000aa3f  jz      loc_18000AB72
0x18000aa45  test    byte ptr [r15], 1
0x18000aa49  jz      short loc_18000AA69
0x18000aa4b  xorps   xmm0, xmm0
0x18000aa4e  lea     rdx, [rbp+3Fh+pxform]; pxform
0x18000aa52  xor     eax, eax
0x18000aa54  mov     rcx, r14; pxo
0x18000aa57  movups  xmmword ptr [rbp+3Fh+pxform.eM11], xmm0
0x18000aa5b  mov     qword ptr [rbp+3Fh+pxform.eDx], rax
0x18000aa5f  call    cs:__imp_XFORMOBJ_iGetXform
0x18000aa65  mov     edi, eax
0x18000aa67  jmp     short loc_18000AA6B
0x18000aa69  xor     edi, edi
0x18000aa6b  lea     rdx, [rbp+3Fh+prectfx]; prectfx
0x18000aa6f  mov     rcx, rsi; ppo
0x18000aa72  call    cs:__imp_PATHOBJ_vGetBounds
0x18000aa78  mov     eax, [rbp+3Fh+prectfx.xLeft]
0x18000aa7b  mov     r9, r15
0x18000aa7e  sar     eax, 4
0x18000aa81  mov     r8, r13
0x18000aa84  mov     [rbp+3Fh+pxform.eM11], eax
0x18000aa87  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000aa8b  mov     eax, [rbp+3Fh+prectfx.yTop]
0x18000aa8e  mov     rcx, rbx
0x18000aa91  sar     eax, 4
0x18000aa94  mov     [rbp+3Fh+pxform.eM12], eax
0x18000aa97  mov     eax, [rbp+3Fh+prectfx.xRight]
0x18000aa9a  add     eax, 10h
0x18000aa9d  sar     eax, 4
0x18000aaa0  mov     [rbp+3Fh+pxform.eM21], eax
0x18000aaa3  mov     eax, [rbp+3Fh+prectfx.yBottom]
0x18000aaa6  add     eax, 10h
0x18000aaa9  sar     eax, 4
0x18000aaac  mov     [rbp+3Fh+pxform.eM22], eax
0x18000aaaf  lea     rax, [rbp+3Fh+pxform]
0x18000aab3  mov     [rsp+0E0h+var_B8], rax
0x18000aab8  mov     [rsp+0E0h+var_C0], r12
0x18000aabd  call    GSSendAttributes
0x18000aac2  mov     rdx, rsi
0x18000aac5  mov     rcx, rbx
0x18000aac8  call    GBSendPath
0x18000aacd  mov     rcx, rbx
0x18000aad0  call    GSSendGsave
0x18000aad5  mov     ecx, [rbp+3Fh+mixFill]
0x18000aadb  lea     rdx, qword_180062928
0x18000aae2  mov     r8, [rbp+3Fh+var_80]
0x18000aae6  mov     eax, ecx
0x18000aae8  shr     rax, 8
0x18000aaec  and     ecx, 0Fh
0x18000aaef  and     eax, 0Fh
0x18000aaf2  movzx   r9d, byte ptr [rax+rdx]
0x18000aaf7  movzx   eax, byte ptr [rcx+rdx]
0x18000aafb  mov     rcx, rbx
0x18000aafe  mov     rdx, [rbp+3Fh+var_78]
0x18000ab02  shl     r9d, 8
0x18000ab06  or      r9d, eax
0x18000ab09  mov     eax, [rbp+3Fh+flOptions]
0x18000ab0f  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18000ab13  call    GBPatternFill
0x18000ab18  mov     rcx, rbx
0x18000ab1b  call    GSSendGrestore
0x18000ab20  test    edi, edi
0x18000ab22  jz      short loc_18000AB37
0x18000ab24  mov     rcx, rbx
0x18000ab27  call    GSSendGsave
0x18000ab2c  mov     rdx, r14
0x18000ab2f  mov     rcx, rbx
0x18000ab32  call    GSSendXForm
0x18000ab37  mov     edx, 1Bh
0x18000ab3c  mov     rcx, rbx
0x18000ab3f  call    OPSendOperator
0x18000ab44  mov     r8d, 2
0x18000ab4a  lea     rdx, gstrCRLF; "\r\n"
0x18000ab51  mov     rcx, rbx
0x18000ab54  call    OPRawPortWrite
0x18000ab59  test    edi, edi
0x18000ab5b  jz      short loc_18000AB65
0x18000ab5d  mov     rcx, rbx
0x18000ab60  call    GSSendGrestore
0x18000ab65  xor     eax, eax
0x18000ab67  cmp     [rbx+0D70h], eax
0x18000ab6d  setz    al
0x18000ab70  jmp     short loc_18000AB81
0x18000ab72  mov     rdx, rsi
0x18000ab75  mov     rcx, rbx
0x18000ab78  call    GBSendPath
0x18000ab7d  jmp     short loc_18000AB81
0x18000ab7f  mov     eax, ecx
0x18000ab81  mov     rcx, [rbp+3Fh+var_48]
0x18000ab85  xor     rcx, rsp; StackCookie
0x18000ab88  call    __security_check_cookie
0x18000ab8d  add     rsp, 0A8h
0x18000ab94  pop     r15
0x18000ab96  pop     r14
0x18000ab98  pop     r13
0x18000ab9a  pop     r12
0x18000ab9c  pop     rdi
0x18000ab9d  pop     rsi
0x18000ab9e  pop     rbx
0x18000ab9f  pop     rbp
0x18000aba0  retn
```
