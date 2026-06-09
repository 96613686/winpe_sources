# _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)

- ea: `0x180019ff0`
- end: `0x18001a12b`
- name: `??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z`
- size: `315`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003c70`
- `0x180006990`
- `0x18000e834`
- `0x18000f54c`
- `0x180019428`
- `0x180019ed0`
- `0x180024594`
- `0x180043438`
- `0x180046b28`
- `0x1800473b0`

## callees

- `0x180019ff0`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a03d`

## pseudocode

```c
__int64 __fastcall _AllocString<CTCoAllocPolicy>(__int64 a1, __int64 a2, __int64 *a3, _QWORD *a4)
{
  unsigned __int64 v4; // rsi
  unsigned __int64 v7; // rbx
  _WORD *v8; // rax
  _WORD *v9; // rdx
  unsigned int v10; // edi
  __int64 *v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  _WORD *v14; // r9
  __int64 v15; // r11
  _WORD *v16; // rcx
  __int64 v17; // r10
  __int64 v19; // rbx
  bool v20; // cf

  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)a3 + v4) );
  v7 = v4 + 1;
  *a4 = 0;
  if ( v4 + 1 < v4 || !is_mul_ok(v7, 2u) )
    return (unsigned int)-2147024362;
  v8 = CoTaskMemAlloc(2 * v7);
  *a4 = v8;
  v9 = v8;
  v10 = v8 == 0 ? 0x8007000E : 0;
  if ( v8 )
  {
    if ( v7 <= 0x7FFFFFFF )
    {
      if ( v4 < 0x7FFFFFFF )
      {
        v11 = &qword_180053B30;
        v12 = v4 & -(__int64)(a3 != 0);
        if ( a3 )
          v11 = a3;
        v13 = v4 + 1;
        v14 = v9;
        v15 = 0;
        do
        {
          if ( !v12 )
            break;
          if ( !*(_WORD *)v11 )
            break;
          *v14 = *(_WORD *)v11;
          v11 = (__int64 *)((char *)v11 + 2);
          ++v14;
          --v12;
          ++v15;
          --v13;
        }
        while ( v13 );
        v16 = v14 - 1;
        v17 = v15 - 1;
        if ( v13 )
        {
          v16 = v14;
          v17 = v15;
        }
        *v16 = 0;
        if ( v13 )
        {
          v20 = v7 == v17;
          v19 = v7 - v17;
          if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
            memset_0(&v9[v17 + 1], 0, 2 * v19 - 2);
        }
        return v10;
      }
      if ( v4 == -1 )
        return v10;
    }
    *v8 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180019ff0  mov     [rsp+arg_8], rbx
0x180019ff5  mov     [rsp+arg_10], rbp
0x180019ffa  push    rsi
0x180019ffb  push    rdi
0x180019ffc  push    r14
0x180019ffe  sub     rsp, 20h
0x18001a002  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a006  mov     rdi, r9
0x18001a009  xor     r14d, r14d
0x18001a00c  mov     rbp, r8
0x18001a00f  inc     rsi
0x18001a012  cmp     [r8+rsi*2], r14w
0x18001a017  jnz     short loc_18001A00F
0x18001a019  lea     rbx, [rsi+1]
0x18001a01d  mov     [r9], r14
0x18001a020  cmp     rbx, rsi
0x18001a023  jb      loc_18001A0F2
0x18001a029  mov     eax, 2
0x18001a02e  mul     rbx
0x18001a031  test    rdx, rdx
0x18001a034  jnz     loc_18001A0F2
0x18001a03a  mov     rcx, rax; cb
0x18001a03d  call    cs:__imp_CoTaskMemAlloc
0x18001a043  mov     [rdi], rax
0x18001a046  mov     rcx, rax
0x18001a049  neg     rcx
0x18001a04c  mov     rdx, rax
0x18001a04f  sbb     edi, edi
0x18001a051  not     edi
0x18001a053  and     edi, 8007000Eh
0x18001a059  test    rax, rax
0x18001a05c  jz      short loc_18001A0DD
0x18001a05e  mov     eax, 7FFFFFFFh
0x18001a063  cmp     rbx, rax
0x18001a066  ja      loc_18001A125
0x18001a06c  cmp     rsi, rax
0x18001a06f  jnb     loc_18001A120
0x18001a075  mov     rax, rbp
0x18001a078  neg     rax
0x18001a07b  lea     rax, qword_180053B30
0x18001a082  sbb     rcx, rcx
0x18001a085  and     rcx, rsi
0x18001a088  test    rbp, rbp
0x18001a08b  cmovnz  rax, rbp
0x18001a08f  test    rbx, rbx
0x18001a092  jz      short loc_18001A0DD
0x18001a094  mov     r8, rbx
0x18001a097  mov     r9, rdx
0x18001a09a  mov     r11, r14
0x18001a09d  test    rcx, rcx
0x18001a0a0  jz      short loc_18001A0C4
0x18001a0a2  movzx   r10d, word ptr [rax]
0x18001a0a6  test    r10w, r10w
0x18001a0aa  jz      short loc_18001A0C4
0x18001a0ac  mov     [r9], r10w
0x18001a0b0  add     rax, 2
0x18001a0b4  add     r9, 2
0x18001a0b8  dec     rcx
0x18001a0bb  inc     r11
0x18001a0be  sub     r8, 1
0x18001a0c2  jnz     short loc_18001A09D
0x18001a0c4  test    r8, r8
0x18001a0c7  lea     rcx, [r9-2]
0x18001a0cb  lea     r10, [r11-1]
0x18001a0cf  cmovnz  rcx, r9
0x18001a0d3  cmovnz  r10, r11
0x18001a0d7  mov     [rcx], r14w
0x18001a0db  jnz     short loc_18001A0F9
0x18001a0dd  mov     rbx, [rsp+38h+arg_8]
0x18001a0e2  mov     eax, edi
0x18001a0e4  mov     rbp, [rsp+38h+arg_10]
0x18001a0e9  add     rsp, 20h
0x18001a0ed  pop     r14
0x18001a0ef  pop     rdi
0x18001a0f0  pop     rsi
0x18001a0f1  retn
0x18001a0f2  mov     edi, 80070216h
0x18001a0f7  jmp     short loc_18001A0DD
0x18001a0f9  sub     rbx, r10
0x18001a0fc  cmp     rbx, 1
0x18001a100  jbe     short loc_18001A0DD
0x18001a102  lea     r8, [rbx+rbx]
0x18001a106  cmp     r8, 2
0x18001a10a  jbe     short loc_18001A0DD
0x18001a10c  inc     r10
0x18001a10f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001a113  lea     rcx, [rdx+r10*2]; void *
0x18001a117  xor     edx, edx; Val
0x18001a119  call    memset_0
0x18001a11e  jmp     short loc_18001A0DD
0x18001a120  test    rbx, rbx
0x18001a123  jz      short loc_18001A0DD
0x18001a125  mov     [rdx], r14w
0x18001a129  jmp     short loc_18001A0DD
```
