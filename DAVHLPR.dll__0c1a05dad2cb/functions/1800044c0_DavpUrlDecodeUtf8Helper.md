# DavpUrlDecodeUtf8Helper

- ea: `0x1800044c0`
- end: `0x180004563`
- name: `DavpUrlDecodeUtf8Helper`
- size: `163`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004160`

## callees

- `0x1800044c0`
- `0x1800046c0`
- `0x1800046f0`

## pseudocode

```c
__int64 __fastcall DavpUrlDecodeUtf8Helper(unsigned __int16 **a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v4; // r11
  int v6; // eax
  unsigned int v7; // r10d
  unsigned __int16 v9; // cx
  __int64 v10; // r11
  char32_t *v11; // r9
  Utf8Decoder *v12; // r10
  unsigned int v13; // eax
  unsigned __int8 v14[24]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 v15; // [rsp+40h] [rbp+8h] BYREF

  v4 = (__int64)*a1;
  v6 = **a1;
  if ( v6 == 37 )
  {
    if ( (__int64)((a2 - v4) & 0xFFFFFFFFFFFFFFFEuLL) >= 6 )
    {
      v9 = *(_WORD *)(v4 + 2);
      v15 = 0;
      v14[0] = 0;
      if ( HexDecodeNibble(v9, &v15) && HexDecodeNibble(*(_WORD *)(v10 + 4), v14) )
      {
        v13 = Utf8Decoder::ProcessCodeUnit(v12, v14[0] | (16 * v15), v11);
        *a1 += 3;
        return v13;
      }
    }
  }
  else if ( !*(_BYTE *)(a3 + 5) && (unsigned __int16)v6 < 0x80u )
  {
    *a4 = v6;
    v7 = 0;
    *a1 = (unsigned __int16 *)(v4 + 2);
    return v7;
  }
  return 582;
}

```

## disassembly

```asm
0x1800044c0  push    rbx
0x1800044c2  sub     rsp, 30h
0x1800044c6  mov     r11, [rcx]
0x1800044c9  mov     r10, r8
0x1800044cc  mov     rbx, rcx
0x1800044cf  movzx   eax, word ptr [r11]
0x1800044d3  cmp     eax, 25h ; '%'
0x1800044d6  jz      short loc_180004506
0x1800044d8  cmp     byte ptr [r8+5], 0
0x1800044dd  jnz     short loc_1800044FF
0x1800044df  mov     ecx, 80h
0x1800044e4  cmp     ax, cx
0x1800044e7  jnb     short loc_1800044FF
0x1800044e9  mov     [r9], eax
0x1800044ec  xor     r10d, r10d
0x1800044ef  lea     rax, [r11+2]
0x1800044f3  mov     [rbx], rax
0x1800044f6  mov     eax, r10d
0x1800044f9  add     rsp, 30h
0x1800044fd  pop     rbx
0x1800044fe  retn
0x1800044ff  mov     eax, 246h
0x180004504  jmp     short loc_1800044F9
0x180004506  sub     rdx, r11
0x180004509  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18000450d  cmp     rdx, 6
0x180004511  jl      short loc_1800044FF
0x180004513  movzx   ecx, word ptr [r11+2]; unsigned __int16
0x180004518  lea     rdx, [rsp+38h+arg_0]; unsigned __int8 *
0x18000451d  mov     [rsp+38h+arg_0], 0
0x180004522  mov     [rsp+38h+var_18], 0
0x180004527  call    ?HexDecodeNibble@@YA_NGAEAE@Z; HexDecodeNibble(ushort,uchar &)
0x18000452c  test    al, al
0x18000452e  jz      short loc_1800044FF
0x180004530  movzx   ecx, word ptr [r11+4]; unsigned __int16
0x180004535  lea     rdx, [rsp+38h+var_18]; unsigned __int8 *
0x18000453a  call    ?HexDecodeNibble@@YA_NGAEAE@Z; HexDecodeNibble(ushort,uchar &)
0x18000453f  test    al, al
0x180004541  jz      short loc_1800044FF
0x180004543  movzx   edx, [rsp+38h+arg_0]
0x180004548  mov     r8, r9; char32_t *
0x18000454b  shl     dl, 4
0x18000454e  mov     rcx, r10; this
0x180004551  or      dl, [rsp+38h+var_18]; char
0x180004555  call    ?ProcessCodeUnit@Utf8Decoder@@QEAAKDAEA_U@Z; Utf8Decoder::ProcessCodeUnit(char,char32_t &)
0x18000455a  add     qword ptr [rbx], 6
0x18000455e  mov     r10d, eax
0x180004561  jmp     short loc_1800044F6
```
