# SITE_CUSTOM_PROVIDER::FindInheritedEntry(ulong,ABO_NODE *,PROPERTY_ENTRY * *,STRU *)

- ea: `0x180014270`
- end: `0x180014481`
- name: `?FindInheritedEntry@SITE_CUSTOM_PROVIDER@@AEAAJKPEAVABO_NODE@@PEAPEAVPROPERTY_ENTRY@@PEAVSTRU@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this, unsigned int, struct ABO_NODE *, struct PROPERTY_ENTRY **, struct STRU *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016b1c`

## callees

- `0x18000341a`
- `0x180003460`
- `0x1800077dc`
- `0x18000fec4`
- `0x180014270`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001437a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001439c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001437a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001439c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800143c1`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800143c1`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001440f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001440f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001438e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001438e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800142db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014304`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800142db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014304`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014443`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001444e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014443`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001444e`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001432b`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001432b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001436c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800143d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001436c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800143d2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800143e0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800143e0`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800143ad`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800143ad`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::FindInheritedEntry(
        struct ABO_NODE **this,
        __int64 a2,
        struct ABO_NODE *a3,
        struct PROPERTY_ENTRY **a4,
        struct STRU *a5)
{
  struct PROPERTY_ENTRY *v7; // rsi
  int Entry; // eax
  int v10; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rax
  struct PROPERTY_ENTRY *v15; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v17[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[256]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v19[256]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v7 = 0;
  v15 = 0;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v16, v18, 0x100u);
  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v17, v19, 0x100u);
  if ( a4 && a5 && a3 )
  {
    *a4 = 0;
    STRU::Reset(a5);
    if ( a3 == this[2] )
    {
LABEL_14:
      v10 = -2147024894;
    }
    else
    {
      while ( 1 )
      {
        Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0xBB9u, &v15);
        v10 = Entry;
        if ( Entry >= 0 )
          break;
        if ( Entry != -2147024894 )
          goto LABEL_17;
        Str = STRU::QueryStr((STRU *)v16);
        v10 = STRU::Copy((STRU *)v17, Str);
        if ( v10 < 0 )
          goto LABEL_17;
        v12 = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 56));
        v10 = STRU::Copy((STRU *)v16, v12);
        if ( v10 < 0 )
          goto LABEL_17;
        if ( !STRU::IsEmpty((STRU *)v17) )
        {
          v10 = STRU::Append((STRU *)v16, 0x2Fu);
          if ( v10 < 0 )
            goto LABEL_17;
          v13 = STRU::QueryStr((STRU *)v17);
          v10 = STRU::Append((STRU *)v16, v13);
          if ( v10 < 0 )
            goto LABEL_17;
        }
        a3 = (struct ABO_NODE *)*((_QWORD *)a3 + 2);
        if ( a3 == this[2] )
        {
          v7 = v15;
          goto LABEL_14;
        }
      }
      v10 = STRU::Copy(a5, (const struct STRU *)v16);
      if ( v10 >= 0 )
      {
        *a4 = v15;
        goto LABEL_21;
      }
LABEL_17:
      v7 = v15;
    }
  }
  else
  {
    v10 = -2147024809;
  }
  if ( v7 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v7);
LABEL_21:
  STRU::~STRU((STRU *)v17);
  STRU::~STRU((STRU *)v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014270  mov     [rsp-8+arg_0], rbx
0x180014275  mov     [rsp-8+arg_8], rsi
0x18001427a  push    rbp
0x18001427b  push    rdi
0x18001427c  push    r12
0x18001427e  push    r14
0x180014280  push    r15
0x180014282  lea     rbp, [rsp-3B0h]
0x18001428a  sub     rsp, 4B0h
0x180014291  mov     rax, cs:__security_cookie
0x180014298  xor     rax, rsp
0x18001429b  mov     [rbp+3D0h+var_30], rax
0x1800142a2  mov     r14, [rbp+3D0h+arg_20]
0x1800142a9  mov     rdi, r8
0x1800142ac  mov     r12, rcx
0x1800142af  xor     esi, esi
0x1800142b1  mov     r8d, 200h; Size
0x1800142b7  mov     [rsp+4D0h+var_4B0], rsi
0x1800142bc  lea     rcx, [rbp+3D0h+var_430]; void *
0x1800142c0  xor     edx, edx; Val
0x1800142c2  mov     r15, r9
0x1800142c5  call    memset_0
0x1800142ca  mov     ebx, 100h
0x1800142cf  lea     rdx, [rbp+3D0h+var_430]
0x1800142d3  mov     r8d, ebx
0x1800142d6  lea     rcx, [rsp+4D0h+var_4A8]
0x1800142db  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800142e1  xor     edx, edx; Val
0x1800142e3  lea     rcx, [rbp+3D0h+var_230]; void *
0x1800142ea  mov     r8d, 200h; Size
0x1800142f0  call    memset_0
0x1800142f5  mov     r8d, ebx
0x1800142f8  lea     rdx, [rbp+3D0h+var_230]
0x1800142ff  lea     rcx, [rsp+4D0h+var_470]
0x180014304  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001430a  test    r15, r15
0x18001430d  jz      loc_18001442C
0x180014313  test    r14, r14
0x180014316  jz      loc_18001442C
0x18001431c  test    rdi, rdi
0x18001431f  jz      loc_18001442C
0x180014325  mov     rcx, r14
0x180014328  mov     [r15], rsi
0x18001432b  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180014331  cmp     rdi, [r12+10h]
0x180014336  jz      loc_180014400
0x18001433c  lea     rcx, [rdi+0B8h]; this
0x180014343  mov     edx, 0BB9h; unsigned int
0x180014348  lea     r8, [rsp+4D0h+var_4B0]; struct PROPERTY_ENTRY **
0x18001434d  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180014352  mov     ebx, eax
0x180014354  test    eax, eax
0x180014356  jns     loc_180014407
0x18001435c  cmp     eax, 80070002h
0x180014361  jnz     loc_180014425
0x180014367  lea     rcx, [rsp+4D0h+var_4A8]
0x18001436c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180014372  mov     rdx, rax
0x180014375  lea     rcx, [rsp+4D0h+var_470]
0x18001437a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180014380  mov     ebx, eax
0x180014382  test    eax, eax
0x180014384  js      loc_180014425
0x18001438a  lea     rcx, [rdi+38h]
0x18001438e  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014394  mov     rdx, rax
0x180014397  lea     rcx, [rsp+4D0h+var_4A8]
0x18001439c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800143a2  mov     ebx, eax
0x1800143a4  test    eax, eax
0x1800143a6  js      short loc_180014425
0x1800143a8  lea     rcx, [rsp+4D0h+var_470]
0x1800143ad  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800143b3  test    al, al
0x1800143b5  jnz     short loc_1800143EC
0x1800143b7  mov     edx, 2Fh ; '/'
0x1800143bc  lea     rcx, [rsp+4D0h+var_4A8]
0x1800143c1  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800143c7  mov     ebx, eax
0x1800143c9  test    eax, eax
0x1800143cb  js      short loc_180014425
0x1800143cd  lea     rcx, [rsp+4D0h+var_470]
0x1800143d2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800143d8  mov     rdx, rax
0x1800143db  lea     rcx, [rsp+4D0h+var_4A8]
0x1800143e0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800143e6  mov     ebx, eax
0x1800143e8  test    eax, eax
0x1800143ea  js      short loc_180014425
0x1800143ec  mov     rdi, [rdi+10h]
0x1800143f0  cmp     rdi, [r12+10h]
0x1800143f5  jnz     loc_18001433C
0x1800143fb  mov     rsi, [rsp+4D0h+var_4B0]
0x180014400  mov     ebx, 80070002h
0x180014405  jmp     short loc_180014431
0x180014407  lea     rdx, [rsp+4D0h+var_4A8]
0x18001440c  mov     rcx, r14
0x18001440f  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180014415  mov     ebx, eax
0x180014417  test    eax, eax
0x180014419  js      short loc_180014425
0x18001441b  mov     rax, [rsp+4D0h+var_4B0]
0x180014420  mov     [r15], rax
0x180014423  jmp     short loc_18001443E
0x180014425  mov     rsi, [rsp+4D0h+var_4B0]
0x18001442a  jmp     short loc_180014431
0x18001442c  mov     ebx, 80070057h
0x180014431  test    rsi, rsi
0x180014434  jz      short loc_18001443E
0x180014436  mov     rcx, rsi; this
0x180014439  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001443e  lea     rcx, [rsp+4D0h+var_470]
0x180014443  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180014449  lea     rcx, [rsp+4D0h+var_4A8]
0x18001444e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180014454  mov     eax, ebx
0x180014456  mov     rcx, [rbp+3D0h+var_30]
0x18001445d  xor     rcx, rsp; StackCookie
0x180014460  call    __security_check_cookie
0x180014465  lea     r11, [rsp+4D0h+var_20]
0x18001446d  mov     rbx, [r11+30h]
0x180014471  mov     rsi, [r11+38h]
0x180014475  mov     rsp, r11
0x180014478  pop     r15
0x18001447a  pop     r14
0x18001447c  pop     r12
0x18001447e  pop     rdi
0x18001447f  pop     rbp
0x180014480  retn
```
