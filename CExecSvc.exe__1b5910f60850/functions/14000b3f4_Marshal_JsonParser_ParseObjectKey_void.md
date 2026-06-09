# Marshal::JsonParser::ParseObjectKey(void)

- ea: `0x14000b3f4`
- end: `0x14000b4a6`
- name: `?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400048f0`
- `0x14000a7bc`
- `0x14000cd1c`

## callees

- `0x140002ed8`
- `0x140006790`
- `0x14000b3f4`
- `0x14000b4ac`

## pseudocode

```c
void __fastcall Marshal::JsonParser::ParseObjectKey(void **this)
{
  void **v2; // rax
  unsigned __int64 v3; // r8
  unsigned __int64 v4; // rdx
  char *v5; // r8
  void *v6; // rax
  __int64 v7; // r10
  unsigned __int64 v8; // r9
  bool v9; // cf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void **)Marshal::JsonParser::ParseString(this);
  if ( this + 4 != v2 )
  {
    v3 = (unsigned __int64)v2[2];
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (void **)*v2;
    std::wstring::_Assign<unsigned short>(this + 4, v2, v3);
  }
  v4 = (unsigned __int64)this[1];
  v5 = (char *)this[2];
  if ( (unsigned __int64)v5 >= v4 || *((_WORD *)*this + (_QWORD)v5) != 58 )
  {
    pExceptionObject = 11;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v6 = this[1];
  v7 = 1;
  if ( v4 >= (unsigned __int64)(v5 + 1) )
    v6 = v5 + 1;
  this[3] = v6;
  while ( 1 )
  {
    v8 = (unsigned __int64)&v5[v7];
    v9 = v4 < (unsigned __int64)&v5[v7];
    if ( v4 <= (unsigned __int64)&v5[v7] )
      break;
    if ( *((_WORD *)*this + v8) != 9
      && *((_WORD *)*this + v8) != 10
      && *((_WORD *)*this + v8) != 13
      && *((_WORD *)*this + v8) != 32 )
    {
      v9 = v4 < v8;
      break;
    }
    ++v7;
  }
  if ( !v9 )
    v4 = (unsigned __int64)&v5[v7];
  this[2] = (void *)v4;
}

```

## disassembly

```asm
0x14000b3f4  push    rbx
0x14000b3f6  sub     rsp, 20h
0x14000b3fa  mov     rbx, rcx
0x14000b3fd  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x14000b402  lea     rcx, [rbx+20h]
0x14000b406  cmp     rcx, rax
0x14000b409  jz      short loc_14000B421
0x14000b40b  cmp     qword ptr [rax+18h], 7
0x14000b410  mov     r8, [rax+10h]
0x14000b414  jbe     short loc_14000B419
0x14000b416  mov     rax, [rax]
0x14000b419  mov     rdx, rax
0x14000b41c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14000b421  mov     rdx, [rbx+8]
0x14000b425  mov     r8, [rbx+10h]
0x14000b429  cmp     r8, rdx
0x14000b42c  jnb     short loc_14000B48C
0x14000b42e  mov     rax, [rbx]
0x14000b431  cmp     word ptr [rax+r8*2], 3Ah ; ':'
0x14000b437  jnz     short loc_14000B48C
0x14000b439  lea     rcx, [r8+1]
0x14000b43d  mov     rax, rdx
0x14000b440  cmp     rdx, rcx
0x14000b443  mov     r10d, 1
0x14000b449  cmovnb  rax, rcx
0x14000b44d  mov     [rbx+18h], rax
0x14000b451  lea     r9, [r8+r10]
0x14000b455  cmp     rdx, r9
0x14000b458  jbe     short loc_14000B47E
0x14000b45a  mov     rax, [rbx]
0x14000b45d  movzx   ecx, word ptr [rax+r9*2]
0x14000b462  sub     ecx, 9
0x14000b465  jz      short loc_14000B476
0x14000b467  sub     ecx, 1
0x14000b46a  jz      short loc_14000B476
0x14000b46c  sub     ecx, 3
0x14000b46f  jz      short loc_14000B476
0x14000b471  cmp     ecx, 13h
0x14000b474  jnz     short loc_14000B47B
0x14000b476  inc     r10
0x14000b479  jmp     short loc_14000B451
0x14000b47b  cmp     rdx, r9
0x14000b47e  cmovnb  rdx, r9
0x14000b482  mov     [rbx+10h], rdx
0x14000b486  add     rsp, 20h
0x14000b48a  pop     rbx
0x14000b48b  retn
0x14000b48c  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b493  mov     [rsp+28h+pExceptionObject], 0Bh
0x14000b49b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000b4a0  call    _CxxThrowException_0
```
