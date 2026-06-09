# ValidateKeyDerivationAlgorithm

- ea: `0x180011640`
- end: `0x18001171c`
- name: `ValidateKeyDerivationAlgorithm`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010ee0`
- `0x18006c380`

## callees

- `0x18000ee60`
- `0x180011640`

## string_xrefs

- `0x1800116a2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall ValidateKeyDerivationAlgorithm(_DWORD *a1, _QWORD *a2, int a3)
{
  unsigned int v3; // ebx

  if ( a1 )
  {
    if ( a1[1] == 1297301836 && *a1 == 20 )
    {
      if ( (unsigned int)(a1[2] - 393217) > 6 )
      {
        v3 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            a3,
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            30);
      }
      else
      {
        *a2 = a1;
        return 0;
      }
    }
    else
    {
      v3 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          17);
    }
  }
  else
  {
    v3 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        7);
  }
  return v3;
}

```

## disassembly

```asm
0x180011640  push    rbx
0x180011642  sub     rsp, 40h
0x180011646  test    rcx, rcx
0x180011649  jz      short loc_180011678
0x18001164b  cmp     dword ptr [rcx+4], 4D53414Ch
0x180011652  jnz     short loc_1800116C4
0x180011654  cmp     dword ptr [rcx], 14h
0x180011657  jnz     short loc_1800116C4
0x180011659  mov     eax, [rcx+8]
0x18001165c  sub     eax, 60001h
0x180011661  cmp     eax, 6
0x180011664  ja      loc_1800116EC
0x18001166a  mov     [rdx], rcx
0x18001166d  xor     ebx, ebx
0x18001166f  mov     eax, ebx
0x180011671  add     rsp, 40h
0x180011675  pop     rbx
0x180011676  retn
0x180011678  mov     ebx, 0C0000008h
0x18001167d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011684  lea     rax, WPP_GLOBAL_Control
0x18001168b  cmp     rcx, rax
0x18001168e  jz      short loc_18001166F
0x180011690  test    byte ptr [rcx+1Ch], 1
0x180011694  jz      short loc_18001166F
0x180011696  mov     [rsp+48h+var_18], 107h
0x18001169e  mov     rcx, [rcx+10h]
0x1800116a2  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800116a9  mov     [rsp+48h+var_20], rax
0x1800116ae  lea     r9, aStatus; "Status"
0x1800116b5  mov     [rsp+48h+var_28], 0C0000008h
0x1800116bd  call    WPP_SF_sDsd
0x1800116c2  jmp     short loc_18001166F
0x1800116c4  mov     ebx, 0C0000008h
0x1800116c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116d0  lea     rax, WPP_GLOBAL_Control
0x1800116d7  cmp     rcx, rax
0x1800116da  jz      short loc_18001166F
0x1800116dc  test    byte ptr [rcx+1Ch], 1
0x1800116e0  jz      short loc_18001166F
0x1800116e2  mov     [rsp+48h+var_18], 111h
0x1800116ea  jmp     short loc_18001169E
0x1800116ec  mov     ebx, 0C0000008h
0x1800116f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116f8  lea     rax, WPP_GLOBAL_Control
0x1800116ff  cmp     rcx, rax
0x180011702  jz      loc_18001166F
0x180011708  test    byte ptr [rcx+1Ch], 1
0x18001170c  jz      loc_18001166F
0x180011712  mov     [rsp+48h+var_18], 11Eh
0x18001171a  jmp     short loc_18001169E
```
