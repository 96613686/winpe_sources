# META_SCRIPT_ENTRY::Parse(ushort const *)

- ea: `0x18001cfe8`
- end: `0x18001d18a`
- name: `?Parse@META_SCRIPT_ENTRY@@QEAAJPEBG@Z`
- size: `418`
- prototype: `__int64 __fastcall(META_SCRIPT_ENTRY *__hidden this, wchar_t *Str)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180024a10`

## callees

- `0x18001cfe8`
- `0x180026a60`

## import_xrefs

- `msvcrt!wcschr` at `0x18001d045`
- `msvcrt!wcschr` at `0x18001d06c`
- `msvcrt!wcschr` at `0x18001d099`
- `msvcrt!wcschr` at `0x18001d045`
- `msvcrt!wcschr` at `0x18001d06c`
- `msvcrt!wcschr` at `0x18001d099`
- `msvcrt!wcstoul` at `0x18001d088`
- `msvcrt!wcstoul` at `0x18001d088`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d0d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d14c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d16f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d0d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d14c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d16f`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d018`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d025`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d02e`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d018`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d025`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d02e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d0f9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d0f9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d0e6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d0e6`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d15b`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d15b`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_ENTRY::Parse(META_SCRIPT_ENTRY *this, wchar_t *Str)
{
  int v4; // ebx
  STRU *v5; // rbp
  wchar_t *v6; // rax
  const WCHAR *v7; // r15
  wchar_t *v8; // rax
  const wchar_t *v9; // rbx
  unsigned int v10; // r13d
  wchar_t *v11; // rax
  const unsigned __int16 *v12; // r12
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  int v15; // r8d
  bool v16; // zf

  if ( Str )
  {
    v5 = (META_SCRIPT_ENTRY *)((char *)this + 56);
    STRU::Reset((META_SCRIPT_ENTRY *)((char *)this + 56));
    STRU::Reset((META_SCRIPT_ENTRY *)((char *)this + 112));
    STRU::Reset(this);
    *((_QWORD *)this + 21) = 0;
    v6 = wcschr(Str, 0x2Cu);
    if ( v6 && (v7 = v6 + 1, *v6 = 0, v6 != (wchar_t *)-2LL) && (v8 = wcschr(v6 + 1, 0x2Cu)) != 0 )
    {
      *v8 = 0;
      v9 = v8 + 1;
      v10 = wcstoul(v8 + 1, 0, 10);
      v11 = wcschr(v9, 0x2Cu);
      if ( v11 )
      {
        *v11 = 0;
        v12 = v11 + 1;
      }
      else
      {
        v13 = -1;
        do
          ++v13;
        while ( v9[v13] );
        v12 = &v9[v13];
      }
      if ( *Str != 46 || (v4 = STRU::Copy((META_SCRIPT_ENTRY *)((char *)this + 112), L"*"), v4 >= 0) )
      {
        v4 = STRU::Append((META_SCRIPT_ENTRY *)((char *)this + 112), Str);
        if ( v4 >= 0 )
        {
          v14 = STRU::QueryStr((META_SCRIPT_ENTRY *)((char *)this + 112));
          v15 = *v14 - 42;
          if ( *v14 == 42 )
            v15 = v14[1];
          if ( !v15 )
            *((_DWORD *)this + 43) = 1;
          v4 = ExpandEnvironmentVariables(v7, this);
          if ( v4 >= 0 )
          {
            v16 = *((_DWORD *)this + 43) == 0;
            *((_DWORD *)this + 42) = v10;
            if ( !v16 || (v4 = STRU::Copy(v5, v12), v4 >= 0) )
            {
              if ( STRU::IsEmpty(v5) )
                return (unsigned int)STRU::Copy(v5, L"*");
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024883;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001cfe8  push    rbx
0x18001cfea  push    rbp
0x18001cfeb  push    rsi
0x18001cfec  push    rdi
0x18001cfed  push    r12
0x18001cfef  push    r13
0x18001cff1  push    r14
0x18001cff3  push    r15
0x18001cff5  sub     rsp, 28h
0x18001cff9  xor     r12d, r12d
0x18001cffc  mov     rsi, rdx
0x18001cfff  mov     rdi, rcx
0x18001d002  test    rdx, rdx
0x18001d005  jnz     short loc_18001D011
0x18001d007  mov     ebx, 80070057h
0x18001d00c  jmp     loc_18001D177
0x18001d011  lea     rbp, [rcx+38h]
0x18001d015  mov     rcx, rbp
0x18001d018  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d01e  lea     r14, [rdi+70h]
0x18001d022  mov     rcx, r14
0x18001d025  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d02b  mov     rcx, rdi
0x18001d02e  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d034  mov     ebx, 2Ch ; ','
0x18001d039  mov     [rdi+0A8h], r12
0x18001d040  mov     edx, ebx; Ch
0x18001d042  mov     rcx, rsi; Str
0x18001d045  call    cs:__imp_wcschr
0x18001d04b  test    rax, rax
0x18001d04e  jnz     short loc_18001D05A
0x18001d050  mov     ebx, 8007000Dh
0x18001d055  jmp     loc_18001D177
0x18001d05a  lea     r15, [rax+2]
0x18001d05e  mov     [rax], r12w
0x18001d062  test    r15, r15
0x18001d065  jz      short loc_18001D050
0x18001d067  mov     edx, ebx; Ch
0x18001d069  mov     rcx, r15; Str
0x18001d06c  call    cs:__imp_wcschr
0x18001d072  test    rax, rax
0x18001d075  jz      short loc_18001D050
0x18001d077  xor     edx, edx; EndPtr
0x18001d079  mov     [rax], r12w
0x18001d07d  lea     rbx, [rax+2]
0x18001d081  mov     rcx, rbx; String
0x18001d084  lea     r8d, [rdx+0Ah]; Radix
0x18001d088  call    cs:__imp_wcstoul
0x18001d08e  mov     edx, 2Ch ; ','; Ch
0x18001d093  mov     rcx, rbx; Str
0x18001d096  mov     r13d, eax
0x18001d099  call    cs:__imp_wcschr
0x18001d09f  test    rax, rax
0x18001d0a2  jz      short loc_18001D0AE
0x18001d0a4  mov     [rax], r12w
0x18001d0a8  lea     r12, [rax+2]
0x18001d0ac  jmp     short loc_18001D0C0
0x18001d0ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d0b2  inc     rax
0x18001d0b5  cmp     [rbx+rax*2], r12w
0x18001d0ba  jnz     short loc_18001D0B2
0x18001d0bc  lea     r12, [rbx+rax*2]
0x18001d0c0  cmp     word ptr [rsi], 2Eh ; '.'
0x18001d0c4  jnz     short loc_18001D0E0
0x18001d0c6  lea     rdx, asc_180034228; "*"
0x18001d0cd  mov     rcx, r14
0x18001d0d0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d0d6  mov     ebx, eax
0x18001d0d8  test    eax, eax
0x18001d0da  js      loc_18001D177
0x18001d0e0  mov     rdx, rsi
0x18001d0e3  mov     rcx, r14
0x18001d0e6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001d0ec  mov     ebx, eax
0x18001d0ee  test    eax, eax
0x18001d0f0  js      loc_18001D177
0x18001d0f6  mov     rcx, r14
0x18001d0f9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d0ff  movzx   r8d, word ptr [rax]
0x18001d103  sub     r8d, 2Ah ; '*'
0x18001d107  jnz     short loc_18001D116
0x18001d109  movzx   r8d, word ptr [rax+2]
0x18001d10e  xor     eax, eax
0x18001d110  movzx   edx, ax
0x18001d113  sub     r8d, edx
0x18001d116  test    r8d, r8d
0x18001d119  jnz     short loc_18001D125
0x18001d11b  mov     dword ptr [rdi+0ACh], 1
0x18001d125  mov     rdx, rdi; struct STRU *
0x18001d128  mov     rcx, r15; lpSrc
0x18001d12b  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x18001d130  mov     ebx, eax
0x18001d132  test    eax, eax
0x18001d134  js      short loc_18001D177
0x18001d136  cmp     dword ptr [rdi+0ACh], 0
0x18001d13d  mov     [rdi+0A8h], r13d
0x18001d144  jnz     short loc_18001D158
0x18001d146  mov     rdx, r12
0x18001d149  mov     rcx, rbp
0x18001d14c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d152  mov     ebx, eax
0x18001d154  test    eax, eax
0x18001d156  js      short loc_18001D177
0x18001d158  mov     rcx, rbp
0x18001d15b  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18001d161  test    al, al
0x18001d163  jz      short loc_18001D177
0x18001d165  lea     rdx, asc_180034228; "*"
0x18001d16c  mov     rcx, rbp
0x18001d16f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d175  mov     ebx, eax
0x18001d177  mov     eax, ebx
0x18001d179  add     rsp, 28h
0x18001d17d  pop     r15
0x18001d17f  pop     r14
0x18001d181  pop     r13
0x18001d183  pop     r12
0x18001d185  pop     rdi
0x18001d186  pop     rsi
0x18001d187  pop     rbp
0x18001d188  pop     rbx
0x18001d189  retn
```
