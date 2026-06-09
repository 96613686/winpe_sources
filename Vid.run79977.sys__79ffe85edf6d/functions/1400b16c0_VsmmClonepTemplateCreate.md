# VsmmClonepTemplateCreate

- ea: `0x1400b16c0`
- end: `0x1400b1e0f`
- name: `VsmmClonepTemplateCreate`
- size: `1871`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b06b0`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400347a4`
- `0x140034b64`
- `0x140074864`
- `0x1400758ec`
- `0x140078924`
- `0x1400b16c0`
- `0x1400d6dc0`
- `0x1400f4cc4`
- `0x1400f6a6c`
- `0x1400f9410`
- `0x1400fd58c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b1992`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b1992`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1885`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1885`
- `ntoskrnl!PsGetProcessJob` at `0x1400b1cd3`
- `ntoskrnl!PsGetProcessJob` at `0x1400b1cd3`

## string_xrefs

- `0x1400b1744`: `VsmmClonepTemplateCreate`
- `0x1400b1a35`: `VsmmClonepTemplateCreate`
- `0x1400b1a8f`: `VsmmClonepTemplateCreate`
- `0x1400b1b97`: `VsmmClonepTemplateCreate`
- `0x1400b1bf3`: `VsmmClonepTemplateCreate`
- `0x1400b1d12`: `VsmmClonepTemplateCreate`
- `0x1400b1d96`: `VsmmClonepTemplateCreate`

## pseudocode

```c
__int64 __fastcall VsmmClonepTemplateCreate(__int64 a1, char a2, _QWORD *a3)
{
  int v4; // ebx
  int v5; // edi
  int v6; // r11d
  _QWORD *v7; // rsi
  _DWORD *Next; // rax
  __int64 Pool2; // rax
  __int64 v10; // r8
  _QWORD *v11; // r15
  __int64 v12; // rcx
  bool v13; // zf
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  _DWORD *v16; // rdi
  int v17; // r11d
  void *v18; // rdx
  int v19; // r11d
  char *v20; // rbx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v26; // [rsp+60h] [rbp-A0h]
  _BYTE v27[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  __int64 *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  int *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h] BYREF
  int v40; // [rsp+FCh] [rbp-4h]
  __int64 *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]

  v26 = a3;
  P = 0;
  v4 = a2 & 1;
  v5 = VsmmClonepTemplateAlloc(!(a2 & 1), &P);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      v22 = 1482;
      v30 = (__int64 *)&v22;
      v32 = &v23;
      v34 = a1 + 656;
      v31 = 4;
      v36 = &v39;
      v38 = *(_QWORD *)(a1 + 128);
      v39 = *(unsigned __int16 *)(a1 + 120);
      v24 = *(_QWORD *)(a1 + 648);
      v41 = &v24;
      LODWORD(v23) = v5;
      v33 = 4;
      v35 = 16;
      v37 = 2;
      v40 = v6;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004E990, 0, 0, 10, v27);
    }
    v7 = P;
    goto LABEL_58;
  }
  v23 = -1;
  Next = (_DWORD *)VidHandleTableGetNext(a1 + 3232, &v23);
  v7 = P;
  while ( 1 )
  {
    v16 = Next;
    if ( !Next )
    {
      v5 = VsmmNtSlatMemoryProcessCreate(
             *(_QWORD *)(a1 + 10328),
             0,
             0,
             v4 != 0 ? 3 : 17,
             (PVOID)(a1 + 10336),
             (__int64)(v7 + 11),
             (__int64)(v7 + 12));
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_58;
        tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v23) = 1609;
        v18 = &unk_14004E76A;
        goto LABEL_47;
      }
      if ( v4 )
        goto LABEL_57;
      if ( PsGetProcessJob(v7[11]) )
      {
        v5 = -1073741811;
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_58;
        tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v23) = 1622;
        v18 = &unk_14004E7D8;
        goto LABEL_47;
      }
      v20 = (char *)VidDeviceExtension + 680;
      VidObjectLockAcquireExclusive((char *)VidDeviceExtension + 680);
      v5 = VsmmClonepTableInsertById(v20, v7);
      VidObjectLockRelease(v20);
      if ( v5 >= 0 )
      {
LABEL_57:
        v5 = 0;
        *v26 = v7;
        v7 = 0;
        goto LABEL_58;
      }
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_58;
      tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v23) = 1639;
      v18 = &unk_14004E846;
LABEL_47:
      v31 = 4;
      v30 = &v23;
      v32 = (__int64 *)&v22;
      v34 = a1 + 656;
      v22 = v5;
      v36 = &v39;
      v38 = *(_QWORD *)(a1 + 128);
      v39 = *(unsigned __int16 *)(a1 + 120);
      v24 = *(_QWORD *)(a1 + 648);
      v41 = &v24;
      v33 = 4;
      v35 = 16;
      v37 = 2;
      v40 = v17;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v18, 0, 0, 10, v27);
      goto LABEL_58;
    }
    if ( (Next[66] & 8) != 0 && (Next[32] & 0x10000000) == 0 )
      break;
LABEL_31:
    Next = (_DWORD *)VidHandleTableGetNext(a1 + 3232, &v23);
  }
  if ( Next[8] == 1 )
  {
    v5 = -1073741436;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_58;
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1526;
    v18 = &unk_14004E8B4;
    goto LABEL_47;
  }
  Pool2 = ExAllocatePool2(256, 80, 1833788502);
  v11 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_58;
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1542;
    v18 = &unk_14004E922;
    goto LABEL_47;
  }
  *(_QWORD *)(Pool2 + 24) = *((_QWORD *)v16 + 119);
  *(_QWORD *)(Pool2 + 32) = *((_QWORD *)v16 + 5) << 12;
  *(_DWORD *)(Pool2 + 44) = *(_DWORD *)(Pool2 + 44) & 0xFFFFFFFE | *((_WORD *)v16 + 133) & 1;
  *(_OWORD *)(Pool2 + 48) = *((_OWORD *)v16 + 61);
  if ( (v16[66] & 0x4000) == 0 || (v5 = VsmmBitmapClone(Pool2 + 64, v16 + 132), v5 >= 0) )
  {
    v12 = v11[3];
    v13 = (v7[14] & 1) == 0;
    v14 = v7[13];
    v24 = v12;
    if ( !v13 )
    {
      if ( v14 )
        v14 ^= (unsigned __int64)(v7 + 13);
      else
        v14 = 0;
    }
    LOBYTE(v10) = 0;
    v22 = v7[14] & 1;
    if ( v14 )
    {
      while ( 1 )
      {
        if ( (int)VsmmClonepTemplateCompareMemoryBlockEntry(v12, v14, v10) < 0 )
        {
          v15 = *(_QWORD *)v14;
          if ( v22 )
          {
            if ( !v15 )
              goto LABEL_29;
            v15 ^= v14;
          }
          if ( !v15 )
          {
LABEL_29:
            LOBYTE(v10) = 0;
            break;
          }
        }
        else
        {
          v15 = *(_QWORD *)(v14 + 8);
          if ( v22 )
          {
            if ( !v15 )
              goto LABEL_23;
            v15 ^= v14;
          }
          if ( !v15 )
          {
LABEL_23:
            LOBYTE(v10) = 1;
            break;
          }
        }
        v12 = v24;
        v14 = v15;
      }
    }
    RtlRbInsertNodeEx(v7 + 13, v14, v10, v11);
    goto LABEL_31;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1560;
    v30 = &v23;
    v32 = (__int64 *)&v22;
    v34 = a1 + 656;
    v31 = 4;
    v36 = &v39;
    v38 = *(_QWORD *)(a1 + 128);
    v39 = *(unsigned __int16 *)(a1 + 120);
    v24 = *(_QWORD *)(a1 + 648);
    v41 = &v24;
    v22 = v5;
    v33 = 4;
    v35 = 16;
    v37 = 2;
    v40 = v19;
    v42 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004E6FC, 0, 0, 10, v27);
  }
  VsmmClonepTemplateFreeMemoryBlockEntry(v11);
LABEL_58:
  if ( v7 )
    VsmmClonepTemplateFree(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400b16c0  mov     [rsp-8+arg_18], rbx
0x1400b16c5  push    rbp
0x1400b16c6  push    rsi
0x1400b16c7  push    rdi
0x1400b16c8  push    r12
0x1400b16ca  push    r13
0x1400b16cc  push    r14
0x1400b16ce  push    r15
0x1400b16d0  lea     rbp, [rsp-20h]
0x1400b16d5  sub     rsp, 120h
0x1400b16dc  mov     rax, cs:__security_cookie
0x1400b16e3  xor     rax, rsp
0x1400b16e6  mov     [rbp+50h+var_40], rax
0x1400b16ea  mov     ebx, edx
0x1400b16ec  mov     [rsp+150h+var_F0], r8
0x1400b16f1  mov     r13, rcx
0x1400b16f4  mov     [rsp+150h+P], 0
0x1400b16fd  and     ebx, 1
0x1400b1700  lea     rdx, [rsp+150h+P]
0x1400b1705  mov     ecx, ebx
0x1400b1707  xor     ecx, 1
0x1400b170a  call    VsmmClonepTemplateAlloc
0x1400b170f  xor     r11d, r11d
0x1400b1712  mov     edi, eax
0x1400b1714  test    eax, eax
0x1400b1716  jns     loc_1400B181E
0x1400b171c  mov     ecx, cs:dword_140065110
0x1400b1722  cmp     ecx, 2
0x1400b1725  jbe     loc_1400B1814
0x1400b172b  mov     edx, 100h
0x1400b1730  lea     rcx, dword_140065110
0x1400b1737  call    _tlgKeywordOn
0x1400b173c  test    al, al
0x1400b173e  jz      loc_1400B1814
0x1400b1744  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400b174b  lea     rcx, [rbp+50h+var_C0]
0x1400b174f  call    _tlgCreate1Sz_char
0x1400b1754  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b175b  lea     rcx, [rbp+50h+var_B0]
0x1400b175f  call    _tlgCreate1Sz_char
0x1400b1764  lea     rax, [rsp+150h+var_110]
0x1400b1769  mov     [rsp+150h+var_110], 5CAh
0x1400b1771  mov     [rbp+50h+var_A0], rax
0x1400b1775  lea     rcx, [rsp+150h+var_108]
0x1400b177a  lea     rax, [r13+290h]
0x1400b1781  mov     [rbp+50h+var_90], rcx
0x1400b1785  mov     [rbp+50h+var_80], rax
0x1400b1789  lea     rdx, unk_14004E990
0x1400b1790  lea     rax, [rbp+50h+var_58]
0x1400b1794  mov     [rbp+50h+var_98], 4
0x1400b179c  mov     [rbp+50h+var_70], rax
0x1400b17a0  lea     rcx, dword_140065110
0x1400b17a7  mov     rax, [r13+80h]
0x1400b17ae  xor     r9d, r9d
0x1400b17b1  mov     [rbp+50h+var_60], rax
0x1400b17b5  xor     r8d, r8d
0x1400b17b8  movzx   eax, word ptr [r13+78h]
0x1400b17bd  mov     [rbp+50h+var_58], eax
0x1400b17c0  mov     rax, [r13+288h]
0x1400b17c7  mov     [rsp+150h+var_100], rax
0x1400b17cc  lea     rax, [rsp+150h+var_100]
0x1400b17d1  mov     [rbp+50h+var_50], rax
0x1400b17d5  lea     rax, [rsp+150h+var_E0]
0x1400b17da  mov     [rsp+150h+var_128], rax
0x1400b17df  mov     dword ptr [rsp+150h+var_130], 0Ah
0x1400b17e7  mov     dword ptr [rsp+150h+var_108], edi
0x1400b17eb  mov     [rbp+50h+var_88], 4
0x1400b17f3  mov     [rbp+50h+var_78], 10h
0x1400b17fb  mov     [rbp+50h+var_68], 2
0x1400b1803  mov     [rbp+50h+var_54], r11d
0x1400b1807  mov     [rbp+50h+var_48], 8
0x1400b180f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b1814  mov     rsi, [rsp+150h+P]
0x1400b1819  jmp     loc_1400B1DD8
0x1400b181e  lea     rcx, [r13+0CA0h]
0x1400b1825  mov     [rsp+150h+var_108], 0FFFFFFFFFFFFFFFFh
0x1400b182e  lea     rdx, [rsp+150h+var_108]
0x1400b1833  call    VidHandleTableGetNext
0x1400b1838  mov     rsi, [rsp+150h+P]
0x1400b183d  mov     r14d, 100h
0x1400b1843  mov     r12d, 8
0x1400b1849  jmp     loc_1400B19B8
0x1400b184e  mov     ecx, [rdi+108h]
0x1400b1854  test    r12b, cl
0x1400b1857  jz      loc_1400B19A7
0x1400b185d  mov     ecx, [rdi+80h]
0x1400b1863  bt      ecx, 1Ch
0x1400b1867  jb      loc_1400B19A7
0x1400b186d  cmp     dword ptr [rdi+20h], 1
0x1400b1871  jz      loc_1400B1BC8
0x1400b1877  mov     edx, 50h ; 'P'
0x1400b187c  mov     r8d, 6D4D6456h
0x1400b1882  mov     rcx, r14
0x1400b1885  call    cs:__imp_ExAllocatePool2
0x1400b188c  nop     dword ptr [rax+rax+00h]
0x1400b1891  xor     r11d, r11d
0x1400b1894  mov     r15, rax
0x1400b1897  test    rax, rax
0x1400b189a  jz      loc_1400B1B6C
0x1400b18a0  mov     rcx, [rdi+3B8h]
0x1400b18a7  mov     [rax+18h], rcx
0x1400b18ab  mov     rcx, [rdi+28h]
0x1400b18af  shl     rcx, 0Ch
0x1400b18b3  mov     [rax+20h], rcx
0x1400b18b7  movzx   edx, word ptr [rdi+10Ah]
0x1400b18be  mov     ecx, [rax+2Ch]
0x1400b18c1  and     edx, 1
0x1400b18c4  and     ecx, 0FFFFFFFEh
0x1400b18c7  or      edx, ecx
0x1400b18c9  mov     [rax+2Ch], edx
0x1400b18cc  movups  xmm0, xmmword ptr [rdi+3D0h]
0x1400b18d3  movdqu  xmmword ptr [rax+30h], xmm0
0x1400b18d8  test    dword ptr [rdi+108h], 4000h
0x1400b18e2  jz      short loc_1400B1901
0x1400b18e4  lea     rdx, [rdi+210h]
0x1400b18eb  lea     rcx, [rax+40h]
0x1400b18ef  call    VsmmBitmapClone
0x1400b18f4  xor     r11d, r11d
0x1400b18f7  mov     edi, eax
0x1400b18f9  test    eax, eax
0x1400b18fb  js      loc_1400B1A69
0x1400b1901  mov     rcx, [r15+18h]
0x1400b1905  lea     r12, [rsi+68h]
0x1400b1909  test    byte ptr [r12+8], 1
0x1400b190f  mov     rdi, [r12]
0x1400b1913  mov     [rsp+150h+var_100], rcx
0x1400b1918  jz      short loc_1400B1927
0x1400b191a  test    rdi, rdi
0x1400b191d  jz      short loc_1400B1924
0x1400b191f  xor     rdi, r12
0x1400b1922  jmp     short loc_1400B1927
0x1400b1924  mov     rdi, r11
0x1400b1927  movzx   eax, byte ptr [r12+8]
0x1400b192d  mov     r8b, r11b
0x1400b1930  and     eax, 1
0x1400b1933  mov     [rsp+150h+var_110], eax
0x1400b1937  test    rdi, rdi
0x1400b193a  jz      short loc_1400B1989
0x1400b193c  mov     rdx, rdi
0x1400b193f  call    VsmmClonepTemplateCompareMemoryBlockEntry
0x1400b1944  test    eax, eax
0x1400b1946  js      short loc_1400B1965
0x1400b1948  cmp     [rsp+150h+var_110], 0
0x1400b194d  mov     rax, [rdi+8]
0x1400b1951  jz      short loc_1400B195B
0x1400b1953  test    rax, rax
0x1400b1956  jz      short loc_1400B1960
0x1400b1958  xor     rax, rdi
0x1400b195b  test    rax, rax
0x1400b195e  jnz     short loc_1400B197C
0x1400b1960  mov     r8b, 1
0x1400b1963  jmp     short loc_1400B1989
0x1400b1965  cmp     [rsp+150h+var_110], 0
0x1400b196a  mov     rax, [rdi]
0x1400b196d  jz      short loc_1400B1977
0x1400b196f  test    rax, rax
0x1400b1972  jz      short loc_1400B1986
0x1400b1974  xor     rax, rdi
0x1400b1977  test    rax, rax
0x1400b197a  jz      short loc_1400B1986
0x1400b197c  mov     rcx, [rsp+150h+var_100]
0x1400b1981  mov     rdi, rax
0x1400b1984  jmp     short loc_1400B193C
0x1400b1986  xor     r8b, r8b
0x1400b1989  mov     r9, r15
0x1400b198c  mov     rdx, rdi
0x1400b198f  mov     rcx, r12
0x1400b1992  call    cs:__imp_RtlRbInsertNodeEx
0x1400b1999  nop     dword ptr [rax+rax+00h]
0x1400b199e  xor     r11d, r11d
0x1400b19a1  mov     r12d, 8
0x1400b19a7  lea     rdx, [rsp+150h+var_108]
0x1400b19ac  lea     rcx, [r13+0CA0h]
0x1400b19b3  call    VidHandleTableGetNext
0x1400b19b8  mov     rdi, rax
0x1400b19bb  test    rax, rax
0x1400b19be  jnz     loc_1400B184E
0x1400b19c4  mov     eax, ebx
0x1400b19c6  lea     rcx, [rsi+60h]
0x1400b19ca  mov     [rsp+150h+var_120], rcx; __int64
0x1400b19cf  lea     rdx, [r13+2860h]
0x1400b19d6  mov     rcx, [r13+2858h]; int
0x1400b19dd  lea     r15, [rsi+58h]
0x1400b19e1  neg     eax
0x1400b19e3  mov     [rsp+150h+var_128], r15; __int64
0x1400b19e8  mov     [rsp+150h+var_130], rdx; PVOID
0x1400b19ed  sbb     r9d, r9d
0x1400b19f0  xor     r8d, r8d; int
0x1400b19f3  and     r9d, 0FFFFFFF2h
0x1400b19f7  xor     edx, edx; int
0x1400b19f9  add     r9d, 11h; int
0x1400b19fd  call    VsmmNtSlatMemoryProcessCreate
0x1400b1a02  xor     r11d, r11d
0x1400b1a05  mov     edi, eax
0x1400b1a07  test    eax, eax
0x1400b1a09  jns     loc_1400B1CC8
0x1400b1a0f  mov     eax, cs:dword_140065110
0x1400b1a15  cmp     eax, 2
0x1400b1a18  jbe     loc_1400B1DD8
0x1400b1a1e  mov     rdx, r14
0x1400b1a21  lea     rcx, dword_140065110
0x1400b1a28  call    _tlgKeywordOn
0x1400b1a2d  test    al, al
0x1400b1a2f  jz      loc_1400B1DD8
0x1400b1a35  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400b1a3c  lea     rcx, [rbp+50h+var_C0]
0x1400b1a40  call    _tlgCreate1Sz_char
0x1400b1a45  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b1a4c  lea     rcx, [rbp+50h+var_B0]
0x1400b1a50  call    _tlgCreate1Sz_char
0x1400b1a55  mov     dword ptr [rsp+150h+var_108], 649h
0x1400b1a5d  lea     rdx, unk_14004E76A
0x1400b1a64  jmp     loc_1400B1C22
0x1400b1a69  mov     eax, cs:dword_140065110
0x1400b1a6f  cmp     eax, 2
0x1400b1a72  jbe     loc_1400B1B5F
0x1400b1a78  mov     rdx, r14
0x1400b1a7b  lea     rcx, dword_140065110
0x1400b1a82  call    _tlgKeywordOn
0x1400b1a87  test    al, al
0x1400b1a89  jz      loc_1400B1B5F
0x1400b1a8f  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400b1a96  lea     rcx, [rbp+50h+var_C0]
0x1400b1a9a  call    _tlgCreate1Sz_char
0x1400b1a9f  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b1aa6  lea     rcx, [rbp+50h+var_B0]
0x1400b1aaa  call    _tlgCreate1Sz_char
0x1400b1aaf  lea     rax, [rsp+150h+var_108]
0x1400b1ab4  mov     dword ptr [rsp+150h+var_108], 618h
0x1400b1abc  mov     [rbp+50h+var_A0], rax
0x1400b1ac0  lea     rcx, [rsp+150h+var_110]
0x1400b1ac5  lea     rax, [r13+290h]
0x1400b1acc  mov     [rbp+50h+var_90], rcx
0x1400b1ad0  mov     [rbp+50h+var_80], rax
0x1400b1ad4  lea     rdx, unk_14004E6FC
0x1400b1adb  lea     rax, [rbp+50h+var_58]
0x1400b1adf  mov     [rbp+50h+var_98], 4
0x1400b1ae7  mov     [rbp+50h+var_70], rax
0x1400b1aeb  lea     rcx, dword_140065110
0x1400b1af2  mov     rax, [r13+80h]
0x1400b1af9  xor     r9d, r9d
0x1400b1afc  mov     [rbp+50h+var_60], rax
0x1400b1b00  xor     r8d, r8d
0x1400b1b03  movzx   eax, word ptr [r13+78h]
0x1400b1b08  mov     [rbp+50h+var_58], eax
0x1400b1b0b  mov     rax, [r13+288h]
0x1400b1b12  mov     [rsp+150h+var_100], rax
0x1400b1b17  lea     rax, [rsp+150h+var_100]
0x1400b1b1c  mov     [rbp+50h+var_50], rax
0x1400b1b20  lea     rax, [rsp+150h+var_E0]
0x1400b1b25  mov     [rsp+150h+var_128], rax
0x1400b1b2a  mov     dword ptr [rsp+150h+var_130], 0Ah
0x1400b1b32  mov     [rsp+150h+var_110], edi
0x1400b1b36  mov     [rbp+50h+var_88], 4
0x1400b1b3e  mov     [rbp+50h+var_78], 10h
0x1400b1b46  mov     [rbp+50h+var_68], 2
0x1400b1b4e  mov     [rbp+50h+var_54], r11d
0x1400b1b52  mov     [rbp+50h+var_48], 8
0x1400b1b5a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b1b5f  mov     rcx, r15; P
0x1400b1b62  call    VsmmClonepTemplateFreeMemoryBlockEntry
0x1400b1b67  jmp     loc_1400B1DD8
0x1400b1b6c  mov     eax, cs:dword_140065110
0x1400b1b72  mov     edi, 0C000009Ah
0x1400b1b77  cmp     eax, 2
0x1400b1b7a  jbe     loc_1400B1DD8
0x1400b1b80  mov     rdx, r14
0x1400b1b83  lea     rcx, dword_140065110
0x1400b1b8a  call    _tlgKeywordOn
0x1400b1b8f  test    al, al
0x1400b1b91  jz      loc_1400B1DD8
0x1400b1b97  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400b1b9e  lea     rcx, [rbp+50h+var_C0]
0x1400b1ba2  call    _tlgCreate1Sz_char
0x1400b1ba7  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b1bae  lea     rcx, [rbp+50h+var_B0]
0x1400b1bb2  call    _tlgCreate1Sz_char
0x1400b1bb7  mov     dword ptr [rsp+150h+var_108], 606h
0x1400b1bbf  lea     rdx, unk_14004E922
0x1400b1bc6  jmp     short loc_1400B1C22
0x1400b1bc8  mov     eax, cs:dword_140065110
0x1400b1bce  mov     edi, 0C0000184h
0x1400b1bd3  cmp     eax, 2
0x1400b1bd6  jbe     loc_1400B1DD8
0x1400b1bdc  mov     rdx, r14
0x1400b1bdf  lea     rcx, dword_140065110
0x1400b1be6  call    _tlgKeywordOn
0x1400b1beb  test    al, al
0x1400b1bed  jz      loc_1400B1DD8
0x1400b1bf3  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400b1bfa  lea     rcx, [rbp+50h+var_C0]
0x1400b1bfe  call    _tlgCreate1Sz_char
0x1400b1c03  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b1c0a  lea     rcx, [rbp+50h+var_B0]
0x1400b1c0e  call    _tlgCreate1Sz_char
0x1400b1c13  mov     dword ptr [rsp+150h+var_108], 5F6h
0x1400b1c1b  lea     rdx, unk_14004E8B4
0x1400b1c22  lea     rax, [rsp+150h+var_108]
0x1400b1c27  mov     [rbp+50h+var_98], 4
0x1400b1c2f  mov     [rbp+50h+var_A0], rax
  ... truncated ...
```
