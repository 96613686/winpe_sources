# _pSpUtilsStringTableLookUpString

- ea: `0x18004003c`
- end: `0x180040199`
- name: `_pSpUtilsStringTableLookUpString`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003f96c`
- `0x1800404cc`

## callees

- `0x18003f8b8`
- `0x18004003c`
- `0x1800405e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800400c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800400c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040144`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040144`

## pseudocode

```c
__int64 __fastcall pSpUtilsStringTableLookUpString(
        __int64 *a1,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        const WCHAR **a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8)
{
  char v8; // r15
  unsigned int v13; // ebx
  unsigned int v14; // esi
  const WCHAR *v15; // rdi
  __int64 v16; // rcx
  unsigned int v17; // edx
  const WCHAR *v18; // rsi
  BOOL bIgnoreCase; // r15d
  int v20; // eax
  __int64 v21; // rax
  int v22; // [rsp+60h] [rbp+30h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+38h] BYREF

  v8 = a6;
  lpMem = a2;
  a8 = 0;
  v22 = 0;
  if ( !(unsigned int)pSpUtilsConvertStringCaseSensitive(&lpMem, &a6, &v22) )
    return 0xFFFFFFFFLL;
  v13 = -1;
  if ( (unsigned int)ComputeHashValue(lpMem, a3, a6, &a8) )
  {
    v16 = *a1;
    v14 = a8;
    if ( *(int *)(*a1 + 4LL * a8) >= 2036 )
    {
      v17 = *((_DWORD *)a1 + 2);
      if ( *(_DWORD *)(v16 + 4LL * a8) < (signed int)v17 )
      {
        v18 = (const WCHAR *)(v16 + *(int *)(v16 + 4LL * a8));
        v15 = 0;
        a7 = (unsigned int)(v17 / ((unsigned __int64)*((unsigned int *)a1 + 8) + 6)) + 1;
        bIgnoreCase = (v8 & 1) == 0;
        while ( 1 )
        {
          v20 = CompareStringOrdinal(v18 + 2, -1, (LPCWCH)lpMem, -1, bIgnoreCase);
          if ( v20 == 2 )
            break;
          if ( v20 == 1 && !bIgnoreCase )
            goto LABEL_26;
          v21 = *(int *)v18;
          if ( (_DWORD)v21 == -1 )
            goto LABEL_25;
          if ( (int)v21 >= 2036 && (int)v21 < *((_DWORD *)a1 + 2) )
          {
            v15 = v18;
            v18 = (const WCHAR *)(*a1 + v21);
            LODWORD(a7) = a7 - 1;
            if ( (_DWORD)a7 )
              continue;
          }
          goto LABEL_4;
        }
        v13 = (_DWORD)v18 - *(_DWORD *)a1;
LABEL_25:
        v15 = v18;
LABEL_26:
        v14 = a8;
        goto LABEL_6;
      }
    }
  }
  else
  {
LABEL_4:
    v14 = a8;
  }
  v15 = 0;
LABEL_6:
  if ( v22 )
    HeapFree(hHeap, 0, lpMem);
  if ( a4 )
    *a4 = v14;
  if ( a5 )
    *a5 = v15;
  return v13;
}

```

## disassembly

```asm
0x18004003c  mov     [rsp-28h+arg_10], rbx
0x180040041  mov     [rsp-28h+arg_18], rsi
0x180040046  push    rbp
0x180040047  push    rdi
0x180040048  push    r13
0x18004004a  push    r14
0x18004004c  push    r15
0x18004004e  mov     rbp, rsp
0x180040051  sub     rsp, 30h
0x180040055  mov     r15d, [rbp+arg_28]
0x180040059  mov     rdi, r8
0x18004005c  mov     r14, rcx
0x18004005f  mov     [rbp+lpMem], rdx
0x180040063  lea     r8, [rbp+arg_0]
0x180040067  mov     [rbp+arg_38], 0
0x18004006e  lea     rdx, [rbp+arg_28]
0x180040072  mov     [rbp+arg_0], 0
0x180040079  lea     rcx, [rbp+lpMem]
0x18004007d  mov     r13, r9
0x180040080  call    pSpUtilsConvertStringCaseSensitive
0x180040085  test    eax, eax
0x180040087  jnz     short loc_18004008E
0x180040089  or      eax, 0FFFFFFFFh
0x18004008c  jmp     short loc_1800400DE
0x18004008e  mov     r8d, [rbp+arg_28]
0x180040092  lea     r9, [rbp+arg_38]
0x180040096  mov     rcx, [rbp+lpMem]
0x18004009a  mov     rdx, rdi
0x18004009d  or      ebx, 0FFFFFFFFh
0x1800400a0  call    _ComputeHashValue
0x1800400a5  test    eax, eax
0x1800400a7  jnz     short loc_1800400F5
0x1800400a9  mov     esi, [rbp+arg_38]
0x1800400ac  xor     edi, edi
0x1800400ae  cmp     [rbp+arg_0], 0
0x1800400b2  jz      short loc_1800400C7
0x1800400b4  mov     r8, [rbp+lpMem]; lpMem
0x1800400b8  xor     edx, edx; dwFlags
0x1800400ba  mov     rcx, cs:hHeap; hHeap
0x1800400c1  call    cs:__imp_HeapFree
0x1800400c7  test    r13, r13
0x1800400ca  jz      short loc_1800400D0
0x1800400cc  mov     [r13+0], esi
0x1800400d0  mov     rax, [rbp+arg_20]
0x1800400d4  test    rax, rax
0x1800400d7  jz      short loc_1800400DC
0x1800400d9  mov     [rax], rdi
0x1800400dc  mov     eax, ebx
0x1800400de  mov     rbx, [rsp+30h+arg_10]
0x1800400e3  mov     rsi, [rsp+30h+arg_18]
0x1800400e8  add     rsp, 30h
0x1800400ec  pop     r15
0x1800400ee  pop     r14
0x1800400f0  pop     r13
0x1800400f2  pop     rdi
0x1800400f3  pop     rbp
0x1800400f4  retn
0x1800400f5  mov     rcx, [r14]
0x1800400f8  mov     esi, [rbp+arg_38]
0x1800400fb  cmp     dword ptr [rcx+rsi*4], 7F4h
0x180040102  jl      short loc_1800400AC
0x180040104  mov     edx, [r14+8]
0x180040108  cmp     [rcx+rsi*4], edx
0x18004010b  jge     short loc_1800400AC
0x18004010d  movsxd  rsi, dword ptr [rcx+rsi*4]
0x180040111  mov     eax, edx
0x180040113  add     rsi, rcx
0x180040116  xor     edx, edx
0x180040118  mov     ecx, [r14+20h]
0x18004011c  xor     edi, edi
0x18004011e  add     rcx, 6
0x180040122  not     r15d
0x180040125  div     rcx
0x180040128  inc     eax
0x18004012a  mov     [rbp+arg_30], rax
0x18004012e  and     r15d, 1
0x180040132  mov     r8, [rbp+lpMem]; lpString2
0x180040136  lea     rcx, [rsi+4]; lpString1
0x18004013a  mov     r9d, ebx; cchCount2
0x18004013d  mov     [rsp+30h+bIgnoreCase], r15d; bIgnoreCase
0x180040142  mov     edx, ebx; cchCount1
0x180040144  call    cs:__imp_CompareStringOrdinal
0x18004014a  cmp     eax, 2
0x18004014d  jz      short loc_180040189
0x18004014f  cmp     eax, 1
0x180040152  jnz     short loc_180040159
0x180040154  test    r15d, r15d
0x180040157  jz      short loc_180040191
0x180040159  movsxd  rax, dword ptr [rsi]
0x18004015c  cmp     eax, ebx
0x18004015e  jz      short loc_18004018E
0x180040160  cmp     eax, 7F4h
0x180040165  jl      loc_1800400A9
0x18004016b  cmp     eax, [r14+8]
0x18004016f  jge     loc_1800400A9
0x180040175  mov     rdi, rsi
0x180040178  mov     rsi, rax
0x18004017b  add     rsi, [r14]
0x18004017e  add     dword ptr [rbp+arg_30], 0FFFFFFFFh
0x180040182  jnz     short loc_180040132
0x180040184  jmp     loc_1800400A9
0x180040189  mov     ebx, esi
0x18004018b  sub     ebx, [r14]
0x18004018e  mov     rdi, rsi
0x180040191  mov     esi, [rbp+arg_38]
0x180040194  jmp     loc_1800400AE
```
