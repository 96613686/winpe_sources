# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800046d0`
- end: `0x1800049ac`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `732`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004c80`

## callees

- `0x1800025d0`
- `0x1800046d0`
- `0x18000b990`
- `0x18000bd50`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800047dd`
- `KERNEL32!HeapFree` at `0x1800047dd`
- `KERNEL32!GetProcessHeap` at `0x1800047cf`
- `KERNEL32!GetProcessHeap` at `0x1800047cf`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800048c6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004949`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800048c6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004949`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800048d2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180004955`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800048d2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180004955`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  bool v10; // zf
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rbp
  unsigned __int64 *v17; // rdi
  LPVOID v18; // r15
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  char *v21; // rbx
  unsigned __int64 v22; // rcx
  char **v23; // rdi
  _BYTE *v24; // rdx
  char *v25; // rbp
  __int64 v26; // rax
  __int64 v27; // r15
  _BYTE *v28; // rdx
  char **v29; // rdi
  __int64 v30; // rax
  size_t v31; // r15
  _WORD *v32; // rdx
  char **v33; // rdi
  size_t v34; // rsi

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  v5 = -1;
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
      v10 = *(_BYTE *)(v6 + v9++ + 1) == 0;
    while ( !v10 );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v11 = *((_QWORD *)a2 + 16);
  if ( v11 )
  {
    v12 = -1;
    do
      v10 = *(_BYTE *)(v11 + v12++ + 1) == 0;
    while ( !v10 );
    v7 = v12 + 1;
  }
  v13 = *((_QWORD *)a2 + 3);
  if ( v13 )
  {
    v15 = -1;
    do
      v10 = *(_WORD *)(v13 + 2 * v15++ + 2) == 0;
    while ( !v10 );
    v14 = 2 * v15 + 2;
  }
  else
  {
    v14 = 2;
  }
  v16 = v8 + v14 + v7;
  v17 = (unsigned __int64 *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v17 < v16 )
  {
    v18 = wil::details::ProcessHeapAlloc(8u, v8 + v14 + v7);
    if ( v18 )
    {
      v19 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v19);
      *((_QWORD *)this + 8) = v18;
      *v17 = v16;
    }
  }
  v21 = (char *)*((_QWORD *)this + 8);
  if ( v21 )
  {
    v22 = *v17;
    v23 = (char **)((char *)this + 16);
    v24 = (_BYTE *)*((_QWORD *)a2 + 7);
    v25 = &v21[v22];
    if ( v21 != &v21[v22] && v24 && *v24 )
    {
      v26 = -1;
      do
        v10 = v24[++v26] == 0;
      while ( !v10 );
      v27 = v26 + 1;
      if ( v22 < v26 + 1 )
      {
        if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
          *v23 = 0;
        v28 = (_BYTE *)*((_QWORD *)a2 + 16);
        v29 = (char **)((char *)this + 32);
LABEL_37:
        if ( v28 && *v28 )
        {
          v30 = -1;
          do
            v10 = v28[++v30] == 0;
          while ( !v10 );
          v31 = v30 + 1;
          if ( v25 - v21 < (unsigned __int64)(v30 + 1) )
          {
            if ( v29 )
              *v29 = 0;
            v32 = (_WORD *)*((_QWORD *)a2 + 3);
            v33 = (char **)((char *)this + 56);
LABEL_55:
            if ( v32 && *v32 )
            {
              do
                v10 = v32[++v5] == 0;
              while ( !v10 );
              v34 = 2 * v5 + 2;
              if ( v25 - v21 >= v34 )
              {
                if ( v34 )
                {
                  if ( v21 )
                  {
                    _mm_lfence();
                    memmove(v21, v32, v34);
                  }
                  else
                  {
                    *_errno() = 22;
                    _invalid_parameter_noinfo();
                  }
                }
                if ( v33 )
                  *v33 = v21;
                v21 += v34;
LABEL_68:
                memset(v21, 0, v25 - v21);
                return;
              }
            }
LABEL_66:
            if ( v33 )
              *v33 = 0;
            goto LABEL_68;
          }
          if ( v30 != -1 )
          {
            if ( v21 )
            {
              _mm_lfence();
              memmove(v21, v28, v31);
            }
            else
            {
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
          }
          if ( v29 )
            *v29 = v21;
          v21 += v31;
LABEL_54:
          v32 = (_WORD *)*((_QWORD *)a2 + 3);
          v33 = (char **)((char *)this + 56);
          if ( v21 == v25 )
            goto LABEL_66;
          goto LABEL_55;
        }
LABEL_52:
        if ( v29 )
          *v29 = 0;
        goto LABEL_54;
      }
      if ( v26 != -1 )
      {
        _mm_lfence();
        memmove(*((void **)this + 8), v24, v26 + 1);
      }
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v23 = v21;
      v21 += v27;
    }
    else if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
    {
      *v23 = 0;
    }
    v28 = (_BYTE *)*((_QWORD *)a2 + 16);
    v29 = (char **)((char *)this + 32);
    if ( v21 == v25 )
      goto LABEL_52;
    goto LABEL_37;
  }
}

```

## disassembly

```asm
0x1800046d0  mov     [rsp+arg_10], rbx
0x1800046d5  push    rbp
0x1800046d6  push    rsi
0x1800046d7  push    r12
0x1800046d9  push    r13
0x1800046db  push    r14
0x1800046dd  sub     rsp, 20h
0x1800046e1  mov     [rcx+4], r8d
0x1800046e5  xor     r12d, r12d
0x1800046e8  mov     eax, [rdx+8]
0x1800046eb  mov     r14, rcx
0x1800046ee  mov     [rcx+8], eax
0x1800046f1  mov     r13, rdx
0x1800046f4  mov     [rcx+10h], r12
0x1800046f8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800046ff  movzx   eax, word ptr [rdx+40h]
0x180004703  mov     [rcx+18h], ax
0x180004707  movzx   eax, byte ptr [rdx]
0x18000470a  mov     [rcx+1Ah], al
0x18000470d  mov     [rcx+20h], r12
0x180004711  mov     rax, [rdx+88h]
0x180004718  mov     [rcx+28h], rax
0x18000471c  mov     rax, [rdx+90h]
0x180004723  mov     [rcx+30h], rax
0x180004727  mov     [rcx+38h], r12
0x18000472b  mov     rcx, [rdx+38h]
0x18000472f  mov     edx, 1
0x180004734  test    rcx, rcx
0x180004737  jnz     short loc_18000473E
0x180004739  mov     r8d, edx
0x18000473c  jmp     short loc_180004750
0x18000473e  mov     rax, rsi
0x180004741  cmp     [rcx+rax+1], r12b
0x180004746  lea     rax, [rax+1]
0x18000474a  jnz     short loc_180004741
0x18000474c  lea     r8, [rax+1]; unsigned __int64
0x180004750  mov     rcx, [r13+80h]
0x180004757  test    rcx, rcx
0x18000475a  jz      short loc_18000476F
0x18000475c  mov     rax, rsi
0x18000475f  nop
0x180004760  cmp     [rcx+rax+1], r12b
0x180004765  lea     rax, [rax+1]
0x180004769  jnz     short loc_180004760
0x18000476b  lea     rdx, [rax+1]
0x18000476f  mov     rcx, [r13+18h]
0x180004773  test    rcx, rcx
0x180004776  jnz     short loc_18000477F
0x180004778  mov     eax, 2
0x18000477d  jmp     short loc_180004796
0x18000477f  mov     rax, rsi
0x180004782  cmp     [rcx+rax*2+2], r12w
0x180004788  lea     rax, [rax+1]
0x18000478c  jnz     short loc_180004782
0x18000478e  lea     rax, ds:2[rax*2]
0x180004796  mov     [rsp+48h+arg_0], rdi
0x18000479b  lea     rbp, [rax+rdx]
0x18000479f  add     rbp, r8
0x1800047a2  mov     [rsp+48h+arg_8], r15
0x1800047a7  lea     rdi, [r14+48h]
0x1800047ab  cmp     [r14+40h], r12
0x1800047af  jz      short loc_1800047B6
0x1800047b1  cmp     [rdi], rbp
0x1800047b4  jnb     short loc_1800047EA
0x1800047b6  mov     rdx, rbp; dwBytes
0x1800047b9  mov     ecx, 8; dwFlags
0x1800047be  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800047c3  mov     r15, rax
0x1800047c6  test    rax, rax
0x1800047c9  jz      short loc_1800047EA
0x1800047cb  mov     rbx, [r14+40h]
0x1800047cf  call    cs:__imp_GetProcessHeap
0x1800047d5  mov     r8, rbx; lpMem
0x1800047d8  xor     edx, edx; dwFlags
0x1800047da  mov     rcx, rax; hHeap
0x1800047dd  call    cs:__imp_HeapFree
0x1800047e3  mov     [r14+40h], r15
0x1800047e7  mov     [rdi], rbp
0x1800047ea  mov     rbx, [r14+40h]
0x1800047ee  test    rbx, rbx
0x1800047f1  jz      loc_180004990
0x1800047f7  mov     rcx, [rdi]
0x1800047fa  lea     rdi, [r14+10h]
0x1800047fe  mov     rdx, [r13+38h]; Src
0x180004802  lea     rbp, [rcx+rbx]
0x180004806  cmp     rbx, rbp
0x180004809  jz      short loc_180004869
0x18000480b  test    rdx, rdx
0x18000480e  jz      short loc_180004869
0x180004810  cmp     byte ptr [rdx], 0
0x180004813  jz      short loc_180004869
0x180004815  mov     rax, rsi
0x180004818  nop     dword ptr [rax+rax+00000000h]
0x180004820  cmp     byte ptr [rdx+rax+1], 0
0x180004825  lea     rax, [rax+1]
0x180004829  jnz     short loc_180004820
0x18000482b  lea     r15, [rax+1]
0x18000482f  cmp     rcx, r15
0x180004832  jnb     short loc_180004849
0x180004834  test    rdi, rdi
0x180004837  jz      short loc_18000483C
0x180004839  mov     [rdi], r12
0x18000483c  mov     rdx, [r13+80h]
0x180004843  lea     rdi, [r14+20h]
0x180004847  jmp     short loc_180004881
0x180004849  test    r15, r15
0x18000484c  jz      short loc_18000485C
0x18000484e  lfence
0x180004851  mov     r8, r15; Size
0x180004854  mov     rcx, rbx; void *
0x180004857  call    memmove
0x18000485c  test    rdi, rdi
0x18000485f  jz      short loc_180004864
0x180004861  mov     [rdi], rbx
0x180004864  add     rbx, r15
0x180004867  jmp     short loc_180004871
0x180004869  test    rdi, rdi
0x18000486c  jz      short loc_180004871
0x18000486e  mov     [rdi], r12
0x180004871  mov     rdx, [r13+80h]; Src
0x180004878  lea     rdi, [r14+20h]
0x18000487c  cmp     rbx, rbp
0x18000487f  jz      short loc_1800048F5
0x180004881  test    rdx, rdx
0x180004884  jz      short loc_1800048F5
0x180004886  cmp     byte ptr [rdx], 0
0x180004889  jz      short loc_1800048F5
0x18000488b  mov     rax, rsi
0x18000488e  xchg    ax, ax
0x180004890  cmp     byte ptr [rdx+rax+1], 0
0x180004895  lea     rax, [rax+1]
0x180004899  jnz     short loc_180004890
0x18000489b  lea     r15, [rax+1]
0x18000489f  mov     rax, rbp
0x1800048a2  sub     rax, rbx
0x1800048a5  cmp     rax, r15
0x1800048a8  jnb     short loc_1800048BC
0x1800048aa  test    rdi, rdi
0x1800048ad  jz      short loc_1800048B2
0x1800048af  mov     [rdi], r12
0x1800048b2  mov     rdx, [r13+18h]
0x1800048b6  lea     rdi, [r14+38h]
0x1800048ba  jmp     short loc_18000490A
0x1800048bc  test    r15, r15
0x1800048bf  jz      short loc_1800048E8
0x1800048c1  test    rbx, rbx
0x1800048c4  jnz     short loc_1800048DA
0x1800048c6  call    cs:__imp__errno
0x1800048cc  mov     dword ptr [rax], 16h
0x1800048d2  call    cs:__imp__invalid_parameter_noinfo
0x1800048d8  jmp     short loc_1800048E8
0x1800048da  lfence
0x1800048dd  mov     r8, r15; Size
0x1800048e0  mov     rcx, rbx; void *
0x1800048e3  call    memmove
0x1800048e8  test    rdi, rdi
0x1800048eb  jz      short loc_1800048F0
0x1800048ed  mov     [rdi], rbx
0x1800048f0  add     rbx, r15
0x1800048f3  jmp     short loc_1800048FD
0x1800048f5  test    rdi, rdi
0x1800048f8  jz      short loc_1800048FD
0x1800048fa  mov     [rdi], r12
0x1800048fd  mov     rdx, [r13+18h]; Src
0x180004901  lea     rdi, [r14+38h]
0x180004905  cmp     rbx, rbp
0x180004908  jz      short loc_180004978
0x18000490a  test    rdx, rdx
0x18000490d  jz      short loc_180004978
0x18000490f  cmp     word ptr [rdx], 0
0x180004913  jz      short loc_180004978
0x180004915  nop     word ptr [rax+rax+00000000h]
0x180004920  cmp     word ptr [rdx+rsi*2+2], 0
0x180004926  lea     rsi, [rsi+1]
0x18000492a  jnz     short loc_180004920
0x18000492c  mov     rax, rbp
0x18000492f  lea     rsi, ds:2[rsi*2]
0x180004937  sub     rax, rbx
0x18000493a  cmp     rax, rsi
0x18000493d  jb      short loc_180004978
0x18000493f  test    rsi, rsi
0x180004942  jz      short loc_18000496B
0x180004944  test    rbx, rbx
0x180004947  jnz     short loc_18000495D
0x180004949  call    cs:__imp__errno
0x18000494f  mov     dword ptr [rax], 16h
0x180004955  call    cs:__imp__invalid_parameter_noinfo
0x18000495b  jmp     short loc_18000496B
0x18000495d  lfence
0x180004960  mov     r8, rsi; Size
0x180004963  mov     rcx, rbx; void *
0x180004966  call    memmove
0x18000496b  test    rdi, rdi
0x18000496e  jz      short loc_180004973
0x180004970  mov     [rdi], rbx
0x180004973  add     rbx, rsi
0x180004976  jmp     short loc_180004980
0x180004978  test    rdi, rdi
0x18000497b  jz      short loc_180004980
0x18000497d  mov     [rdi], r12
0x180004980  sub     rbp, rbx
0x180004983  xor     edx, edx; Val
0x180004985  mov     r8, rbp; Size
0x180004988  mov     rcx, rbx; void *
0x18000498b  call    memset
0x180004990  mov     r15, [rsp+48h+arg_8]
0x180004995  mov     rdi, [rsp+48h+arg_0]
0x18000499a  mov     rbx, [rsp+48h+arg_10]
0x18000499f  add     rsp, 20h
0x1800049a3  pop     r14
0x1800049a5  pop     r13
0x1800049a7  pop     r12
0x1800049a9  pop     rsi
0x1800049aa  pop     rbp
0x1800049ab  retn
```
