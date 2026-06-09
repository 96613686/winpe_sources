# BWritePfbToOutput

- ea: `0x18000f998`
- end: `0x18000fced`
- name: `BWritePfbToOutput`
- size: `853`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ee40`
- `0x18000f51c`

## callees

- `0x180001ee0`
- `0x18000f998`
- `0x180016940`
- `0x180016edc`
- `0x18001aa48`
- `0x18001adb0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fc33`
- `KERNEL32!SetLastError` at `0x18000fc7a`
- `KERNEL32!SetLastError` at `0x18000fc33`
- `KERNEL32!SetLastError` at `0x18000fc7a`
- `KERNEL32!LocalFree` at `0x18000fc49`
- `KERNEL32!LocalFree` at `0x18000fc49`
- `KERNEL32!LocalAlloc` at `0x18000fb2c`
- `KERNEL32!LocalAlloc` at `0x18000fb2c`

## pseudocode

```c
__int64 __fastcall BWritePfbToOutput(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v3; // eax
  int v6; // ebx
  const char *v7; // r14
  unsigned __int64 v8; // rbp
  __int64 v9; // r15
  const char *v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  unsigned __int64 v14; // r12
  char *v15; // rax
  char v16; // r15
  char *v17; // r14
  unsigned int v18; // ebx
  _BYTE *v19; // rax
  _BYTE *v20; // r8
  unsigned int v21; // ecx
  char v22; // al
  unsigned int v23; // edx
  char v24; // al
  unsigned int v25; // ecx
  _BYTE *hMem; // [rsp+30h] [rbp-F8h]
  char v28[160]; // [rsp+40h] [rbp-E8h] BYREF

  v3 = *(_DWORD *)(a2 + 392);
  *a3 = v3;
  if ( !v3 )
    return 0;
  v6 = *(_DWORD *)(a2 + 416);
  v7 = (const char *)(a2 + 48);
  v8 = *(_QWORD *)(a2 + 400);
  v9 = *(unsigned int *)(a2 + 392);
  v10 = "\r\n%%%%IncludeResource: %s %s\r\n";
  v11 = 1;
  if ( !v6 )
    v10 = "\r\n%%%%BeginResource: %s %s\r\n";
  DSCSend(a1, v10, "font", v7);
  RESIncludeOrDefineResource(a1, 1, **(unsigned int **)(a1 + 3536), v7, v6 == 0);
  if ( (*(_DWORD *)(a1 + 3564) & 0x400000) != 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v7[v12] );
    if ( v12 < 0x80 )
    {
      v13 = OPSprintf(v28, 148, "/%s findfont pop\n", v7);
      v11 = OPRawPortWrite(a1, v28, v13);
      if ( !v11 )
        return v11;
      goto LABEL_9;
    }
    return 0;
  }
LABEL_9:
  v14 = v9 + v8;
  while ( v8 < v14 && !*(_DWORD *)(a2 + 416) )
  {
    if ( *(_BYTE *)v8 != 0x80 )
      goto LABEL_51;
    v15 = (char *)(v8 + 1);
    if ( v8 + 1 >= v14 )
      goto LABEL_51;
    v16 = *v15;
    if ( *v15 == 3 )
      break;
    v17 = (char *)(v8 + 6);
    if ( v8 + 6 >= v14
      || (v18 = *(unsigned __int8 *)(v8 + 2)
              | ((*(unsigned __int8 *)(v8 + 3) | (*(unsigned __int16 *)(v8 + 4) << 8)) << 8),
          v18 >= *(_DWORD *)(a2 + 392))
      || (unsigned __int64)&v17[v18] >= v14 )
    {
LABEL_51:
      if ( !*(_DWORD *)(a1 + 3440) )
      {
        *(_DWORD *)(a1 + 3440) = 1;
        SetLastError(0xDu);
      }
      return 0;
    }
    v19 = LocalAlloc(0, 4 * v18);
    v20 = v19;
    if ( !v19 )
      return 0;
    hMem = v19;
    if ( v16 == 1 )
    {
      v21 = 0;
      if ( v18 )
      {
        do
        {
          v22 = *v17++;
          *v20++ = v22;
          if ( v22 == 13 )
            *v20++ = 10;
          ++v21;
        }
        while ( v21 < v18 );
        goto LABEL_35;
      }
    }
    else
    {
      if ( v16 != 2 )
      {
        if ( !*(_DWORD *)(a1 + 3440) )
        {
          *(_DWORD *)(a1 + 3440) = 1;
          SetLastError(0xDu);
        }
        v11 = 0;
        goto LABEL_40;
      }
      if ( *(_WORD *)(a1 + 166) )
      {
        v25 = 1;
        if ( v18 )
        {
          do
          {
            ++v25;
            *v20++ = *v17++;
          }
          while ( v25 <= v18 );
LABEL_35:
          v19 = hMem;
        }
      }
      else
      {
        v23 = 1;
        if ( v18 )
        {
          do
          {
            *v20 = *((_BYTE *)ghexBytes + ((unsigned __int64)(unsigned __int8)*v17 >> 4));
            v24 = *v17++;
            v20[1] = *((_BYTE *)ghexBytes + (v24 & 0xF));
            v20 += 2;
            if ( (v23 & 0x1F) == 0 || v23 == v18 )
            {
              *(_WORD *)v20 = 2573;
              v20 += 2;
            }
            ++v23;
          }
          while ( v23 <= v18 );
          goto LABEL_35;
        }
      }
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(a1 + 3432))(
            a1,
            v19,
            (unsigned int)((_DWORD)v20 - (_DWORD)v19),
            0);
LABEL_40:
    LocalFree(hMem);
    v8 += v18 + 6;
    if ( !v11 )
      return v11;
  }
  if ( !*(_DWORD *)(a2 + 416) )
  {
    v11 = OPRawPortWrite(a1, "\r\n", 2u);
    DSCSend(a1, "%%%%EndResource\r\n\r\n");
  }
  return v11;
}

```

## disassembly

```asm
0x18000f998  mov     [rsp+arg_18], rbx
0x18000f99d  push    rbp
0x18000f99e  push    rsi
0x18000f99f  push    rdi
0x18000f9a0  push    r12
0x18000f9a2  push    r13
0x18000f9a4  push    r14
0x18000f9a6  push    r15
0x18000f9a8  sub     rsp, 0F0h
0x18000f9af  mov     rax, cs:__security_cookie
0x18000f9b6  xor     rax, rsp
0x18000f9b9  mov     [rsp+128h+var_48], rax
0x18000f9c1  mov     eax, [rdx+188h]
0x18000f9c7  xor     r12d, r12d
0x18000f9ca  mov     [r8], eax
0x18000f9cd  mov     r13, rdx
0x18000f9d0  mov     rsi, rcx
0x18000f9d3  test    eax, eax
0x18000f9d5  jz      loc_18000FCBD
0x18000f9db  mov     ebx, [rdx+1A0h]
0x18000f9e1  lea     r14, [rdx+30h]
0x18000f9e5  mov     rbp, [rdx+190h]
0x18000f9ec  lea     rax, DSC_BeginResource; "\r\n%%%%BeginResource: %s %s\r\n"
0x18000f9f3  mov     r15d, [rdx+188h]
0x18000f9fa  lea     r8, RES_font; "font"
0x18000fa01  test    ebx, ebx
0x18000fa03  lea     rdx, DSC_IncludeResource; "\r\n%%%%IncludeResource: %s %s\r\n"
0x18000fa0a  mov     r9, r14
0x18000fa0d  lea     edi, [r12+1]
0x18000fa12  cmovz   rdx, rax
0x18000fa16  call    DSCSend
0x18000fa1b  mov     rax, [rsi+0DD0h]
0x18000fa22  mov     ecx, r12d
0x18000fa25  test    ebx, ebx
0x18000fa27  mov     r9, r14
0x18000fa2a  mov     edx, edi
0x18000fa2c  setz    cl
0x18000fa2f  mov     r8d, [rax]
0x18000fa32  mov     [rsp+128h+var_108], ecx
0x18000fa36  mov     rcx, rsi
0x18000fa39  call    RESIncludeOrDefineResource
0x18000fa3e  test    dword ptr [rsi+0DECh], 400000h
0x18000fa48  jz      short loc_18000FA9B
0x18000fa4a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fa4e  inc     rax
0x18000fa51  cmp     [r14+rax], r12b
0x18000fa55  jnz     short loc_18000FA4E
0x18000fa57  cmp     rax, 80h
0x18000fa5d  jnb     loc_18000FCBD
0x18000fa63  mov     r9, r14
0x18000fa66  lea     r8, aSFindfontPop; "/%s findfont pop\n"
0x18000fa6d  mov     edx, 94h
0x18000fa72  lea     rcx, [rsp+128h+var_E8]
0x18000fa77  call    OPSprintf
0x18000fa7c  mov     r8d, eax
0x18000fa7f  lea     rdx, [rsp+128h+var_E8]
0x18000fa84  mov     rcx, rsi
0x18000fa87  call    OPRawPortWrite
0x18000fa8c  xor     r9d, r9d
0x18000fa8f  mov     edi, eax
0x18000fa91  test    eax, eax
0x18000fa93  jz      loc_18000FCC0
0x18000fa99  jmp     short loc_18000FA9E
0x18000fa9b  xor     r9d, r9d
0x18000fa9e  lea     r12, [r15+rbp]
0x18000faa2  cmp     rbp, r12
0x18000faa5  jnb     loc_18000FC88
0x18000faab  cmp     [r13+1A0h], r9d
0x18000fab2  jnz     loc_18000FC88
0x18000fab8  cmp     byte ptr [rbp+0], 80h
0x18000fabc  jnz     loc_18000FC62
0x18000fac2  lea     rax, [rbp+1]
0x18000fac6  cmp     rax, r12
0x18000fac9  jnb     loc_18000FC62
0x18000facf  mov     r15b, [rax]
0x18000fad2  cmp     r15b, 3
0x18000fad6  jz      loc_18000FC88
0x18000fadc  lea     r14, [rbp+6]
0x18000fae0  cmp     r14, r12
0x18000fae3  jnb     loc_18000FC62
0x18000fae9  movzx   eax, byte ptr [rbp+4]
0x18000faed  movzx   ebx, byte ptr [rbp+5]
0x18000faf1  shl     ebx, 8
0x18000faf4  or      ebx, eax
0x18000faf6  movzx   eax, byte ptr [rbp+3]
0x18000fafa  shl     ebx, 8
0x18000fafd  or      ebx, eax
0x18000faff  movzx   eax, byte ptr [rbp+2]
0x18000fb03  shl     ebx, 8
0x18000fb06  or      ebx, eax
0x18000fb08  cmp     ebx, [r13+188h]
0x18000fb0f  jnb     loc_18000FC62
0x18000fb15  mov     eax, ebx
0x18000fb17  add     rax, r14
0x18000fb1a  cmp     rax, r12
0x18000fb1d  jnb     loc_18000FC62
0x18000fb23  lea     edx, ds:0[rbx*4]; uBytes
0x18000fb2a  xor     ecx, ecx; uFlags
0x18000fb2c  call    cs:__imp_LocalAlloc
0x18000fb32  xor     r9d, r9d
0x18000fb35  mov     r8, rax
0x18000fb38  test    rax, rax
0x18000fb3b  jz      loc_18000FC83
0x18000fb41  lea     r10d, [r9+1]
0x18000fb45  mov     [rsp+128h+hMem], rax
0x18000fb4a  cmp     r15b, r10b
0x18000fb4d  jnz     short loc_18000FB7A
0x18000fb4f  mov     ecx, r9d
0x18000fb52  test    ebx, ebx
0x18000fb54  jz      loc_18000FBFE
0x18000fb5a  mov     al, [r14]
0x18000fb5d  add     r14, r10
0x18000fb60  mov     [r8], al
0x18000fb63  inc     r8
0x18000fb66  cmp     al, 0Dh
0x18000fb68  jnz     short loc_18000FB71
0x18000fb6a  mov     byte ptr [r8], 0Ah
0x18000fb6e  inc     r8
0x18000fb71  add     ecx, r10d
0x18000fb74  cmp     ecx, ebx
0x18000fb76  jb      short loc_18000FB5A
0x18000fb78  jmp     short loc_18000FBF9
0x18000fb7a  cmp     r15b, 2
0x18000fb7e  jnz     loc_18000FC1E
0x18000fb84  cmp     [rsi+0A6h], r9w
0x18000fb8c  jnz     short loc_18000FBDE
0x18000fb8e  mov     edx, r10d
0x18000fb91  cmp     ebx, r10d
0x18000fb94  jb      short loc_18000FBFE
0x18000fb96  lea     r11, ghexBytes
0x18000fb9d  movzx   eax, byte ptr [r14]
0x18000fba1  shr     rax, 4
0x18000fba5  mov     al, [rax+r11]
0x18000fba9  mov     [r8], al
0x18000fbac  movzx   eax, byte ptr [r14]
0x18000fbb0  add     r14, r10
0x18000fbb3  and     eax, 0Fh
0x18000fbb6  mov     al, [rax+r11]
0x18000fbba  mov     [r8+1], al
0x18000fbbe  add     r8, 2
0x18000fbc2  test    dl, 1Fh
0x18000fbc5  jz      short loc_18000FBCB
0x18000fbc7  cmp     edx, ebx
0x18000fbc9  jnz     short loc_18000FBD5
0x18000fbcb  mov     word ptr [r8], 0A0Dh
0x18000fbd1  add     r8, 2
0x18000fbd5  add     edx, r10d
0x18000fbd8  cmp     edx, ebx
0x18000fbda  jbe     short loc_18000FB9D
0x18000fbdc  jmp     short loc_18000FBF9
0x18000fbde  mov     ecx, r10d
0x18000fbe1  cmp     ebx, r10d
0x18000fbe4  jb      short loc_18000FBFE
0x18000fbe6  mov     al, [r14]
0x18000fbe9  add     ecx, r10d
0x18000fbec  mov     [r8], al
0x18000fbef  add     r14, r10
0x18000fbf2  add     r8, r10
0x18000fbf5  cmp     ecx, ebx
0x18000fbf7  jbe     short loc_18000FBE6
0x18000fbf9  mov     rax, [rsp+128h+hMem]
0x18000fbfe  test    edi, edi
0x18000fc00  jz      short loc_18000FC3F
0x18000fc02  sub     r8d, eax
0x18000fc05  mov     rdx, rax
0x18000fc08  mov     rax, [rsi+0D68h]
0x18000fc0f  mov     rcx, rsi
0x18000fc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc17  mov     edi, eax
0x18000fc19  xor     r9d, r9d
0x18000fc1c  jmp     short loc_18000FC3F
0x18000fc1e  cmp     [rsi+0D70h], r9d
0x18000fc25  jnz     short loc_18000FC3C
0x18000fc27  mov     ecx, 0Dh; dwErrCode
0x18000fc2c  mov     [rsi+0D70h], r10d
0x18000fc33  call    cs:__imp_SetLastError
0x18000fc39  xor     r9d, r9d
0x18000fc3c  mov     edi, r9d
0x18000fc3f  mov     rcx, [rsp+128h+hMem]; hMem
0x18000fc44  test    rcx, rcx
0x18000fc47  jz      short loc_18000FC52
0x18000fc49  call    cs:__imp_LocalFree
0x18000fc4f  xor     r9d, r9d
0x18000fc52  lea     ecx, [rbx+6]
0x18000fc55  add     rbp, rcx
0x18000fc58  test    edi, edi
0x18000fc5a  jnz     loc_18000FAA2
0x18000fc60  jmp     short loc_18000FCC0
0x18000fc62  cmp     [rsi+0D70h], r9d
0x18000fc69  jnz     short loc_18000FC83
0x18000fc6b  mov     ecx, 0Dh; dwErrCode
0x18000fc70  mov     dword ptr [rsi+0D70h], 1
0x18000fc7a  call    cs:__imp_SetLastError
0x18000fc80  xor     r9d, r9d
0x18000fc83  mov     edi, r9d
0x18000fc86  jmp     short loc_18000FCC0
0x18000fc88  test    edi, edi
0x18000fc8a  jz      short loc_18000FCC0
0x18000fc8c  cmp     [r13+1A0h], r9d
0x18000fc93  jnz     short loc_18000FCC0
0x18000fc95  mov     r8d, 2
0x18000fc9b  lea     rdx, asc_180062FDC; "\r\n"
0x18000fca2  mov     rcx, rsi
0x18000fca5  call    OPRawPortWrite
0x18000fcaa  lea     rdx, DSC_EndResource; "%%%%EndResource\r\n\r\n"
0x18000fcb1  mov     rcx, rsi
0x18000fcb4  mov     edi, eax
0x18000fcb6  call    DSCSend
0x18000fcbb  jmp     short loc_18000FCC0
0x18000fcbd  mov     edi, r12d
0x18000fcc0  mov     eax, edi
0x18000fcc2  mov     rcx, [rsp+128h+var_48]
0x18000fcca  xor     rcx, rsp; StackCookie
0x18000fccd  call    __security_check_cookie
0x18000fcd2  mov     rbx, [rsp+128h+arg_18]
0x18000fcda  add     rsp, 0F0h
0x18000fce1  pop     r15
0x18000fce3  pop     r14
0x18000fce5  pop     r13
0x18000fce7  pop     r12
0x18000fce9  pop     rdi
0x18000fcea  pop     rsi
0x18000fceb  pop     rbp
0x18000fcec  retn
```
