# IcsRead

- ea: `0x18007e8c0`
- end: `0x18007eaca`
- name: `IcsRead`
- size: `522`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18007d2d0`
- `0x18007d4e0`

## callees

- `0x1800363f0`
- `0x18007e8c0`

## pseudocode

```c
__int64 __fastcall IcsRead(int *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 result; // rax
  char v6; // dl
  unsigned __int8 v7; // al
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax

  if ( !*a1 )
    FillBitCache(a1, 1u);
  *(_BYTE *)(a2 + 1) = ((unsigned int)a1[1] >> --*a1) & 1;
  if ( (unsigned int)*a1 < 2 )
    FillBitCache(a1, 2u);
  *a1 -= 2;
  *(_BYTE *)(a2 + 3) = ((unsigned int)a1[1] >> *a1) & 3;
  if ( !*a1 )
    FillBitCache(a1, 1u);
  *(_BYTE *)(a2 + 2) = ((unsigned int)a1[1] >> --*a1) & 1;
  v4 = 4LL * *(char *)(a2 + 7);
  if ( *(_BYTE *)(a2 + 3) == 2 )
  {
    *(_BYTE *)(a2 + 6) = SamplingRateInfoTable[v4 + 2];
    if ( (unsigned int)*a1 < 4 )
      FillBitCache(a1, 4u);
    *a1 -= 4;
    *(_BYTE *)(a2 + 4) = ((unsigned int)a1[1] >> *a1) & 0xF;
    if ( (unsigned int)*a1 < 7 )
      FillBitCache(a1, 7u);
    *a1 -= 7;
    v6 = ((unsigned int)a1[1] >> *a1) & 0x7F;
    *(_WORD *)(a2 + 9) = 256;
    *(_BYTE *)(a2 + 5) = v6;
    if ( (v6 & 0x40) != 0 )
    {
      *(_BYTE *)(a2 + 10) = 2;
      v7 = 0;
    }
    else
    {
      *(_BYTE *)(a2 + 9) = 1;
      v7 = 1;
    }
    *(_BYTE *)(a2 + 11) = 1;
    if ( (v6 & 0x20) != 0 )
      ++*(_BYTE *)(v7 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v7 + 1;
    *(_BYTE *)(a2 + 12) = 1;
    v8 = *(char *)(a2 + 9);
    if ( (*(_BYTE *)(a2 + 5) & 0x10) != 0 )
      ++*(_BYTE *)(v8 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v8 + 1;
    *(_BYTE *)(a2 + 13) = 1;
    v9 = *(char *)(a2 + 9);
    if ( (*(_BYTE *)(a2 + 5) & 8) != 0 )
      ++*(_BYTE *)(v9 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v9 + 1;
    *(_BYTE *)(a2 + 14) = 1;
    v10 = *(char *)(a2 + 9);
    if ( (*(_BYTE *)(a2 + 5) & 4) != 0 )
      ++*(_BYTE *)(v10 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v10 + 1;
    *(_BYTE *)(a2 + 15) = 1;
    v11 = *(char *)(a2 + 9);
    if ( (*(_BYTE *)(a2 + 5) & 2) != 0 )
      ++*(_BYTE *)(v11 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v11 + 1;
    *(_BYTE *)(a2 + 16) = 1;
    v12 = *(char *)(a2 + 9);
    if ( (*(_BYTE *)(a2 + 5) & 1) != 0 )
      ++*(_BYTE *)(v12 + a2 + 10);
    else
      *(_BYTE *)(a2 + 9) = v12 + 1;
    ++*(_BYTE *)(a2 + 9);
    *(_BYTE *)(a2 + 17) = 1;
    result = 0;
    *(_BYTE *)a2 = 1;
  }
  else
  {
    *(_BYTE *)(a2 + 6) = BYTE4(SamplingRateInfoTable[v4]);
    if ( (unsigned int)*a1 < 6 )
      FillBitCache(a1, 6u);
    *a1 -= 6;
    *(_BYTE *)(a2 + 4) = ((unsigned int)a1[1] >> *a1) & 0x3F;
    if ( !*a1 )
      FillBitCache(a1, 1u);
    if ( (((unsigned int)a1[1] >> --*a1) & 1) != 0 )
    {
      return 6;
    }
    else
    {
      *(_WORD *)(a2 + 9) = 257;
      result = 0;
      *(_BYTE *)a2 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007e8c0  mov     [rsp+arg_0], rbx
0x18007e8c5  push    rdi
0x18007e8c6  sub     rsp, 20h
0x18007e8ca  cmp     dword ptr [rcx], 1
0x18007e8cd  mov     rbx, rdx
0x18007e8d0  mov     rdi, rcx
0x18007e8d3  jnb     short loc_18007E8DF
0x18007e8d5  mov     edx, 1
0x18007e8da  call    FillBitCache
0x18007e8df  dec     dword ptr [rdi]
0x18007e8e1  mov     eax, [rdi+4]
0x18007e8e4  mov     ecx, [rdi]
0x18007e8e6  shr     eax, cl
0x18007e8e8  and     al, 1
0x18007e8ea  mov     [rbx+1], al
0x18007e8ed  cmp     dword ptr [rdi], 2
0x18007e8f0  jnb     short loc_18007E8FF
0x18007e8f2  mov     edx, 2
0x18007e8f7  mov     rcx, rdi
0x18007e8fa  call    FillBitCache
0x18007e8ff  add     dword ptr [rdi], 0FFFFFFFEh
0x18007e902  mov     eax, [rdi+4]
0x18007e905  mov     ecx, [rdi]
0x18007e907  shr     eax, cl
0x18007e909  and     al, 3
0x18007e90b  mov     [rbx+3], al
0x18007e90e  cmp     dword ptr [rdi], 1
0x18007e911  jnb     short loc_18007E920
0x18007e913  mov     edx, 1
0x18007e918  mov     rcx, rdi
0x18007e91b  call    FillBitCache
0x18007e920  dec     dword ptr [rdi]
0x18007e922  mov     eax, [rdi+4]
0x18007e925  mov     ecx, [rdi]
0x18007e927  shr     eax, cl
0x18007e929  lea     rcx, SamplingRateInfoTable
0x18007e930  and     al, 1
0x18007e932  mov     [rbx+2], al
0x18007e935  movsx   rax, byte ptr [rbx+7]
0x18007e93a  shl     rax, 5
0x18007e93e  cmp     byte ptr [rbx+3], 2
0x18007e942  jz      short loc_18007E9B5
0x18007e944  movzx   eax, byte ptr [rax+rcx+4]
0x18007e949  mov     [rbx+6], al
0x18007e94c  cmp     dword ptr [rdi], 6
0x18007e94f  jnb     short loc_18007E95E
0x18007e951  mov     edx, 6
0x18007e956  mov     rcx, rdi
0x18007e959  call    FillBitCache
0x18007e95e  add     dword ptr [rdi], 0FFFFFFFAh
0x18007e961  mov     eax, [rdi+4]
0x18007e964  mov     ecx, [rdi]
0x18007e966  shr     eax, cl
0x18007e968  and     al, 3Fh
0x18007e96a  mov     [rbx+4], al
0x18007e96d  cmp     dword ptr [rdi], 1
0x18007e970  jnb     short loc_18007E97F
0x18007e972  mov     edx, 1
0x18007e977  mov     rcx, rdi
0x18007e97a  call    FillBitCache
0x18007e97f  dec     dword ptr [rdi]
0x18007e981  mov     edx, [rdi+4]
0x18007e984  mov     ecx, [rdi]
0x18007e986  shr     edx, cl
0x18007e988  test    dl, 1
0x18007e98b  jz      short loc_18007E99E
0x18007e98d  mov     eax, 6
0x18007e992  mov     rbx, [rsp+28h+arg_0]
0x18007e997  add     rsp, 20h
0x18007e99b  pop     rdi
0x18007e99c  retn
0x18007e99e  mov     word ptr [rbx+9], 101h
0x18007e9a4  xor     eax, eax
0x18007e9a6  mov     byte ptr [rbx], 1
0x18007e9a9  mov     rbx, [rsp+28h+arg_0]
0x18007e9ae  add     rsp, 20h
0x18007e9b2  pop     rdi
0x18007e9b3  retn
0x18007e9b5  movzx   eax, byte ptr [rax+rcx+10h]
0x18007e9ba  mov     [rbx+6], al
0x18007e9bd  cmp     dword ptr [rdi], 4
0x18007e9c0  jnb     short loc_18007E9CF
0x18007e9c2  mov     edx, 4
0x18007e9c7  mov     rcx, rdi
0x18007e9ca  call    FillBitCache
0x18007e9cf  add     dword ptr [rdi], 0FFFFFFFCh
0x18007e9d2  mov     eax, [rdi+4]
0x18007e9d5  mov     ecx, [rdi]
0x18007e9d7  shr     eax, cl
0x18007e9d9  and     al, 0Fh
0x18007e9db  mov     [rbx+4], al
0x18007e9de  cmp     dword ptr [rdi], 7
0x18007e9e1  jnb     short loc_18007E9F0
0x18007e9e3  mov     edx, 7
0x18007e9e8  mov     rcx, rdi
0x18007e9eb  call    FillBitCache
0x18007e9f0  add     dword ptr [rdi], 0FFFFFFF9h
0x18007e9f3  mov     edx, [rdi+4]
0x18007e9f6  mov     ecx, [rdi]
0x18007e9f8  shr     edx, cl
0x18007e9fa  and     dl, 7Fh
0x18007e9fd  mov     word ptr [rbx+9], 100h
0x18007ea03  mov     [rbx+5], dl
0x18007ea06  test    dl, 40h
0x18007ea09  jz      short loc_18007EA13
0x18007ea0b  mov     byte ptr [rbx+0Ah], 2
0x18007ea0f  xor     al, al
0x18007ea11  jmp     short loc_18007EA19
0x18007ea13  mov     byte ptr [rbx+9], 1
0x18007ea17  mov     al, 1
0x18007ea19  mov     byte ptr [rbx+0Bh], 1
0x18007ea1d  test    dl, 20h
0x18007ea20  jz      short loc_18007EA2B
0x18007ea22  movzx   eax, al
0x18007ea25  inc     byte ptr [rax+rbx+0Ah]
0x18007ea29  jmp     short loc_18007EA30
0x18007ea2b  inc     al
0x18007ea2d  mov     [rbx+9], al
0x18007ea30  mov     byte ptr [rbx+0Ch], 1
0x18007ea34  test    byte ptr [rbx+5], 10h
0x18007ea38  movsx   rax, byte ptr [rbx+9]
0x18007ea3d  jz      short loc_18007EA45
0x18007ea3f  inc     byte ptr [rax+rbx+0Ah]
0x18007ea43  jmp     short loc_18007EA4A
0x18007ea45  inc     al
0x18007ea47  mov     [rbx+9], al
0x18007ea4a  mov     byte ptr [rbx+0Dh], 1
0x18007ea4e  test    byte ptr [rbx+5], 8
0x18007ea52  movsx   rax, byte ptr [rbx+9]
0x18007ea57  jz      short loc_18007EA5F
0x18007ea59  inc     byte ptr [rax+rbx+0Ah]
0x18007ea5d  jmp     short loc_18007EA64
0x18007ea5f  inc     al
0x18007ea61  mov     [rbx+9], al
0x18007ea64  mov     byte ptr [rbx+0Eh], 1
0x18007ea68  test    byte ptr [rbx+5], 4
0x18007ea6c  movsx   rax, byte ptr [rbx+9]
0x18007ea71  jz      short loc_18007EA79
0x18007ea73  inc     byte ptr [rax+rbx+0Ah]
0x18007ea77  jmp     short loc_18007EA7E
0x18007ea79  inc     al
0x18007ea7b  mov     [rbx+9], al
0x18007ea7e  mov     byte ptr [rbx+0Fh], 1
0x18007ea82  test    byte ptr [rbx+5], 2
0x18007ea86  movsx   rax, byte ptr [rbx+9]
0x18007ea8b  jz      short loc_18007EA93
0x18007ea8d  inc     byte ptr [rax+rbx+0Ah]
0x18007ea91  jmp     short loc_18007EA98
0x18007ea93  inc     al
0x18007ea95  mov     [rbx+9], al
0x18007ea98  mov     byte ptr [rbx+10h], 1
0x18007ea9c  test    byte ptr [rbx+5], 1
0x18007eaa0  movsx   rax, byte ptr [rbx+9]
0x18007eaa5  jz      short loc_18007EAAD
0x18007eaa7  inc     byte ptr [rax+rbx+0Ah]
0x18007eaab  jmp     short loc_18007EAB2
0x18007eaad  inc     al
0x18007eaaf  mov     [rbx+9], al
0x18007eab2  inc     byte ptr [rbx+9]
0x18007eab5  mov     byte ptr [rbx+11h], 1
0x18007eab9  xor     eax, eax
0x18007eabb  mov     byte ptr [rbx], 1
0x18007eabe  mov     rbx, [rsp+28h+arg_0]
0x18007eac3  add     rsp, 20h
0x18007eac7  pop     rdi
0x18007eac8  retn
```
