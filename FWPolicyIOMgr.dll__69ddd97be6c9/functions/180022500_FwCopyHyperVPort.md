# FwCopyHyperVPort

- ea: `0x180022500`
- end: `0x180022687`
- name: `FwCopyHyperVPort`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001cdc`
- `0x180022500`
- `0x180022ee0`

## import_xrefs

- `fwbase!FwAlloc` at `0x18002251d`
- `fwbase!FwAlloc` at `0x18002251d`
- `fwbase!FwStringCopy` at `0x18002255d`
- `fwbase!FwStringCopy` at `0x1800225a3`
- `fwbase!FwStringCopy` at `0x1800225e6`
- `fwbase!FwStringCopy` at `0x18002261a`
- `fwbase!FwStringCopy` at `0x18002255d`
- `fwbase!FwStringCopy` at `0x1800225a3`
- `fwbase!FwStringCopy` at `0x1800225e6`
- `fwbase!FwStringCopy` at `0x18002261a`

## string_xrefs

- `0x18002258f`: `FwStringCopy:switchName`
- `0x1800225d5`: `FwStringCopy:portName`
- `0x180022644`: `FwStringCopy:constrainedInterfaceAlias`

## pseudocode

```c
__int64 __fastcall FwCopyHyperVPort(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  int v5; // ebx
  LPCOLESTR v6; // rcx
  int v7; // edx
  const char *v8; // rax

  *a2 = 0;
  v4 = FwAlloc(96);
  *(_OWORD *)(v4 + 24) = *(_OWORD *)(a1 + 24);
  *(_OWORD *)(v4 + 40) = *(_OWORD *)(a1 + 40);
  *(_OWORD *)(v4 + 56) = *(_OWORD *)(a1 + 56);
  *(_DWORD *)(v4 + 72) = *(_DWORD *)(a1 + 72);
  *(_DWORD *)(v4 + 76) = *(_DWORD *)(a1 + 76);
  *(_DWORD *)(v4 + 80) = *(_DWORD *)(a1 + 80);
  v5 = FwStringCopy(*(_QWORD *)(a1 + 8), v4 + 8);
  if ( v5 >= 0 )
  {
    v5 = FwStringCopy(*(_QWORD *)(a1 + 16), v4 + 16);
    if ( v5 >= 0 )
    {
      v5 = FwStringCopy(*(_QWORD *)(a1 + 88), v4 + 88);
      if ( v5 >= 0 )
      {
        v5 = FwStringCopy(*(_QWORD *)(a1 + 88), v4 + 88);
        if ( v5 >= 0 )
        {
          *a2 = v4;
          return (unsigned int)v5;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_19;
        v7 = 213;
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_19;
        v7 = 212;
      }
      v8 = "FwStringCopy:constrainedInterfaceAlias";
      goto LABEL_18;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 211;
      v8 = "FwStringCopy:portName";
      goto LABEL_18;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 210;
      v8 = "FwStringCopy:switchName";
LABEL_18:
      WPP_SF_ds(*((_QWORD *)v6 + 2), v7, (unsigned int)WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v5, (__int64)v8);
    }
  }
LABEL_19:
  if ( v4 )
    FwFreeHyperVPortsBySchemaVersion(v4, 545);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022500  push    rbx
0x180022502  push    rbp
0x180022503  push    rsi
0x180022504  push    rdi
0x180022505  push    r14
0x180022507  sub     rsp, 30h
0x18002250b  mov     rsi, rcx
0x18002250e  mov     qword ptr [rdx], 0
0x180022515  mov     ecx, 60h ; '`'
0x18002251a  mov     r14, rdx
0x18002251d  call    cs:__imp_FwAlloc
0x180022523  movups  xmm0, xmmword ptr [rsi+18h]
0x180022527  mov     rdi, rax
0x18002252a  movdqu  xmmword ptr [rax+18h], xmm0
0x18002252f  lea     rdx, [rax+8]
0x180022533  movups  xmm1, xmmword ptr [rsi+28h]
0x180022537  movdqu  xmmword ptr [rax+28h], xmm1
0x18002253c  movups  xmm0, xmmword ptr [rsi+38h]
0x180022540  movdqu  xmmword ptr [rax+38h], xmm0
0x180022545  mov     r8d, [rsi+48h]
0x180022549  mov     [rax+48h], r8d
0x18002254d  mov     ecx, [rsi+4Ch]
0x180022550  mov     [rax+4Ch], ecx
0x180022553  mov     ecx, [rsi+50h]
0x180022556  mov     [rax+50h], ecx
0x180022559  mov     rcx, [rsi+8]
0x18002255d  call    cs:__imp_FwStringCopy
0x180022563  mov     ebx, eax
0x180022565  test    eax, eax
0x180022567  jns     short loc_18002259B
0x180022569  mov     rcx, cs:WPP_GLOBAL_Control
0x180022570  lea     rax, WPP_GLOBAL_Control
0x180022577  cmp     rcx, rax
0x18002257a  jz      loc_180022663
0x180022580  test    byte ptr [rcx+1Ch], 1
0x180022584  jz      loc_180022663
0x18002258a  mov     edx, 0D2h
0x18002258f  lea     rax, aFwstringcopySw; "FwStringCopy:switchName"
0x180022596  jmp     loc_18002264B
0x18002259b  mov     rcx, [rsi+10h]
0x18002259f  lea     rdx, [rdi+10h]
0x1800225a3  call    cs:__imp_FwStringCopy
0x1800225a9  mov     ebx, eax
0x1800225ab  test    eax, eax
0x1800225ad  jns     short loc_1800225DE
0x1800225af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225b6  lea     rax, WPP_GLOBAL_Control
0x1800225bd  cmp     rcx, rax
0x1800225c0  jz      loc_180022663
0x1800225c6  test    byte ptr [rcx+1Ch], 1
0x1800225ca  jz      loc_180022663
0x1800225d0  mov     edx, 0D3h
0x1800225d5  lea     rax, aFwstringcopyPo; "FwStringCopy:portName"
0x1800225dc  jmp     short loc_18002264B
0x1800225de  mov     rcx, [rsi+58h]
0x1800225e2  lea     rdx, [rdi+58h]
0x1800225e6  call    cs:__imp_FwStringCopy
0x1800225ec  mov     ebx, eax
0x1800225ee  test    eax, eax
0x1800225f0  jns     short loc_180022612
0x1800225f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225f9  lea     rax, WPP_GLOBAL_Control
0x180022600  cmp     rcx, rax
0x180022603  jz      short loc_180022663
0x180022605  test    byte ptr [rcx+1Ch], 1
0x180022609  jz      short loc_180022663
0x18002260b  mov     edx, 0D4h
0x180022610  jmp     short loc_180022644
0x180022612  mov     rcx, [rsi+58h]
0x180022616  lea     rdx, [rdi+58h]
0x18002261a  call    cs:__imp_FwStringCopy
0x180022620  mov     ebx, eax
0x180022622  test    eax, eax
0x180022624  jns     short loc_180022677
0x180022626  mov     rcx, cs:WPP_GLOBAL_Control
0x18002262d  lea     rax, WPP_GLOBAL_Control
0x180022634  cmp     rcx, rax
0x180022637  jz      short loc_180022663
0x180022639  test    byte ptr [rcx+1Ch], 1
0x18002263d  jz      short loc_180022663
0x18002263f  mov     edx, 0D5h
0x180022644  lea     rax, aFwstringcopyCo; "FwStringCopy:constrainedInterfaceAlias"
0x18002264b  mov     rcx, [rcx+10h]
0x18002264f  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180022656  mov     r9d, ebx
0x180022659  mov     [rsp+58h+var_38], rax
0x18002265e  call    WPP_SF_ds
0x180022663  test    rdi, rdi
0x180022666  jz      short loc_18002267A
0x180022668  mov     edx, 221h
0x18002266d  mov     rcx, rdi
0x180022670  call    FwFreeHyperVPortsBySchemaVersion
0x180022675  jmp     short loc_18002267A
0x180022677  mov     [r14], rdi
0x18002267a  mov     eax, ebx
0x18002267c  add     rsp, 30h
0x180022680  pop     r14
0x180022682  pop     rdi
0x180022683  pop     rsi
0x180022684  pop     rbp
0x180022685  pop     rbx
0x180022686  retn
```
