# std::regex_error::_Stringify(std::regex_constants::error_type)

- ea: `0x14004ea24`
- end: `0x14004eaf0`
- name: `?_Stringify@regex_error@std@@CAPEBDW4error_type@regex_constants@2@@Z`
- size: `204`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004e978`

## callees

- `0x14004ea24`

## string_xrefs

- `0x14004ead0`: `regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.`

## pseudocode

```c
const char *__fastcall std::regex_error::_Stringify(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx

  if ( a1 <= 7 )
  {
    if ( a1 == 7 )
      return "regex_error(error_badbrace): The expression contained an invalid range in a {} expression.";
    if ( !a1 )
      return "regex_error(error_collate): The expression contained an invalid collating element name.";
    v1 = a1 - 1;
    if ( !v1 )
      return "regex_error(error_ctype): The expression contained an invalid character class name.";
    v2 = v1 - 1;
    if ( !v2 )
      return "regex_error(error_escape): The expression contained an invalid escaped character, or a trailing escape.";
    v3 = v2 - 1;
    if ( !v3 )
      return "regex_error(error_backref): The expression contained an invalid back reference.";
    v4 = v3 - 1;
    if ( !v4 )
      return "regex_error(error_brack): The expression contained mismatched [ and ].";
    v5 = v4 - 1;
    if ( !v5 )
      return "regex_error(error_paren): The expression contained mismatched ( and ).";
    if ( v5 == 1 )
      return "regex_error(error_brace): The expression contained mismatched { and }.";
    return "regex_error";
  }
  v7 = a1 - 8;
  if ( !v7 )
    return "regex_error(error_range): The expression contained an invalid character range, such as [b-a] in most encodings.";
  v8 = v7 - 1;
  if ( !v8 )
    return "regex_error(error_space): There was insufficient memory to convert the expression into a finite state machine.";
  v9 = v8 - 1;
  if ( !v9 )
    return "regex_error(error_badrepeat): One of *?+{ was not preceded by a valid regular expression.";
  v10 = v9 - 1;
  if ( !v10 )
    return "regex_error(error_complexity): The complexity of an attempted match against a regular expression exceeded a pre-set level.";
  v11 = v10 - 1;
  if ( !v11 )
    return "regex_error(error_stack): There was insufficient memory to determine whether the regular expression could mat"
           "ch the specified character sequence.";
  v12 = v11 - 1;
  if ( !v12 )
    return "regex_error(error_parse)";
  if ( v12 != 1 )
    return "regex_error";
  return "regex_error(error_syntax)";
}

```

## disassembly

```asm
0x14004ea24  cmp     ecx, 7
0x14004ea27  jg      short loc_14004EA8D
0x14004ea29  jz      short loc_14004EA85
0x14004ea2b  test    ecx, ecx
0x14004ea2d  jz      short loc_14004EA7D
0x14004ea2f  sub     ecx, 1
0x14004ea32  jz      short loc_14004EA75
0x14004ea34  sub     ecx, 1
0x14004ea37  jz      short loc_14004EA6D
0x14004ea39  sub     ecx, 1
0x14004ea3c  jz      short loc_14004EA65
0x14004ea3e  sub     ecx, 1
0x14004ea41  jz      short loc_14004EA5D
0x14004ea43  sub     ecx, 1
0x14004ea46  jz      short loc_14004EA55
0x14004ea48  cmp     ecx, 1
0x14004ea4b  jnz     short loc_14004EAB0
0x14004ea4d  lea     rax, aRegexErrorErro
0x14004ea54  retn
0x14004ea55  lea     rax, aRegexErrorErro_0
0x14004ea5c  retn
0x14004ea5d  lea     rax, aRegexErrorErro_1
0x14004ea64  retn
0x14004ea65  lea     rax, aRegexErrorErro_2
0x14004ea6c  retn
0x14004ea6d  lea     rax, aRegexErrorErro_3
0x14004ea74  retn
0x14004ea75  lea     rax, aRegexErrorErro_4
0x14004ea7c  retn
0x14004ea7d  lea     rax, aRegexErrorErro_5
0x14004ea84  retn
0x14004ea85  lea     rax, aRegexErrorErro_6
0x14004ea8c  retn
0x14004ea8d  sub     ecx, 8
0x14004ea90  jz      short loc_14004EAE8
0x14004ea92  sub     ecx, 1
0x14004ea95  jz      short loc_14004EAE0
0x14004ea97  sub     ecx, 1
0x14004ea9a  jz      short loc_14004EAD8
0x14004ea9c  sub     ecx, 1
0x14004ea9f  jz      short loc_14004EAD0
0x14004eaa1  sub     ecx, 1
0x14004eaa4  jz      short loc_14004EAC8
0x14004eaa6  sub     ecx, 1
0x14004eaa9  jz      short loc_14004EAC0
0x14004eaab  cmp     ecx, 1
0x14004eaae  jz      short loc_14004EAB8
0x14004eab0  lea     rax, aRegexError
0x14004eab7  retn
0x14004eab8  lea     rax, aRegexErrorErro_7
0x14004eabf  retn
0x14004eac0  lea     rax, aRegexErrorErro_8
0x14004eac7  retn
0x14004eac8  lea     rax, aRegexErrorErro_9
0x14004eacf  retn
0x14004ead0  lea     rax, aRegexErrorErro_10
0x14004ead7  retn
0x14004ead8  lea     rax, aRegexErrorErro_11
0x14004eadf  retn
0x14004eae0  lea     rax, aRegexErrorErro_12
0x14004eae7  retn
0x14004eae8  lea     rax, aRegexErrorErro_13
0x14004eaef  retn
```
