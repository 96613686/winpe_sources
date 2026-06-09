# SITES_CUSTOM_PROVIDER::MapAddKey(ABO_NODE *)

- ea: `0x180013110`
- end: `0x180013286`
- name: `?MapAddKey@SITES_CUSTOM_PROVIDER@@UEAAJPEAVABO_NODE@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(SITES_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000341a`
- `0x180003460`
- `0x1800077dc`
- `0x18000fec4`
- `0x180012718`
- `0x180013110`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800131b8`
- `msvcrt!wcstoul` at `0x1800131b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800131f7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800131f7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800131a4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013207`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800131a4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013207`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013177`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180013177`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013253`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180013253`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013226`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180013226`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013215`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013215`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::MapAddKey(SITES_CUSTOM_PROVIDER *this, struct ABO_NODE *a2)
{
  int Entry; // ebx
  const wchar_t *v5; // rax
  unsigned int v6; // r15d
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v8; // rax
  wchar_t *EndPtr; // [rsp+20h] [rbp-E0h] BYREF
  struct PROPERTY_ENTRY *v11; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[64]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v13[256]; // [rsp+70h] [rbp-90h] BYREF

  EndPtr = 0;
  v11 = 0;
  memset_0(v13, 0, sizeof(v13));
  STRU::STRU((STRU *)v12, v13, 0x100u);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 2) != *((_QWORD *)a2 + 2)
      || (v5 = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56)), v6 = wcstoul(v5, &EndPtr, 10), *EndPtr) )
    {
      Entry = -2147024894;
    }
    else
    {
      Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a2 + 184), 0x3F7u, &v11);
      if ( Entry == -2147024894 )
      {
        Entry = STRU::Copy((STRU *)v12, L"SITE_");
        if ( Entry >= 0 )
        {
          Str = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
          Entry = STRU::Append((STRU *)v12, Str);
          if ( Entry >= 0 )
          {
            v8 = STRU::QueryStr((STRU *)v12);
            Entry = SITES_CUSTOM_PROVIDER::CreateSite(this, a2, v8, v6);
          }
        }
      }
      if ( v11 )
        PROPERTY_MAPPING::DereferencePropertyMapping(v11);
    }
  }
  else
  {
    Entry = -2147024809;
  }
  STRU::~STRU((STRU *)v12);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x180013110  mov     [rsp-8+arg_10], rbx
0x180013115  mov     [rsp-8+arg_18], rsi
0x18001311a  push    rbp
0x18001311b  push    rdi
0x18001311c  push    r12
0x18001311e  push    r14
0x180013120  push    r15
0x180013122  lea     rbp, [rsp-180h]
0x18001312a  sub     rsp, 280h
0x180013131  mov     rax, cs:__security_cookie
0x180013138  xor     rax, rsp
0x18001313b  mov     [rbp+1A0h+var_30], rax
0x180013142  mov     rdi, rdx
0x180013145  mov     rsi, rcx
0x180013148  xor     r12d, r12d
0x18001314b  lea     rcx, [rsp+2A0h+var_230]; void *
0x180013150  xor     edx, edx; Val
0x180013152  mov     [rsp+2A0h+EndPtr], r12
0x180013157  mov     r8d, 200h; Size
0x18001315d  mov     [rsp+2A0h+var_278], r12
0x180013162  call    memset_0
0x180013167  mov     r8d, 100h
0x18001316d  lea     rdx, [rsp+2A0h+var_230]
0x180013172  lea     rcx, [rsp+2A0h+var_270]
0x180013177  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001317d  test    rdi, rdi
0x180013180  jnz     short loc_18001318C
0x180013182  mov     ebx, 80070057h
0x180013187  jmp     loc_18001324E
0x18001318c  mov     rax, [rdi+10h]
0x180013190  cmp     [rsi+10h], rax
0x180013194  jz      short loc_1800131A0
0x180013196  mov     ebx, 80070002h
0x18001319b  jmp     loc_18001324E
0x1800131a0  lea     rcx, [rdi+38h]
0x1800131a4  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800131aa  mov     r8d, 0Ah; Radix
0x1800131b0  lea     rdx, [rsp+2A0h+EndPtr]; EndPtr
0x1800131b5  mov     rcx, rax; String
0x1800131b8  call    cs:__imp_wcstoul
0x1800131be  mov     r15d, eax
0x1800131c1  mov     rax, [rsp+2A0h+EndPtr]
0x1800131c6  cmp     [rax], r12w
0x1800131ca  jnz     short loc_180013196
0x1800131cc  lea     rcx, [rdi+0B8h]; this
0x1800131d3  mov     edx, 3F7h; unsigned int
0x1800131d8  lea     r8, [rsp+2A0h+var_278]; struct PROPERTY_ENTRY **
0x1800131dd  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x1800131e2  mov     ebx, eax
0x1800131e4  cmp     eax, 80070002h
0x1800131e9  jnz     short loc_18001323F
0x1800131eb  lea     rdx, aSite_0; "SITE_"
0x1800131f2  lea     rcx, [rsp+2A0h+var_270]
0x1800131f7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800131fd  mov     ebx, eax
0x1800131ff  test    eax, eax
0x180013201  js      short loc_18001323F
0x180013203  lea     rcx, [rdi+38h]
0x180013207  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001320d  mov     rdx, rax
0x180013210  lea     rcx, [rsp+2A0h+var_270]
0x180013215  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001321b  mov     ebx, eax
0x18001321d  test    eax, eax
0x18001321f  js      short loc_18001323F
0x180013221  lea     rcx, [rsp+2A0h+var_270]
0x180013226  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001322c  mov     r9d, r15d; unsigned int
0x18001322f  mov     rdx, rdi; struct ABO_NODE *
0x180013232  mov     r8, rax; unsigned __int16 *
0x180013235  mov     rcx, rsi; this
0x180013238  call    ?CreateSite@SITES_CUSTOM_PROVIDER@@AEAAJPEAVABO_NODE@@PEBGK@Z; SITES_CUSTOM_PROVIDER::CreateSite(ABO_NODE *,ushort const *,ulong)
0x18001323d  mov     ebx, eax
0x18001323f  mov     rcx, [rsp+2A0h+var_278]; this
0x180013244  test    rcx, rcx
0x180013247  jz      short loc_18001324E
0x180013249  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001324e  lea     rcx, [rsp+2A0h+var_270]
0x180013253  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180013259  mov     eax, ebx
0x18001325b  mov     rcx, [rbp+1A0h+var_30]
0x180013262  xor     rcx, rsp; StackCookie
0x180013265  call    __security_check_cookie
0x18001326a  lea     r11, [rsp+2A0h+var_20]
0x180013272  mov     rbx, [r11+40h]
0x180013276  mov     rsi, [r11+48h]
0x18001327a  mov     rsp, r11
0x18001327d  pop     r15
0x18001327f  pop     r14
0x180013281  pop     r12
0x180013283  pop     rdi
0x180013284  pop     rbp
0x180013285  retn
```
