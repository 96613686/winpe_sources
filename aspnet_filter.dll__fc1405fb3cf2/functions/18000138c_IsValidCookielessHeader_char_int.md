# IsValidCookielessHeader(char *,int)

- ea: `0x18000138c`
- end: `0x18000142e`
- name: `?IsValidCookielessHeader@@YAHPEADH@Z`
- size: `162`
- prototype: `_BOOL8 __fastcall(char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x180001330`
- `0x180001364`
- `0x18000138c`

## pseudocode

```c
_BOOL8 __fastcall IsValidCookielessHeader(char *a1, int a2)
{
  __int64 v2; // rsi
  int v3; // edi
  __int64 v5; // rbx
  int v6; // edi
  __int64 i; // rbx
  char v8; // cl

  v2 = a2;
  v3 = 0;
  if ( a2 >= 3 )
  {
    if ( a2 == 24 && IsLegit(a1) )
      return 1;
    if ( v2 - 3 >= 0 )
    {
      v5 = 0;
LABEL_6:
      if ( (unsigned __int8)(a1[v5] - 65) <= 0x19u && a1[v5 + 1] == 40 )
      {
        v6 = v3 + 2;
        for ( i = v5 + 2; i < v2; ++i )
        {
          v8 = a1[i];
          if ( v8 == 41 )
          {
            v3 = v6 + 1;
            v5 = i + 1;
            if ( v5 <= v2 - 3 )
              goto LABEL_6;
            return v3 >= (int)v2;
          }
          if ( !(unsigned int)IsV2LegalChar(v8) )
            return 0;
          ++v6;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000138c  mov     [rsp+arg_0], rbx
0x180001391  mov     [rsp+arg_8], rbp
0x180001396  mov     [rsp+arg_10], rsi
0x18000139b  push    rdi
0x18000139c  push    r14
0x18000139e  push    r15
0x1800013a0  sub     rsp, 20h
0x1800013a4  movsxd  rsi, edx
0x1800013a7  xor     edi, edi
0x1800013a9  mov     rbp, rcx
0x1800013ac  cmp     esi, 3
0x1800013af  jl      short loc_180001413
0x1800013b1  cmp     esi, 18h
0x1800013b4  jnz     short loc_1800013BF
0x1800013b6  call    ?IsLegit@@YA_NPEAD@Z; IsLegit(char *)
0x1800013bb  test    al, al
0x1800013bd  jnz     short loc_18000140C
0x1800013bf  mov     r14, rsi
0x1800013c2  sub     r14, 3
0x1800013c6  js      short loc_180001413
0x1800013c8  xor     ebx, ebx
0x1800013ca  mov     al, [rbx+rbp]
0x1800013cd  sub     al, 41h ; 'A'
0x1800013cf  cmp     al, 19h
0x1800013d1  ja      short loc_180001413
0x1800013d3  cmp     byte ptr [rbx+rbp+1], 28h ; '('
0x1800013d8  jnz     short loc_180001413
0x1800013da  add     edi, 2
0x1800013dd  add     rbx, 2
0x1800013e1  cmp     rbx, rsi
0x1800013e4  jge     short loc_180001413
0x1800013e6  mov     cl, [rbx+rbp]; char
0x1800013e9  cmp     cl, 29h ; ')'
0x1800013ec  jz      short loc_1800013FE
0x1800013ee  call    ?IsV2LegalChar@@YAHD@Z; IsV2LegalChar(char)
0x1800013f3  test    eax, eax
0x1800013f5  jz      short loc_180001413
0x1800013f7  inc     edi
0x1800013f9  inc     rbx
0x1800013fc  jmp     short loc_1800013E1
0x1800013fe  inc     edi
0x180001400  inc     rbx
0x180001403  cmp     rbx, r14
0x180001406  jle     short loc_1800013CA
0x180001408  cmp     edi, esi
0x18000140a  jl      short loc_180001413
0x18000140c  mov     eax, 1
0x180001411  jmp     short loc_180001415
0x180001413  xor     eax, eax
0x180001415  mov     rbx, [rsp+38h+arg_0]
0x18000141a  mov     rbp, [rsp+38h+arg_8]
0x18000141f  mov     rsi, [rsp+38h+arg_10]
0x180001424  add     rsp, 20h
0x180001428  pop     r15
0x18000142a  pop     r14
0x18000142c  pop     rdi
0x18000142d  retn
```
