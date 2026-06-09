# FwReduceObjectsToVersion

- ea: `0x180023210`
- end: `0x1800237ed`
- name: `FwReduceObjectsToVersion`
- size: `1501`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800042c4`
- `0x1800090b0`
- `0x180022f60`
- `0x180023210`

## import_xrefs

- `fwbase!FwFree` at `0x18002325b`
- `fwbase!FwFree` at `0x180023279`
- `fwbase!FwFree` at `0x1800232a9`
- `fwbase!FwFree` at `0x180023415`
- `fwbase!FwFree` at `0x180023476`
- `fwbase!FwFree` at `0x1800234b4`
- `fwbase!FwFree` at `0x1800234df`
- `fwbase!FwFree` at `0x18002350a`
- `fwbase!FwFree` at `0x1800235fc`
- `fwbase!FwFree` at `0x18002325b`
- `fwbase!FwFree` at `0x180023279`
- `fwbase!FwFree` at `0x1800232a9`
- `fwbase!FwFree` at `0x180023415`
- `fwbase!FwFree` at `0x180023476`
- `fwbase!FwFree` at `0x1800234b4`
- `fwbase!FwFree` at `0x1800234df`
- `fwbase!FwFree` at `0x18002350a`
- `fwbase!FwFree` at `0x1800235fc`
- `fwbase!FwMetaDataFree` at `0x180023553`
- `fwbase!FwMetaDataFree` at `0x180023610`
- `fwbase!FwMetaDataFree` at `0x180023553`
- `fwbase!FwMetaDataFree` at `0x180023610`
- `fwbase!Int_FwValidateComplianceAndReduceFirewallRuleToVersion` at `0x180023525`
- `fwbase!Int_FwValidateComplianceAndReduceFirewallRuleToVersion` at `0x180023525`
- `fwbase!Int_FwValidateComplianceAndReduceConnSecRuleToVersion` at `0x180023582`
- `fwbase!Int_FwValidateComplianceAndReduceConnSecRuleToVersion` at `0x180023582`
- `fwbase!Int_FwValidateComplianceAndReduceMainModeRuleToVersion` at `0x18002363b`
- `fwbase!Int_FwValidateComplianceAndReduceMainModeRuleToVersion` at `0x18002363b`
- `fwbase!Int_FwValidateComplianceAndReduceAuthSetToVersion` at `0x1800236a4`
- `fwbase!Int_FwValidateComplianceAndReduceAuthSetToVersion` at `0x1800236a4`
- `fwbase!Int_FwValidateComplianceAndReduceCryptoSetToVersion` at `0x1800236de`
- `fwbase!Int_FwValidateComplianceAndReduceCryptoSetToVersion` at `0x1800236de`

## pseudocode

```c
__int64 __fastcall FwReduceObjectsToVersion(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned __int16 a5,
        unsigned __int16 a6)
{
  __int64 v6; // rbx
  signed int v7; // edi
  __int64 *i; // r15
  __int16 v11; // ax
  __int64 v12; // rcx
  __int16 v13; // ax
  __int16 v14; // ax
  __int16 v15; // ax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int16 v25; // ax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int16 v29; // ax
  int v30; // eax
  int v31; // eax
  LPCOLESTR v32; // rcx
  __int64 v33; // rdx

  v6 = *a1;
  v7 = 0;
  for ( i = a1; ; v6 = *i )
  {
    if ( !v6 )
      return (unsigned int)v7;
    if ( !a3 )
    {
      if ( a6 < 0x221u )
      {
        FwFree(*(_QWORD *)(v6 + 496));
        *(_QWORD *)(v6 + 496) = 0;
      }
      if ( a6 < 0x21Fu )
      {
        FwFree(*(_QWORD *)(v6 + 488));
        *(_QWORD *)(v6 + 488) = 0;
        *(_OWORD *)(v6 + 460) = 0;
        *(_DWORD *)(v6 + 480) = 0;
      }
      if ( a6 < 0x21Bu )
      {
        FwFree(*(_QWORD *)(v6 + 448));
        v11 = *(_WORD *)(v6 + 424);
        *(_QWORD *)(v6 + 448) = 0;
        *(_DWORD *)(v6 + 456) = 0;
        if ( (v11 & 0x80u) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          v11 &= ~0x80u;
          *(_WORD *)(v6 + 424) = v11;
        }
        if ( (v11 & 0x100) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          *(_WORD *)(v6 + 424) = v11 & 0xFEFF;
        }
      }
      if ( a6 < 0x21Au )
      {
        v12 = *(unsigned int *)(v6 + 432);
        if ( (_DWORD)v12 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwBinariesFree(v12, *(_QWORD *)(v6 + 440));
        v13 = *(_WORD *)(v6 + 424);
        *(_DWORD *)(v6 + 432) = 0;
        *(_QWORD *)(v6 + 440) = 0;
        if ( (v13 & 0x10) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          v13 &= ~0x10u;
          *(_WORD *)(v6 + 424) = v13;
        }
        if ( (v13 & 0x20) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          *(_WORD *)(v6 + 424) = v13 & 0xFFDF;
        }
      }
      if ( a6 < 0x218u )
      {
        v14 = *(_WORD *)(v6 + 424);
        if ( (v14 & 1) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          v14 &= ~1u;
          *(_WORD *)(v6 + 424) = v14;
        }
        if ( (v14 & 2) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          v14 &= ~2u;
          *(_WORD *)(v6 + 424) = v14;
        }
        if ( (v14 & 4) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          *(_WORD *)(v6 + 424) = v14 & 0xFFFB;
        }
        v15 = *(_WORD *)(v6 + 292);
        if ( (v15 & 0x1000) != 0 )
        {
          *(_DWORD *)(v6 + 336) = 0x20000;
          v16 = *(_QWORD *)(v6 + 368);
          *(_WORD *)(v6 + 292) = v15 & 0xEFFF;
          FwFree(v16);
          *(_QWORD *)(v6 + 368) = 0;
        }
        v17 = *(unsigned int *)(v6 + 400);
        if ( (_DWORD)v17 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwBinariesFree(v17, *(_QWORD *)(v6 + 408));
        v18 = *(_QWORD *)(v6 + 416);
        *(_DWORD *)(v6 + 400) = 0;
        *(_QWORD *)(v6 + 408) = 0;
        if ( v18 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwFree(v18);
        *(_QWORD *)(v6 + 416) = 0;
      }
      if ( a6 < 0x214u )
      {
        v19 = *(_QWORD *)(v6 + 368);
        if ( v19 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwFree(v19);
        v20 = *(_QWORD *)(v6 + 384);
        *(_QWORD *)(v6 + 368) = 0;
        if ( v20 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwFree(v20);
        v21 = *(_QWORD *)(v6 + 376);
        *(_QWORD *)(v6 + 384) = 0;
        if ( v21 && *(_DWORD *)(v6 + 336) == 0x10000 )
          *(_DWORD *)(v6 + 336) = 0x20000;
        FwFree(v21);
        *(_QWORD *)(v6 + 376) = 0;
      }
      v22 = Int_FwValidateComplianceAndReduceFirewallRuleToVersion(v6, 0, a5);
      v7 = v22;
      if ( v22 > 0 )
        v7 = (unsigned __int16)v22 | 0x80070000;
      if ( v7 < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return (unsigned int)v7;
        v33 = 31;
        goto LABEL_104;
      }
      if ( a6 < 0x20Au )
      {
        FwMetaDataFree(*(_QWORD *)(v6 + 360));
        *(_QWORD *)(v6 + 360) = 0;
      }
      v23 = *(_DWORD *)(v6 + 336);
      goto LABEL_85;
    }
    if ( a3 == 1 )
    {
      v24 = Int_FwValidateComplianceAndReduceConnSecRuleToVersion(v6, 0, a5);
      v7 = v24;
      if ( v24 > 0 )
        v7 = (unsigned __int16)v24 | 0x80070000;
      if ( v7 < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return (unsigned int)v7;
        v33 = 32;
        goto LABEL_104;
      }
      if ( a6 < 0x218u )
      {
        v25 = *(_WORD *)(v6 + 340);
        if ( (v25 & 0x100) != 0 )
        {
          *(_DWORD *)(v6 + 384) = 0x20000;
          *(_WORD *)(v6 + 340) = v25 & 0xFEFF;
        }
      }
      if ( a6 < 0x20Au )
      {
        v26 = *(_QWORD *)(v6 + 392);
        if ( v26 && *(_DWORD *)(v6 + 384) == 0x10000 )
          *(_DWORD *)(v6 + 384) = 0x20000;
        FwFree(v26);
        v27 = *(_QWORD *)(v6 + 408);
        *(_QWORD *)(v6 + 392) = 0;
        FwMetaDataFree(v27);
        *(_QWORD *)(v6 + 408) = 0;
      }
      v23 = *(_DWORD *)(v6 + 384);
      goto LABEL_85;
    }
    if ( a3 != 2 )
      break;
    v28 = Int_FwValidateComplianceAndReduceMainModeRuleToVersion(v6, 0, a5);
    v7 = v28;
    if ( v28 > 0 )
      v7 = (unsigned __int16)v28 | 0x80070000;
    if ( v7 < 0 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v7;
      v33 = 33;
      goto LABEL_104;
    }
    if ( a6 < 0x218u )
    {
      v29 = *(_WORD *)(v6 + 208);
      if ( (v29 & 0x100) != 0 )
      {
        *(_DWORD *)(v6 + 256) = 0x20000;
        *(_WORD *)(v6 + 208) = v29 & 0xFEFF;
      }
    }
    v23 = *(_DWORD *)(v6 + 256);
LABEL_85:
    if ( (v23 & a4) != 0 )
    {
      i = (__int64 *)v6;
    }
    else
    {
      *i = *(_QWORD *)v6;
      *(_QWORD *)v6 = 0;
      FwFreeObjects(v6, a3);
    }
  }
  if ( a3 == 4 )
  {
    v30 = Int_FwValidateComplianceAndReduceAuthSetToVersion(v6, 0, a5);
    v7 = v30;
    if ( v30 > 0 )
      v7 = (unsigned __int16)v30 | 0x80070000;
    if ( v7 >= 0 )
    {
      v23 = *(_DWORD *)(v6 + 80);
      goto LABEL_85;
    }
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return (unsigned int)v7;
    v33 = 34;
LABEL_104:
    WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  v23 = 0x10000;
  if ( a3 != 5 )
    goto LABEL_85;
  v31 = Int_FwValidateComplianceAndReduceCryptoSetToVersion(v6, 0, a5);
  v7 = v31;
  if ( v31 > 0 )
    v7 = (unsigned __int16)v31 | 0x80070000;
  if ( v7 >= 0 )
  {
    v23 = *(_DWORD *)(v6 + 88);
    goto LABEL_85;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v33 = 35;
    goto LABEL_104;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023210  push    rbx
0x180023212  push    rbp
0x180023213  push    rsi
0x180023214  push    rdi
0x180023215  push    r12
0x180023217  push    r13
0x180023219  push    r15
0x18002321b  sub     rsp, 20h
0x18002321f  mov     rbx, [rcx]
0x180023222  xor     r13d, r13d
0x180023225  movzx   esi, [rsp+58h+arg_28]
0x18002322d  mov     edi, r13d
0x180023230  mov     r12d, r9d
0x180023233  mov     ebp, r8d
0x180023236  mov     r15, rcx
0x180023239  test    rbx, rbx
0x18002323c  jz      loc_1800237DC
0x180023242  test    ebp, ebp
0x180023244  jnz     loc_18002356B
0x18002324a  mov     eax, 221h
0x18002324f  cmp     si, ax
0x180023252  jnb     short loc_180023268
0x180023254  mov     rcx, [rbx+1F0h]
0x18002325b  call    cs:__imp_FwFree
0x180023261  mov     [rbx+1F0h], r13
0x180023268  mov     eax, 21Fh
0x18002326d  cmp     si, ax
0x180023270  jnb     short loc_180023298
0x180023272  mov     rcx, [rbx+1E8h]
0x180023279  call    cs:__imp_FwFree
0x18002327f  xorps   xmm0, xmm0
0x180023282  mov     [rbx+1E8h], r13
0x180023289  movdqu  xmmword ptr [rbx+1CCh], xmm0
0x180023291  mov     [rbx+1E0h], r13d
0x180023298  mov     eax, 21Bh
0x18002329d  cmp     si, ax
0x1800232a0  jnb     short loc_180023301
0x1800232a2  mov     rcx, [rbx+1C0h]
0x1800232a9  call    cs:__imp_FwFree
0x1800232af  movzx   eax, word ptr [rbx+1A8h]
0x1800232b6  mov     [rbx+1C0h], r13
0x1800232bd  mov     [rbx+1C8h], r13d
0x1800232c4  test    al, al
0x1800232c6  jns     short loc_1800232E1
0x1800232c8  mov     ecx, 0FF7Fh
0x1800232cd  mov     dword ptr [rbx+150h], 20000h
0x1800232d7  and     ax, cx
0x1800232da  mov     [rbx+1A8h], ax
0x1800232e1  bt      ax, 8
0x1800232e6  jnb     short loc_180023301
0x1800232e8  mov     ecx, 0FEFFh
0x1800232ed  mov     dword ptr [rbx+150h], 20000h
0x1800232f7  and     ax, cx
0x1800232fa  mov     [rbx+1A8h], ax
0x180023301  mov     eax, 21Ah
0x180023306  cmp     si, ax
0x180023309  jnb     short loc_180023386
0x18002330b  mov     ecx, [rbx+1B0h]
0x180023311  test    ecx, ecx
0x180023313  jz      short loc_18002332B
0x180023315  cmp     dword ptr [rbx+150h], 10000h
0x18002331f  jnz     short loc_18002332B
0x180023321  mov     dword ptr [rbx+150h], 20000h
0x18002332b  mov     rdx, [rbx+1B8h]
0x180023332  call    FwBinariesFree
0x180023337  movzx   eax, word ptr [rbx+1A8h]
0x18002333e  mov     [rbx+1B0h], r13d
0x180023345  mov     [rbx+1B8h], r13
0x18002334c  test    al, 10h
0x18002334e  jz      short loc_180023369
0x180023350  mov     ecx, 0FFEFh
0x180023355  mov     dword ptr [rbx+150h], 20000h
0x18002335f  and     ax, cx
0x180023362  mov     [rbx+1A8h], ax
0x180023369  test    al, 20h
0x18002336b  jz      short loc_180023386
0x18002336d  mov     ecx, 0FFDFh
0x180023372  mov     dword ptr [rbx+150h], 20000h
0x18002337c  and     ax, cx
0x18002337f  mov     [rbx+1A8h], ax
0x180023386  mov     eax, 218h
0x18002338b  cmp     si, ax
0x18002338e  jnb     loc_180023483
0x180023394  movzx   eax, word ptr [rbx+1A8h]
0x18002339b  mov     edi, 20000h
0x1800233a0  test    al, 1
0x1800233a2  jz      short loc_1800233B9
0x1800233a4  mov     ecx, 0FFFEh
0x1800233a9  mov     [rbx+150h], edi
0x1800233af  and     ax, cx
0x1800233b2  mov     [rbx+1A8h], ax
0x1800233b9  test    al, 2
0x1800233bb  jz      short loc_1800233D2
0x1800233bd  mov     ecx, 0FFFDh
0x1800233c2  mov     [rbx+150h], edi
0x1800233c8  and     ax, cx
0x1800233cb  mov     [rbx+1A8h], ax
0x1800233d2  test    al, 4
0x1800233d4  jz      short loc_1800233EB
0x1800233d6  mov     ecx, 0FFFBh
0x1800233db  mov     [rbx+150h], edi
0x1800233e1  and     ax, cx
0x1800233e4  mov     [rbx+1A8h], ax
0x1800233eb  movzx   eax, word ptr [rbx+124h]
0x1800233f2  bt      ax, 0Ch
0x1800233f7  jnb     short loc_180023422
0x1800233f9  mov     ecx, 0EFFFh
0x1800233fe  mov     [rbx+150h], edi
0x180023404  and     ax, cx
0x180023407  mov     rcx, [rbx+170h]
0x18002340e  mov     [rbx+124h], ax
0x180023415  call    cs:__imp_FwFree
0x18002341b  mov     [rbx+170h], r13
0x180023422  mov     ecx, [rbx+190h]
0x180023428  test    ecx, ecx
0x18002342a  jz      short loc_18002343E
0x18002342c  cmp     dword ptr [rbx+150h], 10000h
0x180023436  jnz     short loc_18002343E
0x180023438  mov     [rbx+150h], edi
0x18002343e  mov     rdx, [rbx+198h]
0x180023445  call    FwBinariesFree
0x18002344a  mov     rcx, [rbx+1A0h]
0x180023451  mov     [rbx+190h], r13d
0x180023458  mov     [rbx+198h], r13
0x18002345f  test    rcx, rcx
0x180023462  jz      short loc_180023476
0x180023464  cmp     dword ptr [rbx+150h], 10000h
0x18002346e  jnz     short loc_180023476
0x180023470  mov     [rbx+150h], edi
0x180023476  call    cs:__imp_FwFree
0x18002347c  mov     [rbx+1A0h], r13
0x180023483  mov     eax, 214h
0x180023488  cmp     si, ax
0x18002348b  jnb     loc_180023517
0x180023491  mov     rcx, [rbx+170h]
0x180023498  mov     edi, 10000h
0x18002349d  test    rcx, rcx
0x1800234a0  jz      short loc_1800234B4
0x1800234a2  cmp     [rbx+150h], edi
0x1800234a8  jnz     short loc_1800234B4
0x1800234aa  mov     dword ptr [rbx+150h], 20000h
0x1800234b4  call    cs:__imp_FwFree
0x1800234ba  mov     rcx, [rbx+180h]
0x1800234c1  mov     [rbx+170h], r13
0x1800234c8  test    rcx, rcx
0x1800234cb  jz      short loc_1800234DF
0x1800234cd  cmp     [rbx+150h], edi
0x1800234d3  jnz     short loc_1800234DF
0x1800234d5  mov     dword ptr [rbx+150h], 20000h
0x1800234df  call    cs:__imp_FwFree
0x1800234e5  mov     rcx, [rbx+178h]
0x1800234ec  mov     [rbx+180h], r13
0x1800234f3  test    rcx, rcx
0x1800234f6  jz      short loc_18002350A
0x1800234f8  cmp     [rbx+150h], edi
0x1800234fe  jnz     short loc_18002350A
0x180023500  mov     dword ptr [rbx+150h], 20000h
0x18002350a  call    cs:__imp_FwFree
0x180023510  mov     [rbx+178h], r13
0x180023517  movzx   r8d, [rsp+58h+arg_20]
0x180023520  xor     edx, edx
0x180023522  mov     rcx, rbx
0x180023525  call    cs:__imp_Int_FwValidateComplianceAndReduceFirewallRuleToVersion
0x18002352b  mov     edi, eax
0x18002352d  test    eax, eax
0x18002352f  jle     short loc_18002353A
0x180023531  movzx   edi, ax
0x180023534  or      edi, 80070000h
0x18002353a  test    edi, edi
0x18002353c  js      loc_180023723
0x180023542  mov     eax, 20Ah
0x180023547  cmp     si, ax
0x18002354a  jnb     short loc_180023560
0x18002354c  mov     rcx, [rbx+168h]
0x180023553  call    cs:__imp_FwMetaDataFree
0x180023559  mov     [rbx+168h], r13
0x180023560  mov     eax, [rbx+150h]
0x180023566  jmp     loc_1800236FE
0x18002356b  cmp     ebp, 1
0x18002356e  jnz     loc_180023628
0x180023574  movzx   r8d, [rsp+58h+arg_20]
0x18002357d  xor     edx, edx
0x18002357f  mov     rcx, rbx
0x180023582  call    cs:__imp_Int_FwValidateComplianceAndReduceConnSecRuleToVersion
0x180023588  mov     edi, eax
0x18002358a  test    eax, eax
0x18002358c  jle     short loc_180023597
0x18002358e  movzx   edi, ax
0x180023591  or      edi, 80070000h
0x180023597  test    edi, edi
0x180023599  js      loc_18002374B
0x18002359f  mov     eax, 218h
0x1800235a4  cmp     si, ax
0x1800235a7  jnb     short loc_1800235D0
0x1800235a9  movzx   eax, word ptr [rbx+154h]
0x1800235b0  bt      ax, 8
0x1800235b5  jnb     short loc_1800235D0
0x1800235b7  mov     ecx, 0FEFFh
0x1800235bc  mov     dword ptr [rbx+180h], 20000h
0x1800235c6  and     ax, cx
0x1800235c9  mov     [rbx+154h], ax
0x1800235d0  mov     eax, 20Ah
0x1800235d5  cmp     si, ax
0x1800235d8  jnb     short loc_18002361D
0x1800235da  mov     rcx, [rbx+188h]
0x1800235e1  test    rcx, rcx
0x1800235e4  jz      short loc_1800235FC
0x1800235e6  cmp     dword ptr [rbx+180h], 10000h
0x1800235f0  jnz     short loc_1800235FC
0x1800235f2  mov     dword ptr [rbx+180h], 20000h
0x1800235fc  call    cs:__imp_FwFree
0x180023602  mov     rcx, [rbx+198h]
0x180023609  mov     [rbx+188h], r13
0x180023610  call    cs:__imp_FwMetaDataFree
0x180023616  mov     [rbx+198h], r13
0x18002361d  mov     eax, [rbx+180h]
0x180023623  jmp     loc_1800236FE
0x180023628  cmp     ebp, 2
0x18002362b  jnz     short loc_180023691
0x18002362d  movzx   r8d, [rsp+58h+arg_20]
0x180023636  xor     edx, edx
0x180023638  mov     rcx, rbx
0x18002363b  call    cs:__imp_Int_FwValidateComplianceAndReduceMainModeRuleToVersion
0x180023641  mov     edi, eax
0x180023643  test    eax, eax
0x180023645  jle     short loc_180023650
0x180023647  movzx   edi, ax
0x18002364a  or      edi, 80070000h
0x180023650  test    edi, edi
0x180023652  js      loc_18002376B
0x180023658  mov     eax, 218h
0x18002365d  cmp     si, ax
0x180023660  jnb     short loc_180023689
0x180023662  movzx   eax, word ptr [rbx+0D0h]
0x180023669  bt      ax, 8
0x18002366e  jnb     short loc_180023689
0x180023670  mov     ecx, 0FEFFh
0x180023675  mov     dword ptr [rbx+100h], 20000h
0x18002367f  and     ax, cx
0x180023682  mov     [rbx+0D0h], ax
0x180023689  mov     eax, [rbx+100h]
0x18002368f  jmp     short loc_1800236FE
0x180023691  cmp     ebp, 4
0x180023694  jnz     short loc_1800236C6
0x180023696  movzx   r8d, [rsp+58h+arg_20]
0x18002369f  xor     edx, edx
0x1800236a1  mov     rcx, rbx
0x1800236a4  call    cs:__imp_Int_FwValidateComplianceAndReduceAuthSetToVersion
0x1800236aa  mov     edi, eax
0x1800236ac  test    eax, eax
0x1800236ae  jle     short loc_1800236B9
0x1800236b0  movzx   edi, ax
0x1800236b3  or      edi, 80070000h
0x1800236b9  test    edi, edi
0x1800236bb  js      loc_18002378B
0x1800236c1  mov     eax, [rbx+50h]
0x1800236c4  jmp     short loc_1800236FE
0x1800236c6  mov     eax, 10000h
0x1800236cb  cmp     ebp, 5
0x1800236ce  jnz     short loc_1800236FE
0x1800236d0  movzx   r8d, [rsp+58h+arg_20]
0x1800236d9  xor     edx, edx
0x1800236db  mov     rcx, rbx
0x1800236de  call    cs:__imp_Int_FwValidateComplianceAndReduceCryptoSetToVersion
0x1800236e4  mov     edi, eax
0x1800236e6  test    eax, eax
0x1800236e8  jle     short loc_1800236F3
0x1800236ea  movzx   edi, ax
0x1800236ed  or      edi, 80070000h
0x1800236f3  test    edi, edi
0x1800236f5  js      loc_1800237AB
0x1800236fb  mov     eax, [rbx+58h]
0x1800236fe  test    r12d, eax
0x180023701  jnz     short loc_180023718
0x180023703  mov     rax, [rbx]
0x180023706  mov     edx, ebp
0x180023708  mov     [r15], rax
0x18002370b  mov     rcx, rbx
0x18002370e  mov     [rbx], r13
0x180023711  call    FwFreeObjects
0x180023716  jmp     short loc_18002371B
0x180023718  mov     r15, rbx
0x18002371b  mov     rbx, [r15]
0x18002371e  jmp     loc_180023239
0x180023723  mov     rcx, cs:WPP_GLOBAL_Control
0x18002372a  lea     rax, WPP_GLOBAL_Control
0x180023731  cmp     rcx, rax
0x180023734  jz      loc_1800237DC
0x18002373a  test    byte ptr [rcx+1Ch], 1
0x18002373e  jz      loc_1800237DC
0x180023744  mov     edx, 1Fh
0x180023749  jmp     short loc_1800237C9
0x18002374b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023752  lea     rax, WPP_GLOBAL_Control
0x180023759  cmp     rcx, rax
0x18002375c  jz      short loc_1800237DC
0x18002375e  test    byte ptr [rcx+1Ch], 1
0x180023762  jz      short loc_1800237DC
0x180023764  mov     edx, 20h ; ' '
0x180023769  jmp     short loc_1800237C9
  ... truncated ...
```
