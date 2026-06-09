# AslpFileGetVersionBlockFromResourceRoot

- ea: `0x140035a68`
- end: `0x140035cb2`
- name: `AslpFileGetVersionBlockFromResourceRoot`
- size: `586`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140055540`

## callees

- `0x140006c10`
- `0x140035a68`
- `0x140036568`
- `0x14003e364`
- `0x140051e8c`

## string_xrefs

- `0x140035c75`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x140035ae1`: `Found resource directory entry out of image bounds`
- `0x140035b2f`: `Found resource directory out of image bounds`
- `0x140035b8d`: `Found resource directory out of image bounds`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockFromResourceRoot(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  unsigned __int64 v7; // rbx
  unsigned __int64 v11; // r11
  __int64 v12; // rcx
  __int64 v13; // r11
  __int64 v14; // r8
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r11
  int ImageNtHeader; // ebx
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned __int16 *v31; // rcx
  __int64 v32; // [rsp+90h] [rbp+18h] BYREF

  v4 = *(_QWORD *)(a4 + 32);
  v5 = *(_QWORD *)(a4 + 40);
  v7 = *(unsigned __int16 *)(a3 + 14);
  v32 = 0;
  v11 = 0;
  v12 = a3 + 16 + 8LL * *(unsigned __int16 *)(a3 + 12);
  while ( v11 < v7 )
  {
    if ( !(unsigned __int8)AslpMemoryCheckBounds(v12, 8, v4, v5) )
    {
      v14 = 2097;
      goto LABEL_7;
    }
    if ( *(_WORD *)v12 == 16 )
      goto LABEL_10;
    v12 += 8;
    v11 = v13 + 1;
  }
  if ( v11 == v7 )
    return 3221225609LL;
LABEL_10:
  v16 = *(_DWORD *)(v12 + 4);
  if ( v16 >= 0 )
    goto LABEL_24;
  if ( !(unsigned __int8)AslpMemoryCheckBounds((v16 & 0x7FFFFFFF) + a3, 16, v4, v5) )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockFromResourceRoot", 2124, "Found resource directory out of image bounds");
    return 3221226030LL;
  }
  if ( !*(_WORD *)(v17 + 14) && !*(_WORD *)(v17 + 12) )
    return 3221225609LL;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v17 + 16, 8, v18, v19) )
  {
    v14 = 2134;
LABEL_7:
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockFromResourceRoot",
      v14,
      "Found resource directory entry out of image bounds");
    return 3221226030LL;
  }
  v22 = *(_DWORD *)(v12 + 4);
  if ( v22 < 0 )
  {
    if ( !(unsigned __int8)AslpMemoryCheckBounds((v22 & 0x7FFFFFFF) + a3, 16, v20, v21) )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetVersionBlockFromResourceRoot",
        2145,
        "Found resource directory out of image bounds");
      return 3221226030LL;
    }
    if ( *(_WORD *)(v24 + 14) || *(_WORD *)(v24 + 12) )
    {
      if ( !(unsigned __int8)AslpMemoryCheckBounds(v23 + v24, v27, v25, v26) )
      {
        v14 = 2155;
        goto LABEL_7;
      }
      goto LABEL_24;
    }
    return 3221225609LL;
  }
LABEL_24:
  if ( !(unsigned __int8)AslpMemoryCheckBounds(a3 + *(unsigned int *)(v12 + 4), 16, v4, v5) )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockFromResourceRoot",
      2169,
      "Found resource data entry out of image bounds");
    return 3221226030LL;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(&v32, a4);
  if ( ImageNtHeader < 0 )
    goto LABEL_32;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v32, 8, v4, v5) )
  {
    ImageNtHeader = -1073741266;
LABEL_32:
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockFromResourceRoot",
      2179,
      "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
      ImageNtHeader);
    return (unsigned int)ImageNtHeader;
  }
  v30 = AslpImageRvaToVa(v29, a4);
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v30, 38, v4, v5) )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockFromResourceRoot",
      2185,
      "Found version block root but it was out of image bounds");
    return 3221226030LL;
  }
  *a1 = v31;
  *a2 = *v31;
  return 0;
}

```

## disassembly

```asm
0x140035a68  mov     rax, rsp
0x140035a6b  push    rbx
0x140035a6c  push    rbp
0x140035a6d  push    rsi
0x140035a6e  push    rdi
0x140035a6f  push    r12
0x140035a71  push    r13
0x140035a73  push    r14
0x140035a75  push    r15
0x140035a77  sub     rsp, 38h
0x140035a7b  mov     rdi, [r9+20h]
0x140035a7f  xor     r14d, r14d
0x140035a82  mov     rsi, [r9+28h]
0x140035a86  mov     r13, rcx
0x140035a89  movzx   ebx, word ptr [r8+0Eh]
0x140035a8e  lea     rcx, [r8+10h]
0x140035a92  mov     [rax+18h], r14
0x140035a96  mov     r12, rdx
0x140035a99  movzx   eax, word ptr [r8+0Ch]
0x140035a9e  lea     edx, [r14+10h]
0x140035aa2  mov     r15, r9
0x140035aa5  mov     rbp, r8
0x140035aa8  mov     r11d, r14d
0x140035aab  lea     rcx, [rcx+rax*8]
0x140035aaf  cmp     r11, rbx
0x140035ab2  jnb     short loc_140035B03
0x140035ab4  mov     r9, rsi
0x140035ab7  mov     r8, rdi
0x140035aba  mov     edx, 8
0x140035abf  call    AslpMemoryCheckBounds
0x140035ac4  test    al, al
0x140035ac6  jz      short loc_140035ADB
0x140035ac8  mov     edx, 10h
0x140035acd  cmp     [rcx], dx
0x140035ad0  jz      short loc_140035B09
0x140035ad2  add     rcx, 8
0x140035ad6  inc     r11
0x140035ad9  jmp     short loc_140035AAF
0x140035adb  mov     r8d, 831h
0x140035ae1  lea     r9, aFoundResourceD; "Found resource directory entry out of i"...
0x140035ae8  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x140035aef  mov     ecx, 1
0x140035af4  call    AslLogCallPrintf
0x140035af9  mov     eax, 0C000022Eh
0x140035afe  jmp     loc_140035CA0
0x140035b03  jz      loc_140035C9B
0x140035b09  mov     eax, [rcx+4]
0x140035b0c  test    eax, eax
0x140035b0e  jns     loc_140035BCB
0x140035b14  mov     ebx, 7FFFFFFFh
0x140035b19  mov     r9, rsi
0x140035b1c  and     rax, rbx
0x140035b1f  mov     r8, rdi
0x140035b22  lea     rcx, [rax+rbp]
0x140035b26  call    AslpMemoryCheckBounds
0x140035b2b  test    al, al
0x140035b2d  jnz     short loc_140035B3E
0x140035b2f  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x140035b36  mov     r8d, 84Ch
0x140035b3c  jmp     short loc_140035AE8
0x140035b3e  cmp     [rcx+0Eh], r14w
0x140035b43  jnz     short loc_140035B50
0x140035b45  cmp     [rcx+0Ch], r14w
0x140035b4a  jz      loc_140035C9B
0x140035b50  mov     r11d, 8
0x140035b56  add     rcx, 10h
0x140035b5a  mov     edx, r11d
0x140035b5d  call    AslpMemoryCheckBounds
0x140035b62  test    al, al
0x140035b64  jnz     short loc_140035B71
0x140035b66  mov     r8d, 856h
0x140035b6c  jmp     loc_140035AE1
0x140035b71  mov     eax, [rcx+4]
0x140035b74  test    eax, eax
0x140035b76  jns     short loc_140035BCB
0x140035b78  and     rax, rbx
0x140035b7b  mov     edx, 10h
0x140035b80  lea     rcx, [rax+rbp]
0x140035b84  call    AslpMemoryCheckBounds
0x140035b89  test    al, al
0x140035b8b  jnz     short loc_140035B9F
0x140035b8d  lea     r9, aFoundResourceD_0; "Found resource directory out of image b"...
0x140035b94  mov     r8d, 861h
0x140035b9a  jmp     loc_140035AE8
0x140035b9f  cmp     [rcx+0Eh], r14w
0x140035ba4  jnz     short loc_140035BB1
0x140035ba6  cmp     [rcx+0Ch], r14w
0x140035bab  jz      loc_140035C9B
0x140035bb1  add     rcx, rdx
0x140035bb4  mov     rdx, r11
0x140035bb7  call    AslpMemoryCheckBounds
0x140035bbc  test    al, al
0x140035bbe  jnz     short loc_140035BCB
0x140035bc0  mov     r8d, 86Bh
0x140035bc6  jmp     loc_140035AE1
0x140035bcb  mov     r14d, [rcx+4]
0x140035bcf  mov     r9, rsi
0x140035bd2  add     r14, rbp
0x140035bd5  mov     r8, rdi
0x140035bd8  mov     rcx, r14
0x140035bdb  mov     edx, 10h
0x140035be0  call    AslpMemoryCheckBounds
0x140035be5  test    al, al
0x140035be7  jnz     short loc_140035BFB
0x140035be9  lea     r9, aFoundResourceD_1; "Found resource data entry out of image "...
0x140035bf0  mov     r8d, 879h
0x140035bf6  jmp     loc_140035AE8
0x140035bfb  mov     rdx, r15
0x140035bfe  lea     rcx, [rsp+78h+arg_10]
0x140035c06  call    AslpFileGetImageNtHeader
0x140035c0b  mov     ebx, eax
0x140035c0d  test    eax, eax
0x140035c0f  js      short loc_140035C75
0x140035c11  mov     rcx, [rsp+78h+arg_10]
0x140035c19  mov     r9, rsi
0x140035c1c  mov     r8, rdi
0x140035c1f  mov     edx, 8
0x140035c24  call    AslpMemoryCheckBounds
0x140035c29  test    al, al
0x140035c2b  jz      short loc_140035C70
0x140035c2d  mov     r8d, [r14]
0x140035c30  mov     rdx, r15
0x140035c33  call    AslpImageRvaToVa
0x140035c38  mov     rcx, rax
0x140035c3b  mov     r9, rsi
0x140035c3e  mov     r8, rdi
0x140035c41  mov     edx, 26h ; '&'
0x140035c46  call    AslpMemoryCheckBounds
0x140035c4b  test    al, al
0x140035c4d  jnz     short loc_140035C61
0x140035c4f  lea     r9, aFoundVersionBl; "Found version block root but it was out"...
0x140035c56  mov     r8d, 889h
0x140035c5c  jmp     loc_140035AE8
0x140035c61  mov     [r13+0], rcx
0x140035c65  movzx   eax, word ptr [rcx]
0x140035c68  mov     [r12], rax
0x140035c6c  xor     eax, eax
0x140035c6e  jmp     short loc_140035CA0
0x140035c70  mov     ebx, 0C000022Eh
0x140035c75  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x140035c7c  mov     [rsp+78h+var_58], ebx
0x140035c80  mov     r8d, 883h
0x140035c86  lea     rdx, aAslpfilegetver_7; "AslpFileGetVersionBlockFromResourceRoot"
0x140035c8d  mov     ecx, 1
0x140035c92  call    AslLogCallPrintf
0x140035c97  mov     eax, ebx
0x140035c99  jmp     short loc_140035CA0
0x140035c9b  mov     eax, 0C0000089h
0x140035ca0  add     rsp, 38h
0x140035ca4  pop     r15
0x140035ca6  pop     r14
0x140035ca8  pop     r13
0x140035caa  pop     r12
0x140035cac  pop     rdi
0x140035cad  pop     rsi
0x140035cae  pop     rbp
0x140035caf  pop     rbx
0x140035cb0  retn
```
