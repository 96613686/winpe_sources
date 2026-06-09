# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009524`
- end: `0x18000973d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007490`

## callees

- `0x180003d14`
- `0x180008b08`
- `0x180009524`
- `0x18000b408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000961a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000961a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180009524  push    rbx
0x180009526  push    rbp
0x180009527  push    rsi
0x180009528  push    rdi
0x180009529  push    r12
0x18000952b  push    r13
0x18000952d  push    r14
0x18000952f  push    r15
0x180009531  sub     rsp, 28h
0x180009535  mov     [rcx+4], r8d
0x180009539  xor     r13d, r13d
0x18000953c  mov     eax, [rdx+8]
0x18000953f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009543  mov     [rcx+8], eax
0x180009546  mov     rdi, rcx
0x180009549  mov     [rcx+10h], r13
0x18000954d  mov     r12, rdx
0x180009550  movzx   eax, word ptr [rdx+40h]
0x180009554  mov     [rcx+18h], ax
0x180009558  mov     al, [rdx]
0x18000955a  mov     [rcx+1Ah], al
0x18000955d  mov     [rcx+20h], r13
0x180009561  mov     rax, [rdx+88h]
0x180009568  mov     [rcx+28h], rax
0x18000956c  mov     rax, [rdx+90h]
0x180009573  mov     [rcx+30h], rax
0x180009577  mov     [rcx+38h], r13
0x18000957b  mov     rcx, [rdx+38h]
0x18000957f  lea     edx, [rbp+2]
0x180009582  test    rcx, rcx
0x180009585  jnz     short loc_18000958C
0x180009587  mov     r8d, edx
0x18000958a  jmp     short loc_18000959C
0x18000958c  mov     rax, rbp
0x18000958f  inc     rax
0x180009592  cmp     [rcx+rax], r13b
0x180009596  jnz     short loc_18000958F
0x180009598  lea     r8, [rax+1]; unsigned __int64
0x18000959c  mov     rcx, [r12+80h]
0x1800095a4  test    rcx, rcx
0x1800095a7  jz      short loc_1800095B9
0x1800095a9  mov     rax, rbp
0x1800095ac  inc     rax
0x1800095af  cmp     [rcx+rax], r13b
0x1800095b3  jnz     short loc_1800095AC
0x1800095b5  lea     rdx, [rax+1]
0x1800095b9  mov     rcx, [r12+18h]
0x1800095be  test    rcx, rcx
0x1800095c1  jnz     short loc_1800095C8
0x1800095c3  lea     eax, [rcx+2]
0x1800095c6  jmp     short loc_1800095DD
0x1800095c8  mov     rax, rbp
0x1800095cb  inc     rax
0x1800095ce  cmp     [rcx+rax*2], r13w
0x1800095d3  jnz     short loc_1800095CB
0x1800095d5  lea     rax, ds:2[rax*2]
0x1800095dd  lea     r14, [rdx+rax]
0x1800095e1  add     r14, r8
0x1800095e4  lea     rsi, [rdi+48h]
0x1800095e8  cmp     [rdi+40h], r13
0x1800095ec  jz      short loc_1800095F3
0x1800095ee  cmp     [rsi], r14
0x1800095f1  jnb     short loc_180009627
0x1800095f3  mov     rdx, r14; dwBytes
0x1800095f6  mov     ecx, 8; dwFlags
0x1800095fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009600  mov     r15, rax
0x180009603  test    rax, rax
0x180009606  jz      short loc_180009627
0x180009608  mov     rbx, [rdi+40h]
0x18000960c  call    cs:__imp_GetProcessHeap
0x180009612  mov     r8, rbx; lpMem
0x180009615  xor     edx, edx; dwFlags
0x180009617  mov     rcx, rax; hHeap
0x18000961a  call    cs:__imp_HeapFree
0x180009620  mov     [rdi+40h], r15
0x180009624  mov     [rsi], r14
0x180009627  mov     rbx, [rdi+40h]
0x18000962b  test    rbx, rbx
0x18000962e  jz      loc_18000972C
0x180009634  mov     rdx, [rsi]; DestinationSize
0x180009637  lea     rsi, [rdx+rbx]
0x18000963b  cmp     rbx, rsi
0x18000963e  jz      short loc_18000967E
0x180009640  mov     r8, [r12+38h]; Source
0x180009645  test    r8, r8
0x180009648  jz      short loc_18000967E
0x18000964a  cmp     [r8], r13b
0x18000964d  jz      short loc_18000967E
0x18000964f  mov     rax, rbp
0x180009652  inc     rax
0x180009655  cmp     [r8+rax], r13b
0x180009659  jnz     short loc_180009652
0x18000965b  lea     r14, [rax+1]
0x18000965f  cmp     rdx, r14
0x180009662  jnb     short loc_18000966A
0x180009664  mov     [rdi+10h], r13
0x180009668  jmp     short loc_180009687
0x18000966a  mov     r9, r14; SourceSize
0x18000966d  mov     rcx, rbx; Destination
0x180009670  call    memcpy_s
0x180009675  mov     [rdi+10h], rbx
0x180009679  add     rbx, r14
0x18000967c  jmp     short loc_180009682
0x18000967e  mov     [rdi+10h], r13
0x180009682  cmp     rbx, rsi
0x180009685  jz      short loc_1800096CE
0x180009687  mov     r8, [r12+80h]; Source
0x18000968f  test    r8, r8
0x180009692  jz      short loc_1800096CE
0x180009694  cmp     [r8], r13b
0x180009697  jz      short loc_1800096CE
0x180009699  mov     rax, rbp
0x18000969c  inc     rax
0x18000969f  cmp     [r8+rax], r13b
0x1800096a3  jnz     short loc_18000969C
0x1800096a5  mov     rdx, rsi
0x1800096a8  lea     r14, [rax+1]
0x1800096ac  sub     rdx, rbx; DestinationSize
0x1800096af  cmp     rdx, r14
0x1800096b2  jnb     short loc_1800096BA
0x1800096b4  mov     [rdi+20h], r13
0x1800096b8  jmp     short loc_1800096D7
0x1800096ba  mov     r9, r14; SourceSize
0x1800096bd  mov     rcx, rbx; Destination
0x1800096c0  call    memcpy_s
0x1800096c5  mov     [rdi+20h], rbx
0x1800096c9  add     rbx, r14
0x1800096cc  jmp     short loc_1800096D2
0x1800096ce  mov     [rdi+20h], r13
0x1800096d2  cmp     rbx, rsi
0x1800096d5  jz      short loc_180009718
0x1800096d7  mov     r8, [r12+18h]; Source
0x1800096dc  test    r8, r8
0x1800096df  jz      short loc_180009718
0x1800096e1  cmp     [r8], r13w
0x1800096e5  jz      short loc_180009718
0x1800096e7  inc     rbp
0x1800096ea  cmp     [r8+rbp*2], r13w
0x1800096ef  jnz     short loc_1800096E7
0x1800096f1  mov     rdx, rsi
0x1800096f4  lea     r14, ds:2[rbp*2]
0x1800096fc  sub     rdx, rbx; DestinationSize
0x1800096ff  cmp     rdx, r14
0x180009702  jb      short loc_180009718
0x180009704  mov     r9, r14; SourceSize
0x180009707  mov     rcx, rbx; Destination
0x18000970a  call    memcpy_s
0x18000970f  mov     [rdi+38h], rbx
0x180009713  add     rbx, r14
0x180009716  jmp     short loc_18000971C
0x180009718  mov     [rdi+38h], r13
0x18000971c  sub     rsi, rbx
0x18000971f  xor     edx, edx; Val
0x180009721  mov     r8, rsi; Size
0x180009724  mov     rcx, rbx; void *
0x180009727  call    memset_0
0x18000972c  add     rsp, 28h
0x180009730  pop     r15
0x180009732  pop     r14
0x180009734  pop     r13
0x180009736  pop     r12
0x180009738  pop     rdi
0x180009739  pop     rsi
0x18000973a  pop     rbp
0x18000973b  pop     rbx
0x18000973c  retn
```
