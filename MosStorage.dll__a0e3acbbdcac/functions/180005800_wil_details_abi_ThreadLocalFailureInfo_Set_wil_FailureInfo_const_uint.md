# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005800`
- end: `0x180005a19`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042c0`

## callees

- `0x180002802`
- `0x180005308`
- `0x180005800`
- `0x180006798`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058e8`

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
0x180005800  push    rbx
0x180005802  push    rbp
0x180005803  push    rsi
0x180005804  push    rdi
0x180005805  push    r12
0x180005807  push    r13
0x180005809  push    r14
0x18000580b  push    r15
0x18000580d  sub     rsp, 28h
0x180005811  mov     [rcx+4], r8d
0x180005815  xor     r13d, r13d
0x180005818  mov     eax, [rdx+8]
0x18000581b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000581f  mov     [rcx+8], eax
0x180005822  mov     rdi, rcx
0x180005825  mov     [rcx+10h], r13
0x180005829  mov     r12, rdx
0x18000582c  movzx   eax, word ptr [rdx+40h]
0x180005830  mov     [rcx+18h], ax
0x180005834  mov     al, [rdx]
0x180005836  mov     [rcx+1Ah], al
0x180005839  mov     [rcx+20h], r13
0x18000583d  mov     rax, [rdx+88h]
0x180005844  mov     [rcx+28h], rax
0x180005848  mov     rax, [rdx+90h]
0x18000584f  mov     [rcx+30h], rax
0x180005853  mov     [rcx+38h], r13
0x180005857  mov     rcx, [rdx+38h]
0x18000585b  lea     edx, [rbp+2]
0x18000585e  test    rcx, rcx
0x180005861  jnz     short loc_180005868
0x180005863  mov     r8d, edx
0x180005866  jmp     short loc_180005878
0x180005868  mov     rax, rbp
0x18000586b  inc     rax
0x18000586e  cmp     [rcx+rax], r13b
0x180005872  jnz     short loc_18000586B
0x180005874  lea     r8, [rax+1]; unsigned __int64
0x180005878  mov     rcx, [r12+80h]
0x180005880  test    rcx, rcx
0x180005883  jz      short loc_180005895
0x180005885  mov     rax, rbp
0x180005888  inc     rax
0x18000588b  cmp     [rcx+rax], r13b
0x18000588f  jnz     short loc_180005888
0x180005891  lea     rdx, [rax+1]
0x180005895  mov     rcx, [r12+18h]
0x18000589a  test    rcx, rcx
0x18000589d  jnz     short loc_1800058A4
0x18000589f  lea     eax, [rcx+2]
0x1800058a2  jmp     short loc_1800058B9
0x1800058a4  mov     rax, rbp
0x1800058a7  inc     rax
0x1800058aa  cmp     [rcx+rax*2], r13w
0x1800058af  jnz     short loc_1800058A7
0x1800058b1  lea     rax, ds:2[rax*2]
0x1800058b9  lea     r14, [rdx+rax]
0x1800058bd  add     r14, r8
0x1800058c0  lea     rsi, [rdi+48h]
0x1800058c4  cmp     [rdi+40h], r13
0x1800058c8  jz      short loc_1800058CF
0x1800058ca  cmp     [rsi], r14
0x1800058cd  jnb     short loc_180005903
0x1800058cf  mov     rdx, r14; dwBytes
0x1800058d2  mov     ecx, 8; dwFlags
0x1800058d7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800058dc  mov     r15, rax
0x1800058df  test    rax, rax
0x1800058e2  jz      short loc_180005903
0x1800058e4  mov     rbx, [rdi+40h]
0x1800058e8  call    cs:__imp_GetProcessHeap
0x1800058ee  mov     r8, rbx; lpMem
0x1800058f1  xor     edx, edx; dwFlags
0x1800058f3  mov     rcx, rax; hHeap
0x1800058f6  call    cs:__imp_HeapFree
0x1800058fc  mov     [rdi+40h], r15
0x180005900  mov     [rsi], r14
0x180005903  mov     rbx, [rdi+40h]
0x180005907  test    rbx, rbx
0x18000590a  jz      loc_180005A08
0x180005910  mov     rdx, [rsi]; DestinationSize
0x180005913  lea     rsi, [rdx+rbx]
0x180005917  cmp     rbx, rsi
0x18000591a  jz      short loc_18000595A
0x18000591c  mov     r8, [r12+38h]; Source
0x180005921  test    r8, r8
0x180005924  jz      short loc_18000595A
0x180005926  cmp     [r8], r13b
0x180005929  jz      short loc_18000595A
0x18000592b  mov     rax, rbp
0x18000592e  inc     rax
0x180005931  cmp     [r8+rax], r13b
0x180005935  jnz     short loc_18000592E
0x180005937  lea     r14, [rax+1]
0x18000593b  cmp     rdx, r14
0x18000593e  jnb     short loc_180005946
0x180005940  mov     [rdi+10h], r13
0x180005944  jmp     short loc_180005963
0x180005946  mov     r9, r14; SourceSize
0x180005949  mov     rcx, rbx; Destination
0x18000594c  call    memcpy_s
0x180005951  mov     [rdi+10h], rbx
0x180005955  add     rbx, r14
0x180005958  jmp     short loc_18000595E
0x18000595a  mov     [rdi+10h], r13
0x18000595e  cmp     rbx, rsi
0x180005961  jz      short loc_1800059AA
0x180005963  mov     r8, [r12+80h]; Source
0x18000596b  test    r8, r8
0x18000596e  jz      short loc_1800059AA
0x180005970  cmp     [r8], r13b
0x180005973  jz      short loc_1800059AA
0x180005975  mov     rax, rbp
0x180005978  inc     rax
0x18000597b  cmp     [r8+rax], r13b
0x18000597f  jnz     short loc_180005978
0x180005981  mov     rdx, rsi
0x180005984  lea     r14, [rax+1]
0x180005988  sub     rdx, rbx; DestinationSize
0x18000598b  cmp     rdx, r14
0x18000598e  jnb     short loc_180005996
0x180005990  mov     [rdi+20h], r13
0x180005994  jmp     short loc_1800059B3
0x180005996  mov     r9, r14; SourceSize
0x180005999  mov     rcx, rbx; Destination
0x18000599c  call    memcpy_s
0x1800059a1  mov     [rdi+20h], rbx
0x1800059a5  add     rbx, r14
0x1800059a8  jmp     short loc_1800059AE
0x1800059aa  mov     [rdi+20h], r13
0x1800059ae  cmp     rbx, rsi
0x1800059b1  jz      short loc_1800059F4
0x1800059b3  mov     r8, [r12+18h]; Source
0x1800059b8  test    r8, r8
0x1800059bb  jz      short loc_1800059F4
0x1800059bd  cmp     [r8], r13w
0x1800059c1  jz      short loc_1800059F4
0x1800059c3  inc     rbp
0x1800059c6  cmp     [r8+rbp*2], r13w
0x1800059cb  jnz     short loc_1800059C3
0x1800059cd  mov     rdx, rsi
0x1800059d0  lea     r14, ds:2[rbp*2]
0x1800059d8  sub     rdx, rbx; DestinationSize
0x1800059db  cmp     rdx, r14
0x1800059de  jb      short loc_1800059F4
0x1800059e0  mov     r9, r14; SourceSize
0x1800059e3  mov     rcx, rbx; Destination
0x1800059e6  call    memcpy_s
0x1800059eb  mov     [rdi+38h], rbx
0x1800059ef  add     rbx, r14
0x1800059f2  jmp     short loc_1800059F8
0x1800059f4  mov     [rdi+38h], r13
0x1800059f8  sub     rsi, rbx
0x1800059fb  xor     edx, edx; Val
0x1800059fd  mov     r8, rsi; Size
0x180005a00  mov     rcx, rbx; void *
0x180005a03  call    memset_0
0x180005a08  add     rsp, 28h
0x180005a0c  pop     r15
0x180005a0e  pop     r14
0x180005a10  pop     r13
0x180005a12  pop     r12
0x180005a14  pop     rdi
0x180005a15  pop     rsi
0x180005a16  pop     rbp
0x180005a17  pop     rbx
0x180005a18  retn
```
