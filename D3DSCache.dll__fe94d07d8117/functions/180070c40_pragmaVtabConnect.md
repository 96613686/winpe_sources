# pragmaVtabConnect

- ea: `0x180070c40`
- end: `0x180070e04`
- name: `pragmaVtabConnect`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180035970`
- `0x1800423b4`
- `0x1800449f0`
- `0x180070c40`
- `0x180095340`
- `0x1800958b0`
- `0x180096460`
- `0x180096550`
- `0x180097c50`
- `0x180097ce0`

## string_xrefs

- `0x180070c7b`: `CREATE TABLE x`

## pseudocode

```c
__int64 __fastcall pragmaVtabConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, __int64 *a6)
{
  __int64 v8; // rbx
  int v9; // r14d
  __int64 v10; // r8
  int v11; // ebx
  char v12; // si
  unsigned int v13; // r15d
  __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  _QWORD v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[208]; // [rsp+50h] [rbp-B0h] BYREF

  v19 = a6;
  v18[2] = 200;
  v8 = 0;
  v18[1] = v20;
  v18[3] = 0;
  v18[0] = 0;
  sqlite3_str_appendall(v18, "CREATE TABLE x");
  if ( !*(_BYTE *)(a2 + 11) )
    goto LABEL_5;
  v9 = 0;
  v10 = 40;
  v11 = *(unsigned __int8 *)(a2 + 10);
  do
  {
    sqlite3_str_appendf(v18, "%c\"%s\"", v10, off_1800AA4C0[v11]);
    ++v9;
    ++v11;
    v10 = 44;
  }
  while ( v9 < *(unsigned __int8 *)(a2 + 11) );
  v8 = 0;
  if ( !v9 )
  {
LABEL_5:
    sqlite3_str_appendf(v18, "(\"%s\"", *(const char **)a2);
    LOBYTE(v9) = 1;
  }
  v12 = 0;
  if ( (*(_BYTE *)(a2 + 9) & 0x20) != 0 )
  {
    sqlite3_str_appendall(v18, ",arg HIDDEN");
    v12 = 1;
  }
  if ( (*(_BYTE *)(a2 + 9) & 0xC0) != 0 )
  {
    sqlite3_str_appendall(v18, ",schema HIDDEN");
    ++v12;
  }
  sqlite3_str_append(v18, ")", 1);
  sqlite3StrAccumFinish(v18);
  v13 = sqlite3_declare_vtab(a1, v20);
  if ( v13 )
  {
    v15 = (const char *)sqlite3_errmsg(a1);
    v16 = sqlite3_mprintf("%s", v15);
    *v19 = v16;
  }
  else
  {
    v14 = sqlite3_malloc(48);
    v8 = v14;
    if ( v14 )
    {
      *(_OWORD *)v14 = 0;
      *(_OWORD *)(v14 + 16) = 0;
      *(_OWORD *)(v14 + 32) = 0;
      *(_QWORD *)(v14 + 32) = a2;
      *(_QWORD *)(v14 + 24) = a1;
      *(_BYTE *)(v14 + 41) = v9;
      *(_BYTE *)(v14 + 40) = v12;
    }
    else
    {
      v13 = 7;
    }
  }
  *a5 = v8;
  return v13;
}

```

## disassembly

```asm
0x180070c40  mov     [rsp-8+arg_10], rbx
0x180070c45  push    rbp
0x180070c46  push    rsi
0x180070c47  push    rdi
0x180070c48  push    r12
0x180070c4a  push    r13
0x180070c4c  push    r14
0x180070c4e  push    r15
0x180070c50  lea     rbp, [rsp-30h]
0x180070c55  sub     rsp, 130h
0x180070c5c  mov     rax, cs:__security_cookie
0x180070c63  xor     rax, rsp
0x180070c66  mov     [rbp+60h+var_40], rax
0x180070c6a  mov     rax, [rbp+60h+arg_28]
0x180070c71  mov     rdi, rdx
0x180070c74  mov     r13, [rbp+60h+arg_20]
0x180070c7b  lea     rdx, aCreateTableX; "CREATE TABLE x"
0x180070c82  mov     [rsp+160h+var_120], rax
0x180070c87  mov     r12, rcx
0x180070c8a  lea     rax, [rsp+160h+var_110]
0x180070c8f  mov     [rsp+160h+var_130], 0C8h
0x180070c98  xor     ebx, ebx
0x180070c9a  mov     [rsp+160h+var_138], rax
0x180070c9f  lea     rcx, [rsp+160h+var_140]
0x180070ca4  mov     [rsp+160h+var_128], rbx
0x180070ca9  mov     [rsp+160h+var_140], rbx
0x180070cae  call    sqlite3_str_appendall
0x180070cb3  lea     r15d, [rbx+1]
0x180070cb7  cmp     [rdi+0Bh], bl
0x180070cba  jbe     short loc_180070D02
0x180070cbc  mov     r14d, ebx
0x180070cbf  lea     r8d, [r15+27h]
0x180070cc3  movzx   ebx, byte ptr [rdi+0Ah]
0x180070cc7  lea     rax, off_1800AA4C0; "id"
0x180070cce  movsxd  r9, ebx
0x180070cd1  lea     rdx, aCS; "%c\"%s\""
0x180070cd8  lea     rcx, [rsp+160h+var_140]
0x180070cdd  mov     r9, [rax+r9*8]
0x180070ce1  call    sqlite3_str_appendf
0x180070ce6  movzx   eax, byte ptr [rdi+0Bh]
0x180070cea  add     r14d, r15d
0x180070ced  add     ebx, r15d
0x180070cf0  mov     r8d, 2Ch ; ','
0x180070cf6  cmp     r14d, eax
0x180070cf9  jl      short loc_180070CC7
0x180070cfb  xor     ebx, ebx
0x180070cfd  test    r14d, r14d
0x180070d00  jnz     short loc_180070D19
0x180070d02  mov     r8, [rdi]
0x180070d05  lea     rdx, aS_9; "(\"%s\""
0x180070d0c  lea     rcx, [rsp+160h+var_140]
0x180070d11  call    sqlite3_str_appendf
0x180070d16  mov     r14d, r15d
0x180070d19  test    byte ptr [rdi+9], 20h
0x180070d1d  mov     esi, ebx
0x180070d1f  jz      short loc_180070D35
0x180070d21  lea     rdx, aArgHidden; ",arg HIDDEN"
0x180070d28  lea     rcx, [rsp+160h+var_140]
0x180070d2d  call    sqlite3_str_appendall
0x180070d32  mov     esi, r15d
0x180070d35  test    byte ptr [rdi+9], 0C0h
0x180070d39  jz      short loc_180070D4F
0x180070d3b  lea     rdx, aSchemaHidden; ",schema HIDDEN"
0x180070d42  lea     rcx, [rsp+160h+var_140]
0x180070d47  call    sqlite3_str_appendall
0x180070d4c  add     esi, r15d
0x180070d4f  mov     r8d, r15d
0x180070d52  lea     rdx, asc_1800B09E0; ")"
0x180070d59  lea     rcx, [rsp+160h+var_140]
0x180070d5e  call    sqlite3_str_append
0x180070d63  lea     rcx, [rsp+160h+var_140]
0x180070d68  call    sqlite3StrAccumFinish
0x180070d6d  lea     rdx, [rsp+160h+var_110]
0x180070d72  mov     rcx, r12
0x180070d75  call    sqlite3_declare_vtab
0x180070d7a  mov     r15d, eax
0x180070d7d  test    eax, eax
0x180070d7f  jnz     short loc_180070DB7
0x180070d81  lea     ecx, [rax+30h]
0x180070d84  call    sqlite3_malloc
0x180070d89  mov     rbx, rax
0x180070d8c  test    rax, rax
0x180070d8f  jnz     short loc_180070D97
0x180070d91  lea     r15d, [rax+7]
0x180070d95  jmp     short loc_180070DD6
0x180070d97  xorps   xmm0, xmm0
0x180070d9a  movups  xmmword ptr [rax], xmm0
0x180070d9d  movups  xmmword ptr [rax+10h], xmm0
0x180070da1  movups  xmmword ptr [rax+20h], xmm0
0x180070da5  mov     [rax+20h], rdi
0x180070da9  mov     [rax+18h], r12
0x180070dad  mov     [rax+29h], r14b
0x180070db1  mov     [rax+28h], sil
0x180070db5  jmp     short loc_180070DD6
0x180070db7  mov     rcx, r12
0x180070dba  call    sqlite3_errmsg
0x180070dbf  mov     rdx, rax
0x180070dc2  lea     rcx, aS_10; "%s"
0x180070dc9  call    sqlite3_mprintf
0x180070dce  mov     rcx, [rsp+160h+var_120]
0x180070dd3  mov     [rcx], rax
0x180070dd6  mov     [r13+0], rbx
0x180070dda  mov     eax, r15d
0x180070ddd  mov     rcx, [rbp+60h+var_40]
0x180070de1  xor     rcx, rsp; StackCookie
0x180070de4  call    __security_check_cookie
0x180070de9  mov     rbx, [rsp+160h+arg_10]
0x180070df1  add     rsp, 130h
0x180070df8  pop     r15
0x180070dfa  pop     r14
0x180070dfc  pop     r13
0x180070dfe  pop     r12
0x180070e00  pop     rdi
0x180070e01  pop     rsi
0x180070e02  pop     rbp
0x180070e03  retn
```
