# CDataStreamElement_Read

- ea: `0x180013dac`
- end: `0x180013eec`
- name: `CDataStreamElement_Read`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000c510`

## callees

- `0x18000c38c`
- `0x18000eb68`
- `0x180012d90`
- `0x180012fdc`
- `0x18001308c`
- `0x1800131b4`
- `0x180013550`
- `0x180013dac`
- `0x180013ef4`
- `0x180013f68`
- `0x180014078`
- `0x180017540`

## pseudocode

```c
__int64 __fastcall CDataStreamElement_Read(__int64 a1, __int64 a2, _BYTE *a3, unsigned int a4)
{
  int started; // r12d
  int v9; // ebp
  unsigned int v10; // ebx
  unsigned int v11; // esi
  int v12; // ebp
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx

  started = transportDec_CrcStartReg(*(struct TRANSPORTDEC *const *)(a1 + 24), 0);
  *a3 = CDKreadBits_1(a2, 4);
  v9 = CDKreadBit(a2);
  v10 = CDKreadBits_1(a2, 8);
  if ( v10 == 255 )
    v10 = CDKreadBits_1(a2, 8) + 255;
  v11 = 8 * v10;
  if ( v9 )
    CDKbyteAlign(a2, a4);
  CDKsyncCache(a2);
  v12 = *(_DWORD *)(a2 + 8);
  v13 = CAacDecoder_AncDataParse(a1 + 4376, a2, v10);
  transportDec_CrcEndReg(*(struct TRANSPORTDEC *const *)(a1 + 24), started);
  CDKsyncCache(a2);
  CDKpushBack_2(a2, (unsigned int)(v12 - *(_DWORD *)(a2 + 8)));
  aacDecoder_drcMarkPayload(*(_QWORD *)(a1 + 4336), a2, 2);
  CDKsyncCache(a2);
  CDKpushBack_2(a2, (unsigned int)(v12 - *(_DWORD *)(a2 + 8)));
  v14 = pcmDmx_Parse(*(_QWORD *)(a1 + 4424), a2, v11);
  if ( !v13 && v14 )
    v13 = 5;
  CDKsyncCache(a2);
  v15 = v11 + *(_DWORD *)(a2 + 8) - v12;
  if ( (int)v15 >= 0 )
    CDKpushFor_0(a2, v15);
  else
    CDKpushBack_2(a2, (unsigned int)-(int)v15);
  return v13;
}

```

## disassembly

```asm
0x180013dac  push    rbx
0x180013dae  push    rbp
0x180013daf  push    rsi
0x180013db0  push    rdi
0x180013db1  push    r12
0x180013db3  push    r14
0x180013db5  push    r15
0x180013db7  sub     rsp, 20h
0x180013dbb  mov     rdi, rdx
0x180013dbe  mov     r15, rcx
0x180013dc1  mov     rcx, [rcx+18h]; struct TRANSPORTDEC *
0x180013dc5  xor     edx, edx; int
0x180013dc7  mov     r14d, r9d
0x180013dca  mov     rbx, r8
0x180013dcd  call    ?transportDec_CrcStartReg@@YAHQEAUTRANSPORTDEC@@H@Z; transportDec_CrcStartReg(TRANSPORTDEC * const,int)
0x180013dd2  mov     edx, 4
0x180013dd7  mov     rcx, rdi
0x180013dda  mov     r12d, eax
0x180013ddd  call    CDKreadBits_1
0x180013de2  mov     rcx, rdi
0x180013de5  mov     [rbx], al
0x180013de7  call    CDKreadBit
0x180013dec  mov     esi, 8
0x180013df1  mov     rcx, rdi
0x180013df4  mov     edx, esi
0x180013df6  mov     ebp, eax
0x180013df8  call    CDKreadBits_1
0x180013dfd  mov     ebx, eax
0x180013dff  cmp     eax, 0FFh
0x180013e04  jnz     short loc_180013E16
0x180013e06  mov     edx, esi
0x180013e08  mov     rcx, rdi
0x180013e0b  call    CDKreadBits_1
0x180013e10  lea     ebx, [rax+0FFh]
0x180013e16  lea     esi, ds:0[rbx*8]
0x180013e1d  test    ebp, ebp
0x180013e1f  jz      short loc_180013E2C
0x180013e21  mov     edx, r14d
0x180013e24  mov     rcx, rdi
0x180013e27  call    CDKbyteAlign
0x180013e2c  mov     rcx, rdi
0x180013e2f  call    CDKsyncCache
0x180013e34  mov     ebp, [rdi+8]
0x180013e37  lea     rcx, [r15+1118h]
0x180013e3e  mov     r8d, ebx
0x180013e41  mov     rdx, rdi
0x180013e44  call    CAacDecoder_AncDataParse
0x180013e49  mov     rcx, [r15+18h]; struct TRANSPORTDEC *
0x180013e4d  mov     edx, r12d; int
0x180013e50  mov     ebx, eax
0x180013e52  call    ?transportDec_CrcEndReg@@YAXQEAUTRANSPORTDEC@@H@Z; transportDec_CrcEndReg(TRANSPORTDEC * const,int)
0x180013e57  mov     rcx, rdi
0x180013e5a  call    CDKsyncCache
0x180013e5f  mov     edx, ebp
0x180013e61  mov     rcx, rdi
0x180013e64  sub     edx, [rdi+8]
0x180013e67  call    CDKpushBack_2
0x180013e6c  mov     rcx, [r15+10F0h]
0x180013e73  mov     r8d, 2
0x180013e79  mov     rdx, rdi
0x180013e7c  call    ?aacDecoder_drcMarkPayload@@YAHPEAUCDrcInfo@@PEAUCDK_BITSTREAM@@W4AACDEC_DRC_PAYLOAD_TYPE@@@Z; aacDecoder_drcMarkPayload(CDrcInfo *,CDK_BITSTREAM *,AACDEC_DRC_PAYLOAD_TYPE)
0x180013e81  mov     rcx, rdi
0x180013e84  call    CDKsyncCache
0x180013e89  mov     edx, ebp
0x180013e8b  mov     rcx, rdi
0x180013e8e  sub     edx, [rdi+8]
0x180013e91  call    CDKpushBack_2
0x180013e96  mov     rcx, [r15+1148h]
0x180013e9d  mov     r8d, esi
0x180013ea0  mov     rdx, rdi
0x180013ea3  call    pcmDmx_Parse
0x180013ea8  test    ebx, ebx
0x180013eaa  jz      short loc_180013EE0
0x180013eac  mov     rcx, rdi
0x180013eaf  call    CDKsyncCache
0x180013eb4  mov     edx, [rdi+8]
0x180013eb7  mov     rcx, rdi
0x180013eba  sub     edx, ebp
0x180013ebc  add     edx, esi
0x180013ebe  jns     short loc_180013ED9
0x180013ec0  neg     edx
0x180013ec2  call    CDKpushBack_2
0x180013ec7  mov     eax, ebx
0x180013ec9  add     rsp, 20h
0x180013ecd  pop     r15
0x180013ecf  pop     r14
0x180013ed1  pop     r12
0x180013ed3  pop     rdi
0x180013ed4  pop     rsi
0x180013ed5  pop     rbp
0x180013ed6  pop     rbx
0x180013ed7  retn
0x180013ed9  call    CDKpushFor_0
0x180013ede  jmp     short loc_180013EC7
0x180013ee0  test    eax, eax
0x180013ee2  mov     ecx, 5
0x180013ee7  cmovnz  ebx, ecx
0x180013eea  jmp     short loc_180013EAC
```
