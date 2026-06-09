# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800060c8`
- end: `0x180006359`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004600`

## callees

- `0x18000265c`
- `0x180003cfc`
- `0x180005894`
- `0x1800060c8`
- `0x180006c7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000627a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000627a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000628e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000628e`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s_0(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x1800060c8  push    rbx
0x1800060ca  push    rbp
0x1800060cb  push    rsi
0x1800060cc  push    rdi
0x1800060cd  push    r12
0x1800060cf  push    r13
0x1800060d1  push    r14
0x1800060d3  push    r15
0x1800060d5  sub     rsp, 28h
0x1800060d9  mov     esi, [rcx+10h]
0x1800060dc  xor     r12d, r12d
0x1800060df  mov     r15, rdx
0x1800060e2  mov     rbx, rcx
0x1800060e5  mov     ebp, 50h ; 'P'
0x1800060ea  cmp     [rcx+18h], r12
0x1800060ee  jnz     short loc_180006125
0x1800060f0  test    esi, esi
0x1800060f2  jz      short loc_180006125
0x1800060f4  mov     edx, 190h; dwBytes
0x1800060f9  lea     ecx, [rbp-48h]; dwFlags
0x1800060fc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006101  mov     [rbx+18h], rax
0x180006105  test    rax, rax
0x180006108  jz      short loc_180006125
0x18000610a  mov     dword ptr [rbx+20h], 5
0x180006111  lea     rcx, [rax+190h]
0x180006118  jmp     short loc_180006120
0x18000611a  mov     [rax], bp
0x18000611d  add     rax, rbp
0x180006120  cmp     rax, rcx
0x180006123  jnz     short loc_18000611A
0x180006125  mov     rdi, [rbx+18h]
0x180006129  test    rdi, rdi
0x18000612c  jz      loc_180006347
0x180006132  test    esi, esi
0x180006134  jz      short loc_18000616C
0x180006136  movzx   eax, word ptr [rbx+20h]
0x18000613a  mov     rcx, rdi
0x18000613d  lea     rdx, [rax+rax*4]
0x180006141  shl     rdx, 4
0x180006145  add     rdx, rdi
0x180006148  cmp     rdi, rdx
0x18000614b  jz      short loc_18000616C
0x18000614d  mov     r8d, [rbx+10h]
0x180006151  cmp     [rcx+4], r8d
0x180006155  jbe     short loc_180006164
0x180006157  mov     eax, [r15+8]
0x18000615b  cmp     [rcx+8], eax
0x18000615e  jz      loc_180006347
0x180006164  add     rcx, rbp
0x180006167  cmp     rcx, rdx
0x18000616a  jnz     short loc_180006151
0x18000616c  movzx   eax, word ptr [rbx+22h]
0x180006170  mov     r8d, 1
0x180006176  movzx   ecx, word ptr [rbx+20h]
0x18000617a  add     eax, r8d
0x18000617d  xor     edx, edx
0x18000617f  div     ecx
0x180006181  mov     ecx, r8d
0x180006184  movzx   eax, dx
0x180006187  mov     [rbx+22h], dx
0x18000618b  lea     rsi, [rax+rax*4]
0x18000618f  mov     rax, [rbx+8]
0x180006193  shl     rsi, 4
0x180006197  lock xadd [rax], ecx
0x18000619b  add     ecx, r8d
0x18000619e  lea     r13, [rsi+rdi]
0x1800061a2  mov     [rsi+rdi+4], ecx
0x1800061a6  lea     rbx, [rdi+20h]
0x1800061aa  mov     eax, [r15+8]
0x1800061ae  add     rbx, rsi
0x1800061b1  mov     [rsi+rdi+8], eax
0x1800061b5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800061b9  mov     [r13+10h], r12
0x1800061bd  movzx   eax, word ptr [r15+40h]
0x1800061c2  mov     [rsi+rdi+18h], ax
0x1800061c7  mov     al, [r15]
0x1800061ca  mov     [rsi+rdi+1Ah], al
0x1800061ce  mov     [rbx], r12
0x1800061d1  mov     rax, [r15+88h]
0x1800061d8  mov     [rsi+rdi+28h], rax
0x1800061dd  mov     rax, [r15+90h]
0x1800061e4  mov     [rsi+rdi+30h], rax
0x1800061e9  mov     [rsi+rdi+38h], r12
0x1800061ee  mov     rcx, [r15+38h]
0x1800061f2  test    rcx, rcx
0x1800061f5  jnz     short loc_1800061FC
0x1800061f7  mov     edx, r8d
0x1800061fa  jmp     short loc_18000620C
0x1800061fc  mov     rax, r14
0x1800061ff  inc     rax
0x180006202  cmp     [rcx+rax], r12b
0x180006206  jnz     short loc_1800061FF
0x180006208  lea     rdx, [rax+1]
0x18000620c  mov     rcx, [r15+80h]
0x180006213  test    rcx, rcx
0x180006216  jz      short loc_180006228
0x180006218  mov     rax, r14
0x18000621b  inc     rax
0x18000621e  cmp     [rcx+rax], r12b
0x180006222  jnz     short loc_18000621B
0x180006224  lea     r8, [rax+1]; unsigned __int64
0x180006228  mov     rcx, [r15+18h]
0x18000622c  test    rcx, rcx
0x18000622f  jnz     short loc_180006236
0x180006231  lea     eax, [rcx+2]
0x180006234  jmp     short loc_18000624B
0x180006236  mov     rax, r14
0x180006239  inc     rax
0x18000623c  cmp     [rcx+rax*2], r12w
0x180006241  jnz     short loc_180006239
0x180006243  lea     rax, ds:2[rax*2]
0x18000624b  lea     rbp, [r8+rax]
0x18000624f  add     rbp, rdx
0x180006252  cmp     [rsi+rdi+40h], r12
0x180006257  jz      short loc_180006260
0x180006259  cmp     [rsi+rdi+48h], rbp
0x18000625e  jnb     short loc_1800062AE
0x180006260  mov     rdx, rbp; dwBytes
0x180006263  mov     ecx, 8; dwFlags
0x180006268  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000626d  mov     r12, rax
0x180006270  test    rax, rax
0x180006273  jz      short loc_1800062AB
0x180006275  mov     rbx, [rsi+rdi+40h]
0x18000627a  call    cs:__imp_GetProcessHeap
0x180006281  nop     dword ptr [rax+rax+00h]
0x180006286  mov     r8, rbx; lpMem
0x180006289  xor     edx, edx; dwFlags
0x18000628b  mov     rcx, rax; hHeap
0x18000628e  call    cs:__imp_HeapFree
0x180006295  nop     dword ptr [rax+rax+00h]
0x18000629a  lea     rbx, [rdi+20h]
0x18000629e  mov     [rsi+rdi+40h], r12
0x1800062a3  add     rbx, rsi
0x1800062a6  mov     [rsi+rdi+48h], rbp
0x1800062ab  xor     r12d, r12d
0x1800062ae  mov     rcx, [rsi+rdi+40h]
0x1800062b3  test    rcx, rcx
0x1800062b6  jz      loc_180006347
0x1800062bc  mov     rbp, [rsi+rdi+48h]
0x1800062c1  lea     r9, [r13+10h]
0x1800062c5  mov     r8, [r15+38h]
0x1800062c9  add     rbp, rcx
0x1800062cc  mov     rdx, rbp
0x1800062cf  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800062d4  mov     r8, [r15+80h]
0x1800062db  mov     r9, rbx
0x1800062de  mov     rdx, rbp
0x1800062e1  mov     rcx, rax
0x1800062e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800062e9  mov     rbx, rax
0x1800062ec  cmp     rax, rbp
0x1800062ef  jz      short loc_180006332
0x1800062f1  mov     r8, [r15+18h]; Source
0x1800062f5  test    r8, r8
0x1800062f8  jz      short loc_180006332
0x1800062fa  cmp     [r8], r12w
0x1800062fe  jz      short loc_180006332
0x180006300  inc     r14
0x180006303  cmp     [r8+r14*2], r12w
0x180006308  jnz     short loc_180006300
0x18000630a  mov     rdx, rbp
0x18000630d  lea     r14, ds:2[r14*2]
0x180006315  sub     rdx, rbx; DestinationSize
0x180006318  cmp     rdx, r14
0x18000631b  jb      short loc_180006332
0x18000631d  mov     r9, r14; SourceSize
0x180006320  mov     rcx, rbx; Destination
0x180006323  call    memcpy_s_0
0x180006328  mov     [rsi+rdi+38h], rbx
0x18000632d  add     rbx, r14
0x180006330  jmp     short loc_180006337
0x180006332  mov     [rsi+rdi+38h], r12
0x180006337  sub     rbp, rbx
0x18000633a  xor     edx, edx; Val
0x18000633c  mov     r8, rbp; Size
0x18000633f  mov     rcx, rbx; void *
0x180006342  call    memset_0
0x180006347  add     rsp, 28h
0x18000634b  pop     r15
0x18000634d  pop     r14
0x18000634f  pop     r13
0x180006351  pop     r12
0x180006353  pop     rdi
0x180006354  pop     rsi
0x180006355  pop     rbp
0x180006356  pop     rbx
0x180006357  retn
```
