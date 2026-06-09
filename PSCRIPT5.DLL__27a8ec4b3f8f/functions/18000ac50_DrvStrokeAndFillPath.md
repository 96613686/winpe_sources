# DrvStrokeAndFillPath

- ea: `0x18000ac50`
- end: `0x18000af5e`
- name: `DrvStrokeAndFillPath`
- size: `782`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pboStroke, LINEATTRS *plineattrs, BRUSHOBJ *pboFill, POINTL *pptlBrushOrg, MIX mixFill, FLONG flOptions)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180001f20`
- `0x18000a81c`
- `0x18000ac50`
- `0x180012200`
- `0x1800129f0`
- `0x180012a50`
- `0x180012c30`
- `0x180012e18`
- `0x1800166c0`
- `0x1800170a0`
- `0x18001758c`
- `0x1800198f8`
- `0x180019e10`
- `0x18005f010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000ae28`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000ae28`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000ae0f`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000ae0f`

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
    result = SMChangeState((__int64)dhpdev, 5);
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
        GSSendAttributes((__int64)dhpdev, -1, (__int64)pboStroke, (__int64)plineattrs, (__int64)pco, &pxform);
        GBSendPath((__int64)dhpdev, ppo);
        GSSendGsave((__int64)dhpdev);
        GBPatternFill(
          (__int64)dhpdev,
          (__int64)pboFill,
          (int *)pptlBrushOrg,
          *((unsigned __int8 *)qword_180064918 + (mixFill & 0xF))
        | (*((unsigned __int8 *)qword_180064918 + ((mixFill >> 8) & 0xF)) << 8),
          flOptions);
        GSSendGrestore((__int64)dhpdev);
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
0x18000ac50  push    rbp
0x18000ac52  push    rbx
0x18000ac53  push    rsi
0x18000ac54  push    rdi
0x18000ac55  push    r12
0x18000ac57  push    r13
0x18000ac59  push    r14
0x18000ac5b  push    r15
0x18000ac5d  lea     rbp, [rsp-7]
0x18000ac62  sub     rsp, 0A8h
0x18000ac69  mov     rax, cs:__security_cookie
0x18000ac70  xor     rax, rsp
0x18000ac73  mov     [rbp+3Fh+var_48], rax
0x18000ac77  mov     rbx, [rcx+10h]
0x18000ac7b  xorps   xmm0, xmm0
0x18000ac7e  mov     r15, [rbp+3Fh+plineattrs]
0x18000ac82  mov     r12, r8
0x18000ac85  mov     r8, [rbp+3Fh+pptlBrushOrg]
0x18000ac8c  mov     rsi, rdx
0x18000ac8f  mov     rdx, [rbp+3Fh+pboFill]
0x18000ac93  mov     rdi, rcx
0x18000ac96  mov     r13, [rbp+3Fh+pboStroke]
0x18000ac9a  mov     r14, r9
0x18000ac9d  movups  xmmword ptr [rbp+3Fh+prectfx.xLeft], xmm0
0x18000aca1  mov     rax, [rbx+60h]
0x18000aca5  mov     ecx, 1
0x18000acaa  mov     [rbp+3Fh+var_78], rdx
0x18000acae  mov     [rbp+3Fh+var_80], r8
0x18000acb2  cmp     dword ptr [rax+7Ch], 2
0x18000acb6  jnz     short loc_18000ACC4
0x18000acb8  cmp     [rbx+87Ch], ecx
0x18000acbe  ja      loc_18000AF3B
0x18000acc4  test    dword ptr [rbx+868h], 0C0000000h
0x18000acce  jnz     loc_18000AF3B
0x18000acd4  cmp     dword ptr [rbx+2C0h], 3
0x18000acdb  jz      loc_18000AF3B
0x18000ace1  mov     r11, [rbx+0D90h]
0x18000ace8  test    r11, r11
0x18000aceb  jz      loc_18000AD87
0x18000acf1  cmp     qword ptr [r11+0D0h], 0
0x18000acf9  jz      loc_18000AD87
0x18000acff  mov     eax, [rbx+0D98h]
0x18000ad05  test    cl, al
0x18000ad07  jnz     short loc_18000AD87
0x18000ad09  or      eax, ecx
0x18000ad0b  mov     [rbx+0D98h], eax
0x18000ad11  mov     rax, [r11+0D8h]
0x18000ad18  mov     rcx, [rax+20h]
0x18000ad1c  mov     [rbx+20h], rcx
0x18000ad20  mov     rax, [r11+0D8h]
0x18000ad27  mov     rcx, [rax+28h]
0x18000ad2b  mov     [rbx+8], rcx
0x18000ad2f  mov     rcx, rdi
0x18000ad32  mov     rax, [r11+0D8h]
0x18000ad39  mov     r10, [rax+38h]
0x18000ad3d  mov     eax, [rbp+3Fh+flOptions]
0x18000ad43  mov     [rsp+0E0h+var_98], eax
0x18000ad47  mov     eax, [rbp+3Fh+mixFill]
0x18000ad4d  mov     [rsp+0E0h+var_A0], eax
0x18000ad51  mov     [rsp+0E0h+var_A8], r8
0x18000ad56  mov     r8, r12
0x18000ad59  mov     [rsp+0E0h+var_B0], rdx
0x18000ad5e  mov     rdx, rsi
0x18000ad61  mov     [rbx+30h], r10
0x18000ad65  mov     rax, [r11+0D0h]
0x18000ad6c  mov     [rsp+0E0h+var_B8], r15
0x18000ad71  mov     [rsp+0E0h+var_C0], r13
0x18000ad76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7b  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000ad82  jmp     loc_18000AF3D
0x18000ad87  cmp     dword ptr [rbx+878h], 3
0x18000ad8e  jnz     short loc_18000ADB6
0x18000ad90  mov     r8, rsi
0x18000ad93  mov     rdx, r12
0x18000ad96  mov     rcx, rbx
0x18000ad99  call    BDoMSEpsHackRect
0x18000ad9e  test    eax, eax
0x18000ada0  jz      short loc_18000ADB6
0x18000ada2  mov     dword ptr [rbx+878h], 2
0x18000adac  mov     eax, 1
0x18000adb1  jmp     loc_18000AF3D
0x18000adb6  mov     edx, 5
0x18000adbb  mov     rcx, rbx
0x18000adbe  call    SMChangeState
0x18000adc3  test    eax, eax
0x18000adc5  jz      loc_18000AF3D
0x18000adcb  mov     edx, 10h
0x18000add0  mov     rcx, rbx
0x18000add3  call    PSProcsetSend
0x18000add8  cmp     dword ptr [rbx+86Ch], 0
0x18000addf  jg      loc_18000AF2E
0x18000ade5  cmp     [rbp+3Fh+mixFill], 0B0Bh
0x18000adef  jz      loc_18000AF2E
0x18000adf5  test    byte ptr [r15], 1
0x18000adf9  jz      short loc_18000AE1F
0x18000adfb  xorps   xmm0, xmm0
0x18000adfe  lea     rdx, [rbp+3Fh+pxform]; pxform
0x18000ae02  xor     eax, eax
0x18000ae04  mov     rcx, r14; pxo
0x18000ae07  movups  xmmword ptr [rbp+3Fh+pxform.eM11], xmm0
0x18000ae0b  mov     qword ptr [rbp+3Fh+pxform.eDx], rax
0x18000ae0f  call    cs:__imp_XFORMOBJ_iGetXform
0x18000ae16  nop     dword ptr [rax+rax+00h]
0x18000ae1b  mov     edi, eax
0x18000ae1d  jmp     short loc_18000AE21
0x18000ae1f  xor     edi, edi
0x18000ae21  lea     rdx, [rbp+3Fh+prectfx]; prectfx
0x18000ae25  mov     rcx, rsi; ppo
0x18000ae28  call    cs:__imp_PATHOBJ_vGetBounds
0x18000ae2f  nop     dword ptr [rax+rax+00h]
0x18000ae34  mov     eax, [rbp+3Fh+prectfx.xLeft]
0x18000ae37  mov     r9, r15
0x18000ae3a  sar     eax, 4
0x18000ae3d  mov     r8, r13
0x18000ae40  mov     [rbp+3Fh+pxform.eM11], eax
0x18000ae43  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ae47  mov     eax, [rbp+3Fh+prectfx.yTop]
0x18000ae4a  mov     rcx, rbx
0x18000ae4d  sar     eax, 4
0x18000ae50  mov     [rbp+3Fh+pxform.eM12], eax
0x18000ae53  mov     eax, [rbp+3Fh+prectfx.xRight]
0x18000ae56  add     eax, 10h
0x18000ae59  sar     eax, 4
0x18000ae5c  mov     [rbp+3Fh+pxform.eM21], eax
0x18000ae5f  mov     eax, [rbp+3Fh+prectfx.yBottom]
0x18000ae62  add     eax, 10h
0x18000ae65  sar     eax, 4
0x18000ae68  mov     [rbp+3Fh+pxform.eM22], eax
0x18000ae6b  lea     rax, [rbp+3Fh+pxform]
0x18000ae6f  mov     [rsp+0E0h+var_B8], rax
0x18000ae74  mov     [rsp+0E0h+var_C0], r12
0x18000ae79  call    GSSendAttributes
0x18000ae7e  mov     rdx, rsi
0x18000ae81  mov     rcx, rbx
0x18000ae84  call    GBSendPath
0x18000ae89  mov     rcx, rbx
0x18000ae8c  call    GSSendGsave
0x18000ae91  mov     ecx, [rbp+3Fh+mixFill]
0x18000ae97  lea     rdx, qword_180064918
0x18000ae9e  mov     r8, [rbp+3Fh+var_80]
0x18000aea2  mov     eax, ecx
0x18000aea4  shr     rax, 8
0x18000aea8  and     ecx, 0Fh
0x18000aeab  and     eax, 0Fh
0x18000aeae  movzx   r9d, byte ptr [rax+rdx]
0x18000aeb3  movzx   eax, byte ptr [rcx+rdx]
0x18000aeb7  mov     rcx, rbx
0x18000aeba  mov     rdx, [rbp+3Fh+var_78]
0x18000aebe  shl     r9d, 8
0x18000aec2  or      r9d, eax
0x18000aec5  mov     eax, [rbp+3Fh+flOptions]
0x18000aecb  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18000aecf  call    GBPatternFill
0x18000aed4  mov     rcx, rbx
0x18000aed7  call    GSSendGrestore
0x18000aedc  test    edi, edi
0x18000aede  jz      short loc_18000AEF3
0x18000aee0  mov     rcx, rbx
0x18000aee3  call    GSSendGsave
0x18000aee8  mov     rdx, r14
0x18000aeeb  mov     rcx, rbx
0x18000aeee  call    GSSendXForm
0x18000aef3  mov     edx, 1Bh
0x18000aef8  mov     rcx, rbx
0x18000aefb  call    OPSendOperator
0x18000af00  mov     r8d, 2
0x18000af06  lea     rdx, gstrCRLF; "\r\n"
0x18000af0d  mov     rcx, rbx
0x18000af10  call    OPRawPortWrite
0x18000af15  test    edi, edi
0x18000af17  jz      short loc_18000AF21
0x18000af19  mov     rcx, rbx
0x18000af1c  call    GSSendGrestore
0x18000af21  xor     eax, eax
0x18000af23  cmp     [rbx+0D70h], eax
0x18000af29  setz    al
0x18000af2c  jmp     short loc_18000AF3D
0x18000af2e  mov     rdx, rsi
0x18000af31  mov     rcx, rbx
0x18000af34  call    GBSendPath
0x18000af39  jmp     short loc_18000AF3D
0x18000af3b  mov     eax, ecx
0x18000af3d  mov     rcx, [rbp+3Fh+var_48]
0x18000af41  xor     rcx, rsp; StackCookie
0x18000af44  call    __security_check_cookie
0x18000af49  add     rsp, 0A8h
0x18000af50  pop     r15
0x18000af52  pop     r14
0x18000af54  pop     r13
0x18000af56  pop     r12
0x18000af58  pop     rdi
0x18000af59  pop     rsi
0x18000af5a  pop     rbx
0x18000af5b  pop     rbp
0x18000af5c  retn
```
