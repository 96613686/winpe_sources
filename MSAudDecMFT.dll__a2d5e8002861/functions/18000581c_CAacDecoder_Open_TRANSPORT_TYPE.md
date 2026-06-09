# CAacDecoder_Open(TRANSPORT_TYPE)

- ea: `0x18000581c`
- end: `0x180005a36`
- name: `?CAacDecoder_Open@@YAPEAUAAC_DECODER_INSTANCE@@W4TRANSPORT_TYPE@@@Z`
- size: `538`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005288`

## callees

- `0x18000581c`
- `0x180005a3c`
- `0x180005b44`
- `0x180006914`
- `0x18002f3c0`
- `0x180042960`
- `0x18004dd14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000582f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800059ab`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000582f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800059ab`

## pseudocode

```c
char *CAacDecoder_Open()
{
  char *v0; // rax
  char *v1; // rdi
  bool v2; // sf
  bool v3; // of
  struct CDrcInfo *v4; // rax
  unsigned int Delay; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax

  v0 = (char *)calloc(1u, 0x1230u);
  v1 = v0;
  if ( v0 )
  {
    v3 = __OFSUB__(_isa_available, 5);
    v2 = _isa_available - 5 < 0;
    v0[2600] = 0;
    *((_DWORD *)v0 + 663) = 0;
    v0[2602] = 0;
    v0[2604] = 0;
    v0[2606] = 0;
    v0[2657] = 0;
    *((_WORD *)v0 + 1330) = 0;
    v0[2663] = 0;
    v0[2665] = 0;
    v0[2667] = 0;
    v0[2669] = 0;
    *((_QWORD *)v0 + 172) = v0 + 852;
    *((_QWORD *)v0 + 171) = v0 + 820;
    *((_QWORD *)v0 + 174) = v0 + 316;
    *((_DWORD *)v0 + 346) = 0;
    *((_WORD *)v0 + 1282) = 257;
    *((_QWORD *)v0 + 547) = 0;
    *((_DWORD *)v0 + 1096) = 0;
    *(_OWORD *)(v0 + 4388) = 0;
    CDK_isAVX2_FMAavailable = v2 == v3;
    *(_OWORD *)(v0 + 4404) = 0;
    *((_DWORD *)v0 + 1105) = 0;
    *((_DWORD *)v0 + 350) = 0;
    *((_DWORD *)v0 + 351) = -1;
    *((_DWORD *)v0 + 352) = -1;
    *((_DWORD *)v0 + 353) = -1;
    *((_QWORD *)v0 + 177) = 0;
    *((_DWORD *)v0 + 357) = -1;
    *((_QWORD *)v0 + 179) = 0;
    *((_DWORD *)v0 + 360) = 0;
    v0[1444] = -1;
    *((_DWORD *)v0 + 341) = 0;
    *((_QWORD *)v0 + 169) = 0;
    v0[1468] = -1;
    v0[1469] = -1;
    v0[1470] = -1;
    v0[1471] = -1;
    *((_DWORD *)v0 + 368) = -1;
    v0[1476] = 0;
    memset_0(v0 + 881, 0, 0x1D1u);
    v1[883] = 15;
    CConcealment_InitCommonData((struct CConcealParams_fl *)(v1 + 2128));
    *((_DWORD *)v1 + 601) = -1;
    v4 = (struct CDrcInfo *)calloc(1u, 0x70u);
    *((_QWORD *)v1 + 542) = v4;
    if ( v4 )
    {
      aacDecoder_drcInit(v4);
      Delay = CConcealment_GetDelay((struct CConcealParams_fl *)(v1 + 2128));
      if ( Delay <= 1 )
      {
        v7 = *((_QWORD *)v1 + 542);
        if ( v7 )
          *(_BYTE *)(v7 + 28) = Delay;
      }
      v8 = CDKaalloc_L(0x20000);
      *((_QWORD *)v1 + 202) = v8;
      if ( v8 )
      {
        v9 = CDKaalloc_L(0x40000);
        *((_QWORD *)v1 + 203) = v9;
        *((_DWORD *)v1 + 408) = 262208;
        if ( v9 )
          return v1;
      }
    }
  }
  CAacDecoder_Close((struct AAC_DECODER_INSTANCE *)v1);
  return 0;
}

```

## disassembly

```asm
0x18000581c  push    rbx
0x18000581e  push    rbp
0x18000581f  push    rsi
0x180005820  push    rdi
0x180005821  sub     rsp, 28h
0x180005825  mov     edx, 1230h; Size
0x18000582a  mov     ecx, 1; Count
0x18000582f  call    cs:__imp_calloc
0x180005836  nop     dword ptr [rax+rax+00h]
0x18000583b  xor     ebp, ebp
0x18000583d  mov     rdi, rax
0x180005840  test    rax, rax
0x180005843  jz      loc_1800059C3
0x180005849  cmp     cs:__isa_available, 5
0x180005850  lea     rbx, [rdi+371h]
0x180005857  mov     [rax+0A28h], bpl
0x18000585e  mov     ecx, ebp
0x180005860  mov     [rax+0A5Ch], ebp
0x180005866  setnl   cl
0x180005869  mov     [rax+0A2Ah], bpl
0x180005870  or      esi, 0FFFFFFFFh
0x180005873  mov     [rax+0A2Ch], bpl
0x18000587a  xorps   xmm0, xmm0
0x18000587d  mov     [rax+0A2Eh], bpl
0x180005884  xor     edx, edx; Val
0x180005886  mov     [rax+0A61h], bpl
0x18000588d  mov     r8d, 1D1h; Size
0x180005893  mov     [rax+0A64h], bp
0x18000589a  mov     [rax+0A67h], bpl
0x1800058a1  mov     [rax+0A69h], bpl
0x1800058a8  mov     [rax+0A6Bh], bpl
0x1800058af  mov     [rax+0A6Dh], bpl
0x1800058b6  add     rax, 354h
0x1800058bc  mov     [rdi+560h], rax
0x1800058c3  lea     rax, [rdi+334h]
0x1800058ca  mov     [rdi+558h], rax
0x1800058d1  lea     rax, [rdi+13Ch]
0x1800058d8  mov     [rdi+570h], rax
0x1800058df  mov     [rdi+568h], ebp
0x1800058e5  mov     word ptr [rdi+0A04h], 101h
0x1800058ee  mov     [rdi+1118h], rbp
0x1800058f5  mov     [rdi+1120h], ebp
0x1800058fb  movups  xmmword ptr [rdi+1124h], xmm0
0x180005902  mov     cs:?CDK_isAVX2_FMAavailable@@3HA, ecx; int CDK_isAVX2_FMAavailable
0x180005908  mov     rcx, rbx; void *
0x18000590b  movups  xmmword ptr [rdi+1134h], xmm0
0x180005912  mov     [rdi+1144h], ebp
0x180005918  mov     [rdi+578h], ebp
0x18000591e  mov     [rdi+57Ch], esi
0x180005924  mov     [rdi+580h], esi
0x18000592a  mov     [rdi+584h], esi
0x180005930  mov     [rdi+588h], rbp
0x180005937  mov     [rdi+594h], esi
0x18000593d  mov     [rdi+598h], rbp
0x180005944  mov     [rdi+5A0h], ebp
0x18000594a  mov     [rdi+5A4h], sil
0x180005951  mov     [rdi+554h], ebp
0x180005957  mov     [rdi+548h], rbp
0x18000595e  mov     [rdi+5BCh], sil
0x180005965  mov     [rdi+5BDh], sil
0x18000596c  mov     [rdi+5BEh], sil
0x180005973  mov     [rdi+5BFh], sil
0x18000597a  mov     [rdi+5C0h], esi
0x180005980  mov     [rdi+5C4h], bpl
0x180005987  call    memset_0
0x18000598c  mov     byte ptr [rbx+2], 0Fh
0x180005990  lea     rbx, [rdi+850h]
0x180005997  mov     rcx, rbx; struct CConcealParams_fl *
0x18000599a  call    ?CConcealment_InitCommonData@@YAXPEAUCConcealParams_fl@@@Z; CConcealment_InitCommonData(CConcealParams_fl *)
0x18000599f  lea     edx, [rbp+70h]; Size
0x1800059a2  mov     [rdi+964h], esi
0x1800059a8  lea     ecx, [rbp+1]; Count
0x1800059ab  call    cs:__imp_calloc
0x1800059b2  nop     dword ptr [rax+rax+00h]
0x1800059b7  mov     [rdi+10F0h], rax
0x1800059be  test    rax, rax
0x1800059c1  jnz     short loc_1800059D7
0x1800059c3  mov     rcx, rdi; Block
0x1800059c6  call    ?CAacDecoder_Close@@YAXPEAUAAC_DECODER_INSTANCE@@@Z; CAacDecoder_Close(AAC_DECODER_INSTANCE *)
0x1800059cb  xor     eax, eax
0x1800059cd  add     rsp, 28h
0x1800059d1  pop     rdi
0x1800059d2  pop     rsi
0x1800059d3  pop     rbp
0x1800059d4  pop     rbx
0x1800059d5  retn
0x1800059d7  mov     rcx, rax; struct CDrcInfo *
0x1800059da  call    ?aacDecoder_drcInit@@YAXPEAUCDrcInfo@@@Z; aacDecoder_drcInit(CDrcInfo *)
0x1800059df  mov     rcx, rbx; struct CConcealParams_fl *
0x1800059e2  call    ?CConcealment_GetDelay@@YAIPEAUCConcealParams_fl@@@Z; CConcealment_GetDelay(CConcealParams_fl *)
0x1800059e7  cmp     eax, 1
0x1800059ea  ja      short loc_1800059FB
0x1800059ec  mov     rcx, [rdi+10F0h]
0x1800059f3  test    rcx, rcx
0x1800059f6  jz      short loc_1800059FB
0x1800059f8  mov     [rcx+1Ch], al
0x1800059fb  mov     ecx, 20000h
0x180005a00  call    CDKaalloc_L
0x180005a05  mov     [rdi+650h], rax
0x180005a0c  test    rax, rax
0x180005a0f  jz      short loc_1800059C3
0x180005a11  mov     ecx, 40000h
0x180005a16  call    CDKaalloc_L
0x180005a1b  mov     [rdi+658h], rax
0x180005a22  mov     dword ptr [rdi+660h], 40040h
0x180005a2c  test    rax, rax
0x180005a2f  jz      short loc_1800059C3
0x180005a31  mov     rax, rdi
0x180005a34  jmp     short loc_1800059CD
```
