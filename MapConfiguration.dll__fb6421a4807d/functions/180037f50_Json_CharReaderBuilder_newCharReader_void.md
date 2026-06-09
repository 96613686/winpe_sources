# Json::CharReaderBuilder::newCharReader(void)

- ea: `0x180037f50`
- end: `0x1800380b3`
- name: `?newCharReader@CharReaderBuilder@Json@@UEBAPEAVCharReader@2@XZ`
- size: `355`
- prototype: `struct Json::CharReader *__fastcall(Json::CharReaderBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800217dc`

## callees

- `0x180009988`
- `0x180034a00`
- `0x180034ca0`
- `0x180034f8c`
- `0x180036674`

## string_xrefs

- `0x180037f89`: `allowComments`
- `0x180037f66`: `collectComments`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Json::CharReader *__fastcall Json::CharReaderBuilder::newCharReader(Json::CharReaderBuilder *this)
{
  char *v1; // rbx
  Json::Value *v2; // rax
  bool v3; // di
  Json::Value *v4; // rax
  Json::Value *v5; // rax
  Json::Value *v6; // rax
  Json::Value *v7; // rax
  Json::Value *v8; // rax
  Json::Value *v9; // rax
  Json::Value *v10; // rax
  Json::Value *v11; // rax
  Json::Value *v12; // rax
  _BYTE v14[8]; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+28h] [rbp-8h]
  char *v16; // [rsp+40h] [rbp+10h]

  v1 = (char *)this + 8;
  v2 = (Json::Value *)Json::Value::operator[]((char *)this + 8, L"collectComments");
  v3 = Json::Value::asBool(v2);
  v4 = (Json::Value *)Json::Value::operator[](v1, L"allowComments");
  v14[0] = Json::Value::asBool(v4);
  v5 = (Json::Value *)Json::Value::operator[](v1, L"strictRoot");
  v14[1] = Json::Value::asBool(v5);
  v6 = (Json::Value *)Json::Value::operator[](v1, L"allowDroppedNullPlaceholders");
  v14[2] = Json::Value::asBool(v6);
  v7 = (Json::Value *)Json::Value::operator[](v1, L"allowNumericKeys");
  v14[3] = Json::Value::asBool(v7);
  v8 = (Json::Value *)Json::Value::operator[](v1, L"allowSingleQuotes");
  v14[4] = Json::Value::asBool(v8);
  v9 = (Json::Value *)Json::Value::operator[](v1, L"stackLimit");
  v15 = Json::Value::asInt(v9);
  v10 = (Json::Value *)Json::Value::operator[](v1, L"failIfExtra");
  v14[5] = Json::Value::asBool(v10);
  v11 = (Json::Value *)Json::Value::operator[](v1, L"rejectDupKeys");
  v14[6] = Json::Value::asBool(v11);
  v12 = (Json::Value *)Json::Value::operator[](v1, L"allowSpecialFloats");
  v14[7] = Json::Value::asBool(v12);
  v16 = (char *)operator new(0xE0u);
  *(_QWORD *)v16 = &Json::OurCharReader::`vftable';
  v16[8] = v3;
  Json::OurReader::OurReader((Json::OurReader *)(v16 + 16), (const struct Json::OurFeatures *)v14);
  return (struct Json::CharReader *)v16;
}

```

## disassembly

```asm
0x180037f50  mov     [rsp-8+arg_8], rbx
0x180037f55  mov     [rsp-8+arg_10], rdi
0x180037f5a  push    rbp
0x180037f5b  mov     rbp, rsp
0x180037f5e  sub     rsp, 30h
0x180037f62  lea     rbx, [rcx+8]
0x180037f66  lea     rdx, aCollectcomment; "collectComments"
0x180037f6d  mov     rcx, rbx
0x180037f70  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180037f75  mov     rcx, rax; this
0x180037f78  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180037f7d  mov     dil, al
0x180037f80  xor     eax, eax
0x180037f82  mov     [rbp+var_10], rax
0x180037f86  mov     [rbp+var_8], eax
0x180037f89  lea     rdx, aAllowcomments; "allowComments"
0x180037f90  mov     rcx, rbx
0x180037f93  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180037f98  mov     rcx, rax; this
0x180037f9b  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180037fa0  mov     byte ptr [rbp+var_10], al
0x180037fa3  lea     rdx, aStrictroot; "strictRoot"
0x180037faa  mov     rcx, rbx
0x180037fad  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180037fb2  mov     rcx, rax; this
0x180037fb5  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180037fba  mov     byte ptr [rbp+var_10+1], al
0x180037fbd  lea     rdx, aAllowdroppednu; "allowDroppedNullPlaceholders"
0x180037fc4  mov     rcx, rbx
0x180037fc7  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180037fcc  mov     rcx, rax; this
0x180037fcf  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180037fd4  mov     byte ptr [rbp+var_10+2], al
0x180037fd7  lea     rdx, aAllownumericke; "allowNumericKeys"
0x180037fde  mov     rcx, rbx
0x180037fe1  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180037fe6  mov     rcx, rax; this
0x180037fe9  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180037fee  mov     byte ptr [rbp+var_10+3], al
0x180037ff1  lea     rdx, aAllowsinglequo; "allowSingleQuotes"
0x180037ff8  mov     rcx, rbx
0x180037ffb  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180038000  mov     rcx, rax; this
0x180038003  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180038008  mov     byte ptr [rbp+var_10+4], al
0x18003800b  lea     rdx, aStacklimit; "stackLimit"
0x180038012  mov     rcx, rbx
0x180038015  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003801a  mov     rcx, rax; this
0x18003801d  call    ?asInt@Value@Json@@QEBAHXZ; Json::Value::asInt(void)
0x180038022  mov     [rbp+var_8], eax
0x180038025  lea     rdx, aFailifextra; "failIfExtra"
0x18003802c  mov     rcx, rbx
0x18003802f  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180038034  mov     rcx, rax; this
0x180038037  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x18003803c  mov     byte ptr [rbp+var_10+5], al
0x18003803f  lea     rdx, aRejectdupkeys; "rejectDupKeys"
0x180038046  mov     rcx, rbx
0x180038049  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003804e  mov     rcx, rax; this
0x180038051  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180038056  mov     byte ptr [rbp+var_10+6], al
0x180038059  lea     rdx, aAllowspecialfl; "allowSpecialFloats"
0x180038060  mov     rcx, rbx
0x180038063  call    ??AValue@Json@@QEBAAEBV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180038068  mov     rcx, rax; this
0x18003806b  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x180038070  mov     byte ptr [rbp+var_10+7], al
0x180038073  mov     ecx, 0E0h; Size
0x180038078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003807d  mov     rbx, rax
0x180038080  mov     [rbp+arg_0], rax
0x180038084  lea     rax, ??_7OurCharReader@Json@@6B@; const Json::OurCharReader::`vftable'
0x18003808b  mov     [rbx], rax
0x18003808e  mov     [rbx+8], dil
0x180038092  lea     rcx, [rbx+10h]; this
0x180038096  lea     rdx, [rbp+var_10]; struct Json::OurFeatures *
0x18003809a  call    ??0OurReader@Json@@QEAA@AEBVOurFeatures@1@@Z; Json::OurReader::OurReader(Json::OurFeatures const &)
0x18003809f  nop
0x1800380a0  mov     rax, rbx
0x1800380a3  mov     rbx, [rsp+30h+arg_8]
0x1800380a8  mov     rdi, [rsp+30h+arg_10]
0x1800380ad  add     rsp, 30h
0x1800380b1  pop     rbp
0x1800380b2  retn
```
