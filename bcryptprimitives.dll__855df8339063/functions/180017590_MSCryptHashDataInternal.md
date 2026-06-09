# MSCryptHashDataInternal

- ea: `0x180017590`
- end: `0x1800178a0`
- name: `MSCryptHashDataInternal`
- size: `784`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180013b70`
- `0x180016db0`
- `0x180017240`
- `0x1800173f0`
- `0x1800185e0`

## callees

- `0x1800013f0`
- `0x18000ecb0`
- `0x1800151a0`
- `0x180015540`
- `0x180017590`
- `0x180018d40`
- `0x180031eb0`
- `0x1800325b0`
- `0x180040ef0`
- `0x1800455d0`
- `0x18004c1a0`
- `0x180057298`
- `0x180070660`
- `0x180070860`
- `0x180070b00`
- `0x180070b5c`
- `0x180070bec`

## string_xrefs

- `0x180017813`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashDataInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rdi
  unsigned int v6; // ebp
  __int64 v7; // rcx
  __int64 v9; // rdx
  __int64 (__fastcall **v10)(); // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int i; // edx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int j; // edx
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned int k; // edx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int m; // edx
  __int64 v28; // rax
  __int64 v29; // rcx

  v4 = a3;
  v6 = 0;
  switch ( *(_DWORD *)(a1 + 8) )
  {
    case 0x20001:
      v9 = a1 + 128;
      goto LABEL_6;
    case 0x20002:
      v12 = a1 + 128;
      goto LABEL_11;
    case 0x20003:
      v9 = a1 + 128;
      v10 = SymCryptMd2Algorithm_default;
      goto LABEL_7;
    case 0x20004:
      v9 = a1 + 128;
      v10 = SymCryptMd4Algorithm_default;
      goto LABEL_7;
    case 0x20005:
      v7 = a1 + 128;
      goto LABEL_3;
    case 0x20006:
      v13 = a1 + 128;
      goto LABEL_18;
    case 0x20007:
      v11 = a1 + 128;
      goto LABEL_9;
    case 0x20008:
      if ( *(_DWORD *)(a1 + 116) )
        SymCryptGcmAuthPart(a1 + 2736, a2, a3);
      else
        return (unsigned int)-1073740758;
      return v6;
    case 0x20009:
      v12 = a1 + 208;
LABEL_11:
      SymCryptSha1Append(v12, a2, a3);
      return v6;
    case 0x2000A:
      v9 = a1 + 176;
LABEL_6:
      v10 = &SymCryptMd5Algorithm_default;
LABEL_7:
      SymCryptHashAppendInternal(v10, v9, a2, a3);
      return v6;
    case 0x2000B:
      v7 = a1 + 208;
LABEL_3:
      SymCryptSha256Append(v7, a2, a3);
      return v6;
    case 0x2000C:
      v13 = a1 + 272;
LABEL_18:
      SymCryptSha512_256Append(v13, a2, a3);
      return v6;
    case 0x2000D:
      v11 = a1 + 272;
LABEL_9:
      SymCryptSha512Append(v11, a2, a3);
      return v6;
    case 0x2000E:
      SymCryptAesCmacAppend(a1 + 672, a2, a3);
      return v6;
    case 0x2000F:
    case 0x20010:
    case 0x20011:
    case 0x20019:
    case 0x2001A:
      SymCryptSha3_256Append(a1 + 128, a2, a3);
      return v6;
    case 0x20012:
    case 0x20013:
    case 0x20014:
      SymCryptHashAppend(**(_QWORD **)(a1 + 640), a1 + 656, a2, a3);
      return v6;
    case 0x20015:
      v14 = *(_DWORD *)(a1 + 280);
      if ( !v14 || v14 == 3 )
      {
        SymCryptCShake128Init(
          a1 + 288,
          *(_QWORD *)(a1 + 184),
          *(_DWORD *)(a1 + 192),
          *(_QWORD *)(a1 + 264),
          *(unsigned int *)(a1 + 272));
      }
      else if ( v14 != 1 )
      {
        goto LABEL_44;
      }
      for ( i = 0; i < *(_DWORD *)(a1 + 44); *(_OWORD *)(v20 + a1 + 752) = *(_OWORD *)(a1 + 512) )
      {
        v19 = i++;
        v20 = 240 * v19;
        *(_OWORD *)(v20 + a1 + 528) = *(_OWORD *)(a1 + 288);
        *(_OWORD *)(v20 + a1 + 544) = *(_OWORD *)(a1 + 304);
        *(_OWORD *)(v20 + a1 + 560) = *(_OWORD *)(a1 + 320);
        *(_OWORD *)(v20 + a1 + 576) = *(_OWORD *)(a1 + 336);
        *(_OWORD *)(v20 + a1 + 592) = *(_OWORD *)(a1 + 352);
        *(_OWORD *)(v20 + a1 + 608) = *(_OWORD *)(a1 + 368);
        *(_OWORD *)(v20 + a1 + 624) = *(_OWORD *)(a1 + 384);
        *(_OWORD *)(v20 + a1 + 640) = *(_OWORD *)(a1 + 400);
        *(_OWORD *)(v20 + a1 + 656) = *(_OWORD *)(a1 + 416);
        *(_OWORD *)(v20 + a1 + 672) = *(_OWORD *)(a1 + 432);
        *(_OWORD *)(v20 + a1 + 688) = *(_OWORD *)(a1 + 448);
        *(_OWORD *)(v20 + a1 + 704) = *(_OWORD *)(a1 + 464);
        *(_OWORD *)(v20 + a1 + 720) = *(_OWORD *)(a1 + 480);
        *(_OWORD *)(v20 + a1 + 736) = *(_OWORD *)(a1 + 496);
      }
      *(_DWORD *)(a1 + 280) = 2;
      goto LABEL_44;
    case 0x20016:
      v15 = *(_DWORD *)(a1 + 280);
      if ( !v15 || v15 == 3 )
      {
        SymCryptCShake256Init(
          a1 + 288,
          *(_QWORD *)(a1 + 184),
          *(_DWORD *)(a1 + 192),
          *(_QWORD *)(a1 + 264),
          *(unsigned int *)(a1 + 272));
      }
      else if ( v15 != 1 )
      {
        goto LABEL_44;
      }
      for ( j = 0; j < *(_DWORD *)(a1 + 44); *(_OWORD *)(v23 + a1 + 752) = *(_OWORD *)(a1 + 512) )
      {
        v22 = j++;
        v23 = 240 * v22;
        *(_OWORD *)(v23 + a1 + 528) = *(_OWORD *)(a1 + 288);
        *(_OWORD *)(v23 + a1 + 544) = *(_OWORD *)(a1 + 304);
        *(_OWORD *)(v23 + a1 + 560) = *(_OWORD *)(a1 + 320);
        *(_OWORD *)(v23 + a1 + 576) = *(_OWORD *)(a1 + 336);
        *(_OWORD *)(v23 + a1 + 592) = *(_OWORD *)(a1 + 352);
        *(_OWORD *)(v23 + a1 + 608) = *(_OWORD *)(a1 + 368);
        *(_OWORD *)(v23 + a1 + 624) = *(_OWORD *)(a1 + 384);
        *(_OWORD *)(v23 + a1 + 640) = *(_OWORD *)(a1 + 400);
        *(_OWORD *)(v23 + a1 + 656) = *(_OWORD *)(a1 + 416);
        *(_OWORD *)(v23 + a1 + 672) = *(_OWORD *)(a1 + 432);
        *(_OWORD *)(v23 + a1 + 688) = *(_OWORD *)(a1 + 448);
        *(_OWORD *)(v23 + a1 + 704) = *(_OWORD *)(a1 + 464);
        *(_OWORD *)(v23 + a1 + 720) = *(_OWORD *)(a1 + 480);
        *(_OWORD *)(v23 + a1 + 736) = *(_OWORD *)(a1 + 496);
      }
      *(_DWORD *)(a1 + 280) = 2;
LABEL_44:
      SymCryptCShake256Append(a1 + 528, a2, v4);
      return v6;
    case 0x20017:
      v16 = *(_DWORD *)(a1 + 528);
      if ( v16 )
      {
        if ( ((v16 - 1) & 0xFFFFFFFD) != 0 )
          goto LABEL_53;
      }
      else
      {
        SymCryptKmac128ExpandKeyEx(
          a1 + 128,
          *(_QWORD *)(a1 + 432),
          *(_DWORD *)(a1 + 440),
          *(_QWORD *)(a1 + 512),
          *(unsigned int *)(a1 + 520));
        *(_DWORD *)(a1 + 528) = 1;
      }
      for ( k = 0; k < *(_DWORD *)(a1 + 44); *(_OWORD *)(v26 + a1 + 768) = *(_OWORD *)(a1 + 352) )
      {
        v25 = k++;
        v26 = 240 * v25;
        *(_OWORD *)(v26 + a1 + 544) = *(_OWORD *)(a1 + 128);
        *(_OWORD *)(v26 + a1 + 560) = *(_OWORD *)(a1 + 144);
        *(_OWORD *)(v26 + a1 + 576) = *(_OWORD *)(a1 + 160);
        *(_OWORD *)(v26 + a1 + 592) = *(_OWORD *)(a1 + 176);
        *(_OWORD *)(v26 + a1 + 608) = *(_OWORD *)(a1 + 192);
        *(_OWORD *)(v26 + a1 + 624) = *(_OWORD *)(a1 + 208);
        *(_OWORD *)(v26 + a1 + 640) = *(_OWORD *)(a1 + 224);
        *(_OWORD *)(v26 + a1 + 656) = *(_OWORD *)(a1 + 240);
        *(_OWORD *)(v26 + a1 + 672) = *(_OWORD *)(a1 + 256);
        *(_OWORD *)(v26 + a1 + 688) = *(_OWORD *)(a1 + 272);
        *(_OWORD *)(v26 + a1 + 704) = *(_OWORD *)(a1 + 288);
        *(_OWORD *)(v26 + a1 + 720) = *(_OWORD *)(a1 + 304);
        *(_OWORD *)(v26 + a1 + 736) = *(_OWORD *)(a1 + 320);
        *(_OWORD *)(v26 + a1 + 752) = *(_OWORD *)(a1 + 336);
      }
      goto LABEL_52;
    case 0x20018:
      v17 = *(_DWORD *)(a1 + 528);
      if ( v17 )
      {
        if ( ((v17 - 1) & 0xFFFFFFFD) != 0 )
          goto LABEL_53;
      }
      else
      {
        SymCryptKmac256ExpandKeyEx(
          a1 + 128,
          *(_QWORD *)(a1 + 432),
          *(_DWORD *)(a1 + 440),
          *(_QWORD *)(a1 + 512),
          *(unsigned int *)(a1 + 520));
        *(_DWORD *)(a1 + 528) = 1;
      }
      for ( m = 0; m < *(_DWORD *)(a1 + 44); *(_OWORD *)(v29 + a1 + 768) = *(_OWORD *)(a1 + 352) )
      {
        v28 = m++;
        v29 = 240 * v28;
        *(_OWORD *)(v29 + a1 + 544) = *(_OWORD *)(a1 + 128);
        *(_OWORD *)(v29 + a1 + 560) = *(_OWORD *)(a1 + 144);
        *(_OWORD *)(v29 + a1 + 576) = *(_OWORD *)(a1 + 160);
        *(_OWORD *)(v29 + a1 + 592) = *(_OWORD *)(a1 + 176);
        *(_OWORD *)(v29 + a1 + 608) = *(_OWORD *)(a1 + 192);
        *(_OWORD *)(v29 + a1 + 624) = *(_OWORD *)(a1 + 208);
        *(_OWORD *)(v29 + a1 + 640) = *(_OWORD *)(a1 + 224);
        *(_OWORD *)(v29 + a1 + 656) = *(_OWORD *)(a1 + 240);
        *(_OWORD *)(v29 + a1 + 672) = *(_OWORD *)(a1 + 256);
        *(_OWORD *)(v29 + a1 + 688) = *(_OWORD *)(a1 + 272);
        *(_OWORD *)(v29 + a1 + 704) = *(_OWORD *)(a1 + 288);
        *(_OWORD *)(v29 + a1 + 720) = *(_OWORD *)(a1 + 304);
        *(_OWORD *)(v29 + a1 + 736) = *(_OWORD *)(a1 + 320);
        *(_OWORD *)(v29 + a1 + 752) = *(_OWORD *)(a1 + 336);
      }
LABEL_52:
      *(_DWORD *)(a1 + 528) = 2;
LABEL_53:
      SymCryptKeccakAppend(a1 + 544, a2, v4);
      return v6;
    default:
      v6 = -1073741637;
      DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 2205);
      return v6;
  }
}

```

## disassembly

```asm
0x180017590  push    rbx
0x180017592  push    rbp
0x180017593  push    rsi
0x180017594  push    rdi
0x180017595  sub     rsp, 38h
0x180017599  mov     eax, [rcx+8]
0x18001759c  mov     rsi, rdx
0x18001759f  add     eax, 0FFFDFFFFh; switch 26 cases
0x1800175a4  mov     edi, r8d
0x1800175a7  mov     rbx, rcx
0x1800175aa  cmp     eax, 19h
0x1800175ad  ja      def_1800175C6; jumptable 00000001800175C6 default case
0x1800175b3  lea     rcx, cs:180000000h
0x1800175ba  xor     ebp, ebp
0x1800175bc  mov     eax, ds:(jpt_1800175C6 - 180000000h)[rcx+rax*4]
0x1800175c3  add     rax, rcx
0x1800175c6  jmp     rax; switch jump
0x1800175cc  lea     rcx, [rbx+80h]; jumptable 00000001800175C6 case 131077
0x1800175d3  mov     r8, rdi
0x1800175d6  call    SymCryptSha256Append
0x1800175db  mov     eax, ebp
0x1800175dd  add     rsp, 38h
0x1800175e1  pop     rdi
0x1800175e2  pop     rsi
0x1800175e3  pop     rbp
0x1800175e4  pop     rbx
0x1800175e5  retn
0x1800175e7  mov     r8, rdi; jumptable 00000001800175C6 case 131087
0x1800175ea  lea     rcx, [rbx+80h]
0x1800175f1  call    SymCryptSha3_256Append
0x1800175f6  jmp     short loc_1800175DB
0x1800175f8  lea     rdx, [rbx+80h]; jumptable 00000001800175C6 case 131073
0x1800175ff  lea     rcx, SymCryptMd5Algorithm_default
0x180017606  mov     r9, rdi
0x180017609  mov     r8, rsi
0x18001760c  call    SymCryptHashAppendInternal
0x180017611  jmp     short loc_1800175DB
0x180017613  lea     rcx, [rbx+110h]; jumptable 00000001800175C6 case 131085
0x18001761a  mov     r8, rdi
0x18001761d  call    SymCryptSha512Append
0x180017622  jmp     short loc_1800175DB
0x180017624  lea     rcx, [rbx+80h]; jumptable 00000001800175C6 case 131074
0x18001762b  mov     r8, rdi
0x18001762e  call    SymCryptSha1Append
0x180017633  jmp     short loc_1800175DB
0x180017635  lea     rcx, [rbx+80h]; jumptable 00000001800175C6 case 131079
0x18001763c  jmp     short loc_18001761A
0x18001763e  lea     rdx, [rbx+0B0h]; jumptable 00000001800175C6 case 131082
0x180017645  jmp     short loc_1800175FF
0x180017647  lea     rdx, [rbx+80h]; jumptable 00000001800175C6 case 131075
0x18001764e  lea     rcx, SymCryptMd2Algorithm_default
0x180017655  jmp     short loc_180017606
0x180017657  lea     rdx, [rbx+80h]; jumptable 00000001800175C6 case 131076
0x18001765e  lea     rcx, SymCryptMd4Algorithm_default
0x180017665  jmp     short loc_180017606
0x180017667  lea     rcx, [rbx+80h]; jumptable 00000001800175C6 case 131078
0x18001766e  jmp     short loc_180017677
0x180017670  lea     rcx, [rbx+110h]; jumptable 00000001800175C6 case 131084
0x180017677  mov     r8, rdi
0x18001767a  call    SymCryptSha512_256Append
0x18001767f  jmp     loc_1800175DB
0x180017684  cmp     [rbx+74h], ebp; jumptable 00000001800175C6 case 131080
0x180017687  jnz     loc_180080DCA
0x18001768d  mov     ebp, 0C000042Ah
0x180017692  jmp     loc_1800175DB
0x180017697  lea     rcx, [rbx+0D0h]; jumptable 00000001800175C6 case 131081
0x18001769e  jmp     short loc_18001762B
0x1800176a0  lea     rcx, [rbx+0D0h]; jumptable 00000001800175C6 case 131083
0x1800176a7  jmp     loc_1800175D3
0x1800176ac  mov     r8, rdi; jumptable 00000001800175C6 case 131086
0x1800176af  lea     rcx, [rbx+2A0h]
0x1800176b6  call    SymCryptAesCmacAppend
0x1800176bb  jmp     loc_1800175DB
0x1800176c0  mov     r8, rdi; jumptable 00000001800175C6 case 131088
0x1800176c3  lea     rcx, [rbx+80h]
0x1800176ca  call    SymCryptSha3_256Append
0x1800176cf  jmp     loc_1800175DB
0x1800176d4  mov     r8, rdi; jumptable 00000001800175C6 case 131089
0x1800176d7  lea     rcx, [rbx+80h]
0x1800176de  call    SymCryptSha3_256Append
0x1800176e3  jmp     loc_1800175DB
0x1800176e8  mov     rcx, [rbx+280h]; jumptable 00000001800175C6 cases 131090-131092
0x1800176ef  lea     rdx, [rbx+290h]
0x1800176f6  mov     r9, rdi
0x1800176f9  mov     r8, rsi
0x1800176fc  mov     rcx, [rcx]
0x1800176ff  call    SymCryptHashAppend
0x180017704  jmp     loc_1800175DB
0x180017709  mov     eax, [rbx+118h]; jumptable 00000001800175C6 case 131093
0x18001770f  test    eax, eax
0x180017711  jz      loc_180080DDF
0x180017717  cmp     eax, 3
0x18001771a  jz      loc_180080DDF
0x180017720  cmp     eax, 1
0x180017723  jz      loc_180080E0B
0x180017729  jmp     loc_180080F15
0x18001772e  mov     eax, [rbx+118h]; jumptable 00000001800175C6 case 131094
0x180017734  test    eax, eax
0x180017736  jz      loc_180080F2D
0x18001773c  cmp     eax, 3
0x18001773f  jz      loc_180080F2D
0x180017745  cmp     eax, 1
0x180017748  jz      loc_180080F59
0x18001774e  jmp     loc_180081063
0x180017753  mov     eax, [rbx+210h]; jumptable 00000001800175C6 case 131095
0x180017759  test    eax, eax
0x18001775b  jnz     loc_18008107B
0x180017761  mov     eax, [rbx+208h]
0x180017767  lea     rcx, [rbx+80h]
0x18001776e  mov     r8d, [rbx+1B8h]
0x180017775  mov     r9, [rbx+200h]
0x18001777c  mov     rdx, [rbx+1B0h]
0x180017783  mov     [rsp+58h+var_38], rax
0x180017788  call    SymCryptKmac128ExpandKeyEx
0x18001778d  mov     dword ptr [rbx+210h], 1
0x180017797  jmp     loc_180081088
0x18001779c  mov     eax, [rbx+210h]; jumptable 00000001800175C6 case 131096
0x1800177a2  test    eax, eax
0x1800177a4  jnz     loc_1800811AA
0x1800177aa  mov     eax, [rbx+208h]
0x1800177b0  lea     rcx, [rbx+80h]
0x1800177b7  mov     r8d, [rbx+1B8h]
0x1800177be  mov     r9, [rbx+200h]
0x1800177c5  mov     rdx, [rbx+1B0h]
0x1800177cc  mov     [rsp+58h+var_38], rax
0x1800177d1  call    SymCryptKmac256ExpandKeyEx
0x1800177d6  mov     dword ptr [rbx+210h], 1
0x1800177e0  jmp     loc_1800811B3
0x1800177e5  mov     r8, rdi; jumptable 00000001800175C6 case 131097
0x1800177e8  lea     rcx, [rbx+80h]
0x1800177ef  call    SymCryptSha3_256Append
0x1800177f4  jmp     loc_1800175DB
0x1800177f9  mov     r8, rdi; jumptable 00000001800175C6 case 131098
0x1800177fc  lea     rcx, [rbx+80h]
0x180017803  call    SymCryptSha3_256Append
0x180017808  jmp     loc_1800175DB
0x18001780d  mov     r9d, 89Dh; jumptable 00000001800175C6 default case
0x180017813  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001781a  lea     rdx, aStatus; "Status"
0x180017821  mov     ecx, 0C00000BBh
0x180017826  mov     ebp, 0C00000BBh
0x18001782b  call    DebugTraceError
0x180017830  jmp     loc_1800175DB
0x180080dca  mov     r8, rdi
0x180080dcd  lea     rcx, [rbx+0AB0h]
0x180080dd4  call    SymCryptGcmAuthPart
0x180080dd9  nop
0x180080dda  jmp     loc_1800175DB
0x180080ddf  mov     eax, [rbx+110h]
0x180080de5  lea     rcx, [rbx+120h]
0x180080dec  mov     r8d, [rbx+0C0h]
0x180080df3  mov     r9, [rbx+108h]
0x180080dfa  mov     rdx, [rbx+0B8h]
0x180080e01  mov     [rsp+58h+var_38], rax
0x180080e06  call    SymCryptCShake128Init
0x180080e0b  xor     edx, edx
0x180080e0d  cmp     [rbx+2Ch], edx
0x180080e10  jbe     loc_180080F0B
0x180080e16  movups  xmm0, xmmword ptr [rbx+120h]
0x180080e1d  mov     eax, edx
0x180080e1f  inc     edx
0x180080e21  imul    rcx, rax, 0F0h
0x180080e28  movups  xmmword ptr [rcx+rbx+210h], xmm0
0x180080e30  movups  xmm1, xmmword ptr [rbx+130h]
0x180080e37  movups  xmmword ptr [rcx+rbx+220h], xmm1
0x180080e3f  movups  xmm0, xmmword ptr [rbx+140h]
0x180080e46  movups  xmmword ptr [rcx+rbx+230h], xmm0
0x180080e4e  movups  xmm1, xmmword ptr [rbx+150h]
0x180080e55  movups  xmmword ptr [rcx+rbx+240h], xmm1
0x180080e5d  movups  xmm0, xmmword ptr [rbx+160h]
0x180080e64  movups  xmmword ptr [rcx+rbx+250h], xmm0
0x180080e6c  movups  xmm1, xmmword ptr [rbx+170h]
0x180080e73  movups  xmmword ptr [rcx+rbx+260h], xmm1
0x180080e7b  movups  xmm0, xmmword ptr [rbx+180h]
0x180080e82  movups  xmmword ptr [rcx+rbx+270h], xmm0
0x180080e8a  movups  xmm1, xmmword ptr [rbx+190h]
0x180080e91  movups  xmmword ptr [rcx+rbx+280h], xmm1
0x180080e99  movups  xmm0, xmmword ptr [rbx+1A0h]
0x180080ea0  movups  xmmword ptr [rcx+rbx+290h], xmm0
0x180080ea8  movups  xmm1, xmmword ptr [rbx+1B0h]
0x180080eaf  movups  xmmword ptr [rcx+rbx+2A0h], xmm1
0x180080eb7  movups  xmm0, xmmword ptr [rbx+1C0h]
0x180080ebe  movups  xmmword ptr [rcx+rbx+2B0h], xmm0
0x180080ec6  movups  xmm1, xmmword ptr [rbx+1D0h]
0x180080ecd  movups  xmmword ptr [rcx+rbx+2C0h], xmm1
0x180080ed5  movups  xmm0, xmmword ptr [rbx+1E0h]
0x180080edc  movups  xmmword ptr [rcx+rbx+2D0h], xmm0
0x180080ee4  movups  xmm1, xmmword ptr [rbx+1F0h]
0x180080eeb  movups  xmmword ptr [rcx+rbx+2E0h], xmm1
0x180080ef3  movups  xmm0, xmmword ptr [rbx+200h]
0x180080efa  movups  xmmword ptr [rcx+rbx+2F0h], xmm0
0x180080f02  cmp     edx, [rbx+2Ch]
0x180080f05  jb      loc_180080E16
0x180080f0b  mov     dword ptr [rbx+118h], 2
0x180080f15  mov     r8, rdi
0x180080f18  lea     rcx, [rbx+210h]
0x180080f1f  mov     rdx, rsi
0x180080f22  call    SymCryptCShake256Append
0x180080f27  nop
0x180080f28  jmp     loc_1800175DB
0x180080f2d  mov     eax, [rbx+110h]
0x180080f33  lea     rcx, [rbx+120h]
0x180080f3a  mov     r8d, [rbx+0C0h]
0x180080f41  mov     r9, [rbx+108h]
0x180080f48  mov     rdx, [rbx+0B8h]
0x180080f4f  mov     [rsp+58h+var_38], rax
0x180080f54  call    SymCryptCShake256Init
0x180080f59  xor     edx, edx
0x180080f5b  cmp     [rbx+2Ch], edx
0x180080f5e  jbe     loc_180081059
0x180080f64  movups  xmm0, xmmword ptr [rbx+120h]
0x180080f6b  mov     eax, edx
0x180080f6d  inc     edx
0x180080f6f  imul    rcx, rax, 0F0h
0x180080f76  movups  xmmword ptr [rcx+rbx+210h], xmm0
0x180080f7e  movups  xmm1, xmmword ptr [rbx+130h]
0x180080f85  movups  xmmword ptr [rcx+rbx+220h], xmm1
0x180080f8d  movups  xmm0, xmmword ptr [rbx+140h]
0x180080f94  movups  xmmword ptr [rcx+rbx+230h], xmm0
0x180080f9c  movups  xmm1, xmmword ptr [rbx+150h]
0x180080fa3  movups  xmmword ptr [rcx+rbx+240h], xmm1
0x180080fab  movups  xmm0, xmmword ptr [rbx+160h]
0x180080fb2  movups  xmmword ptr [rcx+rbx+250h], xmm0
0x180080fba  movups  xmm1, xmmword ptr [rbx+170h]
0x180080fc1  movups  xmmword ptr [rcx+rbx+260h], xmm1
0x180080fc9  movups  xmm0, xmmword ptr [rbx+180h]
0x180080fd0  movups  xmmword ptr [rcx+rbx+270h], xmm0
0x180080fd8  movups  xmm1, xmmword ptr [rbx+190h]
0x180080fdf  movups  xmmword ptr [rcx+rbx+280h], xmm1
0x180080fe7  movups  xmm0, xmmword ptr [rbx+1A0h]
0x180080fee  movups  xmmword ptr [rcx+rbx+290h], xmm0
0x180080ff6  movups  xmm1, xmmword ptr [rbx+1B0h]
0x180080ffd  movups  xmmword ptr [rcx+rbx+2A0h], xmm1
0x180081005  movups  xmm0, xmmword ptr [rbx+1C0h]
0x18008100c  movups  xmmword ptr [rcx+rbx+2B0h], xmm0
0x180081014  movups  xmm1, xmmword ptr [rbx+1D0h]
0x18008101b  movups  xmmword ptr [rcx+rbx+2C0h], xmm1
0x180081023  movups  xmm0, xmmword ptr [rbx+1E0h]
0x18008102a  movups  xmmword ptr [rcx+rbx+2D0h], xmm0
0x180081032  movups  xmm1, xmmword ptr [rbx+1F0h]
0x180081039  movups  xmmword ptr [rcx+rbx+2E0h], xmm1
0x180081041  movups  xmm0, xmmword ptr [rbx+200h]
0x180081048  movups  xmmword ptr [rcx+rbx+2F0h], xmm0
0x180081050  cmp     edx, [rbx+2Ch]
0x180081053  jb      loc_180080F64
0x180081059  mov     dword ptr [rbx+118h], 2
0x180081063  mov     r8, rdi
0x180081066  lea     rcx, [rbx+210h]
0x18008106d  mov     rdx, rsi
0x180081070  call    SymCryptCShake256Append
0x180081075  nop
0x180081076  jmp     loc_1800175DB
0x18008107b  dec     eax
0x18008107d  test    eax, 0FFFFFFFDh
0x180081082  jnz     loc_180081192
0x180081088  xor     edx, edx
0x18008108a  cmp     [rbx+2Ch], edx
0x18008108d  jbe     loc_180081188
0x180081093  movups  xmm0, xmmword ptr [rbx+80h]
0x18008109a  mov     eax, edx
0x18008109c  inc     edx
0x18008109e  imul    rcx, rax, 0F0h
0x1800810a5  movups  xmmword ptr [rcx+rbx+220h], xmm0
0x1800810ad  movups  xmm1, xmmword ptr [rbx+90h]
0x1800810b4  movups  xmmword ptr [rcx+rbx+230h], xmm1
0x1800810bc  movups  xmm0, xmmword ptr [rbx+0A0h]
0x1800810c3  movups  xmmword ptr [rcx+rbx+240h], xmm0
0x1800810cb  movups  xmm1, xmmword ptr [rbx+0B0h]
0x1800810d2  movups  xmmword ptr [rcx+rbx+250h], xmm1
0x1800810da  movups  xmm0, xmmword ptr [rbx+0C0h]
0x1800810e1  movups  xmmword ptr [rcx+rbx+260h], xmm0
0x1800810e9  movups  xmm1, xmmword ptr [rbx+0D0h]
0x1800810f0  movups  xmmword ptr [rcx+rbx+270h], xmm1
0x1800810f8  movups  xmm0, xmmword ptr [rbx+0E0h]
0x1800810ff  movups  xmmword ptr [rcx+rbx+280h], xmm0
0x180081107  movups  xmm1, xmmword ptr [rbx+0F0h]
0x18008110e  movups  xmmword ptr [rcx+rbx+290h], xmm1
0x180081116  movups  xmm0, xmmword ptr [rbx+100h]
0x18008111d  movups  xmmword ptr [rcx+rbx+2A0h], xmm0
0x180081125  movups  xmm1, xmmword ptr [rbx+110h]
0x18008112c  movups  xmmword ptr [rcx+rbx+2B0h], xmm1
0x180081134  movups  xmm0, xmmword ptr [rbx+120h]
0x18008113b  movups  xmmword ptr [rcx+rbx+2C0h], xmm0
0x180081143  movups  xmm1, xmmword ptr [rbx+130h]
0x18008114a  movups  xmmword ptr [rcx+rbx+2D0h], xmm1
0x180081152  movups  xmm0, xmmword ptr [rbx+140h]
0x180081159  movups  xmmword ptr [rcx+rbx+2E0h], xmm0
0x180081161  movups  xmm1, xmmword ptr [rbx+150h]
0x180081168  movups  xmmword ptr [rcx+rbx+2F0h], xmm1
0x180081170  movups  xmm0, xmmword ptr [rbx+160h]
0x180081177  movups  xmmword ptr [rcx+rbx+300h], xmm0
0x18008117f  cmp     edx, [rbx+2Ch]
0x180081182  jb      loc_180081093
0x180081188  mov     dword ptr [rbx+210h], 2
0x180081192  mov     r8, rdi
0x180081195  lea     rcx, [rbx+220h]
0x18008119c  mov     rdx, rsi
0x18008119f  call    SymCryptKeccakAppend
0x1800811a4  nop
0x1800811a5  jmp     loc_1800175DB
  ... truncated ...
```
