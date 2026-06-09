# SplitTokens(wchar_t const *,uint *,wchar_t * * *)

- ea: `0x18007b694`
- end: `0x18007b884`
- name: `?SplitTokens@@YAJPEB_WPEAIPEAPEAPEA_W@Z`
- size: `496`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *, wchar_t ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007b608`

## callees

- `0x18007b694`
- `0x18007b88c`
- `0x18007b910`
- `0x18007b9a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007b77f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007b815`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007b77f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007b815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b872`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SplitTokens(const wchar_t *a1, const wchar_t *a2, wchar_t ***a3)
{
  wchar_t *v4; // r14
  int v5; // esi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v9; // r12d
  SIZE_T v10; // rbx
  wchar_t **v11; // rax
  unsigned int v12; // ebx
  unsigned int v13; // edx
  unsigned int v14; // r15d
  const wchar_t *v15; // r13
  __int64 v16; // rsi
  int v17; // r14d
  wchar_t *v18; // rax
  unsigned int i; // ebx
  __int128 v20; // [rsp+20h] [rbp-40h] BYREF
  __int128 v21; // [rsp+30h] [rbp-30h] BYREF
  const int *v22; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v23; // [rsp+48h] [rbp-18h]
  int v24; // [rsp+50h] [rbp-10h]
  signed int v25; // [rsp+54h] [rbp-Ch]
  wchar_t *v26; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v27; // [rsp+A8h] [rbp+48h]

  v27 = a2;
  v4 = (wchar_t *)a2;
  v5 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v25 = v6;
  v24 = v6;
  v23 = a1;
  v22 = &CConstString::`vftable';
  v7 = CLMString::CountTokens((CLMString *)&v22, a2);
  *(_DWORD *)v4 = v7;
  if ( v7 )
  {
    v9 = 0;
    v10 = 8 * v7;
    v11 = (wchar_t **)CoTaskMemAlloc(v10);
    *a3 = v11;
    if ( v11 )
    {
      for ( ; v10; --v10 )
      {
        *(_BYTE *)v11 = 0;
        v11 = (wchar_t **)((char *)v11 + 1);
      }
      v20 = 0u;
      v12 = 0;
      while ( v12 != -1 )
      {
        while ( 1 )
        {
          v13 = v25;
          if ( (int)v12 >= v25 )
            break;
          v18 = wcschr(L";,|", v23[v12]);
          if ( !v18 || (unsigned int)(v18 - L";,|") == -1 )
          {
            v13 = v25;
            break;
          }
          ++v12;
        }
        if ( v12 == v13 )
          break;
        v14 = v12;
        v15 = &v23[v12];
        v16 = 0;
        while ( 1 )
        {
          v17 = v16 + v12;
          if ( (unsigned int)v16 + v12 >= v13 )
            goto LABEL_18;
          if ( wcschr(L";,|", v15[v16]) )
            break;
          v16 = (unsigned int)(v16 + 1);
          v13 = v25;
        }
        if ( v17 == -1 )
        {
          v13 = v25;
LABEL_18:
          v12 = -1;
          DWORD1(v20) = v13 - v14;
          goto LABEL_19;
        }
        v12 = v17 + 1;
        DWORD1(v20) = v17 - v14;
LABEL_19:
        *((_QWORD *)&v20 + 1) = &v22;
        LODWORD(v20) = v14;
        CLMSubStr::TrimSpaces((CLMSubStr *)&v20);
        v26 = 0;
        v21 = v20;
        v5 = AllocAndCopyLMSubStr(&v26, &v21);
        if ( v5 < 0 )
        {
          v4 = (wchar_t *)v27;
          goto LABEL_28;
        }
        (*a3)[v9++] = v26;
      }
    }
    else
    {
      v5 = -2147024882;
LABEL_28:
      if ( *a3 )
      {
        for ( i = 0; i < v9; ++i )
          CoTaskMemFree((*a3)[i]);
        CoTaskMemFree(*a3);
      }
      *a3 = 0;
      *(_DWORD *)v4 = 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007b694  mov     [rsp-38h+arg_10], rbx
0x18007b699  mov     [rsp-38h+arg_8], rdx
0x18007b69e  push    rbp
0x18007b69f  push    rsi
0x18007b6a0  push    rdi
0x18007b6a1  push    r12
0x18007b6a3  push    r13
0x18007b6a5  push    r14
0x18007b6a7  push    r15
0x18007b6a9  mov     rbp, rsp
0x18007b6ac  sub     rsp, 60h
0x18007b6b0  mov     rdi, r8
0x18007b6b3  mov     r14, rdx
0x18007b6b6  xor     r15d, r15d
0x18007b6b9  mov     esi, r15d
0x18007b6bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007b6c0  inc     rax
0x18007b6c3  cmp     [rcx+rax*2], r15w
0x18007b6c8  jnz     short loc_18007B6C0
0x18007b6ca  mov     [rbp+var_C], eax
0x18007b6cd  mov     [rbp+var_10], eax
0x18007b6d0  mov     [rbp+var_18], rcx
0x18007b6d4  lea     rax, ??_7CConstString@@6B@; const CConstString::`vftable'
0x18007b6db  mov     [rbp+var_20], rax
0x18007b6df  lea     rcx, [rbp+var_20]; this
0x18007b6e3  call    ?CountTokens@CLMString@@QEBAHPEB_W@Z; CLMString::CountTokens(wchar_t const *)
0x18007b6e8  mov     [r14], eax
0x18007b6eb  test    eax, eax
0x18007b6ed  jnz     short loc_18007B709
0x18007b6ef  mov     eax, esi
0x18007b6f1  mov     rbx, [rsp+60h+arg_10]
0x18007b6f9  add     rsp, 60h
0x18007b6fd  pop     r15
0x18007b6ff  pop     r14
0x18007b701  pop     r13
0x18007b703  pop     r12
0x18007b705  pop     rdi
0x18007b706  pop     rsi
0x18007b707  pop     rbp
0x18007b708  retn
0x18007b709  mov     r12d, r15d
0x18007b70c  shl     eax, 3
0x18007b70f  movsxd  rbx, eax
0x18007b712  mov     rcx, rbx; cb
0x18007b715  call    cs:__imp_CoTaskMemAlloc
0x18007b71b  mov     [rdi], rax
0x18007b71e  test    rax, rax
0x18007b721  jz      loc_18007B841
0x18007b727  test    rbx, rbx
0x18007b72a  jz      short loc_18007B738
0x18007b72c  mov     [rax], r15b
0x18007b72f  inc     rax
0x18007b732  sub     rbx, 1
0x18007b736  jnz     short loc_18007B72C
0x18007b738  mov     qword ptr [rbp+var_40], r15
0x18007b73c  mov     qword ptr [rbp+var_40+8], r15
0x18007b740  mov     ebx, r15d
0x18007b743  lea     r8, asc_180264BE8; ";,|"
0x18007b74a  cmp     ebx, 0FFFFFFFFh
0x18007b74d  jz      short loc_18007B6EF
0x18007b74f  mov     edx, [rbp+var_C]
0x18007b752  cmp     ebx, edx
0x18007b754  jl      loc_18007B808
0x18007b75a  cmp     ebx, edx
0x18007b75c  jz      short loc_18007B6EF
0x18007b75e  mov     r15d, ebx
0x18007b761  mov     ecx, ebx
0x18007b763  mov     rax, [rbp+var_18]
0x18007b767  lea     r13, [rax+rcx*2]
0x18007b76b  xor     esi, esi
0x18007b76d  lea     r14d, [rsi+rbx]
0x18007b771  cmp     r14d, edx
0x18007b774  jnb     short loc_18007B7A1
0x18007b776  movzx   edx, word ptr [r13+rsi*2+0]; Ch
0x18007b77c  mov     rcx, r8; Str
0x18007b77f  call    cs:__imp_wcschr
0x18007b785  test    rax, rax
0x18007b788  jnz     short loc_18007B798
0x18007b78a  inc     esi
0x18007b78c  mov     edx, [rbp+var_C]
0x18007b78f  lea     r8, asc_180264BE8; ";,|"
0x18007b796  jmp     short loc_18007B76D
0x18007b798  cmp     r14d, 0FFFFFFFFh
0x18007b79c  jnz     short loc_18007B7F8
0x18007b79e  mov     edx, [rbp+var_C]
0x18007b7a1  or      ebx, 0FFFFFFFFh
0x18007b7a4  sub     edx, r15d
0x18007b7a7  mov     dword ptr [rbp+var_40+4], edx
0x18007b7aa  lea     rax, [rbp+var_20]
0x18007b7ae  mov     qword ptr [rbp+var_40+8], rax
0x18007b7b2  mov     dword ptr [rbp+var_40], r15d
0x18007b7b6  lea     rcx, [rbp+var_40]; this
0x18007b7ba  call    ?TrimSpaces@CLMSubStr@@QEAAXXZ; CLMSubStr::TrimSpaces(void)
0x18007b7bf  xor     r15d, r15d
0x18007b7c2  mov     [rbp+arg_0], r15
0x18007b7c6  movaps  xmm0, [rbp+var_40]
0x18007b7ca  movdqa  [rbp+var_30], xmm0
0x18007b7cf  lea     rdx, [rbp+var_30]
0x18007b7d3  lea     rcx, [rbp+arg_0]
0x18007b7d7  call    ?AllocAndCopyLMSubStr@@YAJPEAPEA_WVCLMSubStr@@@Z; AllocAndCopyLMSubStr(wchar_t * *,CLMSubStr)
0x18007b7dc  mov     esi, eax
0x18007b7de  test    eax, eax
0x18007b7e0  js      short loc_18007B848
0x18007b7e2  mov     r8d, r12d
0x18007b7e5  mov     rdx, [rdi]
0x18007b7e8  mov     rcx, [rbp+arg_0]
0x18007b7ec  mov     [rdx+r8*8], rcx
0x18007b7f0  inc     r12d
0x18007b7f3  jmp     loc_18007B743
0x18007b7f8  lea     ebx, [r14+1]
0x18007b7fc  mov     eax, ebx
0x18007b7fe  sub     eax, r15d
0x18007b801  dec     eax
0x18007b803  mov     dword ptr [rbp+var_40+4], eax
0x18007b806  jmp     short loc_18007B7AA
0x18007b808  mov     eax, ebx
0x18007b80a  mov     rdx, [rbp+var_18]
0x18007b80e  movzx   edx, word ptr [rdx+rax*2]; Ch
0x18007b812  mov     rcx, r8; Str
0x18007b815  call    cs:__imp_wcschr
0x18007b81b  lea     r8, asc_180264BE8; ";,|"
0x18007b822  test    rax, rax
0x18007b825  jz      short loc_18007B832
0x18007b827  sub     rax, r8
0x18007b82a  sar     rax, 1
0x18007b82d  cmp     eax, 0FFFFFFFFh
0x18007b830  jnz     short loc_18007B83A
0x18007b832  mov     edx, [rbp+var_C]
0x18007b835  jmp     loc_18007B75A
0x18007b83a  inc     ebx
0x18007b83c  jmp     loc_18007B74F
0x18007b841  mov     esi, 8007000Eh
0x18007b846  jmp     short loc_18007B84C
0x18007b848  mov     r14, [rbp+arg_8]
0x18007b84c  cmp     [rdi], r15
0x18007b84f  jz      short loc_18007B878
0x18007b851  mov     ebx, r15d
0x18007b854  test    r12d, r12d
0x18007b857  jz      short loc_18007B86F
0x18007b859  mov     eax, ebx
0x18007b85b  mov     rcx, [rdi]
0x18007b85e  mov     rcx, [rcx+rax*8]; pv
0x18007b862  call    cs:__imp_CoTaskMemFree
0x18007b868  inc     ebx
0x18007b86a  cmp     ebx, r12d
0x18007b86d  jb      short loc_18007B859
0x18007b86f  mov     rcx, [rdi]; pv
0x18007b872  call    cs:__imp_CoTaskMemFree
0x18007b878  mov     [rdi], r15
0x18007b87b  mov     [r14], r15d
0x18007b87e  jmp     loc_18007B6EF
```
