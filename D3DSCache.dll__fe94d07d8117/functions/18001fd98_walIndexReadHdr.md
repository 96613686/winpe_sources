# walIndexReadHdr

- ea: `0x18001fd98`
- end: `0x18002007f`
- name: `walIndexReadHdr`
- size: `743`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180031db0`
- `0x180090390`

## callees

- `0x18001fbf8`
- `0x18001fd3c`
- `0x18001fd98`
- `0x180020088`
- `0x180020188`
- `0x180033a24`
- `0x18003680c`
- `0x180036e80`
- `0x18003a860`
- `0x1800449f0`
- `0x18009fe4c`
- `0x18009febc`
- `0x1800a0614`
- `0x1800a0a34`
- `0x1800a6cfc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe0c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe0c`

## string_xrefs

- `0x180020010`: `cannot open file`

## pseudocode

```c
__int64 __fastcall walIndexReadHdr(__int64 a1, _DWORD *a2)
{
  int v2; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  bool v7; // zf
  __m128i **v8; // rax
  __m128i *v9; // rsi
  __m128i v10; // xmm6
  __m128i v11; // xmm0
  __m128i v12; // xmm1
  __m128i v13; // xmm1
  __m128i v14; // xmm0
  __int128 v15; // xmm0
  __m128i v16; // xmm1
  __m128i v17; // xmm0
  int v18; // esi
  char v19; // r14
  __int64 v20; // [rsp+38h] [rbp-59h] BYREF
  __int64 v21; // [rsp+40h] [rbp-51h] BYREF
  _OWORD Buf2[3]; // [rsp+48h] [rbp-49h] BYREF
  ULONG_PTR Arguments[2]; // [rsp+78h] [rbp-19h] BYREF
  __m128i v24; // [rsp+88h] [rbp-9h]
  __m128i v25; // [rsp+98h] [rbp+7h]

  v2 = (int)qword_1800C6B00;
  v20 = 0;
  if ( qword_1800C6B00 )
    v2 = qword_1800C6B00(650);
  if ( v2 )
  {
    v24.m128i_i64[0] = v2;
    *(_OWORD *)Arguments = 0;
    RaiseException(0xC0000006, 0, 3u, Arguments);
  }
  if ( *(int *)(a1 + 40) > 0 && (v20 = **(_QWORD **)(a1 + 48)) != 0 )
  {
    v5 = 0;
  }
  else
  {
    result = walIndexPageRealloc(a1, 0, &v20);
    v5 = result;
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result != 1288 )
        return result;
      *(_BYTE *)(a1 + 70) = 1;
      *(_BYTE *)(a1 + 63) = 2;
      *a2 = 1;
    }
  }
  if ( v20 )
  {
    sehInjectFault();
    v7 = *(_BYTE *)(a1 + 63) == 2;
    v8 = *(__m128i ***)(a1 + 48);
    v9 = *v8;
    v10 = **v8;
    v11 = (*v8)[1];
    v12 = (*v8)[2];
    *(__m128i *)Arguments = v10;
    v24 = v11;
    v25 = v12;
    if ( !v7 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 120LL))(*(_QWORD *)(a1 + 8));
    v13 = v9[4];
    Buf2[0] = v9[3];
    v14 = v9[5];
    Buf2[1] = v13;
    Buf2[2] = v14;
    if ( !memcmp_0(Arguments, Buf2, 0x30u)
      && (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 12))
      && (walChecksumBytes(1, (unsigned int)Arguments, 40, 0, (__int64)&v21), v21 == v25.m128i_i64[1]) )
    {
      if ( memcmp_0((const void *)(a1 + 72), Arguments, 0x30u) )
      {
        v15 = *(_OWORD *)Arguments;
        *a2 = 1;
        v16 = v24;
        *(_OWORD *)(a1 + 72) = v15;
        v17 = v25;
        *(__m128i *)(a1 + 88) = v16;
        *(__m128i *)(a1 + 104) = v17;
        *(_DWORD *)(a1 + 56) = (*(_WORD *)(a1 + 86) & 0xFE00) + ((*(_WORD *)(a1 + 86) & 1) << 16);
      }
      v18 = 0;
    }
    else
    {
      v18 = 1;
    }
    if ( !v18 )
      goto LABEL_36;
  }
  else
  {
    v18 = 1;
  }
  if ( !*(_BYTE *)(a1 + 70) && (*(_BYTE *)(a1 + 66) & 2) != 0 )
  {
    v5 = walLockShared(a1, 0);
    if ( !v5 )
    {
      walUnlockShared(a1, 0);
      v5 = 264;
    }
    goto LABEL_38;
  }
  v19 = *(_BYTE *)(a1 + 64);
  if ( !v19 )
  {
    v5 = walLockExclusive(a1, 0, 1);
    if ( v5 )
      goto LABEL_38;
  }
  *(_BYTE *)(a1 + 64) = 1;
  v5 = walIndexPage(a1, 0, &v20);
  if ( !v5 )
  {
    v18 = walIndexTryHdr(a1, a2);
    if ( v18 )
    {
      v5 = walIndexRecover(a1);
      *a2 = 1;
    }
  }
  if ( !v19 )
  {
    *(_BYTE *)(a1 + 64) = 0;
    walUnlockExclusive(a1, 0, 1);
  }
  if ( v18 )
    goto LABEL_38;
LABEL_36:
  if ( *(_DWORD *)(a1 + 72) != 3007000 )
    v5 = sqlite3ReportError(14, 67624, "cannot open file");
LABEL_38:
  if ( *(_BYTE *)(a1 + 70) )
  {
    if ( v5 )
    {
      walIndexClose(a1, 0);
      *(_BYTE *)(a1 + 70) = 0;
      if ( v5 == 522 )
        v5 = -1;
    }
    *(_BYTE *)(a1 + 63) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001fd98  mov     rax, rsp
0x18001fd9b  mov     [rax+18h], rbx
0x18001fd9f  mov     [rax+20h], rsi
0x18001fda3  push    rbp
0x18001fda4  push    rdi
0x18001fda5  push    r13
0x18001fda7  push    r14
0x18001fda9  push    r15
0x18001fdab  lea     rbp, [rax-5Fh]
0x18001fdaf  sub     rsp, 0C0h
0x18001fdb6  movaps  xmmword ptr [rax-38h], xmm6
0x18001fdba  mov     rax, cs:__security_cookie
0x18001fdc1  xor     rax, rsp
0x18001fdc4  mov     [rbp+57h+var_40], rax
0x18001fdc8  mov     rax, cs:qword_1800C6B00
0x18001fdcf  mov     r15, rdx
0x18001fdd2  mov     [rbp+57h+var_B0], 0
0x18001fdda  mov     rbx, rcx
0x18001fddd  test    rax, rax
0x18001fde0  jz      short loc_18001FDEC
0x18001fde2  mov     ecx, 28Ah
0x18001fde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdec  test    eax, eax
0x18001fdee  jz      short loc_18001FE12
0x18001fdf0  xor     edx, edx; dwExceptionFlags
0x18001fdf2  cdqe
0x18001fdf4  xorps   xmm0, xmm0
0x18001fdf7  mov     qword ptr [rbp+57h+var_60], rax
0x18001fdfb  lea     r9, [rbp+57h+Arguments]; lpArguments
0x18001fdff  mov     ecx, 0C0000006h; dwExceptionCode
0x18001fe04  movups  xmmword ptr [rbp+57h+Arguments], xmm0
0x18001fe08  lea     r8d, [rdx+3]; nNumberOfArguments
0x18001fe0c  call    cs:__imp_RaiseException
0x18001fe12  cmp     dword ptr [rbx+28h], 0
0x18001fe16  mov     r13d, 1
0x18001fe1c  jle     short loc_18001FE32
0x18001fe1e  mov     rax, [rbx+30h]
0x18001fe22  mov     rcx, [rax]
0x18001fe25  mov     [rbp+57h+var_B0], rcx
0x18001fe29  test    rcx, rcx
0x18001fe2c  jz      short loc_18001FE32
0x18001fe2e  xor     edi, edi
0x18001fe30  jmp     short loc_18001FE5C
0x18001fe32  lea     r8, [rbp+57h+var_B0]
0x18001fe36  xor     edx, edx
0x18001fe38  mov     rcx, rbx
0x18001fe3b  call    walIndexPageRealloc
0x18001fe40  mov     edi, eax
0x18001fe42  test    eax, eax
0x18001fe44  jz      short loc_18001FE5C
0x18001fe46  cmp     eax, 508h
0x18001fe4b  jnz     loc_180020052
0x18001fe51  mov     [rbx+46h], r13b
0x18001fe55  mov     byte ptr [rbx+3Fh], 2
0x18001fe59  mov     [r15], r13d
0x18001fe5c  cmp     [rbp+57h+var_B0], 0
0x18001fe61  jz      loc_18001FF64
0x18001fe67  call    sehInjectFault
0x18001fe6c  cmp     byte ptr [rbx+3Fh], 2
0x18001fe70  mov     rax, [rbx+30h]
0x18001fe74  mov     rsi, [rax]
0x18001fe77  movups  xmm6, xmmword ptr [rsi]
0x18001fe7a  movups  xmm0, xmmword ptr [rsi+10h]
0x18001fe7e  movups  xmm1, xmmword ptr [rsi+20h]
0x18001fe82  movups  xmmword ptr [rbp+57h+Arguments], xmm6
0x18001fe86  movups  [rbp+57h+var_60], xmm0
0x18001fe8a  movups  [rbp+57h+var_50], xmm1
0x18001fe8e  jz      short loc_18001FEA0
0x18001fe90  mov     rcx, [rbx+8]
0x18001fe94  mov     rax, [rcx]
0x18001fe97  mov     rax, [rax+78h]
0x18001fe9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea0  movups  xmm0, xmmword ptr [rsi+30h]
0x18001fea4  mov     r14d, 30h ; '0'
0x18001feaa  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001feae  movups  xmm1, xmmword ptr [rsi+40h]
0x18001feb2  mov     r8d, r14d; Size
0x18001feb5  lea     rcx, [rbp+57h+Arguments]; Buf1
0x18001feb9  movups  [rbp+57h+Buf2], xmm0
0x18001febd  movups  xmm0, xmmword ptr [rsi+50h]
0x18001fec1  movups  [rbp+57h+var_90], xmm1
0x18001fec5  movups  [rbp+57h+var_80], xmm0
0x18001fec9  call    memcmp_0
0x18001fece  test    eax, eax
0x18001fed0  jnz     loc_18001FF58
0x18001fed6  psrldq  xmm6, 0Ch
0x18001fedb  movd    eax, xmm6
0x18001fedf  test    al, al
0x18001fee1  jz      short loc_18001FF58
0x18001fee3  lea     rax, [rbp+57h+var_A8]
0x18001fee7  xor     r9d, r9d
0x18001feea  lea     r8d, [r14-8]
0x18001feee  mov     [rsp+0E0h+var_C0], rax
0x18001fef3  lea     rdx, [rbp+57h+Arguments]
0x18001fef7  mov     ecx, r13d
0x18001fefa  call    walChecksumBytes
0x18001feff  mov     eax, dword ptr [rbp+57h+var_50+8]
0x18001ff02  cmp     dword ptr [rbp+57h+var_A8], eax
0x18001ff05  jnz     short loc_18001FF58
0x18001ff07  mov     eax, dword ptr [rbp+57h+var_50+0Ch]
0x18001ff0a  cmp     dword ptr [rbp+57h+var_A8+4], eax
0x18001ff0d  jnz     short loc_18001FF58
0x18001ff0f  mov     r8d, r14d; Size
0x18001ff12  lea     rdx, [rbp+57h+Arguments]; Buf2
0x18001ff16  lea     rcx, [rbx+48h]; Buf1
0x18001ff1a  call    memcmp_0
0x18001ff1f  test    eax, eax
0x18001ff21  jz      short loc_18001FF54
0x18001ff23  movups  xmm0, xmmword ptr [rbp+57h+Arguments]
0x18001ff27  mov     [r15], r13d
0x18001ff2a  movups  xmm1, [rbp+57h+var_60]
0x18001ff2e  movups  xmmword ptr [rbx+48h], xmm0
0x18001ff32  movups  xmm0, [rbp+57h+var_50]
0x18001ff36  movups  xmmword ptr [rbx+58h], xmm1
0x18001ff3a  movups  xmmword ptr [rbx+68h], xmm0
0x18001ff3e  movzx   eax, word ptr [rbx+56h]
0x18001ff42  mov     ecx, eax
0x18001ff44  and     eax, 0FE00h
0x18001ff49  and     ecx, r13d
0x18001ff4c  shl     ecx, 10h
0x18001ff4f  add     ecx, eax
0x18001ff51  mov     [rbx+38h], ecx
0x18001ff54  xor     esi, esi
0x18001ff56  jmp     short loc_18001FF5B
0x18001ff58  mov     esi, r13d
0x18001ff5b  test    esi, esi
0x18001ff5d  jnz     short loc_18001FF67
0x18001ff5f  jmp     loc_180020007
0x18001ff64  mov     esi, r13d
0x18001ff67  cmp     byte ptr [rbx+46h], 0
0x18001ff6b  jnz     short loc_18001FF9B
0x18001ff6d  test    byte ptr [rbx+42h], 2
0x18001ff71  jz      short loc_18001FF9B
0x18001ff73  xor     edx, edx
0x18001ff75  mov     rcx, rbx
0x18001ff78  call    walLockShared
0x18001ff7d  mov     edi, eax
0x18001ff7f  test    eax, eax
0x18001ff81  jnz     loc_180020028
0x18001ff87  xor     edx, edx
0x18001ff89  mov     rcx, rbx
0x18001ff8c  call    walUnlockShared
0x18001ff91  mov     edi, 108h
0x18001ff96  jmp     loc_180020028
0x18001ff9b  mov     r14b, [rbx+40h]
0x18001ff9f  test    r14b, r14b
0x18001ffa2  jnz     short loc_18001FFB7
0x18001ffa4  mov     r8d, r13d
0x18001ffa7  xor     edx, edx
0x18001ffa9  mov     rcx, rbx
0x18001ffac  call    walLockExclusive
0x18001ffb1  mov     edi, eax
0x18001ffb3  test    eax, eax
0x18001ffb5  jnz     short loc_180020028
0x18001ffb7  lea     r8, [rbp+57h+var_B0]
0x18001ffbb  mov     [rbx+40h], r13b
0x18001ffbf  xor     edx, edx
0x18001ffc1  mov     rcx, rbx
0x18001ffc4  call    walIndexPage
0x18001ffc9  mov     edi, eax
0x18001ffcb  test    eax, eax
0x18001ffcd  jnz     short loc_18001FFED
0x18001ffcf  mov     rdx, r15
0x18001ffd2  mov     rcx, rbx
0x18001ffd5  call    walIndexTryHdr
0x18001ffda  mov     esi, eax
0x18001ffdc  test    eax, eax
0x18001ffde  jz      short loc_18001FFED
0x18001ffe0  mov     rcx, rbx
0x18001ffe3  call    walIndexRecover
0x18001ffe8  mov     edi, eax
0x18001ffea  mov     [r15], r13d
0x18001ffed  test    r14b, r14b
0x18001fff0  jnz     short loc_180020003
0x18001fff2  mov     r8d, r13d
0x18001fff5  mov     [rbx+40h], r14b
0x18001fff9  xor     edx, edx
0x18001fffb  mov     rcx, rbx
0x18001fffe  call    walUnlockExclusive
0x180020003  test    esi, esi
0x180020005  jnz     short loc_180020028
0x180020007  cmp     dword ptr [rbx+48h], 2DE218h
0x18002000e  jz      short loc_180020028
0x180020010  lea     r8, aCannotOpenFile; "cannot open file"
0x180020017  mov     edx, 10828h
0x18002001c  mov     ecx, 0Eh
0x180020021  call    sqlite3ReportError
0x180020026  mov     edi, eax
0x180020028  cmp     byte ptr [rbx+46h], 0
0x18002002c  jz      short loc_180020050
0x18002002e  test    edi, edi
0x180020030  jz      short loc_18002004C
0x180020032  xor     edx, edx
0x180020034  mov     rcx, rbx
0x180020037  call    walIndexClose
0x18002003c  or      eax, 0FFFFFFFFh
0x18002003f  mov     byte ptr [rbx+46h], 0
0x180020043  cmp     edi, 20Ah
0x180020049  cmovz   edi, eax
0x18002004c  mov     byte ptr [rbx+3Fh], 0
0x180020050  mov     eax, edi
0x180020052  mov     rcx, [rbp+57h+var_40]
0x180020056  xor     rcx, rsp; StackCookie
0x180020059  call    __security_check_cookie
0x18002005e  lea     r11, [rsp+0E0h+var_20]
0x180020066  mov     rbx, [r11+40h]
0x18002006a  mov     rsi, [r11+48h]
0x18002006e  movaps  xmm6, xmmword ptr [r11-10h]
0x180020073  mov     rsp, r11
0x180020076  pop     r15
0x180020078  pop     r14
0x18002007a  pop     r13
0x18002007c  pop     rdi
0x18002007d  pop     rbp
0x18002007e  retn
```
