# cbCalcJTExpSize

- ea: `0x180023fb0`
- end: `0x18002414a`
- name: `cbCalcJTExpSize`
- size: `410`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180025a1c`

## callees

- `0x180023fb0`
- `0x18004a668`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023fcf`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023fcf`

## string_xrefs

- `0x180023ff2`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall cbCalcJTExpSize(__int64 a1, __int64 a2, __int64 a3)
{
  const wchar_t *v3; // rdi
  wchar_t *v6; // rax
  const wchar_t *v7; // rax
  __int64 v8; // rax
  bool v9; // zf
  int v10; // r14d
  unsigned int v11; // r15d
  unsigned int *v12; // rbx
  unsigned int i; // ebp
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edi
  _DWORD *v17; // r9
  __int64 v18; // r8
  unsigned int v19; // r11d
  unsigned int v20; // r10d
  __int64 v21; // rdx
  __int64 v22; // rax

  v3 = *(const wchar_t **)(a3 + 40);
  v6 = wcsrchr(v3, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = v3;
  if ( v7 && !wcsicmp(v7, L"PrintConfig.dll") )
  {
    v10 = 94;
  }
  else
  {
    v8 = -1;
    do
      v9 = *(_WORD *)(*(_QWORD *)(a3 + 8) + 2 * v8++ + 2) == 0;
    while ( !v9 );
    v10 = 2 * v8 + 18;
  }
  v11 = *(_DWORD *)(a2 + 24) + *(_DWORD *)(a2 + 28);
  if ( !v11 )
    return 0;
  v12 = (unsigned int *)(*(_QWORD *)(a2 + 328) + *(unsigned int *)(a2 + 32));
  if ( !v12 )
    return 0;
  for ( i = 0; i < v11; ++i )
  {
    if ( v12[11] != 2 )
    {
      v14 = *v12;
      if ( (_DWORD)v14 )
        v15 = *(_QWORD *)(a2 + 320) + v14;
      else
        v15 = 0;
      v16 = v12[13];
      if ( v16 )
        v17 = (_DWORD *)(*(_QWORD *)(a2 + 328) + v12[14]);
      else
        v17 = 0;
      if ( !v15 || !v16 || !v17 )
        return 0;
      v18 = -1;
      do
        v9 = *(_BYTE *)(v15 + v18++ + 1) == 0;
      while ( !v9 );
      v19 = 0;
      v20 = 0;
      while ( v20 < v16 )
      {
        if ( !*v17 )
          return 0;
        v21 = *(_QWORD *)(a2 + 320) + (unsigned int)*v17;
        if ( !v21 )
          return 0;
        v22 = -1;
        do
          ++v22;
        while ( *(_BYTE *)(v21 + v22) );
        ++v20;
        v17 = (_DWORD *)((char *)v17 + v12[12]);
        if ( v19 >= (unsigned int)v22 )
          LODWORD(v22) = v19;
        v19 = v22;
      }
      v10 += v19 + v18 + 2;
    }
    v12 += 21;
  }
  return (v10 + 9) & 0xFFFFFFF8;
}

```

## disassembly

```asm
0x180023fb0  mov     [rsp+arg_10], rbx
0x180023fb5  push    rsi
0x180023fb6  push    rdi
0x180023fb7  push    r15
0x180023fb9  sub     rsp, 20h
0x180023fbd  mov     rdi, [r8+28h]
0x180023fc1  mov     rsi, rdx
0x180023fc4  mov     rcx, rdi; Str
0x180023fc7  mov     edx, 5Ch ; '\'; Ch
0x180023fcc  mov     rbx, r8
0x180023fcf  call    cs:__imp_wcsrchr
0x180023fd6  nop     dword ptr [rax+rax+00h]
0x180023fdb  test    rax, rax
0x180023fde  jz      loc_180024126
0x180023fe4  add     rax, 2
0x180023fe8  mov     [rsp+38h+arg_8], r14
0x180023fed  test    rax, rax
0x180023ff0  jz      short loc_180024009
0x180023ff2  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180023ff9  mov     rcx, rax; String1
0x180023ffc  call    _wcsicmp
0x180024001  test    eax, eax
0x180024003  jz      loc_18002412E
0x180024009  mov     rcx, [rbx+8]
0x18002400d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024014  cmp     word ptr [rcx+rax*2+2], 0
0x18002401a  lea     rax, [rax+1]
0x18002401e  jnz     short loc_180024014
0x180024020  lea     r14d, ds:12h[rax*2]
0x180024028  mov     r15d, [rsi+1Ch]
0x18002402c  mov     [rsp+38h+arg_0], rbp
0x180024031  add     r15d, [rsi+18h]
0x180024035  jz      loc_180024104
0x18002403b  mov     ebx, [rsi+20h]
0x18002403e  add     rbx, [rsi+148h]
0x180024045  jz      loc_180024104
0x18002404b  xor     ebp, ebp
0x18002404d  nop     dword ptr [rax]
0x180024050  cmp     ebp, r15d
0x180024053  jnb     loc_180024141
0x180024059  cmp     dword ptr [rbx+2Ch], 2
0x18002405d  jz      loc_1800240F9
0x180024063  mov     eax, [rbx]
0x180024065  test    eax, eax
0x180024067  jz      loc_18002411F
0x18002406d  add     rax, [rsi+140h]
0x180024074  mov     edi, [rbx+34h]
0x180024077  test    edi, edi
0x180024079  jz      loc_180024139
0x18002407f  mov     r9d, [rbx+38h]
0x180024083  add     r9, [rsi+148h]
0x18002408a  test    rax, rax
0x18002408d  jz      short loc_180024104
0x18002408f  test    edi, edi
0x180024091  jz      short loc_180024104
0x180024093  test    r9, r9
0x180024096  jz      short loc_180024104
0x180024098  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002409f  nop
0x1800240a0  cmp     byte ptr [rax+r8+1], 0
0x1800240a6  lea     r8, [r8+1]
0x1800240aa  jnz     short loc_1800240A0
0x1800240ac  xor     r11d, r11d
0x1800240af  xor     r10d, r10d
0x1800240b2  cmp     r10d, edi
0x1800240b5  jnb     short loc_1800240EE
0x1800240b7  mov     eax, [r9]
0x1800240ba  test    eax, eax
0x1800240bc  jz      short loc_180024104
0x1800240be  mov     edx, eax
0x1800240c0  add     rdx, [rsi+140h]
0x1800240c7  jz      short loc_180024104
0x1800240c9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800240d0  inc     rax
0x1800240d3  cmp     byte ptr [rdx+rax], 0
0x1800240d7  jnz     short loc_1800240D0
0x1800240d9  mov     ecx, [rbx+30h]
0x1800240dc  inc     r10d
0x1800240df  add     r9, rcx
0x1800240e2  cmp     r11d, eax
0x1800240e5  cmovnb  eax, r11d
0x1800240e9  mov     r11d, eax
0x1800240ec  jmp     short loc_1800240B2
0x1800240ee  lea     eax, [r11+r8]
0x1800240f2  add     r14d, 2
0x1800240f6  add     r14d, eax
0x1800240f9  inc     ebp
0x1800240fb  add     rbx, 54h ; 'T'
0x1800240ff  jmp     loc_180024050
0x180024104  xor     eax, eax
0x180024106  mov     r14, [rsp+38h+arg_8]
0x18002410b  mov     rbp, [rsp+38h+arg_0]
0x180024110  mov     rbx, [rsp+38h+arg_10]
0x180024115  add     rsp, 20h
0x180024119  pop     r15
0x18002411b  pop     rdi
0x18002411c  pop     rsi
0x18002411d  retn
0x18002411f  xor     eax, eax
0x180024121  jmp     loc_180024074
0x180024126  mov     rax, rdi
0x180024129  jmp     loc_180023FE8
0x18002412e  mov     r14d, 5Eh ; '^'
0x180024134  jmp     loc_180024028
0x180024139  xor     r9d, r9d
0x18002413c  jmp     loc_18002408A
0x180024141  lea     eax, [r14+9]
0x180024145  and     eax, 0FFFFFFF8h
0x180024148  jmp     short loc_180024106
```
