# ReadRepTree

- ea: `0x140002b50`
- end: `0x140002eee`
- name: `ReadRepTree`
- size: `926`
- prototype: `_BOOL8 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002a48`

## callees

- `0x140002b50`
- `0x140002ef4`
- `0x140002fcc`
- `0x140011560`
- `0x1400119c0`

## pseudocode

```c
_BOOL8 __fastcall ReadRepTree(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rdi
  int v9; // ebx
  int v10; // ecx
  int v11; // r9d
  int v12; // edi
  unsigned int v13; // r8d
  __int16 v14; // bx
  int v15; // ebx
  unsigned int v16; // r8d
  int v17; // r14d
  __int16 v18; // bx
  int v20; // ebx
  int v21; // eax
  int v22; // ecx
  int v23; // ebx
  char v24; // dl
  __int64 v25; // rax
  int v26; // ebx
  int v27; // eax
  int v28; // ecx
  int v29; // ebx
  unsigned int v30; // edx
  int v31; // ecx
  unsigned int v32; // edx
  int v33; // ecx
  unsigned __int8 v34[32]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v35[96]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v36[256]; // [rsp+110h] [rbp+10h] BYREF

  for ( i = 0; i != 20; ++i )
  {
    v9 = *(_DWORD *)(a1 + 11968) >> 28;
    fillbuf(a1, 4);
    v34[i] = v9;
  }
  if ( *(_DWORD *)(a1 + 11980) )
    return 0;
  LOBYTE(v11) = 8;
  make_table(v10, 20, (int)v34, v11, v36, (__int64)v35);
  v12 = 0;
LABEL_5:
  if ( v12 < a2 )
  {
    v13 = *(_DWORD *)(a1 + 11968);
    v14 = v36[(unsigned __int64)v13 >> 24];
    if ( v14 >= 0 )
      goto LABEL_7;
    v30 = 0x800000;
    while ( 1 )
    {
      v31 = 2 * (__int16)-v14;
      if ( (v13 & v30) != 0 )
      {
        if ( (unsigned int)(v31 + 1) >= 0x5E )
        {
          v14 = 0;
          *(_DWORD *)(a1 + 11980) = 1;
        }
        else
        {
          v14 = v35[v31 + 1];
        }
      }
      else
      {
        if ( (unsigned int)v31 >= 0x5E )
        {
          v14 = 0;
          *(_DWORD *)(a1 + 11980) = 1;
LABEL_7:
          if ( (unsigned __int16)v14 >= 0x18u )
            goto LABEL_19;
          if ( *(_DWORD *)(a1 + 11980) )
            return 0;
          fillbuf(a1, v34[(unsigned __int16)v14]);
          if ( *(_DWORD *)(a1 + 11980) )
            return 0;
          if ( v14 == 17 )
          {
            v20 = *(_DWORD *)(a1 + 11968) >> 28;
            fillbuf(a1, 4);
            v21 = v20 + 4;
            v22 = v12 + v20 + 4;
            v23 = a2 - v12;
            if ( v22 < a2 )
              v23 = v21;
            if ( v23 > 0 )
            {
              memset((void *)(a4 + v12), 0, v23);
              do
              {
                --v23;
                ++v12;
              }
              while ( v23 > 0 );
            }
            goto LABEL_24;
          }
          if ( v14 == 18 )
          {
            v26 = *(_DWORD *)(a1 + 11968) >> 27;
            fillbuf(a1, 5);
            v27 = v26 + 20;
            v28 = v12 + v26 + 20;
            v29 = a2 - v12;
            if ( v28 < a2 )
              v29 = v27;
            if ( v29 > 0 )
            {
              memset((void *)(a4 + v12), 0, v29);
              do
              {
                --v29;
                ++v12;
              }
              while ( v29 > 0 );
            }
LABEL_24:
            --v12;
            goto LABEL_14;
          }
          if ( v14 != 19 )
          {
            *(_BYTE *)(v12 + a4) = *((_BYTE *)&qword_140013210[2]
                                   + *(unsigned __int8 *)(v12 + a3)
                                   - (unsigned __int64)(unsigned __int16)v14
                                   + 1);
            goto LABEL_14;
          }
          v15 = *(_DWORD *)(a1 + 11968) >> 31;
          fillbuf(a1, 1);
          v16 = *(_DWORD *)(a1 + 11968);
          v17 = a2 - v12;
          if ( v12 + v15 + 4 < a2 )
            v17 = v15 + 4;
          v18 = v36[(unsigned __int64)v16 >> 24];
          if ( v18 < 0 )
          {
            v32 = 0x800000;
            do
            {
              v33 = 2 * (__int16)-v18;
              if ( (v16 & v32) != 0 )
              {
                if ( (unsigned int)(v33 + 1) >= 0x5E )
                {
                  v18 = 0;
                  *(_DWORD *)(a1 + 11980) = 1;
                }
                else
                {
                  v18 = v35[v33 + 1];
                }
              }
              else
              {
                if ( (unsigned int)v33 >= 0x5E )
                {
                  v18 = 0;
                  *(_DWORD *)(a1 + 11980) = 1;
                  break;
                }
                v18 = v35[v33];
              }
              v32 >>= 1;
            }
            while ( v18 < 0 );
          }
          if ( (unsigned __int16)v18 >= 0x18u )
          {
LABEL_19:
            *(_DWORD *)(a1 + 11980) = 1;
            return 0;
          }
          if ( *(_DWORD *)(a1 + 11980) )
            return 0;
          fillbuf(a1, v34[(unsigned __int16)v18]);
          if ( *(_DWORD *)(a1 + 11980) )
            return 0;
          if ( v17 > 0 )
          {
            v24 = *((_BYTE *)&qword_140013210[2]
                  + *(unsigned __int8 *)(v12 + a3)
                  - (unsigned __int64)(unsigned __int16)v18
                  + 1);
            do
            {
              if ( v12 >= a2 )
                break;
              v25 = v12;
              --v17;
              ++v12;
              *(_BYTE *)(v25 + a4) = v24;
            }
            while ( v17 > 0 );
          }
          --v12;
LABEL_14:
          ++v12;
          goto LABEL_5;
        }
        v14 = v35[v31];
      }
      v30 >>= 1;
      if ( v14 >= 0 )
        goto LABEL_7;
    }
  }
  return *(_DWORD *)(a1 + 11980) == 0;
}

```

## disassembly

```asm
0x140002b50  mov     [rsp-8+arg_8], rbx
0x140002b55  push    rbp
0x140002b56  push    rsi
0x140002b57  push    rdi
0x140002b58  push    r12
0x140002b5a  push    r13
0x140002b5c  push    r14
0x140002b5e  push    r15
0x140002b60  lea     rbp, [rsp-220h]
0x140002b68  sub     rsp, 320h
0x140002b6f  mov     rax, cs:__security_cookie
0x140002b76  xor     rax, rsp
0x140002b79  mov     [rbp+250h+var_40], rax
0x140002b80  xor     r14d, r14d
0x140002b83  mov     r12, r9
0x140002b86  mov     edi, r14d
0x140002b89  mov     r13, r8
0x140002b8c  mov     r15d, edx
0x140002b8f  mov     rsi, rcx
0x140002b92  mov     ebx, [rsi+2EC0h]
0x140002b98  mov     edx, 4
0x140002b9d  mov     rcx, rsi
0x140002ba0  shr     ebx, 1Ch
0x140002ba3  call    fillbuf
0x140002ba8  mov     [rsp+rdi+350h+var_320], bl
0x140002bac  inc     rdi
0x140002baf  cmp     rdi, 14h
0x140002bb3  jnz     short loc_140002B92
0x140002bb5  cmp     [rsi+2ECCh], r14d
0x140002bbc  jnz     loc_140002CE2
0x140002bc2  lea     rax, [rsp+350h+var_300]
0x140002bc7  mov     r9b, 8; int
0x140002bca  mov     [rsp+350h+var_328], rax; __int64
0x140002bcf  lea     r8, [rsp+350h+var_320]; int
0x140002bd4  lea     rax, [rbp+250h+var_240]
0x140002bd8  mov     edx, edi; int
0x140002bda  mov     [rsp+350h+var_330], rax; void *
0x140002bdf  call    make_table
0x140002be4  lea     r9, qword_140013210
0x140002beb  mov     edi, r14d
0x140002bee  cmp     edi, r15d
0x140002bf1  jge     loc_140002E01
0x140002bf7  mov     r8d, [rsi+2EC0h]
0x140002bfe  mov     eax, r8d
0x140002c01  shr     rax, 18h
0x140002c05  movzx   ebx, [rbp+rax*2+250h+var_240]
0x140002c0a  test    bx, bx
0x140002c0d  js      loc_140002E13
0x140002c13  cmp     bx, 18h
0x140002c17  jnb     loc_140002CD8
0x140002c1d  mov     eax, [rsi+2ECCh]
0x140002c23  test    eax, eax
0x140002c25  jnz     loc_140002CE2
0x140002c2b  movzx   eax, bx
0x140002c2e  mov     rcx, rsi
0x140002c31  movzx   edx, [rsp+rax+350h+var_320]
0x140002c36  call    fillbuf
0x140002c3b  mov     eax, [rsi+2ECCh]
0x140002c41  lea     r9, qword_140013210
0x140002c48  test    eax, eax
0x140002c4a  jnz     loc_140002CE2
0x140002c50  cmp     bx, 11h
0x140002c54  jz      loc_140002D0F
0x140002c5a  cmp     bx, 12h
0x140002c5e  jz      loc_140002DB3
0x140002c64  cmp     bx, 13h
0x140002c68  jz      short loc_140002C88
0x140002c6a  movsxd  rdx, edi
0x140002c6d  movzx   eax, bx
0x140002c70  movzx   ecx, byte ptr [rdx+r13]
0x140002c75  sub     rcx, rax
0x140002c78  mov     al, [rcx+r9+11h]
0x140002c7d  mov     [rdx+r12], al
0x140002c81  inc     edi
0x140002c83  jmp     loc_140002BEE
0x140002c88  mov     ebx, [rsi+2EC0h]
0x140002c8e  mov     edx, 1
0x140002c93  mov     rcx, rsi
0x140002c96  shr     ebx, 1Fh
0x140002c99  call    fillbuf
0x140002c9e  mov     r8d, [rsi+2EC0h]
0x140002ca5  lea     eax, [rbx+4]
0x140002ca8  lea     ecx, [rbx+4]
0x140002cab  mov     r14d, r15d
0x140002cae  sub     r14d, edi
0x140002cb1  add     ecx, edi
0x140002cb3  cmp     ecx, r15d
0x140002cb6  cmovl   r14d, eax
0x140002cba  mov     eax, r8d
0x140002cbd  shr     rax, 18h
0x140002cc1  xor     r9d, r9d
0x140002cc4  movzx   ebx, [rbp+rax*2+250h+var_240]
0x140002cc9  test    bx, bx
0x140002ccc  js      loc_140002E8F
0x140002cd2  cmp     bx, 18h
0x140002cd6  jb      short loc_140002D4E
0x140002cd8  mov     dword ptr [rsi+2ECCh], 1
0x140002ce2  xor     eax, eax
0x140002ce4  mov     rcx, [rbp+250h+var_40]
0x140002ceb  xor     rcx, rsp; StackCookie
0x140002cee  call    __security_check_cookie
0x140002cf3  mov     rbx, [rsp+350h+arg_8]
0x140002cfb  add     rsp, 320h
0x140002d02  pop     r15
0x140002d04  pop     r14
0x140002d06  pop     r13
0x140002d08  pop     r12
0x140002d0a  pop     rdi
0x140002d0b  pop     rsi
0x140002d0c  pop     rbp
0x140002d0d  retn
0x140002d0f  mov     ebx, [rsi+2EC0h]
0x140002d15  mov     edx, 4
0x140002d1a  mov     rcx, rsi
0x140002d1d  shr     ebx, 1Ch
0x140002d20  call    fillbuf
0x140002d25  lea     ecx, [rbx+4]
0x140002d28  lea     eax, [rbx+4]
0x140002d2b  add     ecx, edi
0x140002d2d  mov     ebx, r15d
0x140002d30  sub     ebx, edi
0x140002d32  cmp     ecx, r15d
0x140002d35  cmovl   ebx, eax
0x140002d38  test    ebx, ebx
0x140002d3a  jg      loc_140002E72
0x140002d40  dec     edi
0x140002d42  lea     r9, qword_140013210
0x140002d49  jmp     loc_140002C81
0x140002d4e  mov     eax, [rsi+2ECCh]
0x140002d54  test    eax, eax
0x140002d56  jnz     short loc_140002CE2
0x140002d58  movzx   eax, bx
0x140002d5b  mov     rcx, rsi
0x140002d5e  movzx   edx, [rsp+rax+350h+var_320]
0x140002d63  call    fillbuf
0x140002d68  mov     eax, [rsi+2ECCh]
0x140002d6e  test    eax, eax
0x140002d70  jnz     loc_140002CE2
0x140002d76  test    r14d, r14d
0x140002d79  jg      short loc_140002D82
0x140002d7b  dec     edi
0x140002d7d  xor     r14d, r14d
0x140002d80  jmp     short loc_140002D42
0x140002d82  movsxd  rax, edi
0x140002d85  lea     rdx, qword_140013210
0x140002d8c  movzx   ecx, byte ptr [rax+r13]
0x140002d91  movzx   eax, bx
0x140002d94  sub     rcx, rax
0x140002d97  mov     dl, [rcx+rdx+11h]
0x140002d9b  cmp     edi, r15d
0x140002d9e  jge     short loc_140002D7B
0x140002da0  movsxd  rax, edi
0x140002da3  dec     r14d
0x140002da6  inc     edi
0x140002da8  mov     [rax+r12], dl
0x140002dac  test    r14d, r14d
0x140002daf  jg      short loc_140002D9B
0x140002db1  jmp     short loc_140002D7B
0x140002db3  mov     ebx, [rsi+2EC0h]
0x140002db9  mov     edx, 5
0x140002dbe  mov     rcx, rsi
0x140002dc1  shr     ebx, 1Bh
0x140002dc4  call    fillbuf
0x140002dc9  lea     ecx, [rbx+14h]
0x140002dcc  lea     eax, [rbx+14h]
0x140002dcf  add     ecx, edi
0x140002dd1  mov     ebx, r15d
0x140002dd4  sub     ebx, edi
0x140002dd6  cmp     ecx, r15d
0x140002dd9  cmovl   ebx, eax
0x140002ddc  test    ebx, ebx
0x140002dde  jle     loc_140002D40
0x140002de4  movsxd  rcx, edi
0x140002de7  xor     edx, edx; Val
0x140002de9  add     rcx, r12; void *
0x140002dec  movsxd  r8, ebx; Size
0x140002def  call    memset
0x140002df4  dec     ebx
0x140002df6  inc     edi
0x140002df8  test    ebx, ebx
0x140002dfa  jg      short loc_140002DF4
0x140002dfc  jmp     loc_140002D40
0x140002e01  cmp     [rsi+2ECCh], r14d
0x140002e08  mov     eax, r14d
0x140002e0b  setz    al
0x140002e0e  jmp     loc_140002CE4
0x140002e13  mov     edx, 800000h
0x140002e18  neg     bx
0x140002e1b  movsx   eax, bx
0x140002e1e  lea     ecx, [rax+rax]
0x140002e21  test    edx, r8d
0x140002e24  jz      short loc_140002E47
0x140002e26  lea     eax, [rcx+1]
0x140002e29  cmp     eax, 5Eh ; '^'
0x140002e2c  jnb     short loc_140002E38
0x140002e2e  movsxd  rax, ecx
0x140002e31  movzx   ebx, [rsp+rax*2+350h+var_300+2]
0x140002e36  jmp     short loc_140002E54
0x140002e38  mov     ebx, r14d
0x140002e3b  mov     dword ptr [rsi+2ECCh], 1
0x140002e45  jmp     short loc_140002E54
0x140002e47  cmp     ecx, 5Eh ; '^'
0x140002e4a  jnb     short loc_140002E60
0x140002e4c  movsxd  rax, ecx
0x140002e4f  movzx   ebx, [rsp+rax*2+350h+var_300]
0x140002e54  shr     edx, 1
0x140002e56  test    bx, bx
0x140002e59  js      short loc_140002E18
0x140002e5b  jmp     loc_140002C13
0x140002e60  mov     ebx, r14d
0x140002e63  mov     dword ptr [rsi+2ECCh], 1
0x140002e6d  jmp     loc_140002C13
0x140002e72  movsxd  rcx, edi
0x140002e75  xor     edx, edx; Val
0x140002e77  add     rcx, r12; void *
0x140002e7a  movsxd  r8, ebx; Size
0x140002e7d  call    memset
0x140002e82  dec     ebx
0x140002e84  inc     edi
0x140002e86  test    ebx, ebx
0x140002e88  jg      short loc_140002E82
0x140002e8a  jmp     loc_140002D40
0x140002e8f  mov     edx, 800000h
0x140002e94  neg     bx
0x140002e97  movsx   eax, bx
0x140002e9a  lea     ecx, [rax+rax]
0x140002e9d  test    edx, r8d
0x140002ea0  jz      short loc_140002EC3
0x140002ea2  lea     eax, [rcx+1]
0x140002ea5  cmp     eax, 5Eh ; '^'
0x140002ea8  jnb     short loc_140002EB4
0x140002eaa  movsxd  rax, ecx
0x140002ead  movzx   ebx, [rsp+rax*2+350h+var_300+2]
0x140002eb2  jmp     short loc_140002ED0
0x140002eb4  mov     ebx, r9d
0x140002eb7  mov     dword ptr [rsi+2ECCh], 1
0x140002ec1  jmp     short loc_140002ED0
0x140002ec3  cmp     ecx, 5Eh ; '^'
0x140002ec6  jnb     short loc_140002EDC
0x140002ec8  movsxd  rax, ecx
0x140002ecb  movzx   ebx, [rsp+rax*2+350h+var_300]
0x140002ed0  shr     edx, 1
0x140002ed2  test    bx, bx
0x140002ed5  js      short loc_140002E94
0x140002ed7  jmp     loc_140002CD2
0x140002edc  mov     ebx, r9d
0x140002edf  mov     dword ptr [rsi+2ECCh], 1
0x140002ee9  jmp     loc_140002CD2
```
