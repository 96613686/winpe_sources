# I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)

- ea: `0x18002140c`
- end: `0x18002154e`
- name: `?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z`
- size: `322`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, struct _CARD_CACHE_FILE_FORMAT *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180021a4c`
- `0x180021b48`
- `0x180021bc8`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x18001f3a4`
- `0x18002140c`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall I_CspReadCardCacheFile(struct _CARD_STATE *a1, struct _CARD_CACHE_FILE_FORMAT *a2)
{
  __int64 v2; // rax
  unsigned int v5; // edi
  int v6; // r9d
  int v7; // ecx
  __int64 v8; // rcx
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  v10 = 0;
  if ( v2 )
  {
    v5 = 0;
    if ( !*((_DWORD *)a1 + 155) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, _QWORD, char *, __int128 *))(v2 + 248))(
             v2,
             0,
             "cardcf",
             0,
             (char *)&v10 + 8,
             &v10);
      if ( v5 )
        goto LABEL_14;
      v7 = v10;
      if ( (unsigned int)v10 < 6 )
      {
        v5 = 24;
        goto LABEL_14;
      }
      if ( *((_QWORD *)a1 + 76) )
      {
        CspFreeH(*((_QWORD *)a1 + 76));
        v7 = v10;
      }
      *((_QWORD *)a1 + 76) = *((_QWORD *)&v10 + 1);
      *((_DWORD *)a1 + 154) = v7;
      *((_DWORD *)a1 + 155) = 1;
      *((_QWORD *)&v10 + 1) = 0;
    }
    v8 = *((_QWORD *)a1 + 76);
    *(_DWORD *)a2 = *(_DWORD *)v8;
    *((_WORD *)a2 + 2) = *(_WORD *)(v8 + 4);
  }
  else
  {
    v5 = 87;
    WppTraceIndent((__int64)a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
  }
LABEL_14:
  if ( *((_QWORD *)&v10 + 1) )
    CspFreeH(*((_QWORD *)&v10 + 1));
  return v5;
}

```

## disassembly

```asm
0x18002140c  mov     [rsp+arg_0], rbx
0x180021411  mov     [rsp+arg_8], rsi
0x180021416  push    rdi
0x180021417  sub     rsp, 50h
0x18002141b  mov     rax, [rcx+8]
0x18002141f  xorps   xmm0, xmm0
0x180021422  mov     rsi, rdx
0x180021425  mov     rbx, rcx
0x180021428  movups  [rsp+58h+var_18], xmm0
0x18002142d  test    rax, rax
0x180021430  jnz     short loc_18002148C
0x180021432  lea     edx, [rax+2]
0x180021435  lea     edi, [rax+57h]
0x180021438  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002143d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021444  lea     rax, WPP_GLOBAL_Control
0x18002144b  cmp     rcx, rax
0x18002144e  jz      loc_18002152D
0x180021454  test    byte ptr [rcx+1Ch], 1
0x180021458  jz      loc_18002152D
0x18002145e  cmp     byte ptr [rcx+19h], 2
0x180021462  jb      loc_18002152D
0x180021468  mov     rcx, [rcx+10h]
0x18002146c  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x180021473  lea     edx, [rdi-4Ah]
0x180021476  mov     [rsp+58h+var_38], rax
0x18002147b  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021482  call    WPP_SF_ss
0x180021487  jmp     loc_18002152D
0x18002148c  xor     edi, edi
0x18002148e  cmp     [rcx+26Ch], edi
0x180021494  jnz     loc_18002151A
0x18002149a  lea     rcx, [rsp+58h+var_18]
0x18002149f  xor     r9d, r9d
0x1800214a2  mov     [rsp+58h+var_30], rcx
0x1800214a7  lea     r8, aCardcf; "cardcf"
0x1800214ae  lea     rcx, [rsp+58h+var_18+8]
0x1800214b3  xor     edx, edx
0x1800214b5  mov     [rsp+58h+var_38], rcx
0x1800214ba  mov     rcx, rax
0x1800214bd  mov     rax, [rax+0F8h]
0x1800214c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214c9  mov     edi, eax
0x1800214cb  test    eax, eax
0x1800214cd  jnz     short loc_18002152D
0x1800214cf  mov     ecx, dword ptr [rsp+58h+var_18]
0x1800214d3  cmp     ecx, 6
0x1800214d6  jnb     short loc_1800214DD
0x1800214d8  lea     edi, [rax+18h]
0x1800214db  jmp     short loc_18002152D
0x1800214dd  mov     rax, [rbx+260h]
0x1800214e4  test    rax, rax
0x1800214e7  jz      short loc_1800214F5
0x1800214e9  mov     rcx, rax
0x1800214ec  call    CspFreeH
0x1800214f1  mov     ecx, dword ptr [rsp+58h+var_18]
0x1800214f5  mov     rax, qword ptr [rsp+58h+var_18+8]
0x1800214fa  mov     [rbx+260h], rax
0x180021501  mov     [rbx+268h], ecx
0x180021507  mov     dword ptr [rbx+26Ch], 1
0x180021511  mov     qword ptr [rsp+58h+var_18+8], 0
0x18002151a  mov     rcx, [rbx+260h]
0x180021521  mov     eax, [rcx]
0x180021523  mov     [rsi], eax
0x180021525  movzx   eax, word ptr [rcx+4]
0x180021529  mov     [rsi+4], ax
0x18002152d  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x180021532  test    rcx, rcx
0x180021535  jz      short loc_18002153C
0x180021537  call    CspFreeH
0x18002153c  mov     rbx, [rsp+58h+arg_0]
0x180021541  mov     eax, edi
0x180021543  mov     rsi, [rsp+58h+arg_8]
0x180021548  add     rsp, 50h
0x18002154c  pop     rdi
0x18002154d  retn
```
