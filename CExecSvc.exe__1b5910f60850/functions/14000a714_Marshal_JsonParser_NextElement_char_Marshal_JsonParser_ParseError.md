# Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)

- ea: `0x14000a714`
- end: `0x14000a7b4`
- name: `?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z`
- size: `160`
- prototype: `char __fastcall(_QWORD *, char, int)`
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
- `0x14000a714`

## pseudocode

```c
char __fastcall Marshal::JsonParser::NextElement(_QWORD *a1, char a2, int a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v5; // r11
  int v6; // ecx
  char v7; // bl
  unsigned __int64 v8; // rax
  __int64 v9; // r8
  unsigned __int64 v10; // rdx
  bool v11; // cf
  char result; // al
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  v3 = a1[1];
  v5 = a1[2];
  if ( v5 >= v3 )
    v6 = -1;
  else
    v6 = *(unsigned __int16 *)(*a1 + 2 * v5);
  if ( v6 == a2 )
  {
    v7 = 0;
  }
  else
  {
    if ( v6 != 44 )
    {
      pExceptionObject = a3;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v7 = 1;
  }
  v8 = v3;
  v9 = 1;
  if ( v3 >= v5 + 1 )
    v8 = v5 + 1;
  a1[3] = v8;
  while ( 1 )
  {
    v10 = v5 + v9;
    v11 = v3 < v5 + v9;
    if ( v3 <= v5 + v9 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v10) != 9
      && *(_WORD *)(*a1 + 2 * v10) != 10
      && *(_WORD *)(*a1 + 2 * v10) != 13
      && *(_WORD *)(*a1 + 2 * v10) != 32 )
    {
      v11 = v3 < v10;
      break;
    }
    ++v9;
  }
  if ( !v11 )
    v3 = v5 + v9;
  result = v7;
  a1[2] = v3;
  return result;
}

```

## disassembly

```asm
0x14000a714  push    rbx
0x14000a716  sub     rsp, 20h
0x14000a71a  mov     r9, [rcx+8]
0x14000a71e  mov     r10, rcx
0x14000a721  mov     r11, [rcx+10h]
0x14000a725  cmp     r11, r9
0x14000a728  jnb     short loc_14000A734
0x14000a72a  mov     rax, [rcx]
0x14000a72d  movzx   ecx, word ptr [rax+r11*2]
0x14000a732  jmp     short loc_14000A737
0x14000a734  or      ecx, 0FFFFFFFFh
0x14000a737  movsx   eax, dl
0x14000a73a  cmp     ecx, eax
0x14000a73c  jnz     short loc_14000A742
0x14000a73e  xor     bl, bl
0x14000a740  jmp     short loc_14000A749
0x14000a742  cmp     ecx, 2Ch ; ','
0x14000a745  jnz     short loc_14000A79D
0x14000a747  mov     bl, 1
0x14000a749  lea     rcx, [r11+1]
0x14000a74d  mov     rax, r9
0x14000a750  cmp     r9, rcx
0x14000a753  mov     r8d, 1
0x14000a759  cmovnb  rax, rcx
0x14000a75d  mov     [r10+18h], rax
0x14000a761  lea     rdx, [r11+r8]
0x14000a765  cmp     r9, rdx
0x14000a768  jbe     short loc_14000A78D
0x14000a76a  mov     rax, [r10]
0x14000a76d  movzx   ecx, word ptr [rax+rdx*2]
0x14000a771  sub     ecx, 9
0x14000a774  jz      short loc_14000A785
0x14000a776  sub     ecx, 1
0x14000a779  jz      short loc_14000A785
0x14000a77b  sub     ecx, 3
0x14000a77e  jz      short loc_14000A785
0x14000a780  cmp     ecx, 13h
0x14000a783  jnz     short loc_14000A78A
0x14000a785  inc     r8
0x14000a788  jmp     short loc_14000A761
0x14000a78a  cmp     r9, rdx
0x14000a78d  cmovnb  r9, rdx
0x14000a791  mov     al, bl
0x14000a793  mov     [r10+10h], r9
0x14000a797  add     rsp, 20h
0x14000a79b  pop     rbx
0x14000a79c  retn
0x14000a79d  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000a7a4  mov     [rsp+28h+pExceptionObject], r8d
0x14000a7a9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000a7ae  call    _CxxThrowException_0
```
