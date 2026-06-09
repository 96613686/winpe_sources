# _anonymous_namespace_::AllocEventProperties

- ea: `0x18000fd2c`
- end: `0x18000fe5a`
- name: `_anonymous_namespace_::AllocEventProperties`
- size: `302`
- prototype: `_DWORD *__fastcall(__int64, __int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800103ec`
- `0x180010488`
- `0x1800105fc`

## callees

- `0x18000fd2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fdef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fdef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdfd`

## pseudocode

```c
_DWORD *__fastcall anonymous_namespace_::AllocEventProperties(__int64 a1, __int64 *a2)
{
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  _DWORD *v6; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  _WORD *v12; // rax
  _WORD *v13; // r10
  _WORD *v14; // rcx
  HANDLE v15; // rax
  _WORD *v16; // rax
  _WORD *v17; // rcx

  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 8u, 0x1078u);
  v6 = v5;
  if ( !v5 )
    return 0;
  *(_DWORD *)v5 = 4216;
  v8 = 2147483646;
  *((_DWORD *)v5 + 11) = 0x20000;
  v9 = 1024;
  *((_DWORD *)v5 + 10) = 2;
  v10 = 2147483646;
  v11 = 1024;
  *(_OWORD *)(v5 + 24) = *(_OWORD *)(a1 + 8);
  *((_DWORD *)v5 + 16) = *(_DWORD *)(a1 + 64);
  *((_DWORD *)v5 + 15) = *(_DWORD *)(a1 + 56);
  *((_DWORD *)v5 + 17) = *(_DWORD *)(a1 + 60);
  v12 = v5 + 120;
  v6[29] = 120;
  v6[28] = 2168;
  v13 = *(_WORD **)a1;
  do
  {
    if ( !v10 )
      break;
    if ( !*v13 )
      break;
    *v12++ = *v13++;
    --v10;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  if ( !v11 )
    goto LABEL_10;
  if ( !a2 )
    a2 = qword_180015BA0;
  v16 = v6 + 542;
  do
  {
    if ( !v8 )
      break;
    if ( !*(_WORD *)a2 )
      break;
    *v16 = *(_WORD *)a2;
    a2 = (__int64 *)((char *)a2 + 2);
    ++v16;
    --v8;
    --v9;
  }
  while ( v9 );
  v17 = v16 - 1;
  if ( v9 )
    v17 = v16;
  *v17 = 0;
  if ( !v9 )
  {
LABEL_10:
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fd2c  push    rbx
0x18000fd2e  push    rbp
0x18000fd2f  push    rsi
0x18000fd30  push    rdi
0x18000fd31  sub     rsp, 28h
0x18000fd35  mov     rdi, rdx
0x18000fd38  mov     rsi, rcx
0x18000fd3b  call    cs:__imp_GetProcessHeap
0x18000fd41  mov     edx, 8; dwFlags
0x18000fd46  mov     r8d, 1078h; dwBytes
0x18000fd4c  mov     rcx, rax; hHeap
0x18000fd4f  call    cs:__imp_HeapAlloc
0x18000fd55  xor     ebp, ebp
0x18000fd57  mov     rbx, rax
0x18000fd5a  test    rax, rax
0x18000fd5d  jnz     short loc_18000FD66
0x18000fd5f  xor     eax, eax
0x18000fd61  jmp     loc_18000FE51
0x18000fd66  mov     dword ptr [rax], 1078h
0x18000fd6c  mov     r9d, 7FFFFFFEh
0x18000fd72  mov     dword ptr [rax+2Ch], 20000h
0x18000fd79  mov     edx, 400h
0x18000fd7e  mov     dword ptr [rax+28h], 2
0x18000fd85  mov     ecx, r9d
0x18000fd88  movups  xmm0, xmmword ptr [rsi+8]
0x18000fd8c  mov     r8d, edx
0x18000fd8f  movdqu  xmmword ptr [rax+18h], xmm0
0x18000fd94  mov     eax, [rsi+40h]
0x18000fd97  mov     [rbx+40h], eax
0x18000fd9a  mov     eax, [rsi+38h]
0x18000fd9d  mov     [rbx+3Ch], eax
0x18000fda0  mov     eax, [rsi+3Ch]
0x18000fda3  mov     [rbx+44h], eax
0x18000fda6  lea     rax, [rbx+78h]
0x18000fdaa  mov     dword ptr [rbx+74h], 78h ; 'x'
0x18000fdb1  mov     dword ptr [rbx+70h], 878h
0x18000fdb8  mov     r10, [rsi]
0x18000fdbb  test    rcx, rcx
0x18000fdbe  jz      short loc_18000FDDF
0x18000fdc0  movzx   r11d, word ptr [r10]
0x18000fdc4  test    r11w, r11w
0x18000fdc8  jz      short loc_18000FDDF
0x18000fdca  mov     [rax], r11w
0x18000fdce  add     r10, 2
0x18000fdd2  add     rax, 2
0x18000fdd6  dec     rcx
0x18000fdd9  sub     r8, 1
0x18000fddd  jnz     short loc_18000FDBB
0x18000fddf  test    r8, r8
0x18000fde2  lea     rcx, [rax-2]
0x18000fde6  cmovnz  rcx, rax
0x18000fdea  mov     [rcx], bp
0x18000fded  jnz     short loc_18000FE08
0x18000fdef  call    cs:__imp_GetProcessHeap
0x18000fdf5  mov     r8, rbx; lpMem
0x18000fdf8  xor     edx, edx; dwFlags
0x18000fdfa  mov     rcx, rax; hHeap
0x18000fdfd  call    cs:__imp_HeapFree
0x18000fe03  jmp     loc_18000FD5F
0x18000fe08  lea     rax, qword_180015BA0
0x18000fe0f  test    rdi, rdi
0x18000fe12  cmovz   rdi, rax
0x18000fe16  lea     rax, [rbx+878h]
0x18000fe1d  test    r9, r9
0x18000fe20  jz      short loc_18000FE3E
0x18000fe22  movzx   ecx, word ptr [rdi]
0x18000fe25  test    cx, cx
0x18000fe28  jz      short loc_18000FE3E
0x18000fe2a  mov     [rax], cx
0x18000fe2d  add     rdi, 2
0x18000fe31  add     rax, 2
0x18000fe35  dec     r9
0x18000fe38  sub     rdx, 1
0x18000fe3c  jnz     short loc_18000FE1D
0x18000fe3e  test    rdx, rdx
0x18000fe41  lea     rcx, [rax-2]
0x18000fe45  cmovnz  rcx, rax
0x18000fe49  mov     [rcx], bp
0x18000fe4c  jz      short loc_18000FDEF
0x18000fe4e  mov     rax, rbx
0x18000fe51  add     rsp, 28h
0x18000fe55  pop     rdi
0x18000fe56  pop     rsi
0x18000fe57  pop     rbp
0x18000fe58  pop     rbx
0x18000fe59  retn
```
