# Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)

- ea: `0x140008fec`
- end: `0x140009101`
- name: `?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z`
- size: `277`
- prototype: `char __fastcall(_QWORD *, char, char, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400048f0`
- `0x140004d60`
- `0x140004e60`
- `0x14000a7bc`
- `0x14000cd1c`

## callees

- `0x140002ed8`
- `0x140008fec`

## pseudocode

```c
char __fastcall Marshal::JsonParser::BeginAggregate(_QWORD *a1, char a2, char a3, int a4)
{
  unsigned __int64 v4; // r10
  int v5; // edi
  unsigned __int64 v6; // rbx
  int v8; // esi
  int v9; // ecx
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  unsigned __int64 v16; // rdx
  bool v17; // cf
  char result; // al
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  v4 = a1[1];
  v5 = -1;
  v6 = a1[2];
  v8 = a3;
  if ( v6 >= v4 )
    v9 = -1;
  else
    v9 = *(unsigned __int16 *)(*a1 + 2 * v6);
  if ( v9 != a2 )
  {
    pExceptionObject = a4;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v10 = v4;
  v11 = 1;
  if ( v4 >= v6 + 1 )
    v10 = v6 + 1;
  a1[3] = v10;
  while ( 1 )
  {
    v12 = v6 + v11;
    if ( v6 + v11 >= v4
      || *(_WORD *)(*a1 + 2 * v12) != 9
      && *(_WORD *)(*a1 + 2 * v12) != 10
      && *(_WORD *)(*a1 + 2 * v12) != 13
      && *(_WORD *)(*a1 + 2 * v12) != 32 )
    {
      break;
    }
    ++v11;
  }
  v13 = v4;
  if ( v4 >= v12 )
    v13 = v12;
  a1[2] = v13;
  if ( v13 < v4 )
    v5 = *(unsigned __int16 *)(*a1 + 2 * v13);
  if ( v5 != v8 )
    return 1;
  v14 = v4;
  v15 = 1;
  if ( v4 >= v13 + 1 )
    v14 = v13 + 1;
  a1[3] = v14;
  while ( 1 )
  {
    v16 = v13 + v15;
    v17 = v4 < v13 + v15;
    if ( v4 <= v13 + v15 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v16) != 9
      && *(_WORD *)(*a1 + 2 * v16) != 10
      && *(_WORD *)(*a1 + 2 * v16) != 13
      && *(_WORD *)(*a1 + 2 * v16) != 32 )
    {
      v17 = v4 < v16;
      break;
    }
    ++v15;
  }
  if ( !v17 )
    v4 = v13 + v15;
  result = 0;
  a1[2] = v4;
  return result;
}

```

## disassembly

```asm
0x140008fec  mov     [rsp+arg_0], rbx
0x140008ff1  mov     [rsp+arg_10], rsi
0x140008ff6  push    rdi
0x140008ff7  sub     rsp, 20h
0x140008ffb  mov     r10, [rcx+8]
0x140008fff  or      edi, 0FFFFFFFFh
0x140009002  mov     rbx, [rcx+10h]
0x140009006  mov     r11, rcx
0x140009009  movsx   esi, r8b
0x14000900d  cmp     rbx, r10
0x140009010  jnb     short loc_14000901B
0x140009012  mov     rax, [rcx]
0x140009015  movzx   ecx, word ptr [rax+rbx*2]
0x140009019  jmp     short loc_14000901D
0x14000901b  mov     ecx, edi
0x14000901d  movsx   eax, dl
0x140009020  cmp     ecx, eax
0x140009022  jnz     loc_1400090EA
0x140009028  lea     rcx, [rbx+1]
0x14000902c  mov     rax, r10
0x14000902f  cmp     r10, rcx
0x140009032  mov     r8d, 1
0x140009038  cmovnb  rax, rcx
0x14000903c  mov     [r11+18h], rax
0x140009040  lea     rdx, [rbx+r8]
0x140009044  cmp     rdx, r10
0x140009047  jnb     short loc_140009069
0x140009049  mov     rax, [r11]
0x14000904c  movzx   ecx, word ptr [rax+rdx*2]
0x140009050  sub     ecx, 9
0x140009053  jz      short loc_140009064
0x140009055  sub     ecx, 1
0x140009058  jz      short loc_140009064
0x14000905a  sub     ecx, 3
0x14000905d  jz      short loc_140009064
0x14000905f  cmp     ecx, 13h
0x140009062  jnz     short loc_140009069
0x140009064  inc     r8
0x140009067  jmp     short loc_140009040
0x140009069  cmp     r10, rdx
0x14000906c  mov     r8, r10
0x14000906f  cmovnb  r8, rdx
0x140009073  mov     [r11+10h], r8
0x140009077  cmp     r8, r10
0x14000907a  jnb     short loc_140009084
0x14000907c  mov     rax, [r11]
0x14000907f  movzx   edi, word ptr [rax+r8*2]
0x140009084  cmp     edi, esi
0x140009086  jnz     short loc_1400090D8
0x140009088  lea     rcx, [r8+1]
0x14000908c  mov     rax, r10
0x14000908f  cmp     r10, rcx
0x140009092  mov     r9d, 1
0x140009098  cmovnb  rax, rcx
0x14000909c  mov     [r11+18h], rax
0x1400090a0  lea     rdx, [r8+r9]
0x1400090a4  cmp     r10, rdx
0x1400090a7  jbe     short loc_1400090CC
0x1400090a9  mov     rax, [r11]
0x1400090ac  movzx   ecx, word ptr [rax+rdx*2]
0x1400090b0  sub     ecx, 9
0x1400090b3  jz      short loc_1400090C4
0x1400090b5  sub     ecx, 1
0x1400090b8  jz      short loc_1400090C4
0x1400090ba  sub     ecx, 3
0x1400090bd  jz      short loc_1400090C4
0x1400090bf  cmp     ecx, 13h
0x1400090c2  jnz     short loc_1400090C9
0x1400090c4  inc     r9
0x1400090c7  jmp     short loc_1400090A0
0x1400090c9  cmp     r10, rdx
0x1400090cc  cmovnb  r10, rdx
0x1400090d0  xor     al, al
0x1400090d2  mov     [r11+10h], r10
0x1400090d6  jmp     short loc_1400090DA
0x1400090d8  mov     al, 1
0x1400090da  mov     rbx, [rsp+28h+arg_0]
0x1400090df  mov     rsi, [rsp+28h+arg_10]
0x1400090e4  add     rsp, 20h
0x1400090e8  pop     rdi
0x1400090e9  retn
0x1400090ea  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x1400090f1  mov     [rsp+28h+pExceptionObject], r9d
0x1400090f6  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1400090fb  call    _CxxThrowException_0
```
