# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140003f20`
- end: `0x14000413c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002b90`

## callees

- `0x14000187f`
- `0x140003bd8`
- `0x140003f20`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004016`
- `KERNEL32!HeapFree` at `0x140004016`
- `KERNEL32!GetProcessHeap` at `0x140004008`
- `KERNEL32!GetProcessHeap` at `0x140004008`
- `msvcrt!memcpy_s` at `0x14000406c`
- `msvcrt!memcpy_s` at `0x1400040bd`
- `msvcrt!memcpy_s` at `0x140004108`
- `msvcrt!memcpy_s` at `0x14000406c`
- `msvcrt!memcpy_s` at `0x1400040bd`
- `msvcrt!memcpy_s` at `0x140004108`

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
0x140003f20  push    rbx
0x140003f22  push    rbp
0x140003f23  push    rsi
0x140003f24  push    rdi
0x140003f25  push    r12
0x140003f27  push    r13
0x140003f29  push    r14
0x140003f2b  push    r15
0x140003f2d  sub     rsp, 28h
0x140003f31  mov     [rcx+4], r8d
0x140003f35  xor     r13d, r13d
0x140003f38  mov     eax, [rdx+8]
0x140003f3b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140003f3f  mov     [rcx+8], eax
0x140003f42  mov     rdi, rcx
0x140003f45  mov     [rcx+10h], r13
0x140003f49  mov     r12, rdx
0x140003f4c  movzx   eax, word ptr [rdx+40h]
0x140003f50  mov     [rcx+18h], ax
0x140003f54  mov     al, [rdx]
0x140003f56  mov     [rcx+1Ah], al
0x140003f59  mov     [rcx+20h], r13
0x140003f5d  mov     rax, [rdx+88h]
0x140003f64  mov     [rcx+28h], rax
0x140003f68  mov     rax, [rdx+90h]
0x140003f6f  mov     [rcx+30h], rax
0x140003f73  mov     [rcx+38h], r13
0x140003f77  mov     rcx, [rdx+38h]
0x140003f7b  lea     edx, [rbp+2]
0x140003f7e  test    rcx, rcx
0x140003f81  jnz     short loc_140003F88
0x140003f83  mov     r8d, edx
0x140003f86  jmp     short loc_140003F98
0x140003f88  mov     rax, rbp
0x140003f8b  inc     rax
0x140003f8e  cmp     [rcx+rax], r13b
0x140003f92  jnz     short loc_140003F8B
0x140003f94  lea     r8, [rax+1]; unsigned __int64
0x140003f98  mov     rcx, [r12+80h]
0x140003fa0  test    rcx, rcx
0x140003fa3  jz      short loc_140003FB5
0x140003fa5  mov     rax, rbp
0x140003fa8  inc     rax
0x140003fab  cmp     [rcx+rax], r13b
0x140003faf  jnz     short loc_140003FA8
0x140003fb1  lea     rdx, [rax+1]
0x140003fb5  mov     rcx, [r12+18h]
0x140003fba  test    rcx, rcx
0x140003fbd  jnz     short loc_140003FC4
0x140003fbf  lea     eax, [rcx+2]
0x140003fc2  jmp     short loc_140003FD9
0x140003fc4  mov     rax, rbp
0x140003fc7  inc     rax
0x140003fca  cmp     [rcx+rax*2], r13w
0x140003fcf  jnz     short loc_140003FC7
0x140003fd1  lea     rax, ds:2[rax*2]
0x140003fd9  lea     r14, [rdx+rax]
0x140003fdd  add     r14, r8
0x140003fe0  lea     rsi, [rdi+48h]
0x140003fe4  cmp     [rdi+40h], r13
0x140003fe8  jz      short loc_140003FEF
0x140003fea  cmp     [rsi], r14
0x140003fed  jnb     short loc_140004023
0x140003fef  mov     rdx, r14; dwBytes
0x140003ff2  mov     ecx, 8; dwFlags
0x140003ff7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003ffc  mov     r15, rax
0x140003fff  test    rax, rax
0x140004002  jz      short loc_140004023
0x140004004  mov     rbx, [rdi+40h]
0x140004008  call    cs:__imp_GetProcessHeap
0x14000400e  mov     r8, rbx; lpMem
0x140004011  xor     edx, edx; dwFlags
0x140004013  mov     rcx, rax; hHeap
0x140004016  call    cs:__imp_HeapFree
0x14000401c  mov     [rdi+40h], r15
0x140004020  mov     [rsi], r14
0x140004023  mov     rbx, [rdi+40h]
0x140004027  test    rbx, rbx
0x14000402a  jz      loc_14000412B
0x140004030  mov     rdx, [rsi]; DestinationSize
0x140004033  lea     rsi, [rdx+rbx]
0x140004037  cmp     rbx, rsi
0x14000403a  jz      short loc_14000407B
0x14000403c  mov     r8, [r12+38h]; Source
0x140004041  test    r8, r8
0x140004044  jz      short loc_14000407B
0x140004046  cmp     [r8], r13b
0x140004049  jz      short loc_14000407B
0x14000404b  mov     rax, rbp
0x14000404e  inc     rax
0x140004051  cmp     [r8+rax], r13b
0x140004055  jnz     short loc_14000404E
0x140004057  lea     r14, [rax+1]
0x14000405b  cmp     rdx, r14
0x14000405e  jnb     short loc_140004066
0x140004060  mov     [rdi+10h], r13
0x140004064  jmp     short loc_140004084
0x140004066  mov     r9, r14; SourceSize
0x140004069  mov     rcx, rbx; Destination
0x14000406c  call    cs:__imp_memcpy_s
0x140004072  mov     [rdi+10h], rbx
0x140004076  add     rbx, r14
0x140004079  jmp     short loc_14000407F
0x14000407b  mov     [rdi+10h], r13
0x14000407f  cmp     rbx, rsi
0x140004082  jz      short loc_1400040CC
0x140004084  mov     r8, [r12+80h]; Source
0x14000408c  test    r8, r8
0x14000408f  jz      short loc_1400040CC
0x140004091  cmp     [r8], r13b
0x140004094  jz      short loc_1400040CC
0x140004096  mov     rax, rbp
0x140004099  inc     rax
0x14000409c  cmp     [r8+rax], r13b
0x1400040a0  jnz     short loc_140004099
0x1400040a2  mov     rdx, rsi
0x1400040a5  lea     r14, [rax+1]
0x1400040a9  sub     rdx, rbx; DestinationSize
0x1400040ac  cmp     rdx, r14
0x1400040af  jnb     short loc_1400040B7
0x1400040b1  mov     [rdi+20h], r13
0x1400040b5  jmp     short loc_1400040D5
0x1400040b7  mov     r9, r14; SourceSize
0x1400040ba  mov     rcx, rbx; Destination
0x1400040bd  call    cs:__imp_memcpy_s
0x1400040c3  mov     [rdi+20h], rbx
0x1400040c7  add     rbx, r14
0x1400040ca  jmp     short loc_1400040D0
0x1400040cc  mov     [rdi+20h], r13
0x1400040d0  cmp     rbx, rsi
0x1400040d3  jz      short loc_140004117
0x1400040d5  mov     r8, [r12+18h]; Source
0x1400040da  test    r8, r8
0x1400040dd  jz      short loc_140004117
0x1400040df  cmp     [r8], r13w
0x1400040e3  jz      short loc_140004117
0x1400040e5  inc     rbp
0x1400040e8  cmp     [r8+rbp*2], r13w
0x1400040ed  jnz     short loc_1400040E5
0x1400040ef  mov     rdx, rsi
0x1400040f2  lea     r14, ds:2[rbp*2]
0x1400040fa  sub     rdx, rbx; DestinationSize
0x1400040fd  cmp     rdx, r14
0x140004100  jb      short loc_140004117
0x140004102  mov     r9, r14; SourceSize
0x140004105  mov     rcx, rbx; Destination
0x140004108  call    cs:__imp_memcpy_s
0x14000410e  mov     [rdi+38h], rbx
0x140004112  add     rbx, r14
0x140004115  jmp     short loc_14000411B
0x140004117  mov     [rdi+38h], r13
0x14000411b  sub     rsi, rbx
0x14000411e  xor     edx, edx; Val
0x140004120  mov     r8, rsi; Size
0x140004123  mov     rcx, rbx; void *
0x140004126  call    memset_0
0x14000412b  add     rsp, 28h
0x14000412f  pop     r15
0x140004131  pop     r14
0x140004133  pop     r13
0x140004135  pop     r12
0x140004137  pop     rdi
0x140004138  pop     rsi
0x140004139  pop     rbp
0x14000413a  pop     rbx
0x14000413b  retn
```
