# MSCryptEccGenerateKeyPair

- ea: `0x18000fe20`
- end: `0x180010262`
- name: `MSCryptEccGenerateKeyPair`
- size: `1090`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe00`
- `0x18004fda0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000fe20`
- `0x180010270`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000fede`
- `ntdll!RtlAllocateHeap` at `0x18000fede`

## string_xrefs

- `0x18000fef4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18000ff6b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18000ffb8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180010032`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180010087`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800100d9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800101a1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800101fd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18001022e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccGenerateKeyPair(__int64 a1, _QWORD *a2, int a3, int a4, int a5)
{
  int v6; // r11d
  wchar_t **v9; // r9
  __int64 i; // rax
  _QWORD *v11; // rcx
  int v12; // ebp
  _OWORD *Heap; // rax
  int v14; // edx
  int v15; // r8d
  _OWORD *v16; // rdi
  __int64 v17; // rcx
  __int64 result; // rax
  unsigned int v19; // ebp
  _QWORD *v20; // rcx

  v6 = a3;
  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297301836 && *(_DWORD *)a1 == 24 )
    {
      v9 = &off_180084710;
      if ( !a5 )
        v9 = &off_1800847D0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 4 )
          goto LABEL_31;
        a3 = 6 * i;
        if ( *(_DWORD *)(a1 + 8) == LODWORD(v9[6 * i + 1]) )
          break;
      }
      if ( v9[6 * i] )
      {
        v11 = *(_QWORD **)(a1 + 16);
        if ( v11 )
        {
          v12 = *(_DWORD *)(*v11 + 12LL);
          LODWORD(v11) = *(_DWORD *)(v11[1] + 12LL);
        }
        else
        {
          v12 = 0;
        }
        if ( v6 && (_DWORD)v11 != v6 )
        {
          DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 526);
          v20 = WPP_GLOBAL_Control;
          goto LABEL_27;
        }
        if ( !a2 || a4 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              a3,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              188);
          return 3221225485LL;
        }
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
        v16 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          *((_QWORD *)Heap + 4) = 0;
          *((_DWORD *)Heap + 2) = *(_DWORD *)(a1 + 8);
          *(_DWORD *)Heap = 40;
          *((_DWORD *)Heap + 1) = 1297304409;
          v17 = *(_QWORD *)(a1 + 16);
          if ( v17 )
          {
            if ( !v12 || v12 == *(_DWORD *)(*(_QWORD *)v17 + 12LL) )
            {
              *((_DWORD *)Heap + 8) |= 1u;
              *((_QWORD *)Heap + 2) = v17;
              goto LABEL_19;
            }
            v19 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                v15,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                88);
          }
          else
          {
            if ( !v12 )
            {
LABEL_19:
              result = 0;
              *a2 = v16;
              return result;
            }
            v19 = -1073741811;
            DebugTraceError(
              3221225485LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              1640);
          }
          MSCryptFree(v16);
        }
        else
        {
          v19 = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              v15,
              (unsigned int)"Status",
              23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              62);
        }
        DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2755);
        return v19;
      }
LABEL_31:
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          249);
        v20 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          241);
        v20 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
      v20 = WPP_GLOBAL_Control;
    }
  }
LABEL_27:
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      v20[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      181);
    return 3221225485LL;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000fe20  push    rbx
0x18000fe22  push    rbp
0x18000fe23  push    rsi
0x18000fe24  push    r14
0x18000fe26  sub     rsp, 48h
0x18000fe2a  mov     r10d, r9d
0x18000fe2d  mov     r11d, r8d
0x18000fe30  mov     r14, rdx
0x18000fe33  mov     rbx, rcx
0x18000fe36  test    rcx, rcx
0x18000fe39  jz      loc_18000FF9B
0x18000fe3f  cmp     dword ptr [rcx+4], 4D53414Ch
0x18000fe46  jnz     loc_1800100B4
0x18000fe4c  cmp     dword ptr [rcx], 18h
0x18000fe4f  jnz     loc_1800100B4
0x18000fe55  cmp     [rsp+68h+arg_20], 0
0x18000fe5d  lea     rax, off_1800847D0; "ECDH_P256"
0x18000fe64  lea     r9, off_180084710; "ECDSA_P256"
0x18000fe6b  cmovz   r9, rax
0x18000fe6f  xor     eax, eax
0x18000fe71  cmp     eax, 4
0x18000fe74  jnb     loc_180010015
0x18000fe7a  lea     r8, [rax+rax*2]
0x18000fe7e  add     r8, r8
0x18000fe81  mov     ecx, [r9+r8*8+8]
0x18000fe86  cmp     [rbx+8], ecx
0x18000fe89  jz      short loc_18000FE8F
0x18000fe8b  inc     eax
0x18000fe8d  jmp     short loc_18000FE71
0x18000fe8f  cmp     qword ptr [r9+r8*8], 0
0x18000fe94  jz      loc_180010015
0x18000fe9a  mov     rcx, [rbx+10h]
0x18000fe9e  test    rcx, rcx
0x18000fea1  jnz     loc_180010003
0x18000fea7  xor     ebp, ebp
0x18000fea9  test    r11d, r11d
0x18000feac  jnz     loc_180010198
0x18000feb2  test    r14, r14
0x18000feb5  jz      loc_18001010D
0x18000febb  test    r10d, r10d
0x18000febe  jnz     loc_18001010D
0x18000fec4  mov     rcx, gs:60h
0x18000fecd  xor     edx, edx; Flags
0x18000fecf  mov     r8d, 28h ; '('; Size
0x18000fed5  mov     [rsp+68h+arg_0], rdi
0x18000feda  mov     rcx, [rcx+30h]; HeapHandle
0x18000fede  call    cs:__imp_RtlAllocateHeap
0x18000fee5  nop     dword ptr [rax+rax+00h]
0x18000feea  mov     rdi, rax
0x18000feed  test    rax, rax
0x18000fef0  jz      short loc_18000FF49
0x18000fef2  xor     eax, eax
0x18000fef4  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fefb  xorps   xmm0, xmm0
0x18000fefe  movups  xmmword ptr [rdi], xmm0
0x18000ff01  movups  xmmword ptr [rdi+10h], xmm0
0x18000ff05  mov     [rdi+20h], rax
0x18000ff09  mov     eax, [rbx+8]
0x18000ff0c  mov     [rdi+8], eax
0x18000ff0f  mov     dword ptr [rdi], 28h ; '('
0x18000ff15  mov     dword ptr [rdi+4], 4D534B59h
0x18000ff1c  mov     rcx, [rbx+10h]
0x18000ff20  test    rcx, rcx
0x18000ff23  jnz     loc_180010066
0x18000ff29  test    ebp, ebp
0x18000ff2b  jnz     loc_1800101D5
0x18000ff31  mov     rbx, rdi
0x18000ff34  mov     rdi, [rsp+68h+arg_0]
0x18000ff39  xor     eax, eax
0x18000ff3b  mov     [r14], rbx
0x18000ff3e  add     rsp, 48h
0x18000ff42  pop     r14
0x18000ff44  pop     rsi
0x18000ff45  pop     rbp
0x18000ff46  pop     rbx
0x18000ff47  retn
0x18000ff49  mov     ebp, 0C0000017h
0x18000ff4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff55  lea     rbx, WPP_GLOBAL_Control
0x18000ff5c  cmp     rcx, rbx
0x18000ff5f  jz      short loc_18000FF6B
0x18000ff61  test    byte ptr [rcx+1Ch], 1
0x18000ff65  jnz     loc_180010083
0x18000ff6b  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ff72  mov     r9d, 0AC3h
0x18000ff78  lea     rdx, aStatus; "Status"
0x18000ff7f  mov     r8, rsi
0x18000ff82  mov     ecx, ebp
0x18000ff84  call    DebugTraceError
0x18000ff89  mov     rdi, [rsp+68h+arg_0]
0x18000ff8e  mov     eax, ebp
0x18000ff90  add     rsp, 48h
0x18000ff94  pop     r14
0x18000ff96  pop     rsi
0x18000ff97  pop     rbp
0x18000ff98  pop     rbx
0x18000ff99  retn
0x18000ff9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffa2  lea     rbx, WPP_GLOBAL_Control
0x18000ffa9  cmp     rcx, rbx
0x18000ffac  jz      short loc_18000FFB8
0x18000ffae  test    byte ptr [rcx+1Ch], 1
0x18000ffb2  jnz     loc_18001022A
0x18000ffb8  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ffbf  mov     ebp, 0C000000Dh
0x18000ffc4  cmp     rcx, rbx
0x18000ffc7  jz      loc_18001012F
0x18000ffcd  test    byte ptr [rcx+1Ch], 1
0x18000ffd1  jz      loc_18001012F
0x18000ffd7  mov     rcx, [rcx+10h]
0x18000ffdb  lea     r9, aStatus; "Status"
0x18000ffe2  mov     [rsp+68h+var_38], 0AB5h
0x18000ffea  mov     [rsp+68h+var_40], rsi
0x18000ffef  mov     [rsp+68h+var_48], 0C000000Dh
0x18000fff7  call    WPP_SF_sDsd
0x18000fffc  mov     eax, ebp
0x18000fffe  jmp     loc_18000FF3E
0x180010003  mov     rax, [rcx]
0x180010006  mov     ebp, [rax+0Ch]
0x180010009  mov     rax, [rcx+8]
0x18001000d  mov     ecx, [rax+0Ch]
0x180010010  jmp     loc_18000FEA9
0x180010015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001001c  lea     rbx, WPP_GLOBAL_Control
0x180010023  cmp     rcx, rbx
0x180010026  jz      short loc_18000FFB8
0x180010028  test    byte ptr [rcx+1Ch], 1
0x18001002c  jz      short loc_18000FFB8
0x18001002e  mov     rcx, [rcx+10h]
0x180010032  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010039  mov     [rsp+68h+var_38], 1F9h
0x180010041  lea     r9, aStatus; "Status"
0x180010048  mov     [rsp+68h+var_40], rsi
0x18001004d  mov     [rsp+68h+var_48], 0C000000Dh
0x180010055  call    WPP_SF_sDsd
0x18001005a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010061  jmp     loc_18000FFBF
0x180010066  test    ebp, ebp
0x180010068  jz      short loc_180010076
0x18001006a  mov     rax, [rcx]
0x18001006d  cmp     ebp, [rax+0Ch]
0x180010070  jnz     loc_18001013C
0x180010076  or      dword ptr [rdi+20h], 1
0x18001007a  mov     [rdi+10h], rcx
0x18001007e  jmp     loc_18000FF31
0x180010083  mov     rcx, [rcx+10h]
0x180010087  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001008e  mov     [rsp+68h+var_38], 63Eh
0x180010096  lea     r9, aStatus; "Status"
0x18001009d  mov     [rsp+68h+var_40], rsi
0x1800100a2  mov     [rsp+68h+var_48], 0C0000017h
0x1800100aa  call    WPP_SF_sDsd
0x1800100af  jmp     loc_18000FF72
0x1800100b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100bb  lea     rbx, WPP_GLOBAL_Control
0x1800100c2  cmp     rcx, rbx
0x1800100c5  jz      loc_18000FFB8
0x1800100cb  test    byte ptr [rcx+1Ch], 1
0x1800100cf  jz      loc_18000FFB8
0x1800100d5  mov     rcx, [rcx+10h]
0x1800100d9  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800100e0  mov     [rsp+68h+var_38], 1F1h
0x1800100e8  lea     r9, aStatus; "Status"
0x1800100ef  mov     [rsp+68h+var_40], rsi
0x1800100f4  mov     [rsp+68h+var_48], 0C000000Dh
0x1800100fc  call    WPP_SF_sDsd
0x180010101  mov     rcx, cs:WPP_GLOBAL_Control
0x180010108  jmp     loc_18000FFBF
0x18001010d  mov     ebp, 0C000000Dh
0x180010112  mov     rcx, cs:WPP_GLOBAL_Control
0x180010119  lea     rbx, WPP_GLOBAL_Control
0x180010120  cmp     rcx, rbx
0x180010123  jz      short loc_18001012F
0x180010125  test    byte ptr [rcx+1Ch], 1
0x180010129  jnz     loc_1800101F9
0x18001012f  mov     eax, ebp
0x180010131  add     rsp, 48h
0x180010135  pop     r14
0x180010137  pop     rsi
0x180010138  pop     rbp
0x180010139  pop     rbx
0x18001013a  retn
0x18001013c  mov     ebp, 0C000000Dh
0x180010141  mov     rcx, cs:WPP_GLOBAL_Control
0x180010148  lea     rbx, WPP_GLOBAL_Control
0x18001014f  cmp     rcx, rbx
0x180010152  jz      short loc_18001015A
0x180010154  test    byte ptr [rcx+1Ch], 1
0x180010158  jnz     short loc_180010171
0x18001015a  mov     rcx, rdi
0x18001015d  xor     ebx, ebx
0x18001015f  call    MSCryptFree
0x180010164  test    ebp, ebp
0x180010166  jns     loc_18000FF34
0x18001016c  jmp     loc_18000FF72
0x180010171  mov     rcx, [rcx+10h]
0x180010175  lea     r9, aStatus; "Status"
0x18001017c  mov     [rsp+68h+var_38], 658h
0x180010184  mov     [rsp+68h+var_40], rsi
0x180010189  mov     [rsp+68h+var_48], 0C000000Dh
0x180010191  call    WPP_SF_sDsd
0x180010196  jmp     short loc_18001015A
0x180010198  cmp     ecx, r11d
0x18001019b  jz      loc_18000FEB2
0x1800101a1  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800101a8  mov     r9d, 20Eh
0x1800101ae  mov     r8, rsi
0x1800101b1  lea     rdx, aStatus; "Status"
0x1800101b8  mov     ecx, 0C000000Dh
0x1800101bd  call    DebugTraceError
0x1800101c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101c9  lea     rbx, WPP_GLOBAL_Control
0x1800101d0  jmp     loc_18000FFBF
0x1800101d5  mov     r9d, 668h
0x1800101db  lea     rdx, aStatus; "Status"
0x1800101e2  mov     r8, rsi
0x1800101e5  mov     ecx, 0C000000Dh
0x1800101ea  mov     ebp, 0C000000Dh
0x1800101ef  call    DebugTraceError
0x1800101f4  jmp     loc_18001015A
0x1800101f9  mov     rcx, [rcx+10h]
0x1800101fd  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010204  mov     [rsp+68h+var_38], 0ABCh
0x18001020c  lea     r9, aStatus; "Status"
0x180010213  mov     [rsp+68h+var_40], rsi
0x180010218  mov     [rsp+68h+var_48], 0C000000Dh
0x180010220  call    WPP_SF_sDsd
0x180010225  jmp     loc_18001012F
0x18001022a  mov     rcx, [rcx+10h]
0x18001022e  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010235  mov     [rsp+68h+var_38], 1E7h
0x18001023d  lea     r9, aStatus; "Status"
0x180010244  mov     [rsp+68h+var_40], rsi
0x180010249  mov     [rsp+68h+var_48], 0C000000Dh
0x180010251  call    WPP_SF_sDsd
0x180010256  mov     rcx, cs:WPP_GLOBAL_Control
0x18001025d  jmp     loc_18000FFBF
```
