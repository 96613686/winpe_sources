# GetLastNodePath(ushort const *,ABO_NODE *,STRU *)

- ea: `0x180026cdc`
- end: `0x180026f58`
- name: `?GetLastNodePath@@YAJPEBGPEAVABO_NODE@@PEAVSTRU@@@Z`
- size: `636`
- prototype: `int(const unsigned __int16 *, struct ABO_NODE *, struct STRU *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d040`
- `0x18000d8f0`
- `0x18000dea0`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x180005e94`
- `0x180026cdc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026ea1`
- `msvcrt!_wcsicmp` at `0x180026ea1`
- `msvcrt!wcschr` at `0x180026dc9`
- `msvcrt!wcschr` at `0x180026dc9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026da2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e15`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e33`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026ecc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026da2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e15`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e33`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026e5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026ecc`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180026e95`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180026e95`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d3a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d60`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d85`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d3a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d60`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180026d85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ee0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026eeb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ef6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ee0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026eeb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ef6`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180026e6c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180026e6c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026dbc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026ddc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026df0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e4d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e80`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026ec0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026dbc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026ddc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026df0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e4d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026e80`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026ec0`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026f45`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026f45`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180026e01`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180026e01`

## pseudocode

```c
__int64 __fastcall GetLastNodePath(const unsigned __int16 *a1, struct ABO_NODE *a2, struct STRU *a3)
{
  const unsigned __int16 *v6; // rdx
  int v7; // esi
  const wchar_t *Str; // rax
  wchar_t *v9; // rax
  wchar_t *v10; // r14
  __int64 v11; // rbx
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rax
  __int64 v15; // r14
  const wchar_t *v16; // rbx
  const wchar_t *v17; // rax
  const unsigned __int16 *v18; // rax
  _BYTE v20[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v23[248]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v24[248]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v25[248]; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset_0(v23, 0, 0x1EAu);
  STRU::STRU((STRU *)v20, v23, 0xF5u);
  memset_0(v24, 0, 0x1EAu);
  STRU::STRU((STRU *)v21, v24, 0xF5u);
  memset_0(v25, 0, 0x1EAu);
  STRU::STRU((STRU *)v22, v25, 0xF5u);
  v6 = a1 + 1;
  if ( *a1 != 47 )
    v6 = a1;
  v7 = STRU::Copy((STRU *)v20, v6);
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      ABO_NODE::ReferenceAboNode(a2);
      if ( STRU::IsEmpty((STRU *)v20) )
        break;
      Str = STRU::QueryStr((STRU *)v20);
      v9 = wcschr(Str, 0x2Fu);
      v10 = v9;
      if ( v9 )
      {
        v11 = v9 - STRU::QueryStr((STRU *)v20);
        v12 = STRU::QueryStr((STRU *)v20);
        v7 = STRU::Copy((STRU *)v21, v12, v11);
        if ( v7 < 0
          || (v7 = STRU::Copy((STRU *)v22, v10 + 1), v7 < 0)
          || (v13 = STRU::QueryStr((STRU *)v22), v7 = STRU::Copy((STRU *)v20, v13), v7 < 0) )
        {
LABEL_9:
          if ( !a2 )
            goto LABEL_19;
          goto LABEL_18;
        }
      }
      else
      {
        v14 = STRU::QueryStr((STRU *)v20);
        v7 = STRU::Copy((STRU *)v21, v14);
        if ( v7 < 0 )
          goto LABEL_9;
        STRU::Reset((STRU *)v20);
      }
      v15 = 0;
      if ( !*((_DWORD *)a2 + 10) )
        break;
      while ( 1 )
      {
        v16 = STRU::QueryStr((STRU *)v21);
        v17 = STRU::QueryStr((STRU *)(*(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * v15) + 56LL));
        if ( !_wcsicmp(v17, v16) )
          break;
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *((_DWORD *)a2 + 10) )
          goto LABEL_16;
      }
      ABO_NODE::DereferenceAboNode(a2);
      a2 = *(struct ABO_NODE **)(*((_QWORD *)a2 + 4) + 8 * v15);
    }
LABEL_16:
    if ( !a2 )
      goto LABEL_19;
    v18 = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 256));
    v7 = STRU::Copy(a3, v18);
LABEL_18:
    ABO_NODE::DereferenceAboNode(a2);
  }
LABEL_19:
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026cdc  mov     [rsp-8+arg_18], rbx
0x180026ce1  push    rbp
0x180026ce2  push    rsi
0x180026ce3  push    rdi
0x180026ce4  push    r12
0x180026ce6  push    r13
0x180026ce8  push    r14
0x180026cea  push    r15
0x180026cec  lea     rbp, [rsp-5B0h]
0x180026cf4  sub     rsp, 6B0h
0x180026cfb  mov     rax, cs:__security_cookie
0x180026d02  xor     rax, rsp
0x180026d05  mov     [rbp+5E0h+var_40], rax
0x180026d0c  mov     r12, r8
0x180026d0f  mov     rdi, rdx
0x180026d12  mov     rbx, rcx
0x180026d15  mov     r14d, 1EAh
0x180026d1b  mov     r8d, r14d; Size
0x180026d1e  lea     rcx, [rbp+5E0h+var_610]; void *
0x180026d22  xor     edx, edx; Val
0x180026d24  call    memset_0
0x180026d29  mov     esi, 0F5h
0x180026d2e  lea     rdx, [rbp+5E0h+var_610]
0x180026d32  mov     r8d, esi
0x180026d35  lea     rcx, [rsp+6E0h+var_6C0]
0x180026d3a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026d40  mov     r8d, r14d; Size
0x180026d43  lea     rcx, [rbp+5E0h+var_420]; void *
0x180026d4a  xor     edx, edx; Val
0x180026d4c  call    memset_0
0x180026d51  mov     r8d, esi
0x180026d54  lea     rdx, [rbp+5E0h+var_420]
0x180026d5b  lea     rcx, [rsp+6E0h+var_688]
0x180026d60  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026d66  mov     r8d, r14d; Size
0x180026d69  lea     rcx, [rbp+5E0h+var_230]; void *
0x180026d70  xor     edx, edx; Val
0x180026d72  call    memset_0
0x180026d77  mov     r8d, esi
0x180026d7a  lea     rdx, [rbp+5E0h+var_230]
0x180026d81  lea     rcx, [rbp+5E0h+var_650]
0x180026d85  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180026d8b  mov     r13d, 2Fh ; '/'
0x180026d91  lea     rdx, [rbx+2]
0x180026d95  cmp     [rbx], r13w
0x180026d99  lea     rcx, [rsp+6E0h+var_6C0]
0x180026d9e  cmovnz  rdx, rbx
0x180026da2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026da8  mov     esi, eax
0x180026daa  test    eax, eax
0x180026dac  js      loc_180026EDC
0x180026db2  jmp     loc_180026F38
0x180026db7  lea     rcx, [rsp+6E0h+var_6C0]
0x180026dbc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026dc2  mov     rcx, rax; Str
0x180026dc5  movzx   edx, r13w; Ch
0x180026dc9  call    cs:__imp_wcschr
0x180026dcf  lea     rcx, [rsp+6E0h+var_6C0]
0x180026dd4  mov     r14, rax
0x180026dd7  test    rax, rax
0x180026dda  jz      short loc_180026E4D
0x180026ddc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026de2  mov     rbx, r14
0x180026de5  lea     rcx, [rsp+6E0h+var_6C0]
0x180026dea  sub     rbx, rax
0x180026ded  sar     rbx, 1
0x180026df0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026df6  mov     r8d, ebx
0x180026df9  lea     rcx, [rsp+6E0h+var_688]
0x180026dfe  mov     rdx, rax
0x180026e01  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180026e07  mov     esi, eax
0x180026e09  test    eax, eax
0x180026e0b  js      short loc_180026E3F
0x180026e0d  lea     rdx, [r14+2]
0x180026e11  lea     rcx, [rbp+5E0h+var_650]
0x180026e15  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026e1b  mov     esi, eax
0x180026e1d  test    eax, eax
0x180026e1f  js      short loc_180026E3F
0x180026e21  lea     rcx, [rbp+5E0h+var_650]
0x180026e25  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026e2b  mov     rdx, rax
0x180026e2e  lea     rcx, [rsp+6E0h+var_6C0]
0x180026e33  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026e39  mov     esi, eax
0x180026e3b  test    eax, eax
0x180026e3d  jns     short loc_180026E72
0x180026e3f  test    rdi, rdi
0x180026e42  jz      loc_180026EDC
0x180026e48  jmp     loc_180026ED4
0x180026e4d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026e53  mov     rdx, rax
0x180026e56  lea     rcx, [rsp+6E0h+var_688]
0x180026e5b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026e61  mov     esi, eax
0x180026e63  test    eax, eax
0x180026e65  js      short loc_180026E3F
0x180026e67  lea     rcx, [rsp+6E0h+var_6C0]
0x180026e6c  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180026e72  xor     r14d, r14d
0x180026e75  cmp     [rdi+28h], r14d
0x180026e79  jbe     short loc_180026EB4
0x180026e7b  lea     rcx, [rsp+6E0h+var_688]
0x180026e80  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026e86  mov     rcx, [rdi+20h]
0x180026e8a  mov     rbx, rax
0x180026e8d  mov     rcx, [rcx+r14*8]
0x180026e91  add     rcx, 38h ; '8'
0x180026e95  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180026e9b  mov     rcx, rax; String1
0x180026e9e  mov     rdx, rbx; String2
0x180026ea1  call    cs:__imp__wcsicmp
0x180026ea7  test    eax, eax
0x180026ea9  jz      short loc_180026F28
0x180026eab  inc     r14d
0x180026eae  cmp     r14d, [rdi+28h]
0x180026eb2  jb      short loc_180026E7B
0x180026eb4  test    rdi, rdi
0x180026eb7  jz      short loc_180026EDC
0x180026eb9  lea     rcx, [rdi+100h]
0x180026ec0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026ec6  mov     rdx, rax
0x180026ec9  mov     rcx, r12
0x180026ecc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026ed2  mov     esi, eax
0x180026ed4  mov     rcx, rdi; this
0x180026ed7  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180026edc  lea     rcx, [rbp+5E0h+var_650]
0x180026ee0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026ee6  lea     rcx, [rsp+6E0h+var_688]
0x180026eeb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026ef1  lea     rcx, [rsp+6E0h+var_6C0]
0x180026ef6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026efc  mov     eax, esi
0x180026efe  mov     rcx, [rbp+5E0h+var_40]
0x180026f05  xor     rcx, rsp; StackCookie
0x180026f08  call    __security_check_cookie
0x180026f0d  mov     rbx, [rsp+6E0h+arg_18]
0x180026f15  add     rsp, 6B0h
0x180026f1c  pop     r15
0x180026f1e  pop     r14
0x180026f20  pop     r13
0x180026f22  pop     r12
0x180026f24  pop     rdi
0x180026f25  pop     rsi
0x180026f26  pop     rbp
0x180026f27  retn
0x180026f28  mov     rcx, rdi; this
0x180026f2b  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180026f30  mov     rax, [rdi+20h]
0x180026f34  mov     rdi, [rax+r14*8]
0x180026f38  mov     rcx, rdi; this
0x180026f3b  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180026f40  lea     rcx, [rsp+6E0h+var_6C0]
0x180026f45  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180026f4b  test    al, al
0x180026f4d  jz      loc_180026DB7
0x180026f53  jmp     loc_180026EB4
```
