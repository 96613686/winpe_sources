# prvValidateMediaTypeSize

- ea: `0x1800087f8`
- end: `0x180008a97`
- name: `prvValidateMediaTypeSize`
- size: `671`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007800`
- `0x180007f20`

## callees

- `0x1800082bc`
- `0x1800087f8`
- `0x180020f39`

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
0x1800087f8  push    rbx
0x1800087fa  push    rbp
0x1800087fb  push    rsi
0x1800087fc  push    rdi
0x1800087fd  push    r14
0x1800087ff  sub     rsp, 20h
0x180008803  mov     esi, r8d
0x180008806  mov     rdi, rdx
0x180008809  xor     ebx, ebx
0x18000880b  lea     rdx, FORMAT_None; Buf2
0x180008812  mov     rbp, rcx
0x180008815  lea     r14d, [rbx+10h]
0x180008819  mov     r8d, r14d; Size
0x18000881c  call    memcmp_0
0x180008821  test    eax, eax
0x180008823  jz      loc_180008A8A
0x180008829  mov     r8d, r14d; Size
0x18000882c  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180008833  mov     rcx, rbp; Buf1
0x180008836  call    memcmp_0
0x18000883b  test    eax, eax
0x18000883d  jz      loc_180008A8A
0x180008843  mov     r8d, r14d; Size
0x180008846  lea     rdx, FORMAT_VideoInfo; Buf2
0x18000884d  mov     rcx, rbp; Buf1
0x180008850  call    memcmp_0
0x180008855  test    eax, eax
0x180008857  jnz     short loc_180008877
0x180008859  test    rdi, rdi
0x18000885c  jz      loc_18000897B
0x180008862  cmp     esi, 58h ; 'X'
0x180008865  jb      loc_18000897B
0x18000886b  lea     edx, [rsi-30h]
0x18000886e  lea     rcx, [rdi+30h]
0x180008872  jmp     loc_180008935
0x180008877  mov     r8, r14; Size
0x18000887a  lea     rdx, FORMAT_VideoInfo2; Buf2
0x180008881  mov     rcx, rbp; Buf1
0x180008884  call    memcmp_0
0x180008889  test    eax, eax
0x18000888b  jnz     short loc_1800088AB
0x18000888d  test    rdi, rdi
0x180008890  jz      loc_18000897B
0x180008896  cmp     esi, 70h ; 'p'
0x180008899  jb      loc_18000897B
0x18000889f  lea     edx, [rsi-48h]
0x1800088a2  lea     rcx, [rdi+48h]
0x1800088a6  jmp     loc_180008935
0x1800088ab  mov     r8, r14; Size
0x1800088ae  lea     rdx, FORMAT_MPEGVideo; Buf2
0x1800088b5  mov     rcx, rbp; Buf1
0x1800088b8  call    memcmp_0
0x1800088bd  test    eax, eax
0x1800088bf  jnz     short loc_1800088F4
0x1800088c1  test    rdi, rdi
0x1800088c4  jz      loc_18000897B
0x1800088ca  cmp     esi, 60h ; '`'
0x1800088cd  jb      loc_18000897B
0x1800088d3  mov     eax, [rdi+5Ch]
0x1800088d6  mov     edx, 4000h
0x1800088db  cmp     eax, edx
0x1800088dd  ja      loc_18000897B
0x1800088e3  add     eax, 60h ; '`'
0x1800088e6  cmp     esi, eax
0x1800088e8  jb      loc_18000897B
0x1800088ee  lea     rcx, [rdi+30h]
0x1800088f2  jmp     short loc_180008930
0x1800088f4  mov     r8, r14; Size
0x1800088f7  lea     rdx, FORMAT_MPEG2Video; Buf2
0x1800088fe  mov     rcx, rbp; Buf1
0x180008901  call    memcmp_0
0x180008906  test    eax, eax
0x180008908  jnz     short loc_180008941
0x18000890a  test    rdi, rdi
0x18000890d  jz      short loc_18000897B
0x18000890f  cmp     esi, 84h
0x180008915  jb      short loc_18000897B
0x180008917  mov     eax, [rdi+74h]
0x18000891a  mov     edx, 4000h
0x18000891f  cmp     eax, edx
0x180008921  ja      short loc_18000897B
0x180008923  add     eax, 84h
0x180008928  cmp     esi, eax
0x18000892a  jb      short loc_18000897B
0x18000892c  lea     rcx, [rdi+48h]
0x180008930  mov     edx, 28h ; '('
0x180008935  call    prvValidateBMIHSize
0x18000893a  mov     ebx, eax
0x18000893c  jmp     loc_180008A8A
0x180008941  mov     r8, r14; Size
0x180008944  lea     rdx, FORMAT_WaveFormatEx; Buf2
0x18000894b  mov     rcx, rbp; Buf1
0x18000894e  call    memcmp_0
0x180008953  test    eax, eax
0x180008955  jnz     short loc_180008985
0x180008957  test    rdi, rdi
0x18000895a  jz      short loc_18000897B
0x18000895c  cmp     esi, 12h
0x18000895f  jb      short loc_18000897B
0x180008961  mov     edx, 4000h
0x180008966  cmp     [rdi+10h], dx
0x18000896a  ja      short loc_18000897B
0x18000896c  movzx   eax, word ptr [rdi+10h]
0x180008970  add     eax, 12h
0x180008973  cmp     esi, eax
0x180008975  jnb     loc_180008A8A
0x18000897b  mov     ebx, 0C00D36B4h
0x180008980  jmp     loc_180008A8A
0x180008985  mov     r8, r14; Size
0x180008988  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x18000898f  mov     rcx, rbp; Buf1
0x180008992  call    memcmp_0
0x180008997  test    eax, eax
0x180008999  jnz     short loc_1800089D7
0x18000899b  test    rdi, rdi
0x18000899e  jz      short loc_18000897B
0x1800089a0  cmp     esi, 0A4h
0x1800089a6  jb      short loc_18000897B
0x1800089a8  mov     ecx, [rdi]
0x1800089aa  lea     eax, [rcx-0A4h]
0x1800089b0  cmp     eax, 3F5Ch
0x1800089b5  ja      short loc_18000897B
0x1800089b7  mov     eax, [rdi+0A4h]
0x1800089bd  cmp     eax, 100h
0x1800089c2  ja      short loc_18000897B
0x1800089c4  lea     eax, ds:0A4h[rax*4]
0x1800089cb  cmp     esi, eax
0x1800089cd  jb      short loc_18000897B
0x1800089cf  cmp     ecx, eax
0x1800089d1  jb      short loc_18000897B
0x1800089d3  cmp     esi, ecx
0x1800089d5  jmp     short loc_180008975
0x1800089d7  mov     r8, r14; Size
0x1800089da  lea     rdx, FORMAT_DvInfo; Buf2
0x1800089e1  mov     rcx, rbp; Buf1
0x1800089e4  call    memcmp_0
0x1800089e9  test    eax, eax
0x1800089eb  jnz     short loc_1800089FA
0x1800089ed  test    rdi, rdi
0x1800089f0  jz      short loc_18000897B
0x1800089f2  cmp     esi, 20h ; ' '
0x1800089f5  jmp     loc_180008975
0x1800089fa  mov     r8, r14; Size
0x1800089fd  lea     rdx, FORMAT_MPEGStreams; Buf2
0x180008a04  mov     rcx, rbp; Buf1
0x180008a07  call    memcmp_0
0x180008a0c  test    eax, eax
0x180008a0e  jnz     short loc_180008A85
0x180008a10  test    rdi, rdi
0x180008a13  jz      loc_18000897B
0x180008a19  lea     r8d, [rax+8]
0x180008a1d  cmp     esi, r8d
0x180008a20  jb      loc_18000897B
0x180008a26  mov     r9d, [rdi+4]
0x180008a2a  cmp     r9d, 400h
0x180008a31  ja      loc_18000897B
0x180008a37  add     rdi, r8
0x180008a3a  xor     r10d, r10d
0x180008a3d  test    r9d, r9d
0x180008a40  jz      short loc_180008A8A
0x180008a42  mov     edx, 4000h
0x180008a47  lea     eax, [r8+60h]
0x180008a4b  cmp     esi, eax
0x180008a4d  jb      loc_18000897B
0x180008a53  mov     eax, [rdi+50h]
0x180008a56  cmp     eax, edx
0x180008a58  ja      loc_18000897B
0x180008a5e  lea     ecx, [rax+60h]
0x180008a61  lea     eax, [rcx+r8]
0x180008a65  cmp     esi, eax
0x180008a67  jb      loc_18000897B
0x180008a6d  lea     eax, [rcx+7]
0x180008a70  inc     r10d
0x180008a73  and     eax, 0FFFFFFF8h
0x180008a76  mov     ecx, eax
0x180008a78  add     r8d, eax
0x180008a7b  add     rdi, rcx
0x180008a7e  cmp     r10d, r9d
0x180008a81  jnz     short loc_180008A47
0x180008a83  jmp     short loc_180008A8A
0x180008a85  mov     ebx, 0C00D3E98h
0x180008a8a  mov     eax, ebx
0x180008a8c  add     rsp, 20h
0x180008a90  pop     r14
0x180008a92  pop     rdi
0x180008a93  pop     rsi
0x180008a94  pop     rbp
0x180008a95  pop     rbx
0x180008a96  retn
```
