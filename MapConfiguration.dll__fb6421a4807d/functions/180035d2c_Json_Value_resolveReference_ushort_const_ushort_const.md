# Json::Value::resolveReference(ushort const *,ushort const *)

- ea: `0x180035d2c`
- end: `0x180035e53`
- name: `?resolveReference@Value@Json@@AEAAAEAV12@PEBG0@Z`
- size: `295`
- prototype: `struct Json::Value *__fastcall(Json::Value *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800346dc`
- `0x1800348b8`

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
- `0x180035cb4`
- `0x180035d2c`
- `0x1800360f0`

## string_xrefs

- `0x180035d6d`: `in Json::Value::resolveReference(key, end): requires objectValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct Json::Value *__fastcall Json::Value::resolveReference(
        Json::Value *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char v6; // al
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v10; // rbx
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v12[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[232]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v15; // [rsp+150h] [rbp+50h] BYREF
  int v16; // [rsp+158h] [rbp+58h]

  v6 = *((_BYTE *)this + 8);
  if ( v6 )
  {
    if ( v6 != 7 )
    {
      std::ostringstream::ostringstream((__int64)v13);
      std::operator<<<std::char_traits<char>>(
        (__int64)v13,
        (__int64)"in Json::Value::resolveReference(key, end): requires objectValue");
      std::stringbuf::str(v14, &v15);
      Json::throwLogicError(&v15);
    }
  }
  else
  {
    v7 = Json::Value::Value((__int64)&v15, 7);
    Json::Value::operator=(this, v7);
  }
  v15 = a2;
  v16 = (4 * (a3 - a2)) | 2;
  std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::lower_bound(
    *(_QWORD *)this,
    &v11,
    &v15);
  v8 = v11;
  if ( v11 == **(_QWORD **)this || !(unsigned __int8)Json::Value::CZString::operator==(v11 + 32, &v15) )
  {
    std::pair<Json::Value::CZString const,Json::Value>::pair<Json::Value::CZString const,Json::Value>(
      (__int64)v12,
      (const struct Json::Value::CZString *)&v15);
    v10 = std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Emplace_hint<std::pair<Json::Value::CZString const,Json::Value> &>(
            *(__int64 **)this,
            v8,
            (__int64)v12)
        + 48;
    std::pair<Json::Value::CZString const,Json::Value>::~pair<Json::Value::CZString const,Json::Value>((Json::Value::CZString *)v12);
    Json::Value::CZString::~CZString((Json::Value::CZString *)&v15);
    return (struct Json::Value *)v10;
  }
  else
  {
    Json::Value::CZString::~CZString((Json::Value::CZString *)&v15);
    return (struct Json::Value *)(v8 + 48);
  }
}

```

## disassembly

```asm
0x180035d2c  push    rbp
0x180035d2e  push    rbx
0x180035d2f  push    rsi
0x180035d30  push    rdi
0x180035d31  lea     rbp, [rsp-88h]
0x180035d39  sub     rsp, 188h
0x180035d40  mov     rax, cs:__security_cookie
0x180035d47  xor     rax, rsp
0x180035d4a  mov     [rbp+0A0h+var_28], rax
0x180035d4e  mov     rbx, r8
0x180035d51  mov     rdi, rdx
0x180035d54  mov     rsi, rcx
0x180035d57  mov     al, [rcx+8]
0x180035d5a  test    al, al
0x180035d5c  jz      short loc_180035D97
0x180035d5e  cmp     al, 7
0x180035d60  jz      short loc_180035DB0
0x180035d62  lea     rcx, [rsp+1A0h+var_140]
0x180035d67  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180035d6c  nop
0x180035d6d  lea     rdx, aInJsonValueRes; "in Json::Value::resolveReference(key, e"...
0x180035d74  lea     rcx, [rsp+1A0h+var_140]
0x180035d79  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180035d7e  lea     rdx, [rbp+0A0h+var_50]
0x180035d82  lea     rcx, [rsp+1A0h+var_138]
0x180035d87  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180035d8c  nop
0x180035d8d  lea     rcx, [rbp+0A0h+var_50]
0x180035d91  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x180035d97  mov     edx, 7
0x180035d9c  lea     rcx, [rbp+0A0h+var_50]
0x180035da0  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180035da5  mov     rdx, rax
0x180035da8  mov     rcx, rsi
0x180035dab  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180035db0  mov     [rbp+0A0h+var_50], rdi
0x180035db4  sub     rbx, rdi
0x180035db7  sar     rbx, 1
0x180035dba  shl     ebx, 2
0x180035dbd  or      ebx, 2
0x180035dc0  mov     [rbp+0A0h+var_48], ebx
0x180035dc3  lea     r8, [rbp+0A0h+var_50]
0x180035dc7  lea     rdx, [rsp+1A0h+var_180]
0x180035dcc  mov     rcx, [rsi]
0x180035dcf  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@@2@AEBVCZString@Value@Json@@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::lower_bound(Json::Value::CZString const &)
0x180035dd4  mov     rax, [rsi]
0x180035dd7  mov     rbx, [rsp+1A0h+var_180]
0x180035ddc  cmp     rbx, [rax]
0x180035ddf  jz      short loc_180035E01
0x180035de1  lea     rdx, [rbp+0A0h+var_50]
0x180035de5  lea     rcx, [rbx+20h]
0x180035de9  call    ??8CZString@Value@Json@@QEBA_NAEBV012@@Z; Json::Value::CZString::operator==(Json::Value::CZString const &)
0x180035dee  test    al, al
0x180035df0  jz      short loc_180035E01
0x180035df2  lea     rcx, [rbp+0A0h+var_50]; this
0x180035df6  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x180035dfb  lea     rax, [rbx+30h]
0x180035dff  jmp     short loc_180035E3B
0x180035e01  lea     rdx, [rbp+0A0h+var_50]
0x180035e05  lea     rcx, [rsp+1A0h+var_178]
0x180035e0a  call    ??$?0AEAVCZString@Value@Json@@AEBV12@$0A@@?$pair@$$CBVCZString@Value@Json@@V23@@std@@QEAA@AEAVCZString@Value@Json@@AEBV34@@Z; std::pair<Json::Value::CZString const,Json::Value>::pair<Json::Value::CZString const,Json::Value>(Json::Value::CZString &,Json::Value const &)
0x180035e0f  nop
0x180035e10  lea     r8, [rsp+1A0h+var_178]
0x180035e15  mov     rdx, rbx
0x180035e18  mov     rcx, [rsi]
0x180035e1b  call    ??$_Emplace_hint@AEAU?$pair@$$CBVCZString@Value@Json@@V23@@std@@@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@1@QEAU21@AEAU?$pair@$$CBVCZString@Value@Json@@V23@@1@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::_Emplace_hint<std::pair<Json::Value::CZString const,Json::Value> &>(std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *> * const,std::pair<Json::Value::CZString const,Json::Value> &)
0x180035e20  lea     rbx, [rax+30h]
0x180035e24  lea     rcx, [rsp+1A0h+var_178]; this
0x180035e29  call    ??1?$pair@$$CBVCZString@Value@Json@@V23@@std@@QEAA@XZ; std::pair<Json::Value::CZString const,Json::Value>::~pair<Json::Value::CZString const,Json::Value>(void)
0x180035e2e  nop
0x180035e2f  lea     rcx, [rbp+0A0h+var_50]; this
0x180035e33  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x180035e38  mov     rax, rbx
0x180035e3b  mov     rcx, [rbp+0A0h+var_28]
0x180035e3f  xor     rcx, rsp; StackCookie
0x180035e42  call    __security_check_cookie
0x180035e47  add     rsp, 188h
0x180035e4e  pop     rdi
0x180035e4f  pop     rsi
0x180035e50  pop     rbx
0x180035e51  pop     rbp
0x180035e52  retn
```
