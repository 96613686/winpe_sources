# Marshal::JsonParser::PeekValueType(void)

- ea: `0x14000b8c8`
- end: `0x14000b94f`
- name: `?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004748`
- `0x140004820`
- `0x140004894`
- `0x1400048f0`
- `0x140004cf0`
- `0x140004d60`
- `0x140004e60`
- `0x14000a7bc`
- `0x14000cd1c`

## callees

- `0x140002ed8`
- `0x14000b8c8`

## pseudocode

```c
__int64 __fastcall Marshal::JsonParser::PeekValueType(_QWORD *a1)
{
  unsigned __int64 v1; // rdx
  unsigned int v2; // ecx
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[2];
  if ( v1 >= a1[1] )
    goto LABEL_17;
  v2 = *(unsigned __int16 *)(*a1 + 2 * v1);
  switch ( v2 )
  {
    case '"':
      return 1;
    case '[':
      return 2;
    case 'f':
      return 4;
    case 'n':
      return 5;
    case 't':
      return 4;
  }
  if ( v2 != 123 )
  {
    if ( v2 >= 0x30 && v2 <= 0x39 || v2 == 45 )
      return 0;
LABEL_17:
    pExceptionObject = 2;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  return 3;
}

```

## disassembly

```asm
0x14000b8c8  sub     rsp, 28h
0x14000b8cc  mov     rdx, [rcx+10h]
0x14000b8d0  cmp     rdx, [rcx+8]
0x14000b8d4  jnb     short loc_14000B934
0x14000b8d6  mov     rax, [rcx]
0x14000b8d9  movzx   ecx, word ptr [rax+rdx*2]
0x14000b8dd  cmp     ecx, 22h ; '"'
0x14000b8e0  jz      short loc_14000B92D
0x14000b8e2  cmp     ecx, 5Bh ; '['
0x14000b8e5  jz      short loc_14000B926
0x14000b8e7  cmp     ecx, 66h ; 'f'
0x14000b8ea  jz      short loc_14000B91F
0x14000b8ec  cmp     ecx, 6Eh ; 'n'
0x14000b8ef  jz      short loc_14000B918
0x14000b8f1  cmp     ecx, 74h ; 't'
0x14000b8f4  jz      short loc_14000B91F
0x14000b8f6  cmp     ecx, 7Bh ; '{'
0x14000b8f9  jz      short loc_14000B911
0x14000b8fb  cmp     ecx, 30h ; '0'
0x14000b8fe  jb      short loc_14000B905
0x14000b900  cmp     ecx, 39h ; '9'
0x14000b903  jbe     short loc_14000B90A
0x14000b905  cmp     ecx, 2Dh ; '-'
0x14000b908  jnz     short loc_14000B934
0x14000b90a  xor     eax, eax
0x14000b90c  add     rsp, 28h
0x14000b910  retn
0x14000b911  mov     eax, 3
0x14000b916  jmp     short loc_14000B90C
0x14000b918  mov     eax, 5
0x14000b91d  jmp     short loc_14000B90C
0x14000b91f  mov     eax, 4
0x14000b924  jmp     short loc_14000B90C
0x14000b926  mov     eax, 2
0x14000b92b  jmp     short loc_14000B90C
0x14000b92d  mov     eax, 1
0x14000b932  jmp     short loc_14000B90C
0x14000b934  mov     eax, 2
0x14000b939  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b940  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000b945  mov     [rsp+28h+pExceptionObject], eax
0x14000b949  call    _CxxThrowException_0
```
