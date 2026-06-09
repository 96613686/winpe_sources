# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800070f4`
- end: `0x18000730d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b70`

## callees

- `0x180002570`
- `0x180005cd8`
- `0x1800070f4`
- `0x180008bc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ea`

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
0x1800070f4  push    rbx
0x1800070f6  push    rbp
0x1800070f7  push    rsi
0x1800070f8  push    rdi
0x1800070f9  push    r12
0x1800070fb  push    r13
0x1800070fd  push    r14
0x1800070ff  push    r15
0x180007101  sub     rsp, 28h
0x180007105  mov     [rcx+4], r8d
0x180007109  xor     r13d, r13d
0x18000710c  mov     eax, [rdx+8]
0x18000710f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007113  mov     [rcx+8], eax
0x180007116  mov     rdi, rcx
0x180007119  mov     [rcx+10h], r13
0x18000711d  mov     r12, rdx
0x180007120  movzx   eax, word ptr [rdx+40h]
0x180007124  mov     [rcx+18h], ax
0x180007128  mov     al, [rdx]
0x18000712a  mov     [rcx+1Ah], al
0x18000712d  mov     [rcx+20h], r13
0x180007131  mov     rax, [rdx+88h]
0x180007138  mov     [rcx+28h], rax
0x18000713c  mov     rax, [rdx+90h]
0x180007143  mov     [rcx+30h], rax
0x180007147  mov     [rcx+38h], r13
0x18000714b  mov     rcx, [rdx+38h]
0x18000714f  lea     edx, [rbp+2]
0x180007152  test    rcx, rcx
0x180007155  jnz     short loc_18000715C
0x180007157  mov     r8d, edx
0x18000715a  jmp     short loc_18000716C
0x18000715c  mov     rax, rbp
0x18000715f  inc     rax
0x180007162  cmp     [rcx+rax], r13b
0x180007166  jnz     short loc_18000715F
0x180007168  lea     r8, [rax+1]; unsigned __int64
0x18000716c  mov     rcx, [r12+80h]
0x180007174  test    rcx, rcx
0x180007177  jz      short loc_180007189
0x180007179  mov     rax, rbp
0x18000717c  inc     rax
0x18000717f  cmp     [rcx+rax], r13b
0x180007183  jnz     short loc_18000717C
0x180007185  lea     rdx, [rax+1]
0x180007189  mov     rcx, [r12+18h]
0x18000718e  test    rcx, rcx
0x180007191  jnz     short loc_180007198
0x180007193  lea     eax, [rcx+2]
0x180007196  jmp     short loc_1800071AD
0x180007198  mov     rax, rbp
0x18000719b  inc     rax
0x18000719e  cmp     [rcx+rax*2], r13w
0x1800071a3  jnz     short loc_18000719B
0x1800071a5  lea     rax, ds:2[rax*2]
0x1800071ad  lea     r14, [rdx+rax]
0x1800071b1  add     r14, r8
0x1800071b4  lea     rsi, [rdi+48h]
0x1800071b8  cmp     [rdi+40h], r13
0x1800071bc  jz      short loc_1800071C3
0x1800071be  cmp     [rsi], r14
0x1800071c1  jnb     short loc_1800071F7
0x1800071c3  mov     rdx, r14; dwBytes
0x1800071c6  mov     ecx, 8; dwFlags
0x1800071cb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800071d0  mov     r15, rax
0x1800071d3  test    rax, rax
0x1800071d6  jz      short loc_1800071F7
0x1800071d8  mov     rbx, [rdi+40h]
0x1800071dc  call    cs:__imp_GetProcessHeap
0x1800071e2  mov     r8, rbx; lpMem
0x1800071e5  xor     edx, edx; dwFlags
0x1800071e7  mov     rcx, rax; hHeap
0x1800071ea  call    cs:__imp_HeapFree
0x1800071f0  mov     [rdi+40h], r15
0x1800071f4  mov     [rsi], r14
0x1800071f7  mov     rbx, [rdi+40h]
0x1800071fb  test    rbx, rbx
0x1800071fe  jz      loc_1800072FC
0x180007204  mov     rdx, [rsi]; DestinationSize
0x180007207  lea     rsi, [rdx+rbx]
0x18000720b  cmp     rbx, rsi
0x18000720e  jz      short loc_18000724E
0x180007210  mov     r8, [r12+38h]; Source
0x180007215  test    r8, r8
0x180007218  jz      short loc_18000724E
0x18000721a  cmp     [r8], r13b
0x18000721d  jz      short loc_18000724E
0x18000721f  mov     rax, rbp
0x180007222  inc     rax
0x180007225  cmp     [r8+rax], r13b
0x180007229  jnz     short loc_180007222
0x18000722b  lea     r14, [rax+1]
0x18000722f  cmp     rdx, r14
0x180007232  jnb     short loc_18000723A
0x180007234  mov     [rdi+10h], r13
0x180007238  jmp     short loc_180007257
0x18000723a  mov     r9, r14; SourceSize
0x18000723d  mov     rcx, rbx; Destination
0x180007240  call    memcpy_s
0x180007245  mov     [rdi+10h], rbx
0x180007249  add     rbx, r14
0x18000724c  jmp     short loc_180007252
0x18000724e  mov     [rdi+10h], r13
0x180007252  cmp     rbx, rsi
0x180007255  jz      short loc_18000729E
0x180007257  mov     r8, [r12+80h]; Source
0x18000725f  test    r8, r8
0x180007262  jz      short loc_18000729E
0x180007264  cmp     [r8], r13b
0x180007267  jz      short loc_18000729E
0x180007269  mov     rax, rbp
0x18000726c  inc     rax
0x18000726f  cmp     [r8+rax], r13b
0x180007273  jnz     short loc_18000726C
0x180007275  mov     rdx, rsi
0x180007278  lea     r14, [rax+1]
0x18000727c  sub     rdx, rbx; DestinationSize
0x18000727f  cmp     rdx, r14
0x180007282  jnb     short loc_18000728A
0x180007284  mov     [rdi+20h], r13
0x180007288  jmp     short loc_1800072A7
0x18000728a  mov     r9, r14; SourceSize
0x18000728d  mov     rcx, rbx; Destination
0x180007290  call    memcpy_s
0x180007295  mov     [rdi+20h], rbx
0x180007299  add     rbx, r14
0x18000729c  jmp     short loc_1800072A2
0x18000729e  mov     [rdi+20h], r13
0x1800072a2  cmp     rbx, rsi
0x1800072a5  jz      short loc_1800072E8
0x1800072a7  mov     r8, [r12+18h]; Source
0x1800072ac  test    r8, r8
0x1800072af  jz      short loc_1800072E8
0x1800072b1  cmp     [r8], r13w
0x1800072b5  jz      short loc_1800072E8
0x1800072b7  inc     rbp
0x1800072ba  cmp     [r8+rbp*2], r13w
0x1800072bf  jnz     short loc_1800072B7
0x1800072c1  mov     rdx, rsi
0x1800072c4  lea     r14, ds:2[rbp*2]
0x1800072cc  sub     rdx, rbx; DestinationSize
0x1800072cf  cmp     rdx, r14
0x1800072d2  jb      short loc_1800072E8
0x1800072d4  mov     r9, r14; SourceSize
0x1800072d7  mov     rcx, rbx; Destination
0x1800072da  call    memcpy_s
0x1800072df  mov     [rdi+38h], rbx
0x1800072e3  add     rbx, r14
0x1800072e6  jmp     short loc_1800072EC
0x1800072e8  mov     [rdi+38h], r13
0x1800072ec  sub     rsi, rbx
0x1800072ef  xor     edx, edx; Val
0x1800072f1  mov     r8, rsi; Size
0x1800072f4  mov     rcx, rbx; void *
0x1800072f7  call    memset_0
0x1800072fc  add     rsp, 28h
0x180007300  pop     r15
0x180007302  pop     r14
0x180007304  pop     r13
0x180007306  pop     r12
0x180007308  pop     rdi
0x180007309  pop     rsi
0x18000730a  pop     rbp
0x18000730b  pop     rbx
0x18000730c  retn
```
