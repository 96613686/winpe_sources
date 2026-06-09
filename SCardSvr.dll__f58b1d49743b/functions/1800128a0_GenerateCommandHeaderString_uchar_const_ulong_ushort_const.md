# GenerateCommandHeaderString(uchar const *,ulong,ushort const * *)

- ea: `0x1800128a0`
- end: `0x180012a21`
- name: `?GenerateCommandHeaderString@@YAKPEBEKPEAPEBG@Z`
- size: `385`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b974`

## callees

- `0x1800128a0`
- `0x18001364c`
- `0x180027708`
- `0x1800277fc`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012933`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800129e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012933`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800129e6`

## pseudocode

```c
__int64 __fastcall GenerateCommandHeaderString(const unsigned __int8 *a1, unsigned int a2, const unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  wchar_t *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  HANDLE ProcessHeap; // rax
  const wchar_t *v11; // rcx
  _WORD *v12; // rdi
  size_t v13; // r8
  size_t v14; // rdx
  size_t *v15; // r8
  unsigned int v16; // ebp
  unsigned int v17; // ebx
  unsigned __int64 v18; // r14
  __int64 v19; // rcx
  HANDLE v20; // rax
  size_t v22; // [rsp+20h] [rbp-78h]
  unsigned __int16 v23[2]; // [rsp+30h] [rbp-68h] BYREF
  __int16 v24; // [rsp+34h] [rbp-64h]
  wchar_t pszSrc[12]; // [rsp+38h] [rbp-60h] BYREF

  *(_DWORD *)v23 = 0;
  v24 = 0;
  wcscpy(pszSrc, L"XX XX XX XX");
  if ( !a3 )
    return 87;
  v7 = pszSrc;
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    return 87;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 0, 2 * v9 + 2);
  if ( !v12 )
    return 14;
  if ( StringValidateDestW(v11, v9 + 1, v13) < 0 )
  {
    if ( v14 )
      *v12 = 0;
    goto LABEL_19;
  }
  if ( StringCopyWorkerW(v12, v14, v15, pszSrc, v22) < 0 )
  {
LABEL_19:
    v6 = 87;
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v12);
    return v6;
  }
  v16 = 0;
  v17 = 0;
  while ( v17 < a2 )
  {
    v18 = v16 + 1;
    if ( v18 >= v9 )
      break;
    if ( (int)StringCchPrintfW(v23, 3u, L"%02x", a1[v17]) < 0 )
      goto LABEL_19;
    ++v17;
    v19 = v16;
    v16 += 3;
    v12[v19] = v23[0];
    v12[v18] = v23[1];
  }
  v6 = 0;
  v12[v9] = 0;
  *a3 = v12;
  return v6;
}

```

## disassembly

```asm
0x1800128a0  mov     [rsp+arg_8], rbx
0x1800128a5  push    rbp
0x1800128a6  push    rsi
0x1800128a7  push    rdi
0x1800128a8  push    r12
0x1800128aa  push    r13
0x1800128ac  push    r14
0x1800128ae  push    r15
0x1800128b0  sub     rsp, 60h
0x1800128b4  mov     rax, cs:__security_cookie
0x1800128bb  xor     rax, rsp
0x1800128be  mov     [rsp+98h+var_48], rax
0x1800128c3  movups  xmm0, xmmword ptr cs:aXxXxXxXx; "XX XX XX XX"
0x1800128ca  xor     eax, eax
0x1800128cc  xor     r14d, r14d
0x1800128cf  movsd   xmm1, qword ptr cs:aXxXxXxXx+10h; " XX"
0x1800128d7  mov     r15, r8
0x1800128da  movsd   [rsp+98h+var_50], xmm1
0x1800128e0  mov     r12d, edx
0x1800128e3  mov     dword ptr [rsp+98h+var_68], eax
0x1800128e7  mov     r13, rcx
0x1800128ea  mov     [rsp+98h+var_64], ax
0x1800128ef  movups  xmmword ptr [rsp+98h+pszSrc], xmm0
0x1800128f4  test    r8, r8
0x1800128f7  jnz     short loc_180012903
0x1800128f9  mov     ebx, 57h ; 'W'
0x1800128fe  jmp     loc_1800129FA
0x180012903  mov     edx, 7FFFFFFFh
0x180012908  lea     rax, [rsp+98h+pszSrc]
0x18001290d  mov     ecx, edx
0x18001290f  cmp     [rax], r14w
0x180012913  jz      short loc_18001291F
0x180012915  add     rax, 2
0x180012919  sub     rcx, 1
0x18001291d  jnz     short loc_18001290F
0x18001291f  sub     rdx, rcx
0x180012922  mov     rax, rcx
0x180012925  neg     rax
0x180012928  sbb     rsi, rsi
0x18001292b  and     rsi, rdx
0x18001292e  test    rcx, rcx
0x180012931  jz      short loc_1800128F9
0x180012933  call    cs:__imp_GetProcessHeap
0x180012939  lea     r8, ds:2[rsi*2]; dwBytes
0x180012941  xor     edx, edx; dwFlags
0x180012943  mov     rcx, rax; hHeap
0x180012946  call    cs:__imp_HeapAlloc
0x18001294c  mov     rdi, rax
0x18001294f  test    rax, rax
0x180012952  jnz     short loc_18001295C
0x180012954  lea     ebx, [rax+0Eh]
0x180012957  jmp     loc_1800129FA
0x18001295c  lea     rdx, [rsi+1]; cchDest
0x180012960  call    StringValidateDestW
0x180012965  test    eax, eax
0x180012967  js      short loc_1800129D8
0x180012969  lea     r9, [rsp+98h+pszSrc]; pszSrc
0x18001296e  mov     rcx, rdi; pszDest
0x180012971  call    StringCopyWorkerW
0x180012976  test    eax, eax
0x180012978  js      short loc_1800129E1
0x18001297a  mov     ebp, r14d
0x18001297d  mov     ebx, r14d
0x180012980  cmp     ebx, r12d
0x180012983  jnb     short loc_1800129CB
0x180012985  lea     r14d, [rbp+1]
0x180012989  cmp     r14, rsi
0x18001298c  jnb     short loc_1800129CB
0x18001298e  mov     eax, ebx
0x180012990  lea     r8, a02x; "%02x"
0x180012997  mov     edx, 3; unsigned __int64
0x18001299c  lea     rcx, [rsp+98h+var_68]; unsigned __int16 *
0x1800129a1  movzx   r9d, byte ptr [rax+r13]
0x1800129a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800129ab  test    eax, eax
0x1800129ad  js      short loc_1800129E1
0x1800129af  movzx   eax, [rsp+98h+var_68]
0x1800129b4  inc     ebx
0x1800129b6  mov     ecx, ebp
0x1800129b8  add     ebp, 3
0x1800129bb  mov     [rdi+rcx*2], ax
0x1800129bf  movzx   eax, [rsp+98h+var_68+2]
0x1800129c4  mov     [rdi+r14*2], ax
0x1800129c9  jmp     short loc_180012980
0x1800129cb  xor     ebx, ebx
0x1800129cd  xor     eax, eax
0x1800129cf  mov     [rdi+rsi*2], ax
0x1800129d3  mov     [r15], rdi
0x1800129d6  jmp     short loc_1800129FA
0x1800129d8  test    rdx, rdx
0x1800129db  jz      short loc_1800129E1
0x1800129dd  mov     [rdi], r14w
0x1800129e1  mov     ebx, 57h ; 'W'
0x1800129e6  call    cs:__imp_GetProcessHeap
0x1800129ec  mov     r8, rdi; lpMem
0x1800129ef  xor     edx, edx; dwFlags
0x1800129f1  mov     rcx, rax; hHeap
0x1800129f4  call    cs:__imp_HeapFree
0x1800129fa  mov     eax, ebx
0x1800129fc  mov     rcx, [rsp+98h+var_48]
0x180012a01  xor     rcx, rsp; StackCookie
0x180012a04  call    __security_check_cookie
0x180012a09  mov     rbx, [rsp+98h+arg_8]
0x180012a11  add     rsp, 60h
0x180012a15  pop     r15
0x180012a17  pop     r14
0x180012a19  pop     r13
0x180012a1b  pop     r12
0x180012a1d  pop     rdi
0x180012a1e  pop     rsi
0x180012a1f  pop     rbp
0x180012a20  retn
```
