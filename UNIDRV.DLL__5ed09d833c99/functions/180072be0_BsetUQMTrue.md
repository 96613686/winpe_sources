# BsetUQMTrue

- ea: `0x180072be0`
- end: `0x180072cbb`
- name: `BsetUQMTrue`
- size: `219`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180072a14`

## callees

- `0x180007150`
- `0x18000af00`
- `0x180072be0`

## string_xrefs

- `0x180072c68`: `Warning: unexpected value atrUpdateQualityMacro ATREEREF`
- `0x180072c61`: `Warning: atrUpdateQualityMacro ATREEREF points to a tree.                     Unexpected Condition\n`

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
      WriteDbgTraceErrorGpd((__int64)"BsetUQMTrue", v10);
      WriteDbgTraceErrorGpd((__int64)"BsetUQMTrue", "Unexpected condition encountered while processing Quality Macros ");
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
0x180072be0  mov     r11, rsp
0x180072be3  mov     [r11+10h], rbx
0x180072be7  mov     [r11+18h], rsi
0x180072beb  push    rdi
0x180072bec  sub     rsp, 30h
0x180072bf0  mov     eax, ecx
0x180072bf2  mov     esi, 1
0x180072bf7  imul    rbx, rax, 18Ch
0x180072bfe  mov     rdi, rdx
0x180072c01  mov     [rsp+38h+arg_0], esi
0x180072c05  add     rbx, [rdx+108h]
0x180072c0c  mov     eax, [rbx+3Ch]
0x180072c0f  cmp     eax, 7FFFFFFFh
0x180072c14  jnz     short loc_180072C46
0x180072c16  mov     r8d, [rdx+920h]
0x180072c1d  lea     r9d, [rsi+3]
0x180072c21  mov     [r11-18h], rdx
0x180072c25  lea     rcx, [rbx+3Ch]
0x180072c29  lea     rdx, [r11+8]
0x180072c2d  call    BwriteToHeap
0x180072c32  test    eax, eax
0x180072c34  jz      short loc_180072C3D
0x180072c36  bts     dword ptr [rbx+3Ch], 1Fh
0x180072c3b  jmp     short loc_180072CAA
0x180072c3d  mov     dword ptr [rbx+3Ch], 7FFFFFFFh
0x180072c44  jmp     short loc_180072CAA
0x180072c46  mov     rcx, rax
0x180072c49  test    eax, eax
0x180072c4b  jns     short loc_180072C59
0x180072c4d  mov     rax, [rdx]
0x180072c50  btr     ecx, 1Fh
0x180072c54  mov     [rcx+rax], esi
0x180072c57  jmp     short loc_180072CA8
0x180072c59  lea     rcx, [rax+rax*4]
0x180072c5d  mov     rax, [rdx+48h]
0x180072c61  lea     r8, aWarningAtrupda; "Warning: atrUpdateQualityMacro ATREEREF"...
0x180072c68  lea     rdx, aWarningUnexpec; "Warning: unexpected value atrUpdateQual"...
0x180072c6f  cmp     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x180072c73  lea     rcx, aBsetuqmtrue; "BsetUQMTrue"
0x180072c7a  cmovnz  rdx, r8
0x180072c7e  call    WriteDbgTraceErrorGpd
0x180072c83  lea     rdx, aUnexpectedCond; "Unexpected condition encountered while "...
0x180072c8a  lea     rcx, aBsetuqmtrue; "BsetUQMTrue"
0x180072c91  call    WriteDbgTraceErrorGpd
0x180072c96  mov     [rdi+8B0h], esi
0x180072c9c  xor     esi, esi
0x180072c9e  mov     dword ptr [rdi+8ACh], 3
0x180072ca8  mov     eax, esi
0x180072caa  mov     rbx, [rsp+38h+arg_8]
0x180072caf  mov     rsi, [rsp+38h+arg_10]
0x180072cb4  add     rsp, 30h
0x180072cb8  pop     rdi
0x180072cb9  retn
```
