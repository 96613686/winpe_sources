# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009394`
- end: `0x1800095ad`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007b10`

## callees

- `0x180004118`
- `0x180008d74`
- `0x180009394`
- `0x18000ab68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000948a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000948a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000947c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000947c`

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
0x180009394  push    rbx
0x180009396  push    rbp
0x180009397  push    rsi
0x180009398  push    rdi
0x180009399  push    r12
0x18000939b  push    r13
0x18000939d  push    r14
0x18000939f  push    r15
0x1800093a1  sub     rsp, 28h
0x1800093a5  mov     [rcx+4], r8d
0x1800093a9  xor     r13d, r13d
0x1800093ac  mov     eax, [rdx+8]
0x1800093af  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800093b3  mov     [rcx+8], eax
0x1800093b6  mov     rdi, rcx
0x1800093b9  mov     [rcx+10h], r13
0x1800093bd  mov     r12, rdx
0x1800093c0  movzx   eax, word ptr [rdx+40h]
0x1800093c4  mov     [rcx+18h], ax
0x1800093c8  mov     al, [rdx]
0x1800093ca  mov     [rcx+1Ah], al
0x1800093cd  mov     [rcx+20h], r13
0x1800093d1  mov     rax, [rdx+88h]
0x1800093d8  mov     [rcx+28h], rax
0x1800093dc  mov     rax, [rdx+90h]
0x1800093e3  mov     [rcx+30h], rax
0x1800093e7  mov     [rcx+38h], r13
0x1800093eb  mov     rcx, [rdx+38h]
0x1800093ef  lea     edx, [rbp+2]
0x1800093f2  test    rcx, rcx
0x1800093f5  jnz     short loc_1800093FC
0x1800093f7  mov     r8d, edx
0x1800093fa  jmp     short loc_18000940C
0x1800093fc  mov     rax, rbp
0x1800093ff  inc     rax
0x180009402  cmp     [rcx+rax], r13b
0x180009406  jnz     short loc_1800093FF
0x180009408  lea     r8, [rax+1]; unsigned __int64
0x18000940c  mov     rcx, [r12+80h]
0x180009414  test    rcx, rcx
0x180009417  jz      short loc_180009429
0x180009419  mov     rax, rbp
0x18000941c  inc     rax
0x18000941f  cmp     [rcx+rax], r13b
0x180009423  jnz     short loc_18000941C
0x180009425  lea     rdx, [rax+1]
0x180009429  mov     rcx, [r12+18h]
0x18000942e  test    rcx, rcx
0x180009431  jnz     short loc_180009438
0x180009433  lea     eax, [rcx+2]
0x180009436  jmp     short loc_18000944D
0x180009438  mov     rax, rbp
0x18000943b  inc     rax
0x18000943e  cmp     [rcx+rax*2], r13w
0x180009443  jnz     short loc_18000943B
0x180009445  lea     rax, ds:2[rax*2]
0x18000944d  lea     r14, [rdx+rax]
0x180009451  add     r14, r8
0x180009454  lea     rsi, [rdi+48h]
0x180009458  cmp     [rdi+40h], r13
0x18000945c  jz      short loc_180009463
0x18000945e  cmp     [rsi], r14
0x180009461  jnb     short loc_180009497
0x180009463  mov     rdx, r14; dwBytes
0x180009466  mov     ecx, 8; dwFlags
0x18000946b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009470  mov     r15, rax
0x180009473  test    rax, rax
0x180009476  jz      short loc_180009497
0x180009478  mov     rbx, [rdi+40h]
0x18000947c  call    cs:__imp_GetProcessHeap
0x180009482  mov     r8, rbx; lpMem
0x180009485  xor     edx, edx; dwFlags
0x180009487  mov     rcx, rax; hHeap
0x18000948a  call    cs:__imp_HeapFree
0x180009490  mov     [rdi+40h], r15
0x180009494  mov     [rsi], r14
0x180009497  mov     rbx, [rdi+40h]
0x18000949b  test    rbx, rbx
0x18000949e  jz      loc_18000959C
0x1800094a4  mov     rdx, [rsi]; DestinationSize
0x1800094a7  lea     rsi, [rdx+rbx]
0x1800094ab  cmp     rbx, rsi
0x1800094ae  jz      short loc_1800094EE
0x1800094b0  mov     r8, [r12+38h]; Source
0x1800094b5  test    r8, r8
0x1800094b8  jz      short loc_1800094EE
0x1800094ba  cmp     [r8], r13b
0x1800094bd  jz      short loc_1800094EE
0x1800094bf  mov     rax, rbp
0x1800094c2  inc     rax
0x1800094c5  cmp     [r8+rax], r13b
0x1800094c9  jnz     short loc_1800094C2
0x1800094cb  lea     r14, [rax+1]
0x1800094cf  cmp     rdx, r14
0x1800094d2  jnb     short loc_1800094DA
0x1800094d4  mov     [rdi+10h], r13
0x1800094d8  jmp     short loc_1800094F7
0x1800094da  mov     r9, r14; SourceSize
0x1800094dd  mov     rcx, rbx; Destination
0x1800094e0  call    memcpy_s
0x1800094e5  mov     [rdi+10h], rbx
0x1800094e9  add     rbx, r14
0x1800094ec  jmp     short loc_1800094F2
0x1800094ee  mov     [rdi+10h], r13
0x1800094f2  cmp     rbx, rsi
0x1800094f5  jz      short loc_18000953E
0x1800094f7  mov     r8, [r12+80h]; Source
0x1800094ff  test    r8, r8
0x180009502  jz      short loc_18000953E
0x180009504  cmp     [r8], r13b
0x180009507  jz      short loc_18000953E
0x180009509  mov     rax, rbp
0x18000950c  inc     rax
0x18000950f  cmp     [r8+rax], r13b
0x180009513  jnz     short loc_18000950C
0x180009515  mov     rdx, rsi
0x180009518  lea     r14, [rax+1]
0x18000951c  sub     rdx, rbx; DestinationSize
0x18000951f  cmp     rdx, r14
0x180009522  jnb     short loc_18000952A
0x180009524  mov     [rdi+20h], r13
0x180009528  jmp     short loc_180009547
0x18000952a  mov     r9, r14; SourceSize
0x18000952d  mov     rcx, rbx; Destination
0x180009530  call    memcpy_s
0x180009535  mov     [rdi+20h], rbx
0x180009539  add     rbx, r14
0x18000953c  jmp     short loc_180009542
0x18000953e  mov     [rdi+20h], r13
0x180009542  cmp     rbx, rsi
0x180009545  jz      short loc_180009588
0x180009547  mov     r8, [r12+18h]; Source
0x18000954c  test    r8, r8
0x18000954f  jz      short loc_180009588
0x180009551  cmp     [r8], r13w
0x180009555  jz      short loc_180009588
0x180009557  inc     rbp
0x18000955a  cmp     [r8+rbp*2], r13w
0x18000955f  jnz     short loc_180009557
0x180009561  mov     rdx, rsi
0x180009564  lea     r14, ds:2[rbp*2]
0x18000956c  sub     rdx, rbx; DestinationSize
0x18000956f  cmp     rdx, r14
0x180009572  jb      short loc_180009588
0x180009574  mov     r9, r14; SourceSize
0x180009577  mov     rcx, rbx; Destination
0x18000957a  call    memcpy_s
0x18000957f  mov     [rdi+38h], rbx
0x180009583  add     rbx, r14
0x180009586  jmp     short loc_18000958C
0x180009588  mov     [rdi+38h], r13
0x18000958c  sub     rsi, rbx
0x18000958f  xor     edx, edx; Val
0x180009591  mov     r8, rsi; Size
0x180009594  mov     rcx, rbx; void *
0x180009597  call    memset_0
0x18000959c  add     rsp, 28h
0x1800095a0  pop     r15
0x1800095a2  pop     r14
0x1800095a4  pop     r13
0x1800095a6  pop     r12
0x1800095a8  pop     rdi
0x1800095a9  pop     rsi
0x1800095aa  pop     rbp
0x1800095ab  pop     rbx
0x1800095ac  retn
```
