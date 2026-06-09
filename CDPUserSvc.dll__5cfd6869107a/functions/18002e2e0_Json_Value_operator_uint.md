# Json::Value::operator[](uint)

- ea: `0x18002e2e0`
- end: `0x18002e599`
- name: `??AValue@Json@@QEAAAEAV01@I@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002e260`

## callees

- `0x18000ecb8`
- `0x18002c570`
- `0x18002c5a0`
- `0x18002d510`
- `0x18002d720`
- `0x18002da20`
- `0x18002e030`
- `0x18002e0f0`
- `0x18002e2e0`
- `0x18002e930`
- `0x180030090`
- `0x1800308b0`
- `0x180041074`
- `0x18005a9d0`
- `0x18005af9c`
- `0x18005bd84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e4ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e4ee`

## string_xrefs

- `0x18002e563`: `assert json failed`
- `0x18002e57e`: `assert json failed`
- `0x18002e53a`: `in Json::Value::operator[](ArrayIndex): requires arrayValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Json::Value::operator[](__int64 a1, unsigned int a2)
{
  char v4; // al
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  int v11; // eax
  const struct Json::Value *v13; // rax
  __int64 *v14; // r15
  __int64 v15; // rax
  __int64 inserted; // r13
  __int64 *v17; // rbx
  __int64 v18; // r14
  __int64 *v19; // rsi
  __int64 v20; // rax
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v22; // [rsp+30h] [rbp-D0h]
  _BYTE v23[40]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[240]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v25; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v26; // [rsp+158h] [rbp+58h]
  _QWORD *v27; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v28; // [rsp+178h] [rbp+78h]
  __int128 v29; // [rsp+180h] [rbp+80h]
  __int64 v30; // [rsp+190h] [rbp+90h]

  v4 = *(_BYTE *)(a1 + 8);
  if ( v4 && v4 != 6 )
  {
    std::ostringstream::ostringstream(v24, 1);
    std::operator<<<std::char_traits<char>>(
      (__int64)v24,
      (__int64)"in Json::Value::operator[](ArrayIndex): requires arrayValue");
    v20 = std::ostringstream::str(v24, &v27);
    Json::throwLogicError(v20);
  }
  if ( !v4 )
  {
    LOBYTE(v28) = 6;
    v28 &= ~0x100u;
    v29 = 0;
    v30 = 0;
    v5 = operator new(0x10u);
    v6 = v5;
    if ( v5 )
    {
      *v5 = 0;
      v5[1] = 0;
      v7 = operator new(0x58u);
      *v7 = v7;
      v7[1] = v7;
      v7[2] = v7;
      *((_WORD *)v7 + 12) = 257;
      *v6 = v7;
    }
    else
    {
      v6 = 0;
    }
    v27 = v6;
    Json::Value::operator=(a1, &v27);
  }
  v27 = 0;
  v28 = a2;
  v8 = **(_QWORD **)a1;
  v9 = *(_QWORD *)(v8 + 8);
  v10 = v8;
  if ( !*(_BYTE *)(v9 + 25) )
  {
    do
    {
      if ( *(_QWORD *)(v9 + 32) )
      {
        std::string::string((__int64)&v25, (__int64)"assert json failed");
        Json::throwLogicError(&v25);
      }
      if ( *(_DWORD *)(v9 + 40) >= a2 )
      {
        v10 = v9;
        v9 = *(_QWORD *)v9;
      }
      else
      {
        v9 = *(_QWORD *)(v9 + 16);
      }
    }
    while ( !*(_BYTE *)(v9 + 25) );
    if ( v10 != v8 )
    {
      v11 = *(_DWORD *)(v10 + 40);
      if ( *(_QWORD *)(v10 + 32) )
      {
        if ( ((a2 ^ v11) & 0xFFFFFFFC) == 0 )
        {
          std::string::string((__int64)&v25, (__int64)"assert json failed");
          Json::throwLogicError(&v25);
        }
      }
      else if ( v11 == a2 )
      {
        return v10 + 48;
      }
    }
  }
  v13 = Json::Value::nullSingleton();
  Block = 0;
  v22 = a2;
  Json::Value::Value((Json::Value *)v23, v13);
  v14 = *(__int64 **)a1;
  v15 = std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Find_hint<Json::Value::CZString>(
          (__int64)v14,
          (__int64)&v25,
          v10,
          (__int64)&Block);
  inserted = *(_QWORD *)v15;
  v17 = *(__int64 **)(v15 + 8);
  if ( !*(_BYTE *)(v15 + 16) )
  {
    if ( v14[1] == 0x2E8BA2E8BA2E8BALL )
      std::_Throw_tree_length_error();
    v18 = *v14;
    v25 = v14;
    v26 = 0;
    v19 = (__int64 *)operator new(0x58u);
    v26 = v19;
    Json::Value::CZString::CZString((Json::Value::CZString *)(v19 + 4), (const struct Json::Value::CZString *)&Block);
    Json::Value::Value((Json::Value *)(v19 + 6), (const struct Json::Value *)v23);
    *v19 = v18;
    v19[1] = v18;
    v19[2] = v18;
    *((_WORD *)v19 + 12) = 0;
    v25 = (__int64 *)inserted;
    v26 = v17;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<Json::Value::CZString const,Json::Value>>>::_Insert_node(
                 v14,
                 &v25,
                 v19);
  }
  Json::Value::~Value((Json::Value *)v23);
  if ( Block )
  {
    if ( (v22 & 3) == 1 )
      free(Block);
  }
  return inserted + 48;
}

```

## disassembly

```asm
0x18002e2e0  mov     [rsp-8+arg_8], rbx
0x18002e2e5  mov     [rsp-8+arg_10], rsi
0x18002e2ea  push    rbp
0x18002e2eb  push    rdi
0x18002e2ec  push    r13
0x18002e2ee  push    r14
0x18002e2f0  push    r15
0x18002e2f2  lea     rbp, [rsp-0A0h]
0x18002e2fa  sub     rsp, 1A0h
0x18002e301  mov     rax, cs:__security_cookie
0x18002e308  xor     rax, rsp
0x18002e30b  mov     [rbp+0C0h+var_28], rax
0x18002e312  mov     edi, edx
0x18002e314  mov     r15, rcx
0x18002e317  movzx   eax, byte ptr [rcx+8]
0x18002e31b  test    al, al
0x18002e31d  jz      short loc_18002E327
0x18002e31f  cmp     al, 6
0x18002e321  jnz     loc_18002E52A
0x18002e327  xor     esi, esi
0x18002e329  test    al, al
0x18002e32b  jnz     short loc_18002E39B
0x18002e32d  mov     byte ptr [rbp+0C0h+var_48], 6
0x18002e331  and     [rbp+0C0h+var_48], 0FFFFFEFFh
0x18002e338  xorps   xmm0, xmm0
0x18002e33b  movdqu  [rbp+0C0h+var_40], xmm0
0x18002e343  mov     [rbp+0C0h+var_30], rsi
0x18002e34a  mov     ecx, 10h; Size
0x18002e34f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e354  mov     rbx, rax
0x18002e357  mov     [rsp+1C0h+var_1A0], rax
0x18002e35c  test    rax, rax
0x18002e35f  jz      short loc_18002E388
0x18002e361  mov     [rax], rsi
0x18002e364  mov     [rax+8], rsi
0x18002e368  mov     ecx, 58h ; 'X'; Size
0x18002e36d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e372  mov     [rax], rax
0x18002e375  mov     [rax+8], rax
0x18002e379  mov     [rax+10h], rax
0x18002e37d  mov     word ptr [rax+18h], 101h
0x18002e383  mov     [rbx], rax
0x18002e386  jmp     short loc_18002E38B
0x18002e388  mov     rbx, rsi
0x18002e38b  mov     [rbp+0C0h+var_50], rbx
0x18002e38f  lea     rdx, [rbp+0C0h+var_50]
0x18002e393  mov     rcx, r15
0x18002e396  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18002e39b  mov     [rbp+0C0h+var_50], rsi
0x18002e39f  mov     [rbp+0C0h+var_48], edi
0x18002e3a2  mov     rax, [r15]
0x18002e3a5  mov     rcx, [rax]
0x18002e3a8  mov     rax, [rcx+8]
0x18002e3ac  mov     rbx, rcx
0x18002e3af  cmp     byte ptr [rax+19h], 0
0x18002e3b3  jnz     short loc_18002E400
0x18002e3b5  cmp     qword ptr [rax+20h], 0
0x18002e3ba  jnz     loc_18002E57E
0x18002e3c0  cmp     [rax+28h], edi
0x18002e3c3  jnb     short loc_18002E3CB
0x18002e3c5  mov     rax, [rax+10h]
0x18002e3c9  jmp     short loc_18002E3D1
0x18002e3cb  mov     rbx, rax
0x18002e3ce  mov     rax, [rax]
0x18002e3d1  cmp     byte ptr [rax+19h], 0
0x18002e3d5  jz      short loc_18002E3B5
0x18002e3d7  cmp     rbx, rcx
0x18002e3da  jz      short loc_18002E400
0x18002e3dc  mov     eax, [rbx+28h]
0x18002e3df  cmp     qword ptr [rbx+20h], 0
0x18002e3e4  jnz     short loc_18002E3F3
0x18002e3e6  cmp     eax, edi
0x18002e3e8  jnz     short loc_18002E400
0x18002e3ea  lea     rax, [rbx+30h]
0x18002e3ee  jmp     loc_18002E4F9
0x18002e3f3  xor     eax, edi
0x18002e3f5  test    eax, 0FFFFFFFCh
0x18002e3fa  jz      loc_18002E563
0x18002e400  call    ?nullSingleton@Value@Json@@SAAEBV12@XZ; Json::Value::nullSingleton(void)
0x18002e405  mov     [rsp+1C0h+Block], rsi
0x18002e40a  mov     ecx, edi
0x18002e40c  xor     ecx, edi
0x18002e40e  and     ecx, 3
0x18002e411  xor     ecx, edi
0x18002e413  mov     [rsp+1C0h+var_190], ecx
0x18002e417  mov     rdx, rax; struct Json::Value *
0x18002e41a  lea     rcx, [rsp+1C0h+var_188]; this
0x18002e41f  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x18002e424  nop
0x18002e425  mov     r15, [r15]
0x18002e428  lea     r9, [rsp+1C0h+Block]
0x18002e42d  mov     r8, rbx
0x18002e430  lea     rdx, [rbp+0C0h+var_70]
0x18002e434  mov     rcx, r15
0x18002e437  call    ??$_Find_hint@VCZString@Value@Json@@@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@1@AEBVCZString@Value@Json@@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Find_hint<Json::Value::CZString>(std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *> * const,Json::Value::CZString const &)
0x18002e43c  mov     r13, [rax]
0x18002e43f  mov     rbx, [rax+8]
0x18002e443  cmp     byte ptr [rax+10h], 0
0x18002e447  jnz     loc_18002E4CE
0x18002e44d  mov     rax, 2E8BA2E8BA2E8BAh
0x18002e457  cmp     [r15+8], rax
0x18002e45b  jz      loc_18002E524
0x18002e461  mov     r14, [r15]
0x18002e464  mov     [rbp+0C0h+var_70], r15
0x18002e468  mov     [rbp+0C0h+var_68], rsi
0x18002e46c  mov     ecx, 58h ; 'X'; Size
0x18002e471  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e476  mov     rsi, rax
0x18002e479  mov     [rbp+0C0h+var_68], rax
0x18002e47d  lea     rdi, [rax+20h]
0x18002e481  mov     [rsp+1C0h+var_1A0], rdi
0x18002e486  lea     rdx, [rsp+1C0h+Block]; struct Json::Value::CZString *
0x18002e48b  mov     rcx, rdi; this
0x18002e48e  call    ??0CZString@Value@Json@@QEAA@AEBV012@@Z; Json::Value::CZString::CZString(Json::Value::CZString const &)
0x18002e493  nop
0x18002e494  lea     rcx, [rdi+10h]; this
0x18002e498  lea     rdx, [rsp+1C0h+var_188]; struct Json::Value *
0x18002e49d  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x18002e4a2  nop
0x18002e4a3  mov     [rsi], r14
0x18002e4a6  mov     [rsi+8], r14
0x18002e4aa  mov     [rsi+10h], r14
0x18002e4ae  mov     word ptr [rsi+18h], 0
0x18002e4b4  mov     [rbp+0C0h+var_70], r13
0x18002e4b8  mov     [rbp+0C0h+var_68], rbx
0x18002e4bc  mov     r8, rsi
0x18002e4bf  lea     rdx, [rbp+0C0h+var_70]
0x18002e4c3  mov     rcx, r15
0x18002e4c6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Json::Value::CZString const,Json::Value>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *> *>,std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *> * const)
0x18002e4cb  mov     r13, rax
0x18002e4ce  lea     rcx, [rsp+1C0h+var_188]; this
0x18002e4d3  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18002e4d8  mov     rcx, [rsp+1C0h+Block]; Block
0x18002e4dd  test    rcx, rcx
0x18002e4e0  jz      short loc_18002E4F5
0x18002e4e2  mov     edx, [rsp+1C0h+var_190]
0x18002e4e6  and     dl, 3
0x18002e4e9  cmp     dl, 1
0x18002e4ec  jnz     short loc_18002E4F5
0x18002e4ee  call    cs:__imp_free
0x18002e4f4  nop
0x18002e4f5  lea     rax, [r13+30h]
0x18002e4f9  mov     rcx, [rbp+0C0h+var_28]
0x18002e500  xor     rcx, rsp; StackCookie
0x18002e503  call    __security_check_cookie
0x18002e508  lea     r11, [rsp+1C0h+var_20]
0x18002e510  mov     rbx, [r11+38h]
0x18002e514  mov     rsi, [r11+40h]
0x18002e518  mov     rsp, r11
0x18002e51b  pop     r15
0x18002e51d  pop     r14
0x18002e51f  pop     r13
0x18002e521  pop     rdi
0x18002e522  pop     rbp
0x18002e523  retn
0x18002e524  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18002e52a  mov     edx, 1
0x18002e52f  lea     rcx, [rsp+1C0h+var_160]
0x18002e534  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18002e539  nop
0x18002e53a  lea     rdx, aInJsonValueOpe_0; "in Json::Value::operator[](ArrayIndex):"...
0x18002e541  lea     rcx, [rsp+1C0h+var_160]
0x18002e546  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002e54b  lea     rdx, [rbp+0C0h+var_50]
0x18002e54f  lea     rcx, [rsp+1C0h+var_160]
0x18002e554  call    ?str@?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::ostringstream::str(void)
0x18002e559  nop
0x18002e55a  mov     rcx, rax
0x18002e55d  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18002e563  lea     rdx, aAssertJsonFail; "assert json failed"
0x18002e56a  lea     rcx, [rbp+0C0h+var_70]
0x18002e56e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e573  nop
0x18002e574  lea     rcx, [rbp+0C0h+var_70]
0x18002e578  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18002e57e  lea     rdx, aAssertJsonFail; "assert json failed"
0x18002e585  lea     rcx, [rbp+0C0h+var_70]
0x18002e589  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e58e  nop
0x18002e58f  lea     rcx, [rbp+0C0h+var_70]
0x18002e593  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
```
