# pragmaVtabConnect

- ea: `0x18007c4e0`
- end: `0x18007c6a4`
- name: `pragmaVtabConnect`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001110`
- `0x180005300`
- `0x180005840`
- `0x1800237f0`
- `0x1800263e0`
- `0x18004a310`
- `0x18004d2f0`
- `0x180068880`
- `0x18007c4e0`
- `0x18008dfb0`

## string_xrefs

- `0x18007c51b`: `CREATE TABLE x`

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
    sqlite3_str_appendf(v18, "%c\"%s\"", v10, off_18009C110[v11]);
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
0x18007c4e0  mov     [rsp-8+arg_10], rbx
0x18007c4e5  push    rbp
0x18007c4e6  push    rsi
0x18007c4e7  push    rdi
0x18007c4e8  push    r12
0x18007c4ea  push    r13
0x18007c4ec  push    r14
0x18007c4ee  push    r15
0x18007c4f0  lea     rbp, [rsp-30h]
0x18007c4f5  sub     rsp, 130h
0x18007c4fc  mov     rax, cs:__security_cookie
0x18007c503  xor     rax, rsp
0x18007c506  mov     [rbp+60h+var_40], rax
0x18007c50a  mov     rax, [rbp+60h+arg_28]
0x18007c511  mov     rdi, rdx
0x18007c514  mov     r13, [rbp+60h+arg_20]
0x18007c51b  lea     rdx, aCreateTableX; "CREATE TABLE x"
0x18007c522  mov     [rsp+160h+var_120], rax
0x18007c527  mov     r12, rcx
0x18007c52a  lea     rax, [rsp+160h+var_110]
0x18007c52f  mov     [rsp+160h+var_130], 0C8h
0x18007c538  xor     ebx, ebx
0x18007c53a  mov     [rsp+160h+var_138], rax
0x18007c53f  lea     rcx, [rsp+160h+var_140]
0x18007c544  mov     [rsp+160h+var_128], rbx
0x18007c549  mov     [rsp+160h+var_140], rbx
0x18007c54e  call    sqlite3_str_appendall
0x18007c553  lea     r15d, [rbx+1]
0x18007c557  cmp     [rdi+0Bh], bl
0x18007c55a  jbe     short loc_18007C5A2
0x18007c55c  mov     r14d, ebx
0x18007c55f  lea     r8d, [r15+27h]
0x18007c563  movzx   ebx, byte ptr [rdi+0Ah]
0x18007c567  lea     rax, off_18009C110; "id"
0x18007c56e  movsxd  r9, ebx
0x18007c571  lea     rdx, aCS; "%c\"%s\""
0x18007c578  lea     rcx, [rsp+160h+var_140]
0x18007c57d  mov     r9, [rax+r9*8]
0x18007c581  call    sqlite3_str_appendf
0x18007c586  movzx   eax, byte ptr [rdi+0Bh]
0x18007c58a  add     r14d, r15d
0x18007c58d  add     ebx, r15d
0x18007c590  mov     r8d, 2Ch ; ','
0x18007c596  cmp     r14d, eax
0x18007c599  jl      short loc_18007C567
0x18007c59b  xor     ebx, ebx
0x18007c59d  test    r14d, r14d
0x18007c5a0  jnz     short loc_18007C5B9
0x18007c5a2  mov     r8, [rdi]
0x18007c5a5  lea     rdx, aS_6; "(\"%s\""
0x18007c5ac  lea     rcx, [rsp+160h+var_140]
0x18007c5b1  call    sqlite3_str_appendf
0x18007c5b6  mov     r14d, r15d
0x18007c5b9  test    byte ptr [rdi+9], 20h
0x18007c5bd  mov     esi, ebx
0x18007c5bf  jz      short loc_18007C5D5
0x18007c5c1  lea     rdx, aArgHidden; ",arg HIDDEN"
0x18007c5c8  lea     rcx, [rsp+160h+var_140]
0x18007c5cd  call    sqlite3_str_appendall
0x18007c5d2  mov     esi, r15d
0x18007c5d5  test    byte ptr [rdi+9], 0C0h
0x18007c5d9  jz      short loc_18007C5EF
0x18007c5db  lea     rdx, aSchemaHidden; ",schema HIDDEN"
0x18007c5e2  lea     rcx, [rsp+160h+var_140]
0x18007c5e7  call    sqlite3_str_appendall
0x18007c5ec  add     esi, r15d
0x18007c5ef  mov     r8d, r15d
0x18007c5f2  lea     rdx, asc_1800A1320; ")"
0x18007c5f9  lea     rcx, [rsp+160h+var_140]
0x18007c5fe  call    sqlite3_str_append
0x18007c603  lea     rcx, [rsp+160h+var_140]
0x18007c608  call    sqlite3StrAccumFinish
0x18007c60d  lea     rdx, [rsp+160h+var_110]
0x18007c612  mov     rcx, r12
0x18007c615  call    sqlite3_declare_vtab
0x18007c61a  mov     r15d, eax
0x18007c61d  test    eax, eax
0x18007c61f  jnz     short loc_18007C657
0x18007c621  lea     ecx, [rax+30h]
0x18007c624  call    sqlite3_malloc
0x18007c629  mov     rbx, rax
0x18007c62c  test    rax, rax
0x18007c62f  jnz     short loc_18007C637
0x18007c631  lea     r15d, [rax+7]
0x18007c635  jmp     short loc_18007C676
0x18007c637  xorps   xmm0, xmm0
0x18007c63a  movups  xmmword ptr [rax], xmm0
0x18007c63d  movups  xmmword ptr [rax+10h], xmm0
0x18007c641  movups  xmmword ptr [rax+20h], xmm0
0x18007c645  mov     [rax+20h], rdi
0x18007c649  mov     [rax+18h], r12
0x18007c64d  mov     [rax+29h], r14b
0x18007c651  mov     [rax+28h], sil
0x18007c655  jmp     short loc_18007C676
0x18007c657  mov     rcx, r12
0x18007c65a  call    sqlite3_errmsg
0x18007c65f  mov     rdx, rax
0x18007c662  lea     rcx, aS_7; "%s"
0x18007c669  call    sqlite3_mprintf
0x18007c66e  mov     rcx, [rsp+160h+var_120]
0x18007c673  mov     [rcx], rax
0x18007c676  mov     [r13+0], rbx
0x18007c67a  mov     eax, r15d
0x18007c67d  mov     rcx, [rbp+60h+var_40]
0x18007c681  xor     rcx, rsp; StackCookie
0x18007c684  call    __security_check_cookie
0x18007c689  mov     rbx, [rsp+160h+arg_10]
0x18007c691  add     rsp, 130h
0x18007c698  pop     r15
0x18007c69a  pop     r14
0x18007c69c  pop     r13
0x18007c69e  pop     r12
0x18007c6a0  pop     rdi
0x18007c6a1  pop     rsi
0x18007c6a2  pop     rbp
0x18007c6a3  retn
```
