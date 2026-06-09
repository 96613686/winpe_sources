# IProcessTokenStream

- ea: `0x18001c3dc`
- end: `0x18001c5dc`
- name: `IProcessTokenStream`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b4bc`
- `0x18003ca04`

## callees

- `0x180007220`
- `0x18001c3dc`
- `0x1800487e0`

## string_xrefs

- `0x18001c59c`: `IProcessTokenStream, invalid stack pointer`
- `0x18001c5a3`: `IProcessTokenStream`

## pseudocode

```c
__int64 __fastcall IProcessTokenStream(__int64 a1, __int64 a2, int *a3, _DWORD *a4)
{
  int v4; // ebx
  unsigned int v5; // edi
  __int64 v6; // r8
  int v7; // r10d
  unsigned int *v10; // r11
  int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // edx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  _DWORD v26[102]; // [rsp+18h] [rbp-E8h]

  v4 = *a3;
  v5 = 0;
  v6 = (unsigned int)a3[1];
  v7 = 0;
  v10 = (unsigned int *)(*(_QWORD *)(a1 + 96) + *(unsigned int *)(a1 + 32) + 8 * v6);
  *a4 = 0;
  while ( v4 )
  {
    v11 = v10[1];
    v12 = v7;
    v13 = v7;
    if ( v11 > 5 )
    {
      v21 = v11 - 6;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 == 1 )
              {
                if ( !v7 )
                  goto LABEL_40;
                v5 = v26[v7-- + 1];
              }
            }
            else
            {
              *a4 = 1;
            }
          }
          else
          {
            if ( --v7 <= 0 )
              goto LABEL_40;
            v6 = v13;
            v26[v13] %= v26[v12 + 1];
          }
        }
        else
        {
          if ( --v7 <= 0 )
            goto LABEL_40;
          v6 = v13;
          v26[v13] /= (int)v26[v12 + 1];
        }
      }
      else
      {
        if ( --v7 <= 0 )
        {
LABEL_40:
          WriteDbgTraceErrorGpd("IProcessTokenStream", "IProcessTokenStream, invalid stack pointer", v6, v12);
          return 0;
        }
        v26[v13] *= v26[v12 + 1];
      }
    }
    else if ( v11 == 5 )
    {
      if ( --v7 <= 0 )
        goto LABEL_40;
      v26[v13] -= v26[v12 + 1];
    }
    else
    {
      if ( !v11 )
      {
        if ( v7 >= 100 )
          goto LABEL_40;
        v19 = *v10;
        goto LABEL_22;
      }
      v14 = v11 - 1;
      if ( !v14 )
      {
        if ( v7 >= 100 )
          goto LABEL_40;
        v19 = **(_DWORD **)(a2 + 8LL * *v10);
LABEL_22:
        v20 = v7++;
        v26[v20 + 2] = v19;
        goto LABEL_39;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( v16 == 1 )
          {
            if ( --v7 <= 0 )
              goto LABEL_40;
            v26[v13] += v26[v12 + 1];
          }
        }
        else
        {
          if ( --v7 <= 0 )
            goto LABEL_40;
          v17 = v13;
          v18 = v26[v12 + 1];
          if ( v26[v17] < v18 )
            goto LABEL_17;
        }
      }
      else
      {
        if ( --v7 <= 0 )
          goto LABEL_40;
        v17 = v13;
        v18 = v26[v12 + 1];
        if ( v26[v17] > v18 )
LABEL_17:
          v26[v17] = v18;
      }
    }
LABEL_39:
    --v4;
    v10 += 2;
  }
  return v5;
}

```

## disassembly

```asm
0x18001c3dc  mov     [rsp-8+arg_0], rbx
0x18001c3e1  mov     [rsp-8+arg_8], rsi
0x18001c3e6  push    rbp
0x18001c3e7  push    rdi
0x18001c3e8  push    r14
0x18001c3ea  lea     rbp, [rsp-0C0h]
0x18001c3f2  sub     rsp, 1C0h
0x18001c3f9  mov     rax, cs:__security_cookie
0x18001c400  xor     rax, rsp
0x18001c403  mov     [rbp+0D0h+var_20], rax
0x18001c40a  mov     ebx, [r8]
0x18001c40d  xor     edi, edi
0x18001c40f  mov     r8d, [r8+4]
0x18001c413  xor     r10d, r10d
0x18001c416  mov     eax, [rcx+20h]
0x18001c419  mov     rsi, r9
0x18001c41c  mov     r14, rdx
0x18001c41f  lea     r11, [rax+r8*8]
0x18001c423  add     r11, [rcx+60h]
0x18001c427  mov     [r9], edi
0x18001c42a  test    ebx, ebx
0x18001c42c  jz      loc_18001C5B3
0x18001c432  mov     ecx, [r11+4]
0x18001c436  movsxd  r9, r10d
0x18001c439  movsxd  rdx, r10d
0x18001c43c  cmp     ecx, 5
0x18001c43f  jg      loc_18001C513
0x18001c445  jz      loc_18001C4FC
0x18001c44b  test    ecx, ecx
0x18001c44d  jz      loc_18001C4E0
0x18001c453  sub     ecx, 1
0x18001c456  jz      short loc_18001C4CB
0x18001c458  sub     ecx, 1
0x18001c45b  jz      short loc_18001C4A4
0x18001c45d  sub     ecx, 1
0x18001c460  jz      short loc_18001C485
0x18001c462  cmp     ecx, 1
0x18001c465  jnz     loc_18001C591
0x18001c46b  dec     r10d
0x18001c46e  test    r10d, r10d
0x18001c471  jle     loc_18001C59C
0x18001c477  mov     ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c47c  add     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c480  jmp     loc_18001C591
0x18001c485  dec     r10d
0x18001c488  test    r10d, r10d
0x18001c48b  jle     loc_18001C59C
0x18001c491  mov     rcx, rdx
0x18001c494  mov     edx, [rsp+r9*4+1D0h+var_1B4]
0x18001c499  cmp     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c49d  jl      short loc_18001C4C2
0x18001c49f  jmp     loc_18001C591
0x18001c4a4  dec     r10d
0x18001c4a7  test    r10d, r10d
0x18001c4aa  jle     loc_18001C59C
0x18001c4b0  mov     rcx, rdx
0x18001c4b3  mov     edx, [rsp+r9*4+1D0h+var_1B4]
0x18001c4b8  cmp     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c4bc  jle     loc_18001C591
0x18001c4c2  mov     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c4c6  jmp     loc_18001C591
0x18001c4cb  cmp     r10d, 64h ; 'd'
0x18001c4cf  jge     loc_18001C59C
0x18001c4d5  mov     eax, [r11]
0x18001c4d8  mov     rax, [r14+rax*8]
0x18001c4dc  mov     eax, [rax]
0x18001c4de  jmp     short loc_18001C4ED
0x18001c4e0  cmp     r10d, 64h ; 'd'
0x18001c4e4  jge     loc_18001C59C
0x18001c4ea  mov     eax, [r11]
0x18001c4ed  movsxd  rcx, r10d
0x18001c4f0  inc     r10d
0x18001c4f3  mov     [rsp+rcx*4+1D0h+var_1B0], eax
0x18001c4f7  jmp     loc_18001C591
0x18001c4fc  dec     r10d
0x18001c4ff  test    r10d, r10d
0x18001c502  jle     loc_18001C59C
0x18001c508  mov     ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c50d  sub     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c511  jmp     short loc_18001C591
0x18001c513  sub     ecx, 6
0x18001c516  jz      short loc_18001C57B
0x18001c518  sub     ecx, 1
0x18001c51b  jz      short loc_18001C55F
0x18001c51d  sub     ecx, 1
0x18001c520  jz      short loc_18001C543
0x18001c522  sub     ecx, 1
0x18001c525  jz      short loc_18001C53B
0x18001c527  cmp     ecx, 1
0x18001c52a  jnz     short loc_18001C591
0x18001c52c  test    r10d, r10d
0x18001c52f  jz      short loc_18001C59C
0x18001c531  mov     edi, [rsp+r9*4+1D0h+var_1B4]
0x18001c536  dec     r10d
0x18001c539  jmp     short loc_18001C591
0x18001c53b  mov     dword ptr [rsi], 1
0x18001c541  jmp     short loc_18001C591
0x18001c543  dec     r10d
0x18001c546  test    r10d, r10d
0x18001c549  jle     short loc_18001C59C
0x18001c54b  mov     eax, [rsp+rdx*4+1D0h+var_1B8]
0x18001c54f  mov     r8, rdx
0x18001c552  cdq
0x18001c553  idiv    [rsp+r9*4+1D0h+var_1B4]
0x18001c558  mov     [rsp+r8*4+1D0h+var_1B8], edx
0x18001c55d  jmp     short loc_18001C591
0x18001c55f  dec     r10d
0x18001c562  test    r10d, r10d
0x18001c565  jle     short loc_18001C59C
0x18001c567  mov     eax, [rsp+rdx*4+1D0h+var_1B8]
0x18001c56b  mov     r8, rdx
0x18001c56e  cdq
0x18001c56f  idiv    [rsp+r9*4+1D0h+var_1B4]
0x18001c574  mov     [rsp+r8*4+1D0h+var_1B8], eax
0x18001c579  jmp     short loc_18001C591
0x18001c57b  dec     r10d
0x18001c57e  test    r10d, r10d
0x18001c581  jle     short loc_18001C59C
0x18001c583  mov     ecx, [rsp+rdx*4+1D0h+var_1B8]
0x18001c587  imul    ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c58d  mov     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c591  dec     ebx
0x18001c593  add     r11, 8
0x18001c597  jmp     loc_18001C42A
0x18001c59c  lea     rdx, aIprocesstokens_0; "IProcessTokenStream, invalid stack poin"...
0x18001c5a3  lea     rcx, aIprocesstokens; "IProcessTokenStream"
0x18001c5aa  call    WriteDbgTraceErrorGpd
0x18001c5af  xor     eax, eax
0x18001c5b1  jmp     short loc_18001C5B5
0x18001c5b3  mov     eax, edi
0x18001c5b5  mov     rcx, [rbp+0D0h+var_20]
0x18001c5bc  xor     rcx, rsp; StackCookie
0x18001c5bf  call    __security_check_cookie
0x18001c5c4  lea     r11, [rsp+1D0h+var_10]
0x18001c5cc  mov     rbx, [r11+20h]
0x18001c5d0  mov     rsi, [r11+28h]
0x18001c5d4  mov     rsp, r11
0x18001c5d7  pop     r14
0x18001c5d9  pop     rdi
0x18001c5da  pop     rbp
0x18001c5db  retn
```
