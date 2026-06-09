# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800182a4`
- end: `0x1800184bd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015d20`

## callees

- `0x180002024`
- `0x180016e88`
- `0x1800182a4`
- `0x180019c40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001839a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001839a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001838c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001838c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x1800182a4  push    rbx
0x1800182a6  push    rbp
0x1800182a7  push    rsi
0x1800182a8  push    rdi
0x1800182a9  push    r12
0x1800182ab  push    r13
0x1800182ad  push    r14
0x1800182af  push    r15
0x1800182b1  sub     rsp, 28h
0x1800182b5  mov     [rcx+4], r8d
0x1800182b9  xor     r13d, r13d
0x1800182bc  mov     eax, [rdx+8]
0x1800182bf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800182c3  mov     [rcx+8], eax
0x1800182c6  mov     rdi, rcx
0x1800182c9  mov     [rcx+10h], r13
0x1800182cd  mov     r12, rdx
0x1800182d0  movzx   eax, word ptr [rdx+40h]
0x1800182d4  mov     [rcx+18h], ax
0x1800182d8  mov     al, [rdx]
0x1800182da  mov     [rcx+1Ah], al
0x1800182dd  mov     [rcx+20h], r13
0x1800182e1  mov     rax, [rdx+88h]
0x1800182e8  mov     [rcx+28h], rax
0x1800182ec  mov     rax, [rdx+90h]
0x1800182f3  mov     [rcx+30h], rax
0x1800182f7  mov     [rcx+38h], r13
0x1800182fb  mov     rcx, [rdx+38h]
0x1800182ff  lea     edx, [rbp+2]
0x180018302  test    rcx, rcx
0x180018305  jnz     short loc_18001830C
0x180018307  mov     r8d, edx
0x18001830a  jmp     short loc_18001831C
0x18001830c  mov     rax, rbp
0x18001830f  inc     rax
0x180018312  cmp     [rcx+rax], r13b
0x180018316  jnz     short loc_18001830F
0x180018318  lea     r8, [rax+1]; unsigned __int64
0x18001831c  mov     rcx, [r12+80h]
0x180018324  test    rcx, rcx
0x180018327  jz      short loc_180018339
0x180018329  mov     rax, rbp
0x18001832c  inc     rax
0x18001832f  cmp     [rcx+rax], r13b
0x180018333  jnz     short loc_18001832C
0x180018335  lea     rdx, [rax+1]
0x180018339  mov     rcx, [r12+18h]
0x18001833e  test    rcx, rcx
0x180018341  jnz     short loc_180018348
0x180018343  lea     eax, [rcx+2]
0x180018346  jmp     short loc_18001835D
0x180018348  mov     rax, rbp
0x18001834b  inc     rax
0x18001834e  cmp     [rcx+rax*2], r13w
0x180018353  jnz     short loc_18001834B
0x180018355  lea     rax, ds:2[rax*2]
0x18001835d  lea     r14, [rdx+rax]
0x180018361  add     r14, r8
0x180018364  lea     rsi, [rdi+48h]
0x180018368  cmp     [rdi+40h], r13
0x18001836c  jz      short loc_180018373
0x18001836e  cmp     [rsi], r14
0x180018371  jnb     short loc_1800183A7
0x180018373  mov     rdx, r14; dwBytes
0x180018376  mov     ecx, 8; dwFlags
0x18001837b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180018380  mov     r15, rax
0x180018383  test    rax, rax
0x180018386  jz      short loc_1800183A7
0x180018388  mov     rbx, [rdi+40h]
0x18001838c  call    cs:__imp_GetProcessHeap
0x180018392  mov     r8, rbx; lpMem
0x180018395  xor     edx, edx; dwFlags
0x180018397  mov     rcx, rax; hHeap
0x18001839a  call    cs:__imp_HeapFree
0x1800183a0  mov     [rdi+40h], r15
0x1800183a4  mov     [rsi], r14
0x1800183a7  mov     rbx, [rdi+40h]
0x1800183ab  test    rbx, rbx
0x1800183ae  jz      loc_1800184AC
0x1800183b4  mov     rdx, [rsi]; DestinationSize
0x1800183b7  lea     rsi, [rdx+rbx]
0x1800183bb  cmp     rbx, rsi
0x1800183be  jz      short loc_1800183FE
0x1800183c0  mov     r8, [r12+38h]; Source
0x1800183c5  test    r8, r8
0x1800183c8  jz      short loc_1800183FE
0x1800183ca  cmp     [r8], r13b
0x1800183cd  jz      short loc_1800183FE
0x1800183cf  mov     rax, rbp
0x1800183d2  inc     rax
0x1800183d5  cmp     [r8+rax], r13b
0x1800183d9  jnz     short loc_1800183D2
0x1800183db  lea     r14, [rax+1]
0x1800183df  cmp     rdx, r14
0x1800183e2  jnb     short loc_1800183EA
0x1800183e4  mov     [rdi+10h], r13
0x1800183e8  jmp     short loc_180018407
0x1800183ea  mov     r9, r14; SourceSize
0x1800183ed  mov     rcx, rbx; Destination
0x1800183f0  call    memcpy_s
0x1800183f5  mov     [rdi+10h], rbx
0x1800183f9  add     rbx, r14
0x1800183fc  jmp     short loc_180018402
0x1800183fe  mov     [rdi+10h], r13
0x180018402  cmp     rbx, rsi
0x180018405  jz      short loc_18001844E
0x180018407  mov     r8, [r12+80h]; Source
0x18001840f  test    r8, r8
0x180018412  jz      short loc_18001844E
0x180018414  cmp     [r8], r13b
0x180018417  jz      short loc_18001844E
0x180018419  mov     rax, rbp
0x18001841c  inc     rax
0x18001841f  cmp     [r8+rax], r13b
0x180018423  jnz     short loc_18001841C
0x180018425  mov     rdx, rsi
0x180018428  lea     r14, [rax+1]
0x18001842c  sub     rdx, rbx; DestinationSize
0x18001842f  cmp     rdx, r14
0x180018432  jnb     short loc_18001843A
0x180018434  mov     [rdi+20h], r13
0x180018438  jmp     short loc_180018457
0x18001843a  mov     r9, r14; SourceSize
0x18001843d  mov     rcx, rbx; Destination
0x180018440  call    memcpy_s
0x180018445  mov     [rdi+20h], rbx
0x180018449  add     rbx, r14
0x18001844c  jmp     short loc_180018452
0x18001844e  mov     [rdi+20h], r13
0x180018452  cmp     rbx, rsi
0x180018455  jz      short loc_180018498
0x180018457  mov     r8, [r12+18h]; Source
0x18001845c  test    r8, r8
0x18001845f  jz      short loc_180018498
0x180018461  cmp     [r8], r13w
0x180018465  jz      short loc_180018498
0x180018467  inc     rbp
0x18001846a  cmp     [r8+rbp*2], r13w
0x18001846f  jnz     short loc_180018467
0x180018471  mov     rdx, rsi
0x180018474  lea     r14, ds:2[rbp*2]
0x18001847c  sub     rdx, rbx; DestinationSize
0x18001847f  cmp     rdx, r14
0x180018482  jb      short loc_180018498
0x180018484  mov     r9, r14; SourceSize
0x180018487  mov     rcx, rbx; Destination
0x18001848a  call    memcpy_s
0x18001848f  mov     [rdi+38h], rbx
0x180018493  add     rbx, r14
0x180018496  jmp     short loc_18001849C
0x180018498  mov     [rdi+38h], r13
0x18001849c  sub     rsi, rbx
0x18001849f  xor     edx, edx; Val
0x1800184a1  mov     r8, rsi; Size
0x1800184a4  mov     rcx, rbx; void *
0x1800184a7  call    memset_0
0x1800184ac  add     rsp, 28h
0x1800184b0  pop     r15
0x1800184b2  pop     r14
0x1800184b4  pop     r13
0x1800184b6  pop     r12
0x1800184b8  pop     rdi
0x1800184b9  pop     rsi
0x1800184ba  pop     rbp
0x1800184bb  pop     rbx
0x1800184bc  retn
```
