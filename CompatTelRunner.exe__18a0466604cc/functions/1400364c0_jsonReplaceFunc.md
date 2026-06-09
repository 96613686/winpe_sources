# jsonReplaceFunc

- ea: `0x1400364c0`
- end: `0x1400365b8`
- name: `jsonReplaceFunc`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x140033fc8`
- `0x140034ef4`
- `0x1400364c0`
- `0x1400365c0`
- `0x140036e0c`
- `0x140073758`
- `0x14007c6ac`
- `0x14008ac90`
- `0x14008b8d0`

## string_xrefs

- `0x1400364e0`: `replace`
- `0x1400364e7`: `json_%s() needs an odd number of arguments`

## pseudocode

```c
void __fastcall jsonReplaceFunc(__int64 *a1, int a2, _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rsi
  unsigned int v12; // ebp
  __int64 v13; // rax
  __int64 v14; // rax

  if ( a2 >= 1 )
  {
    if ( (a2 & 1) != 0 )
    {
      v11 = jsonParseCached(a1, *a3, a1, a2 > 1);
      if ( v11 )
      {
        v12 = 1;
        if ( (unsigned int)a2 <= 1 )
        {
LABEL_10:
          jsonReturnJson(v11, *(_QWORD *)(v11 + 8), a1, 1);
        }
        else
        {
          while ( 1 )
          {
            LOBYTE(v10) = 1;
            v13 = sqlite3ValueText(a3[v12], v10);
            *(_BYTE *)(v11 + 54) = 1;
            v14 = jsonLookup(v11, v13, 0, a1);
            if ( *(_BYTE *)(v11 + 50) )
              break;
            if ( v14 )
              jsonReplaceNode(a1, v11, (v14 - *(_QWORD *)(v11 + 8)) >> 4, a3[v12 + 1]);
            v12 += 2;
            if ( v12 >= a2 )
              goto LABEL_10;
          }
        }
      }
    }
    else
    {
      v6 = sqlite3_mprintf("json_%s() needs an odd number of arguments", "replace");
      v7 = *a1;
      LOBYTE(v8) = 1;
      *((_DWORD *)a1 + 9) = 1;
      v9 = v6;
      sqlite3VdbeMemSetStr(v7, v6, -1, v8, -1);
      sqlite3_free(v9);
    }
  }
}

```

## disassembly

```asm
0x1400364c0  cmp     edx, 1
0x1400364c3  jl      locret_1400365B7
0x1400364c9  push    rbx
0x1400364ca  push    rbp
0x1400364cb  push    rsi
0x1400364cc  push    rdi
0x1400364cd  push    r14
0x1400364cf  sub     rsp, 30h
0x1400364d3  mov     ebx, edx
0x1400364d5  mov     r14, r8
0x1400364d8  mov     rdi, rcx
0x1400364db  test    bl, 1
0x1400364de  jnz     short loc_140036521
0x1400364e0  lea     rdx, aReplace; "replace"
0x1400364e7  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x1400364ee  call    sqlite3_mprintf
0x1400364f3  mov     rcx, [rdi]
0x1400364f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400364fa  mov     r9b, 1
0x1400364fd  mov     [rsp+58h+var_38], r8
0x140036502  mov     rdx, rax
0x140036505  mov     dword ptr [rdi+24h], 1
0x14003650c  mov     rbx, rax
0x14003650f  call    sqlite3VdbeMemSetStr
0x140036514  mov     rcx, rbx
0x140036517  call    sqlite3_free
0x14003651c  jmp     loc_1400365AD
0x140036521  mov     rdx, [r14]
0x140036524  xor     r9d, r9d
0x140036527  cmp     ebx, 1
0x14003652a  mov     r8, rdi
0x14003652d  setnle  r9b
0x140036531  call    jsonParseCached
0x140036536  mov     rsi, rax
0x140036539  test    rax, rax
0x14003653c  jz      short loc_1400365AD
0x14003653e  mov     ebp, 1
0x140036543  cmp     ebx, ebp
0x140036545  jbe     short loc_140036598
0x140036547  mov     ecx, ebp
0x140036549  mov     dl, 1
0x14003654b  mov     rcx, [r14+rcx*8]
0x14003654f  call    sqlite3ValueText
0x140036554  mov     r9, rdi
0x140036557  mov     byte ptr [rsi+36h], 1
0x14003655b  xor     r8d, r8d
0x14003655e  mov     rdx, rax
0x140036561  mov     rcx, rsi
0x140036564  call    jsonLookup
0x140036569  cmp     byte ptr [rsi+32h], 0
0x14003656d  mov     r8, rax
0x140036570  jnz     short loc_1400365AD
0x140036572  test    rax, rax
0x140036575  jz      short loc_140036591
0x140036577  sub     r8, [rsi+8]
0x14003657b  lea     eax, [rbp+1]
0x14003657e  mov     r9, [r14+rax*8]
0x140036582  mov     rdx, rsi
0x140036585  sar     r8, 4
0x140036589  mov     rcx, rdi
0x14003658c  call    jsonReplaceNode
0x140036591  add     ebp, 2
0x140036594  cmp     ebp, ebx
0x140036596  jb      short loc_140036547
0x140036598  mov     rdx, [rsi+8]
0x14003659c  mov     r9d, 1
0x1400365a2  mov     r8, rdi
0x1400365a5  mov     rcx, rsi
0x1400365a8  call    jsonReturnJson
0x1400365ad  add     rsp, 30h
0x1400365b1  pop     r14
0x1400365b3  pop     rdi
0x1400365b4  pop     rsi
0x1400365b5  pop     rbp
0x1400365b6  pop     rbx
0x1400365b7  retn
```
