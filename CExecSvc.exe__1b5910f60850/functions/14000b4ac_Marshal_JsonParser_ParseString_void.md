# Marshal::JsonParser::ParseString(void)

- ea: `0x14000b4ac`
- end: `0x14000b55e`
- name: `?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `178`
- prototype: `_WORD **__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004820`
- `0x14000b3f4`
- `0x14000cd1c`

## callees

- `0x14000b4ac`
- `0x14000b564`

## pseudocode

```c
_WORD **__fastcall Marshal::JsonParser::ParseString(_QWORD *a1)
{
  _WORD **v1; // rbx
  _WORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r10
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // r8
  bool v13; // cf
  _WORD **result; // rax
  _QWORD v15[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = (_WORD **)(a1 + 8);
  a1[10] = 0;
  if ( a1[11] <= 7u )
    v3 = a1 + 8;
  else
    v3 = *v1;
  *v3 = 0;
  v4 = a1[2];
  v5 = a1[1] - v4;
  v15[0] = *a1 + 2 * v4;
  v15[1] = v5;
  v6 = Marshal::JsonParser::ParseString(v15, v1);
  v7 = a1[1];
  v8 = v6;
  v9 = a1[2];
  v10 = v9 + v6;
  v11 = v7;
  if ( v7 >= v10 )
    v11 = v10;
  a1[3] = v11;
  while ( 1 )
  {
    v12 = v9 + v8;
    v13 = v7 < v9 + v8;
    if ( v7 <= v9 + v8 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v12) != 9
      && *(_WORD *)(*a1 + 2 * v12) != 10
      && *(_WORD *)(*a1 + 2 * v12) != 13
      && *(_WORD *)(*a1 + 2 * v12) != 32 )
    {
      v13 = v7 < v12;
      break;
    }
    ++v8;
  }
  if ( !v13 )
    v7 = v9 + v8;
  result = v1;
  a1[2] = v7;
  return result;
}

```

## disassembly

```asm
0x14000b4ac  mov     [rsp+arg_0], rbx
0x14000b4b1  push    rdi
0x14000b4b2  sub     rsp, 30h
0x14000b4b6  lea     rbx, [rcx+40h]
0x14000b4ba  xor     eax, eax
0x14000b4bc  mov     [rbx+10h], rax
0x14000b4c0  mov     rdi, rcx
0x14000b4c3  cmp     qword ptr [rbx+18h], 7
0x14000b4c8  jbe     short loc_14000B4CF
0x14000b4ca  mov     rcx, [rbx]
0x14000b4cd  jmp     short loc_14000B4D2
0x14000b4cf  mov     rcx, rbx
0x14000b4d2  mov     [rcx], ax
0x14000b4d5  mov     rdx, [rdi+10h]
0x14000b4d9  mov     rax, [rdi]
0x14000b4dc  lea     rcx, [rax+rdx*2]
0x14000b4e0  mov     rax, [rdi+8]
0x14000b4e4  sub     rax, rdx
0x14000b4e7  mov     [rsp+38h+var_18], rcx
0x14000b4ec  mov     rdx, rbx
0x14000b4ef  mov     [rsp+38h+var_10], rax
0x14000b4f4  lea     rcx, [rsp+38h+var_18]
0x14000b4f9  call    ?ParseString@JsonParser@Marshal@@SA_KV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_N@Z; Marshal::JsonParser::ParseString(std::basic_string_view<ushort>,std::wstring &,bool)
0x14000b4fe  mov     rdx, [rdi+8]
0x14000b502  mov     r9, rax
0x14000b505  mov     r10, [rdi+10h]
0x14000b509  lea     rcx, [r10+rax]
0x14000b50d  mov     rax, rdx
0x14000b510  cmp     rdx, rcx
0x14000b513  cmovnb  rax, rcx
0x14000b517  mov     [rdi+18h], rax
0x14000b51b  lea     r8, [r10+r9]
0x14000b51f  cmp     rdx, r8
0x14000b522  jbe     short loc_14000B548
0x14000b524  mov     rax, [rdi]
0x14000b527  movzx   ecx, word ptr [rax+r8*2]
0x14000b52c  sub     ecx, 9
0x14000b52f  jz      short loc_14000B540
0x14000b531  sub     ecx, 1
0x14000b534  jz      short loc_14000B540
0x14000b536  sub     ecx, 3
0x14000b539  jz      short loc_14000B540
0x14000b53b  cmp     ecx, 13h
0x14000b53e  jnz     short loc_14000B545
0x14000b540  inc     r9
0x14000b543  jmp     short loc_14000B51B
0x14000b545  cmp     rdx, r8
0x14000b548  cmovnb  rdx, r8
0x14000b54c  mov     rax, rbx
0x14000b54f  mov     rbx, [rsp+38h+arg_0]
0x14000b554  mov     [rdi+10h], rdx
0x14000b558  add     rsp, 30h
0x14000b55c  pop     rdi
0x14000b55d  retn
```
