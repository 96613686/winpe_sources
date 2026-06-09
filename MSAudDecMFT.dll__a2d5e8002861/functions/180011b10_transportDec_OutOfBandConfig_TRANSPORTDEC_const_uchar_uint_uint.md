# transportDec_OutOfBandConfig(TRANSPORTDEC * const,uchar *,uint,uint)

- ea: `0x180011b10`
- end: `0x180011da1`
- name: `?transportDec_OutOfBandConfig@@YA?AW4TRANSPORTDEC_ERROR@@QEAUTRANSPORTDEC@@PEAEII@Z`
- size: `657`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a810`
- `0x180041630`

## callees

- `0x18000e9b0`
- `0x18001115c`
- `0x180011b10`
- `0x180011da8`
- `0x18004d320`
- `0x18004dd14`
- `0x180078c50`
- `0x18009606c`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall transportDec_OutOfBandConfig(__int64 a1, const void *a2, unsigned int a3, unsigned int a4)
{
  unsigned int v7; // edi
  char v8; // bl
  unsigned int v9; // r14d
  char v10; // r13
  int v11; // r15d
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 result; // rax
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h]
  char v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+64h] [rbp-9Ch]
  _BYTE *v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+74h] [rbp-8Ch]
  int v29; // [rsp+7Ch] [rbp-84h]
  _BYTE v30[1024]; // [rsp+80h] [rbp-80h] BYREF

  v21 = a4;
  v29 = 0;
  v20 = 0;
  v7 = a4;
  memset_0(v30, 0, sizeof(v30));
  if ( a3 > 0x400 )
    return 1026;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  v10 = 1;
  memcpy_0(v30, a2, a3);
  v27 = 1024;
  v24 = 0;
  v23 = 8 * a3;
  v11 = 0;
  v25 = 0;
  v26 = v30;
  v28 = 0x2000;
  v22 = 0;
  while ( 1 )
  {
    if ( v11 >= 2 )
    {
      if ( v20 )
        *(_DWORD *)(a1 + 3872) |= 0x20u;
      return v9;
    }
    if ( v11 > 0 )
    {
      CDKsyncCache_0(&v22);
      CDKpushBack(&v22, 8 * a3 - (unsigned int)v23);
      v10 = 2;
    }
    if ( *(_DWORD *)a1 == 6 || *(_DWORD *)a1 == 7 || *(_DWORD *)a1 == 10 )
      break;
    LOBYTE(v17) = v8;
    v20 = 1;
    LOBYTE(v16) = v10;
    v9 = AudioSpecificConfig_Parse(a1 + 2068, &v22, 1, a1 + 8, v16, v17, 0);
    if ( v9 )
      return v9;
    v12 = 1756LL * v7;
    memcpy_0((void *)(v12 + a1 + 312), (const void *)(a1 + 2068), 0x6DCu);
    LOBYTE(v13) = *(_BYTE *)(v12 + a1 + 1546);
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64))(a1 + 8))(
           *(_QWORD *)(a1 + 16),
           v12 + a1 + 312,
           v13,
           v12 + a1 + 1547) )
    {
      return 1025;
    }
    v8 = v19;
    v7 = v21;
LABEL_17:
    if ( !v11 )
    {
      v15 = 1756LL * v7;
      if ( *(_BYTE *)(v15 + a1 + 1547) || *(_BYTE *)(v15 + a1 + 1548) || *(_BYTE *)(v15 + a1 + 1549) )
      {
        v8 = 1;
        v19 = 1;
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(a1 + 40))(*(_QWORD *)(a1 + 48), v15 + a1 + 312) )
          return 1025;
      }
    }
    ++v11;
  }
  if ( !v7 )
  {
    LOBYTE(v18) = v8;
    LOBYTE(v17) = v10;
    result = CLatmDemux_ReadStreamMuxConfig(&v22, a1 + 192, a1 + 8, a1 + 312, &v20, v17, v18);
    v9 = result;
    if ( (_DWORD)result )
      return result;
    goto LABEL_17;
  }
  return 514;
}

```

## disassembly

```asm
0x180011b10  push    rbp
0x180011b12  push    rbx
0x180011b13  push    rsi
0x180011b14  push    rdi
0x180011b15  push    r12
0x180011b17  push    r13
0x180011b19  push    r14
0x180011b1b  push    r15
0x180011b1d  lea     rbp, [rsp-398h]
0x180011b25  sub     rsp, 498h
0x180011b2c  mov     rax, cs:__security_cookie
0x180011b33  xor     rax, rsp
0x180011b36  mov     [rbp+3D0h+var_50], rax
0x180011b3d  mov     r12d, r8d
0x180011b40  mov     r15, rdx
0x180011b43  mov     rsi, rcx
0x180011b46  mov     [rsp+4D0h+var_488], r9d
0x180011b4b  mov     ebx, 400h
0x180011b50  mov     [rsp+4D0h+var_454], 0
0x180011b58  mov     r8d, ebx; Size
0x180011b5b  mov     [rsp+4D0h+var_48C], 0
0x180011b63  xor     edx, edx; Val
0x180011b65  lea     rcx, [rbp+3D0h+var_450]; void *
0x180011b69  mov     edi, r9d
0x180011b6c  call    memset_0
0x180011b71  cmp     r12d, ebx
0x180011b74  ja      loc_180011D2D
0x180011b7a  xor     bl, bl
0x180011b7c  lea     rcx, [rbp+3D0h+var_450]; void *
0x180011b80  mov     r8d, r12d; Size
0x180011b83  mov     [rsp+4D0h+var_490], bl
0x180011b87  mov     rdx, r15; Src
0x180011b8a  xor     r14d, r14d
0x180011b8d  mov     r13b, 1
0x180011b90  call    memcpy_0
0x180011b95  xor     edx, edx
0x180011b97  mov     [rsp+4D0h+var_460], 400h
0x180011b9f  lea     eax, ds:0[r12*8]
0x180011ba7  mov     [rsp+4D0h+var_474], rdx
0x180011bac  mov     [rsp+4D0h+var_478], eax
0x180011bb0  mov     r15d, edx
0x180011bb3  lea     rax, [rbp+3D0h+var_450]
0x180011bb7  mov     [rsp+4D0h+var_46C], edx
0x180011bbb  mov     [rsp+4D0h+var_468], rax
0x180011bc0  mov     [rsp+4D0h+var_45C], 2000h
0x180011bc9  mov     [rsp+4D0h+var_480], rdx
0x180011bce  cmp     r15d, 2
0x180011bd2  jge     loc_180011CD3
0x180011bd8  test    r15d, r15d
0x180011bdb  jle     short loc_180011C02
0x180011bdd  lea     rcx, [rsp+4D0h+var_480]
0x180011be2  call    CDKsyncCache_0
0x180011be7  lea     edx, ds:0[r12*8]
0x180011bef  sub     edx, [rsp+4D0h+var_478]
0x180011bf3  lea     rcx, [rsp+4D0h+var_480]
0x180011bf8  call    CDKpushBack
0x180011bfd  xor     edx, edx
0x180011bff  mov     r13b, 2
0x180011c02  mov     ecx, [rsi]
0x180011c04  sub     ecx, 6
0x180011c07  jz      loc_180011D37
0x180011c0d  sub     ecx, 1
0x180011c10  jz      loc_180011D37
0x180011c16  cmp     ecx, 3
0x180011c19  jz      loc_180011D37
0x180011c1f  mov     [rsp+4D0h+var_4A0], edx
0x180011c23  lea     r9, [rsi+8]
0x180011c27  mov     r8d, 1
0x180011c2d  mov     [rsp+4D0h+var_4A8], bl
0x180011c31  lea     rdx, [rsp+4D0h+var_480]
0x180011c36  mov     [rsp+4D0h+var_48C], r8d
0x180011c3b  lea     rcx, [rsi+814h]
0x180011c42  mov     byte ptr [rsp+4D0h+var_4B0], r13b
0x180011c47  call    ?AudioSpecificConfig_Parse@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@HPEAUCSTpCallBacks@@EEW4AUDIO_OBJECT_TYPE@@@Z; AudioSpecificConfig_Parse(CSAudioSpecificConfig *,CDK_BITSTREAM *,int,CSTpCallBacks *,uchar,uchar,AUDIO_OBJECT_TYPE)
0x180011c4c  mov     r14d, eax
0x180011c4f  test    eax, eax
0x180011c51  jnz     short loc_180011CAC
0x180011c53  mov     ecx, edi
0x180011c55  lea     rdx, [rsi+814h]; Src
0x180011c5c  imul    rdi, rcx, 6DCh
0x180011c63  mov     r8d, 6DCh; Size
0x180011c69  lea     rbx, [rdi+rsi]
0x180011c6d  lea     rcx, [rbx+138h]; void *
0x180011c74  call    memcpy_0
0x180011c79  mov     r8b, [rdi+rsi+60Ah]
0x180011c81  lea     r9, [rsi+60Bh]
0x180011c88  mov     rcx, [rsi+10h]
0x180011c8c  lea     rdx, [rbx+138h]
0x180011c93  mov     rax, [rsi+8]
0x180011c97  add     r9, rdi
0x180011c9a  call    cs:__guard_dispatch_icall_fptr
0x180011ca0  xor     edx, edx
0x180011ca2  test    eax, eax
0x180011ca4  jz      short loc_180011CE2
0x180011ca6  mov     r14d, 401h
0x180011cac  mov     eax, r14d
0x180011caf  mov     rcx, [rbp+3D0h+var_50]
0x180011cb6  xor     rcx, rsp; StackCookie
0x180011cb9  call    __security_check_cookie
0x180011cbe  add     rsp, 498h
0x180011cc5  pop     r15
0x180011cc7  pop     r14
0x180011cc9  pop     r13
0x180011ccb  pop     r12
0x180011ccd  pop     rdi
0x180011cce  pop     rsi
0x180011ccf  pop     rbx
0x180011cd0  pop     rbp
0x180011cd1  retn
0x180011cd3  cmp     [rsp+4D0h+var_48C], edx
0x180011cd7  jz      short loc_180011CAC
0x180011cd9  or      dword ptr [rsi+0F20h], 20h
0x180011ce0  jmp     short loc_180011CAC
0x180011ce2  mov     bl, [rsp+4D0h+var_490]
0x180011ce6  mov     edi, [rsp+4D0h+var_488]
0x180011cea  test    r15d, r15d
0x180011ced  jnz     short loc_180011D25
0x180011cef  mov     eax, edi
0x180011cf1  imul    rcx, rax, 6DCh
0x180011cf8  cmp     [rcx+rsi+60Bh], dl
0x180011cff  jz      short loc_180011D7C
0x180011d01  mov     rax, [rsi+28h]
0x180011d05  lea     rdx, [rsi+138h]
0x180011d0c  add     rdx, rcx
0x180011d0f  mov     bl, 1
0x180011d11  mov     rcx, [rsi+30h]
0x180011d15  mov     [rsp+4D0h+var_490], bl
0x180011d19  call    cs:__guard_dispatch_icall_fptr
0x180011d1f  xor     edx, edx
0x180011d21  test    eax, eax
0x180011d23  jnz     short loc_180011CA6
0x180011d25  inc     r15d
0x180011d28  jmp     loc_180011BCE
0x180011d2d  mov     eax, 402h
0x180011d32  jmp     loc_180011CAF
0x180011d37  test    edi, edi
0x180011d39  jnz     short loc_180011D97
0x180011d3b  mov     byte ptr [rsp+4D0h+var_4A0], bl
0x180011d3f  lea     rax, [rsp+4D0h+var_48C]
0x180011d44  mov     [rsp+4D0h+var_4A8], r13b
0x180011d49  lea     r9, [rsi+138h]
0x180011d50  lea     r8, [rsi+8]
0x180011d54  mov     [rsp+4D0h+var_4B0], rax
0x180011d59  lea     rdx, [rsi+0C0h]
0x180011d60  lea     rcx, [rsp+4D0h+var_480]
0x180011d65  call    ?CLatmDemux_ReadStreamMuxConfig@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@PEAUCSTpCallBacks@@PEAUCSAudioSpecificConfig@@PEAHEE@Z; CLatmDemux_ReadStreamMuxConfig(CDK_BITSTREAM *,CLatmDemux *,CSTpCallBacks *,CSAudioSpecificConfig *,int *,uchar,uchar)
0x180011d6a  xor     edx, edx
0x180011d6c  mov     r14d, eax
0x180011d6f  test    eax, eax
0x180011d71  jnz     loc_180011CAF
0x180011d77  jmp     loc_180011CEA
0x180011d7c  cmp     [rcx+rsi+60Ch], dl
0x180011d83  jnz     loc_180011D01
0x180011d89  cmp     [rcx+rsi+60Dh], dl
0x180011d90  jz      short loc_180011D25
0x180011d92  jmp     loc_180011D01
0x180011d97  mov     eax, 202h
0x180011d9c  jmp     loc_180011CAF
```
