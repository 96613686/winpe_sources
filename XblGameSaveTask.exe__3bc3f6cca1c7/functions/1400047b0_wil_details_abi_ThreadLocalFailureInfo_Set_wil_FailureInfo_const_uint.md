# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400047b0`
- end: `0x1400049c9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400033f0`

## callees

- `0x140001f36`
- `0x140004448`
- `0x1400047b0`
- `0x140005768`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400048a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400048a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004898`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004898`

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
0x1400047b0  push    rbx
0x1400047b2  push    rbp
0x1400047b3  push    rsi
0x1400047b4  push    rdi
0x1400047b5  push    r12
0x1400047b7  push    r13
0x1400047b9  push    r14
0x1400047bb  push    r15
0x1400047bd  sub     rsp, 28h
0x1400047c1  mov     [rcx+4], r8d
0x1400047c5  xor     r13d, r13d
0x1400047c8  mov     eax, [rdx+8]
0x1400047cb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400047cf  mov     [rcx+8], eax
0x1400047d2  mov     rdi, rcx
0x1400047d5  mov     [rcx+10h], r13
0x1400047d9  mov     r12, rdx
0x1400047dc  movzx   eax, word ptr [rdx+40h]
0x1400047e0  mov     [rcx+18h], ax
0x1400047e4  mov     al, [rdx]
0x1400047e6  mov     [rcx+1Ah], al
0x1400047e9  mov     [rcx+20h], r13
0x1400047ed  mov     rax, [rdx+88h]
0x1400047f4  mov     [rcx+28h], rax
0x1400047f8  mov     rax, [rdx+90h]
0x1400047ff  mov     [rcx+30h], rax
0x140004803  mov     [rcx+38h], r13
0x140004807  mov     rcx, [rdx+38h]
0x14000480b  lea     edx, [rbp+2]
0x14000480e  test    rcx, rcx
0x140004811  jnz     short loc_140004818
0x140004813  mov     r8d, edx
0x140004816  jmp     short loc_140004828
0x140004818  mov     rax, rbp
0x14000481b  inc     rax
0x14000481e  cmp     [rcx+rax], r13b
0x140004822  jnz     short loc_14000481B
0x140004824  lea     r8, [rax+1]; unsigned __int64
0x140004828  mov     rcx, [r12+80h]
0x140004830  test    rcx, rcx
0x140004833  jz      short loc_140004845
0x140004835  mov     rax, rbp
0x140004838  inc     rax
0x14000483b  cmp     [rcx+rax], r13b
0x14000483f  jnz     short loc_140004838
0x140004841  lea     rdx, [rax+1]
0x140004845  mov     rcx, [r12+18h]
0x14000484a  test    rcx, rcx
0x14000484d  jnz     short loc_140004854
0x14000484f  lea     eax, [rcx+2]
0x140004852  jmp     short loc_140004869
0x140004854  mov     rax, rbp
0x140004857  inc     rax
0x14000485a  cmp     [rcx+rax*2], r13w
0x14000485f  jnz     short loc_140004857
0x140004861  lea     rax, ds:2[rax*2]
0x140004869  lea     r14, [rdx+rax]
0x14000486d  add     r14, r8
0x140004870  lea     rsi, [rdi+48h]
0x140004874  cmp     [rdi+40h], r13
0x140004878  jz      short loc_14000487F
0x14000487a  cmp     [rsi], r14
0x14000487d  jnb     short loc_1400048B3
0x14000487f  mov     rdx, r14; dwBytes
0x140004882  mov     ecx, 8; dwFlags
0x140004887  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000488c  mov     r15, rax
0x14000488f  test    rax, rax
0x140004892  jz      short loc_1400048B3
0x140004894  mov     rbx, [rdi+40h]
0x140004898  call    cs:__imp_GetProcessHeap
0x14000489e  mov     r8, rbx; lpMem
0x1400048a1  xor     edx, edx; dwFlags
0x1400048a3  mov     rcx, rax; hHeap
0x1400048a6  call    cs:__imp_HeapFree
0x1400048ac  mov     [rdi+40h], r15
0x1400048b0  mov     [rsi], r14
0x1400048b3  mov     rbx, [rdi+40h]
0x1400048b7  test    rbx, rbx
0x1400048ba  jz      loc_1400049B8
0x1400048c0  mov     rdx, [rsi]; DestinationSize
0x1400048c3  lea     rsi, [rdx+rbx]
0x1400048c7  cmp     rbx, rsi
0x1400048ca  jz      short loc_14000490A
0x1400048cc  mov     r8, [r12+38h]; Source
0x1400048d1  test    r8, r8
0x1400048d4  jz      short loc_14000490A
0x1400048d6  cmp     [r8], r13b
0x1400048d9  jz      short loc_14000490A
0x1400048db  mov     rax, rbp
0x1400048de  inc     rax
0x1400048e1  cmp     [r8+rax], r13b
0x1400048e5  jnz     short loc_1400048DE
0x1400048e7  lea     r14, [rax+1]
0x1400048eb  cmp     rdx, r14
0x1400048ee  jnb     short loc_1400048F6
0x1400048f0  mov     [rdi+10h], r13
0x1400048f4  jmp     short loc_140004913
0x1400048f6  mov     r9, r14; SourceSize
0x1400048f9  mov     rcx, rbx; Destination
0x1400048fc  call    memcpy_s
0x140004901  mov     [rdi+10h], rbx
0x140004905  add     rbx, r14
0x140004908  jmp     short loc_14000490E
0x14000490a  mov     [rdi+10h], r13
0x14000490e  cmp     rbx, rsi
0x140004911  jz      short loc_14000495A
0x140004913  mov     r8, [r12+80h]; Source
0x14000491b  test    r8, r8
0x14000491e  jz      short loc_14000495A
0x140004920  cmp     [r8], r13b
0x140004923  jz      short loc_14000495A
0x140004925  mov     rax, rbp
0x140004928  inc     rax
0x14000492b  cmp     [r8+rax], r13b
0x14000492f  jnz     short loc_140004928
0x140004931  mov     rdx, rsi
0x140004934  lea     r14, [rax+1]
0x140004938  sub     rdx, rbx; DestinationSize
0x14000493b  cmp     rdx, r14
0x14000493e  jnb     short loc_140004946
0x140004940  mov     [rdi+20h], r13
0x140004944  jmp     short loc_140004963
0x140004946  mov     r9, r14; SourceSize
0x140004949  mov     rcx, rbx; Destination
0x14000494c  call    memcpy_s
0x140004951  mov     [rdi+20h], rbx
0x140004955  add     rbx, r14
0x140004958  jmp     short loc_14000495E
0x14000495a  mov     [rdi+20h], r13
0x14000495e  cmp     rbx, rsi
0x140004961  jz      short loc_1400049A4
0x140004963  mov     r8, [r12+18h]; Source
0x140004968  test    r8, r8
0x14000496b  jz      short loc_1400049A4
0x14000496d  cmp     [r8], r13w
0x140004971  jz      short loc_1400049A4
0x140004973  inc     rbp
0x140004976  cmp     [r8+rbp*2], r13w
0x14000497b  jnz     short loc_140004973
0x14000497d  mov     rdx, rsi
0x140004980  lea     r14, ds:2[rbp*2]
0x140004988  sub     rdx, rbx; DestinationSize
0x14000498b  cmp     rdx, r14
0x14000498e  jb      short loc_1400049A4
0x140004990  mov     r9, r14; SourceSize
0x140004993  mov     rcx, rbx; Destination
0x140004996  call    memcpy_s
0x14000499b  mov     [rdi+38h], rbx
0x14000499f  add     rbx, r14
0x1400049a2  jmp     short loc_1400049A8
0x1400049a4  mov     [rdi+38h], r13
0x1400049a8  sub     rsi, rbx
0x1400049ab  xor     edx, edx; Val
0x1400049ad  mov     r8, rsi; Size
0x1400049b0  mov     rcx, rbx; void *
0x1400049b3  call    memset_0
0x1400049b8  add     rsp, 28h
0x1400049bc  pop     r15
0x1400049be  pop     r14
0x1400049c0  pop     r13
0x1400049c2  pop     r12
0x1400049c4  pop     rdi
0x1400049c5  pop     rsi
0x1400049c6  pop     rbp
0x1400049c7  pop     rbx
0x1400049c8  retn
```
