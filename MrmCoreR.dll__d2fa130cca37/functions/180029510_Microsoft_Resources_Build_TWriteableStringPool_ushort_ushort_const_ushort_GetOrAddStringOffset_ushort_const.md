# Microsoft::Resources::Build::TWriteableStringPool<ushort *,ushort const *,ushort>::GetOrAddStringOffset(ushort const *)

- ea: `0x180029510`
- end: `0x1800296db`
- name: `?GetOrAddStringOffset@?$TWriteableStringPool@PEAGPEBGG@Build@Resources@Microsoft@@QEAAHPEBG@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006de74`

## callees

- `0x180028ad0`
- `0x180029510`
- `0x1800297e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002957e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002969c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002957e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002969c`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::TWriteableStringPool<unsigned short *,unsigned short const *,unsigned short>::GetOrAddStringOffset(
        __int64 a1,
        const WCHAR *a2)
{
  const WCHAR *v2; // rsi
  int i; // ebx
  int v5; // eax
  const WCHAR *v6; // r8
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  __int64 v12; // rcx
  unsigned int v14; // edx
  int v15; // r14d
  unsigned int v16; // ecx
  unsigned int v17; // ebx
  __int64 v18; // r10
  __int64 v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // r8
  _WORD *v22; // r9
  _WORD *v23; // rdx
  int v24; // eax

  v2 = a2;
  if ( !a2 || !*a2 )
    return 0;
  for ( i = 1; ; ++i )
  {
    v5 = *(_DWORD *)(a1 + 16);
    if ( i >= v5 )
      break;
    v6 = (const WCHAR *)(*(_QWORD *)(a1 + 24) + 2LL * i);
    if ( *v2 != *v6 )
      continue;
    v7 = *(_DWORD *)(a1 + 12);
    if ( v7 )
    {
      if ( v7 != 1 )
        continue;
      v8 = CompareStringOrdinal(v2, -1, v6, -1, 1);
      v9 = v8 - 2;
      if ( v8 == -2147483647 )
      {
        v10 = 0x7FFFFFFF;
      }
      else if ( v9 < 0 )
      {
        v10 = -1;
      }
      else
      {
        v10 = v9 > 0;
      }
    }
    else
    {
      v24 = CompareStringOrdinal(v2, -1, v6, -1, 0);
      v10 = IntToComparison((unsigned int)(v24 - 2));
    }
    if ( !v10 )
      return (unsigned int)i;
  }
  v12 = -1;
  while ( v2[++v12] != 0 )
    ;
  v14 = *(_DWORD *)(a1 + 20);
  v15 = v12 + 1;
  v16 = v12 + 1 + v5;
  if ( v16 <= v14 )
  {
    v17 = *(_DWORD *)(a1 + 20);
    goto LABEL_20;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
  {
    if ( v16 <= 2 * v14 )
      v16 = 2 * v14;
    v17 = v16;
    if ( (unsigned __int8)DefArray_TryEnsureSizeByElemSize(*(void **)(a1 + 24), a1 + 24) )
    {
      *(_DWORD *)(a1 + 20) = v17;
LABEL_20:
      v18 = *(int *)(a1 + 16);
      v19 = 2147483646;
      v20 = v17 - v18;
      v21 = v20;
      v22 = (_WORD *)(*(_QWORD *)(a1 + 24) + 2 * v18);
      if ( v20 - 1 > 0x7FFFFFFE )
      {
        if ( v20 )
          *v22 = 0;
      }
      else
      {
        do
        {
          if ( !v19 )
            break;
          if ( !*v2 )
            break;
          *v22++ = *v2++;
          --v19;
          --v21;
        }
        while ( v21 );
        v23 = v22 - 1;
        if ( v21 )
          v23 = v22;
        *v23 = 0;
        if ( v21 )
        {
          *(_DWORD *)(a1 + 16) += v15;
          return (unsigned int)v18;
        }
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180029510  mov     [rsp+arg_10], rsi
0x180029515  push    rdi
0x180029516  sub     rsp, 30h
0x18002951a  mov     rsi, rdx
0x18002951d  mov     rdi, rcx
0x180029520  test    rdx, rdx
0x180029523  jz      loc_1800296D4
0x180029529  cmp     word ptr [rdx], 0
0x18002952d  jz      loc_1800296D4
0x180029533  mov     [rsp+38h+arg_0], rbx
0x180029538  mov     ebx, 1
0x18002953d  nop     dword ptr [rax]
0x180029540  mov     eax, [rdi+10h]
0x180029543  cmp     ebx, eax
0x180029545  jge     short loc_1800295BB
0x180029547  mov     rax, [rdi+18h]
0x18002954b  movsxd  rcx, ebx
0x18002954e  lea     r8, [rax+rcx*2]; lpString2
0x180029552  movzx   eax, word ptr [rax+rcx*2]
0x180029556  cmp     [rsi], ax
0x180029559  jz      short loc_18002955F
0x18002955b  inc     ebx
0x18002955d  jmp     short loc_180029540
0x18002955f  mov     ecx, [rdi+0Ch]
0x180029562  test    ecx, ecx
0x180029564  jz      loc_180029689
0x18002956a  cmp     ecx, 1
0x18002956d  jnz     short loc_18002955B
0x18002956f  mov     edx, 0FFFFFFFFh; cchCount1
0x180029574  mov     [rsp+38h+bIgnoreCase], ecx; bIgnoreCase
0x180029578  mov     r9d, edx; cchCount2
0x18002957b  mov     rcx, rsi; lpString1
0x18002957e  call    cs:__imp_CompareStringOrdinal
0x180029584  lea     ecx, [rax-2]
0x180029587  cmp     ecx, 7FFFFFFFh
0x18002958d  jz      loc_1800296CA
0x180029593  test    ecx, ecx
0x180029595  js      short loc_1800295B4
0x180029597  xor     eax, eax
0x180029599  test    ecx, ecx
0x18002959b  setnle  al
0x18002959e  test    eax, eax
0x1800295a0  jnz     short loc_18002955B
0x1800295a2  mov     eax, ebx
0x1800295a4  mov     rbx, [rsp+38h+arg_0]
0x1800295a9  mov     rsi, [rsp+38h+arg_10]
0x1800295ae  add     rsp, 30h
0x1800295b2  pop     rdi
0x1800295b3  retn
0x1800295b4  mov     eax, 0FFFFFFFFh
0x1800295b9  jmp     short loc_18002959E
0x1800295bb  mov     [rsp+38h+arg_8], r14
0x1800295c0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800295c7  cmp     word ptr [rsi+rcx*2+2], 0
0x1800295cd  lea     rcx, [rcx+1]
0x1800295d1  jnz     short loc_1800295C7
0x1800295d3  mov     edx, [rdi+14h]
0x1800295d6  lea     r14d, [rcx+1]
0x1800295da  lea     ecx, [r14+rax]
0x1800295de  cmp     ecx, edx
0x1800295e0  ja      short loc_18002964E
0x1800295e2  mov     ebx, edx
0x1800295e4  movsxd  r10, dword ptr [rdi+10h]
0x1800295e8  mov     ecx, 7FFFFFFEh
0x1800295ed  mov     rax, [rdi+18h]
0x1800295f1  sub     ebx, r10d
0x1800295f4  mov     r8d, ebx
0x1800295f7  lea     r9, [rax+r10*2]
0x1800295fb  lea     eax, [rbx-1]
0x1800295fe  cmp     eax, ecx
0x180029600  ja      loc_1800296AF
0x180029606  test    rcx, rcx
0x180029609  jz      short loc_180029628
0x18002960b  movzx   eax, word ptr [rsi]
0x18002960e  test    ax, ax
0x180029611  jz      short loc_180029628
0x180029613  mov     [r9], ax
0x180029617  add     rsi, 2
0x18002961b  add     r9, 2
0x18002961f  dec     rcx
0x180029622  sub     r8, 1
0x180029626  jnz     short loc_180029606
0x180029628  test    r8, r8
0x18002962b  lea     rdx, [r9-2]
0x18002962f  cmovnz  rdx, r9
0x180029633  xor     ecx, ecx
0x180029635  mov     [rdx], cx
0x180029638  test    r8, r8
0x18002963b  jz      short loc_1800296B3
0x18002963d  add     [rdi+10h], r14d
0x180029641  mov     eax, r10d
0x180029644  mov     r14, [rsp+38h+arg_8]
0x180029649  jmp     loc_1800295A4
0x18002964e  test    dword ptr [rdi+8], 100h
0x180029655  jnz     short loc_1800296B3
0x180029657  lea     eax, [rdx+rdx]
0x18002965a  mov     r8, rdx
0x18002965d  cmp     ecx, eax
0x18002965f  mov     edx, 2
0x180029664  cmovbe  ecx, eax
0x180029667  mov     ebx, ecx
0x180029669  lea     rcx, [rdi+18h]
0x18002966d  mov     qword ptr [rsp+38h+bIgnoreCase], rcx; __int64
0x180029672  mov     r9d, ebx
0x180029675  mov     rcx, [rcx]; Source
0x180029678  call    _DefArray_TryEnsureSizeByElemSize
0x18002967d  test    al, al
0x18002967f  jz      short loc_1800296B3
0x180029681  mov     [rdi+14h], ebx
0x180029684  jmp     loc_1800295E4
0x180029689  mov     edx, 0FFFFFFFFh; cchCount1
0x18002968e  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180029696  mov     r9d, edx; cchCount2
0x180029699  mov     rcx, rsi; lpString1
0x18002969c  call    cs:__imp_CompareStringOrdinal
0x1800296a2  lea     ecx, [rax-2]
0x1800296a5  call    _IntToComparison
0x1800296aa  jmp     loc_18002959E
0x1800296af  test    ebx, ebx
0x1800296b1  jnz     short loc_1800296C2
0x1800296b3  mov     r14, [rsp+38h+arg_8]
0x1800296b8  mov     eax, 0FFFFFFFFh
0x1800296bd  jmp     loc_1800295A4
0x1800296c2  xor     ecx, ecx
0x1800296c4  mov     [r9], cx
0x1800296c8  jmp     short loc_1800296B3
0x1800296ca  mov     eax, 7FFFFFFFh
0x1800296cf  jmp     loc_18002959E
0x1800296d4  xor     eax, eax
0x1800296d6  jmp     loc_1800295A9
```
