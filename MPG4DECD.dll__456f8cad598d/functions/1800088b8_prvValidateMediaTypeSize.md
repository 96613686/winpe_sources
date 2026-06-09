# prvValidateMediaTypeSize

- ea: `0x1800088b8`
- end: `0x180008b57`
- name: `prvValidateMediaTypeSize`
- size: `671`
- prototype: `__int64 __fastcall(void *Buf1, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800078c0`
- `0x180007fe0`

## callees

- `0x18000837c`
- `0x1800088b8`
- `0x180020ff9`

## pseudocode

```c
__int64 __fastcall prvValidateMediaTypeSize(void *Buf1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  bool v11; // cf
  unsigned int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // r8d
  unsigned int v16; // r9d
  __int64 v17; // rdi
  int v18; // r10d
  unsigned int v19; // eax
  unsigned int v20; // eax

  v5 = 0;
  if ( memcmp_0(Buf1, &FORMAT_None, 0x10u) && memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
  {
    if ( !memcmp_0(Buf1, &FORMAT_VideoInfo, 0x10u) )
    {
      if ( a2 && a3 >= 0x58 )
      {
        v7 = a3 - 48;
        v8 = a2 + 48;
        return (unsigned int)prvValidateBMIHSize(v8, v7);
      }
      return (unsigned int)-1072875852;
    }
    if ( !memcmp_0(Buf1, &FORMAT_VideoInfo2, 0x10u) )
    {
      if ( a2 && a3 >= 0x70 )
      {
        v7 = a3 - 72;
        v8 = a2 + 72;
        return (unsigned int)prvValidateBMIHSize(v8, v7);
      }
      return (unsigned int)-1072875852;
    }
    if ( !memcmp_0(Buf1, &FORMAT_MPEGVideo, 0x10u) )
    {
      if ( !a2 )
        return (unsigned int)-1072875852;
      if ( a3 < 0x60 )
        return (unsigned int)-1072875852;
      v9 = *(_DWORD *)(a2 + 92);
      if ( v9 > 0x4000 || a3 < v9 + 96 )
        return (unsigned int)-1072875852;
      v8 = a2 + 48;
    }
    else
    {
      if ( memcmp_0(Buf1, &FORMAT_MPEG2Video, 0x10u) )
      {
        if ( !memcmp_0(Buf1, &FORMAT_WaveFormatEx, 0x10u) )
        {
          if ( !a2 || a3 < 0x12 || *(_WORD *)(a2 + 16) > 0x4000u )
            return (unsigned int)-1072875852;
          v11 = a3 < (unsigned int)*(unsigned __int16 *)(a2 + 16) + 18;
        }
        else if ( !memcmp_0(Buf1, &FORMAT_MFVideoFormat, 0x10u) )
        {
          if ( !a2 )
            return (unsigned int)-1072875852;
          if ( a3 < 0xA4 )
            return (unsigned int)-1072875852;
          v12 = *(_DWORD *)a2;
          if ( (unsigned int)(*(_DWORD *)a2 - 164) > 0x3F5C )
            return (unsigned int)-1072875852;
          v13 = *(_DWORD *)(a2 + 164);
          if ( v13 > 0x100 )
            return (unsigned int)-1072875852;
          v14 = 4 * v13 + 164;
          if ( a3 < v14 || v12 < v14 )
            return (unsigned int)-1072875852;
          v11 = a3 < v12;
        }
        else
        {
          if ( memcmp_0(Buf1, &FORMAT_DvInfo, 0x10u) )
          {
            if ( memcmp_0(Buf1, &FORMAT_MPEGStreams, 0x10u) )
              return (unsigned int)-1072873832;
            if ( a2 )
            {
              v15 = 8;
              if ( a3 >= 8 )
              {
                v16 = *(_DWORD *)(a2 + 4);
                if ( v16 <= 0x400 )
                {
                  v17 = a2 + 8;
                  v18 = 0;
                  if ( !v16 )
                    return v5;
                  while ( a3 >= v15 + 96 )
                  {
                    v19 = *(_DWORD *)(v17 + 80);
                    if ( v19 > 0x4000 || a3 < v19 + 96 + v15 )
                      break;
                    ++v18;
                    v20 = (v19 + 103) & 0xFFFFFFF8;
                    v15 += v20;
                    v17 += v20;
                    if ( v18 == v16 )
                      return v5;
                  }
                }
              }
            }
            return (unsigned int)-1072875852;
          }
          if ( !a2 )
            return (unsigned int)-1072875852;
          v11 = a3 < 0x20;
        }
        if ( !v11 )
          return v5;
        return (unsigned int)-1072875852;
      }
      if ( !a2 )
        return (unsigned int)-1072875852;
      if ( a3 < 0x84 )
        return (unsigned int)-1072875852;
      v10 = *(_DWORD *)(a2 + 116);
      if ( v10 > 0x4000 || a3 < v10 + 132 )
        return (unsigned int)-1072875852;
      v8 = a2 + 72;
    }
    v7 = 40;
    return (unsigned int)prvValidateBMIHSize(v8, v7);
  }
  return v5;
}

```

## disassembly

```asm
0x1800088b8  push    rbx
0x1800088ba  push    rbp
0x1800088bb  push    rsi
0x1800088bc  push    rdi
0x1800088bd  push    r14
0x1800088bf  sub     rsp, 20h
0x1800088c3  mov     esi, r8d
0x1800088c6  mov     rdi, rdx
0x1800088c9  xor     ebx, ebx
0x1800088cb  lea     rdx, FORMAT_None; Buf2
0x1800088d2  mov     rbp, rcx
0x1800088d5  lea     r14d, [rbx+10h]
0x1800088d9  mov     r8d, r14d; Size
0x1800088dc  call    memcmp_0
0x1800088e1  test    eax, eax
0x1800088e3  jz      loc_180008B4A
0x1800088e9  mov     r8d, r14d; Size
0x1800088ec  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800088f3  mov     rcx, rbp; Buf1
0x1800088f6  call    memcmp_0
0x1800088fb  test    eax, eax
0x1800088fd  jz      loc_180008B4A
0x180008903  mov     r8d, r14d; Size
0x180008906  lea     rdx, FORMAT_VideoInfo; Buf2
0x18000890d  mov     rcx, rbp; Buf1
0x180008910  call    memcmp_0
0x180008915  test    eax, eax
0x180008917  jnz     short loc_180008937
0x180008919  test    rdi, rdi
0x18000891c  jz      loc_180008A3B
0x180008922  cmp     esi, 58h ; 'X'
0x180008925  jb      loc_180008A3B
0x18000892b  lea     edx, [rsi-30h]
0x18000892e  lea     rcx, [rdi+30h]
0x180008932  jmp     loc_1800089F5
0x180008937  mov     r8, r14; Size
0x18000893a  lea     rdx, FORMAT_VideoInfo2; Buf2
0x180008941  mov     rcx, rbp; Buf1
0x180008944  call    memcmp_0
0x180008949  test    eax, eax
0x18000894b  jnz     short loc_18000896B
0x18000894d  test    rdi, rdi
0x180008950  jz      loc_180008A3B
0x180008956  cmp     esi, 70h ; 'p'
0x180008959  jb      loc_180008A3B
0x18000895f  lea     edx, [rsi-48h]
0x180008962  lea     rcx, [rdi+48h]
0x180008966  jmp     loc_1800089F5
0x18000896b  mov     r8, r14; Size
0x18000896e  lea     rdx, FORMAT_MPEGVideo; Buf2
0x180008975  mov     rcx, rbp; Buf1
0x180008978  call    memcmp_0
0x18000897d  test    eax, eax
0x18000897f  jnz     short loc_1800089B4
0x180008981  test    rdi, rdi
0x180008984  jz      loc_180008A3B
0x18000898a  cmp     esi, 60h ; '`'
0x18000898d  jb      loc_180008A3B
0x180008993  mov     eax, [rdi+5Ch]
0x180008996  mov     edx, 4000h
0x18000899b  cmp     eax, edx
0x18000899d  ja      loc_180008A3B
0x1800089a3  add     eax, 60h ; '`'
0x1800089a6  cmp     esi, eax
0x1800089a8  jb      loc_180008A3B
0x1800089ae  lea     rcx, [rdi+30h]
0x1800089b2  jmp     short loc_1800089F0
0x1800089b4  mov     r8, r14; Size
0x1800089b7  lea     rdx, FORMAT_MPEG2Video; Buf2
0x1800089be  mov     rcx, rbp; Buf1
0x1800089c1  call    memcmp_0
0x1800089c6  test    eax, eax
0x1800089c8  jnz     short loc_180008A01
0x1800089ca  test    rdi, rdi
0x1800089cd  jz      short loc_180008A3B
0x1800089cf  cmp     esi, 84h
0x1800089d5  jb      short loc_180008A3B
0x1800089d7  mov     eax, [rdi+74h]
0x1800089da  mov     edx, 4000h
0x1800089df  cmp     eax, edx
0x1800089e1  ja      short loc_180008A3B
0x1800089e3  add     eax, 84h
0x1800089e8  cmp     esi, eax
0x1800089ea  jb      short loc_180008A3B
0x1800089ec  lea     rcx, [rdi+48h]
0x1800089f0  mov     edx, 28h ; '('
0x1800089f5  call    prvValidateBMIHSize
0x1800089fa  mov     ebx, eax
0x1800089fc  jmp     loc_180008B4A
0x180008a01  mov     r8, r14; Size
0x180008a04  lea     rdx, FORMAT_WaveFormatEx; Buf2
0x180008a0b  mov     rcx, rbp; Buf1
0x180008a0e  call    memcmp_0
0x180008a13  test    eax, eax
0x180008a15  jnz     short loc_180008A45
0x180008a17  test    rdi, rdi
0x180008a1a  jz      short loc_180008A3B
0x180008a1c  cmp     esi, 12h
0x180008a1f  jb      short loc_180008A3B
0x180008a21  mov     edx, 4000h
0x180008a26  cmp     [rdi+10h], dx
0x180008a2a  ja      short loc_180008A3B
0x180008a2c  movzx   eax, word ptr [rdi+10h]
0x180008a30  add     eax, 12h
0x180008a33  cmp     esi, eax
0x180008a35  jnb     loc_180008B4A
0x180008a3b  mov     ebx, 0C00D36B4h
0x180008a40  jmp     loc_180008B4A
0x180008a45  mov     r8, r14; Size
0x180008a48  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x180008a4f  mov     rcx, rbp; Buf1
0x180008a52  call    memcmp_0
0x180008a57  test    eax, eax
0x180008a59  jnz     short loc_180008A97
0x180008a5b  test    rdi, rdi
0x180008a5e  jz      short loc_180008A3B
0x180008a60  cmp     esi, 0A4h
0x180008a66  jb      short loc_180008A3B
0x180008a68  mov     ecx, [rdi]
0x180008a6a  lea     eax, [rcx-0A4h]
0x180008a70  cmp     eax, 3F5Ch
0x180008a75  ja      short loc_180008A3B
0x180008a77  mov     eax, [rdi+0A4h]
0x180008a7d  cmp     eax, 100h
0x180008a82  ja      short loc_180008A3B
0x180008a84  lea     eax, ds:0A4h[rax*4]
0x180008a8b  cmp     esi, eax
0x180008a8d  jb      short loc_180008A3B
0x180008a8f  cmp     ecx, eax
0x180008a91  jb      short loc_180008A3B
0x180008a93  cmp     esi, ecx
0x180008a95  jmp     short loc_180008A35
0x180008a97  mov     r8, r14; Size
0x180008a9a  lea     rdx, FORMAT_DvInfo; Buf2
0x180008aa1  mov     rcx, rbp; Buf1
0x180008aa4  call    memcmp_0
0x180008aa9  test    eax, eax
0x180008aab  jnz     short loc_180008ABA
0x180008aad  test    rdi, rdi
0x180008ab0  jz      short loc_180008A3B
0x180008ab2  cmp     esi, 20h ; ' '
0x180008ab5  jmp     loc_180008A35
0x180008aba  mov     r8, r14; Size
0x180008abd  lea     rdx, FORMAT_MPEGStreams; Buf2
0x180008ac4  mov     rcx, rbp; Buf1
0x180008ac7  call    memcmp_0
0x180008acc  test    eax, eax
0x180008ace  jnz     short loc_180008B45
0x180008ad0  test    rdi, rdi
0x180008ad3  jz      loc_180008A3B
0x180008ad9  lea     r8d, [rax+8]
0x180008add  cmp     esi, r8d
0x180008ae0  jb      loc_180008A3B
0x180008ae6  mov     r9d, [rdi+4]
0x180008aea  cmp     r9d, 400h
0x180008af1  ja      loc_180008A3B
0x180008af7  add     rdi, r8
0x180008afa  xor     r10d, r10d
0x180008afd  test    r9d, r9d
0x180008b00  jz      short loc_180008B4A
0x180008b02  mov     edx, 4000h
0x180008b07  lea     eax, [r8+60h]
0x180008b0b  cmp     esi, eax
0x180008b0d  jb      loc_180008A3B
0x180008b13  mov     eax, [rdi+50h]
0x180008b16  cmp     eax, edx
0x180008b18  ja      loc_180008A3B
0x180008b1e  lea     ecx, [rax+60h]
0x180008b21  lea     eax, [rcx+r8]
0x180008b25  cmp     esi, eax
0x180008b27  jb      loc_180008A3B
0x180008b2d  lea     eax, [rcx+7]
0x180008b30  inc     r10d
0x180008b33  and     eax, 0FFFFFFF8h
0x180008b36  mov     ecx, eax
0x180008b38  add     r8d, eax
0x180008b3b  add     rdi, rcx
0x180008b3e  cmp     r10d, r9d
0x180008b41  jnz     short loc_180008B07
0x180008b43  jmp     short loc_180008B4A
0x180008b45  mov     ebx, 0C00D3E98h
0x180008b4a  mov     eax, ebx
0x180008b4c  add     rsp, 20h
0x180008b50  pop     r14
0x180008b52  pop     rdi
0x180008b53  pop     rsi
0x180008b54  pop     rbp
0x180008b55  pop     rbx
0x180008b56  retn
```
