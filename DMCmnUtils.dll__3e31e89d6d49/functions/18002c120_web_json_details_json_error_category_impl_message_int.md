# web::json::details::json_error_category_impl::message(int)

- ea: `0x18002c120`
- end: `0x18002c298`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002c120`
- `0x180082e78`

## string_xrefs

- `0x18002c14c`: `Left-over characters in stream after parsing a JSON value`
- `0x18002c17c`: `Malformed comment`
- `0x18002c1f4`: `Malformed token`
- `0x18002c23c`: `Unexpected token`
- `0x18002c254`: `Unknown json error`

## pseudocode

```c
__int64 __fastcall web::json::details::json_error_category_impl::message(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  switch ( a3 )
  {
    case 1:
      std::string::string(a2, "Left-over characters in stream after parsing a JSON value");
      result = a2;
      break;
    case 2:
      std::string::string(a2, "Malformed array literal");
      result = a2;
      break;
    case 3:
      std::string::string(a2, "Malformed comment");
      result = a2;
      break;
    case 4:
      std::string::string(a2, "Malformed literal");
      result = a2;
      break;
    case 5:
      std::string::string(a2, "Malformed object literal");
      result = a2;
      break;
    case 6:
      std::string::string(a2, "Malformed numeric literal");
      result = a2;
      break;
    case 7:
      std::string::string(a2, "Malformed string literal");
      result = a2;
      break;
    case 8:
      std::string::string(a2, "Malformed token");
      result = a2;
      break;
    case 9:
      std::string::string(a2, "Mismatched braces");
      result = a2;
      break;
    case 10:
      std::string::string(a2, "Nesting too deep");
      result = a2;
      break;
    case 11:
      std::string::string(a2, "Unexpected token");
      result = a2;
      break;
    default:
      std::string::string(a2, "Unknown json error");
      result = a2;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18002c120  push    rbx
0x18002c122  sub     rsp, 30h
0x18002c126  dec     r8d; switch 11 cases
0x18002c129  mov     rbx, rdx
0x18002c12c  cmp     r8d, 0Ah
0x18002c130  ja      def_18002C14A; jumptable 000000018002C14A default case
0x18002c136  lea     rdx, __ImageBase
0x18002c13d  movsxd  rax, r8d
0x18002c140  mov     ecx, ds:(jpt_18002C14A - 180000000h)[rdx+rax*4]
0x18002c147  add     rcx, rdx
0x18002c14a  jmp     rcx; switch jump
0x18002c14c  lea     rdx, aLeftOverCharac_0; jumptable 000000018002C14A case 1
0x18002c153  mov     rcx, rbx
0x18002c156  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c15b  mov     rax, rbx
0x18002c15e  add     rsp, 30h
0x18002c162  pop     rbx
0x18002c163  retn
0x18002c164  lea     rdx, aMalformedArray; jumptable 000000018002C14A case 2
0x18002c16b  mov     rcx, rbx
0x18002c16e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c173  mov     rax, rbx
0x18002c176  add     rsp, 30h
0x18002c17a  pop     rbx
0x18002c17b  retn
0x18002c17c  lea     rdx, aMalformedComme; jumptable 000000018002C14A case 3
0x18002c183  mov     rcx, rbx
0x18002c186  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c18b  mov     rax, rbx
0x18002c18e  add     rsp, 30h
0x18002c192  pop     rbx
0x18002c193  retn
0x18002c194  lea     rdx, aMalformedLiter; jumptable 000000018002C14A case 4
0x18002c19b  mov     rcx, rbx
0x18002c19e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c1a3  mov     rax, rbx
0x18002c1a6  add     rsp, 30h
0x18002c1aa  pop     rbx
0x18002c1ab  retn
0x18002c1ac  lea     rdx, aMalformedObjec; jumptable 000000018002C14A case 5
0x18002c1b3  mov     rcx, rbx
0x18002c1b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c1bb  mov     rax, rbx
0x18002c1be  add     rsp, 30h
0x18002c1c2  pop     rbx
0x18002c1c3  retn
0x18002c1c4  lea     rdx, aMalformedNumer; jumptable 000000018002C14A case 6
0x18002c1cb  mov     rcx, rbx
0x18002c1ce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c1d3  mov     rax, rbx
0x18002c1d6  add     rsp, 30h
0x18002c1da  pop     rbx
0x18002c1db  retn
0x18002c1dc  lea     rdx, aMalformedStrin; jumptable 000000018002C14A case 7
0x18002c1e3  mov     rcx, rbx
0x18002c1e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c1eb  mov     rax, rbx
0x18002c1ee  add     rsp, 30h
0x18002c1f2  pop     rbx
0x18002c1f3  retn
0x18002c1f4  lea     rdx, aMalformedToken; jumptable 000000018002C14A case 8
0x18002c1fb  mov     rcx, rbx
0x18002c1fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c203  mov     rax, rbx
0x18002c206  add     rsp, 30h
0x18002c20a  pop     rbx
0x18002c20b  retn
0x18002c20c  lea     rdx, aMismatchedBrac; jumptable 000000018002C14A case 9
0x18002c213  mov     rcx, rbx
0x18002c216  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c21b  mov     rax, rbx
0x18002c21e  add     rsp, 30h
0x18002c222  pop     rbx
0x18002c223  retn
0x18002c224  lea     rdx, aNestingTooDeep; jumptable 000000018002C14A case 10
0x18002c22b  mov     rcx, rbx
0x18002c22e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c233  mov     rax, rbx
0x18002c236  add     rsp, 30h
0x18002c23a  pop     rbx
0x18002c23b  retn
0x18002c23c  lea     rdx, aUnexpectedToke; jumptable 000000018002C14A case 11
0x18002c243  mov     rcx, rbx
0x18002c246  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c24b  mov     rax, rbx
0x18002c24e  add     rsp, 30h
0x18002c252  pop     rbx
0x18002c253  retn
0x18002c254  lea     rdx, aUnknownJsonErr; jumptable 000000018002C14A default case
0x18002c25b  mov     rcx, rbx
0x18002c25e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c263  mov     rax, rbx
0x18002c266  add     rsp, 30h
0x18002c26a  pop     rbx
0x18002c26b  retn
```
