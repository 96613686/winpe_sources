# jsonStringGrow

- ea: `0x1800771e0`
- end: `0x1800772cb`
- name: `jsonStringGrow`
- size: `235`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180072b2c`
- `0x180072f10`
- `0x18007672c`
- `0x18007718c`
- `0x18007750c`

## callees

- `0x18000aac0`
- `0x18000c0f0`
- `0x1800623c8`
- `0x180068190`
- `0x1800771e0`
- `0x1800772d4`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall jsonStringGrow(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // rax
  __int64 v4; // rdi
  void *v6; // rax
  void *v7; // rsi
  __int64 v8; // rsi
  __int64 v9; // rax

  v2 = *(_QWORD *)(a1 + 16);
  if ( a2 >= v2 )
    v4 = v2 + a2 + 10LL;
  else
    v4 = 2 * v2;
  if ( !*(_BYTE *)(a1 + 32) )
  {
    v8 = *(_QWORD *)(a1 + 8);
    v9 = sqlite3_realloc64(v8 - 8, v4 + 9);
    if ( v9 )
    {
      *(_QWORD *)(a1 + 8) = v9 + 8;
      if ( v9 != -8 )
        goto LABEL_13;
    }
    else
    {
      sqlite3_free(v8 - 8);
    }
    *(_BYTE *)(a1 + 33) |= 1u;
    *(_QWORD *)(a1 + 8) = a1 + 34;
    *(_QWORD *)(a1 + 16) = 100;
    *(_QWORD *)(a1 + 24) = 0;
    *(_BYTE *)(a1 + 32) = 1;
    return 7;
  }
  if ( *(_BYTE *)(a1 + 33) )
    return 1;
  v6 = (void *)sqlite3RCStrNew(v4);
  v7 = v6;
  if ( !v6 )
  {
    *(_BYTE *)(a1 + 33) |= 1u;
    if ( *(_QWORD *)a1 )
      sqlite3_result_error_nomem(*(_QWORD *)a1);
    jsonStringReset(a1);
    return 7;
  }
  memcpy_0(v6, *(const void **)(a1 + 8), *(_QWORD *)(a1 + 24));
  *(_QWORD *)(a1 + 8) = v7;
  *(_BYTE *)(a1 + 32) = 0;
LABEL_13:
  *(_QWORD *)(a1 + 16) = v4;
  return 0;
}

```

## disassembly

```asm
0x1800771e0  mov     [rsp+arg_0], rbx
0x1800771e5  mov     [rsp+arg_8], rsi
0x1800771ea  push    rdi
0x1800771eb  sub     rsp, 20h
0x1800771ef  mov     rax, [rcx+10h]
0x1800771f3  mov     rbx, rcx
0x1800771f6  mov     ecx, edx
0x1800771f8  cmp     rcx, rax
0x1800771fb  jnb     short loc_180077203
0x1800771fd  lea     rdi, [rax+rax]
0x180077201  jmp     short loc_18007720A
0x180077203  lea     rdi, [rcx+0Ah]
0x180077207  add     rdi, rax
0x18007720a  cmp     byte ptr [rbx+20h], 0
0x18007720e  jz      short loc_18007727B
0x180077210  cmp     byte ptr [rbx+21h], 0
0x180077214  jz      short loc_18007721D
0x180077216  mov     eax, 1
0x18007721b  jmp     short loc_18007726B
0x18007721d  mov     rcx, rdi
0x180077220  call    sqlite3RCStrNew
0x180077225  mov     rsi, rax
0x180077228  test    rax, rax
0x18007722b  jnz     short loc_18007724D
0x18007722d  or      byte ptr [rbx+21h], 1
0x180077231  mov     rcx, [rbx]
0x180077234  test    rcx, rcx
0x180077237  jz      short loc_18007723E
0x180077239  call    sqlite3_result_error_nomem
0x18007723e  mov     rcx, rbx
0x180077241  call    jsonStringReset
0x180077246  mov     eax, 7
0x18007724b  jmp     short loc_18007726B
0x18007724d  mov     r8, [rbx+18h]; Size
0x180077251  mov     rcx, rsi; void *
0x180077254  mov     rdx, [rbx+8]; Src
0x180077258  call    memcpy_0
0x18007725d  mov     [rbx+8], rsi
0x180077261  mov     byte ptr [rbx+20h], 0
0x180077265  mov     [rbx+10h], rdi
0x180077269  xor     eax, eax
0x18007726b  mov     rbx, [rsp+28h+arg_0]
0x180077270  mov     rsi, [rsp+28h+arg_8]
0x180077275  add     rsp, 20h
0x180077279  pop     rdi
0x18007727a  retn
0x18007727b  mov     rsi, [rbx+8]
0x18007727f  lea     rdx, [rdi+9]
0x180077283  lea     rcx, [rsi-8]
0x180077287  call    sqlite3_realloc64
0x18007728c  test    rax, rax
0x18007728f  jnz     short loc_18007729C
0x180077291  lea     rcx, [rsi-8]
0x180077295  call    sqlite3_free
0x18007729a  jmp     short loc_1800772A6
0x18007729c  add     rax, 8
0x1800772a0  mov     [rbx+8], rax
0x1800772a4  jnz     short loc_180077265
0x1800772a6  or      byte ptr [rbx+21h], 1
0x1800772aa  lea     rax, [rbx+22h]
0x1800772ae  mov     [rbx+8], rax
0x1800772b2  mov     qword ptr [rbx+10h], 64h ; 'd'
0x1800772ba  mov     qword ptr [rbx+18h], 0
0x1800772c2  mov     byte ptr [rbx+20h], 1
0x1800772c6  jmp     loc_180077246
```
