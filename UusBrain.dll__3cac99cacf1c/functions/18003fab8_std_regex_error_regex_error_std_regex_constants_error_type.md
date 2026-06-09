# std::regex_error::regex_error(std::regex_constants::error_type)

- ea: `0x18003fab8`
- end: `0x18003fbe2`
- name: `??0regex_error@std@@QEAA@W4error_type@regex_constants@1@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003fdc8`

## callees

- `0x180029344`
- `0x18003fab8`

## string_xrefs

- `0x18003fb9d`: `regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.`

## pseudocode

```c
std::runtime_error *__fastcall std::regex_error::regex_error(std::runtime_error *a1, int a2)
{
  const char *v4; // rdx

  if ( a2 > 7 )
  {
    switch ( a2 )
    {
      case 8:
        v4 = "regex_error(error_range): The expression contained an invalid character range, such as [b-a] in most encodings.";
        goto LABEL_33;
      case 9:
        v4 = "regex_error(error_space): There was insufficient memory to convert the expression into a finite state machine.";
        goto LABEL_33;
      case 10:
        v4 = "regex_error(error_badrepeat): One of *?+{ was not preceded by a valid regular expression.";
        goto LABEL_33;
      case 11:
        v4 = "regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.";
        goto LABEL_33;
      case 12:
        v4 = "regex_error(error_stack): There was insufficient memory to determine whether the regular expression could m"
             "atch the specified character sequence.";
        goto LABEL_33;
      case 13:
        v4 = "regex_error(error_parse)";
        goto LABEL_33;
      case 14:
        v4 = "regex_error(error_syntax)";
        goto LABEL_33;
    }
    goto LABEL_25;
  }
  switch ( a2 )
  {
    case 7:
      v4 = "regex_error(error_badbrace): The expression contained an invalid range in a {} expression.";
      goto LABEL_33;
    case 0:
      v4 = "regex_error(error_collate): The expression contained an invalid collating element name.";
      goto LABEL_33;
    case 1:
      v4 = "regex_error(error_ctype): The expression contained an invalid character class name.";
      goto LABEL_33;
    case 2:
      v4 = "regex_error(error_escape): The expression contained an invalid escaped character, or a trailing escape.";
      goto LABEL_33;
    case 3:
      v4 = "regex_error(error_backref): The expression contained an invalid back reference.";
      goto LABEL_33;
    case 4:
      v4 = "regex_error(error_brack): The expression contained mismatched [ and ].";
      goto LABEL_33;
    case 5:
      v4 = "regex_error(error_paren): The expression contained mismatched ( and ).";
      goto LABEL_33;
  }
  if ( a2 != 6 )
  {
LABEL_25:
    v4 = "regex_error";
    goto LABEL_33;
  }
  v4 = "regex_error(error_brace): The expression contained mismatched { and }.";
LABEL_33:
  std::runtime_error::runtime_error(a1, v4);
  *((_DWORD *)a1 + 6) = a2;
  *(_QWORD *)a1 = &std::regex_error::`vftable';
  return a1;
}

```

## disassembly

```asm
0x18003fab8  mov     [rsp+arg_0], rbx
0x18003fabd  push    rdi
0x18003fabe  sub     rsp, 20h
0x18003fac2  mov     ebx, edx
0x18003fac4  mov     rdi, rcx
0x18003fac7  cmp     edx, 7
0x18003faca  jg      loc_18003FB54
0x18003fad0  jz      short loc_18003FB4B
0x18003fad2  mov     r8d, edx
0x18003fad5  test    edx, edx
0x18003fad7  jz      short loc_18003FB42
0x18003fad9  sub     r8d, 1
0x18003fadd  jz      short loc_18003FB39
0x18003fadf  sub     r8d, 1
0x18003fae3  jz      short loc_18003FB2D
0x18003fae5  sub     r8d, 1
0x18003fae9  jz      short loc_18003FB21
0x18003faeb  sub     r8d, 1
0x18003faef  jz      short loc_18003FB15
0x18003faf1  sub     r8d, 1
0x18003faf5  jz      short loc_18003FB09
0x18003faf7  cmp     r8d, 1
0x18003fafb  jnz     short loc_18003FB79
0x18003fafd  lea     rdx, aRegexErrorErro_2; "regex_error(error_brace): The expressio"...
0x18003fb04  jmp     loc_18003FBBF
0x18003fb09  lea     rdx, aRegexErrorErro_13; "regex_error(error_paren): The expressio"...
0x18003fb10  jmp     loc_18003FBBF
0x18003fb15  lea     rdx, aRegexErrorErro_0; "regex_error(error_brack): The expressio"...
0x18003fb1c  jmp     loc_18003FBBF
0x18003fb21  lea     rdx, aRegexErrorErro_10; "regex_error(error_backref): The express"...
0x18003fb28  jmp     loc_18003FBBF
0x18003fb2d  lea     rdx, aRegexErrorErro_12; "regex_error(error_escape): The expressi"...
0x18003fb34  jmp     loc_18003FBBF
0x18003fb39  lea     rdx, aRegexErrorErro_7; "regex_error(error_ctype): The expressio"...
0x18003fb40  jmp     short loc_18003FBBF
0x18003fb42  lea     rdx, aRegexErrorErro; "regex_error(error_collate): The express"...
0x18003fb49  jmp     short loc_18003FBBF
0x18003fb4b  lea     rdx, aRegexErrorErro_3; "regex_error(error_badbrace): The expres"...
0x18003fb52  jmp     short loc_18003FBBF
0x18003fb54  mov     ecx, ebx
0x18003fb56  sub     ecx, 8
0x18003fb59  jz      short loc_18003FBB8
0x18003fb5b  sub     ecx, 1
0x18003fb5e  jz      short loc_18003FBAF
0x18003fb60  sub     ecx, 1
0x18003fb63  jz      short loc_18003FBA6
0x18003fb65  sub     ecx, 1
0x18003fb68  jz      short loc_18003FB9D
0x18003fb6a  sub     ecx, 1
0x18003fb6d  jz      short loc_18003FB94
0x18003fb6f  sub     ecx, 1
0x18003fb72  jz      short loc_18003FB8B
0x18003fb74  cmp     ecx, 1
0x18003fb77  jz      short loc_18003FB82
0x18003fb79  lea     rdx, aRegexError; "regex_error"
0x18003fb80  jmp     short loc_18003FBBF
0x18003fb82  lea     rdx, aRegexErrorErro_11; "regex_error(error_syntax)"
0x18003fb89  jmp     short loc_18003FBBF
0x18003fb8b  lea     rdx, aRegexErrorErro_9; "regex_error(error_parse)"
0x18003fb92  jmp     short loc_18003FBBF
0x18003fb94  lea     rdx, aRegexErrorErro_6; "regex_error(error_stack): There was ins"...
0x18003fb9b  jmp     short loc_18003FBBF
0x18003fb9d  lea     rdx, aRegexErrorErro_1; "regex_error(error_complexity): The comp"...
0x18003fba4  jmp     short loc_18003FBBF
0x18003fba6  lea     rdx, aRegexErrorErro_5; "regex_error(error_badrepeat): One of *?"...
0x18003fbad  jmp     short loc_18003FBBF
0x18003fbaf  lea     rdx, aRegexErrorErro_8; "regex_error(error_space): There was ins"...
0x18003fbb6  jmp     short loc_18003FBBF
0x18003fbb8  lea     rdx, aRegexErrorErro_4; "regex_error(error_range): The expressio"...
0x18003fbbf  mov     rcx, rdi; this
0x18003fbc2  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003fbc7  lea     rax, ??_7regex_error@std@@6B@; const std::regex_error::`vftable'
0x18003fbce  mov     [rdi+18h], ebx
0x18003fbd1  mov     rbx, [rsp+28h+arg_0]
0x18003fbd6  mov     [rdi], rax
0x18003fbd9  mov     rax, rdi
0x18003fbdc  add     rsp, 20h
0x18003fbe0  pop     rdi
0x18003fbe1  retn
```
