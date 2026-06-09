# CLatmDemux_ReadAudioMuxElement

- ea: `0x1800789bc`
- end: `0x180078b5a`
- name: `CLatmDemux_ReadAudioMuxElement`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180078914`

## callees

- `0x1800110c0`
- `0x1800789bc`
- `0x180078b60`
- `0x180078c50`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall CLatmDemux_ReadAudioMuxElement(
        __int128 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        _DWORD *a6)
{
  int v6; // ebp
  char v10; // al
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int128 v13; // xmm8
  __int64 result; // rax
  __int128 v15; // xmm6
  char v16; // r13
  char v17; // r12
  __int128 v18; // xmm7
  __int128 v19; // xmm8

  v6 = 0;
  if ( (_DWORD)a3 )
  {
    v10 = CDKreadBits(a1, 1, a3);
    *(_BYTE *)(a2 + 28) = v10;
    if ( !v10 )
    {
      if ( !*(_BYTE *)(a2 + 39) )
      {
        v11 = *a1;
        v12 = a1[1];
        v13 = a1[2];
        *(_BYTE *)(a2 + 40) = 0;
        result = CLatmDemux_ReadStreamMuxConfig(a1, a2, a4, (__int64)a5, a6, 1, 0);
        if ( (_DWORD)result )
          goto LABEL_28;
        if ( a5[31] && *(_BYTE *)(a2 + 40) )
        {
          *(_WORD *)(a2 + 39) = 0;
          goto LABEL_21;
        }
        *a1 = v11;
        a1[1] = v12;
        a1[2] = v13;
        *(_BYTE *)(a2 + 39) = 1;
      }
      v15 = *a1;
      v16 = 0;
      v17 = 1;
      v18 = a1[1];
      v19 = a1[2];
      while ( v6 < 2 )
      {
        if ( v6 == 1 )
        {
          *a1 = v15;
          v17 = 2;
          a1[1] = v18;
          a1[2] = v19;
        }
        result = CLatmDemux_ReadStreamMuxConfig(a1, a2, a4, (__int64)a5, a6, v17, v16);
        if ( (_DWORD)result )
          goto LABEL_28;
        if ( !v6 && (a5[1235] || a5[1236] || a5[1237]) )
        {
          v16 = 1;
          if ( (*(unsigned int (__fastcall **)(_QWORD, _BYTE *))(a4 + 32))(*(_QWORD *)(a4 + 40), a5) )
          {
            result = 1025;
            goto LABEL_28;
          }
        }
        ++v6;
      }
    }
  }
LABEL_21:
  if ( *a6 )
  {
    if ( *(_BYTE *)(a2 + 30) )
    {
      result = 1026;
    }
    else
    {
      result = CLatmDemux_ReadPayloadLengthInfo(a1, a2);
      if ( !(_DWORD)result )
        return result;
    }
    *a6 = 0;
  }
  else
  {
    result = 258;
  }
LABEL_28:
  *(_BYTE *)(a2 + 39) = 1;
  return result;
}

```

## disassembly

```asm
0x1800789bc  push    rbx
0x1800789be  push    rbp
0x1800789bf  push    rsi
0x1800789c0  push    rdi
0x1800789c1  push    r12
0x1800789c3  push    r13
0x1800789c5  push    r14
0x1800789c7  push    r15
0x1800789c9  sub     rsp, 78h
0x1800789cd  mov     r14, [rsp+0B8h+arg_28]
0x1800789d5  xor     ebp, ebp
0x1800789d7  movaps  [rsp+0B8h+var_58], xmm6
0x1800789dc  mov     r15, r9
0x1800789df  movaps  [rsp+0B8h+var_68], xmm7
0x1800789e4  mov     rbx, rdx
0x1800789e7  movaps  [rsp+0B8h+var_78], xmm8
0x1800789ed  mov     rdi, rcx
0x1800789f0  test    r8d, r8d
0x1800789f3  jz      loc_180078B09
0x1800789f9  lea     edx, [rbp+1]
0x1800789fc  call    CDKreadBits
0x180078a01  mov     [rbx+1Ch], al
0x180078a04  test    al, al
0x180078a06  jnz     loc_180078B09
0x180078a0c  mov     rsi, [rsp+0B8h+arg_20]
0x180078a14  cmp     [rbx+27h], bpl
0x180078a18  jnz     short loc_180078A77
0x180078a1a  movups  xmm6, xmmword ptr [rdi]
0x180078a1d  mov     [rsp+0B8h+var_88], bpl
0x180078a22  mov     r9, rsi
0x180078a25  movups  xmm7, xmmword ptr [rdi+10h]
0x180078a29  mov     [rsp+0B8h+var_90], 1
0x180078a2e  mov     r8, r15
0x180078a31  movups  xmm8, xmmword ptr [rdi+20h]
0x180078a36  mov     rdx, rbx
0x180078a39  mov     [rsp+0B8h+var_98], r14
0x180078a3e  mov     rcx, rdi
0x180078a41  mov     [rbx+28h], bpl
0x180078a45  call    ?CLatmDemux_ReadStreamMuxConfig@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@PEAUCSTpCallBacks@@PEAUCSAudioSpecificConfig@@PEAHEE@Z; CLatmDemux_ReadStreamMuxConfig(CDK_BITSTREAM *,CLatmDemux *,CSTpCallBacks *,CSAudioSpecificConfig *,int *,uchar,uchar)
0x180078a4a  test    eax, eax
0x180078a4c  jnz     loc_180078B34
0x180078a52  cmp     [rsi+1Fh], bpl
0x180078a56  jz      short loc_180078A67
0x180078a58  cmp     [rbx+28h], bpl
0x180078a5c  jz      short loc_180078A67
0x180078a5e  mov     [rbx+27h], bp
0x180078a62  jmp     loc_180078B09
0x180078a67  movups  xmmword ptr [rdi], xmm6
0x180078a6a  movups  xmmword ptr [rdi+10h], xmm7
0x180078a6e  movups  xmmword ptr [rdi+20h], xmm8
0x180078a73  mov     byte ptr [rbx+27h], 1
0x180078a77  movups  xmm6, xmmword ptr [rdi]
0x180078a7a  mov     r13b, bpl
0x180078a7d  mov     r12b, 1
0x180078a80  movups  xmm7, xmmword ptr [rdi+10h]
0x180078a84  movups  xmm8, xmmword ptr [rdi+20h]
0x180078a89  cmp     ebp, 2
0x180078a8c  jge     short loc_180078B07
0x180078a8e  cmp     ebp, 1
0x180078a91  jnz     short loc_180078AA2
0x180078a93  movups  xmmword ptr [rdi], xmm6
0x180078a96  mov     r12b, 2
0x180078a99  movups  xmmword ptr [rdi+10h], xmm7
0x180078a9d  movups  xmmword ptr [rdi+20h], xmm8
0x180078aa2  mov     [rsp+0B8h+var_88], r13b
0x180078aa7  mov     r9, rsi
0x180078aaa  mov     [rsp+0B8h+var_90], r12b
0x180078aaf  mov     r8, r15
0x180078ab2  mov     rdx, rbx
0x180078ab5  mov     [rsp+0B8h+var_98], r14
0x180078aba  mov     rcx, rdi
0x180078abd  call    ?CLatmDemux_ReadStreamMuxConfig@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@PEAUCSTpCallBacks@@PEAUCSAudioSpecificConfig@@PEAHEE@Z; CLatmDemux_ReadStreamMuxConfig(CDK_BITSTREAM *,CLatmDemux *,CSTpCallBacks *,CSAudioSpecificConfig *,int *,uchar,uchar)
0x180078ac2  xor     ecx, ecx
0x180078ac4  test    eax, eax
0x180078ac6  jnz     short loc_180078B34
0x180078ac8  test    ebp, ebp
0x180078aca  jnz     short loc_180078AFC
0x180078acc  cmp     [rsi+4D3h], cl
0x180078ad2  jnz     short loc_180078AE4
0x180078ad4  cmp     [rsi+4D4h], cl
0x180078ada  jnz     short loc_180078AE4
0x180078adc  cmp     [rsi+4D5h], cl
0x180078ae2  jz      short loc_180078AFC
0x180078ae4  mov     rcx, [r15+28h]
0x180078ae8  mov     rdx, rsi
0x180078aeb  mov     rax, [r15+20h]
0x180078aef  mov     r13b, 1
0x180078af2  call    cs:__guard_dispatch_icall_fptr
0x180078af8  test    eax, eax
0x180078afa  jnz     short loc_180078B00
0x180078afc  inc     ebp
0x180078afe  jmp     short loc_180078A89
0x180078b00  mov     eax, 401h
0x180078b05  jmp     short loc_180078B34
0x180078b07  xor     ebp, ebp
0x180078b09  cmp     [r14], ebp
0x180078b0c  jnz     short loc_180078B15
0x180078b0e  mov     eax, 102h
0x180078b13  jmp     short loc_180078B34
0x180078b15  cmp     [rbx+1Eh], bpl
0x180078b19  jnz     short loc_180078B2C
0x180078b1b  mov     rdx, rbx
0x180078b1e  mov     rcx, rdi
0x180078b21  call    ?CLatmDemux_ReadPayloadLengthInfo@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@@Z; CLatmDemux_ReadPayloadLengthInfo(CDK_BITSTREAM *,CLatmDemux *)
0x180078b26  test    eax, eax
0x180078b28  jz      short loc_180078B38
0x180078b2a  jmp     short loc_180078B31
0x180078b2c  mov     eax, 402h
0x180078b31  mov     [r14], ebp
0x180078b34  mov     byte ptr [rbx+27h], 1
0x180078b38  movaps  xmm6, [rsp+0B8h+var_58]
0x180078b3d  movaps  xmm7, [rsp+0B8h+var_68]
0x180078b42  movaps  xmm8, [rsp+0B8h+var_78]
0x180078b48  add     rsp, 78h
0x180078b4c  pop     r15
0x180078b4e  pop     r14
0x180078b50  pop     r13
0x180078b52  pop     r12
0x180078b54  pop     rdi
0x180078b55  pop     rsi
0x180078b56  pop     rbp
0x180078b57  pop     rbx
0x180078b58  retn
```
