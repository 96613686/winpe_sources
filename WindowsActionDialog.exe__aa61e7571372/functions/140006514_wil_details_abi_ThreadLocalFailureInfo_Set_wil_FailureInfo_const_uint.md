# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006514`
- end: `0x14000672d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004450`

## callees

- `0x140001f5c`
- `0x140005f30`
- `0x140006514`
- `0x1400079e8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000660a`
- `KERNEL32!HeapFree` at `0x14000660a`
- `KERNEL32!GetProcessHeap` at `0x1400065fc`
- `KERNEL32!GetProcessHeap` at `0x1400065fc`

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
0x140006514  push    rbx
0x140006516  push    rbp
0x140006517  push    rsi
0x140006518  push    rdi
0x140006519  push    r12
0x14000651b  push    r13
0x14000651d  push    r14
0x14000651f  push    r15
0x140006521  sub     rsp, 28h
0x140006525  mov     [rcx+4], r8d
0x140006529  xor     r13d, r13d
0x14000652c  mov     eax, [rdx+8]
0x14000652f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140006533  mov     [rcx+8], eax
0x140006536  mov     rdi, rcx
0x140006539  mov     [rcx+10h], r13
0x14000653d  mov     r12, rdx
0x140006540  movzx   eax, word ptr [rdx+40h]
0x140006544  mov     [rcx+18h], ax
0x140006548  mov     al, [rdx]
0x14000654a  mov     [rcx+1Ah], al
0x14000654d  mov     [rcx+20h], r13
0x140006551  mov     rax, [rdx+88h]
0x140006558  mov     [rcx+28h], rax
0x14000655c  mov     rax, [rdx+90h]
0x140006563  mov     [rcx+30h], rax
0x140006567  mov     [rcx+38h], r13
0x14000656b  mov     rcx, [rdx+38h]
0x14000656f  lea     edx, [rbp+2]
0x140006572  test    rcx, rcx
0x140006575  jnz     short loc_14000657C
0x140006577  mov     r8d, edx
0x14000657a  jmp     short loc_14000658C
0x14000657c  mov     rax, rbp
0x14000657f  inc     rax
0x140006582  cmp     [rcx+rax], r13b
0x140006586  jnz     short loc_14000657F
0x140006588  lea     r8, [rax+1]; unsigned __int64
0x14000658c  mov     rcx, [r12+80h]
0x140006594  test    rcx, rcx
0x140006597  jz      short loc_1400065A9
0x140006599  mov     rax, rbp
0x14000659c  inc     rax
0x14000659f  cmp     [rcx+rax], r13b
0x1400065a3  jnz     short loc_14000659C
0x1400065a5  lea     rdx, [rax+1]
0x1400065a9  mov     rcx, [r12+18h]
0x1400065ae  test    rcx, rcx
0x1400065b1  jnz     short loc_1400065B8
0x1400065b3  lea     eax, [rcx+2]
0x1400065b6  jmp     short loc_1400065CD
0x1400065b8  mov     rax, rbp
0x1400065bb  inc     rax
0x1400065be  cmp     [rcx+rax*2], r13w
0x1400065c3  jnz     short loc_1400065BB
0x1400065c5  lea     rax, ds:2[rax*2]
0x1400065cd  lea     r14, [rdx+rax]
0x1400065d1  add     r14, r8
0x1400065d4  lea     rsi, [rdi+48h]
0x1400065d8  cmp     [rdi+40h], r13
0x1400065dc  jz      short loc_1400065E3
0x1400065de  cmp     [rsi], r14
0x1400065e1  jnb     short loc_140006617
0x1400065e3  mov     rdx, r14; dwBytes
0x1400065e6  mov     ecx, 8; dwFlags
0x1400065eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400065f0  mov     r15, rax
0x1400065f3  test    rax, rax
0x1400065f6  jz      short loc_140006617
0x1400065f8  mov     rbx, [rdi+40h]
0x1400065fc  call    cs:__imp_GetProcessHeap
0x140006602  mov     r8, rbx; lpMem
0x140006605  xor     edx, edx; dwFlags
0x140006607  mov     rcx, rax; hHeap
0x14000660a  call    cs:__imp_HeapFree
0x140006610  mov     [rdi+40h], r15
0x140006614  mov     [rsi], r14
0x140006617  mov     rbx, [rdi+40h]
0x14000661b  test    rbx, rbx
0x14000661e  jz      loc_14000671C
0x140006624  mov     rdx, [rsi]; DestinationSize
0x140006627  lea     rsi, [rdx+rbx]
0x14000662b  cmp     rbx, rsi
0x14000662e  jz      short loc_14000666E
0x140006630  mov     r8, [r12+38h]; Source
0x140006635  test    r8, r8
0x140006638  jz      short loc_14000666E
0x14000663a  cmp     [r8], r13b
0x14000663d  jz      short loc_14000666E
0x14000663f  mov     rax, rbp
0x140006642  inc     rax
0x140006645  cmp     [r8+rax], r13b
0x140006649  jnz     short loc_140006642
0x14000664b  lea     r14, [rax+1]
0x14000664f  cmp     rdx, r14
0x140006652  jnb     short loc_14000665A
0x140006654  mov     [rdi+10h], r13
0x140006658  jmp     short loc_140006677
0x14000665a  mov     r9, r14; SourceSize
0x14000665d  mov     rcx, rbx; Destination
0x140006660  call    memcpy_s
0x140006665  mov     [rdi+10h], rbx
0x140006669  add     rbx, r14
0x14000666c  jmp     short loc_140006672
0x14000666e  mov     [rdi+10h], r13
0x140006672  cmp     rbx, rsi
0x140006675  jz      short loc_1400066BE
0x140006677  mov     r8, [r12+80h]; Source
0x14000667f  test    r8, r8
0x140006682  jz      short loc_1400066BE
0x140006684  cmp     [r8], r13b
0x140006687  jz      short loc_1400066BE
0x140006689  mov     rax, rbp
0x14000668c  inc     rax
0x14000668f  cmp     [r8+rax], r13b
0x140006693  jnz     short loc_14000668C
0x140006695  mov     rdx, rsi
0x140006698  lea     r14, [rax+1]
0x14000669c  sub     rdx, rbx; DestinationSize
0x14000669f  cmp     rdx, r14
0x1400066a2  jnb     short loc_1400066AA
0x1400066a4  mov     [rdi+20h], r13
0x1400066a8  jmp     short loc_1400066C7
0x1400066aa  mov     r9, r14; SourceSize
0x1400066ad  mov     rcx, rbx; Destination
0x1400066b0  call    memcpy_s
0x1400066b5  mov     [rdi+20h], rbx
0x1400066b9  add     rbx, r14
0x1400066bc  jmp     short loc_1400066C2
0x1400066be  mov     [rdi+20h], r13
0x1400066c2  cmp     rbx, rsi
0x1400066c5  jz      short loc_140006708
0x1400066c7  mov     r8, [r12+18h]; Source
0x1400066cc  test    r8, r8
0x1400066cf  jz      short loc_140006708
0x1400066d1  cmp     [r8], r13w
0x1400066d5  jz      short loc_140006708
0x1400066d7  inc     rbp
0x1400066da  cmp     [r8+rbp*2], r13w
0x1400066df  jnz     short loc_1400066D7
0x1400066e1  mov     rdx, rsi
0x1400066e4  lea     r14, ds:2[rbp*2]
0x1400066ec  sub     rdx, rbx; DestinationSize
0x1400066ef  cmp     rdx, r14
0x1400066f2  jb      short loc_140006708
0x1400066f4  mov     r9, r14; SourceSize
0x1400066f7  mov     rcx, rbx; Destination
0x1400066fa  call    memcpy_s
0x1400066ff  mov     [rdi+38h], rbx
0x140006703  add     rbx, r14
0x140006706  jmp     short loc_14000670C
0x140006708  mov     [rdi+38h], r13
0x14000670c  sub     rsi, rbx
0x14000670f  xor     edx, edx; Val
0x140006711  mov     r8, rsi; Size
0x140006714  mov     rcx, rbx; void *
0x140006717  call    memset_0
0x14000671c  add     rsp, 28h
0x140006720  pop     r15
0x140006722  pop     r14
0x140006724  pop     r13
0x140006726  pop     r12
0x140006728  pop     rdi
0x140006729  pop     rsi
0x14000672a  pop     rbp
0x14000672b  pop     rbx
0x14000672c  retn
```
