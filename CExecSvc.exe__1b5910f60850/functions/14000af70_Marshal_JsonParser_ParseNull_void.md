# Marshal::JsonParser::ParseNull(void)

- ea: `0x14000af70`
- end: `0x14000b038`
- name: `?ParseNull@JsonParser@Marshal@@QEAAXXZ`
- size: `200`
- prototype: `void __fastcall(Marshal::JsonParser *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004cf0`
- `0x14000a7bc`
- `0x14000cd1c`

## callees

- `0x140002ed8`
- `0x14000af70`

## pseudocode

```c
void __fastcall Marshal::JsonParser::ParseNull(Marshal::JsonParser *this)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // r9
  __int64 v3; // rax
  unsigned __int64 v4; // rax
  __int64 v5; // r11
  unsigned __int64 v6; // r10
  bool v7; // cf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 1);
  v2 = *((_QWORD *)this + 2);
  if ( v2 >= v1
    || *(_WORD *)(*(_QWORD *)this + 2 * v2) != 110
    || v2 + 1 >= v1
    || (v3 = *(_QWORD *)this, *(_WORD *)(*(_QWORD *)this + 2 * v2 + 2) != 117)
    || v2 + 2 >= v1
    || *(_WORD *)(v3 + 2 * (v2 + 2)) != 108
    || v2 + 3 >= v1
    || *(_WORD *)(v3 + 2 * (v2 + 3)) != 108 )
  {
    pExceptionObject = 5;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v4 = *((_QWORD *)this + 1);
  v5 = 4;
  if ( v1 >= v2 + 4 )
    v4 = v2 + 4;
  *((_QWORD *)this + 3) = v4;
  while ( 1 )
  {
    v6 = v2 + v5;
    v7 = v1 < v2 + v5;
    if ( v1 <= v2 + v5 )
      break;
    if ( *(_WORD *)(*(_QWORD *)this + 2 * v6) != 9
      && *(_WORD *)(*(_QWORD *)this + 2 * v6) != 10
      && *(_WORD *)(*(_QWORD *)this + 2 * v6) != 13
      && *(_WORD *)(*(_QWORD *)this + 2 * v6) != 32 )
    {
      v7 = v1 < v6;
      break;
    }
    ++v5;
  }
  if ( !v7 )
    v1 = v2 + v5;
  *((_QWORD *)this + 2) = v1;
}

```

## disassembly

```asm
0x14000af70  sub     rsp, 28h
0x14000af74  mov     rdx, [rcx+8]
0x14000af78  mov     r8, rcx
0x14000af7b  mov     r9, [rcx+10h]
0x14000af7f  cmp     r9, rdx
0x14000af82  jnb     loc_14000B01E
0x14000af88  mov     rax, [rcx]
0x14000af8b  cmp     word ptr [rax+r9*2], 6Eh ; 'n'
0x14000af91  jnz     loc_14000B01E
0x14000af97  lea     rax, [r9+1]
0x14000af9b  cmp     rax, rdx
0x14000af9e  jnb     short loc_14000B01E
0x14000afa0  mov     rax, [rcx]
0x14000afa3  cmp     word ptr [rax+r9*2+2], 75h ; 'u'
0x14000afaa  jnz     short loc_14000B01E
0x14000afac  lea     rcx, [r9+2]
0x14000afb0  cmp     rcx, rdx
0x14000afb3  jnb     short loc_14000B01E
0x14000afb5  cmp     word ptr [rax+rcx*2], 6Ch ; 'l'
0x14000afba  jnz     short loc_14000B01E
0x14000afbc  lea     rcx, [r9+3]
0x14000afc0  cmp     rcx, rdx
0x14000afc3  jnb     short loc_14000B01E
0x14000afc5  cmp     word ptr [rax+rcx*2], 6Ch ; 'l'
0x14000afca  jnz     short loc_14000B01E
0x14000afcc  lea     rcx, [r9+4]
0x14000afd0  mov     rax, rdx
0x14000afd3  cmp     rdx, rcx
0x14000afd6  mov     r11d, 4
0x14000afdc  cmovnb  rax, rcx
0x14000afe0  mov     [r8+18h], rax
0x14000afe4  lea     r10, [r9+r11]
0x14000afe8  cmp     rdx, r10
0x14000afeb  jbe     short loc_14000B011
0x14000afed  mov     rax, [r8]
0x14000aff0  movzx   ecx, word ptr [rax+r10*2]
0x14000aff5  sub     ecx, 9
0x14000aff8  jz      short loc_14000B009
0x14000affa  sub     ecx, 1
0x14000affd  jz      short loc_14000B009
0x14000afff  sub     ecx, 3
0x14000b002  jz      short loc_14000B009
0x14000b004  cmp     ecx, 13h
0x14000b007  jnz     short loc_14000B00E
0x14000b009  inc     r11
0x14000b00c  jmp     short loc_14000AFE4
0x14000b00e  cmp     rdx, r10
0x14000b011  cmovnb  rdx, r10
0x14000b015  mov     [r8+10h], rdx
0x14000b019  add     rsp, 28h
0x14000b01d  retn
0x14000b01e  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b025  mov     [rsp+28h+pExceptionObject], 5
0x14000b02d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000b032  call    _CxxThrowException_0
```
