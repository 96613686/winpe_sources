# pragmaVtabConnect

- ea: `0x140040800`
- end: `0x1400409df`
- name: `pragmaVtabConnect`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140001ba0`
- `0x140040800`
- `0x140062c2c`
- `0x14007026c`
- `0x140089cf0`
- `0x14008a290`
- `0x14008b1cc`
- `0x14008b8d0`
- `0x14008d4d0`
- `0x14008d5a0`

## string_xrefs

- `0x140040842`: `CREATE TABLE x`

## pseudocode

```c
__int64 __fastcall pragmaVtabConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, __int64 *a6)
{
  __int64 v6; // rbx
  int v9; // r15d
  __int64 v10; // r8
  int v11; // ebx
  char v12; // si
  unsigned int v13; // r14d
  __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  _QWORD v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[208]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = 0;
  v19 = a6;
  v18[3] = 0;
  v18[0] = 0;
  v18[1] = v20;
  v18[2] = 200;
  sqlite3_str_append(v18, "CREATE TABLE x", 14);
  if ( !*(_BYTE *)(a2 + 11) )
    goto LABEL_5;
  v9 = 0;
  v10 = 40;
  v11 = *(unsigned __int8 *)(a2 + 10);
  do
  {
    sqlite3_str_appendf(v18, "%c\"%s\"", v10, off_1400AA390[v11]);
    ++v9;
    ++v11;
    v10 = 44;
  }
  while ( v9 < *(unsigned __int8 *)(a2 + 11) );
  v6 = 0;
  if ( !v9 )
  {
LABEL_5:
    sqlite3_str_appendf(v18, "(\"%s\"", *(const char **)a2);
    LOBYTE(v9) = 1;
  }
  v12 = 0;
  if ( (*(_BYTE *)(a2 + 9) & 0x20) != 0 )
  {
    sqlite3_str_append(v18, ",arg HIDDEN", 11);
    v12 = 1;
  }
  if ( (*(_BYTE *)(a2 + 9) & 0xC0) != 0 )
  {
    sqlite3_str_append(v18, ",schema HIDDEN", 14);
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
  else if ( !(unsigned int)sqlite3_initialize() && (v14 = sqlite3Malloc(48), (v6 = v14) != 0) )
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
  *a5 = v6;
  return v13;
}

```

## disassembly

```asm
0x140040800  mov     [rsp-8+arg_10], rbx
0x140040805  push    rbp
0x140040806  push    rsi
0x140040807  push    rdi
0x140040808  push    r12
0x14004080a  push    r13
0x14004080c  push    r14
0x14004080e  push    r15
0x140040810  lea     rbp, [rsp-30h]
0x140040815  sub     rsp, 130h
0x14004081c  mov     rax, cs:__security_cookie
0x140040823  xor     rax, rsp
0x140040826  mov     [rbp+60h+var_40], rax
0x14004082a  mov     rax, [rbp+60h+arg_28]
0x140040831  xor     ebx, ebx
0x140040833  mov     r13, [rbp+60h+arg_20]
0x14004083a  mov     rdi, rdx
0x14004083d  mov     [rsp+160h+var_120], rax
0x140040842  lea     rdx, aCreateTableX; "CREATE TABLE x"
0x140040849  mov     r12, rcx
0x14004084c  mov     [rsp+160h+var_128], rbx
0x140040851  lea     rax, [rsp+160h+var_110]
0x140040856  mov     [rsp+160h+var_140], rbx
0x14004085b  lea     r8d, [rbx+0Eh]
0x14004085f  mov     [rsp+160h+var_138], rax
0x140040864  lea     rcx, [rsp+160h+var_140]
0x140040869  mov     [rsp+160h+var_130], 0C8h
0x140040872  call    sqlite3_str_append
0x140040877  lea     r14d, [rbx+1]
0x14004087b  cmp     [rdi+0Bh], bl
0x14004087e  jbe     short loc_1400408C6
0x140040880  mov     r15d, ebx
0x140040883  lea     r8d, [r14+27h]
0x140040887  movzx   ebx, byte ptr [rdi+0Ah]
0x14004088b  lea     rax, off_1400AA390; "id"
0x140040892  movsxd  r9, ebx
0x140040895  lea     rdx, aCS; "%c\"%s\""
0x14004089c  lea     rcx, [rsp+160h+var_140]
0x1400408a1  mov     r9, [rax+r9*8]
0x1400408a5  call    sqlite3_str_appendf
0x1400408aa  movzx   eax, byte ptr [rdi+0Bh]
0x1400408ae  add     r15d, r14d
0x1400408b1  add     ebx, r14d
0x1400408b4  mov     r8d, 2Ch ; ','
0x1400408ba  cmp     r15d, eax
0x1400408bd  jl      short loc_14004088B
0x1400408bf  xor     ebx, ebx
0x1400408c1  test    r15d, r15d
0x1400408c4  jnz     short loc_1400408DD
0x1400408c6  mov     r8, [rdi]
0x1400408c9  lea     rdx, aS_5; "(\"%s\""
0x1400408d0  lea     rcx, [rsp+160h+var_140]
0x1400408d5  call    sqlite3_str_appendf
0x1400408da  mov     r15d, r14d
0x1400408dd  test    byte ptr [rdi+9], 20h
0x1400408e1  mov     esi, ebx
0x1400408e3  jz      short loc_1400408FF
0x1400408e5  mov     r8d, 0Bh
0x1400408eb  lea     rdx, aArgHidden; ",arg HIDDEN"
0x1400408f2  lea     rcx, [rsp+160h+var_140]
0x1400408f7  call    sqlite3_str_append
0x1400408fc  mov     esi, r14d
0x1400408ff  test    byte ptr [rdi+9], 0C0h
0x140040903  jz      short loc_14004091F
0x140040905  mov     r8d, 0Eh
0x14004090b  lea     rdx, aSchemaHidden; ",schema HIDDEN"
0x140040912  lea     rcx, [rsp+160h+var_140]
0x140040917  call    sqlite3_str_append
0x14004091c  add     esi, r14d
0x14004091f  mov     r8d, r14d
0x140040922  lea     rdx, asc_1400B79FC; ")"
0x140040929  lea     rcx, [rsp+160h+var_140]
0x14004092e  call    sqlite3_str_append
0x140040933  lea     rcx, [rsp+160h+var_140]
0x140040938  call    sqlite3StrAccumFinish
0x14004093d  lea     rdx, [rsp+160h+var_110]
0x140040942  mov     rcx, r12
0x140040945  call    sqlite3_declare_vtab
0x14004094a  mov     r14d, eax
0x14004094d  test    eax, eax
0x14004094f  jnz     short loc_140040992
0x140040951  call    sqlite3_initialize
0x140040956  test    eax, eax
0x140040958  jnz     short loc_14004096A
0x14004095a  lea     ecx, [rax+30h]
0x14004095d  call    sqlite3Malloc
0x140040962  mov     rbx, rax
0x140040965  test    rax, rax
0x140040968  jnz     short loc_140040972
0x14004096a  mov     r14d, 7
0x140040970  jmp     short loc_1400409B1
0x140040972  xorps   xmm0, xmm0
0x140040975  movups  xmmword ptr [rax], xmm0
0x140040978  movups  xmmword ptr [rax+10h], xmm0
0x14004097c  movups  xmmword ptr [rax+20h], xmm0
0x140040980  mov     [rax+20h], rdi
0x140040984  mov     [rax+18h], r12
0x140040988  mov     [rax+29h], r15b
0x14004098c  mov     [rax+28h], sil
0x140040990  jmp     short loc_1400409B1
0x140040992  mov     rcx, r12
0x140040995  call    sqlite3_errmsg
0x14004099a  mov     rdx, rax
0x14004099d  lea     rcx, aS_6; "%s"
0x1400409a4  call    sqlite3_mprintf
0x1400409a9  mov     rcx, [rsp+160h+var_120]
0x1400409ae  mov     [rcx], rax
0x1400409b1  mov     [r13+0], rbx
0x1400409b5  mov     eax, r14d
0x1400409b8  mov     rcx, [rbp+60h+var_40]
0x1400409bc  xor     rcx, rsp; StackCookie
0x1400409bf  call    __security_check_cookie
0x1400409c4  mov     rbx, [rsp+160h+arg_10]
0x1400409cc  add     rsp, 130h
0x1400409d3  pop     r15
0x1400409d5  pop     r14
0x1400409d7  pop     r13
0x1400409d9  pop     r12
0x1400409db  pop     rdi
0x1400409dc  pop     rsi
0x1400409dd  pop     rbp
0x1400409de  retn
```
