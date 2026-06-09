# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004760`
- end: `0x180004979`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800033b0`

## callees

- `0x180001f4a`
- `0x1800043f8`
- `0x180004760`
- `0x180005718`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004856`

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
0x180004760  push    rbx
0x180004762  push    rbp
0x180004763  push    rsi
0x180004764  push    rdi
0x180004765  push    r12
0x180004767  push    r13
0x180004769  push    r14
0x18000476b  push    r15
0x18000476d  sub     rsp, 28h
0x180004771  mov     [rcx+4], r8d
0x180004775  xor     r13d, r13d
0x180004778  mov     eax, [rdx+8]
0x18000477b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000477f  mov     [rcx+8], eax
0x180004782  mov     rdi, rcx
0x180004785  mov     [rcx+10h], r13
0x180004789  mov     r12, rdx
0x18000478c  movzx   eax, word ptr [rdx+40h]
0x180004790  mov     [rcx+18h], ax
0x180004794  mov     al, [rdx]
0x180004796  mov     [rcx+1Ah], al
0x180004799  mov     [rcx+20h], r13
0x18000479d  mov     rax, [rdx+88h]
0x1800047a4  mov     [rcx+28h], rax
0x1800047a8  mov     rax, [rdx+90h]
0x1800047af  mov     [rcx+30h], rax
0x1800047b3  mov     [rcx+38h], r13
0x1800047b7  mov     rcx, [rdx+38h]
0x1800047bb  lea     edx, [rbp+2]
0x1800047be  test    rcx, rcx
0x1800047c1  jnz     short loc_1800047C8
0x1800047c3  mov     r8d, edx
0x1800047c6  jmp     short loc_1800047D8
0x1800047c8  mov     rax, rbp
0x1800047cb  inc     rax
0x1800047ce  cmp     [rcx+rax], r13b
0x1800047d2  jnz     short loc_1800047CB
0x1800047d4  lea     r8, [rax+1]; unsigned __int64
0x1800047d8  mov     rcx, [r12+80h]
0x1800047e0  test    rcx, rcx
0x1800047e3  jz      short loc_1800047F5
0x1800047e5  mov     rax, rbp
0x1800047e8  inc     rax
0x1800047eb  cmp     [rcx+rax], r13b
0x1800047ef  jnz     short loc_1800047E8
0x1800047f1  lea     rdx, [rax+1]
0x1800047f5  mov     rcx, [r12+18h]
0x1800047fa  test    rcx, rcx
0x1800047fd  jnz     short loc_180004804
0x1800047ff  lea     eax, [rcx+2]
0x180004802  jmp     short loc_180004819
0x180004804  mov     rax, rbp
0x180004807  inc     rax
0x18000480a  cmp     [rcx+rax*2], r13w
0x18000480f  jnz     short loc_180004807
0x180004811  lea     rax, ds:2[rax*2]
0x180004819  lea     r14, [rdx+rax]
0x18000481d  add     r14, r8
0x180004820  lea     rsi, [rdi+48h]
0x180004824  cmp     [rdi+40h], r13
0x180004828  jz      short loc_18000482F
0x18000482a  cmp     [rsi], r14
0x18000482d  jnb     short loc_180004863
0x18000482f  mov     rdx, r14; dwBytes
0x180004832  mov     ecx, 8; dwFlags
0x180004837  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000483c  mov     r15, rax
0x18000483f  test    rax, rax
0x180004842  jz      short loc_180004863
0x180004844  mov     rbx, [rdi+40h]
0x180004848  call    cs:__imp_GetProcessHeap
0x18000484e  mov     r8, rbx; lpMem
0x180004851  xor     edx, edx; dwFlags
0x180004853  mov     rcx, rax; hHeap
0x180004856  call    cs:__imp_HeapFree
0x18000485c  mov     [rdi+40h], r15
0x180004860  mov     [rsi], r14
0x180004863  mov     rbx, [rdi+40h]
0x180004867  test    rbx, rbx
0x18000486a  jz      loc_180004968
0x180004870  mov     rdx, [rsi]; DestinationSize
0x180004873  lea     rsi, [rdx+rbx]
0x180004877  cmp     rbx, rsi
0x18000487a  jz      short loc_1800048BA
0x18000487c  mov     r8, [r12+38h]; Source
0x180004881  test    r8, r8
0x180004884  jz      short loc_1800048BA
0x180004886  cmp     [r8], r13b
0x180004889  jz      short loc_1800048BA
0x18000488b  mov     rax, rbp
0x18000488e  inc     rax
0x180004891  cmp     [r8+rax], r13b
0x180004895  jnz     short loc_18000488E
0x180004897  lea     r14, [rax+1]
0x18000489b  cmp     rdx, r14
0x18000489e  jnb     short loc_1800048A6
0x1800048a0  mov     [rdi+10h], r13
0x1800048a4  jmp     short loc_1800048C3
0x1800048a6  mov     r9, r14; SourceSize
0x1800048a9  mov     rcx, rbx; Destination
0x1800048ac  call    memcpy_s
0x1800048b1  mov     [rdi+10h], rbx
0x1800048b5  add     rbx, r14
0x1800048b8  jmp     short loc_1800048BE
0x1800048ba  mov     [rdi+10h], r13
0x1800048be  cmp     rbx, rsi
0x1800048c1  jz      short loc_18000490A
0x1800048c3  mov     r8, [r12+80h]; Source
0x1800048cb  test    r8, r8
0x1800048ce  jz      short loc_18000490A
0x1800048d0  cmp     [r8], r13b
0x1800048d3  jz      short loc_18000490A
0x1800048d5  mov     rax, rbp
0x1800048d8  inc     rax
0x1800048db  cmp     [r8+rax], r13b
0x1800048df  jnz     short loc_1800048D8
0x1800048e1  mov     rdx, rsi
0x1800048e4  lea     r14, [rax+1]
0x1800048e8  sub     rdx, rbx; DestinationSize
0x1800048eb  cmp     rdx, r14
0x1800048ee  jnb     short loc_1800048F6
0x1800048f0  mov     [rdi+20h], r13
0x1800048f4  jmp     short loc_180004913
0x1800048f6  mov     r9, r14; SourceSize
0x1800048f9  mov     rcx, rbx; Destination
0x1800048fc  call    memcpy_s
0x180004901  mov     [rdi+20h], rbx
0x180004905  add     rbx, r14
0x180004908  jmp     short loc_18000490E
0x18000490a  mov     [rdi+20h], r13
0x18000490e  cmp     rbx, rsi
0x180004911  jz      short loc_180004954
0x180004913  mov     r8, [r12+18h]; Source
0x180004918  test    r8, r8
0x18000491b  jz      short loc_180004954
0x18000491d  cmp     [r8], r13w
0x180004921  jz      short loc_180004954
0x180004923  inc     rbp
0x180004926  cmp     [r8+rbp*2], r13w
0x18000492b  jnz     short loc_180004923
0x18000492d  mov     rdx, rsi
0x180004930  lea     r14, ds:2[rbp*2]
0x180004938  sub     rdx, rbx; DestinationSize
0x18000493b  cmp     rdx, r14
0x18000493e  jb      short loc_180004954
0x180004940  mov     r9, r14; SourceSize
0x180004943  mov     rcx, rbx; Destination
0x180004946  call    memcpy_s
0x18000494b  mov     [rdi+38h], rbx
0x18000494f  add     rbx, r14
0x180004952  jmp     short loc_180004958
0x180004954  mov     [rdi+38h], r13
0x180004958  sub     rsi, rbx
0x18000495b  xor     edx, edx; Val
0x18000495d  mov     r8, rsi; Size
0x180004960  mov     rcx, rbx; void *
0x180004963  call    memset_0
0x180004968  add     rsp, 28h
0x18000496c  pop     r15
0x18000496e  pop     r14
0x180004970  pop     r13
0x180004972  pop     r12
0x180004974  pop     rdi
0x180004975  pop     rsi
0x180004976  pop     rbp
0x180004977  pop     rbx
0x180004978  retn
```
