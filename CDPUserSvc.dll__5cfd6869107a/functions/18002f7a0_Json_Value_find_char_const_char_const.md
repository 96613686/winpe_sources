# Json::Value::find(char const *,char const *)

- ea: `0x18002f7a0`
- end: `0x18002f98c`
- name: `?find@Value@Json@@QEBAPEBV12@PEBD0@Z`
- size: `492`
- prototype: `const struct Json::Value *(Json::Value *__hidden this, const char *, const char *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e5a0`
- `0x18002f9a0`
- `0x18002ff60`

## callees

- `0x18000ecb8`
- `0x18002c570`
- `0x18002d1a4`
- `0x18002f7a0`
- `0x1800308b0`
- `0x18005a9d0`
- `0x18005af9c`
- `0x18005bd84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f8c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f8df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f8c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f8df`

## string_xrefs

- `0x18002f909`: `assert json failed`
- `0x18002f969`: `assert json failed`
- `0x18002f93c`: `in Json::Value::find(key, end, found): requires objectValue or nullValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
const struct Json::Value *__fastcall Json::Value::find(__int64 **this, char *a2, const char *a3)
{
  char v4; // al
  unsigned int v5; // esi
  __int64 *v6; // r13
  __int64 *v7; // rbx
  __int64 *v8; // r15
  const void *v9; // rcx
  unsigned int v10; // edi
  bool v11; // cf
  unsigned int v12; // edi
  unsigned int v13; // eax
  int v14; // eax
  char v15; // cl
  __int64 *v16; // rax
  unsigned int v17; // ebx
  bool v18; // cf
  unsigned int v19; // ebx
  unsigned int v20; // eax
  const void *v21; // rdx
  int v22; // eax
  __int64 v24; // rax
  _BYTE v25[240]; // [rsp+30h] [rbp-158h] BYREF
  _BYTE v26[32]; // [rsp+120h] [rbp-68h] BYREF

  v4 = *((_BYTE *)this + 8);
  if ( !v4 )
    return 0;
  if ( v4 != 7 )
  {
    std::ostringstream::ostringstream(v25, 1);
    std::operator<<<std::char_traits<char>>(
      (__int64)v25,
      (__int64)"in Json::Value::find(key, end, found): requires objectValue or nullValue");
    v24 = std::ostringstream::str(v25, v26);
    Json::throwLogicError(v24);
  }
  v5 = 4 * ((_DWORD)a3 - (_DWORD)a2);
  v6 = (__int64 *)**this;
  v7 = (__int64 *)v6[1];
  v8 = v6;
  if ( !*((_BYTE *)v7 + 25) )
  {
    do
    {
      v9 = (const void *)v7[4];
      v10 = *((_DWORD *)v7 + 10);
      if ( v9 )
      {
        v12 = v10 >> 2;
        v13 = v12;
        if ( v5 >> 2 < v12 )
          v13 = v5 >> 2;
        if ( !a2 )
        {
          std::string::string((__int64)v26, (__int64)"assert json failed");
          Json::throwLogicError(v26);
        }
        v14 = memcmp_0(v9, a2, v13);
        if ( v14 < 0 )
        {
          v15 = 1;
          goto LABEL_16;
        }
        if ( v14 > 0 )
        {
          v15 = 0;
LABEL_15:
          v8 = v7;
          goto LABEL_16;
        }
        v11 = v12 < v5 >> 2;
      }
      else
      {
        v11 = v10 < v5;
      }
      v15 = v11;
      if ( !v11 )
        goto LABEL_15;
LABEL_16:
      v16 = v7 + 2;
      if ( !v15 )
        v16 = v7;
      v7 = (__int64 *)*v16;
    }
    while ( !*(_BYTE *)(*v16 + 25) );
  }
  if ( *((_BYTE *)v8 + 25) )
    goto LABEL_34;
  v17 = *((_DWORD *)v8 + 10);
  if ( !a2 )
  {
    v18 = v5 < v17;
    goto LABEL_28;
  }
  v19 = v17 >> 2;
  v20 = v5 >> 2;
  if ( v19 < v5 >> 2 )
    v20 = v19;
  v21 = (const void *)v8[4];
  if ( !v21 )
  {
    std::string::string((__int64)v26, (__int64)"assert json failed");
    Json::throwLogicError(v26);
  }
  v22 = memcmp_0(a2, v21, v20);
  if ( v22 < 0 )
    goto LABEL_34;
  if ( v22 <= 0 )
  {
    v18 = v5 >> 2 < v19;
LABEL_28:
    if ( !v18 )
      goto LABEL_29;
LABEL_34:
    if ( a2 && (v5 & 3) == 1 )
      free(a2);
    return 0;
  }
LABEL_29:
  if ( v8 == v6 )
    goto LABEL_34;
  if ( a2 )
  {
    if ( (v5 & 3) == 1 )
      free(a2);
  }
  return (const struct Json::Value *)(v8 + 6);
}

```

## disassembly

```asm
0x18002f7a0  push    rbx
0x18002f7a2  push    rbp
0x18002f7a3  push    rsi
0x18002f7a4  push    rdi
0x18002f7a5  push    r13
0x18002f7a7  push    r14
0x18002f7a9  push    r15
0x18002f7ab  sub     rsp, 150h
0x18002f7b2  mov     rax, cs:__security_cookie
0x18002f7b9  xor     rax, rsp
0x18002f7bc  mov     [rsp+188h+var_48], rax
0x18002f7c4  mov     rsi, r8
0x18002f7c7  mov     r14, rdx
0x18002f7ca  movzx   eax, byte ptr [rcx+8]
0x18002f7ce  test    al, al
0x18002f7d0  jz      loc_18002F8E5
0x18002f7d6  cmp     al, 7
0x18002f7d8  jnz     loc_18002F92C
0x18002f7de  mov     [rsp+188h+var_168], rdx
0x18002f7e3  sub     esi, r14d
0x18002f7e6  shl     esi, 2
0x18002f7e9  mov     [rsp+188h+var_160], esi
0x18002f7ed  mov     rax, [rcx]
0x18002f7f0  mov     r13, [rax]
0x18002f7f3  mov     rbx, [r13+8]
0x18002f7f7  mov     r15, r13
0x18002f7fa  cmp     byte ptr [rbx+19h], 0
0x18002f7fe  jnz     short loc_18002F860
0x18002f800  mov     rcx, [rbx+20h]; Buf1
0x18002f804  mov     edi, [rbx+28h]
0x18002f807  test    rcx, rcx
0x18002f80a  jnz     short loc_18002F810
0x18002f80c  cmp     edi, esi
0x18002f80e  jmp     short loc_18002F843
0x18002f810  shr     edi, 2
0x18002f813  mov     ebp, esi
0x18002f815  shr     ebp, 2
0x18002f818  mov     eax, edi
0x18002f81a  cmp     ebp, edi
0x18002f81c  cmovb   eax, ebp
0x18002f81f  test    r14, r14
0x18002f822  jz      loc_18002F969
0x18002f828  mov     r8d, eax; Size
0x18002f82b  mov     rdx, r14; Buf2
0x18002f82e  call    memcmp_0
0x18002f833  test    eax, eax
0x18002f835  jns     short loc_18002F83B
0x18002f837  mov     cl, 1
0x18002f839  jmp     short loc_18002F84D
0x18002f83b  jle     short loc_18002F841
0x18002f83d  xor     cl, cl
0x18002f83f  jmp     short loc_18002F84A
0x18002f841  cmp     edi, ebp
0x18002f843  setb    cl
0x18002f846  test    cl, cl
0x18002f848  jnz     short loc_18002F84D
0x18002f84a  mov     r15, rbx
0x18002f84d  lea     rax, [rbx+10h]
0x18002f851  test    cl, cl
0x18002f853  cmovz   rax, rbx
0x18002f857  mov     rbx, [rax]
0x18002f85a  cmp     byte ptr [rbx+19h], 0
0x18002f85e  jz      short loc_18002F800
0x18002f860  cmp     byte ptr [r15+19h], 0
0x18002f865  jnz     short loc_18002F8CD
0x18002f867  mov     ebx, [r15+28h]
0x18002f86b  test    r14, r14
0x18002f86e  jnz     short loc_18002F874
0x18002f870  cmp     esi, ebx
0x18002f872  jmp     short loc_18002F8A3
0x18002f874  mov     edi, esi
0x18002f876  shr     edi, 2
0x18002f879  shr     ebx, 2
0x18002f87c  mov     eax, edi
0x18002f87e  cmp     ebx, edi
0x18002f880  cmovb   eax, ebx
0x18002f883  mov     rdx, [r15+20h]; Buf2
0x18002f887  test    rdx, rdx
0x18002f88a  jz      loc_18002F909
0x18002f890  mov     r8d, eax; Size
0x18002f893  mov     rcx, r14; Buf1
0x18002f896  call    memcmp_0
0x18002f89b  test    eax, eax
0x18002f89d  js      short loc_18002F8CD
0x18002f89f  jg      short loc_18002F8AA
0x18002f8a1  cmp     edi, ebx
0x18002f8a3  setb    al
0x18002f8a6  test    al, al
0x18002f8a8  jnz     short loc_18002F8CD
0x18002f8aa  cmp     r15, r13
0x18002f8ad  jz      short loc_18002F8CD
0x18002f8af  test    r14, r14
0x18002f8b2  jz      short loc_18002F8C7
0x18002f8b4  and     sil, 3
0x18002f8b8  cmp     sil, 1
0x18002f8bc  jnz     short loc_18002F8C7
0x18002f8be  mov     rcx, r14; Block
0x18002f8c1  call    cs:__imp_free
0x18002f8c7  lea     rax, [r15+30h]
0x18002f8cb  jmp     short loc_18002F8E7
0x18002f8cd  test    r14, r14
0x18002f8d0  jz      short loc_18002F8E5
0x18002f8d2  and     sil, 3
0x18002f8d6  cmp     sil, 1
0x18002f8da  jnz     short loc_18002F8E5
0x18002f8dc  mov     rcx, r14; Block
0x18002f8df  call    cs:__imp_free
0x18002f8e5  xor     eax, eax
0x18002f8e7  mov     rcx, [rsp+188h+var_48]
0x18002f8ef  xor     rcx, rsp; StackCookie
0x18002f8f2  call    __security_check_cookie
0x18002f8f7  add     rsp, 150h
0x18002f8fe  pop     r15
0x18002f900  pop     r14
0x18002f902  pop     r13
0x18002f904  pop     rdi
0x18002f905  pop     rsi
0x18002f906  pop     rbp
0x18002f907  pop     rbx
0x18002f908  retn
0x18002f909  lea     rdx, aAssertJsonFail; "assert json failed"
0x18002f910  lea     rcx, [rsp+188h+var_68]
0x18002f918  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002f91d  nop
0x18002f91e  lea     rcx, [rsp+188h+var_68]
0x18002f926  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18002f92c  mov     edx, 1
0x18002f931  lea     rcx, [rsp+188h+var_158]
0x18002f936  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18002f93b  nop
0x18002f93c  lea     rdx, aInJsonValueFin; "in Json::Value::find(key, end, found): "...
0x18002f943  lea     rcx, [rsp+188h+var_158]
0x18002f948  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002f94d  lea     rdx, [rsp+188h+var_68]
0x18002f955  lea     rcx, [rsp+188h+var_158]
0x18002f95a  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::ostringstream::str(void)
0x18002f95f  nop
0x18002f960  mov     rcx, rax
0x18002f963  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18002f969  lea     rdx, aAssertJsonFail; "assert json failed"
0x18002f970  lea     rcx, [rsp+188h+var_68]
0x18002f978  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002f97d  nop
0x18002f97e  lea     rcx, [rsp+188h+var_68]
0x18002f986  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
```
