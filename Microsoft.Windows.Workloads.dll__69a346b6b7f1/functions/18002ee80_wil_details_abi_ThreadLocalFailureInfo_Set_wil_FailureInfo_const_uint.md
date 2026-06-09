# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002ee80`
- end: `0x18002f15c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `732`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002f430`

## callees

- `0x18000fd20`
- `0x18002ee80`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002ef8d`
- `KERNEL32!HeapFree` at `0x18002ef8d`
- `KERNEL32!GetProcessHeap` at `0x18002ef7f`
- `KERNEL32!GetProcessHeap` at `0x18002ef7f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f076`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f0f9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f076`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f0f9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f082`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f105`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f082`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f105`

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
0x18002ee80  mov     [rsp+arg_10], rbx
0x18002ee85  push    rbp
0x18002ee86  push    rsi
0x18002ee87  push    r12
0x18002ee89  push    r13
0x18002ee8b  push    r14
0x18002ee8d  sub     rsp, 20h
0x18002ee91  mov     [rcx+4], r8d
0x18002ee95  xor     r12d, r12d
0x18002ee98  mov     eax, [rdx+8]
0x18002ee9b  mov     r14, rcx
0x18002ee9e  mov     [rcx+8], eax
0x18002eea1  mov     r13, rdx
0x18002eea4  mov     [rcx+10h], r12
0x18002eea8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002eeaf  movzx   eax, word ptr [rdx+40h]
0x18002eeb3  mov     [rcx+18h], ax
0x18002eeb7  movzx   eax, byte ptr [rdx]
0x18002eeba  mov     [rcx+1Ah], al
0x18002eebd  mov     [rcx+20h], r12
0x18002eec1  mov     rax, [rdx+88h]
0x18002eec8  mov     [rcx+28h], rax
0x18002eecc  mov     rax, [rdx+90h]
0x18002eed3  mov     [rcx+30h], rax
0x18002eed7  mov     [rcx+38h], r12
0x18002eedb  mov     rcx, [rdx+38h]
0x18002eedf  mov     edx, 1
0x18002eee4  test    rcx, rcx
0x18002eee7  jnz     short loc_18002EEEE
0x18002eee9  mov     r8d, edx
0x18002eeec  jmp     short loc_18002EF00
0x18002eeee  mov     rax, rsi
0x18002eef1  cmp     [rcx+rax+1], r12b
0x18002eef6  lea     rax, [rax+1]
0x18002eefa  jnz     short loc_18002EEF1
0x18002eefc  lea     r8, [rax+1]; unsigned __int64
0x18002ef00  mov     rcx, [r13+80h]
0x18002ef07  test    rcx, rcx
0x18002ef0a  jz      short loc_18002EF1F
0x18002ef0c  mov     rax, rsi
0x18002ef0f  nop
0x18002ef10  cmp     [rcx+rax+1], r12b
0x18002ef15  lea     rax, [rax+1]
0x18002ef19  jnz     short loc_18002EF10
0x18002ef1b  lea     rdx, [rax+1]
0x18002ef1f  mov     rcx, [r13+18h]
0x18002ef23  test    rcx, rcx
0x18002ef26  jnz     short loc_18002EF2F
0x18002ef28  mov     eax, 2
0x18002ef2d  jmp     short loc_18002EF46
0x18002ef2f  mov     rax, rsi
0x18002ef32  cmp     [rcx+rax*2+2], r12w
0x18002ef38  lea     rax, [rax+1]
0x18002ef3c  jnz     short loc_18002EF32
0x18002ef3e  lea     rax, ds:2[rax*2]
0x18002ef46  mov     [rsp+48h+arg_0], rdi
0x18002ef4b  lea     rbp, [rax+rdx]
0x18002ef4f  add     rbp, r8
0x18002ef52  mov     [rsp+48h+arg_8], r15
0x18002ef57  lea     rdi, [r14+48h]
0x18002ef5b  cmp     [r14+40h], r12
0x18002ef5f  jz      short loc_18002EF66
0x18002ef61  cmp     [rdi], rbp
0x18002ef64  jnb     short loc_18002EF9A
0x18002ef66  mov     rdx, rbp; dwBytes
0x18002ef69  mov     ecx, 8; dwFlags
0x18002ef6e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002ef73  mov     r15, rax
0x18002ef76  test    rax, rax
0x18002ef79  jz      short loc_18002EF9A
0x18002ef7b  mov     rbx, [r14+40h]
0x18002ef7f  call    cs:__imp_GetProcessHeap
0x18002ef85  mov     r8, rbx; lpMem
0x18002ef88  xor     edx, edx; dwFlags
0x18002ef8a  mov     rcx, rax; hHeap
0x18002ef8d  call    cs:__imp_HeapFree
0x18002ef93  mov     [r14+40h], r15
0x18002ef97  mov     [rdi], rbp
0x18002ef9a  mov     rbx, [r14+40h]
0x18002ef9e  test    rbx, rbx
0x18002efa1  jz      loc_18002F140
0x18002efa7  mov     rcx, [rdi]
0x18002efaa  lea     rdi, [r14+10h]
0x18002efae  mov     rdx, [r13+38h]; Src
0x18002efb2  lea     rbp, [rcx+rbx]
0x18002efb6  cmp     rbx, rbp
0x18002efb9  jz      short loc_18002F019
0x18002efbb  test    rdx, rdx
0x18002efbe  jz      short loc_18002F019
0x18002efc0  cmp     byte ptr [rdx], 0
0x18002efc3  jz      short loc_18002F019
0x18002efc5  mov     rax, rsi
0x18002efc8  nop     dword ptr [rax+rax+00000000h]
0x18002efd0  cmp     byte ptr [rdx+rax+1], 0
0x18002efd5  lea     rax, [rax+1]
0x18002efd9  jnz     short loc_18002EFD0
0x18002efdb  lea     r15, [rax+1]
0x18002efdf  cmp     rcx, r15
0x18002efe2  jnb     short loc_18002EFF9
0x18002efe4  test    rdi, rdi
0x18002efe7  jz      short loc_18002EFEC
0x18002efe9  mov     [rdi], r12
0x18002efec  mov     rdx, [r13+80h]
0x18002eff3  lea     rdi, [r14+20h]
0x18002eff7  jmp     short loc_18002F031
0x18002eff9  test    r15, r15
0x18002effc  jz      short loc_18002F00C
0x18002effe  lfence
0x18002f001  mov     r8, r15; Size
0x18002f004  mov     rcx, rbx; void *
0x18002f007  call    memmove
0x18002f00c  test    rdi, rdi
0x18002f00f  jz      short loc_18002F014
0x18002f011  mov     [rdi], rbx
0x18002f014  add     rbx, r15
0x18002f017  jmp     short loc_18002F021
0x18002f019  test    rdi, rdi
0x18002f01c  jz      short loc_18002F021
0x18002f01e  mov     [rdi], r12
0x18002f021  mov     rdx, [r13+80h]; Src
0x18002f028  lea     rdi, [r14+20h]
0x18002f02c  cmp     rbx, rbp
0x18002f02f  jz      short loc_18002F0A5
0x18002f031  test    rdx, rdx
0x18002f034  jz      short loc_18002F0A5
0x18002f036  cmp     byte ptr [rdx], 0
0x18002f039  jz      short loc_18002F0A5
0x18002f03b  mov     rax, rsi
0x18002f03e  xchg    ax, ax
0x18002f040  cmp     byte ptr [rdx+rax+1], 0
0x18002f045  lea     rax, [rax+1]
0x18002f049  jnz     short loc_18002F040
0x18002f04b  lea     r15, [rax+1]
0x18002f04f  mov     rax, rbp
0x18002f052  sub     rax, rbx
0x18002f055  cmp     rax, r15
0x18002f058  jnb     short loc_18002F06C
0x18002f05a  test    rdi, rdi
0x18002f05d  jz      short loc_18002F062
0x18002f05f  mov     [rdi], r12
0x18002f062  mov     rdx, [r13+18h]
0x18002f066  lea     rdi, [r14+38h]
0x18002f06a  jmp     short loc_18002F0BA
0x18002f06c  test    r15, r15
0x18002f06f  jz      short loc_18002F098
0x18002f071  test    rbx, rbx
0x18002f074  jnz     short loc_18002F08A
0x18002f076  call    cs:__imp__errno
0x18002f07c  mov     dword ptr [rax], 16h
0x18002f082  call    cs:__imp__invalid_parameter_noinfo
0x18002f088  jmp     short loc_18002F098
0x18002f08a  lfence
0x18002f08d  mov     r8, r15; Size
0x18002f090  mov     rcx, rbx; void *
0x18002f093  call    memmove
0x18002f098  test    rdi, rdi
0x18002f09b  jz      short loc_18002F0A0
0x18002f09d  mov     [rdi], rbx
0x18002f0a0  add     rbx, r15
0x18002f0a3  jmp     short loc_18002F0AD
0x18002f0a5  test    rdi, rdi
0x18002f0a8  jz      short loc_18002F0AD
0x18002f0aa  mov     [rdi], r12
0x18002f0ad  mov     rdx, [r13+18h]; Src
0x18002f0b1  lea     rdi, [r14+38h]
0x18002f0b5  cmp     rbx, rbp
0x18002f0b8  jz      short loc_18002F128
0x18002f0ba  test    rdx, rdx
0x18002f0bd  jz      short loc_18002F128
0x18002f0bf  cmp     word ptr [rdx], 0
0x18002f0c3  jz      short loc_18002F128
0x18002f0c5  nop     word ptr [rax+rax+00000000h]
0x18002f0d0  cmp     word ptr [rdx+rsi*2+2], 0
0x18002f0d6  lea     rsi, [rsi+1]
0x18002f0da  jnz     short loc_18002F0D0
0x18002f0dc  mov     rax, rbp
0x18002f0df  lea     rsi, ds:2[rsi*2]
0x18002f0e7  sub     rax, rbx
0x18002f0ea  cmp     rax, rsi
0x18002f0ed  jb      short loc_18002F128
0x18002f0ef  test    rsi, rsi
0x18002f0f2  jz      short loc_18002F11B
0x18002f0f4  test    rbx, rbx
0x18002f0f7  jnz     short loc_18002F10D
0x18002f0f9  call    cs:__imp__errno
0x18002f0ff  mov     dword ptr [rax], 16h
0x18002f105  call    cs:__imp__invalid_parameter_noinfo
0x18002f10b  jmp     short loc_18002F11B
0x18002f10d  lfence
0x18002f110  mov     r8, rsi; Size
0x18002f113  mov     rcx, rbx; void *
0x18002f116  call    memmove
0x18002f11b  test    rdi, rdi
0x18002f11e  jz      short loc_18002F123
0x18002f120  mov     [rdi], rbx
0x18002f123  add     rbx, rsi
0x18002f126  jmp     short loc_18002F130
0x18002f128  test    rdi, rdi
0x18002f12b  jz      short loc_18002F130
0x18002f12d  mov     [rdi], r12
0x18002f130  sub     rbp, rbx
0x18002f133  xor     edx, edx; Val
0x18002f135  mov     r8, rbp; Size
0x18002f138  mov     rcx, rbx; void *
0x18002f13b  call    memset
0x18002f140  mov     r15, [rsp+48h+arg_8]
0x18002f145  mov     rdi, [rsp+48h+arg_0]
0x18002f14a  mov     rbx, [rsp+48h+arg_10]
0x18002f14f  add     rsp, 20h
0x18002f153  pop     r14
0x18002f155  pop     r13
0x18002f157  pop     r12
0x18002f159  pop     rsi
0x18002f15a  pop     rbp
0x18002f15b  retn
```
