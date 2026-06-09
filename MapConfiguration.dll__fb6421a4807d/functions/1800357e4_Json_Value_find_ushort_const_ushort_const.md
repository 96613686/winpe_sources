# Json::Value::find(ushort const *,ushort const *)

- ea: `0x1800357e4`
- end: `0x1800358c6`
- name: `?find@Value@Json@@QEBAPEBV12@PEBG0@Z`
- size: `226`
- prototype: `const struct Json::Value *__fastcall(Json::Value *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800348d8`
- `0x180034a00`
- `0x1800358cc`
- `0x180035ba0`

## callees

- `0x1800094a0`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002f858`
- `0x180034498`
- `0x18003578c`
- `0x1800357e4`
- `0x1800360f0`

## string_xrefs

- `0x18003581c`: `in Json::Value::find(key, end, found): requires objectValue or nullValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const struct Json::Value *__fastcall Json::Value::find(
        Json::Value *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char v4; // al
  _QWORD *v5; // rax
  __int64 v7; // rbx
  _BYTE v8[16]; // [rsp+20h] [rbp-138h] BYREF
  _BYTE v9[8]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v10[232]; // [rsp+38h] [rbp-120h] BYREF
  const unsigned __int16 *v11; // [rsp+120h] [rbp-38h] BYREF
  int v12; // [rsp+128h] [rbp-30h]

  v4 = *((_BYTE *)this + 8);
  if ( !v4 )
    return 0;
  if ( v4 != 7 )
  {
    std::ostringstream::ostringstream((__int64)v9);
    std::operator<<<std::char_traits<char>>(
      (__int64)v9,
      (__int64)"in Json::Value::find(key, end, found): requires objectValue or nullValue");
    std::stringbuf::str(v10, &v11);
    Json::throwLogicError(&v11);
  }
  v11 = a2;
  v12 = 4 * (a3 - a2);
  v5 = (_QWORD *)std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::find(
                   *(_QWORD *)this,
                   v8,
                   &v11);
  if ( *v5 == **(_QWORD **)this )
  {
    Json::Value::CZString::~CZString((Json::Value::CZString *)&v11);
    return 0;
  }
  v7 = *v5 + 48LL;
  Json::Value::CZString::~CZString((Json::Value::CZString *)&v11);
  return (const struct Json::Value *)v7;
}

```

## disassembly

```asm
0x1800357e4  push    rbx
0x1800357e6  sub     rsp, 150h
0x1800357ed  mov     rax, cs:__security_cookie
0x1800357f4  xor     rax, rsp
0x1800357f7  mov     [rsp+158h+var_18], rax
0x1800357ff  mov     rbx, rcx
0x180035802  mov     al, [rcx+8]
0x180035805  test    al, al
0x180035807  jz      loc_180035895
0x18003580d  cmp     al, 7
0x18003580f  jz      short loc_18003584E
0x180035811  lea     rcx, [rsp+158h+var_128]
0x180035816  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003581b  nop
0x18003581c  lea     rdx, aInJsonValueFin; "in Json::Value::find(key, end, found): "...
0x180035823  lea     rcx, [rsp+158h+var_128]
0x180035828  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003582d  lea     rdx, [rsp+158h+var_38]
0x180035835  lea     rcx, [rsp+158h+var_120]
0x18003583a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18003583f  nop
0x180035840  lea     rcx, [rsp+158h+var_38]
0x180035848  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18003584e  mov     [rsp+158h+var_38], rdx
0x180035856  sub     r8, rdx
0x180035859  sar     r8, 1
0x18003585c  shl     r8d, 2
0x180035860  mov     [rsp+158h+var_30], r8d
0x180035868  lea     r8, [rsp+158h+var_38]
0x180035870  lea     rdx, [rsp+158h+var_138]
0x180035875  mov     rcx, [rcx]
0x180035878  call    ?find@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@@2@AEBVCZString@Value@Json@@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::find(Json::Value::CZString const &)
0x18003587d  mov     rcx, [rax]
0x180035880  mov     rax, [rbx]
0x180035883  cmp     rcx, [rax]
0x180035886  jnz     short loc_1800358B0
0x180035888  lea     rcx, [rsp+158h+var_38]; this
0x180035890  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x180035895  xor     eax, eax
0x180035897  mov     rcx, [rsp+158h+var_18]
0x18003589f  xor     rcx, rsp; StackCookie
0x1800358a2  call    __security_check_cookie
0x1800358a7  add     rsp, 150h
0x1800358ae  pop     rbx
0x1800358af  retn
0x1800358b0  lea     rbx, [rcx+30h]
0x1800358b4  lea     rcx, [rsp+158h+var_38]; this
0x1800358bc  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x1800358c1  mov     rax, rbx
0x1800358c4  jmp     short loc_180035897
```
