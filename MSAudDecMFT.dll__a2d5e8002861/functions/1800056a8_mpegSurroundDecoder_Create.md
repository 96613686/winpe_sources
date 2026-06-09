# mpegSurroundDecoder_Create

- ea: `0x1800056a8`
- end: `0x180005816`
- name: `mpegSurroundDecoder_Create`
- size: `366`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180005288`
- `0x18000a810`
- `0x180018730`
- `0x1800723b4`

## callees

- `0x1800056a8`
- `0x18003ede0`
- `0x18003f438`
- `0x180071dbc`
- `0x18007f9b0`
- `0x1800803ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800056cd`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800056cd`

## pseudocode

```c
__int64 __fastcall mpegSurroundDecoder_Create(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  unsigned int BsFrame; // esi
  void *v7; // rax
  _QWORD *v8; // r8
  __int64 v9; // rcx
  char *v11; // rcx
  __int64 v12; // rcx

  v3 = *(_QWORD **)a1;
  if ( !*(_QWORD *)a1 )
  {
    BsFrame = 0;
    v7 = calloc(1u, 0x1610u);
    *(_QWORD *)a1 = v7;
    if ( v7 )
    {
      while ( 1 )
      {
        v8 = *(_QWORD **)a1;
        if ( (int)v3 >= 1 )
        {
          *v8 = a3;
          v9 = 0;
          *(_BYTE *)(*(_QWORD *)a1 + 5590LL) = 1;
          do
            *(_BYTE *)(*(_QWORD *)a1 + v9++ + 5588) = 0;
          while ( v9 != 2 );
          return 0;
        }
        BsFrame = SpatialDecCreateBsFrame(&v8[386 * (int)v3 + 308], v8 + 694);
        if ( BsFrame )
          break;
        LODWORD(v3) = (_DWORD)v3 + 1;
      }
      v3 = *(_QWORD **)a1;
      if ( *(_QWORD *)a1 )
        goto LABEL_15;
    }
    *(_QWORD *)a1 = 0;
    if ( !BsFrame )
      return 4294966297LL;
    return BsFrame;
  }
  v11 = (char *)v3[282];
  if ( !v11 )
  {
    v11 = CDK_SpatialDecOpen(&xmmword_1800B9DC8);
    if ( !v11 )
    {
      BsFrame = -999;
LABEL_15:
      mpegSurroundDecoder_Close(v3);
      *(_QWORD *)a1 = 0;
      return BsFrame;
    }
  }
  *((_QWORD *)v11 + 156) = *v3;
  v3[282] = v11;
  *((_DWORD *)v3 + 1398) = 0x1000000;
  *((_DWORD *)v3 + 1399) = 10;
  *((_DWORD *)v3 + 1400) = 5;
  *((_DWORD *)v3 + 1401) = 5;
  v3[701] = 3;
  *(_WORD *)((char *)v3 + 2457) = 256;
  *((_BYTE *)v3 + 2456) = 0;
  updateMpegSurroundDecoderStatus(v3, 1);
  *(_QWORD *)a1 = v3;
  v12 = v3[282];
  *(_OWORD *)((char *)v3 + 5628) = xmmword_1800B9DC8;
  SpatialDecInitParserContext(v12);
  return 0;
}

```

## disassembly

```asm
0x1800056a8  push    rbx
0x1800056aa  push    rbp
0x1800056ab  push    rsi
0x1800056ac  push    rdi
0x1800056ad  sub     rsp, 28h
0x1800056b1  mov     rbx, [rcx]
0x1800056b4  mov     rbp, r8
0x1800056b7  mov     rdi, rcx
0x1800056ba  test    rbx, rbx
0x1800056bd  jnz     loc_18000575C
0x1800056c3  mov     edx, 1610h; Size
0x1800056c8  lea     ecx, [rbx+1]; Count
0x1800056cb  xor     esi, esi
0x1800056cd  call    cs:__imp_calloc
0x1800056d4  nop     dword ptr [rax+rax+00h]
0x1800056d9  mov     [rdi], rax
0x1800056dc  test    rax, rax
0x1800056df  jz      short loc_18000574A
0x1800056e1  mov     r8, [rdi]
0x1800056e4  cmp     ebx, 1
0x1800056e7  jl      short loc_180005718
0x1800056e9  mov     [r8], rbp
0x1800056ec  xor     ecx, ecx
0x1800056ee  mov     rax, [rdi]
0x1800056f1  mov     byte ptr [rax+15D6h], 1
0x1800056f8  mov     rax, [rdi]
0x1800056fb  mov     byte ptr [rax+rcx+15D4h], 0
0x180005703  inc     rcx
0x180005706  cmp     rcx, 2
0x18000570a  jnz     short loc_1800056F8
0x18000570c  xor     eax, eax
0x18000570e  add     rsp, 28h
0x180005712  pop     rdi
0x180005713  pop     rsi
0x180005714  pop     rbp
0x180005715  pop     rbx
0x180005716  retn
0x180005718  movsxd  rax, ebx
0x18000571b  lea     rdx, [r8+15B0h]
0x180005722  imul    rcx, rax, 0C10h
0x180005729  add     r8, 9A0h
0x180005730  add     rcx, r8
0x180005733  call    ?SpatialDecCreateBsFrame@@YA?AW4SACDEC_ERROR@@PEAUSPATIAL_BS_FRAME_struct@@PEAUBS_LL_STATE@@@Z; SpatialDecCreateBsFrame(SPATIAL_BS_FRAME_struct *,BS_LL_STATE *)
0x180005738  mov     esi, eax
0x18000573a  test    eax, eax
0x18000573c  jnz     short loc_180005742
0x18000573e  inc     ebx
0x180005740  jmp     short loc_1800056E1
0x180005742  mov     rbx, [rdi]
0x180005745  test    rbx, rbx
0x180005748  jnz     short loc_180005781
0x18000574a  mov     qword ptr [rdi], 0
0x180005751  test    esi, esi
0x180005753  jnz     short loc_180005790
0x180005755  mov     eax, 0FFFFFC19h
0x18000575a  jmp     short loc_18000570E
0x18000575c  mov     rcx, [rbx+8D0h]
0x180005763  test    rcx, rcx
0x180005766  jnz     short loc_180005797
0x180005768  lea     rcx, xmmword_1800B9DC8
0x18000576f  call    CDK_SpatialDecOpen
0x180005774  mov     rcx, rax
0x180005777  test    rax, rax
0x18000577a  jnz     short loc_180005797
0x18000577c  mov     esi, 0FFFFFC19h
0x180005781  mov     rcx, rbx; void *
0x180005784  call    mpegSurroundDecoder_Close
0x180005789  mov     qword ptr [rdi], 0
0x180005790  mov     eax, esi
0x180005792  jmp     loc_18000570E
0x180005797  mov     rax, [rbx]
0x18000579a  mov     [rcx+4E0h], rax
0x1800057a1  mov     eax, 5
0x1800057a6  mov     [rbx+8D0h], rcx
0x1800057ad  mov     rcx, rbx
0x1800057b0  mov     dword ptr [rbx+15D8h], 1000000h
0x1800057ba  mov     dword ptr [rbx+15DCh], 0Ah
0x1800057c4  lea     edx, [rax-4]
0x1800057c7  mov     [rbx+15E0h], eax
0x1800057cd  mov     [rbx+15E4h], eax
0x1800057d3  mov     qword ptr [rbx+15E8h], 3
0x1800057de  mov     word ptr [rbx+999h], 100h
0x1800057e7  mov     byte ptr [rbx+998h], 0
0x1800057ee  call    updateMpegSurroundDecoderStatus
0x1800057f3  mov     [rdi], rbx
0x1800057f6  movups  xmm0, cs:xmmword_1800B9DC8
0x1800057fd  mov     rcx, [rbx+8D0h]
0x180005804  movdqu  xmmword ptr [rbx+15FCh], xmm0
0x18000580c  call    SpatialDecInitParserContext
0x180005811  jmp     loc_18000570C
```
