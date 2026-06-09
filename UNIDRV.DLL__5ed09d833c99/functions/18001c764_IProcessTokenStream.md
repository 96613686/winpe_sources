# IProcessTokenStream

- ea: `0x18001c764`
- end: `0x18001c965`
- name: `IProcessTokenStream`
- size: `513`
- prototype: `__int64 __fastcall(__int64, __int64, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b83c`
- `0x18003d970`

## callees

- `0x180007150`
- `0x18001c764`
- `0x180049d00`

## string_xrefs

- `0x18001c924`: `IProcessTokenStream, invalid stack pointer`
- `0x18001c92b`: `IProcessTokenStream`

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
          WriteDbgTraceErrorGpd((__int64)"IProcessTokenStream", "IProcessTokenStream, invalid stack pointer", v6, v12);
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
0x18001c764  mov     [rsp-8+arg_0], rbx
0x18001c769  mov     [rsp-8+arg_8], rsi
0x18001c76e  push    rbp
0x18001c76f  push    rdi
0x18001c770  push    r14
0x18001c772  lea     rbp, [rsp-0C0h]
0x18001c77a  sub     rsp, 1C0h
0x18001c781  mov     rax, cs:__security_cookie
0x18001c788  xor     rax, rsp
0x18001c78b  mov     [rbp+0D0h+var_20], rax
0x18001c792  mov     ebx, [r8]
0x18001c795  xor     edi, edi
0x18001c797  mov     r8d, [r8+4]
0x18001c79b  xor     r10d, r10d
0x18001c79e  mov     eax, [rcx+20h]
0x18001c7a1  mov     rsi, r9
0x18001c7a4  mov     r14, rdx
0x18001c7a7  lea     r11, [rax+r8*8]
0x18001c7ab  add     r11, [rcx+60h]
0x18001c7af  mov     [r9], edi
0x18001c7b2  test    ebx, ebx
0x18001c7b4  jz      loc_18001C93B
0x18001c7ba  mov     ecx, [r11+4]
0x18001c7be  movsxd  r9, r10d
0x18001c7c1  movsxd  rdx, r10d
0x18001c7c4  cmp     ecx, 5
0x18001c7c7  jg      loc_18001C89B
0x18001c7cd  jz      loc_18001C884
0x18001c7d3  test    ecx, ecx
0x18001c7d5  jz      loc_18001C868
0x18001c7db  sub     ecx, 1
0x18001c7de  jz      short loc_18001C853
0x18001c7e0  sub     ecx, 1
0x18001c7e3  jz      short loc_18001C82C
0x18001c7e5  sub     ecx, 1
0x18001c7e8  jz      short loc_18001C80D
0x18001c7ea  cmp     ecx, 1
0x18001c7ed  jnz     loc_18001C919
0x18001c7f3  dec     r10d
0x18001c7f6  test    r10d, r10d
0x18001c7f9  jle     loc_18001C924
0x18001c7ff  mov     ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c804  add     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c808  jmp     loc_18001C919
0x18001c80d  dec     r10d
0x18001c810  test    r10d, r10d
0x18001c813  jle     loc_18001C924
0x18001c819  mov     rcx, rdx
0x18001c81c  mov     edx, [rsp+r9*4+1D0h+var_1B4]
0x18001c821  cmp     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c825  jl      short loc_18001C84A
0x18001c827  jmp     loc_18001C919
0x18001c82c  dec     r10d
0x18001c82f  test    r10d, r10d
0x18001c832  jle     loc_18001C924
0x18001c838  mov     rcx, rdx
0x18001c83b  mov     edx, [rsp+r9*4+1D0h+var_1B4]
0x18001c840  cmp     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c844  jle     loc_18001C919
0x18001c84a  mov     [rsp+rcx*4+1D0h+var_1B8], edx
0x18001c84e  jmp     loc_18001C919
0x18001c853  cmp     r10d, 64h ; 'd'
0x18001c857  jge     loc_18001C924
0x18001c85d  mov     eax, [r11]
0x18001c860  mov     rax, [r14+rax*8]
0x18001c864  mov     eax, [rax]
0x18001c866  jmp     short loc_18001C875
0x18001c868  cmp     r10d, 64h ; 'd'
0x18001c86c  jge     loc_18001C924
0x18001c872  mov     eax, [r11]
0x18001c875  movsxd  rcx, r10d
0x18001c878  inc     r10d
0x18001c87b  mov     [rsp+rcx*4+1D0h+var_1B0], eax
0x18001c87f  jmp     loc_18001C919
0x18001c884  dec     r10d
0x18001c887  test    r10d, r10d
0x18001c88a  jle     loc_18001C924
0x18001c890  mov     ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c895  sub     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c899  jmp     short loc_18001C919
0x18001c89b  sub     ecx, 6
0x18001c89e  jz      short loc_18001C903
0x18001c8a0  sub     ecx, 1
0x18001c8a3  jz      short loc_18001C8E7
0x18001c8a5  sub     ecx, 1
0x18001c8a8  jz      short loc_18001C8CB
0x18001c8aa  sub     ecx, 1
0x18001c8ad  jz      short loc_18001C8C3
0x18001c8af  cmp     ecx, 1
0x18001c8b2  jnz     short loc_18001C919
0x18001c8b4  test    r10d, r10d
0x18001c8b7  jz      short loc_18001C924
0x18001c8b9  mov     edi, [rsp+r9*4+1D0h+var_1B4]
0x18001c8be  dec     r10d
0x18001c8c1  jmp     short loc_18001C919
0x18001c8c3  mov     dword ptr [rsi], 1
0x18001c8c9  jmp     short loc_18001C919
0x18001c8cb  dec     r10d
0x18001c8ce  test    r10d, r10d
0x18001c8d1  jle     short loc_18001C924
0x18001c8d3  mov     eax, [rsp+rdx*4+1D0h+var_1B8]
0x18001c8d7  mov     r8, rdx
0x18001c8da  cdq
0x18001c8db  idiv    [rsp+r9*4+1D0h+var_1B4]
0x18001c8e0  mov     [rsp+r8*4+1D0h+var_1B8], edx
0x18001c8e5  jmp     short loc_18001C919
0x18001c8e7  dec     r10d
0x18001c8ea  test    r10d, r10d
0x18001c8ed  jle     short loc_18001C924
0x18001c8ef  mov     eax, [rsp+rdx*4+1D0h+var_1B8]
0x18001c8f3  mov     r8, rdx
0x18001c8f6  cdq
0x18001c8f7  idiv    [rsp+r9*4+1D0h+var_1B4]
0x18001c8fc  mov     [rsp+r8*4+1D0h+var_1B8], eax
0x18001c901  jmp     short loc_18001C919
0x18001c903  dec     r10d
0x18001c906  test    r10d, r10d
0x18001c909  jle     short loc_18001C924
0x18001c90b  mov     ecx, [rsp+rdx*4+1D0h+var_1B8]
0x18001c90f  imul    ecx, [rsp+r9*4+1D0h+var_1B4]
0x18001c915  mov     [rsp+rdx*4+1D0h+var_1B8], ecx
0x18001c919  dec     ebx
0x18001c91b  add     r11, 8
0x18001c91f  jmp     loc_18001C7B2
0x18001c924  lea     rdx, aIprocesstokens_0; "IProcessTokenStream, invalid stack poin"...
0x18001c92b  lea     rcx, aIprocesstokens; "IProcessTokenStream"
0x18001c932  call    WriteDbgTraceErrorGpd
0x18001c937  xor     eax, eax
0x18001c939  jmp     short loc_18001C93D
0x18001c93b  mov     eax, edi
0x18001c93d  mov     rcx, [rbp+0D0h+var_20]
0x18001c944  xor     rcx, rsp; StackCookie
0x18001c947  call    __security_check_cookie
0x18001c94c  lea     r11, [rsp+1D0h+var_10]
0x18001c954  mov     rbx, [r11+20h]
0x18001c958  mov     rsi, [r11+28h]
0x18001c95c  mov     rsp, r11
0x18001c95f  pop     r14
0x18001c961  pop     rdi
0x18001c962  pop     rbp
0x18001c963  retn
```
