# BsetUQMTrue

- ea: `0x180070b74`
- end: `0x180070c4e`
- name: `BsetUQMTrue`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800709a8`

## callees

- `0x180007220`
- `0x18000aef4`
- `0x180070b74`

## string_xrefs

- `0x180070bfc`: `Warning: unexpected value atrUpdateQualityMacro ATREEREF`
- `0x180070bf5`: `Warning: atrUpdateQualityMacro ATREEREF points to a tree.                     Unexpected Condition\n`

## pseudocode

```c
__int64 __fastcall BsetUQMTrue(unsigned int a1, __int64 a2)
{
  unsigned int v2; // esi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  const char *v10; // rdx
  int v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = 1;
  v11 = 1;
  v4 = *(_QWORD *)(a2 + 264) + 396LL * a1;
  v5 = *(unsigned int *)(v4 + 60);
  if ( (_DWORD)v5 == 0x7FFFFFFF )
  {
    result = BwriteToHeap((_DWORD *)(v4 + 60), &v11, *(_DWORD *)(a2 + 2336), 4u, a2);
    if ( (_DWORD)result )
      *(_DWORD *)(v4 + 60) |= 0x80000000;
    else
      *(_DWORD *)(v4 + 60) = 0x7FFFFFFF;
  }
  else
  {
    v7 = *(unsigned int *)(v4 + 60);
    if ( (int)v5 >= 0 )
    {
      v8 = 5 * v5;
      v9 = *(_QWORD *)(a2 + 72);
      v10 = "Warning: unexpected value atrUpdateQualityMacro ATREEREF";
      if ( *(_DWORD *)(v9 + 4 * v8) != -1 )
        v10 = "Warning: atrUpdateQualityMacro ATREEREF points to a tree.                     Unexpected Condition\n";
      WriteDbgTraceErrorGpd("BsetUQMTrue", v10);
      WriteDbgTraceErrorGpd("BsetUQMTrue", "Unexpected condition encountered while processing Quality Macros ");
      *(_DWORD *)(a2 + 2224) = 1;
      v2 = 0;
      *(_DWORD *)(a2 + 2220) = 3;
    }
    else
    {
      LODWORD(v7) = v7 & 0x7FFFFFFF;
      *(_DWORD *)(v7 + *(_QWORD *)a2) = 1;
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180070b74  mov     r11, rsp
0x180070b77  mov     [r11+10h], rbx
0x180070b7b  mov     [r11+18h], rsi
0x180070b7f  push    rdi
0x180070b80  sub     rsp, 30h
0x180070b84  mov     eax, ecx
0x180070b86  mov     esi, 1
0x180070b8b  imul    rbx, rax, 18Ch
0x180070b92  mov     rdi, rdx
0x180070b95  mov     [rsp+38h+arg_0], esi
0x180070b99  add     rbx, [rdx+108h]
0x180070ba0  mov     eax, [rbx+3Ch]
0x180070ba3  cmp     eax, 7FFFFFFFh
0x180070ba8  jnz     short loc_180070BDA
0x180070baa  mov     r8d, [rdx+920h]
0x180070bb1  lea     r9d, [rsi+3]
0x180070bb5  mov     [r11-18h], rdx
0x180070bb9  lea     rcx, [rbx+3Ch]
0x180070bbd  lea     rdx, [r11+8]
0x180070bc1  call    BwriteToHeap
0x180070bc6  test    eax, eax
0x180070bc8  jz      short loc_180070BD1
0x180070bca  bts     dword ptr [rbx+3Ch], 1Fh
0x180070bcf  jmp     short loc_180070C3E
0x180070bd1  mov     dword ptr [rbx+3Ch], 7FFFFFFFh
0x180070bd8  jmp     short loc_180070C3E
0x180070bda  mov     rcx, rax
0x180070bdd  test    eax, eax
0x180070bdf  jns     short loc_180070BED
0x180070be1  mov     rax, [rdx]
0x180070be4  btr     ecx, 1Fh
0x180070be8  mov     [rcx+rax], esi
0x180070beb  jmp     short loc_180070C3C
0x180070bed  lea     rcx, [rax+rax*4]
0x180070bf1  mov     rax, [rdx+48h]
0x180070bf5  lea     r8, aWarningAtrupda; "Warning: atrUpdateQualityMacro ATREEREF"...
0x180070bfc  lea     rdx, aWarningUnexpec; "Warning: unexpected value atrUpdateQual"...
0x180070c03  cmp     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x180070c07  lea     rcx, aBsetuqmtrue; "BsetUQMTrue"
0x180070c0e  cmovnz  rdx, r8
0x180070c12  call    WriteDbgTraceErrorGpd
0x180070c17  lea     rdx, aUnexpectedCond; "Unexpected condition encountered while "...
0x180070c1e  lea     rcx, aBsetuqmtrue; "BsetUQMTrue"
0x180070c25  call    WriteDbgTraceErrorGpd
0x180070c2a  mov     [rdi+8B0h], esi
0x180070c30  xor     esi, esi
0x180070c32  mov     dword ptr [rdi+8ACh], 3
0x180070c3c  mov     eax, esi
0x180070c3e  mov     rbx, [rsp+38h+arg_8]
0x180070c43  mov     rsi, [rsp+38h+arg_10]
0x180070c48  add     rsp, 30h
0x180070c4c  pop     rdi
0x180070c4d  retn
```
