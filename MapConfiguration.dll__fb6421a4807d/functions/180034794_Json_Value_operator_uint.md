# Json::Value::operator[](uint)

- ea: `0x180034794`
- end: `0x1800348af`
- name: `??AValue@Json@@QEAAAEAV01@I@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180034714`

## callees

- `0x1800094a0`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002f858`
- `0x180033650`
- `0x1800338cc`
- `0x180034324`
- `0x180034470`
- `0x180034498`
- `0x180034630`
- `0x180034658`
- `0x180034794`
- `0x180035cb4`
- `0x1800360f0`

## string_xrefs

- `0x1800347d1`: `in Json::Value::operator[](ArrayIndex): requires arrayValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Json::Value::operator[](__int64 **a1, int a2)
{
  char v4; // al
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v8; // rbx
  __int64 v9; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v11[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[232]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v13; // [rsp+150h] [rbp+50h] BYREF
  int v14; // [rsp+158h] [rbp+58h]

  v4 = *((_BYTE *)a1 + 8);
  if ( v4 )
  {
    if ( v4 != 6 )
    {
      std::ostringstream::ostringstream((__int64)v11);
      std::operator<<<std::char_traits<char>>(
        (__int64)v11,
        (__int64)"in Json::Value::operator[](ArrayIndex): requires arrayValue");
      std::stringbuf::str(v12, &v13);
      Json::throwLogicError(&v13);
    }
  }
  else
  {
    v5 = Json::Value::Value((__int64)&v13, 6);
    Json::Value::operator=(a1, v5);
  }
  v13 = 0;
  v14 = a2;
  std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::lower_bound(
    *a1,
    &v9,
    &v13);
  v6 = v9;
  if ( v9 == **a1 || !(unsigned __int8)Json::Value::CZString::operator==(v9 + 32, &v13) )
  {
    std::pair<Json::Value::CZString const,Json::Value>::pair<Json::Value::CZString const,Json::Value>(
      (__int64)v10,
      (const struct Json::Value::CZString *)&v13);
    v8 = std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Emplace_hint<std::pair<Json::Value::CZString const,Json::Value> &>(
           *a1,
           v6,
           (__int64)v10)
       + 48;
    std::pair<Json::Value::CZString const,Json::Value>::~pair<Json::Value::CZString const,Json::Value>((Json::Value::CZString *)v10);
    Json::Value::CZString::~CZString((Json::Value::CZString *)&v13);
    return v8;
  }
  else
  {
    Json::Value::CZString::~CZString((Json::Value::CZString *)&v13);
    return v6 + 48;
  }
}

```

## disassembly

```asm
0x180034794  push    rbp
0x180034796  push    rbx
0x180034797  push    rsi
0x180034798  push    rdi
0x180034799  lea     rbp, [rsp-88h]
0x1800347a1  sub     rsp, 188h
0x1800347a8  mov     rax, cs:__security_cookie
0x1800347af  xor     rax, rsp
0x1800347b2  mov     [rbp+0A0h+var_28], rax
0x1800347b6  mov     ebx, edx
0x1800347b8  mov     rdi, rcx
0x1800347bb  mov     al, [rcx+8]
0x1800347be  test    al, al
0x1800347c0  jz      short loc_1800347FB
0x1800347c2  cmp     al, 6
0x1800347c4  jz      short loc_180034814
0x1800347c6  lea     rcx, [rsp+1A0h+var_140]
0x1800347cb  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800347d0  nop
0x1800347d1  lea     rdx, aInJsonValueOpe_0; "in Json::Value::operator[](ArrayIndex):"...
0x1800347d8  lea     rcx, [rsp+1A0h+var_140]
0x1800347dd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800347e2  lea     rdx, [rbp+0A0h+var_50]
0x1800347e6  lea     rcx, [rsp+1A0h+var_138]
0x1800347eb  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800347f0  nop
0x1800347f1  lea     rcx, [rbp+0A0h+var_50]
0x1800347f5  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x1800347fb  mov     edx, 6
0x180034800  lea     rcx, [rbp+0A0h+var_50]
0x180034804  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180034809  mov     rdx, rax
0x18003480c  mov     rcx, rdi
0x18003480f  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180034814  mov     [rbp+0A0h+var_50], 0
0x18003481c  mov     [rbp+0A0h+var_48], ebx
0x18003481f  lea     r8, [rbp+0A0h+var_50]
0x180034823  lea     rdx, [rsp+1A0h+var_180]
0x180034828  mov     rcx, [rdi]
0x18003482b  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@@2@AEBVCZString@Value@Json@@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::lower_bound(Json::Value::CZString const &)
0x180034830  mov     rax, [rdi]
0x180034833  mov     rbx, [rsp+1A0h+var_180]
0x180034838  cmp     rbx, [rax]
0x18003483b  jz      short loc_18003485D
0x18003483d  lea     rdx, [rbp+0A0h+var_50]
0x180034841  lea     rcx, [rbx+20h]
0x180034845  call    ??8CZString@Value@Json@@QEBA_NAEBV012@@Z; Json::Value::CZString::operator==(Json::Value::CZString const &)
0x18003484a  test    al, al
0x18003484c  jz      short loc_18003485D
0x18003484e  lea     rcx, [rbp+0A0h+var_50]; this
0x180034852  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x180034857  lea     rax, [rbx+30h]
0x18003485b  jmp     short loc_180034897
0x18003485d  lea     rdx, [rbp+0A0h+var_50]
0x180034861  lea     rcx, [rsp+1A0h+var_178]
0x180034866  call    ??$?0AEAVCZString@Value@Json@@AEBV12@$0A@@?$pair@$$CBVCZString@Value@Json@@V23@@std@@QEAA@AEAVCZString@Value@Json@@AEBV34@@Z; std::pair<Json::Value::CZString const,Json::Value>::pair<Json::Value::CZString const,Json::Value>(Json::Value::CZString &,Json::Value const &)
0x18003486b  nop
0x18003486c  lea     r8, [rsp+1A0h+var_178]
0x180034871  mov     rdx, rbx
0x180034874  mov     rcx, [rdi]
0x180034877  call    ??$_Emplace_hint@AEAU?$pair@$$CBVCZString@Value@Json@@V23@@std@@@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@1@QEAU21@AEAU?$pair@$$CBVCZString@Value@Json@@V23@@1@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Emplace_hint<std::pair<Json::Value::CZString const,Json::Value> &>(std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *> * const,std::pair<Json::Value::CZString const,Json::Value> &)
0x18003487c  lea     rbx, [rax+30h]
0x180034880  lea     rcx, [rsp+1A0h+var_178]; this
0x180034885  call    ??1?$pair@$$CBVCZString@Value@Json@@V23@@std@@QEAA@XZ; std::pair<Json::Value::CZString const,Json::Value>::~pair<Json::Value::CZString const,Json::Value>(void)
0x18003488a  nop
0x18003488b  lea     rcx, [rbp+0A0h+var_50]; this
0x18003488f  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x180034894  mov     rax, rbx
0x180034897  mov     rcx, [rbp+0A0h+var_28]
0x18003489b  xor     rcx, rsp; StackCookie
0x18003489e  call    __security_check_cookie
0x1800348a3  add     rsp, 188h
0x1800348aa  pop     rdi
0x1800348ab  pop     rsi
0x1800348ac  pop     rbx
0x1800348ad  pop     rbp
0x1800348ae  retn
```
