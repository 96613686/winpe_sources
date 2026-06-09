# web::json::details::json_error_category_impl::message(int)

- ea: `0x1800036c0`
- end: `0x180003838`
- name: `?message@json_error_category_impl@details@json@web@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800036c0`
- `0x18003697c`

## string_xrefs

- `0x1800036ec`: `Left-over characters in stream after parsing a JSON value`
- `0x18000371c`: `Malformed comment`
- `0x180003794`: `Malformed token`
- `0x1800037dc`: `Unexpected token`
- `0x1800037f4`: `Unknown json error`

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
0x1800036c0  push    rbx
0x1800036c2  sub     rsp, 30h
0x1800036c6  dec     r8d; switch 11 cases
0x1800036c9  mov     rbx, rdx
0x1800036cc  cmp     r8d, 0Ah
0x1800036d0  ja      def_1800036EA; jumptable 00000001800036EA default case
0x1800036d6  lea     rdx, __ImageBase
0x1800036dd  movsxd  rax, r8d
0x1800036e0  mov     ecx, ds:(jpt_1800036EA - 180000000h)[rdx+rax*4]
0x1800036e7  add     rcx, rdx
0x1800036ea  jmp     rcx; switch jump
0x1800036ec  lea     rdx, aLeftOverCharac_0; jumptable 00000001800036EA case 1
0x1800036f3  mov     rcx, rbx
0x1800036f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800036fb  mov     rax, rbx
0x1800036fe  add     rsp, 30h
0x180003702  pop     rbx
0x180003703  retn
0x180003704  lea     rdx, aMalformedArray; jumptable 00000001800036EA case 2
0x18000370b  mov     rcx, rbx
0x18000370e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003713  mov     rax, rbx
0x180003716  add     rsp, 30h
0x18000371a  pop     rbx
0x18000371b  retn
0x18000371c  lea     rdx, aMalformedComme; jumptable 00000001800036EA case 3
0x180003723  mov     rcx, rbx
0x180003726  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000372b  mov     rax, rbx
0x18000372e  add     rsp, 30h
0x180003732  pop     rbx
0x180003733  retn
0x180003734  lea     rdx, aMalformedLiter; jumptable 00000001800036EA case 4
0x18000373b  mov     rcx, rbx
0x18000373e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003743  mov     rax, rbx
0x180003746  add     rsp, 30h
0x18000374a  pop     rbx
0x18000374b  retn
0x18000374c  lea     rdx, aMalformedObjec; jumptable 00000001800036EA case 5
0x180003753  mov     rcx, rbx
0x180003756  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000375b  mov     rax, rbx
0x18000375e  add     rsp, 30h
0x180003762  pop     rbx
0x180003763  retn
0x180003764  lea     rdx, aMalformedNumer; jumptable 00000001800036EA case 6
0x18000376b  mov     rcx, rbx
0x18000376e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003773  mov     rax, rbx
0x180003776  add     rsp, 30h
0x18000377a  pop     rbx
0x18000377b  retn
0x18000377c  lea     rdx, aMalformedStrin; jumptable 00000001800036EA case 7
0x180003783  mov     rcx, rbx
0x180003786  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18000378b  mov     rax, rbx
0x18000378e  add     rsp, 30h
0x180003792  pop     rbx
0x180003793  retn
0x180003794  lea     rdx, aMalformedToken; jumptable 00000001800036EA case 8
0x18000379b  mov     rcx, rbx
0x18000379e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800037a3  mov     rax, rbx
0x1800037a6  add     rsp, 30h
0x1800037aa  pop     rbx
0x1800037ab  retn
0x1800037ac  lea     rdx, aMismatchedBrac; jumptable 00000001800036EA case 9
0x1800037b3  mov     rcx, rbx
0x1800037b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800037bb  mov     rax, rbx
0x1800037be  add     rsp, 30h
0x1800037c2  pop     rbx
0x1800037c3  retn
0x1800037c4  lea     rdx, aNestingTooDeep; jumptable 00000001800036EA case 10
0x1800037cb  mov     rcx, rbx
0x1800037ce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800037d3  mov     rax, rbx
0x1800037d6  add     rsp, 30h
0x1800037da  pop     rbx
0x1800037db  retn
0x1800037dc  lea     rdx, aUnexpectedToke; jumptable 00000001800036EA case 11
0x1800037e3  mov     rcx, rbx
0x1800037e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800037eb  mov     rax, rbx
0x1800037ee  add     rsp, 30h
0x1800037f2  pop     rbx
0x1800037f3  retn
0x1800037f4  lea     rdx, aUnknownJsonErr; jumptable 00000001800036EA default case
0x1800037fb  mov     rcx, rbx
0x1800037fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180003803  mov     rax, rbx
0x180003806  add     rsp, 30h
0x18000380a  pop     rbx
0x18000380b  retn
```
