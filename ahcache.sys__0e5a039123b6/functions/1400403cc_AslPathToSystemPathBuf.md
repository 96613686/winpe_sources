# AslPathToSystemPathBuf

- ea: `0x1400403cc`
- end: `0x14004055e`
- name: `AslPathToSystemPathBuf`
- size: `402`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140032adc`
- `0x140032c14`
- `0x140040310`
- `0x140040970`

## callees

- `0x140007e40`
- `0x14003e364`
- `0x1400403cc`

## string_xrefs

- `0x14004050e`: `AslPathToSystemPathBuf`
- `0x140040542`: `AslPathToSystemPathBuf`
- `0x140040531`: `Failed to copy string [%x]`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(_WORD *a1, unsigned __int64 a2, _WORD *a3)
{
  __int64 v6; // r9
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rdx
  _WORD *v10; // r8
  _WORD *v11; // rcx
  unsigned int v12; // esi
  unsigned __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned int v15; // edi
  __int64 v16; // r8
  _WORD *v17; // rdx
  unsigned __int64 i; // rbx
  _WORD *v19; // rcx

  memset(a1, 0, 2 * a2);
  if ( !a2 )
  {
    v12 = -1073741811;
LABEL_24:
    v15 = v12;
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1471, "Failed to copy string [%x]", v12);
    return v15;
  }
  if ( a2 > 0x7FFFFFFF )
  {
    v12 = -1073741811;
    *a1 = 0;
    goto LABEL_24;
  }
  v6 = 2147483646;
  v7 = L"\\SystemRoot";
  v8 = 2147483646;
  v9 = a2;
  v10 = a1;
  do
  {
    if ( !v8 )
      break;
    if ( !*v7 )
      break;
    *v10++ = *v7++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v10 - 1;
  v12 = v9 == 0 ? 0x80000005 : 0;
  if ( v9 )
    v11 = v10;
  *v11 = 0;
  if ( !v9 )
    goto LABEL_24;
  v13 = a2;
  v14 = a1;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = v13 == 0 ? 0xC000000D : 0;
  v16 = (a2 - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_22;
  v17 = &a1[v16];
  for ( i = a2 - v16; i; --i )
  {
    if ( !v6 )
      break;
    if ( !*a3 )
      break;
    *v17++ = *a3++;
    --v6;
  }
  v19 = v17 - 1;
  v15 = i == 0 ? 0x80000005 : 0;
  if ( i )
    v19 = v17;
  *v19 = 0;
  if ( !i )
  {
LABEL_22:
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1488, "Failed to cat string [%x]", v15);
    return (unsigned int)-1073741811;
  }
  return v15;
}

```

## disassembly

```asm
0x1400403cc  push    rbx
0x1400403ce  push    rsi
0x1400403cf  push    rdi
0x1400403d0  push    r14
0x1400403d2  push    r15
0x1400403d4  sub     rsp, 30h
0x1400403d8  mov     r15, r8
0x1400403db  mov     rbx, rdx
0x1400403de  lea     r8, [rdx+rdx]; Size
0x1400403e2  mov     r14, rcx
0x1400403e5  xor     edx, edx; Val
0x1400403e7  call    memset
0x1400403ec  xor     r11d, r11d
0x1400403ef  test    rbx, rbx
0x1400403f2  jz      loc_140040523
0x1400403f8  cmp     rbx, 7FFFFFFFh
0x1400403ff  ja      loc_140040557
0x140040405  mov     r9d, 7FFFFFFEh
0x14004040b  lea     rcx, aSystemroot; "\\SystemRoot"
0x140040412  mov     eax, r9d
0x140040415  mov     rdx, rbx
0x140040418  mov     r8, r14
0x14004041b  test    rax, rax
0x14004041e  jz      short loc_14004043F
0x140040420  movzx   r10d, word ptr [rcx]
0x140040424  test    r10w, r10w
0x140040428  jz      short loc_14004043F
0x14004042a  mov     [r8], r10w
0x14004042e  add     rcx, 2
0x140040432  add     r8, 2
0x140040436  dec     rax
0x140040439  sub     rdx, 1
0x14004043d  jnz     short loc_14004041B
0x14004043f  mov     rax, rdx
0x140040442  lea     rcx, [r8-2]
0x140040446  neg     rax
0x140040449  mov     r10d, 80000005h
0x14004044f  sbb     esi, esi
0x140040451  not     esi
0x140040453  and     esi, r10d
0x140040456  test    rdx, rdx
0x140040459  cmovnz  rcx, r8
0x14004045d  mov     [rcx], r11w
0x140040461  jz      loc_140040531
0x140040467  mov     rdx, rbx
0x14004046a  mov     rax, r14
0x14004046d  cmp     [rax], r11w
0x140040471  jz      short loc_14004047D
0x140040473  add     rax, 2
0x140040477  sub     rdx, 1
0x14004047b  jnz     short loc_14004046D
0x14004047d  mov     rax, rdx
0x140040480  mov     esi, 0C000000Dh
0x140040485  neg     rax
0x140040488  mov     rcx, rbx
0x14004048b  mov     rax, rdx
0x14004048e  sbb     edi, edi
0x140040490  sub     rcx, rdx
0x140040493  not     edi
0x140040495  and     edi, esi
0x140040497  neg     rax
0x14004049a  sbb     r8, r8
0x14004049d  and     r8, rcx
0x1400404a0  test    rdx, rdx
0x1400404a3  jz      short loc_1400404FD
0x1400404a5  lea     rdx, [r14+r8*2]
0x1400404a9  sub     rbx, r8
0x1400404ac  jz      short loc_1400404D0
0x1400404ae  test    r9, r9
0x1400404b1  jz      short loc_1400404D0
0x1400404b3  movzx   eax, word ptr [r15]
0x1400404b7  test    ax, ax
0x1400404ba  jz      short loc_1400404D0
0x1400404bc  mov     [rdx], ax
0x1400404bf  add     r15, 2
0x1400404c3  add     rdx, 2
0x1400404c7  dec     r9
0x1400404ca  sub     rbx, 1
0x1400404ce  jnz     short loc_1400404AE
0x1400404d0  mov     rax, rbx
0x1400404d3  lea     rcx, [rdx-2]
0x1400404d7  neg     rax
0x1400404da  sbb     edi, edi
0x1400404dc  not     edi
0x1400404de  and     edi, r10d
0x1400404e1  test    rbx, rbx
0x1400404e4  cmovnz  rcx, rdx
0x1400404e8  mov     [rcx], r11w
0x1400404ec  jz      short loc_1400404FD
0x1400404ee  mov     eax, edi
0x1400404f0  add     rsp, 30h
0x1400404f4  pop     r15
0x1400404f6  pop     r14
0x1400404f8  pop     rdi
0x1400404f9  pop     rsi
0x1400404fa  pop     rbx
0x1400404fb  retn
0x1400404fd  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x140040504  mov     [rsp+58h+var_38], edi
0x140040508  mov     r8d, 5D0h
0x14004050e  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140040515  mov     ecx, 1
0x14004051a  call    AslLogCallPrintf
0x14004051f  mov     edi, esi
0x140040521  jmp     short loc_1400404EE
0x140040523  mov     esi, 0C000000Dh
0x140040528  test    rbx, rbx
0x14004052b  jz      short loc_140040531
0x14004052d  mov     [r14], r11w
0x140040531  lea     r9, aFailedToCopySt; "Failed to copy string [%x]"
0x140040538  mov     [rsp+58h+var_38], esi
0x14004053c  mov     r8d, 5BFh
0x140040542  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140040549  mov     ecx, 1
0x14004054e  mov     edi, esi
0x140040550  call    AslLogCallPrintf
0x140040555  jmp     short loc_1400404EE
0x140040557  mov     esi, 0C000000Dh
0x14004055c  jmp     short loc_14004052D
```
