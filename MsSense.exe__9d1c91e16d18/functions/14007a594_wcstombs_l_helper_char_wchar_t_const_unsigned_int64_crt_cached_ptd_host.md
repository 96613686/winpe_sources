# _wcstombs_l_helper(char *,wchar_t const *,unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x14007a594`
- end: `0x14007a8d3`
- name: `?_wcstombs_l_helper@@YA_KPEADPEB_W_KAEAV__crt_cached_ptd_host@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(__crt_mbstring *this, const wchar_t *, unsigned __int64, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14007a480`

## callees

- `0x140051ba0`
- `0x14006147c`
- `0x140065e50`
- `0x14007a594`
- `0x14007ad18`
- `0x14007d8f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007a76f`
- `KERNEL32!GetLastError` at `0x14007a76f`

## pseudocode

```c
__int64 __fastcall _wcstombs_l_helper(
        __crt_mbstring *this,
        const wchar_t *a2,
        unsigned __int64 a3,
        struct __crt_cached_ptd_host *a4)
{
  unsigned __int64 v5; // rsi
  __int64 v7; // rdi
  __int64 result; // rax
  __int64 v9; // rax
  int v10; // r10d
  __int64 v11; // rcx
  __int16 v12; // ax
  const wchar_t *v13; // rax
  unsigned __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // r14
  int v19; // edx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  char v26; // al
  wchar_t v27; // ax
  __int64 v28; // rcx
  int v29; // eax
  int v30; // [rsp+40h] [rbp-38h] BYREF
  const wchar_t *v31; // [rsp+48h] [rbp-30h]
  __int64 v32; // [rsp+50h] [rbp-28h]
  _BYTE v33[8]; // [rsp+58h] [rbp-20h] BYREF

  v31 = a2;
  v30 = 0;
  v5 = a3;
  v7 = 0;
  if ( this && !a3 )
    return 0;
  if ( !a2 )
  {
    *((_BYTE *)a4 + 48) = 1;
    *((_DWORD *)a4 + 11) = 22;
    sub_14006147C(0, 0, 0, 0, 0, a4);
    return -1;
  }
  if ( !*((_BYTE *)a4 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(a4);
    a2 = v31;
  }
  v9 = *((_QWORD *)a4 + 3);
  v10 = *(_DWORD *)(v9 + 12);
  if ( v10 == 65001 )
  {
    v32 = 0;
    return sub_14007D8F4(this, (struct _Mbstatet *)a4);
  }
  v11 = *(_QWORD *)(v9 + 312);
  if ( !this )
  {
    if ( !v11 )
    {
      v27 = *a2;
      v28 = 0;
      if ( *a2 )
      {
        while ( v27 <= 0xFFu )
        {
          ++a2;
          ++v28;
          v27 = *a2;
          if ( !*a2 )
            return v28;
        }
        goto LABEL_18;
      }
      return v28;
    }
    v7 = -1;
    v29 = _acrt_WideCharToMultiByte(v10, 0, (_DWORD)a2, -1, 0, 0, 0, (__int64)&v30);
    if ( v29 && !v30 )
      return v29 - 1LL;
    goto LABEL_57;
  }
  if ( !v11 )
  {
    if ( v5 )
    {
      while ( *a2 <= 0xFFu )
      {
        *((_BYTE *)this + v7) = *(_BYTE *)a2;
        v12 = *a2++;
        v31 = a2;
        if ( v12 )
        {
          if ( ++v7 < v5 )
            continue;
        }
        return v7;
      }
LABEL_18:
      *((_BYTE *)a4 + 48) = 1;
      *((_DWORD *)a4 + 11) = 42;
      return -1;
    }
    return v7;
  }
  if ( *(_DWORD *)(v9 + 8) != 1 )
  {
    v7 = -1;
    v17 = _acrt_WideCharToMultiByte(v10, 0, (_DWORD)a2, -1, (_DWORD)this, v5, 0, (__int64)&v30);
    v18 = v17;
    if ( !v30 )
    {
      if ( v17 )
        return v17 - 1LL;
      if ( GetLastError() == 122 )
      {
        if ( !v5 )
          return v18;
        v19 = (int)v31;
LABEL_37:
        v20 = *((_QWORD *)a4 + 3);
        v21 = *(_DWORD *)(v20 + 8);
        v22 = *(_DWORD *)(v20 + 12);
        if ( v21 > 5 )
          v21 = 5;
        v23 = _acrt_WideCharToMultiByte(v22, 0, v19, 1, (unsigned int)v33, v21, 0, (__int64)&v30);
        if ( v23 )
        {
          if ( !v30 && v23 >= 0 )
          {
            v24 = v23;
            if ( (unsigned __int64)v23 <= 5 )
            {
              if ( v23 + v18 <= v5 )
              {
                v25 = 0;
                while ( 1 )
                {
                  v26 = v33[v25];
                  *((_BYTE *)this + v18) = v26;
                  if ( !v26 )
                    break;
                  ++v25;
                  ++v18;
                  if ( v25 >= v24 )
                  {
                    v19 = (_DWORD)v31++ + 2;
                    if ( v18 < v5 )
                      goto LABEL_37;
                    return v18;
                  }
                }
              }
              return v18;
            }
          }
        }
      }
    }
LABEL_57:
    *((_DWORD *)a4 + 11) = 42;
    *((_BYTE *)a4 + 48) = 1;
    return v7;
  }
  if ( v5 )
  {
    v13 = a2;
    v14 = v5;
    while ( *v13 )
    {
      ++v13;
      if ( !--v14 )
        goto LABEL_26;
    }
    LODWORD(v5) = v13 - a2 + 1;
  }
LABEL_26:
  v15 = _acrt_WideCharToMultiByte(v10, 0, (_DWORD)a2, v5, (_DWORD)this, v5, 0, (__int64)&v30);
  v16 = v15;
  if ( !v15 || v30 )
    goto LABEL_18;
  result = v15 - 1LL;
  if ( *((_BYTE *)this + v16 - 1) )
    return v16;
  return result;
}

```

## disassembly

```asm
0x14007a594  push    rbp
0x14007a596  push    rbx
0x14007a597  push    rsi
0x14007a598  push    rdi
0x14007a599  push    r12
0x14007a59b  push    r13
0x14007a59d  push    r14
0x14007a59f  push    r15
0x14007a5a1  mov     rbp, rsp
0x14007a5a4  sub     rsp, 78h
0x14007a5a8  mov     rax, cs:__security_cookie
0x14007a5af  xor     rax, rsp
0x14007a5b2  mov     [rbp+var_18], rax
0x14007a5b6  xor     r12d, r12d
0x14007a5b9  mov     [rbp+var_30], rdx
0x14007a5bd  mov     [rbp+var_38], r12d
0x14007a5c1  mov     rbx, r9
0x14007a5c4  mov     rsi, r8
0x14007a5c7  mov     r15, rcx
0x14007a5ca  mov     edi, r12d
0x14007a5cd  test    rcx, rcx
0x14007a5d0  jz      short loc_14007A5DE
0x14007a5d2  test    r8, r8
0x14007a5d5  jnz     short loc_14007A5DE
0x14007a5d7  xor     eax, eax
0x14007a5d9  jmp     loc_14007A8B6
0x14007a5de  test    rdx, rdx
0x14007a5e1  jnz     short loc_14007A610
0x14007a5e3  mov     byte ptr [r9+30h], 1
0x14007a5e8  xor     r8d, r8d; FileName
0x14007a5eb  mov     dword ptr [r9+2Ch], 16h
0x14007a5f3  xor     ecx, ecx; Expression
0x14007a5f5  xor     r9d, r9d; LineNo
0x14007a5f8  mov     [rsp+78h+var_50], rbx; __crt_cached_ptd_host *
0x14007a5fd  mov     [rsp+78h+var_58], r12; uintptr_t
0x14007a602  call    sub_14006147C
0x14007a607  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007a60b  jmp     loc_14007A8B6
0x14007a610  cmp     [r9+28h], r12b
0x14007a614  jnz     short loc_14007A622
0x14007a616  mov     rcx, rbx; this
0x14007a619  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14007a61e  mov     rdx, [rbp+var_30]
0x14007a622  mov     rax, [rbx+18h]
0x14007a626  mov     r10d, [rax+0Ch]
0x14007a62a  cmp     r10d, 0FDE9h
0x14007a631  jnz     short loc_14007A654
0x14007a633  lea     r9, [rbp+var_28]
0x14007a637  mov     [rbp+var_28], r12
0x14007a63b  mov     r8, rsi
0x14007a63e  mov     [rsp+78h+var_58], rbx; struct _Mbstatet *
0x14007a643  lea     rdx, [rbp+var_30]
0x14007a647  mov     rcx, r15; this
0x14007a64a  call    sub_14007D8F4
0x14007a64f  jmp     loc_14007A8B6
0x14007a654  mov     rcx, [rax+138h]
0x14007a65b  test    r15, r15
0x14007a65e  jz      loc_14007A836
0x14007a664  test    rcx, rcx
0x14007a667  jnz     short loc_14007A6B5
0x14007a669  test    rsi, rsi
0x14007a66c  jz      loc_14007A8B3
0x14007a672  mov     r8d, 0FFh
0x14007a678  cmp     [rdx], r8w
0x14007a67c  ja      short loc_14007A6A5
0x14007a67e  mov     al, [rdx]
0x14007a680  mov     [r15+rdi], al
0x14007a684  movzx   eax, word ptr [rdx]
0x14007a687  add     rdx, 2
0x14007a68b  mov     [rbp+var_30], rdx
0x14007a68f  test    ax, ax
0x14007a692  jz      loc_14007A8B3
0x14007a698  inc     rdi
0x14007a69b  cmp     rdi, rsi
0x14007a69e  jb      short loc_14007A678
0x14007a6a0  jmp     loc_14007A8B3
0x14007a6a5  mov     byte ptr [rbx+30h], 1
0x14007a6a9  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x14007a6b0  jmp     loc_14007A607
0x14007a6b5  cmp     dword ptr [rax+8], 1
0x14007a6b9  jnz     short loc_14007A72A
0x14007a6bb  test    rsi, rsi
0x14007a6be  jz      short loc_14007A6E4
0x14007a6c0  mov     rax, rdx
0x14007a6c3  mov     rcx, rsi
0x14007a6c6  cmp     [rax], r12w
0x14007a6ca  jz      short loc_14007A6D8
0x14007a6cc  add     rax, 2
0x14007a6d0  sub     rcx, 1
0x14007a6d4  jnz     short loc_14007A6C6
0x14007a6d6  jmp     short loc_14007A6E4
0x14007a6d8  mov     rsi, rax
0x14007a6db  sub     rsi, rdx
0x14007a6de  sar     rsi, 1
0x14007a6e1  inc     rsi
0x14007a6e4  lea     rax, [rbp+var_38]
0x14007a6e8  mov     r8, rdx
0x14007a6eb  mov     [rsp+78h+var_40], rax
0x14007a6f0  mov     r9d, esi
0x14007a6f3  mov     [rsp+78h+var_48], r12
0x14007a6f8  xor     edx, edx
0x14007a6fa  mov     dword ptr [rsp+78h+var_50], esi
0x14007a6fe  mov     ecx, r10d
0x14007a701  mov     [rsp+78h+var_58], r15
0x14007a706  call    __acrt_WideCharToMultiByte
0x14007a70b  movsxd  rcx, eax
0x14007a70e  test    eax, eax
0x14007a710  jz      short loc_14007A6A5
0x14007a712  cmp     [rbp+var_38], r12d
0x14007a716  jnz     short loc_14007A6A5
0x14007a718  cmp     [r15+rcx-1], r12b
0x14007a71d  lea     rax, [rcx-1]
0x14007a721  cmovnz  rax, rcx
0x14007a725  jmp     loc_14007A8B6
0x14007a72a  lea     rax, [rbp+var_38]
0x14007a72e  mov     r8, rdx
0x14007a731  mov     [rsp+78h+var_40], rax
0x14007a736  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14007a73a  mov     [rsp+78h+var_48], r12
0x14007a73f  mov     r9d, edi
0x14007a742  mov     dword ptr [rsp+78h+var_50], esi
0x14007a746  xor     edx, edx
0x14007a748  mov     ecx, r10d
0x14007a74b  mov     [rsp+78h+var_58], r15
0x14007a750  call    __acrt_WideCharToMultiByte
0x14007a755  movsxd  r14, eax
0x14007a758  cmp     [rbp+var_38], r12d
0x14007a75c  jnz     loc_14007A8A8
0x14007a762  test    eax, eax
0x14007a764  jz      short loc_14007A76F
0x14007a766  lea     rax, [r14-1]
0x14007a76a  jmp     loc_14007A8B6
0x14007a76f  call    cs:GetLastError
0x14007a775  cmp     eax, 7Ah ; 'z'
0x14007a778  jnz     loc_14007A8A8
0x14007a77e  test    rsi, rsi
0x14007a781  jz      loc_14007A82E
0x14007a787  mov     rdx, [rbp+var_30]
0x14007a78b  lea     r13d, [rax-75h]
0x14007a78f  mov     rcx, [rbx+18h]
0x14007a793  lea     r8, [rbp+var_38]
0x14007a797  mov     [rsp+78h+var_40], r8
0x14007a79c  mov     r9d, 1
0x14007a7a2  mov     [rsp+78h+var_48], r12
0x14007a7a7  mov     r8, rdx
0x14007a7aa  mov     eax, [rcx+8]
0x14007a7ad  cmp     eax, r13d
0x14007a7b0  mov     ecx, [rcx+0Ch]
0x14007a7b3  cmovg   eax, r13d
0x14007a7b7  xor     edx, edx
0x14007a7b9  mov     dword ptr [rsp+78h+var_50], eax
0x14007a7bd  lea     rax, [rbp+var_20]
0x14007a7c1  mov     [rsp+78h+var_58], rax
0x14007a7c6  call    __acrt_WideCharToMultiByte
0x14007a7cb  test    eax, eax
0x14007a7cd  jz      loc_14007A8A8
0x14007a7d3  cmp     [rbp+var_38], r12d
0x14007a7d7  jnz     loc_14007A8A8
0x14007a7dd  test    eax, eax
0x14007a7df  js      loc_14007A8A8
0x14007a7e5  movsxd  rdx, eax
0x14007a7e8  cmp     rdx, r13
0x14007a7eb  ja      loc_14007A8A8
0x14007a7f1  lea     rax, [rdx+r14]
0x14007a7f5  cmp     rax, rsi
0x14007a7f8  ja      short loc_14007A82E
0x14007a7fa  mov     rcx, r12
0x14007a7fd  test    rdx, rdx
0x14007a800  jle     short loc_14007A819
0x14007a802  mov     al, [rbp+rcx+var_20]
0x14007a806  mov     [r15+r14], al
0x14007a80a  test    al, al
0x14007a80c  jz      short loc_14007A82E
0x14007a80e  inc     rcx
0x14007a811  inc     r14
0x14007a814  cmp     rcx, rdx
0x14007a817  jl      short loc_14007A802
0x14007a819  mov     rdx, [rbp+var_30]
0x14007a81d  add     rdx, 2
0x14007a821  mov     [rbp+var_30], rdx
0x14007a825  cmp     r14, rsi
0x14007a828  jb      loc_14007A78F
0x14007a82e  mov     rax, r14
0x14007a831  jmp     loc_14007A8B6
0x14007a836  test    rcx, rcx
0x14007a839  jnz     short loc_14007A86A
0x14007a83b  movzx   eax, word ptr [rdx]
0x14007a83e  mov     rcx, r12
0x14007a841  test    ax, ax
0x14007a844  jz      short loc_14007A865
0x14007a846  mov     r8d, 0FFh
0x14007a84c  cmp     ax, r8w
0x14007a850  ja      loc_14007A6A5
0x14007a856  add     rdx, 2
0x14007a85a  inc     rcx
0x14007a85d  movzx   eax, word ptr [rdx]
0x14007a860  test    ax, ax
0x14007a863  jnz     short loc_14007A84C
0x14007a865  mov     rax, rcx
0x14007a868  jmp     short loc_14007A8B6
0x14007a86a  lea     rax, [rbp+var_38]
0x14007a86e  mov     r8, rdx
0x14007a871  mov     [rsp+78h+var_40], rax
0x14007a876  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14007a87a  mov     [rsp+78h+var_48], r12
0x14007a87f  mov     r9d, edi
0x14007a882  mov     dword ptr [rsp+78h+var_50], r12d
0x14007a887  xor     edx, edx
0x14007a889  mov     ecx, r10d
0x14007a88c  mov     [rsp+78h+var_58], r12
0x14007a891  call    __acrt_WideCharToMultiByte
0x14007a896  cdqe
0x14007a898  test    rax, rax
0x14007a89b  jz      short loc_14007A8A8
0x14007a89d  cmp     [rbp+var_38], r12d
0x14007a8a1  jnz     short loc_14007A8A8
0x14007a8a3  dec     rax
0x14007a8a6  jmp     short loc_14007A8B6
0x14007a8a8  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x14007a8af  mov     byte ptr [rbx+30h], 1
0x14007a8b3  mov     rax, rdi
0x14007a8b6  mov     rcx, [rbp+var_18]
0x14007a8ba  xor     rcx, rsp; StackCookie
0x14007a8bd  call    __security_check_cookie
0x14007a8c2  add     rsp, 78h
0x14007a8c6  pop     r15
0x14007a8c8  pop     r14
0x14007a8ca  pop     r13
0x14007a8cc  pop     r12
0x14007a8ce  pop     rdi
0x14007a8cf  pop     rsi
0x14007a8d0  pop     rbx
0x14007a8d1  pop     rbp
0x14007a8d2  retn
```
