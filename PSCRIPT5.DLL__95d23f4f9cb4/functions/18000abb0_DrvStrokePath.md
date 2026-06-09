# DrvStrokePath

- ea: `0x18000abb0`
- end: `0x18000ae39`
- name: `DrvStrokePath`
- size: `649`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, LINEATTRS *plineattrs, MIX mix)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001ee0`
- `0x18000a488`
- `0x18000abb0`
- `0x180011c50`
- `0x18001241c`
- `0x18001247c`
- `0x18001265c`
- `0x18001283c`
- `0x180015f84`
- `0x180016940`
- `0x180016e24`
- `0x1800195a4`
- `0x18005d010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000ad5d`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000ad5d`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000ad4a`
- `GDI32!XFORMOBJ_iGetXform` at `0x18000ad4a`

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
    result = SMChangeState(dhpdev, 5);
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
        GSSendAttributes((_DWORD)dhpdev, -1, (_DWORD)pbo, (_DWORD)plineattrs, (__int64)pco, (__int64)&pxform);
        GBSendPath((__int64)dhpdev, ppo);
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
0x18000abb0  push    rbp
0x18000abb2  push    rbx
0x18000abb3  push    rsi
0x18000abb4  push    rdi
0x18000abb5  push    r12
0x18000abb7  push    r13
0x18000abb9  push    r14
0x18000abbb  push    r15
0x18000abbd  lea     rbp, [rsp-7]
0x18000abc2  sub     rsp, 88h
0x18000abc9  mov     rax, cs:__security_cookie
0x18000abd0  xor     rax, rsp
0x18000abd3  mov     [rbp+3Fh+var_48], rax
0x18000abd7  mov     rbx, [rcx+10h]
0x18000abdb  xorps   xmm0, xmm0
0x18000abde  mov     r15, [rbp+3Fh+plineattrs]
0x18000abe2  mov     rsi, rdx
0x18000abe5  mov     r13, [rbp+3Fh+pbo]
0x18000abe9  mov     rdi, rcx
0x18000abec  mov     rdx, [rbp+3Fh+pptlBrushOrg]
0x18000abf0  mov     r14, r9
0x18000abf3  movups  xmmword ptr [rbp+3Fh+prectfx.xLeft], xmm0
0x18000abf7  mov     rax, [rbx+60h]
0x18000abfb  mov     r12, r8
0x18000abfe  mov     ecx, 1
0x18000ac03  cmp     dword ptr [rax+7Ch], 2
0x18000ac07  jnz     short loc_18000AC15
0x18000ac09  cmp     [rbx+87Ch], ecx
0x18000ac0f  ja      loc_18000AE17
0x18000ac15  test    dword ptr [rbx+868h], 0C0000000h
0x18000ac1f  jnz     loc_18000AE17
0x18000ac25  cmp     dword ptr [rbx+2C0h], 3
0x18000ac2c  jz      loc_18000AE17
0x18000ac32  mov     r11, [rbx+0D90h]
0x18000ac39  test    r11, r11
0x18000ac3c  jz      loc_18000ACC2
0x18000ac42  cmp     qword ptr [r11+0B0h], 0
0x18000ac4a  jz      short loc_18000ACC2
0x18000ac4c  mov     eax, [rbx+0D98h]
0x18000ac52  test    cl, al
0x18000ac54  jnz     short loc_18000ACC2
0x18000ac56  or      eax, ecx
0x18000ac58  mov     [rbx+0D98h], eax
0x18000ac5e  mov     rax, [r11+0B8h]
0x18000ac65  mov     rcx, [rax+20h]
0x18000ac69  mov     [rbx+20h], rcx
0x18000ac6d  mov     rcx, rdi
0x18000ac70  mov     rax, [r11+0B8h]
0x18000ac77  mov     r10, [rax+28h]
0x18000ac7b  mov     [rbx+8], r10
0x18000ac7f  mov     rax, [r11+0B8h]
0x18000ac86  mov     r10, [rax+38h]
0x18000ac8a  mov     eax, [rbp+3Fh+mix]
0x18000ac90  mov     [rsp+0C0h+var_88], eax
0x18000ac94  mov     [rsp+0C0h+var_90], r15
0x18000ac99  mov     [rsp+0C0h+var_98], rdx
0x18000ac9e  mov     rdx, rsi
0x18000aca1  mov     [rbx+30h], r10
0x18000aca5  mov     rax, [r11+0B0h]
0x18000acac  mov     [rsp+0C0h+var_A0], r13
0x18000acb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acb6  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000acbd  jmp     loc_18000AE19
0x18000acc2  cmp     dword ptr [rbx+878h], 3
0x18000acc9  jnz     short loc_18000ACF1
0x18000accb  mov     r8, rsi
0x18000acce  mov     rdx, r12
0x18000acd1  mov     rcx, rbx
0x18000acd4  call    BDoMSEpsHackRect
0x18000acd9  test    eax, eax
0x18000acdb  jz      short loc_18000ACF1
0x18000acdd  mov     dword ptr [rbx+878h], 2
0x18000ace7  mov     eax, 1
0x18000acec  jmp     loc_18000AE19
0x18000acf1  mov     edx, 5
0x18000acf6  mov     rcx, rbx
0x18000acf9  call    SMChangeState
0x18000acfe  test    eax, eax
0x18000ad00  jz      loc_18000AE19
0x18000ad06  mov     edx, 10h
0x18000ad0b  mov     rcx, rbx
0x18000ad0e  call    PSProcsetSend
0x18000ad13  cmp     dword ptr [rbx+86Ch], 0
0x18000ad1a  jg      loc_18000AE0A
0x18000ad20  cmp     [rbp+3Fh+mix], 0B0Bh
0x18000ad2a  jz      loc_18000AE0A
0x18000ad30  test    byte ptr [r15], 1
0x18000ad34  jz      short loc_18000AD54
0x18000ad36  xorps   xmm0, xmm0
0x18000ad39  lea     rdx, [rbp+3Fh+pxform]; pxform
0x18000ad3d  xor     eax, eax
0x18000ad3f  mov     rcx, r14; pxo
0x18000ad42  movups  xmmword ptr [rbp+3Fh+pxform.eM11], xmm0
0x18000ad46  mov     qword ptr [rbp+3Fh+pxform.eDx], rax
0x18000ad4a  call    cs:__imp_XFORMOBJ_iGetXform
0x18000ad50  mov     edi, eax
0x18000ad52  jmp     short loc_18000AD56
0x18000ad54  xor     edi, edi
0x18000ad56  lea     rdx, [rbp+3Fh+prectfx]; prectfx
0x18000ad5a  mov     rcx, rsi; ppo
0x18000ad5d  call    cs:__imp_PATHOBJ_vGetBounds
0x18000ad63  mov     eax, [rbp+3Fh+prectfx.xLeft]
0x18000ad66  mov     r9, r15
0x18000ad69  sar     eax, 4
0x18000ad6c  mov     r8, r13
0x18000ad6f  mov     [rbp+3Fh+pxform.eM11], eax
0x18000ad72  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ad76  mov     eax, [rbp+3Fh+prectfx.yTop]
0x18000ad79  mov     rcx, rbx
0x18000ad7c  sar     eax, 4
0x18000ad7f  mov     [rbp+3Fh+pxform.eM12], eax
0x18000ad82  mov     eax, [rbp+3Fh+prectfx.xRight]
0x18000ad85  add     eax, 10h
0x18000ad88  sar     eax, 4
0x18000ad8b  mov     [rbp+3Fh+pxform.eM21], eax
0x18000ad8e  mov     eax, [rbp+3Fh+prectfx.yBottom]
0x18000ad91  add     eax, 10h
0x18000ad94  sar     eax, 4
0x18000ad97  mov     [rbp+3Fh+pxform.eM22], eax
0x18000ad9a  lea     rax, [rbp+3Fh+pxform]
0x18000ad9e  mov     [rsp+0C0h+var_98], rax
0x18000ada3  mov     [rsp+0C0h+var_A0], r12
0x18000ada8  call    GSSendAttributes
0x18000adad  mov     rdx, rsi
0x18000adb0  mov     rcx, rbx
0x18000adb3  call    GBSendPath
0x18000adb8  test    edi, edi
0x18000adba  jz      short loc_18000ADCF
0x18000adbc  mov     rcx, rbx
0x18000adbf  call    GSSendGsave
0x18000adc4  mov     rdx, r14
0x18000adc7  mov     rcx, rbx
0x18000adca  call    GSSendXForm
0x18000adcf  mov     edx, 1Bh
0x18000add4  mov     rcx, rbx
0x18000add7  call    OPSendOperator
0x18000addc  mov     r8d, 2
0x18000ade2  lea     rdx, gstrCRLF; "\r\n"
0x18000ade9  mov     rcx, rbx
0x18000adec  call    OPRawPortWrite
0x18000adf1  test    edi, edi
0x18000adf3  jz      short loc_18000ADFD
0x18000adf5  mov     rcx, rbx
0x18000adf8  call    GSSendGrestore
0x18000adfd  xor     eax, eax
0x18000adff  cmp     [rbx+0D70h], eax
0x18000ae05  setz    al
0x18000ae08  jmp     short loc_18000AE19
0x18000ae0a  mov     rdx, rsi
0x18000ae0d  mov     rcx, rbx
0x18000ae10  call    GBSendPath
0x18000ae15  jmp     short loc_18000AE19
0x18000ae17  mov     eax, ecx
0x18000ae19  mov     rcx, [rbp+3Fh+var_48]
0x18000ae1d  xor     rcx, rsp; StackCookie
0x18000ae20  call    __security_check_cookie
0x18000ae25  add     rsp, 88h
0x18000ae2c  pop     r15
0x18000ae2e  pop     r14
0x18000ae30  pop     r13
0x18000ae32  pop     r12
0x18000ae34  pop     rdi
0x18000ae35  pop     rsi
0x18000ae36  pop     rbx
0x18000ae37  pop     rbp
0x18000ae38  retn
```
