# ABO_WRAPPER::FindInheritedAboNode(ABO_TREE *,ushort const *,ABO_NODE * *)

- ea: `0x18000d5d8`
- end: `0x18000d799`
- name: `?FindInheritedAboNode@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGPEAPEAVABO_NODE@@@Z`
- size: `449`
- prototype: `int(ABO_WRAPPER *__hidden this, struct ABO_TREE *, const unsigned __int16 *, struct ABO_NODE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e3e0`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180007ac8`
- `0x18000d5d8`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000d6e1`
- `msvcrt!wcsrchr` at `0x18000d6e1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d67c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d735`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d67c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d735`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d62a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d653`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d62a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d653`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d769`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d774`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d769`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d774`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d691`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6aa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6d5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6f4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d705`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d727`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d691`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6aa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6d5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6f4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d705`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d727`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000d746`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000d746`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000d716`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000d716`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::FindInheritedAboNode(
        ABO_WRAPPER *this,
        struct ABO_TREE *a2,
        const unsigned __int16 *a3,
        struct ABO_NODE **a4)
{
  int v7; // ebx
  const unsigned __int16 *Str; // rax
  ABO_NODE *v9; // rbx
  const unsigned __int16 *v10; // rax
  int v11; // eax
  _BYTE v13[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v15[248]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v16[248]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(v15, 0, 0x1EAu);
  STRU::STRU((STRU *)v14, v15, 0xF5u);
  memset_0(v16, 0, 0x1EAu);
  STRU::STRU((STRU *)v13, v16, 0xF5u);
  if ( a2 && a3 && a4 )
  {
    v7 = STRU::Copy((STRU *)v14, a3);
    if ( v7 >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v14);
      v11 = STRU::Copy((STRU *)v13, Str);
      v7 = v11;
      if ( v11 >= 0 && !STRU::IsEmpty((STRU *)v13) )
      {
        v9 = (ABO_NODE *)*((_QWORD *)a2 + 2);
        v10 = STRU::QueryStr((STRU *)v13);
        ABO_NODE::FindNode(v9, v10, a4);
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  STRU::~STRU((STRU *)v13);
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d5d8  push    rbp
0x18000d5da  push    rbx
0x18000d5db  push    rsi
0x18000d5dc  push    rdi
0x18000d5dd  push    r14
0x18000d5df  lea     rbp, [rsp-380h]
0x18000d5e7  sub     rsp, 480h
0x18000d5ee  mov     rax, cs:__security_cookie
0x18000d5f5  xor     rax, rsp
0x18000d5f8  mov     [rbp+3A0h+var_30], rax
0x18000d5ff  mov     rbx, r8
0x18000d602  lea     rcx, [rbp+3A0h+var_410]; void *
0x18000d606  mov     r14, rdx
0x18000d609  mov     r8d, 1EAh; Size
0x18000d60f  xor     edx, edx; Val
0x18000d611  mov     rsi, r9
0x18000d614  call    memset_0
0x18000d619  mov     edi, 0F5h
0x18000d61e  lea     rdx, [rbp+3A0h+var_410]
0x18000d622  mov     r8d, edi
0x18000d625  lea     rcx, [rsp+4A0h+var_448]
0x18000d62a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d630  xor     edx, edx; Val
0x18000d632  lea     rcx, [rbp+3A0h+var_220]; void *
0x18000d639  mov     r8d, 1EAh; Size
0x18000d63f  call    memset_0
0x18000d644  mov     r8d, edi
0x18000d647  lea     rdx, [rbp+3A0h+var_220]
0x18000d64e  lea     rcx, [rsp+4A0h+var_480]
0x18000d653  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d659  test    r14, r14
0x18000d65c  jz      loc_18000D75F
0x18000d662  test    rbx, rbx
0x18000d665  jz      loc_18000D75F
0x18000d66b  test    rsi, rsi
0x18000d66e  jz      loc_18000D75F
0x18000d674  mov     rdx, rbx
0x18000d677  lea     rcx, [rsp+4A0h+var_448]
0x18000d67c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d682  mov     ebx, eax
0x18000d684  test    eax, eax
0x18000d686  js      loc_18000D764
0x18000d68c  lea     rcx, [rsp+4A0h+var_448]
0x18000d691  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d697  lea     rcx, [rsp+4A0h+var_480]
0x18000d69c  jmp     loc_18000D732
0x18000d6a1  mov     rbx, [r14+10h]
0x18000d6a5  lea     rcx, [rsp+4A0h+var_480]
0x18000d6aa  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d6b0  mov     r8, rsi; struct ABO_NODE **
0x18000d6b3  mov     rcx, rbx; this
0x18000d6b6  mov     rdx, rax; unsigned __int16 *
0x18000d6b9  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000d6be  mov     ebx, eax
0x18000d6c0  cmp     eax, 80070003h
0x18000d6c5  jnz     loc_18000D764
0x18000d6cb  lea     rcx, [rsp+4A0h+var_448]
0x18000d6d0  mov     edi, 2Fh ; '/'
0x18000d6d5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d6db  mov     rcx, rax; Str
0x18000d6de  movzx   edx, di; Ch
0x18000d6e1  call    cs:__imp_wcsrchr
0x18000d6e7  mov     rdi, rax
0x18000d6ea  test    rax, rax
0x18000d6ed  jz      short loc_18000D756
0x18000d6ef  lea     rcx, [rsp+4A0h+var_448]
0x18000d6f4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d6fa  sub     rdi, rax
0x18000d6fd  lea     rcx, [rsp+4A0h+var_448]
0x18000d702  sar     rdi, 1
0x18000d705  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d70b  mov     r8d, edi
0x18000d70e  lea     rcx, [rsp+4A0h+var_480]
0x18000d713  mov     rdx, rax
0x18000d716  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000d71c  mov     ebx, eax
0x18000d71e  test    eax, eax
0x18000d720  js      short loc_18000D764
0x18000d722  lea     rcx, [rsp+4A0h+var_480]
0x18000d727  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d72d  lea     rcx, [rsp+4A0h+var_448]
0x18000d732  mov     rdx, rax
0x18000d735  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d73b  mov     ebx, eax
0x18000d73d  test    eax, eax
0x18000d73f  js      short loc_18000D764
0x18000d741  lea     rcx, [rsp+4A0h+var_480]
0x18000d746  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000d74c  test    al, al
0x18000d74e  jz      loc_18000D6A1
0x18000d754  jmp     short loc_18000D764
0x18000d756  mov     rax, [r14+10h]
0x18000d75a  mov     [rsi], rax
0x18000d75d  jmp     short loc_18000D764
0x18000d75f  mov     ebx, 80070057h
0x18000d764  lea     rcx, [rsp+4A0h+var_480]
0x18000d769  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d76f  lea     rcx, [rsp+4A0h+var_448]
0x18000d774  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d77a  mov     eax, ebx
0x18000d77c  mov     rcx, [rbp+3A0h+var_30]
0x18000d783  xor     rcx, rsp; StackCookie
0x18000d786  call    __security_check_cookie
0x18000d78b  add     rsp, 480h
0x18000d792  pop     r14
0x18000d794  pop     rdi
0x18000d795  pop     rsi
0x18000d796  pop     rbx
0x18000d797  pop     rbp
0x18000d798  retn
```
