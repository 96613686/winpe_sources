# Marshal::JsonParser::ParseBoolean(void)

- ea: `0x14000adb4`
- end: `0x14000af69`
- name: `?ParseBoolean@JsonParser@Marshal@@QEAA_NXZ`
- size: `437`
- prototype: `bool __fastcall(Marshal::JsonParser *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004894`
- `0x14000cd1c`

## callees

- `0x140002ed8`
- `0x14000adb4`

## pseudocode

```c
bool __fastcall Marshal::JsonParser::ParseBoolean(Marshal::JsonParser *this)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // r9
  __int64 v3; // rax
  unsigned __int64 v4; // rax
  __int64 v5; // r11
  unsigned __int64 v6; // r10
  bool v7; // cf
  bool result; // al
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // r11
  unsigned __int64 v12; // r10
  bool v13; // cf
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 1);
  v2 = *((_QWORD *)this + 2);
  if ( v2 >= v1 )
    goto LABEL_45;
  if ( *(_WORD *)(*(_QWORD *)this + 2 * v2) == 116 )
  {
    if ( v2 + 1 >= v1
      || (v3 = *(_QWORD *)this, *(_WORD *)(*(_QWORD *)this + 2 * v2 + 2) != 114)
      || v2 + 2 >= v1
      || *(_WORD *)(v3 + 2 * (v2 + 2)) != 117
      || v2 + 3 >= v1
      || *(_WORD *)(v3 + 2 * (v2 + 3)) != 101 )
    {
      pExceptionObject = 6;
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
    result = 1;
    *((_QWORD *)this + 2) = v1;
    return result;
  }
  if ( *(_WORD *)(*(_QWORD *)this + 2 * v2) != 102
    || v2 + 1 >= v1
    || (v9 = *(_QWORD *)this, *(_WORD *)(*(_QWORD *)this + 2 * v2 + 2) != 97)
    || v2 + 2 >= v1
    || *(_WORD *)(v9 + 2 * (v2 + 2)) != 108
    || v2 + 3 >= v1
    || *(_WORD *)(v9 + 2 * (v2 + 3)) != 115
    || v2 + 4 >= v1
    || *(_WORD *)(v9 + 2 * (v2 + 4)) != 101 )
  {
LABEL_45:
    pExceptionObject = 6;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v10 = *((_QWORD *)this + 1);
  v11 = 5;
  if ( v1 >= v2 + 5 )
    v10 = v2 + 5;
  *((_QWORD *)this + 3) = v10;
  while ( 1 )
  {
    v12 = v2 + v11;
    v13 = v1 < v2 + v11;
    if ( v1 <= v2 + v11 )
      break;
    if ( *(_WORD *)(*(_QWORD *)this + 2 * v12) != 9
      && *(_WORD *)(*(_QWORD *)this + 2 * v12) != 10
      && *(_WORD *)(*(_QWORD *)this + 2 * v12) != 13
      && *(_WORD *)(*(_QWORD *)this + 2 * v12) != 32 )
    {
      v13 = v1 < v12;
      break;
    }
    ++v11;
  }
  if ( !v13 )
    v1 = v2 + v11;
  result = 0;
  *((_QWORD *)this + 2) = v1;
  return result;
}

```

## disassembly

```asm
0x14000adb4  sub     rsp, 28h
0x14000adb8  mov     rdx, [rcx+8]
0x14000adbc  mov     r8, rcx
0x14000adbf  mov     r9, [rcx+10h]
0x14000adc3  cmp     r9, rdx
0x14000adc6  jnb     loc_14000AF4F
0x14000adcc  mov     rax, [rcx]
0x14000adcf  cmp     word ptr [rax+r9*2], 74h ; 't'
0x14000add5  jnz     loc_14000AE7C
0x14000addb  lea     rax, [r9+1]
0x14000addf  cmp     rax, rdx
0x14000ade2  jnb     loc_14000AF35
0x14000ade8  mov     rax, [rcx]
0x14000adeb  cmp     word ptr [rax+r9*2+2], 72h ; 'r'
0x14000adf2  jnz     loc_14000AF35
0x14000adf8  lea     rcx, [r9+2]
0x14000adfc  cmp     rcx, rdx
0x14000adff  jnb     loc_14000AF35
0x14000ae05  cmp     word ptr [rax+rcx*2], 75h ; 'u'
0x14000ae0a  jnz     loc_14000AF35
0x14000ae10  lea     rcx, [r9+3]
0x14000ae14  cmp     rcx, rdx
0x14000ae17  jnb     loc_14000AF35
0x14000ae1d  cmp     word ptr [rax+rcx*2], 65h ; 'e'
0x14000ae22  jnz     loc_14000AF35
0x14000ae28  lea     rcx, [r9+4]
0x14000ae2c  mov     rax, rdx
0x14000ae2f  cmp     rdx, rcx
0x14000ae32  mov     r11d, 4
0x14000ae38  cmovnb  rax, rcx
0x14000ae3c  mov     [r8+18h], rax
0x14000ae40  lea     r10, [r9+r11]
0x14000ae44  cmp     rdx, r10
0x14000ae47  jbe     short loc_14000AE6D
0x14000ae49  mov     rax, [r8]
0x14000ae4c  movzx   ecx, word ptr [rax+r10*2]
0x14000ae51  sub     ecx, 9
0x14000ae54  jz      short loc_14000AE65
0x14000ae56  sub     ecx, 1
0x14000ae59  jz      short loc_14000AE65
0x14000ae5b  sub     ecx, 3
0x14000ae5e  jz      short loc_14000AE65
0x14000ae60  cmp     ecx, 13h
0x14000ae63  jnz     short loc_14000AE6A
0x14000ae65  inc     r11
0x14000ae68  jmp     short loc_14000AE40
0x14000ae6a  cmp     rdx, r10
0x14000ae6d  cmovnb  rdx, r10
0x14000ae71  mov     al, 1
0x14000ae73  mov     [r8+10h], rdx
0x14000ae77  add     rsp, 28h
0x14000ae7b  retn
0x14000ae7c  cmp     word ptr [rax+r9*2], 66h ; 'f'
0x14000ae82  jnz     loc_14000AF4F
0x14000ae88  lea     rax, [r9+1]
0x14000ae8c  cmp     rax, rdx
0x14000ae8f  jnb     loc_14000AF4F
0x14000ae95  mov     rax, [rcx]
0x14000ae98  cmp     word ptr [rax+r9*2+2], 61h ; 'a'
0x14000ae9f  jnz     loc_14000AF4F
0x14000aea5  lea     rcx, [r9+2]
0x14000aea9  cmp     rcx, rdx
0x14000aeac  jnb     loc_14000AF4F
0x14000aeb2  cmp     word ptr [rax+rcx*2], 6Ch ; 'l'
0x14000aeb7  jnz     loc_14000AF4F
0x14000aebd  lea     rcx, [r9+3]
0x14000aec1  cmp     rcx, rdx
0x14000aec4  jnb     loc_14000AF4F
0x14000aeca  cmp     word ptr [rax+rcx*2], 73h ; 's'
0x14000aecf  jnz     short loc_14000AF4F
0x14000aed1  lea     rcx, [r9+4]
0x14000aed5  cmp     rcx, rdx
0x14000aed8  jnb     short loc_14000AF4F
0x14000aeda  cmp     word ptr [rax+rcx*2], 65h ; 'e'
0x14000aedf  jnz     short loc_14000AF4F
0x14000aee1  lea     rcx, [r9+5]
0x14000aee5  mov     rax, rdx
0x14000aee8  cmp     rdx, rcx
0x14000aeeb  mov     r11d, 5
0x14000aef1  cmovnb  rax, rcx
0x14000aef5  mov     [r8+18h], rax
0x14000aef9  lea     r10, [r9+r11]
0x14000aefd  cmp     rdx, r10
0x14000af00  jbe     short loc_14000AF26
0x14000af02  mov     rax, [r8]
0x14000af05  movzx   ecx, word ptr [rax+r10*2]
0x14000af0a  sub     ecx, 9
0x14000af0d  jz      short loc_14000AF1E
0x14000af0f  sub     ecx, 1
0x14000af12  jz      short loc_14000AF1E
0x14000af14  sub     ecx, 3
0x14000af17  jz      short loc_14000AF1E
0x14000af19  cmp     ecx, 13h
0x14000af1c  jnz     short loc_14000AF23
0x14000af1e  inc     r11
0x14000af21  jmp     short loc_14000AEF9
0x14000af23  cmp     rdx, r10
0x14000af26  cmovnb  rdx, r10
0x14000af2a  xor     al, al
0x14000af2c  mov     [r8+10h], rdx
0x14000af30  jmp     loc_14000AE77
0x14000af35  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000af3c  mov     [rsp+28h+pExceptionObject], 6
0x14000af44  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000af49  call    _CxxThrowException_0
0x14000af4f  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000af56  mov     [rsp+28h+pExceptionObject], 6
0x14000af5e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000af63  call    _CxxThrowException_0
```
