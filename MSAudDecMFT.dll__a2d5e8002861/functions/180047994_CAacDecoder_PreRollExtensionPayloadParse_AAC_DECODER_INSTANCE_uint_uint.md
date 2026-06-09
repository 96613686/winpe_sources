# CAacDecoder_PreRollExtensionPayloadParse(AAC_DECODER_INSTANCE *,uint *,uint *)

- ea: `0x180047994`
- end: `0x180047c4f`
- name: `?CAacDecoder_PreRollExtensionPayloadParse@@YA?AW4AAC_DECODER_ERROR@@PEAUAAC_DECODER_INSTANCE@@PEAI1@Z`
- size: `699`
- prototype: `__int64 __fastcall(__int64, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a810`

## callees

- `0x18000c38c`
- `0x180013550`
- `0x180013f68`
- `0x180017540`
- `0x180047994`
- `0x18004d320`
- `0x18004dd14`
- `0x1800712d4`
- `0x1800717e0`

## pseudocode

```c
__int64 __fastcall CAacDecoder_PreRollExtensionPayloadParse(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v6; // rax
  char v7; // r14
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  unsigned int v10; // edi
  BOOL v11; // ebx
  int v12; // eax
  BOOL v13; // ecx
  unsigned int v14; // r12d
  __int64 v15; // rbx
  __int64 v16; // r9
  char v17; // al
  char v18; // cl
  char v19; // r9
  char v20; // cl
  unsigned int v21; // eax
  __int64 i; // r14
  int v23; // ebx
  int v24; // eax
  int v25; // ebx
  __int64 v27; // [rsp+28h] [rbp-D8h]
  char v28; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[3]; // [rsp+41h] [rbp-BFh] BYREF
  int v30; // [rsp+44h] [rbp-BCh]
  _OWORD v31[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v32[512]; // [rsp+80h] [rbp-80h] BYREF

  v29[0] = 0;
  memset_0(v32, 0, sizeof(v32));
  v6 = *(_QWORD *)(a1 + 24);
  v7 = 0;
  v28 = 0;
  v8 = *(_OWORD *)(v6 + 152);
  v31[0] = *(_OWORD *)(v6 + 136);
  v9 = *(_OWORD *)(v6 + 168);
  v31[1] = v8;
  v31[2] = v9;
  CDKsyncCache(v31);
  v30 = DWORD2(v31[0]);
  if ( SDWORD2(v31[0]) <= 0 )
    return 4098;
  v10 = 0;
  CDKreadBit(v31);
  v11 = CDKreadBit(v31) != 0;
  v12 = CDKreadBit(v31);
  v13 = 0;
  if ( !v12 )
    v13 = v11;
  if ( !v13 )
  {
    if ( !*(_BYTE *)(a1 + 4600) )
      return v10;
    *(_BYTE *)(a1 + 4600) = 0;
    return 16386;
  }
  escapedValue(v31, 8, 16);
  v14 = escapedValue(v31, 4, 4);
  if ( (*(_DWORD *)(a1 + 68) & 0x100) != 0 && v14 )
  {
    v15 = 0;
    do
    {
      v32[v15] = CDKreadBits_1(v31, 8);
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < v14 );
    if ( (unsigned int)transportDec_InBandConfig(*(_QWORD *)(a1 + 24), v32, v14, v16, v29, v27, &v28) )
      return 16386;
    v7 = v28;
  }
  if ( !*(_DWORD *)(a1 + 1364) && !v7 )
  {
    if ( (*(_DWORD *)(a1 + 68) & 0x100) == 0 )
      goto LABEL_23;
    *(_BYTE *)(a1 + 4602) = 3;
    if ( *(_BYTE *)(a1 + 4600) )
    {
      *(_BYTE *)(a1 + 4600) = 0;
      return 16386;
    }
  }
  if ( (*(_DWORD *)(a1 + 68) & 0x100) != 0 && *(_BYTE *)(a1 + 4602) == 3 )
  {
    v17 = CDKreadBit(v31);
    v18 = *(_BYTE *)(a1 + 4632);
    v19 = v18 | 2;
    v20 = v18 & 0xFD;
    if ( !v17 )
      v19 = v20;
    *(_BYTE *)(a1 + 4632) = v19;
    CDKreadBit(v31);
    v21 = escapedValue(v31, 2, 4);
    *a2 = v21;
    if ( v21 > 3 )
    {
LABEL_22:
      *a2 = 0;
      return 16386;
    }
  }
LABEL_23:
  for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
  {
    v23 = escapedValue(v31, 16, 16);
    if ( v23 <= 0 )
      goto LABEL_22;
    CDKsyncCache(v31);
    *(_DWORD *)(a3 + 4 * i) = v30 - DWORD2(v31[0]);
    v24 = CDKreadBit(v31);
    if ( !(_DWORD)i && !v24 )
      goto LABEL_22;
    v25 = 8 * v23;
    CDKpushFor_0(v31, (unsigned int)(v25 - 1));
    *(_DWORD *)(a1 + 4 * i + 4608) = v25 + *(_DWORD *)(a3 + 4 * i);
  }
  return v10;
}

```

## disassembly

```asm
0x180047994  mov     [rsp-8+arg_18], rbx
0x180047999  push    rbp
0x18004799a  push    rsi
0x18004799b  push    rdi
0x18004799c  push    r12
0x18004799e  push    r13
0x1800479a0  push    r14
0x1800479a2  push    r15
0x1800479a4  lea     rbp, [rsp-190h]
0x1800479ac  sub     rsp, 290h
0x1800479b3  mov     rax, cs:__security_cookie
0x1800479ba  xor     rax, rsp
0x1800479bd  mov     [rbp+1C0h+var_40], rax
0x1800479c4  mov     r13, r8
0x1800479c7  mov     r15, rdx
0x1800479ca  mov     rsi, rcx
0x1800479cd  xor     r12d, r12d
0x1800479d0  xor     edx, edx; Val
0x1800479d2  mov     [rsp+2C0h+var_27F], r12b
0x1800479d7  mov     r8d, 200h; Size
0x1800479dd  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800479e1  call    memset_0
0x1800479e6  mov     rax, [rsi+18h]
0x1800479ea  lea     rcx, [rsp+2C0h+var_278]
0x1800479ef  mov     r14b, r12b
0x1800479f2  mov     [rsp+2C0h+var_280], r12b
0x1800479f7  movups  xmm0, xmmword ptr [rax+88h]
0x1800479fe  movups  xmm1, xmmword ptr [rax+98h]
0x180047a05  movups  [rsp+2C0h+var_278], xmm0
0x180047a0a  movups  xmm0, xmmword ptr [rax+0A8h]
0x180047a11  movups  [rsp+2C0h+var_268], xmm1
0x180047a16  movups  [rsp+2C0h+var_258], xmm0
0x180047a1b  call    CDKsyncCache
0x180047a20  mov     eax, dword ptr [rsp+2C0h+var_278+8]
0x180047a24  mov     [rsp+2C0h+var_27C], eax
0x180047a28  test    eax, eax
0x180047a2a  jg      short loc_180047A36
0x180047a2c  mov     edi, 1002h
0x180047a31  jmp     loc_180047C22
0x180047a36  lea     rcx, [rsp+2C0h+var_278]
0x180047a3b  mov     edi, r12d
0x180047a3e  call    CDKreadBit
0x180047a43  lea     rcx, [rsp+2C0h+var_278]
0x180047a48  call    CDKreadBit
0x180047a4d  test    eax, eax
0x180047a4f  lea     rcx, [rsp+2C0h+var_278]
0x180047a54  mov     ebx, r12d
0x180047a57  setnz   bl
0x180047a5a  call    CDKreadBit
0x180047a5f  test    eax, eax
0x180047a61  mov     ecx, r12d
0x180047a64  cmovz   ecx, ebx
0x180047a67  test    ecx, ecx
0x180047a69  jz      loc_180047C0D
0x180047a6f  xor     r9d, r9d
0x180047a72  lea     rcx, [rsp+2C0h+var_278]
0x180047a77  lea     ebx, [r9+8]
0x180047a7b  mov     edx, ebx
0x180047a7d  lea     r8d, [r9+10h]
0x180047a81  call    escapedValue
0x180047a86  lea     edx, [rbx-4]
0x180047a89  mov     r9d, ebx
0x180047a8c  mov     r8d, edx
0x180047a8f  lea     rcx, [rsp+2C0h+var_278]
0x180047a94  call    escapedValue
0x180047a99  mov     r12d, eax
0x180047a9c  mov     eax, 100h
0x180047aa1  test    [rsi+44h], eax
0x180047aa4  jz      short loc_180047AFD
0x180047aa6  test    r12d, r12d
0x180047aa9  jz      short loc_180047AFD
0x180047aab  xor     ebx, ebx
0x180047aad  mov     edx, 8
0x180047ab2  lea     rcx, [rsp+2C0h+var_278]
0x180047ab7  call    CDKreadBits_1
0x180047abc  mov     [rbp+rbx+1C0h+var_240], al
0x180047ac0  inc     ebx
0x180047ac2  cmp     ebx, r12d
0x180047ac5  jb      short loc_180047AAD
0x180047ac7  mov     rcx, [rsi+18h]
0x180047acb  lea     rax, [rsp+2C0h+var_280]
0x180047ad0  mov     [rsp+2C0h+var_290], rax
0x180047ad5  lea     rdx, [rbp+1C0h+var_240]
0x180047ad9  lea     rax, [rsp+2C0h+var_27F]
0x180047ade  mov     r8d, r12d
0x180047ae1  mov     [rsp+2C0h+var_2A0], rax
0x180047ae6  call    ?transportDec_InBandConfig@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@PEAEIE1I1@Z; transportDec_InBandConfig(TRANSPORTDEC * const,uchar *,uint,uchar,uchar *,uint,uchar *)
0x180047aeb  test    eax, eax
0x180047aed  jnz     loc_180047C1D
0x180047af3  mov     r14b, [rsp+2C0h+var_280]
0x180047af8  mov     eax, 100h
0x180047afd  cmp     [rsi+554h], edi
0x180047b03  jnz     short loc_180047B2F
0x180047b05  test    r14b, r14b
0x180047b08  jnz     short loc_180047B2F
0x180047b0a  test    [rsi+44h], eax
0x180047b0d  jz      loc_180047B9B
0x180047b13  mov     byte ptr [rsi+11FAh], 3
0x180047b1a  cmp     [rsi+11F8h], dil
0x180047b21  jz      short loc_180047B2F
0x180047b23  mov     [rsi+11F8h], dil
0x180047b2a  jmp     loc_180047C1D
0x180047b2f  test    [rsi+44h], eax
0x180047b32  jz      short loc_180047B9B
0x180047b34  cmp     byte ptr [rsi+11FAh], 3
0x180047b3b  jnz     short loc_180047B9B
0x180047b3d  lea     rcx, [rsp+2C0h+var_278]
0x180047b42  call    CDKreadBit
0x180047b47  mov     r9b, [rsi+1218h]
0x180047b4e  mov     cl, r9b
0x180047b51  or      r9b, 2
0x180047b55  and     cl, 0FDh
0x180047b58  movzx   r9d, r9b
0x180047b5c  movzx   ecx, cl
0x180047b5f  test    al, al
0x180047b61  cmovz   r9d, ecx
0x180047b65  lea     rcx, [rsp+2C0h+var_278]
0x180047b6a  mov     [rsi+1218h], r9b
0x180047b71  call    CDKreadBit
0x180047b76  xor     r9d, r9d
0x180047b79  lea     rcx, [rsp+2C0h+var_278]
0x180047b7e  lea     edx, [r9+2]
0x180047b82  lea     r8d, [r9+4]
0x180047b86  call    escapedValue
0x180047b8b  mov     [r15], eax
0x180047b8e  cmp     eax, 3
0x180047b91  jbe     short loc_180047B9B
0x180047b93  mov     [r15], edi
0x180047b96  jmp     loc_180047C1D
0x180047b9b  xor     r14d, r14d
0x180047b9e  cmp     r14d, [r15]
0x180047ba1  jnb     short loc_180047C22
0x180047ba3  xor     r9d, r9d
0x180047ba6  lea     rcx, [rsp+2C0h+var_278]
0x180047bab  lea     eax, [r9+10h]
0x180047baf  mov     r8d, eax
0x180047bb2  mov     edx, eax
0x180047bb4  call    escapedValue
0x180047bb9  mov     ebx, eax
0x180047bbb  test    eax, eax
0x180047bbd  jle     short loc_180047B93
0x180047bbf  lea     rcx, [rsp+2C0h+var_278]
0x180047bc4  call    CDKsyncCache
0x180047bc9  mov     ecx, [rsp+2C0h+var_27C]
0x180047bcd  sub     ecx, dword ptr [rsp+2C0h+var_278+8]
0x180047bd1  mov     [r13+r14*4+0], ecx
0x180047bd6  lea     rcx, [rsp+2C0h+var_278]
0x180047bdb  call    CDKreadBit
0x180047be0  test    r14d, r14d
0x180047be3  jnz     short loc_180047BE9
0x180047be5  test    eax, eax
0x180047be7  jz      short loc_180047B93
0x180047be9  shl     ebx, 3
0x180047bec  lea     rcx, [rsp+2C0h+var_278]
0x180047bf1  lea     edx, [rbx-1]
0x180047bf4  call    CDKpushFor_0
0x180047bf9  mov     ecx, [r13+r14*4+0]
0x180047bfe  add     ecx, ebx
0x180047c00  mov     [rsi+r14*4+1200h], ecx
0x180047c08  inc     r14d
0x180047c0b  jmp     short loc_180047B9E
0x180047c0d  cmp     [rsi+11F8h], r12b
0x180047c14  jz      short loc_180047C22
0x180047c16  mov     [rsi+11F8h], r12b
0x180047c1d  mov     edi, 4002h
0x180047c22  mov     eax, edi
0x180047c24  mov     rcx, [rbp+1C0h+var_40]
0x180047c2b  xor     rcx, rsp; StackCookie
0x180047c2e  call    __security_check_cookie
0x180047c33  mov     rbx, [rsp+2C0h+arg_18]
0x180047c3b  add     rsp, 290h
0x180047c42  pop     r15
0x180047c44  pop     r14
0x180047c46  pop     r13
0x180047c48  pop     r12
0x180047c4a  pop     rdi
0x180047c4b  pop     rsi
0x180047c4c  pop     rbp
0x180047c4d  retn
```
