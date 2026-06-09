# _pSpUtilsStringTableLookUpString

- ea: `0x140010708`
- end: `0x140010892`
- name: `_pSpUtilsStringTableLookUpString`
- size: `394`
- prototype: `__int64 __fastcall(__int64 *, void *, unsigned int *, unsigned int *, const WCHAR **, int, void *, size_t Size)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010028`
- `0x140010bc0`
- `0x140010c7c`

## callees

- `0x14000ff74`
- `0x140010708`
- `0x140010dac`
- `0x140045ed2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001078a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001078a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010805`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010805`

## pseudocode

```c
__int64 __fastcall pSpUtilsStringTableLookUpString(
        __int64 *a1,
        void *a2,
        unsigned int *a3,
        unsigned int *a4,
        const WCHAR **a5,
        int a6,
        void *a7,
        size_t Size)
{
  char v8; // r14
  unsigned int v13; // edi
  unsigned int v14; // esi
  const WCHAR *v15; // rbx
  __int64 v16; // rcx
  unsigned int v17; // edx
  const WCHAR *v18; // rsi
  BOOL bIgnoreCase; // r14d
  int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // r14d
  unsigned int v23; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h]
  unsigned int v26; // [rsp+80h] [rbp+40h] BYREF
  int v27; // [rsp+88h] [rbp+48h] BYREF
  unsigned int *v28; // [rsp+90h] [rbp+50h]

  v28 = a3;
  v8 = a6;
  lpMem = a2;
  v26 = 0;
  v27 = 0;
  if ( !(unsigned int)pSpUtilsConvertStringCaseSensitive(&lpMem, &a6, &v27) )
    return 0xFFFFFFFFLL;
  v13 = -1;
  if ( (unsigned int)ComputeHashValue(lpMem, a3, a6, &v26) )
  {
    v16 = *a1;
    v14 = v26;
    if ( *(int *)(*a1 + 4LL * v26) >= 2036 )
    {
      v17 = *((_DWORD *)a1 + 2);
      if ( *(_DWORD *)(v16 + 4LL * v26) < (signed int)v17 )
      {
        v18 = (const WCHAR *)(v16 + *(int *)(v16 + 4LL * v26));
        v15 = 0;
        v25 = (unsigned int)(v17 / ((unsigned __int64)*((unsigned int *)a1 + 8) + 6)) + 1;
        bIgnoreCase = (v8 & 1) == 0;
        while ( 1 )
        {
          v20 = CompareStringOrdinal(v18 + 2, -1, (LPCWCH)lpMem, -1, bIgnoreCase);
          if ( v20 == 2 )
            break;
          if ( v20 == 1 && !bIgnoreCase )
            goto LABEL_25;
          v21 = *(int *)v18;
          if ( (_DWORD)v21 == -1 )
          {
            v15 = v18;
            goto LABEL_25;
          }
          if ( (int)v21 >= 2036 && (int)v21 < *((_DWORD *)a1 + 2) )
          {
            v15 = v18;
            v18 = (const WCHAR *)(*a1 + v21);
            LODWORD(v25) = v25 - 1;
            if ( (_DWORD)v25 )
              continue;
          }
          goto LABEL_4;
        }
        v22 = (_DWORD)v18 - *(_DWORD *)a1;
        v15 = v18;
        if ( v22 != -1 && a7 )
        {
          v23 = *((_DWORD *)a1 + 8);
          if ( (unsigned int)Size < v23 )
            v23 = Size;
          memcpy_0(a7, &v18[*v28 + 3], v23);
        }
        v13 = v22;
LABEL_25:
        v14 = v26;
        goto LABEL_6;
      }
    }
  }
  else
  {
LABEL_4:
    v14 = v26;
  }
  v15 = 0;
LABEL_6:
  if ( v27 )
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
0x140010708  mov     [rsp-38h+arg_10], r8
0x14001070d  push    rbp
0x14001070e  push    rbx
0x14001070f  push    rsi
0x140010710  push    rdi
0x140010711  push    r13
0x140010713  push    r14
0x140010715  push    r15
0x140010717  mov     rbp, rsp
0x14001071a  sub     rsp, 40h
0x14001071e  mov     r14d, [rbp+arg_28]
0x140010722  mov     rbx, r8
0x140010725  mov     r15, rcx
0x140010728  mov     [rbp+lpMem], rdx
0x14001072c  lea     r8, [rbp+arg_8]
0x140010730  mov     [rbp+arg_0], 0
0x140010737  lea     rdx, [rbp+arg_28]
0x14001073b  mov     [rbp+arg_8], 0
0x140010742  lea     rcx, [rbp+lpMem]
0x140010746  mov     r13, r9
0x140010749  call    pSpUtilsConvertStringCaseSensitive
0x14001074e  test    eax, eax
0x140010750  jnz     short loc_140010757
0x140010752  or      eax, 0FFFFFFFFh
0x140010755  jmp     short loc_1400107A7
0x140010757  mov     r8d, [rbp+arg_28]
0x14001075b  lea     r9, [rbp+arg_0]
0x14001075f  mov     rcx, [rbp+lpMem]
0x140010763  mov     rdx, rbx
0x140010766  or      edi, 0FFFFFFFFh
0x140010769  call    _ComputeHashValue
0x14001076e  test    eax, eax
0x140010770  jnz     short loc_1400107B6
0x140010772  mov     esi, [rbp+arg_0]
0x140010775  xor     ebx, ebx
0x140010777  cmp     [rbp+arg_8], 0
0x14001077b  jz      short loc_140010790
0x14001077d  mov     r8, [rbp+lpMem]; lpMem
0x140010781  xor     edx, edx; dwFlags
0x140010783  mov     rcx, cs:hHeap; hHeap
0x14001078a  call    cs:__imp_HeapFree
0x140010790  test    r13, r13
0x140010793  jz      short loc_140010799
0x140010795  mov     [r13+0], esi
0x140010799  mov     rax, [rbp+arg_20]
0x14001079d  test    rax, rax
0x1400107a0  jz      short loc_1400107A5
0x1400107a2  mov     [rax], rbx
0x1400107a5  mov     eax, edi
0x1400107a7  add     rsp, 40h
0x1400107ab  pop     r15
0x1400107ad  pop     r14
0x1400107af  pop     r13
0x1400107b1  pop     rdi
0x1400107b2  pop     rsi
0x1400107b3  pop     rbx
0x1400107b4  pop     rbp
0x1400107b5  retn
0x1400107b6  mov     rcx, [r15]
0x1400107b9  mov     esi, [rbp+arg_0]
0x1400107bc  cmp     dword ptr [rcx+rsi*4], 7F4h
0x1400107c3  jl      short loc_140010775
0x1400107c5  mov     edx, [r15+8]
0x1400107c9  cmp     [rcx+rsi*4], edx
0x1400107cc  jge     short loc_140010775
0x1400107ce  movsxd  rsi, dword ptr [rcx+rsi*4]
0x1400107d2  mov     eax, edx
0x1400107d4  add     rsi, rcx
0x1400107d7  xor     edx, edx
0x1400107d9  mov     ecx, [r15+20h]
0x1400107dd  xor     ebx, ebx
0x1400107df  add     rcx, 6
0x1400107e3  not     r14d
0x1400107e6  div     rcx
0x1400107e9  inc     eax
0x1400107eb  mov     [rbp+var_8], rax
0x1400107ef  and     r14d, 1
0x1400107f3  mov     r8, [rbp+lpMem]; lpString2
0x1400107f7  lea     rcx, [rsi+4]; lpString1
0x1400107fb  mov     r9d, edi; cchCount2
0x1400107fe  mov     [rsp+40h+bIgnoreCase], r14d; bIgnoreCase
0x140010803  mov     edx, edi; cchCount1
0x140010805  call    cs:__imp_CompareStringOrdinal
0x14001080b  cmp     eax, 2
0x14001080e  jz      short loc_140010855
0x140010810  cmp     eax, 1
0x140010813  jnz     short loc_14001081A
0x140010815  test    r14d, r14d
0x140010818  jz      short loc_14001084D
0x14001081a  movsxd  rax, dword ptr [rsi]
0x14001081d  cmp     eax, edi
0x14001081f  jz      short loc_14001084A
0x140010821  cmp     eax, 7F4h
0x140010826  jl      loc_140010772
0x14001082c  cmp     eax, [r15+8]
0x140010830  jge     loc_140010772
0x140010836  mov     rbx, rsi
0x140010839  mov     rsi, rax
0x14001083c  add     rsi, [r15]
0x14001083f  add     dword ptr [rbp+var_8], 0FFFFFFFFh
0x140010843  jnz     short loc_1400107F3
0x140010845  jmp     loc_140010772
0x14001084a  mov     rbx, rsi
0x14001084d  mov     esi, [rbp+arg_0]
0x140010850  jmp     loc_140010777
0x140010855  mov     r14d, esi
0x140010858  sub     r14d, [r15]
0x14001085b  mov     rbx, rsi
0x14001085e  cmp     r14d, edi
0x140010861  jz      short loc_14001088D
0x140010863  mov     rcx, [rbp+arg_30]; void *
0x140010867  test    rcx, rcx
0x14001086a  jz      short loc_14001088D
0x14001086c  mov     eax, [r15+20h]
0x140010870  cmp     dword ptr [rbp+Size], eax
0x140010873  cmovb   eax, dword ptr [rbp+Size]
0x140010877  mov     r8d, eax; Size
0x14001087a  mov     rax, [rbp+arg_10]
0x14001087e  mov     eax, [rax]
0x140010880  add     rax, 3
0x140010884  lea     rdx, [rsi+rax*2]; Src
0x140010888  call    memcpy_0
0x14001088d  mov     edi, r14d
0x140010890  jmp     short loc_14001084D
```
