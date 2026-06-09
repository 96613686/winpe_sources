# AudioSpecificConfig

- ea: `0x18003df38`
- end: `0x18003e3e5`
- name: `AudioSpecificConfig`
- size: `1197`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003dc40`
- `0x18005d308`

## callees

- `0x18003dd44`
- `0x18003df38`
- `0x18003e3ec`
- `0x18003e494`
- `0x18003e4f0`

## pseudocode

```c
__int64 __fastcall AudioSpecificConfig(_DWORD *a1, int *a2, _DWORD *a3)
{
  unsigned int v3; // r15d
  unsigned int v7; // eax
  __int64 v8; // rax
  int AudioObjectType; // r9d
  unsigned int v10; // esi
  unsigned int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // eax
  int v15; // ecx
  bool v16; // zf
  int v17; // ecx
  int v18; // ecx
  unsigned int v19; // eax
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rcx

  v3 = 0;
  if ( a3 && *a3 )
    v3 = GetTotalNumberOfBitsRead(a1);
  a1[10] = -*a1 & 7;
  *a2 = GetAudioObjectType(a1);
  if ( *a1 < 4u )
    FillBitCache(a1, 4);
  v7 = a1[1];
  *a1 -= 4;
  v8 = (v7 >> *a1) & 0xF;
  a2[1] = v8;
  if ( (_DWORD)v8 == 15 )
  {
    if ( *a1 < 0x10u )
      FillBitCache(a1, 16);
    *a1 -= 16;
    a2[2] = (unsigned __int16)(a1[1] >> *a1) << 8;
    if ( *a1 < 8u )
      FillBitCache(a1, 8);
    *a1 -= 8;
    a2[2] += (unsigned __int8)(a1[1] >> *a1);
  }
  else
  {
    a2[2] = *((_DWORD *)qword_1800AB100 + v8);
  }
  if ( *a1 < 4u )
    FillBitCache(a1, 4);
  *a1 -= 4;
  AudioObjectType = *a2;
  a2[8] = (a1[1] >> *a1) & 0xF;
  a2[6] = -1;
  a2[7] = -1;
  if ( AudioObjectType == 5 || AudioObjectType == 29 )
  {
    a2[3] = 5;
    a2[6] = 1;
    if ( AudioObjectType == 29 )
      a2[7] = 1;
    if ( *a1 < 4u )
      FillBitCache(a1, 4);
    *a1 -= 4;
    v22 = (a1[1] >> *a1) & 0xF;
    v16 = a2[1] == 15;
    a2[4] = v22;
    if ( v16 )
    {
      if ( *a1 < 0x10u )
        FillBitCache(a1, 16);
      *a1 -= 16;
      a2[5] = (unsigned __int16)(a1[1] >> *a1) << 8;
      if ( *a1 < 8u )
        FillBitCache(a1, 8);
      *a1 -= 8;
      a2[5] += (unsigned __int8)(a1[1] >> *a1);
    }
    else
    {
      a2[5] = *((_DWORD *)qword_1800AB100 + v22);
    }
    AudioObjectType = GetAudioObjectType(a1);
    *a2 = AudioObjectType;
  }
  else
  {
    a2[3] = 0;
  }
  if ( AudioObjectType != 2 && AudioObjectType != 42 )
    goto LABEL_18;
  v10 = 0;
  if ( AudioObjectType != 42 )
  {
    v10 = GASpecificConfig(a1, a2 + 13, (unsigned int)a2[8]);
    if ( v10 )
      goto LABEL_16;
    if ( a2[13] )
    {
      a2[9] = 960;
      v10 = -12;
      goto LABEL_16;
    }
    a2[9] = 1024;
  }
  v15 = *a2;
  if ( *a2 <= 23 )
  {
    if ( v15 == 23 )
      goto LABEL_18;
    v21 = v15 - 17;
    if ( !v21 )
      goto LABEL_18;
    v17 = v21 - 2;
    v16 = v17 == 0;
  }
  else
  {
    v17 = v15 - 24;
    v16 = v17 == 0;
  }
  if ( v16 || (v18 = v17 - 1) == 0 || (unsigned int)(v18 - 1) < 2 )
  {
LABEL_18:
    v10 = -10;
    goto LABEL_16;
  }
  if ( a3 && *a3 && a2[3] != 5 && *a3 >= 16 - v3 + (unsigned int)GetTotalNumberOfBitsRead(a1) )
  {
    if ( *a1 < 0xBu )
      FillBitCache(v27, 11);
    *a1 -= 11;
    if ( ((a1[1] >> *a1) & 0x7FF) == 0x2B7 )
    {
      v23 = GetAudioObjectType(a1);
      a2[3] = v23;
      if ( v23 == 5 )
      {
        if ( !*a1 )
          FillBitCache(a1, 1);
        v24 = a1[1];
        v25 = (v24 >> --*a1) & 1;
        a2[6] = v25;
        if ( v25 )
        {
          if ( *a1 < 4u )
            FillBitCache(a1, 4);
          *a1 -= 4;
          v26 = (a1[1] >> *a1) & 0xF;
          v16 = a2[1] == 15;
          a2[4] = v26;
          if ( v16 )
          {
            if ( *a1 < 0x10u )
              FillBitCache(a1, 16);
            *a1 -= 16;
            a2[5] = (unsigned __int16)(a1[1] >> *a1) << 8;
            if ( *a1 < 8u )
              FillBitCache(a1, 8);
            *a1 -= 8;
            a2[5] += (unsigned __int8)(a1[1] >> *a1);
          }
          else
          {
            a2[5] = *((_DWORD *)qword_1800AB100 + v26);
          }
          if ( *a3 >= 12 - v3 + (unsigned int)GetTotalNumberOfBitsRead(a1) )
          {
            if ( *a1 < 0xBu )
              FillBitCache(a1, 11);
            *a1 -= 11;
            if ( ((a1[1] >> *a1) & 0x7FF) == 0x548 )
            {
              if ( !*a1 )
                FillBitCache(a1, 1);
              a2[7] = (a1[1] >> --*a1) & 1;
            }
          }
        }
      }
      else if ( *a2 == 2 && v23 == 2 )
      {
        a2[3] = 0;
      }
    }
  }
  v19 = a2[3];
  if ( v19 > 0x1D || (v20 = 536870945, !_bittest(&v20, v19)) )
    v10 = -11;
LABEL_16:
  if ( a3 && *a3 )
  {
    v12 = GetTotalNumberOfBitsRead(a1);
    *a3 = 0;
    if ( v12 <= v3 )
      return (unsigned int)-1;
    v14 = v12 - v3;
    if ( v13 < v14 )
      return (unsigned int)-1;
    else
      *a3 = v13 - v14;
  }
  return v10;
}

```

## disassembly

```asm
0x18003df38  push    rbx
0x18003df3a  push    rbp
0x18003df3b  push    rsi
0x18003df3c  push    rdi
0x18003df3d  push    r13
0x18003df3f  push    r14
0x18003df41  push    r15
0x18003df43  sub     rsp, 20h
0x18003df47  xor     r15d, r15d
0x18003df4a  mov     r14, r8
0x18003df4d  mov     rdi, rdx
0x18003df50  mov     rbx, rcx
0x18003df53  test    r8, r8
0x18003df56  jz      short loc_18003DF65
0x18003df58  cmp     [r8], r15d
0x18003df5b  jbe     short loc_18003DF65
0x18003df5d  call    GetTotalNumberOfBitsRead
0x18003df62  mov     r15d, eax
0x18003df65  mov     ecx, [rcx]
0x18003df67  neg     ecx
0x18003df69  and     ecx, 7
0x18003df6c  mov     [rbx+28h], ecx
0x18003df6f  mov     rcx, rbx
0x18003df72  call    GetAudioObjectType
0x18003df77  mov     esi, 4
0x18003df7c  mov     [rdi], eax
0x18003df7e  cmp     [rbx], esi
0x18003df80  jnb     short loc_18003DF8C
0x18003df82  mov     edx, esi
0x18003df84  mov     rcx, rbx
0x18003df87  call    FillBitCache
0x18003df8c  mov     eax, [rbx+4]
0x18003df8f  mov     r13d, 0FFFFFFFCh
0x18003df95  add     [rbx], r13d
0x18003df98  mov     ebp, 10h
0x18003df9d  mov     ecx, [rbx]
0x18003df9f  shr     eax, cl
0x18003dfa1  lea     rcx, qword_1800AB100
0x18003dfa8  and     eax, 0Fh
0x18003dfab  mov     [rdi+4], eax
0x18003dfae  cmp     eax, 0Fh
0x18003dfb1  jz      loc_18003E121
0x18003dfb7  mov     eax, [rcx+rax*4]
0x18003dfba  mov     [rdi+8], eax
0x18003dfbd  cmp     [rbx], esi
0x18003dfbf  jnb     short loc_18003DFCB
0x18003dfc1  mov     edx, esi
0x18003dfc3  mov     rcx, rbx
0x18003dfc6  call    FillBitCache
0x18003dfcb  add     [rbx], r13d
0x18003dfce  mov     eax, [rbx+4]
0x18003dfd1  mov     ecx, [rbx]
0x18003dfd3  mov     r9d, [rdi]
0x18003dfd6  shr     eax, cl
0x18003dfd8  and     eax, 0Fh
0x18003dfdb  mov     [rdi+20h], eax
0x18003dfde  or      eax, 0FFFFFFFFh
0x18003dfe1  mov     [rdi+18h], eax
0x18003dfe4  mov     [rdi+1Ch], eax
0x18003dfe7  lea     r13d, [rax+2]
0x18003dfeb  cmp     r9d, 5
0x18003dfef  jz      loc_18003E375
0x18003dff5  cmp     r9d, 1Dh
0x18003dff9  jz      loc_18003E375
0x18003dfff  mov     dword ptr [rdi+0Ch], 0
0x18003e006  cmp     r9d, 2
0x18003e00a  jnz     loc_18003E393
0x18003e010  xor     esi, esi
0x18003e012  cmp     r9d, 2Ah ; '*'
0x18003e016  jz      loc_18003E0D9
0x18003e01c  cmp     r9d, 11h
0x18003e020  jle     short loc_18003E06B
0x18003e022  mov     ecx, r9d
0x18003e025  sub     ecx, 13h
0x18003e028  jz      short loc_18003E03E
0x18003e02a  sub     ecx, r13d
0x18003e02d  jz      short loc_18003E03E
0x18003e02f  sub     ecx, r13d
0x18003e032  jz      short loc_18003E03E
0x18003e034  sub     ecx, r13d
0x18003e037  jz      short loc_18003E03E
0x18003e039  cmp     ecx, r13d
0x18003e03c  jnz     short loc_18003E089
0x18003e03e  mov     r8d, [rdi+20h]
0x18003e042  lea     rdx, [rdi+34h]
0x18003e046  mov     rcx, rbx
0x18003e049  call    GASpecificConfig
0x18003e04e  mov     esi, eax
0x18003e050  test    eax, eax
0x18003e052  jz      short loc_18003E090
0x18003e054  test    r14, r14
0x18003e057  jnz     short loc_18003E0A8
0x18003e059  mov     eax, esi
0x18003e05b  add     rsp, 20h
0x18003e05f  pop     r15
0x18003e061  pop     r14
0x18003e063  pop     r13
0x18003e065  pop     rdi
0x18003e066  pop     rsi
0x18003e067  pop     rbp
0x18003e068  pop     rbx
0x18003e069  retn
0x18003e06b  jz      short loc_18003E03E
0x18003e06d  mov     ecx, r9d
0x18003e070  sub     ecx, r13d
0x18003e073  jz      short loc_18003E03E
0x18003e075  sub     ecx, r13d
0x18003e078  jz      short loc_18003E03E
0x18003e07a  sub     ecx, r13d
0x18003e07d  jz      short loc_18003E03E
0x18003e07f  sub     ecx, r13d
0x18003e082  jz      short loc_18003E03E
0x18003e084  sub     ecx, 2
0x18003e087  jmp     short loc_18003E037
0x18003e089  mov     esi, 0FFFFFFF6h
0x18003e08e  jmp     short loc_18003E054
0x18003e090  cmp     dword ptr [rdi+34h], 0
0x18003e094  jz      loc_18003E3A2
0x18003e09a  mov     dword ptr [rdi+24h], 3C0h
0x18003e0a1  mov     esi, 0FFFFFFF4h
0x18003e0a6  jmp     short loc_18003E054
0x18003e0a8  mov     edx, [r14]
0x18003e0ab  test    edx, edx
0x18003e0ad  jz      short loc_18003E059
0x18003e0af  mov     rcx, rbx
0x18003e0b2  call    GetTotalNumberOfBitsRead
0x18003e0b7  mov     dword ptr [r14], 0
0x18003e0be  cmp     eax, r15d
0x18003e0c1  jbe     loc_18003E3DD
0x18003e0c7  sub     eax, r15d
0x18003e0ca  cmp     edx, eax
0x18003e0cc  jb      loc_18003E3DD
0x18003e0d2  sub     edx, eax
0x18003e0d4  mov     [r14], edx
0x18003e0d7  jmp     short loc_18003E059
0x18003e0d9  mov     ecx, [rdi]
0x18003e0db  cmp     ecx, 17h
0x18003e0de  jle     loc_18003E169
0x18003e0e4  sub     ecx, 18h
0x18003e0e7  jz      short loc_18003E089
0x18003e0e9  sub     ecx, r13d
0x18003e0ec  jz      short loc_18003E089
0x18003e0ee  sub     ecx, r13d
0x18003e0f1  jz      short loc_18003E089
0x18003e0f3  cmp     ecx, r13d
0x18003e0f6  jz      short loc_18003E089
0x18003e0f8  test    r14, r14
0x18003e0fb  jnz     loc_18003E3AE
0x18003e101  mov     eax, [rdi+0Ch]
0x18003e104  cmp     eax, 1Dh
0x18003e107  ja      short loc_18003E117
0x18003e109  mov     ecx, 20000021h
0x18003e10e  bt      ecx, eax
0x18003e111  jb      loc_18003E054
0x18003e117  mov     esi, 0FFFFFFF5h
0x18003e11c  jmp     loc_18003E054
0x18003e121  cmp     [rbx], ebp
0x18003e123  jnb     short loc_18003E12F
0x18003e125  mov     edx, ebp
0x18003e127  mov     rcx, rbx
0x18003e12a  call    FillBitCache
0x18003e12f  add     dword ptr [rbx], 0FFFFFFF0h
0x18003e132  mov     eax, [rbx+4]
0x18003e135  mov     ecx, [rbx]
0x18003e137  shr     eax, cl
0x18003e139  movzx   eax, ax
0x18003e13c  shl     eax, 8
0x18003e13f  mov     [rdi+8], eax
0x18003e142  cmp     dword ptr [rbx], 8
0x18003e145  jnb     short loc_18003E154
0x18003e147  mov     edx, 8
0x18003e14c  mov     rcx, rbx
0x18003e14f  call    FillBitCache
0x18003e154  add     dword ptr [rbx], 0FFFFFFF8h
0x18003e157  mov     eax, [rbx+4]
0x18003e15a  mov     ecx, [rbx]
0x18003e15c  shr     eax, cl
0x18003e15e  movzx   eax, al
0x18003e161  add     [rdi+8], eax
0x18003e164  jmp     loc_18003DFBD
0x18003e169  jz      loc_18003E089
0x18003e16f  sub     ecx, 11h
0x18003e172  jz      loc_18003E089
0x18003e178  sub     ecx, 2
0x18003e17b  jmp     loc_18003E0E7
0x18003e180  cmp     [rbx], esi
0x18003e182  jnb     short loc_18003E18E
0x18003e184  mov     edx, esi
0x18003e186  mov     rcx, rbx
0x18003e189  call    FillBitCache
0x18003e18e  add     dword ptr [rbx], 0FFFFFFFCh
0x18003e191  mov     eax, [rbx+4]
0x18003e194  mov     ecx, [rbx]
0x18003e196  shr     eax, cl
0x18003e198  and     eax, 0Fh
0x18003e19b  cmp     dword ptr [rdi+4], 0Fh
0x18003e19f  mov     [rdi+10h], eax
0x18003e1a2  jz      short loc_18003E1C3
0x18003e1a4  lea     rcx, qword_1800AB100
0x18003e1ab  mov     eax, [rcx+rax*4]
0x18003e1ae  mov     [rdi+14h], eax
0x18003e1b1  mov     rcx, rbx
0x18003e1b4  call    GetAudioObjectType
0x18003e1b9  mov     r9d, eax
0x18003e1bc  mov     [rdi], eax
0x18003e1be  jmp     loc_18003E006
0x18003e1c3  cmp     [rbx], ebp
0x18003e1c5  jnb     short loc_18003E1D1
0x18003e1c7  mov     edx, ebp
0x18003e1c9  mov     rcx, rbx
0x18003e1cc  call    FillBitCache
0x18003e1d1  add     dword ptr [rbx], 0FFFFFFF0h
0x18003e1d4  mov     eax, [rbx+4]
0x18003e1d7  mov     ecx, [rbx]
0x18003e1d9  shr     eax, cl
0x18003e1db  movzx   eax, ax
0x18003e1de  shl     eax, 8
0x18003e1e1  mov     [rdi+14h], eax
0x18003e1e4  cmp     dword ptr [rbx], 8
0x18003e1e7  jnb     short loc_18003E1F6
0x18003e1e9  mov     edx, 8
0x18003e1ee  mov     rcx, rbx
0x18003e1f1  call    FillBitCache
0x18003e1f6  add     dword ptr [rbx], 0FFFFFFF8h
0x18003e1f9  mov     eax, [rbx+4]
0x18003e1fc  mov     ecx, [rbx]
0x18003e1fe  shr     eax, cl
0x18003e200  movzx   eax, al
0x18003e203  add     [rdi+14h], eax
0x18003e206  jmp     short loc_18003E1B1
0x18003e208  mov     ebp, 0Bh
0x18003e20d  cmp     [rbx], ebp
0x18003e20f  jnb     short loc_18003E218
0x18003e211  mov     edx, ebp
0x18003e213  call    FillBitCache
0x18003e218  add     dword ptr [rbx], 0FFFFFFF5h
0x18003e21b  mov     eax, [rbx+4]
0x18003e21e  mov     ecx, [rbx]
0x18003e220  shr     eax, cl
0x18003e222  and     eax, 7FFh
0x18003e227  cmp     eax, 2B7h
0x18003e22c  jnz     loc_18003E101
0x18003e232  mov     rcx, rbx
0x18003e235  call    GetAudioObjectType
0x18003e23a  mov     [rdi+0Ch], eax
0x18003e23d  cmp     eax, 5
0x18003e240  jz      short loc_18003E260
0x18003e242  cmp     dword ptr [rdi], 2
0x18003e245  jnz     loc_18003E101
0x18003e24b  cmp     eax, 2
0x18003e24e  jnz     loc_18003E101
0x18003e254  mov     dword ptr [rdi+0Ch], 0
0x18003e25b  jmp     loc_18003E101
0x18003e260  cmp     [rbx], r13d
0x18003e263  jnb     short loc_18003E270
0x18003e265  mov     edx, r13d
0x18003e268  mov     rcx, rbx
0x18003e26b  call    FillBitCache
0x18003e270  mov     eax, [rbx+4]
0x18003e273  or      r13d, 0FFFFFFFFh
0x18003e277  add     [rbx], r13d
0x18003e27a  mov     ecx, [rbx]
0x18003e27c  shr     eax, cl
0x18003e27e  and     eax, 1
0x18003e281  mov     [rdi+18h], eax
0x18003e284  jz      loc_18003E101
0x18003e28a  cmp     dword ptr [rbx], 4
0x18003e28d  jnb     short loc_18003E29C
0x18003e28f  mov     edx, 4
0x18003e294  mov     rcx, rbx
0x18003e297  call    FillBitCache
0x18003e29c  add     dword ptr [rbx], 0FFFFFFFCh
0x18003e29f  mov     eax, [rbx+4]
0x18003e2a2  mov     ecx, [rbx]
0x18003e2a4  shr     eax, cl
0x18003e2a6  and     eax, 0Fh
0x18003e2a9  cmp     dword ptr [rdi+4], 0Fh
0x18003e2ad  mov     [rdi+10h], eax
0x18003e2b0  jz      short loc_18003E329
0x18003e2b2  lea     rcx, qword_1800AB100
0x18003e2b9  mov     eax, [rcx+rax*4]
0x18003e2bc  mov     [rdi+14h], eax
0x18003e2bf  mov     rcx, rbx
0x18003e2c2  call    GetTotalNumberOfBitsRead
0x18003e2c7  mov     ecx, 0Ch
0x18003e2cc  sub     ecx, r15d
0x18003e2cf  add     eax, ecx
0x18003e2d1  cmp     [r14], eax
0x18003e2d4  jb      loc_18003E101
0x18003e2da  cmp     [rbx], ebp
0x18003e2dc  jnb     short loc_18003E2E8
0x18003e2de  mov     edx, ebp
0x18003e2e0  mov     rcx, rbx
0x18003e2e3  call    FillBitCache
0x18003e2e8  add     dword ptr [rbx], 0FFFFFFF5h
0x18003e2eb  mov     eax, [rbx+4]
0x18003e2ee  mov     ecx, [rbx]
0x18003e2f0  shr     eax, cl
0x18003e2f2  and     eax, 7FFh
0x18003e2f7  cmp     eax, 548h
  ... truncated ...
```
