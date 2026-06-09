# web::json::details::json_error_category_impl::message(int)

- ea: `0x180041ee0`
- end: `0x180041fa8`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009698`
- `0x180041ee0`

## string_xrefs

- `0x180041f33`: `Left-over characters in stream after parsing a JSON value`
- `0x180041f21`: `Malformed comment`
- `0x180041f87`: `Malformed token`
- `0x180041f63`: `Unknown json error`
- `0x180041f6c`: `Unexpected token`

## pseudocode

```c
__int64 __fastcall web::json::details::json_error_category_impl::message(__int64 a1, __int64 a2, int a3)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  const char *v8; // rdx
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d

  if ( a3 > 6 )
  {
    v9 = a3 - 7;
    if ( !v9 )
    {
      v8 = "Malformed string literal";
      goto LABEL_25;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v8 = "Malformed token";
      goto LABEL_25;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v8 = "Mismatched braces";
      goto LABEL_25;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v8 = "Nesting too deep";
      goto LABEL_25;
    }
    if ( v12 == 1 )
    {
      v8 = "Unexpected token";
      goto LABEL_25;
    }
    goto LABEL_19;
  }
  if ( a3 == 6 )
  {
    v8 = "Malformed numeric literal";
    goto LABEL_25;
  }
  v4 = a3 - 1;
  if ( !v4 )
  {
    v8 = "Left-over characters in stream after parsing a JSON value";
    goto LABEL_25;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = "Malformed array literal";
    goto LABEL_25;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v8 = "Malformed comment";
    goto LABEL_25;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = "Malformed literal";
    goto LABEL_25;
  }
  if ( v7 != 1 )
  {
LABEL_19:
    v8 = "Unknown json error";
    goto LABEL_25;
  }
  v8 = "Malformed object literal";
LABEL_25:
  std::string::string(a2, v8);
  return a2;
}

```

## disassembly

```asm
0x180041ee0  push    rbx
0x180041ee2  sub     rsp, 30h
0x180041ee6  mov     rbx, rdx
0x180041ee9  cmp     r8d, 6
0x180041eed  jg      short loc_180041F45
0x180041eef  jz      short loc_180041F3C
0x180041ef1  sub     r8d, 1
0x180041ef5  jz      short loc_180041F33
0x180041ef7  sub     r8d, 1
0x180041efb  jz      short loc_180041F2A
0x180041efd  sub     r8d, 1
0x180041f01  jz      short loc_180041F21
0x180041f03  sub     r8d, 1
0x180041f07  jz      short loc_180041F18
0x180041f09  cmp     r8d, 1
0x180041f0d  jnz     short loc_180041F63
0x180041f0f  lea     rdx, aMalformedObjec; "Malformed object literal"
0x180041f16  jmp     short loc_180041F97
0x180041f18  lea     rdx, aMalformedLiter; "Malformed literal"
0x180041f1f  jmp     short loc_180041F97
0x180041f21  lea     rdx, aMalformedComme; "Malformed comment"
0x180041f28  jmp     short loc_180041F97
0x180041f2a  lea     rdx, aMalformedArray; "Malformed array literal"
0x180041f31  jmp     short loc_180041F97
0x180041f33  lea     rdx, aLeftOverCharac_0; "Left-over characters in stream after pa"...
0x180041f3a  jmp     short loc_180041F97
0x180041f3c  lea     rdx, aMalformedNumer; "Malformed numeric literal"
0x180041f43  jmp     short loc_180041F97
0x180041f45  sub     r8d, 7
0x180041f49  jz      short loc_180041F90
0x180041f4b  sub     r8d, 1
0x180041f4f  jz      short loc_180041F87
0x180041f51  sub     r8d, 1
0x180041f55  jz      short loc_180041F7E
0x180041f57  sub     r8d, 1
0x180041f5b  jz      short loc_180041F75
0x180041f5d  cmp     r8d, 1
0x180041f61  jz      short loc_180041F6C
0x180041f63  lea     rdx, aUnknownJsonErr; "Unknown json error"
0x180041f6a  jmp     short loc_180041F97
0x180041f6c  lea     rdx, aUnexpectedToke; "Unexpected token"
0x180041f73  jmp     short loc_180041F97
0x180041f75  lea     rdx, aNestingTooDeep; "Nesting too deep"
0x180041f7c  jmp     short loc_180041F97
0x180041f7e  lea     rdx, aMismatchedBrac; "Mismatched braces"
0x180041f85  jmp     short loc_180041F97
0x180041f87  lea     rdx, aMalformedToken; "Malformed token"
0x180041f8e  jmp     short loc_180041F97
0x180041f90  lea     rdx, aMalformedStrin; "Malformed string literal"
0x180041f97  mov     rcx, rbx
0x180041f9a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180041f9f  mov     rax, rbx
0x180041fa2  add     rsp, 30h
0x180041fa6  pop     rbx
0x180041fa7  retn
```
