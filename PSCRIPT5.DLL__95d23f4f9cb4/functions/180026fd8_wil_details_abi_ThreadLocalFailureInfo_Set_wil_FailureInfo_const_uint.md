# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180026fd8`
- end: `0x1800271f1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800248d0`

## callees

- `0x1800028d8`
- `0x180025b78`
- `0x180026fd8`
- `0x18002874c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800270c0`
- `KERNEL32!GetProcessHeap` at `0x1800270c0`
- `KERNEL32!HeapFree` at `0x1800270ce`
- `KERNEL32!HeapFree` at `0x1800270ce`

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
                memcpy_s_0(v20, v22 - v20, v29, 2 * v3 + 2);
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
          memcpy_s_0(v20, v22 - v20, v26, v27 + 1);
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
      memcpy_s_0(*((void *const *)this + 8), v21, v23, v24 + 1);
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
0x180026fd8  push    rbx
0x180026fda  push    rbp
0x180026fdb  push    rsi
0x180026fdc  push    rdi
0x180026fdd  push    r12
0x180026fdf  push    r13
0x180026fe1  push    r14
0x180026fe3  push    r15
0x180026fe5  sub     rsp, 28h
0x180026fe9  mov     [rcx+4], r8d
0x180026fed  xor     r13d, r13d
0x180026ff0  mov     eax, [rdx+8]
0x180026ff3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180026ff7  mov     [rcx+8], eax
0x180026ffa  mov     rdi, rcx
0x180026ffd  mov     [rcx+10h], r13
0x180027001  mov     r12, rdx
0x180027004  movzx   eax, word ptr [rdx+40h]
0x180027008  mov     [rcx+18h], ax
0x18002700c  mov     al, [rdx]
0x18002700e  mov     [rcx+1Ah], al
0x180027011  mov     [rcx+20h], r13
0x180027015  mov     rax, [rdx+88h]
0x18002701c  mov     [rcx+28h], rax
0x180027020  mov     rax, [rdx+90h]
0x180027027  mov     [rcx+30h], rax
0x18002702b  mov     [rcx+38h], r13
0x18002702f  mov     rcx, [rdx+38h]
0x180027033  lea     edx, [rbp+2]
0x180027036  test    rcx, rcx
0x180027039  jnz     short loc_180027040
0x18002703b  mov     r8d, edx
0x18002703e  jmp     short loc_180027050
0x180027040  mov     rax, rbp
0x180027043  inc     rax
0x180027046  cmp     [rcx+rax], r13b
0x18002704a  jnz     short loc_180027043
0x18002704c  lea     r8, [rax+1]; unsigned __int64
0x180027050  mov     rcx, [r12+80h]
0x180027058  test    rcx, rcx
0x18002705b  jz      short loc_18002706D
0x18002705d  mov     rax, rbp
0x180027060  inc     rax
0x180027063  cmp     [rcx+rax], r13b
0x180027067  jnz     short loc_180027060
0x180027069  lea     rdx, [rax+1]
0x18002706d  mov     rcx, [r12+18h]
0x180027072  test    rcx, rcx
0x180027075  jnz     short loc_18002707C
0x180027077  lea     eax, [rcx+2]
0x18002707a  jmp     short loc_180027091
0x18002707c  mov     rax, rbp
0x18002707f  inc     rax
0x180027082  cmp     [rcx+rax*2], r13w
0x180027087  jnz     short loc_18002707F
0x180027089  lea     rax, ds:2[rax*2]
0x180027091  lea     r14, [rdx+rax]
0x180027095  add     r14, r8
0x180027098  lea     rsi, [rdi+48h]
0x18002709c  cmp     [rdi+40h], r13
0x1800270a0  jz      short loc_1800270A7
0x1800270a2  cmp     [rsi], r14
0x1800270a5  jnb     short loc_1800270DB
0x1800270a7  mov     rdx, r14; dwBytes
0x1800270aa  mov     ecx, 8; dwFlags
0x1800270af  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800270b4  mov     r15, rax
0x1800270b7  test    rax, rax
0x1800270ba  jz      short loc_1800270DB
0x1800270bc  mov     rbx, [rdi+40h]
0x1800270c0  call    cs:__imp_GetProcessHeap
0x1800270c6  mov     r8, rbx; lpMem
0x1800270c9  xor     edx, edx; dwFlags
0x1800270cb  mov     rcx, rax; hHeap
0x1800270ce  call    cs:__imp_HeapFree
0x1800270d4  mov     [rdi+40h], r15
0x1800270d8  mov     [rsi], r14
0x1800270db  mov     rbx, [rdi+40h]
0x1800270df  test    rbx, rbx
0x1800270e2  jz      loc_1800271E0
0x1800270e8  mov     rdx, [rsi]; DestinationSize
0x1800270eb  lea     rsi, [rdx+rbx]
0x1800270ef  cmp     rbx, rsi
0x1800270f2  jz      short loc_180027132
0x1800270f4  mov     r8, [r12+38h]; Source
0x1800270f9  test    r8, r8
0x1800270fc  jz      short loc_180027132
0x1800270fe  cmp     [r8], r13b
0x180027101  jz      short loc_180027132
0x180027103  mov     rax, rbp
0x180027106  inc     rax
0x180027109  cmp     [r8+rax], r13b
0x18002710d  jnz     short loc_180027106
0x18002710f  lea     r14, [rax+1]
0x180027113  cmp     rdx, r14
0x180027116  jnb     short loc_18002711E
0x180027118  mov     [rdi+10h], r13
0x18002711c  jmp     short loc_18002713B
0x18002711e  mov     r9, r14; SourceSize
0x180027121  mov     rcx, rbx; Destination
0x180027124  call    memcpy_s_0
0x180027129  mov     [rdi+10h], rbx
0x18002712d  add     rbx, r14
0x180027130  jmp     short loc_180027136
0x180027132  mov     [rdi+10h], r13
0x180027136  cmp     rbx, rsi
0x180027139  jz      short loc_180027182
0x18002713b  mov     r8, [r12+80h]; Source
0x180027143  test    r8, r8
0x180027146  jz      short loc_180027182
0x180027148  cmp     [r8], r13b
0x18002714b  jz      short loc_180027182
0x18002714d  mov     rax, rbp
0x180027150  inc     rax
0x180027153  cmp     [r8+rax], r13b
0x180027157  jnz     short loc_180027150
0x180027159  mov     rdx, rsi
0x18002715c  lea     r14, [rax+1]
0x180027160  sub     rdx, rbx; DestinationSize
0x180027163  cmp     rdx, r14
0x180027166  jnb     short loc_18002716E
0x180027168  mov     [rdi+20h], r13
0x18002716c  jmp     short loc_18002718B
0x18002716e  mov     r9, r14; SourceSize
0x180027171  mov     rcx, rbx; Destination
0x180027174  call    memcpy_s_0
0x180027179  mov     [rdi+20h], rbx
0x18002717d  add     rbx, r14
0x180027180  jmp     short loc_180027186
0x180027182  mov     [rdi+20h], r13
0x180027186  cmp     rbx, rsi
0x180027189  jz      short loc_1800271CC
0x18002718b  mov     r8, [r12+18h]; Source
0x180027190  test    r8, r8
0x180027193  jz      short loc_1800271CC
0x180027195  cmp     [r8], r13w
0x180027199  jz      short loc_1800271CC
0x18002719b  inc     rbp
0x18002719e  cmp     [r8+rbp*2], r13w
0x1800271a3  jnz     short loc_18002719B
0x1800271a5  mov     rdx, rsi
0x1800271a8  lea     r14, ds:2[rbp*2]
0x1800271b0  sub     rdx, rbx; DestinationSize
0x1800271b3  cmp     rdx, r14
0x1800271b6  jb      short loc_1800271CC
0x1800271b8  mov     r9, r14; SourceSize
0x1800271bb  mov     rcx, rbx; Destination
0x1800271be  call    memcpy_s_0
0x1800271c3  mov     [rdi+38h], rbx
0x1800271c7  add     rbx, r14
0x1800271ca  jmp     short loc_1800271D0
0x1800271cc  mov     [rdi+38h], r13
0x1800271d0  sub     rsi, rbx
0x1800271d3  xor     edx, edx; Val
0x1800271d5  mov     r8, rsi; Size
0x1800271d8  mov     rcx, rbx; void *
0x1800271db  call    memset_0
0x1800271e0  add     rsp, 28h
0x1800271e4  pop     r15
0x1800271e6  pop     r14
0x1800271e8  pop     r13
0x1800271ea  pop     r12
0x1800271ec  pop     rdi
0x1800271ed  pop     rsi
0x1800271ee  pop     rbp
0x1800271ef  pop     rbx
0x1800271f0  retn
```
