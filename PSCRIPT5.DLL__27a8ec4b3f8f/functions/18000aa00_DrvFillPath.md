# DrvFillPath

- ea: `0x18000aa00`
- end: `0x18000ac3c`
- name: `DrvFillPath`
- size: `572`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001f20`
- `0x18000a81c`
- `0x18000aa00`
- `0x180012200`
- `0x180012e18`
- `0x1800166c0`
- `0x1800198f8`
- `0x180019e10`
- `0x18005f010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000ab68`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000ab68`

## pseudocode

```c
BOOL __stdcall DrvFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        MIX mix,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rbx
  __int64 v11; // r11
  int v12; // eax
  BOOL result; // eax
  _DWORD v14[4]; // [rsp+40h] [rbp-30h] BYREF
  _RECTFX prectfx; // [rsp+50h] [rbp-20h] BYREF

  dhpdev = pso->dhpdev;
  prectfx = 0;
  if ( *(_DWORD *)(*((_QWORD *)dhpdev + 12) + 124LL) == 2 && *((_DWORD *)dhpdev + 543) > 1u
    || ((_DWORD)dhpdev[538] & 0xC0000000) != 0
    || *((_DWORD *)dhpdev + 176) == 3 )
  {
    return 1;
  }
  v11 = *((_QWORD *)dhpdev + 434);
  if ( v11 && *(_QWORD *)(v11 + 192) && (v12 = *((_DWORD *)dhpdev + 870), (v12 & 1) == 0) )
  {
    *((_DWORD *)dhpdev + 870) = v12 | 1;
    *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v11 + 200) + 32LL);
    *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v11 + 200) + 40LL);
    *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v11 + 200) + 56LL);
    result = (*(__int64 (__fastcall **)(SURFOBJ *))(v11 + 192))(pso);
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
        PATHOBJ_vGetBounds(ppo, &prectfx);
        v14[0] = prectfx.xLeft >> 4;
        v14[1] = prectfx.yTop >> 4;
        v14[2] = (prectfx.xRight + 16) >> 4;
        v14[3] = (prectfx.yBottom + 16) >> 4;
        GSSendAttributes((__int64)dhpdev, -1, 0, 0, (__int64)pco, v14);
        GBSendPath((__int64)dhpdev, ppo);
        GBPatternFill(
          (__int64)dhpdev,
          (__int64)pbo,
          (int *)pptlBrushOrg,
          *((unsigned __int8 *)qword_180064918 + (mix & 0xF))
        | (*((unsigned __int8 *)qword_180064918 + ((mix >> 8) & 0xF)) << 8),
          flOptions);
        return *((_DWORD *)dhpdev + 860) == 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000aa00  push    rbp
0x18000aa02  push    rbx
0x18000aa03  push    rsi
0x18000aa04  push    rdi
0x18000aa05  push    r12
0x18000aa07  push    r14
0x18000aa09  push    r15
0x18000aa0b  mov     rbp, rsp
0x18000aa0e  sub     rsp, 70h
0x18000aa12  mov     rax, cs:__security_cookie
0x18000aa19  xor     rax, rsp
0x18000aa1c  mov     [rbp+var_10], rax
0x18000aa20  mov     rbx, [rcx+10h]
0x18000aa24  xorps   xmm0, xmm0
0x18000aa27  mov     r12, [rbp+pptlBrushOrg]
0x18000aa2b  mov     r14, rcx
0x18000aa2e  movups  xmmword ptr [rbp+prectfx.xLeft], xmm0
0x18000aa32  mov     r15, r9
0x18000aa35  mov     rsi, r8
0x18000aa38  mov     rax, [rbx+60h]
0x18000aa3c  mov     rdi, rdx
0x18000aa3f  mov     ecx, 1
0x18000aa44  cmp     dword ptr [rax+7Ch], 2
0x18000aa48  jnz     short loc_18000AA56
0x18000aa4a  cmp     [rbx+87Ch], ecx
0x18000aa50  ja      loc_18000AC1E
0x18000aa56  test    dword ptr [rbx+868h], 0C0000000h
0x18000aa60  jnz     loc_18000AC1E
0x18000aa66  cmp     dword ptr [rbx+2C0h], 3
0x18000aa6d  jz      loc_18000AC1E
0x18000aa73  mov     r11, [rbx+0D90h]
0x18000aa7a  test    r11, r11
0x18000aa7d  jz      short loc_18000AAF6
0x18000aa7f  cmp     qword ptr [r11+0C0h], 0
0x18000aa87  jz      short loc_18000AAF6
0x18000aa89  mov     eax, [rbx+0D98h]
0x18000aa8f  test    cl, al
0x18000aa91  jnz     short loc_18000AAF6
0x18000aa93  or      eax, ecx
0x18000aa95  mov     [rbx+0D98h], eax
0x18000aa9b  mov     rax, [r11+0C8h]
0x18000aaa2  mov     rcx, [rax+20h]
0x18000aaa6  mov     [rbx+20h], rcx
0x18000aaaa  mov     rcx, r14
0x18000aaad  mov     rax, [r11+0C8h]
0x18000aab4  mov     r10, [rax+28h]
0x18000aab8  mov     [rbx+8], r10
0x18000aabc  mov     rax, [r11+0C8h]
0x18000aac3  mov     r10, [rax+38h]
0x18000aac7  mov     eax, [rbp+flOptions]
0x18000aaca  mov     [rsp+70h+var_40], eax
0x18000aace  mov     eax, [rbp+mix]
0x18000aad1  mov     dword ptr [rsp+70h+var_48], eax
0x18000aad5  mov     [rbx+30h], r10
0x18000aad9  mov     rax, [r11+0C0h]
0x18000aae0  mov     [rsp+70h+var_50], r12
0x18000aae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaea  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000aaf1  jmp     loc_18000AC20
0x18000aaf6  cmp     dword ptr [rbx+878h], 3
0x18000aafd  jnz     short loc_18000AB25
0x18000aaff  mov     r8, rdi
0x18000ab02  mov     rdx, rsi
0x18000ab05  mov     rcx, rbx
0x18000ab08  call    BDoMSEpsHackRect
0x18000ab0d  test    eax, eax
0x18000ab0f  jz      short loc_18000AB25
0x18000ab11  mov     dword ptr [rbx+878h], 2
0x18000ab1b  mov     eax, 1
0x18000ab20  jmp     loc_18000AC20
0x18000ab25  mov     edx, 5
0x18000ab2a  mov     rcx, rbx
0x18000ab2d  call    SMChangeState
0x18000ab32  test    eax, eax
0x18000ab34  jz      loc_18000AC20
0x18000ab3a  mov     edx, 10h
0x18000ab3f  mov     rcx, rbx
0x18000ab42  call    PSProcsetSend
0x18000ab47  cmp     dword ptr [rbx+86Ch], 0
0x18000ab4e  jg      loc_18000AC11
0x18000ab54  cmp     [rbp+mix], 0B0Bh
0x18000ab5b  jz      loc_18000AC11
0x18000ab61  lea     rdx, [rbp+prectfx]; prectfx
0x18000ab65  mov     rcx, rdi; ppo
0x18000ab68  call    cs:__imp_PATHOBJ_vGetBounds
0x18000ab6f  nop     dword ptr [rax+rax+00h]
0x18000ab74  mov     eax, [rbp+prectfx.xLeft]
0x18000ab77  xor     r9d, r9d
0x18000ab7a  sar     eax, 4
0x18000ab7d  xor     r8d, r8d
0x18000ab80  mov     [rbp+var_30], eax
0x18000ab83  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ab87  mov     eax, [rbp+prectfx.yTop]
0x18000ab8a  mov     rcx, rbx
0x18000ab8d  sar     eax, 4
0x18000ab90  mov     [rbp+var_2C], eax
0x18000ab93  mov     eax, [rbp+prectfx.xRight]
0x18000ab96  add     eax, 10h
0x18000ab99  sar     eax, 4
0x18000ab9c  mov     [rbp+var_28], eax
0x18000ab9f  mov     eax, [rbp+prectfx.yBottom]
0x18000aba2  add     eax, 10h
0x18000aba5  sar     eax, 4
0x18000aba8  mov     [rbp+var_24], eax
0x18000abab  lea     rax, [rbp+var_30]
0x18000abaf  mov     [rsp+70h+var_48], rax
0x18000abb4  mov     [rsp+70h+var_50], rsi
0x18000abb9  call    GSSendAttributes
0x18000abbe  mov     rdx, rdi
0x18000abc1  mov     rcx, rbx
0x18000abc4  call    GBSendPath
0x18000abc9  mov     ecx, [rbp+mix]
0x18000abcc  lea     rdx, qword_180064918
0x18000abd3  mov     eax, ecx
0x18000abd5  mov     r8, r12
0x18000abd8  shr     rax, 8
0x18000abdc  and     ecx, 0Fh
0x18000abdf  and     eax, 0Fh
0x18000abe2  movzx   r9d, byte ptr [rax+rdx]
0x18000abe7  movzx   eax, byte ptr [rcx+rdx]
0x18000abeb  mov     rdx, r15
0x18000abee  shl     r9d, 8
0x18000abf2  mov     rcx, rbx
0x18000abf5  or      r9d, eax
0x18000abf8  mov     eax, [rbp+flOptions]
0x18000abfb  mov     dword ptr [rsp+70h+var_50], eax
0x18000abff  call    GBPatternFill
0x18000ac04  xor     eax, eax
0x18000ac06  cmp     [rbx+0D70h], eax
0x18000ac0c  setz    al
0x18000ac0f  jmp     short loc_18000AC20
0x18000ac11  mov     rdx, rdi
0x18000ac14  mov     rcx, rbx
0x18000ac17  call    GBSendPath
0x18000ac1c  jmp     short loc_18000AC20
0x18000ac1e  mov     eax, ecx
0x18000ac20  mov     rcx, [rbp+var_10]
0x18000ac24  xor     rcx, rsp; StackCookie
0x18000ac27  call    __security_check_cookie
0x18000ac2c  add     rsp, 70h
0x18000ac30  pop     r15
0x18000ac32  pop     r14
0x18000ac34  pop     r12
0x18000ac36  pop     rdi
0x18000ac37  pop     rsi
0x18000ac38  pop     rbx
0x18000ac39  pop     rbp
0x18000ac3a  retn
```
