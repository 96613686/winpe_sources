# pragmaVtabConnect

- ea: `0x18008ba10`
- end: `0x18008bbd4`
- name: `pragmaVtabConnect`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18001e8a0`
- `0x18001fff0`
- `0x1800310a0`
- `0x180031d80`
- `0x18003f8e8`
- `0x180061500`
- `0x180077220`
- `0x1800789c0`
- `0x18008ba10`
- `0x18009bf50`

## string_xrefs

- `0x18008ba4b`: `CREATE TABLE x`

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
    sqlite3_str_appendf(v18, "%c\"%s\"", v10, off_1800B29E0[v11]);
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
0x18008ba10  mov     [rsp-8+arg_10], rbx
0x18008ba15  push    rbp
0x18008ba16  push    rsi
0x18008ba17  push    rdi
0x18008ba18  push    r12
0x18008ba1a  push    r13
0x18008ba1c  push    r14
0x18008ba1e  push    r15
0x18008ba20  lea     rbp, [rsp-30h]
0x18008ba25  sub     rsp, 130h
0x18008ba2c  mov     rax, cs:__security_cookie
0x18008ba33  xor     rax, rsp
0x18008ba36  mov     [rbp+60h+var_40], rax
0x18008ba3a  mov     rax, [rbp+60h+arg_28]
0x18008ba41  mov     rdi, rdx
0x18008ba44  mov     r13, [rbp+60h+arg_20]
0x18008ba4b  lea     rdx, aCreateTableX; "CREATE TABLE x"
0x18008ba52  mov     [rsp+160h+var_120], rax
0x18008ba57  mov     r12, rcx
0x18008ba5a  lea     rax, [rsp+160h+var_110]
0x18008ba5f  mov     [rsp+160h+var_130], 0C8h
0x18008ba68  xor     ebx, ebx
0x18008ba6a  mov     [rsp+160h+var_138], rax
0x18008ba6f  lea     rcx, [rsp+160h+var_140]
0x18008ba74  mov     [rsp+160h+var_128], rbx
0x18008ba79  mov     [rsp+160h+var_140], rbx
0x18008ba7e  call    sqlite3_str_appendall
0x18008ba83  lea     r15d, [rbx+1]
0x18008ba87  cmp     [rdi+0Bh], bl
0x18008ba8a  jbe     short loc_18008BAD2
0x18008ba8c  mov     r14d, ebx
0x18008ba8f  lea     r8d, [r15+27h]
0x18008ba93  movzx   ebx, byte ptr [rdi+0Ah]
0x18008ba97  lea     rax, off_1800B29E0; "id"
0x18008ba9e  movsxd  r9, ebx
0x18008baa1  lea     rdx, aCS; "%c\"%s\""
0x18008baa8  lea     rcx, [rsp+160h+var_140]
0x18008baad  mov     r9, [rax+r9*8]
0x18008bab1  call    sqlite3_str_appendf
0x18008bab6  movzx   eax, byte ptr [rdi+0Bh]
0x18008baba  add     r14d, r15d
0x18008babd  add     ebx, r15d
0x18008bac0  mov     r8d, 2Ch ; ','
0x18008bac6  cmp     r14d, eax
0x18008bac9  jl      short loc_18008BA97
0x18008bacb  xor     ebx, ebx
0x18008bacd  test    r14d, r14d
0x18008bad0  jnz     short loc_18008BAE9
0x18008bad2  mov     r8, [rdi]
0x18008bad5  lea     rdx, aS_6; "(\"%s\""
0x18008badc  lea     rcx, [rsp+160h+var_140]
0x18008bae1  call    sqlite3_str_appendf
0x18008bae6  mov     r14d, r15d
0x18008bae9  test    byte ptr [rdi+9], 20h
0x18008baed  mov     esi, ebx
0x18008baef  jz      short loc_18008BB05
0x18008baf1  lea     rdx, aArgHidden; ",arg HIDDEN"
0x18008baf8  lea     rcx, [rsp+160h+var_140]
0x18008bafd  call    sqlite3_str_appendall
0x18008bb02  mov     esi, r15d
0x18008bb05  test    byte ptr [rdi+9], 0C0h
0x18008bb09  jz      short loc_18008BB1F
0x18008bb0b  lea     rdx, aSchemaHidden; ",schema HIDDEN"
0x18008bb12  lea     rcx, [rsp+160h+var_140]
0x18008bb17  call    sqlite3_str_appendall
0x18008bb1c  add     esi, r15d
0x18008bb1f  mov     r8d, r15d
0x18008bb22  lea     rdx, asc_1800B6B24; ")"
0x18008bb29  lea     rcx, [rsp+160h+var_140]
0x18008bb2e  call    sqlite3_str_append
0x18008bb33  lea     rcx, [rsp+160h+var_140]
0x18008bb38  call    sqlite3StrAccumFinish
0x18008bb3d  lea     rdx, [rsp+160h+var_110]
0x18008bb42  mov     rcx, r12
0x18008bb45  call    sqlite3_declare_vtab
0x18008bb4a  mov     r15d, eax
0x18008bb4d  test    eax, eax
0x18008bb4f  jnz     short loc_18008BB87
0x18008bb51  lea     ecx, [rax+30h]
0x18008bb54  call    sqlite3_malloc
0x18008bb59  mov     rbx, rax
0x18008bb5c  test    rax, rax
0x18008bb5f  jnz     short loc_18008BB67
0x18008bb61  lea     r15d, [rax+7]
0x18008bb65  jmp     short loc_18008BBA6
0x18008bb67  xorps   xmm0, xmm0
0x18008bb6a  movups  xmmword ptr [rax], xmm0
0x18008bb6d  movups  xmmword ptr [rax+10h], xmm0
0x18008bb71  movups  xmmword ptr [rax+20h], xmm0
0x18008bb75  mov     [rax+20h], rdi
0x18008bb79  mov     [rax+18h], r12
0x18008bb7d  mov     [rax+29h], r14b
0x18008bb81  mov     [rax+28h], sil
0x18008bb85  jmp     short loc_18008BBA6
0x18008bb87  mov     rcx, r12
0x18008bb8a  call    sqlite3_errmsg
0x18008bb8f  mov     rdx, rax
0x18008bb92  lea     rcx, aS_7; "%s"
0x18008bb99  call    sqlite3_mprintf
0x18008bb9e  mov     rcx, [rsp+160h+var_120]
0x18008bba3  mov     [rcx], rax
0x18008bba6  mov     [r13+0], rbx
0x18008bbaa  mov     eax, r15d
0x18008bbad  mov     rcx, [rbp+60h+var_40]
0x18008bbb1  xor     rcx, rsp; StackCookie
0x18008bbb4  call    __security_check_cookie
0x18008bbb9  mov     rbx, [rsp+160h+arg_10]
0x18008bbc1  add     rsp, 130h
0x18008bbc8  pop     r15
0x18008bbca  pop     r14
0x18008bbcc  pop     r13
0x18008bbce  pop     r12
0x18008bbd0  pop     rdi
0x18008bbd1  pop     rsi
0x18008bbd2  pop     rbp
0x18008bbd3  retn
```
