# Json::CharReaderBuilder::setDefaults(Json::Value *)

- ea: `0x1800396ec`
- end: `0x180039950`
- name: `?setDefaults@CharReaderBuilder@Json@@SAXPEAVValue@2@@Z`
- size: `612`
- prototype: `void __fastcall(struct Json::Value *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003662c`

## callees

- `0x180034630`
- `0x1800348b8`

## string_xrefs

- `0x180039758`: `allowComments`
- `0x180039721`: `collectComments`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Json::CharReaderBuilder::setDefaults(struct Json::Value *a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+28h] [rbp-30h]
  __int128 v14; // [rsp+30h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-18h]

  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 1;
  v2 = Json::Value::operator[](a1, L"collectComments");
  Json::Value::operator=(v2, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 1;
  v3 = Json::Value::operator[](a1, L"allowComments");
  Json::Value::operator=(v3, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v4 = Json::Value::operator[](a1, L"strictRoot");
  Json::Value::operator=(v4, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v5 = Json::Value::operator[](a1, L"allowDroppedNullPlaceholders");
  Json::Value::operator=(v5, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v6 = Json::Value::operator[](a1, L"allowNumericKeys");
  Json::Value::operator=(v6, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v7 = Json::Value::operator[](a1, L"allowSingleQuotes");
  Json::Value::operator=(v7, &v12);
  LOBYTE(v13) = 1;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  v12 = 1000;
  v8 = Json::Value::operator[](a1, L"stackLimit");
  Json::Value::operator=(v8, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v9 = Json::Value::operator[](a1, L"failIfExtra");
  Json::Value::operator=(v9, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v10 = Json::Value::operator[](a1, L"rejectDupKeys");
  Json::Value::operator=(v10, &v12);
  LOBYTE(v13) = 5;
  v13 &= ~0x100u;
  v14 = 0;
  v15 = 0;
  LOBYTE(v12) = 0;
  v11 = Json::Value::operator[](a1, L"allowSpecialFloats");
  Json::Value::operator=(v11, &v12);
}

```

## disassembly

```asm
0x1800396ec  push    rbp
0x1800396ee  push    rbx
0x1800396ef  push    rsi
0x1800396f0  push    rdi
0x1800396f1  mov     rbp, rsp
0x1800396f4  sub     rsp, 58h
0x1800396f8  mov     rbx, rcx
0x1800396fb  lea     rax, [rbp+var_38]
0x1800396ff  mov     [rbp+arg_8], rax
0x180039703  mov     byte ptr [rbp+var_30], 5
0x180039707  mov     edi, 0FFFFFEFFh
0x18003970c  and     [rbp+var_30], edi
0x18003970f  xorps   xmm0, xmm0
0x180039712  movdqu  [rbp+var_28], xmm0
0x180039717  xor     esi, esi
0x180039719  mov     [rbp+var_18], rsi
0x18003971d  mov     byte ptr [rbp+var_38], 1
0x180039721  lea     rdx, aCollectcomment; "collectComments"
0x180039728  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003972d  mov     rcx, rax
0x180039730  lea     rdx, [rbp+var_38]
0x180039734  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180039739  lea     rax, [rbp+var_38]
0x18003973d  mov     [rbp+arg_8], rax
0x180039741  mov     byte ptr [rbp+var_30], 5
0x180039745  and     [rbp+var_30], edi
0x180039748  xorps   xmm0, xmm0
0x18003974b  movdqu  [rbp+var_28], xmm0
0x180039750  mov     [rbp+var_18], rsi
0x180039754  mov     byte ptr [rbp+var_38], 1
0x180039758  lea     rdx, aAllowcomments; "allowComments"
0x18003975f  mov     rcx, rbx
0x180039762  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180039767  mov     rcx, rax
0x18003976a  lea     rdx, [rbp+var_38]
0x18003976e  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180039773  lea     rax, [rbp+var_38]
0x180039777  mov     [rbp+arg_8], rax
0x18003977b  mov     byte ptr [rbp+var_30], 5
0x18003977f  and     [rbp+var_30], edi
0x180039782  xorps   xmm0, xmm0
0x180039785  movdqu  [rbp+var_28], xmm0
0x18003978a  mov     [rbp+var_18], rsi
0x18003978e  mov     byte ptr [rbp+var_38], sil
0x180039792  lea     rdx, aStrictroot; "strictRoot"
0x180039799  mov     rcx, rbx
0x18003979c  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x1800397a1  mov     rcx, rax
0x1800397a4  lea     rdx, [rbp+var_38]
0x1800397a8  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x1800397ad  lea     rax, [rbp+var_38]
0x1800397b1  mov     [rbp+arg_8], rax
0x1800397b5  mov     byte ptr [rbp+var_30], 5
0x1800397b9  and     [rbp+var_30], edi
0x1800397bc  xorps   xmm0, xmm0
0x1800397bf  movdqu  [rbp+var_28], xmm0
0x1800397c4  mov     [rbp+var_18], rsi
0x1800397c8  mov     byte ptr [rbp+var_38], sil
0x1800397cc  lea     rdx, aAllowdroppednu; "allowDroppedNullPlaceholders"
0x1800397d3  mov     rcx, rbx
0x1800397d6  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x1800397db  mov     rcx, rax
0x1800397de  lea     rdx, [rbp+var_38]
0x1800397e2  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x1800397e7  lea     rax, [rbp+var_38]
0x1800397eb  mov     [rbp+arg_8], rax
0x1800397ef  mov     byte ptr [rbp+var_30], 5
0x1800397f3  and     [rbp+var_30], edi
0x1800397f6  xorps   xmm0, xmm0
0x1800397f9  movdqu  [rbp+var_28], xmm0
0x1800397fe  mov     [rbp+var_18], rsi
0x180039802  mov     byte ptr [rbp+var_38], sil
0x180039806  lea     rdx, aAllownumericke; "allowNumericKeys"
0x18003980d  mov     rcx, rbx
0x180039810  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180039815  mov     rcx, rax
0x180039818  lea     rdx, [rbp+var_38]
0x18003981c  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180039821  lea     rax, [rbp+var_38]
0x180039825  mov     [rbp+arg_8], rax
0x180039829  mov     byte ptr [rbp+var_30], 5
0x18003982d  and     [rbp+var_30], edi
0x180039830  xorps   xmm0, xmm0
0x180039833  movdqu  [rbp+var_28], xmm0
0x180039838  mov     [rbp+var_18], rsi
0x18003983c  mov     byte ptr [rbp+var_38], sil
0x180039840  lea     rdx, aAllowsinglequo; "allowSingleQuotes"
0x180039847  mov     rcx, rbx
0x18003984a  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003984f  mov     rcx, rax
0x180039852  lea     rdx, [rbp+var_38]
0x180039856  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18003985b  lea     rax, [rbp+var_38]
0x18003985f  mov     [rbp+arg_8], rax
0x180039863  mov     byte ptr [rbp+var_30], 1
0x180039867  and     [rbp+var_30], edi
0x18003986a  xorps   xmm0, xmm0
0x18003986d  movdqu  [rbp+var_28], xmm0
0x180039872  mov     [rbp+var_18], rsi
0x180039876  mov     [rbp+var_38], 3E8h
0x18003987e  lea     rdx, aStacklimit; "stackLimit"
0x180039885  mov     rcx, rbx
0x180039888  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003988d  mov     rcx, rax
0x180039890  lea     rdx, [rbp+var_38]
0x180039894  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180039899  lea     rax, [rbp+var_38]
0x18003989d  mov     [rbp+arg_8], rax
0x1800398a1  mov     byte ptr [rbp+var_30], 5
0x1800398a5  and     [rbp+var_30], edi
0x1800398a8  xorps   xmm0, xmm0
0x1800398ab  movdqu  [rbp+var_28], xmm0
0x1800398b0  mov     [rbp+var_18], rsi
0x1800398b4  mov     byte ptr [rbp+var_38], sil
0x1800398b8  lea     rdx, aFailifextra; "failIfExtra"
0x1800398bf  mov     rcx, rbx
0x1800398c2  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x1800398c7  mov     rcx, rax
0x1800398ca  lea     rdx, [rbp+var_38]
0x1800398ce  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x1800398d3  lea     rax, [rbp+var_38]
0x1800398d7  mov     [rbp+arg_8], rax
0x1800398db  mov     byte ptr [rbp+var_30], 5
0x1800398df  and     [rbp+var_30], edi
0x1800398e2  xorps   xmm0, xmm0
0x1800398e5  movdqu  [rbp+var_28], xmm0
0x1800398ea  mov     [rbp+var_18], rsi
0x1800398ee  mov     byte ptr [rbp+var_38], sil
0x1800398f2  lea     rdx, aRejectdupkeys; "rejectDupKeys"
0x1800398f9  mov     rcx, rbx
0x1800398fc  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180039901  mov     rcx, rax
0x180039904  lea     rdx, [rbp+var_38]
0x180039908  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18003990d  lea     rax, [rbp+var_38]
0x180039911  mov     [rbp+arg_8], rax
0x180039915  mov     byte ptr [rbp+var_30], 5
0x180039919  and     [rbp+var_30], edi
0x18003991c  xorps   xmm0, xmm0
0x18003991f  movdqu  [rbp+var_28], xmm0
0x180039924  mov     [rbp+var_18], rsi
0x180039928  mov     byte ptr [rbp+var_38], sil
0x18003992c  lea     rdx, aAllowspecialfl; "allowSpecialFloats"
0x180039933  mov     rcx, rbx
0x180039936  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x18003993b  mov     rcx, rax
0x18003993e  lea     rdx, [rbp+var_38]
0x180039942  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180039947  add     rsp, 58h
0x18003994b  pop     rdi
0x18003994c  pop     rsi
0x18003994d  pop     rbx
0x18003994e  pop     rbp
0x18003994f  retn
```
