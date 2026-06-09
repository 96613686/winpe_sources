# ABO_TREE::PopulateSiteNodeTable(SITE_NODE_TABLE *)

- ea: `0x180005cf4`
- end: `0x180005e8d`
- name: `?PopulateSiteNodeTable@ABO_TREE@@AEAAJPEAVSITE_NODE_TABLE@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(ABO_TREE *__hidden this, struct SITE_NODE_TABLE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180004b80`

## callees

- `0x180002990`
- `0x1800029d0`
- `0x180003460`
- `0x180004398`
- `0x18000473c`
- `0x180005cf4`
- `0x180005e94`
- `0x180007ac8`
- `0x180008bf8`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005de3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005de3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e64`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e64`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005d78`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005d78`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005dd6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005dd6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d27`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005dc3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005d27`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005dc3`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180005e05`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180005e05`

## pseudocode

```c
__int64 __fastcall ABO_TREE::PopulateSiteNodeTable(ABO_NODE **this, struct SITE_NODE_TABLE *a2)
{
  ABO_NODE *v5; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v6[56]; // [rsp+28h] [rbp-70h] BYREF

  v5 = 0;
  STRU::STRU((STRU *)v6);
  if ( a2 )
    ABO_NODE::FindNode(this[2], L"LM/W3SVC", &v5);
  STRU::~STRU((STRU *)v6);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180005cf4  mov     [rsp+arg_10], rbx
0x180005cf9  push    rbp
0x180005cfa  push    rsi
0x180005cfb  push    rdi
0x180005cfc  push    r14
0x180005cfe  push    r15
0x180005d00  sub     rsp, 70h
0x180005d04  mov     rax, cs:__security_cookie
0x180005d0b  xor     rax, rsp
0x180005d0e  mov     [rsp+98h+var_38], rax
0x180005d13  mov     rbx, rcx
0x180005d16  mov     [rsp+98h+var_78], 0
0x180005d1f  lea     rcx, [rsp+98h+var_70]
0x180005d24  mov     r15, rdx
0x180005d27  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005d2d  test    r15, r15
0x180005d30  jnz     short loc_180005D3C
0x180005d32  mov     ebx, 80070057h
0x180005d37  jmp     loc_180005E5F
0x180005d3c  mov     rcx, [rbx+10h]; this
0x180005d40  lea     r8, [rsp+98h+var_78]; struct ABO_NODE **
0x180005d45  lea     rdx, aLmW3svc; "LM/W3SVC"
0x180005d4c  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x180005d51  mov     rsi, [rsp+98h+var_78]
0x180005d56  mov     ebx, eax
0x180005d58  test    eax, eax
0x180005d5a  js      loc_180005E52
0x180005d60  xor     ebp, ebp
0x180005d62  cmp     [rsi+28h], ebp
0x180005d65  jbe     loc_180005E52
0x180005d6b  mov     rax, [rsi+20h]
0x180005d6f  lea     rcx, [rsp+98h+var_70]
0x180005d74  mov     r14, [rax+rbp*8]
0x180005d78  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180005d7e  lea     r8, [rsp+98h+var_70]; struct STRU *
0x180005d83  mov     rcx, r14; this
0x180005d86  call    ?GetAttributeValue@ABO_NODE@@QEAAJPEBGPEAVSTRU@@@Z; ABO_NODE::GetAttributeValue(ushort const *,STRU *)
0x180005d8b  mov     ebx, eax
0x180005d8d  test    eax, eax
0x180005d8f  jns     short loc_180005DA3
0x180005d91  cmp     eax, 80070002h
0x180005d96  jnz     loc_180005E52
0x180005d9c  xor     ebx, ebx
0x180005d9e  jmp     loc_180005E24
0x180005da3  mov     ecx, 48h ; 'H'; Size
0x180005da8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005dad  mov     rdi, rax
0x180005db0  test    rax, rax
0x180005db3  jz      loc_180005E4D
0x180005db9  lea     rcx, [rax+8]
0x180005dbd  mov     dword ptr [rax], 1
0x180005dc3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005dc9  lea     rcx, [rsp+98h+var_70]
0x180005dce  mov     qword ptr [rdi+40h], 0
0x180005dd6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005ddc  mov     rdx, rax
0x180005ddf  lea     rcx, [rdi+8]
0x180005de3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005de9  mov     ebx, eax
0x180005deb  test    eax, eax
0x180005ded  js      short loc_180005E36
0x180005def  mov     rcx, r14; this
0x180005df2  mov     [rdi+40h], r14
0x180005df6  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180005dfb  lea     rcx, [r15+8]
0x180005dff  xor     r8d, r8d
0x180005e02  mov     rdx, rdi
0x180005e05  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180005e0b  test    eax, eax
0x180005e0d  js      short loc_180005E31
0x180005e0f  add     dword ptr [rdi], 0FFFFFFFFh
0x180005e12  jnz     short loc_180005E24
0x180005e14  mov     rcx, rdi; this
0x180005e17  call    ??1SITE_NODE_TABLE_ENTRY@@QEAA@XZ; SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(void)
0x180005e1c  mov     rcx, rdi; Block
0x180005e1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e24  inc     ebp
0x180005e26  cmp     ebp, [rsi+28h]
0x180005e29  jb      loc_180005D6B
0x180005e2f  jmp     short loc_180005E52
0x180005e31  mov     ebx, 80004005h
0x180005e36  add     dword ptr [rdi], 0FFFFFFFFh
0x180005e39  jnz     short loc_180005E52
0x180005e3b  mov     rcx, rdi; this
0x180005e3e  call    ??1SITE_NODE_TABLE_ENTRY@@QEAA@XZ; SITE_NODE_TABLE_ENTRY::~SITE_NODE_TABLE_ENTRY(void)
0x180005e43  mov     rcx, rdi; Block
0x180005e46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e4b  jmp     short loc_180005E52
0x180005e4d  mov     ebx, 80070008h
0x180005e52  test    rsi, rsi
0x180005e55  jz      short loc_180005E5F
0x180005e57  mov     rcx, rsi; this
0x180005e5a  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180005e5f  lea     rcx, [rsp+98h+var_70]
0x180005e64  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e6a  mov     eax, ebx
0x180005e6c  mov     rcx, [rsp+98h+var_38]
0x180005e71  xor     rcx, rsp; StackCookie
0x180005e74  call    __security_check_cookie
0x180005e79  mov     rbx, [rsp+98h+arg_10]
0x180005e81  add     rsp, 70h
0x180005e85  pop     r15
0x180005e87  pop     r14
0x180005e89  pop     rdi
0x180005e8a  pop     rsi
0x180005e8b  pop     rbp
0x180005e8c  retn
```
