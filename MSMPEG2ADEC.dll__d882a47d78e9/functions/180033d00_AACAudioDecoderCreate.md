# AACAudioDecoderCreate

- ea: `0x180033d00`
- end: `0x180034024`
- name: `AACAudioDecoderCreate`
- size: `804`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a6b0`

## callees

- `0x1800021a8`
- `0x180033d00`
- `0x180039290`
- `0x180073510`
- `0x180073bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033d32`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033d93`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033db6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033f33`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033d32`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033d93`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033db6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180033f33`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f1d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033ff1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f1d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033fe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033ff1`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180033d6d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180033d6d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180033f69`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180033f69`

## pseudocode

```c
__int64 __fastcall AACAudioDecoderCreate(int *a1, char **a2)
{
  char *v4; // rbx
  __int64 result; // rax
  void *v6; // rax
  void *v7; // rax
  void *v8; // rax
  char *v9; // rax
  int v10; // r9d
  unsigned int v11; // ecx
  int v12; // r10d
  int v13; // edx
  unsigned int v14; // edi
  void **v15; // rdi
  void *v16; // rax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx

  if ( a1 && a2 )
  {
    *a2 = 0;
    v4 = (char *)calloc(1u, 0x268u);
    if ( v4 )
    {
      *(_QWORD *)v4 = *((_QWORD *)a1 + 2);
      v6 = _aligned_malloc(0x10000u, 0x10u);
      *((_QWORD *)v4 + 53) = v6;
      if ( !v6 )
        goto LABEL_19;
      v7 = calloc(1u, 0x30u);
      *((_QWORD *)v4 + 4) = v7;
      if ( !v7 )
        goto LABEL_19;
      v8 = calloc(1u, 0x10E8u);
      *((_QWORD *)v4 + 6) = v8;
      if ( !v8 )
        goto LABEL_19;
      *((_DWORD *)v4 + 152) = a1[2];
      memset_0(v4 + 56, 0, 0x16Cu);
      *((_DWORD *)v4 + 15) = 1;
      v9 = CAacDecoderOpen(*((_QWORD *)v4 + 4), *((_QWORD *)v4 + 6), *((_QWORD *)v4 + 53));
      *((_QWORD *)v4 + 1) = v9;
      if ( !v9 )
        goto LABEL_19;
      v10 = a1[2];
      v11 = 0;
      v12 = a1[1];
      v13 = *a1;
      *(_DWORD *)(*((_QWORD *)v9 + 4) + 4LL) = *a1;
      while ( v13 != LODWORD(SamplingRateInfoTable[4 * v11]) )
      {
        if ( (int)++v11 >= 12 )
        {
          if ( v11 == 12 )
          {
            v14 = -1;
            goto LABEL_20;
          }
          break;
        }
      }
      v15 = (void **)(v4 + 24);
      **((_BYTE **)v9 + 4) = v11;
      *(_DWORD *)(*((_QWORD *)v9 + 4) + 20LL) = v12;
      *((_DWORD *)v9 + 153) = v10;
      *((_QWORD *)v4 + 56) = GenericFloatInterleave;
      *((_QWORD *)v4 + 57) = GenericFloatInterleave;
      *((_QWORD *)v4 + 59) = GenericFloatInterleave;
      *((_QWORD *)v4 + 60) = GenericFloatInterleave;
      *((_QWORD *)v4 + 61) = GenericFloatInterleave;
      *((_QWORD *)v4 + 63) = GenericFloatInterleave;
      *((_QWORD *)v4 + 64) = GenericFloatInterleave;
      *((_QWORD *)v4 + 65) = GenericShortInterleave;
      *((_QWORD *)v4 + 66) = GenericShortInterleave;
      *((_QWORD *)v4 + 68) = GenericShortInterleave;
      *((_QWORD *)v4 + 69) = GenericShortInterleave;
      *((_QWORD *)v4 + 70) = GenericShortInterleave;
      *((_QWORD *)v4 + 72) = GenericShortInterleave;
      *((_QWORD *)v4 + 73) = GenericShortInterleave;
      *((_QWORD *)v4 + 58) = pcm_output_2_float_SSE;
      *((_QWORD *)v4 + 62) = pcm_output_6_float_SSE;
      *((_QWORD *)v4 + 67) = pcm_output_2_pcm_SSE2;
      *((_QWORD *)v4 + 71) = pcm_output_6_pcm_SSE2;
      if ( v4 == (char *)-24LL )
        goto LABEL_19;
      if ( *v15 )
        free(*v15);
      v16 = calloc(1u, 0x90u);
      if ( v16 )
      {
        *v15 = v16;
        result = 0;
        *a2 = v4;
      }
      else
      {
LABEL_19:
        v14 = -2147024882;
LABEL_20:
        v17 = (void *)*((_QWORD *)v4 + 53);
        if ( v17 )
        {
          _aligned_free(v17);
          *((_QWORD *)v4 + 53) = 0;
        }
        v18 = (void *)*((_QWORD *)v4 + 5);
        if ( v18 )
        {
          free(v18);
          *((_QWORD *)v4 + 5) = 0;
        }
        v19 = (void *)*((_QWORD *)v4 + 4);
        if ( v19 )
        {
          free(v19);
          *((_QWORD *)v4 + 4) = 0;
        }
        v20 = (void *)*((_QWORD *)v4 + 6);
        if ( v20 )
        {
          free(v20);
          *((_QWORD *)v4 + 6) = 0;
        }
        CAacDecoderClose(v4 + 8);
        closeSBR(v4 + 16);
        v21 = (void *)*((_QWORD *)v4 + 3);
        if ( v21 )
          free(v21);
        free(v4);
        result = v14;
        *a2 = 0;
      }
    }
    else
    {
      *a2 = 0;
      return 2147942414LL;
    }
  }
  else
  {
    *a2 = 0;
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180033d00  push    rbx
0x180033d02  push    rbp
0x180033d03  push    rsi
0x180033d04  push    rdi
0x180033d05  push    r14
0x180033d07  sub     rsp, 20h
0x180033d0b  xor     ebp, ebp
0x180033d0d  mov     r14, rdx
0x180033d10  mov     rsi, rcx
0x180033d13  test    rcx, rcx
0x180033d16  jz      loc_18003400E
0x180033d1c  test    rdx, rdx
0x180033d1f  jz      loc_18003400E
0x180033d25  mov     [rdx], rbp
0x180033d28  mov     ecx, 1; Count
0x180033d2d  mov     edx, 268h; Size
0x180033d32  call    cs:__imp_calloc
0x180033d39  nop     dword ptr [rax+rax+00h]
0x180033d3e  mov     rbx, rax
0x180033d41  test    rax, rax
0x180033d44  jnz     short loc_180033D5C
0x180033d46  mov     edi, 8007000Eh
0x180033d4b  mov     [r14], rbp
0x180033d4e  mov     eax, edi
0x180033d50  add     rsp, 20h
0x180033d54  pop     r14
0x180033d56  pop     rdi
0x180033d57  pop     rsi
0x180033d58  pop     rbp
0x180033d59  pop     rbx
0x180033d5a  retn
0x180033d5c  mov     rax, [rsi+10h]
0x180033d60  mov     edx, 10h; Alignment
0x180033d65  mov     ecx, 10000h; Size
0x180033d6a  mov     [rbx], rax
0x180033d6d  call    cs:__imp__aligned_malloc
0x180033d74  nop     dword ptr [rax+rax+00h]
0x180033d79  mov     [rbx+1A8h], rax
0x180033d80  test    rax, rax
0x180033d83  jz      loc_180033F58
0x180033d89  mov     edx, 30h ; '0'; Size
0x180033d8e  mov     ecx, 1; Count
0x180033d93  call    cs:__imp_calloc
0x180033d9a  nop     dword ptr [rax+rax+00h]
0x180033d9f  mov     [rbx+20h], rax
0x180033da3  test    rax, rax
0x180033da6  jz      loc_180033F58
0x180033dac  mov     edx, 10E8h; Size
0x180033db1  mov     ecx, 1; Count
0x180033db6  call    cs:__imp_calloc
0x180033dbd  nop     dword ptr [rax+rax+00h]
0x180033dc2  mov     [rbx+30h], rax
0x180033dc6  test    rax, rax
0x180033dc9  jz      loc_180033F58
0x180033dcf  mov     eax, [rsi+8]
0x180033dd2  lea     rcx, [rbx+38h]; void *
0x180033dd6  xor     edx, edx; Val
0x180033dd8  mov     [rbx+260h], eax
0x180033dde  mov     r8d, 16Ch; Size
0x180033de4  call    memset_0
0x180033de9  mov     dword ptr [rbx+3Ch], 1
0x180033df0  mov     r8, [rbx+1A8h]
0x180033df7  mov     rdx, [rbx+30h]
0x180033dfb  mov     rcx, [rbx+20h]
0x180033dff  call    CAacDecoderOpen
0x180033e04  mov     [rbx+8], rax
0x180033e08  mov     r8, rax
0x180033e0b  test    rax, rax
0x180033e0e  jz      loc_180033F58
0x180033e14  mov     rax, [rax+20h]
0x180033e18  lea     r11, SamplingRateInfoTable
0x180033e1f  mov     r9d, [rsi+8]
0x180033e23  mov     ecx, ebp
0x180033e25  mov     r10d, [rsi+4]
0x180033e29  mov     edx, [rsi]
0x180033e2b  mov     [rax+4], edx
0x180033e2e  xchg    ax, ax
0x180033e30  mov     eax, ecx
0x180033e32  shl     rax, 5
0x180033e36  cmp     edx, [rax+r11]
0x180033e3a  jz      short loc_180033E4F
0x180033e3c  inc     ecx
0x180033e3e  cmp     ecx, 0Ch
0x180033e41  jl      short loc_180033E30
0x180033e43  jnz     short loc_180033E4F
0x180033e45  mov     edi, 0FFFFFFFFh
0x180033e4a  jmp     loc_180033F5D
0x180033e4f  mov     rax, [r8+20h]
0x180033e53  lea     rdi, [rbx+18h]
0x180033e57  mov     [rax], cl
0x180033e59  mov     rax, [r8+20h]
0x180033e5d  mov     [rax+14h], r10d
0x180033e61  lea     rax, GenericFloatInterleave
0x180033e68  mov     [r8+264h], r9d
0x180033e6f  mov     [rbx+1C0h], rax
0x180033e76  mov     [rbx+1C8h], rax
0x180033e7d  mov     [rbx+1D8h], rax
0x180033e84  mov     [rbx+1E0h], rax
0x180033e8b  mov     [rbx+1E8h], rax
0x180033e92  mov     [rbx+1F8h], rax
0x180033e99  mov     [rbx+200h], rax
0x180033ea0  lea     rax, GenericShortInterleave
0x180033ea7  mov     [rbx+208h], rax
0x180033eae  mov     [rbx+210h], rax
0x180033eb5  mov     [rbx+220h], rax
0x180033ebc  mov     [rbx+228h], rax
0x180033ec3  mov     [rbx+230h], rax
0x180033eca  mov     [rbx+240h], rax
0x180033ed1  mov     [rbx+248h], rax
0x180033ed8  lea     rax, pcm_output_2_float_SSE
0x180033edf  mov     [rbx+1D0h], rax
0x180033ee6  lea     rax, pcm_output_6_float_SSE
0x180033eed  mov     [rbx+1F0h], rax
0x180033ef4  lea     rax, pcm_output_2_pcm_SSE2
0x180033efb  mov     [rbx+218h], rax
0x180033f02  lea     rax, pcm_output_6_pcm_SSE2
0x180033f09  mov     [rbx+238h], rax
0x180033f10  test    rdi, rdi
0x180033f13  jz      short loc_180033F58
0x180033f15  mov     rcx, [rdi]; Block
0x180033f18  test    rcx, rcx
0x180033f1b  jz      short loc_180033F29
0x180033f1d  call    cs:__imp_free
0x180033f24  nop     dword ptr [rax+rax+00h]
0x180033f29  mov     edx, 90h; Size
0x180033f2e  mov     ecx, 1; Count
0x180033f33  call    cs:__imp_calloc
0x180033f3a  nop     dword ptr [rax+rax+00h]
0x180033f3f  test    rax, rax
0x180033f42  jz      short loc_180033F58
0x180033f44  mov     [rdi], rax
0x180033f47  mov     eax, ebp
0x180033f49  mov     [r14], rbx
0x180033f4c  add     rsp, 20h
0x180033f50  pop     r14
0x180033f52  pop     rdi
0x180033f53  pop     rsi
0x180033f54  pop     rbp
0x180033f55  pop     rbx
0x180033f56  retn
0x180033f58  mov     edi, 8007000Eh
0x180033f5d  mov     rcx, [rbx+1A8h]; Block
0x180033f64  test    rcx, rcx
0x180033f67  jz      short loc_180033F7C
0x180033f69  call    cs:__imp__aligned_free
0x180033f70  nop     dword ptr [rax+rax+00h]
0x180033f75  mov     [rbx+1A8h], rbp
0x180033f7c  mov     rcx, [rbx+28h]; Block
0x180033f80  test    rcx, rcx
0x180033f83  jz      short loc_180033F95
0x180033f85  call    cs:__imp_free
0x180033f8c  nop     dword ptr [rax+rax+00h]
0x180033f91  mov     [rbx+28h], rbp
0x180033f95  mov     rcx, [rbx+20h]; Block
0x180033f99  test    rcx, rcx
0x180033f9c  jz      short loc_180033FAE
0x180033f9e  call    cs:__imp_free
0x180033fa5  nop     dword ptr [rax+rax+00h]
0x180033faa  mov     [rbx+20h], rbp
0x180033fae  mov     rcx, [rbx+30h]; Block
0x180033fb2  test    rcx, rcx
0x180033fb5  jz      short loc_180033FC7
0x180033fb7  call    cs:__imp_free
0x180033fbe  nop     dword ptr [rax+rax+00h]
0x180033fc3  mov     [rbx+30h], rbp
0x180033fc7  lea     rcx, [rbx+8]
0x180033fcb  call    CAacDecoderClose
0x180033fd0  lea     rcx, [rbx+10h]
0x180033fd4  call    closeSBR
0x180033fd9  mov     rcx, [rbx+18h]; Block
0x180033fdd  test    rcx, rcx
0x180033fe0  jz      short loc_180033FEE
0x180033fe2  call    cs:__imp_free
0x180033fe9  nop     dword ptr [rax+rax+00h]
0x180033fee  mov     rcx, rbx; Block
0x180033ff1  call    cs:__imp_free
0x180033ff8  nop     dword ptr [rax+rax+00h]
0x180033ffd  mov     eax, edi
0x180033fff  mov     [r14], rbp
0x180034002  add     rsp, 20h
0x180034006  pop     r14
0x180034008  pop     rdi
0x180034009  pop     rsi
0x18003400a  pop     rbp
0x18003400b  pop     rbx
0x18003400c  retn
0x18003400e  mov     edi, 80070057h
0x180034013  mov     [r14], rbp
0x180034016  mov     eax, edi
0x180034018  add     rsp, 20h
0x18003401c  pop     r14
0x18003401e  pop     rdi
0x18003401f  pop     rsi
0x180034020  pop     rbp
0x180034021  pop     rbx
0x180034022  retn
```
