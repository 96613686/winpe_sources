# aacDecoder_Open

- ea: `0x180005288`
- end: `0x180005436`
- name: `aacDecoder_Open`
- size: `430`
- prototype: `struct TRANSPORTDEC *()`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180048894`

## callees

- `0x18000503c`
- `0x1800051b0`
- `0x180005288`
- `0x18000543c`
- `0x18000546c`
- `0x1800055ec`
- `0x180005688`
- `0x1800056a8`
- `0x18000581c`
- `0x180005dc0`
- `0x180005f40`
- `0x180005f70`
- `0x18002f280`
- `0x18002f3e8`
- `0x1800408b0`
- `0x18004dd14`

## pseudocode

```c
struct TRANSPORTDEC *aacDecoder_Open()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  struct TRANSPORTDEC *result; // rax
  struct TRANSPORTDEC *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  int (__high *v8)(void *, struct CDK_BITSTREAM *, int, int, int, int, enum AUDIO_OBJECT_TYPE); // rdx
  unsigned int v9; // edx
  unsigned int v10; // ecx
  unsigned int v11; // r9d
  struct TDLimiter *v12; // rax
  unsigned int Method; // eax
  unsigned int v14; // [rsp+20h] [rbp-38h]
  struct TRANSPORTDEC *v15; // [rsp+70h] [rbp+18h] BYREF

  CDKinit_check();
  result = (struct TRANSPORTDEC *)transportDec_Open(v1, v0, 1);
  v15 = result;
  v3 = result;
  if ( result )
  {
    v4 = CAacDecoder_Open();
    v5 = v4;
    if ( v4 )
    {
      *(_QWORD *)(v4 + 24) = v3;
      *(_DWORD *)(v4 + 16) = 1;
      CDK_chMapDescr_init(v4 + 864);
      *((_QWORD *)v3 + 2) = v5;
      *((_QWORD *)v3 + 1) = aacDecoder_ConfigCallback;
      *((_QWORD *)v3 + 3) = aacDecoder_DecodeFrameCallback;
      *((_QWORD *)v3 + 4) = v5;
      *((_QWORD *)v3 + 5) = aacDecoder_FreeMemCallback;
      *((_QWORD *)v3 + 6) = v5;
      *((_QWORD *)v3 + 7) = aacDecoder_CtrlCFGChangeCallback;
      *((_QWORD *)v3 + 8) = v5;
      memset_0((void *)(v5 + 2600), 0, 0x6C8u);
      if ( (unsigned int)sbrDecoder_Open(v5 + 2568, v5 + 2600) )
        goto LABEL_14;
      v6 = *(_QWORD *)(v5 + 24);
      if ( v6 )
      {
        v7 = *(_QWORD *)(v5 + 2568);
        *(_QWORD *)(v6 + 88) = aacDecoder_SbrCallback;
        *(_QWORD *)(v6 + 96) = v7;
      }
      if ( (unsigned int)mpegSurroundDecoder_Create(v5 + 4352, 0xFFFFFFFFLL, v5 + 2600) )
        goto LABEL_14;
      *(_DWORD *)(v5 + 4360) = 0;
      *((_QWORD *)v3 + 10) = v5;
      *((_QWORD *)v3 + 9) = aacDecoder_SscCallback;
      if ( (unsigned int)CDK_drcDec_Open(v5 + 4448)
        || (transportDec_RegisterUniDrcConfigCallback(v3, v8, (void *)v5, (int *)(v5 + 4456)),
            *(_BYTE *)(v5 + 4468) = 96,
            pcmDmx_Open(v5 + 4424),
            !*(_QWORD *)(v5 + 4424))
        || (v12 = pcmLimiter_Create(v10, v9, 1.0, v11, v14), (*(_QWORD *)(v5 + 4432) = v12) == 0)
        || (*(_WORD *)(v5 + 4440) = 255,
            Method = CConcealment_GetMethod(v5 + 2128),
            (unsigned int)setConcealMethod(v5, Method)) )
      {
LABEL_14:
        aacDecoder_Close((struct AAC_DECODER_INSTANCE *)v5);
        return 0;
      }
    }
    else
    {
      transportDec_Close(&v15);
    }
    return (struct TRANSPORTDEC *)v5;
  }
  return result;
}

```

## disassembly

```asm
0x180005288  push    rbx
0x18000528a  push    rsi
0x18000528b  push    rdi
0x18000528c  push    r14
0x18000528e  sub     rsp, 38h
0x180005292  call    CDKinit_check
0x180005297  mov     esi, 1
0x18000529c  mov     r8d, esi
0x18000529f  call    ?transportDec_Open@@YAPEAUTRANSPORTDEC@@W4TRANSPORT_TYPE@@II@Z; transportDec_Open(TRANSPORT_TYPE,uint,uint)
0x1800052a4  mov     [rsp+58h+arg_10], rax
0x1800052a9  mov     rbx, rax
0x1800052ac  test    rax, rax
0x1800052af  jz      loc_18000541C
0x1800052b5  call    ?CAacDecoder_Open@@YAPEAUAAC_DECODER_INSTANCE@@W4TRANSPORT_TYPE@@@Z; CAacDecoder_Open(TRANSPORT_TYPE)
0x1800052ba  mov     rdi, rax
0x1800052bd  test    rax, rax
0x1800052c0  jz      loc_18000541E
0x1800052c6  lea     rcx, [rax+360h]
0x1800052cd  mov     [rax+18h], rbx
0x1800052d1  mov     [rax+10h], esi
0x1800052d4  call    CDK_chMapDescr_init
0x1800052d9  mov     [rbx+10h], rdi
0x1800052dd  lea     rcx, aacDecoder_ConfigCallback
0x1800052e4  mov     [rbx+8], rcx
0x1800052e8  lea     rax, aacDecoder_DecodeFrameCallback
0x1800052ef  mov     [rbx+18h], rax
0x1800052f3  lea     rsi, [rdi+0A28h]
0x1800052fa  mov     [rbx+20h], rdi
0x1800052fe  lea     rax, aacDecoder_FreeMemCallback
0x180005305  mov     [rbx+28h], rax
0x180005309  xor     edx, edx; Val
0x18000530b  mov     [rbx+30h], rdi
0x18000530f  lea     rax, aacDecoder_CtrlCFGChangeCallback
0x180005316  mov     r8d, 6C8h; Size
0x18000531c  mov     [rbx+38h], rax
0x180005320  mov     rcx, rsi; void *
0x180005323  mov     [rbx+40h], rdi
0x180005327  call    memset_0
0x18000532c  lea     r14, [rdi+0A08h]
0x180005333  mov     rdx, rsi
0x180005336  mov     rcx, r14
0x180005339  call    sbrDecoder_Open
0x18000533e  test    eax, eax
0x180005340  jnz     loc_18000542A
0x180005346  mov     rcx, [rdi+18h]
0x18000534a  test    rcx, rcx
0x18000534d  jz      short loc_180005361
0x18000534f  mov     rax, [r14]
0x180005352  lea     rdx, aacDecoder_SbrCallback
0x180005359  mov     [rcx+58h], rdx
0x18000535d  mov     [rcx+60h], rax
0x180005361  lea     rcx, [rdi+1100h]
0x180005368  mov     r8, rsi
0x18000536b  or      edx, 0FFFFFFFFh
0x18000536e  call    mpegSurroundDecoder_Create
0x180005373  test    eax, eax
0x180005375  jnz     loc_18000542A
0x18000537b  mov     [rdi+1108h], eax
0x180005381  lea     rcx, [rdi+1160h]
0x180005388  lea     rax, aacDecoder_SscCallback
0x18000538f  mov     [rbx+50h], rdi
0x180005393  mov     [rbx+48h], rax
0x180005397  call    CDK_drcDec_Open
0x18000539c  test    eax, eax
0x18000539e  jnz     loc_18000542A
0x1800053a4  lea     r9, [rdi+1168h]; int *
0x1800053ab  mov     r8, rdi; void *
0x1800053ae  mov     rcx, rbx; struct TRANSPORTDEC *
0x1800053b1  call    ?transportDec_RegisterUniDrcConfigCallback@@YAHPEAUTRANSPORTDEC@@Q6AHPEAXPEAUCDK_BITSTREAM@@HHHHW4AUDIO_OBJECT_TYPE@@@Z1PEAH@Z; transportDec_RegisterUniDrcConfigCallback(TRANSPORTDEC *,int (*const)(void *,CDK_BITSTREAM *,int,int,int,int,AUDIO_OBJECT_TYPE),void *,int *)
0x1800053b6  lea     rbx, [rdi+1148h]
0x1800053bd  mov     byte ptr [rdi+1174h], 60h ; '`'
0x1800053c4  mov     rcx, rbx
0x1800053c7  call    pcmDmx_Open
0x1800053cc  cmp     qword ptr [rbx], 0
0x1800053d0  jz      short loc_18000542A
0x1800053d2  movss   xmm2, cs:__real@3f800000; float
0x1800053da  call    ?pcmLimiter_Create@@YAPEAUTDLimiter@@IIMII@Z; pcmLimiter_Create(uint,uint,float,uint,uint)
0x1800053df  mov     [rdi+1150h], rax
0x1800053e6  test    rax, rax
0x1800053e9  jz      short loc_18000542A
0x1800053eb  lea     rcx, [rdi+850h]
0x1800053f2  mov     word ptr [rdi+1158h], 0FFh
0x1800053fb  call    ?CConcealment_GetMethod@@YA?AW4CConcealmentMethod@@PEAUCConcealParams_fl@@@Z; CConcealment_GetMethod(CConcealParams_fl *)
0x180005400  mov     edx, eax
0x180005402  mov     rcx, rdi
0x180005405  call    setConcealMethod
0x18000540a  test    eax, eax
0x18000540c  jnz     short loc_18000542A
0x18000540e  mov     rax, rdi
0x180005411  add     rsp, 38h
0x180005415  pop     r14
0x180005417  pop     rdi
0x180005418  pop     rsi
0x180005419  pop     rbx
0x18000541a  retn
0x18000541c  jmp     short loc_180005411
0x18000541e  lea     rcx, [rsp+58h+arg_10]; struct TRANSPORTDEC **
0x180005423  call    ?transportDec_Close@@YAXPEAPEAUTRANSPORTDEC@@@Z; transportDec_Close(TRANSPORTDEC * *)
0x180005428  jmp     short loc_18000540E
0x18000542a  mov     rcx, rdi; Block
0x18000542d  call    aacDecoder_Close
0x180005432  xor     edi, edi
0x180005434  jmp     short loc_18000540E
```
