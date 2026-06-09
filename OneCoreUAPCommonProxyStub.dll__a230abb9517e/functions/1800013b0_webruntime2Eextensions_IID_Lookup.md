# _webruntime2Eextensions_IID_Lookup

- ea: `0x1800013b0`
- end: `0x180001523`
- name: `_webruntime2Eextensions_IID_Lookup`
- size: `371`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800013b0`
- `0x18000b174`

## pseudocode

```c
__int64 __fastcall webruntime2Eextensions_IID_Lookup(__int64 **Buf1, int *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  __int64 **v12; // rcx
  signed __int64 v13; // rax

  v4 = memcmp_0(Buf1, &IID___x_ABI_CWebRuntime_CExtensions_CIExtensionScopeDestroyedEventArgs, 0x10u);
  if ( v4 <= 0 )
  {
    v5 = -1;
    if ( !v4 )
    {
      v5 = 32;
      goto LABEL_16;
    }
  }
  else
  {
    v5 = 2;
  }
  v6 = memcmp_0(Buf1, webruntime2Eextensions_ProxyVtblList[v5 + 16][1], 0x10u);
  if ( v6 < 0 || (v5 += 16, v6) )
  {
    v7 = memcmp_0(Buf1, webruntime2Eextensions_ProxyVtblList[v5 + 8][1], 0x10u);
    if ( v7 < 0 || (v5 += 8, v7) )
    {
      v8 = memcmp_0(Buf1, webruntime2Eextensions_ProxyVtblList[v5 + 4][1], 0x10u);
      if ( v8 < 0 || (v5 += 4, v8) )
      {
        v9 = memcmp_0(Buf1, webruntime2Eextensions_ProxyVtblList[v5 + 2][1], 0x10u);
        if ( v9 < 0 || (v5 += 2, v9) )
        {
          v10 = memcmp_0(Buf1, webruntime2Eextensions_ProxyVtblList[v5 + 1][1], 0x10u);
          if ( v10 < 0 || (++v5, v10) )
          {
            if ( v5 + 1 >= 34 )
              return 0;
            v11 = v5++;
            _mm_lfence();
            v12 = webruntime2Eextensions_ProxyVtblList[v11 + 1][1];
            v13 = (char *)*Buf1 - (char *)*v12;
            if ( *Buf1 == *v12 )
              v13 = (char *)Buf1[1] - (char *)v12[1];
            if ( v13 )
              return 0;
          }
        }
      }
    }
  }
LABEL_16:
  *a2 = v5;
  return 1;
}

```

## disassembly

```asm
0x1800013b0  push    rbx
0x1800013b2  push    rbp
0x1800013b3  push    rsi
0x1800013b4  push    rdi
0x1800013b5  sub     rsp, 28h
0x1800013b9  mov     rsi, rdx
0x1800013bc  mov     r8d, 10h; Size
0x1800013c2  mov     rdx, cs:off_18000F630
0x1800013c9  mov     rdi, rcx
0x1800013cc  mov     rdx, [rdx+8]; Buf2
0x1800013d0  call    memcmp_0
0x1800013d5  test    eax, eax
0x1800013d7  jle     loc_1800014CD
0x1800013dd  mov     ebx, 2
0x1800013e2  movsxd  rdx, ebx
0x1800013e5  lea     rbp, _webruntime2Eextensions_ProxyVtblList
0x1800013ec  mov     r8d, 10h; Size
0x1800013f2  mov     rcx, rdi; Buf1
0x1800013f5  mov     rdx, [rbp+rdx*8+80h]
0x1800013fd  mov     rdx, [rdx+8]; Buf2
0x180001401  call    memcmp_0
0x180001406  test    eax, eax
0x180001408  jns     loc_180001516
0x18000140e  movsxd  rdx, ebx
0x180001411  mov     r8d, 10h; Size
0x180001417  mov     rcx, rdi; Buf1
0x18000141a  mov     rdx, [rbp+rdx*8+40h]
0x18000141f  mov     rdx, [rdx+8]; Buf2
0x180001423  call    memcmp_0
0x180001428  test    eax, eax
0x18000142a  jns     loc_1800014FC
0x180001430  movsxd  rdx, ebx
0x180001433  mov     r8d, 10h; Size
0x180001439  mov     rcx, rdi; Buf1
0x18000143c  mov     rdx, [rbp+rdx*8+20h]
0x180001441  mov     rdx, [rdx+8]; Buf2
0x180001445  call    memcmp_0
0x18000144a  test    eax, eax
0x18000144c  jns     loc_180001509
0x180001452  movsxd  rdx, ebx
0x180001455  mov     r8d, 10h; Size
0x18000145b  mov     rcx, rdi; Buf1
0x18000145e  mov     rdx, [rbp+rdx*8+10h]
0x180001463  mov     rdx, [rdx+8]; Buf2
0x180001467  call    memcmp_0
0x18000146c  test    eax, eax
0x18000146e  jns     short loc_1800014EF
0x180001470  movsxd  rdx, ebx
0x180001473  mov     r8d, 10h; Size
0x180001479  mov     rcx, rdi; Buf1
0x18000147c  mov     rdx, [rbp+rdx*8+8]
0x180001481  mov     rdx, [rdx+8]; Buf2
0x180001485  call    memcmp_0
0x18000148a  test    eax, eax
0x18000148c  js      short loc_180001494
0x18000148e  inc     ebx
0x180001490  test    eax, eax
0x180001492  jz      short loc_1800014DF
0x180001494  lea     ecx, [rbx+1]
0x180001497  cmp     ecx, 22h ; '"'
0x18000149a  jge     short loc_1800014C2
0x18000149c  movsxd  rax, ebx
0x18000149f  mov     ebx, ecx
0x1800014a1  lfence
0x1800014a4  mov     rax, [rbp+rax*8+8]
0x1800014a9  mov     rcx, [rax+8]
0x1800014ad  mov     rax, [rdi]
0x1800014b0  sub     rax, [rcx]
0x1800014b3  jnz     short loc_1800014BD
0x1800014b5  mov     rax, [rdi+8]
0x1800014b9  sub     rax, [rcx+8]
0x1800014bd  test    rax, rax
0x1800014c0  jz      short loc_1800014DF
0x1800014c2  xor     eax, eax
0x1800014c4  add     rsp, 28h
0x1800014c8  pop     rdi
0x1800014c9  pop     rsi
0x1800014ca  pop     rbp
0x1800014cb  pop     rbx
0x1800014cc  retn
0x1800014cd  mov     ebx, 0FFFFFFFFh
0x1800014d2  test    eax, eax
0x1800014d4  jnz     loc_1800013E2
0x1800014da  mov     ebx, 20h ; ' '
0x1800014df  mov     [rsi], ebx
0x1800014e1  mov     eax, 1
0x1800014e6  add     rsp, 28h
0x1800014ea  pop     rdi
0x1800014eb  pop     rsi
0x1800014ec  pop     rbp
0x1800014ed  pop     rbx
0x1800014ee  retn
0x1800014ef  add     ebx, 2
0x1800014f2  test    eax, eax
0x1800014f4  jnz     loc_180001470
0x1800014fa  jmp     short loc_1800014DF
0x1800014fc  add     ebx, 8
0x1800014ff  test    eax, eax
0x180001501  jnz     loc_180001430
0x180001507  jmp     short loc_1800014DF
0x180001509  add     ebx, 4
0x18000150c  test    eax, eax
0x18000150e  jnz     loc_180001452
0x180001514  jmp     short loc_1800014DF
0x180001516  add     ebx, 10h
0x180001519  test    eax, eax
0x18000151b  jnz     loc_18000140E
0x180001521  jmp     short loc_1800014DF
```
