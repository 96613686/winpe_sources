# ResolveDfsPath(ushort const *,_DFS_INFO_3 * *)

- ea: `0x180007818`
- end: `0x180007b09`
- name: `?ResolveDfsPath@@YAJPEBGPEAPEAU_DFS_INFO_3@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _DFS_INFO_3 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007368`

## callees

- `0x180007818`
- `0x180007b10`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180007856`
- `msvcrt!_wcsdup` at `0x180007856`
- `msvcrt!free` at `0x1800078f9`
- `msvcrt!free` at `0x1800079e3`
- `msvcrt!free` at `0x180007a92`
- `msvcrt!free` at `0x1800078f9`
- `msvcrt!free` at `0x1800079e3`
- `msvcrt!free` at `0x180007a92`
- `msvcrt!calloc` at `0x180007990`
- `msvcrt!calloc` at `0x180007a5b`
- `msvcrt!calloc` at `0x180007990`
- `msvcrt!calloc` at `0x180007a5b`
- `KERNEL32!lstrcmpiW` at `0x1800079d8`
- `KERNEL32!lstrcmpiW` at `0x1800079d8`
- `netutils!NetApiBufferFree` at `0x18000790c`
- `netutils!NetApiBufferFree` at `0x180007946`
- `netutils!NetApiBufferFree` at `0x180007ae2`
- `netutils!NetApiBufferFree` at `0x18000790c`
- `netutils!NetApiBufferFree` at `0x180007946`
- `netutils!NetApiBufferFree` at `0x180007ae2`
- `dfscli!NetDfsGetClientInfo` at `0x180007891`
- `dfscli!NetDfsGetClientInfo` at `0x180007ab3`
- `dfscli!NetDfsGetClientInfo` at `0x180007891`
- `dfscli!NetDfsGetClientInfo` at `0x180007ab3`

## pseudocode

```c
__int64 __fastcall ResolveDfsPath(const unsigned __int16 *a1, struct _DFS_INFO_3 **a2)
{
  WCHAR *v2; // r14
  int v4; // edi
  LPCWSTR *v5; // rsi
  DWORD i; // eax
  LPBYTE v7; // rbx
  int v8; // r13d
  unsigned int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rbp
  __int64 v12; // r15
  __int64 v13; // r9
  unsigned int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  size_t v17; // r12
  unsigned __int16 *v18; // r15
  const unsigned __int16 *v19; // r8
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r15d
  __int64 v24; // rdx
  __int64 v25; // r13
  __int64 v26; // rax
  size_t v27; // r12
  unsigned __int16 *v28; // rax
  WCHAR *v29; // rbx
  LPBYTE Buffer; // [rsp+70h] [rbp+8h] BYREF
  struct _DFS_INFO_3 **v31; // [rsp+78h] [rbp+10h]
  __int64 v32; // [rsp+80h] [rbp+18h]

  v31 = a2;
  if ( !a1 || !*a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  v2 = _wcsdup(a1);
  if ( !v2 )
    return 2147942414LL;
  Buffer = 0;
  v4 = 0;
  v5 = 0;
  for ( i = NetDfsGetClientInfo(v2, 0, 0, 3u, &Buffer); !i; i = NetDfsGetClientInfo(v29, 0, 0, 3u, &Buffer) )
  {
    v7 = Buffer;
    if ( **(_WORD **)Buffer != 92 || (v8 = 1, *(_WORD *)(*(_QWORD *)Buffer + 2LL) == 92) )
      v8 = 0;
    v9 = *((_DWORD *)Buffer + 5);
    if ( v9 == 1 )
    {
      v10 = *((_QWORD *)Buffer + 3);
      v11 = *(_QWORD *)(v10 + 8);
      v12 = *(_QWORD *)(v10 + 16);
    }
    else
    {
      if ( !v9 )
        goto LABEL_17;
      v13 = *((_QWORD *)Buffer + 3);
      v14 = 0;
      while ( (*(_BYTE *)(v13 + 24LL * v14) & 4) == 0 )
      {
        if ( ++v14 >= v9 )
          goto LABEL_17;
      }
      v11 = *(_QWORD *)(v13 + 24LL * v14 + 8);
      if ( !v11 )
      {
LABEL_17:
        v4 = -2147467259;
        goto LABEL_18;
      }
      v12 = *(_QWORD *)(v13 + 24LL * v14 + 16);
    }
    v32 = v12;
    if ( v5 )
    {
      NetApiBufferFree(v5);
      v7 = Buffer;
    }
    v5 = (LPCWSTR *)v7;
    v7 = 0;
    v15 = -1;
    Buffer = 0;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v11 + 2 * v16) );
    do
      ++v15;
    while ( *(_WORD *)(v12 + 2 * v15) );
    v17 = (v8 ^ 1) + 3 + (int)v15 + (int)v16;
    v18 = (unsigned __int16 *)calloc(v17, 2u);
    if ( !v18 )
    {
      v4 = -2147024882;
      goto LABEL_18;
    }
    v19 = L"\\%s\\%s";
    if ( !v8 )
      v19 = L"\\\\%s\\%s";
    StringCchPrintfW(v18, v17, v19, v11, v32);
    v20 = lstrcmpiW(v18, *v5);
    free(v18);
    if ( !v20 )
      goto LABEL_47;
    v21 = -1;
    do
      ++v21;
    while ( v2[v21] );
    v22 = -1;
    do
      ++v22;
    while ( (*v5)[v22] );
    v23 = v22 + v8;
    if ( (_DWORD)v21 == (_DWORD)v22 + v8 )
      goto LABEL_47;
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(v11 + 2 * v24) );
    v25 = v32;
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(v32 + 2 * v26) );
    v27 = (int)v21 + 4 + (int)v24 + (int)v26 - v23;
    v28 = (unsigned __int16 *)calloc(v27, 2u);
    v29 = v28;
    if ( !v28 )
    {
      v4 = -2147024882;
LABEL_47:
      v7 = Buffer;
LABEL_18:
      if ( !v2 )
        goto LABEL_20;
      break;
    }
    StringCchPrintfW(v28, v27, L"\\\\%s\\%s%s", v11, v25, &v2[v23]);
    free(v2);
    v2 = v29;
  }
  free(v2);
  v7 = Buffer;
LABEL_20:
  if ( v7 )
    NetApiBufferFree(v7);
  if ( v4 < 0 )
  {
    if ( v5 )
      NetApiBufferFree(v5);
  }
  else
  {
    *v31 = (struct _DFS_INFO_3 *)v5;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007818  mov     [rsp+arg_18], rbx
0x18000781d  mov     [rsp+arg_8], rdx
0x180007822  push    rbp
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  push    r12
0x180007827  push    r13
0x180007829  push    r14
0x18000782b  push    r15
0x18000782d  sub     rsp, 30h
0x180007831  xor     r12d, r12d
0x180007834  mov     rax, rdx
0x180007837  test    rcx, rcx
0x18000783a  jz      loc_180007AEC
0x180007840  cmp     [rcx], r12w
0x180007844  jz      loc_180007AEC
0x18000784a  test    rax, rax
0x18000784d  jz      loc_180007AEC
0x180007853  mov     [rdx], r12
0x180007856  call    cs:__imp__wcsdup
0x18000785c  mov     r14, rax
0x18000785f  test    rax, rax
0x180007862  jnz     short loc_18000786E
0x180007864  mov     eax, 8007000Eh
0x180007869  jmp     loc_180007AF1
0x18000786e  lea     rax, [rsp+68h+arg_0]
0x180007873  mov     [rsp+68h+arg_0], r12
0x180007878  mov     r9d, 3; Level
0x18000787e  mov     [rsp+68h+Buffer], rax; Buffer
0x180007883  xor     r8d, r8d; ShareName
0x180007886  xor     edx, edx; ServerName
0x180007888  mov     rcx, r14; DfsEntryPath
0x18000788b  mov     edi, r12d
0x18000788e  mov     rsi, r12
0x180007891  call    cs:__imp_NetDfsGetClientInfo
0x180007897  test    eax, eax
0x180007899  jnz     short loc_1800078F6
0x18000789b  mov     rbx, [rsp+68h+arg_0]
0x1800078a0  lea     ecx, [rax+5Ch]
0x1800078a3  mov     rax, [rbx]
0x1800078a6  cmp     cx, [rax]
0x1800078a9  jnz     short loc_1800078B5
0x1800078ab  lea     r13d, [rcx-5Bh]
0x1800078af  cmp     cx, [rax+2]
0x1800078b3  jnz     short loc_1800078B8
0x1800078b5  mov     r13d, r12d
0x1800078b8  mov     edx, [rbx+14h]
0x1800078bb  cmp     edx, 1
0x1800078be  jnz     short loc_1800078CE
0x1800078c0  mov     rax, [rbx+18h]
0x1800078c4  mov     rbp, [rax+8]
0x1800078c8  mov     r15, [rax+10h]
0x1800078cc  jmp     short loc_180007936
0x1800078ce  test    edx, edx
0x1800078d0  jz      short loc_1800078EC
0x1800078d2  mov     r9, [rbx+18h]
0x1800078d6  mov     ecx, r12d
0x1800078d9  mov     eax, ecx
0x1800078db  lea     r8, [rax+rax*2]
0x1800078df  test    byte ptr [r9+r8*8], 4
0x1800078e4  jnz     short loc_180007927
0x1800078e6  inc     ecx
0x1800078e8  cmp     ecx, edx
0x1800078ea  jb      short loc_1800078D9
0x1800078ec  mov     edi, 80004005h
0x1800078f1  test    r14, r14
0x1800078f4  jz      short loc_180007904
0x1800078f6  mov     rcx, r14; Block
0x1800078f9  call    cs:__imp_free
0x1800078ff  mov     rbx, [rsp+68h+arg_0]
0x180007904  test    rbx, rbx
0x180007907  jz      short loc_180007912
0x180007909  mov     rcx, rbx; Buffer
0x18000790c  call    cs:__imp_NetApiBufferFree
0x180007912  test    edi, edi
0x180007914  js      loc_180007ADA
0x18000791a  mov     rax, [rsp+68h+arg_8]
0x18000791f  mov     [rax], rsi
0x180007922  jmp     loc_180007AE8
0x180007927  mov     rbp, [r9+r8*8+8]
0x18000792c  test    rbp, rbp
0x18000792f  jz      short loc_1800078EC
0x180007931  mov     r15, [r9+r8*8+10h]
0x180007936  mov     [rsp+68h+arg_10], r15
0x18000793e  test    rsi, rsi
0x180007941  jz      short loc_180007951
0x180007943  mov     rcx, rsi; Buffer
0x180007946  call    cs:__imp_NetApiBufferFree
0x18000794c  mov     rbx, [rsp+68h+arg_0]
0x180007951  mov     edx, r13d
0x180007954  mov     rsi, rbx
0x180007957  xor     edx, 1
0x18000795a  mov     rbx, r12
0x18000795d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007961  mov     [rsp+68h+arg_0], rbx
0x180007966  mov     rcx, rax
0x180007969  inc     rcx
0x18000796c  cmp     [rbp+rcx*2+0], r12w
0x180007972  jnz     short loc_180007969
0x180007974  inc     rax
0x180007977  cmp     [r15+rax*2], r12w
0x18000797c  jnz     short loc_180007974
0x18000797e  add     edx, 3
0x180007981  add     eax, edx
0x180007983  mov     edx, 2; Size
0x180007988  add     ecx, eax
0x18000798a  movsxd  r12, ecx
0x18000798d  mov     rcx, r12; Count
0x180007990  call    cs:__imp_calloc
0x180007996  mov     r15, rax
0x180007999  test    rax, rax
0x18000799c  jz      loc_180007AD0
0x1800079a2  lea     rax, aSS_0; "\\\\%s\\%s"
0x1800079a9  test    r13d, r13d
0x1800079ac  lea     r8, aSS_1; "\\%s\\%s"
0x1800079b3  mov     r9, rbp
0x1800079b6  cmovz   r8, rax; unsigned __int16 *
0x1800079ba  mov     rdx, r12; unsigned __int64
0x1800079bd  mov     rax, [rsp+68h+arg_10]
0x1800079c5  mov     rcx, r15; unsigned __int16 *
0x1800079c8  mov     [rsp+68h+Buffer], rax
0x1800079cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800079d2  mov     rdx, [rsi]; lpString2
0x1800079d5  mov     rcx, r15; lpString1
0x1800079d8  call    cs:__imp_lstrcmpiW
0x1800079de  mov     rcx, r15; Block
0x1800079e1  mov     ebx, eax
0x1800079e3  call    cs:__imp_free
0x1800079e9  xor     r12d, r12d
0x1800079ec  test    ebx, ebx
0x1800079ee  jz      loc_180007AC6
0x1800079f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800079f8  mov     rcx, r8
0x1800079fb  inc     rcx
0x1800079fe  cmp     [r14+rcx*2], r12w
0x180007a03  jnz     short loc_1800079FB
0x180007a05  mov     rdx, [rsi]
0x180007a08  mov     rax, r8
0x180007a0b  inc     rax
0x180007a0e  cmp     [rdx+rax*2], r12w
0x180007a13  jnz     short loc_180007A0B
0x180007a15  lea     r15d, [rax+r13]
0x180007a19  cmp     ecx, r15d
0x180007a1c  jz      loc_180007AC6
0x180007a22  mov     rdx, r8
0x180007a25  inc     rdx
0x180007a28  cmp     [rbp+rdx*2+0], r12w
0x180007a2e  jnz     short loc_180007A25
0x180007a30  mov     r13, [rsp+68h+arg_10]
0x180007a38  mov     rax, r8
0x180007a3b  inc     rax
0x180007a3e  cmp     [r13+rax*2+0], r12w
0x180007a44  jnz     short loc_180007A3B
0x180007a46  sub     eax, r15d
0x180007a49  add     ecx, 4
0x180007a4c  add     eax, edx
0x180007a4e  mov     edx, 2; Size
0x180007a53  add     eax, ecx
0x180007a55  movsxd  r12, eax
0x180007a58  mov     rcx, r12; Count
0x180007a5b  call    cs:__imp_calloc
0x180007a61  mov     rbx, rax
0x180007a64  test    rax, rax
0x180007a67  jz      short loc_180007AC1
0x180007a69  movsxd  rcx, r15d
0x180007a6c  mov     r9, rbp
0x180007a6f  mov     rdx, r12; unsigned __int64
0x180007a72  lea     r8, [r14+rcx*2]
0x180007a76  mov     rcx, rax; unsigned __int16 *
0x180007a79  mov     [rsp+68h+var_40], r8
0x180007a7e  lea     r8, aSSS; "\\\\%s\\%s%s"
0x180007a85  mov     [rsp+68h+Buffer], r13
0x180007a8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007a8f  mov     rcx, r14; Block
0x180007a92  call    cs:__imp_free
0x180007a98  lea     rax, [rsp+68h+arg_0]
0x180007a9d  mov     r9d, 3; Level
0x180007aa3  xor     r8d, r8d; ShareName
0x180007aa6  mov     [rsp+68h+Buffer], rax; Buffer
0x180007aab  xor     edx, edx; ServerName
0x180007aad  mov     rcx, rbx; DfsEntryPath
0x180007ab0  mov     r14, rbx
0x180007ab3  call    cs:__imp_NetDfsGetClientInfo
0x180007ab9  xor     r12d, r12d
0x180007abc  jmp     loc_180007897
0x180007ac1  mov     edi, 8007000Eh
0x180007ac6  mov     rbx, [rsp+68h+arg_0]
0x180007acb  jmp     loc_1800078F1
0x180007ad0  mov     edi, 8007000Eh
0x180007ad5  jmp     loc_1800078F1
0x180007ada  test    rsi, rsi
0x180007add  jz      short loc_180007AE8
0x180007adf  mov     rcx, rsi; Buffer
0x180007ae2  call    cs:__imp_NetApiBufferFree
0x180007ae8  mov     eax, edi
0x180007aea  jmp     short loc_180007AF1
0x180007aec  mov     eax, 80070057h
0x180007af1  mov     rbx, [rsp+68h+arg_18]
0x180007af9  add     rsp, 30h
0x180007afd  pop     r15
0x180007aff  pop     r14
0x180007b01  pop     r13
0x180007b03  pop     r12
0x180007b05  pop     rdi
0x180007b06  pop     rsi
0x180007b07  pop     rbp
0x180007b08  retn
```
