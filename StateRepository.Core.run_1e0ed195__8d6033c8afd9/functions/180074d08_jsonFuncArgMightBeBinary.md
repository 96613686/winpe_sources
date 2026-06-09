# jsonFuncArgMightBeBinary

- ea: `0x180074d08`
- end: `0x180074dc4`
- name: `jsonFuncArgMightBeBinary`
- size: `188`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180072da4`
- `0x180074260`
- `0x180074810`
- `0x180074dcc`
- `0x180078870`

## callees

- `0x180027a20`
- `0x180048d38`
- `0x18006910e`
- `0x180074d08`
- `0x180078a58`

## pseudocode

```c
__int64 __fastcall jsonFuncArgMightBeBinary(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  _BYTE *v4; // rdi
  int v5; // esi
  unsigned __int8 v6; // bl
  int v7; // eax
  _BYTE *v9; // [rsp+20h] [rbp-58h] BYREF
  int v10; // [rsp+28h] [rbp-50h]
  unsigned int v11; // [rsp+80h] [rbp+8h] BYREF

  v11 = 0;
  if ( *((_BYTE *)qword_18009EC50 + (*(_WORD *)(a1 + 20) & 0x3F)) != 4 )
    return 0;
  v2 = sqlite3_value_blob(a1);
  LOBYTE(v3) = 1;
  v4 = (_BYTE *)v2;
  v5 = sqlite3ValueBytes(a1, v3);
  if ( v5 < 1 )
    return 0;
  if ( v4
    && (v6 = *v4 & 0xF, v6 <= 0xCu)
    && (memset_0(&v9, 0, 0x48u), v9 = v4, v10 = v5, (v7 = jsonbPayloadSize((__int64 *)&v9, 0, &v11)) != 0)
    && v7 + v11 == v5
    && (v6 > 2u || !v11) )
  {
    return 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180074d08  mov     rax, rsp
0x180074d0b  mov     [rax+10h], rbx
0x180074d0f  mov     [rax+18h], rsi
0x180074d13  push    rdi
0x180074d14  sub     rsp, 70h
0x180074d18  mov     dword ptr [rax+8], 0
0x180074d1f  mov     rbx, rcx
0x180074d22  movzx   eax, word ptr [rcx+14h]
0x180074d26  lea     rcx, qword_18009EC50
0x180074d2d  and     eax, 3Fh
0x180074d30  cmp     byte ptr [rax+rcx], 4
0x180074d34  jnz     short loc_180074DB0
0x180074d36  mov     rcx, rbx
0x180074d39  call    sqlite3_value_blob
0x180074d3e  mov     dl, 1
0x180074d40  mov     rcx, rbx
0x180074d43  mov     rdi, rax
0x180074d46  call    sqlite3ValueBytes
0x180074d4b  mov     esi, eax
0x180074d4d  cmp     eax, 1
0x180074d50  jl      short loc_180074DB0
0x180074d52  test    rdi, rdi
0x180074d55  jz      short loc_180074DB0
0x180074d57  mov     bl, [rdi]
0x180074d59  and     bl, 0Fh
0x180074d5c  cmp     bl, 0Ch
0x180074d5f  ja      short loc_180074DB0
0x180074d61  xor     edx, edx; Val
0x180074d63  lea     rcx, [rsp+78h+var_58]; void *
0x180074d68  lea     r8d, [rdx+48h]; Size
0x180074d6c  call    memset_0
0x180074d71  lea     r8, [rsp+78h+arg_0]
0x180074d79  mov     [rsp+78h+var_58], rdi
0x180074d7e  xor     edx, edx
0x180074d80  mov     [rsp+78h+var_50], esi
0x180074d84  lea     rcx, [rsp+78h+var_58]
0x180074d89  call    jsonbPayloadSize
0x180074d8e  test    eax, eax
0x180074d90  jz      short loc_180074DB0
0x180074d92  mov     edx, [rsp+78h+arg_0]
0x180074d99  lea     ecx, [rax+rdx]
0x180074d9c  cmp     ecx, esi
0x180074d9e  jnz     short loc_180074DB0
0x180074da0  cmp     bl, 2
0x180074da3  ja      short loc_180074DA9
0x180074da5  test    edx, edx
0x180074da7  jnz     short loc_180074DB0
0x180074da9  mov     eax, 1
0x180074dae  jmp     short loc_180074DB2
0x180074db0  xor     eax, eax
0x180074db2  lea     r11, [rsp+78h+var_8]
0x180074db7  mov     rbx, [r11+18h]
0x180074dbb  mov     rsi, [r11+20h]
0x180074dbf  mov     rsp, r11
0x180074dc2  pop     rdi
0x180074dc3  retn
```
