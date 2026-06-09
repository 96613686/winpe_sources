# DrvFillPath

- ea: `0x18000a660`
- end: `0x18000a895`
- name: `DrvFillPath`
- size: `565`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001ee0`
- `0x18000a488`
- `0x18000a660`
- `0x180011c50`
- `0x18001283c`
- `0x180015f84`
- `0x180019094`
- `0x1800195a4`
- `0x18005d010`

## import_xrefs

- `GDI32!PATHOBJ_vGetBounds` at `0x18000a7c8`
- `GDI32!PATHOBJ_vGetBounds` at `0x18000a7c8`

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
        PATHOBJ_vGetBounds(ppo, &prectfx);
        v14[0] = prectfx.xLeft >> 4;
        v14[1] = prectfx.yTop >> 4;
        v14[2] = (prectfx.xRight + 16) >> 4;
        v14[3] = (prectfx.yBottom + 16) >> 4;
        GSSendAttributes((_DWORD)dhpdev, -1, 0, 0, (__int64)pco, (__int64)v14);
        GBSendPath((__int64)dhpdev, ppo);
        GBPatternFill(
          dhpdev,
          pbo,
          pptlBrushOrg,
          *((unsigned __int8 *)qword_180062928 + (mix & 0xF))
        | (*((unsigned __int8 *)qword_180062928 + ((mix >> 8) & 0xF)) << 8),
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
0x18000a660  push    rbp
0x18000a662  push    rbx
0x18000a663  push    rsi
0x18000a664  push    rdi
0x18000a665  push    r12
0x18000a667  push    r14
0x18000a669  push    r15
0x18000a66b  mov     rbp, rsp
0x18000a66e  sub     rsp, 70h
0x18000a672  mov     rax, cs:__security_cookie
0x18000a679  xor     rax, rsp
0x18000a67c  mov     [rbp+var_10], rax
0x18000a680  mov     rbx, [rcx+10h]
0x18000a684  xorps   xmm0, xmm0
0x18000a687  mov     r12, [rbp+pptlBrushOrg]
0x18000a68b  mov     r14, rcx
0x18000a68e  movups  xmmword ptr [rbp+prectfx.xLeft], xmm0
0x18000a692  mov     r15, r9
0x18000a695  mov     rsi, r8
0x18000a698  mov     rax, [rbx+60h]
0x18000a69c  mov     rdi, rdx
0x18000a69f  mov     ecx, 1
0x18000a6a4  cmp     dword ptr [rax+7Ch], 2
0x18000a6a8  jnz     short loc_18000A6B6
0x18000a6aa  cmp     [rbx+87Ch], ecx
0x18000a6b0  ja      loc_18000A878
0x18000a6b6  test    dword ptr [rbx+868h], 0C0000000h
0x18000a6c0  jnz     loc_18000A878
0x18000a6c6  cmp     dword ptr [rbx+2C0h], 3
0x18000a6cd  jz      loc_18000A878
0x18000a6d3  mov     r11, [rbx+0D90h]
0x18000a6da  test    r11, r11
0x18000a6dd  jz      short loc_18000A756
0x18000a6df  cmp     qword ptr [r11+0C0h], 0
0x18000a6e7  jz      short loc_18000A756
0x18000a6e9  mov     eax, [rbx+0D98h]
0x18000a6ef  test    cl, al
0x18000a6f1  jnz     short loc_18000A756
0x18000a6f3  or      eax, ecx
0x18000a6f5  mov     [rbx+0D98h], eax
0x18000a6fb  mov     rax, [r11+0C8h]
0x18000a702  mov     rcx, [rax+20h]
0x18000a706  mov     [rbx+20h], rcx
0x18000a70a  mov     rcx, r14
0x18000a70d  mov     rax, [r11+0C8h]
0x18000a714  mov     r10, [rax+28h]
0x18000a718  mov     [rbx+8], r10
0x18000a71c  mov     rax, [r11+0C8h]
0x18000a723  mov     r10, [rax+38h]
0x18000a727  mov     eax, [rbp+flOptions]
0x18000a72a  mov     [rsp+70h+var_40], eax
0x18000a72e  mov     eax, [rbp+mix]
0x18000a731  mov     dword ptr [rsp+70h+var_48], eax
0x18000a735  mov     [rbx+30h], r10
0x18000a739  mov     rax, [r11+0C0h]
0x18000a740  mov     [rsp+70h+var_50], r12
0x18000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74a  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x18000a751  jmp     loc_18000A87A
0x18000a756  cmp     dword ptr [rbx+878h], 3
0x18000a75d  jnz     short loc_18000A785
0x18000a75f  mov     r8, rdi
0x18000a762  mov     rdx, rsi
0x18000a765  mov     rcx, rbx
0x18000a768  call    BDoMSEpsHackRect
0x18000a76d  test    eax, eax
0x18000a76f  jz      short loc_18000A785
0x18000a771  mov     dword ptr [rbx+878h], 2
0x18000a77b  mov     eax, 1
0x18000a780  jmp     loc_18000A87A
0x18000a785  mov     edx, 5
0x18000a78a  mov     rcx, rbx
0x18000a78d  call    SMChangeState
0x18000a792  test    eax, eax
0x18000a794  jz      loc_18000A87A
0x18000a79a  mov     edx, 10h
0x18000a79f  mov     rcx, rbx
0x18000a7a2  call    PSProcsetSend
0x18000a7a7  cmp     dword ptr [rbx+86Ch], 0
0x18000a7ae  jg      loc_18000A86B
0x18000a7b4  cmp     [rbp+mix], 0B0Bh
0x18000a7bb  jz      loc_18000A86B
0x18000a7c1  lea     rdx, [rbp+prectfx]; prectfx
0x18000a7c5  mov     rcx, rdi; ppo
0x18000a7c8  call    cs:__imp_PATHOBJ_vGetBounds
0x18000a7ce  mov     eax, [rbp+prectfx.xLeft]
0x18000a7d1  xor     r9d, r9d
0x18000a7d4  sar     eax, 4
0x18000a7d7  xor     r8d, r8d
0x18000a7da  mov     [rbp+var_30], eax
0x18000a7dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a7e1  mov     eax, [rbp+prectfx.yTop]
0x18000a7e4  mov     rcx, rbx
0x18000a7e7  sar     eax, 4
0x18000a7ea  mov     [rbp+var_2C], eax
0x18000a7ed  mov     eax, [rbp+prectfx.xRight]
0x18000a7f0  add     eax, 10h
0x18000a7f3  sar     eax, 4
0x18000a7f6  mov     [rbp+var_28], eax
0x18000a7f9  mov     eax, [rbp+prectfx.yBottom]
0x18000a7fc  add     eax, 10h
0x18000a7ff  sar     eax, 4
0x18000a802  mov     [rbp+var_24], eax
0x18000a805  lea     rax, [rbp+var_30]
0x18000a809  mov     [rsp+70h+var_48], rax
0x18000a80e  mov     [rsp+70h+var_50], rsi
0x18000a813  call    GSSendAttributes
0x18000a818  mov     rdx, rdi
0x18000a81b  mov     rcx, rbx
0x18000a81e  call    GBSendPath
0x18000a823  mov     ecx, [rbp+mix]
0x18000a826  lea     rdx, qword_180062928
0x18000a82d  mov     eax, ecx
0x18000a82f  mov     r8, r12
0x18000a832  shr     rax, 8
0x18000a836  and     ecx, 0Fh
0x18000a839  and     eax, 0Fh
0x18000a83c  movzx   r9d, byte ptr [rax+rdx]
0x18000a841  movzx   eax, byte ptr [rcx+rdx]
0x18000a845  mov     rdx, r15
0x18000a848  shl     r9d, 8
0x18000a84c  mov     rcx, rbx
0x18000a84f  or      r9d, eax
0x18000a852  mov     eax, [rbp+flOptions]
0x18000a855  mov     dword ptr [rsp+70h+var_50], eax
0x18000a859  call    GBPatternFill
0x18000a85e  xor     eax, eax
0x18000a860  cmp     [rbx+0D70h], eax
0x18000a866  setz    al
0x18000a869  jmp     short loc_18000A87A
0x18000a86b  mov     rdx, rdi
0x18000a86e  mov     rcx, rbx
0x18000a871  call    GBSendPath
0x18000a876  jmp     short loc_18000A87A
0x18000a878  mov     eax, ecx
0x18000a87a  mov     rcx, [rbp+var_10]
0x18000a87e  xor     rcx, rsp; StackCookie
0x18000a881  call    __security_check_cookie
0x18000a886  add     rsp, 70h
0x18000a88a  pop     r15
0x18000a88c  pop     r14
0x18000a88e  pop     r12
0x18000a890  pop     rdi
0x18000a891  pop     rsi
0x18000a892  pop     rbx
0x18000a893  pop     rbp
0x18000a894  retn
```
