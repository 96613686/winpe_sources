# ABO_NODE::AddChildNode(ABO_NODE *)

- ea: `0x180006b78`
- end: `0x180006ca1`
- name: `?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z`
- size: `297`
- prototype: `int(ABO_NODE *__hidden this, struct ABO_NODE *)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004f98`
- `0x180007148`
- `0x180008050`
- `0x180010880`
- `0x180011dd0`
- `0x180012cb0`
- `0x180014b90`
- `0x1800259c0`
- `0x18002ac00`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180005e94`
- `0x180006b78`
- `0x180006ca8`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006c10`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006c67`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006c10`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006c67`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006c38`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006c38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006bc4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006bc4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006c74`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006c74`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c57`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c57`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006c28`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006c46`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006c28`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006c46`

## pseudocode

```c
__int64 __fastcall ABO_NODE::AddChildNode(ABO_NODE *this, struct ABO_NODE *a2)
{
  unsigned int v4; // r8d
  int v5; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // rax
  _BYTE v10[64]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v11[256]; // [rsp+60h] [rbp-218h] BYREF

  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v10, v11, 0x100u);
  if ( a2 )
  {
    v5 = INDEXED_ARRAY_LIST::AddEntry((ABO_NODE *)((char *)this + 24), a2, v4);
    if ( v5 >= 0 )
    {
      ABO_NODE::ReferenceAboNode(a2);
      *((_QWORD *)a2 + 2) = this;
      Str = STRU::QueryStr((ABO_NODE *)((char *)this + 256));
      v5 = STRU::Copy((STRU *)v10, Str);
      if ( v5 >= 0 )
      {
        v5 = STRU::Append((STRU *)v10, L"/");
        if ( v5 >= 0 )
        {
          v7 = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
          v5 = STRU::Append((STRU *)v10, v7);
          if ( v5 >= 0 )
          {
            v8 = STRU::QueryStr((STRU *)v10);
            v5 = STRU::Copy((struct ABO_NODE *)((char *)a2 + 256), v8);
          }
        }
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006b78  mov     [rsp+arg_10], rbx
0x180006b7d  mov     [rsp+arg_18], rsi
0x180006b82  push    rdi
0x180006b83  sub     rsp, 270h
0x180006b8a  mov     rax, cs:__security_cookie
0x180006b91  xor     rax, rsp
0x180006b94  mov     [rsp+278h+var_18], rax
0x180006b9c  mov     rdi, rdx
0x180006b9f  mov     rsi, rcx
0x180006ba2  xor     edx, edx; Val
0x180006ba4  lea     rcx, [rsp+278h+var_218]; void *
0x180006ba9  mov     r8d, 200h; Size
0x180006baf  call    memset_0
0x180006bb4  mov     r8d, 100h
0x180006bba  lea     rdx, [rsp+278h+var_218]
0x180006bbf  lea     rcx, [rsp+278h+var_258]
0x180006bc4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180006bca  test    rdi, rdi
0x180006bcd  jnz     short loc_180006BD9
0x180006bcf  mov     ebx, 80070057h
0x180006bd4  jmp     loc_180006C6F
0x180006bd9  lea     rcx, [rsi+18h]; this
0x180006bdd  mov     rdx, rdi; struct IIndexedArrayListEntry *
0x180006be0  call    ?AddEntry@INDEXED_ARRAY_LIST@@QEAAJPEAVIIndexedArrayListEntry@@K@Z; INDEXED_ARRAY_LIST::AddEntry(IIndexedArrayListEntry *,ulong)
0x180006be5  mov     ebx, eax
0x180006be7  test    eax, eax
0x180006be9  js      loc_180006C6F
0x180006bef  mov     rcx, rdi; this
0x180006bf2  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180006bf7  lea     rcx, [rsi+100h]
0x180006bfe  mov     [rdi+10h], rsi
0x180006c02  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006c08  mov     rdx, rax
0x180006c0b  lea     rcx, [rsp+278h+var_258]
0x180006c10  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006c16  mov     ebx, eax
0x180006c18  test    eax, eax
0x180006c1a  js      short loc_180006C6F
0x180006c1c  lea     rdx, asc_18002E8E8; "/"
0x180006c23  lea     rcx, [rsp+278h+var_258]
0x180006c28  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006c2e  mov     ebx, eax
0x180006c30  test    eax, eax
0x180006c32  js      short loc_180006C6F
0x180006c34  lea     rcx, [rdi+38h]
0x180006c38  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180006c3e  mov     rdx, rax
0x180006c41  lea     rcx, [rsp+278h+var_258]
0x180006c46  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006c4c  mov     ebx, eax
0x180006c4e  test    eax, eax
0x180006c50  js      short loc_180006C6F
0x180006c52  lea     rcx, [rsp+278h+var_258]
0x180006c57  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006c5d  mov     rdx, rax
0x180006c60  lea     rcx, [rdi+100h]
0x180006c67  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006c6d  mov     ebx, eax
0x180006c6f  lea     rcx, [rsp+278h+var_258]
0x180006c74  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006c7a  mov     eax, ebx
0x180006c7c  mov     rcx, [rsp+278h+var_18]
0x180006c84  xor     rcx, rsp; StackCookie
0x180006c87  call    __security_check_cookie
0x180006c8c  lea     r11, [rsp+278h+var_8]
0x180006c94  mov     rbx, [r11+20h]
0x180006c98  mov     rsi, [r11+28h]
0x180006c9c  mov     rsp, r11
0x180006c9f  pop     rdi
0x180006ca0  retn
```
