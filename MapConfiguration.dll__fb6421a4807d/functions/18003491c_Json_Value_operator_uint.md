# Json::Value::operator[](uint)

- ea: `0x18003491c`
- end: `0x1800349f8`
- name: `??AValue@Json@@QEBAAEBV01@I@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003a7e0`

## callees

- `0x1800094a0`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002f858`
- `0x180034498`
- `0x18003491c`
- `0x18003578c`
- `0x1800360f0`

## string_xrefs

- `0x180034954`: `in Json::Value::operator[](ArrayIndex)const: requires arrayValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Json::Value *__fastcall Json::Value::operator[](__int64 a1, int a2)
{
  char v3; // al
  _QWORD *v4; // rax
  struct Json::Value *v5; // rbx
  _BYTE v7[16]; // [rsp+20h] [rbp-138h] BYREF
  _BYTE v8[8]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v9[232]; // [rsp+38h] [rbp-120h] BYREF
  __int64 v10; // [rsp+120h] [rbp-38h] BYREF
  int v11; // [rsp+128h] [rbp-30h]

  v3 = *(_BYTE *)(a1 + 8);
  if ( !v3 )
    return Json::Value::nullRef;
  if ( v3 != 6 )
  {
    std::ostringstream::ostringstream((__int64)v8);
    std::operator<<<std::char_traits<char>>(
      (__int64)v8,
      (__int64)"in Json::Value::operator[](ArrayIndex)const: requires arrayValue");
    std::stringbuf::str(v9, &v10);
    Json::throwLogicError(&v10);
  }
  v10 = 0;
  v11 = a2;
  v4 = (_QWORD *)std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::find(
                   *(_QWORD *)a1,
                   v7,
                   &v10);
  if ( *v4 == **(_QWORD **)a1 )
    v5 = Json::Value::nullRef;
  else
    v5 = (struct Json::Value *)(*v4 + 48LL);
  Json::Value::CZString::~CZString((Json::Value::CZString *)&v10);
  return v5;
}

```

## disassembly

```asm
0x18003491c  push    rbx
0x18003491e  sub     rsp, 150h
0x180034925  mov     rax, cs:__security_cookie
0x18003492c  xor     rax, rsp
0x18003492f  mov     [rsp+158h+var_18], rax
0x180034937  mov     rbx, rcx
0x18003493a  mov     al, [rcx+8]
0x18003493d  test    al, al
0x18003493f  jz      loc_1800349D8
0x180034945  cmp     al, 6
0x180034947  jz      short loc_180034986
0x180034949  lea     rcx, [rsp+158h+var_128]
0x18003494e  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180034953  nop
0x180034954  lea     rdx, aInJsonValueOpe_1; "in Json::Value::operator[](ArrayIndex)c"...
0x18003495b  lea     rcx, [rsp+158h+var_128]
0x180034960  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180034965  lea     rdx, [rsp+158h+var_38]
0x18003496d  lea     rcx, [rsp+158h+var_120]
0x180034972  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180034977  nop
0x180034978  lea     rcx, [rsp+158h+var_38]
0x180034980  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x180034986  mov     [rsp+158h+var_38], 0
0x180034992  mov     [rsp+158h+var_30], edx
0x180034999  lea     r8, [rsp+158h+var_38]
0x1800349a1  lea     rdx, [rsp+158h+var_138]
0x1800349a6  mov     rcx, [rcx]
0x1800349a9  call    ?find@?$_Tree@V?$_Tmap_traits@VCZString@Value@Json@@V23@U?$less@VCZString@Value@Json@@@std@@V?$allocator@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@@2@AEBVCZString@Value@Json@@@Z; std::_Tree<std::_Tmap_traits<Json::Value::CZString,Json::Value,std::less<Json::Value::CZString>,std::allocator<std::pair<Json::Value::CZString const,Json::Value>>,0>>::find(Json::Value::CZString const &)
0x1800349ae  mov     rcx, [rax]
0x1800349b1  mov     rax, [rbx]
0x1800349b4  cmp     rcx, [rax]
0x1800349b7  jnz     short loc_1800349D2
0x1800349b9  mov     rbx, cs:?nullRef@Value@Json@@2AEBV12@EB; Json::Value const & const Json::Value::nullRef
0x1800349c0  lea     rcx, [rsp+158h+var_38]; this
0x1800349c8  call    ??1CZString@Value@Json@@QEAA@XZ; Json::Value::CZString::~CZString(void)
0x1800349cd  mov     rax, rbx
0x1800349d0  jmp     short loc_1800349DF
0x1800349d2  lea     rbx, [rcx+30h]
0x1800349d6  jmp     short loc_1800349C0
0x1800349d8  mov     rax, cs:?nullRef@Value@Json@@2AEBV12@EB; Json::Value const & const Json::Value::nullRef
0x1800349df  mov     rcx, [rsp+158h+var_18]
0x1800349e7  xor     rcx, rsp; StackCookie
0x1800349ea  call    __security_check_cookie
0x1800349ef  add     rsp, 150h
0x1800349f6  pop     rbx
0x1800349f7  retn
```
