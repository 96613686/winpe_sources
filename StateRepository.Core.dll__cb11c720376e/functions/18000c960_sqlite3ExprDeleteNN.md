# sqlite3ExprDeleteNN

- ea: `0x18000c960`
- end: `0x18000ca2a`
- name: `sqlite3ExprDeleteNN`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `61`
- callee_count: `5`
- tags: ``

## callers

- `0x180003128`
- `0x18000ad30`
- `0x18000c454`
- `0x18000c950`
- `0x18000c960`
- `0x180010950`
- `0x1800167c0`
- `0x180017fac`
- `0x180019e50`
- `0x18001a8dc`
- `0x18001be94`
- `0x1800355c0`
- `0x180037194`
- `0x18003b070`
- `0x18003d188`
- `0x18003df2c`
- `0x18003e04c`
- `0x18003e178`
- `0x180043968`
- `0x180044538`
- `0x180046630`
- `0x18004df0c`
- `0x18004ed80`
- `0x18004f6d8`
- `0x180054f08`
- `0x1800555e8`
- `0x180058e44`
- `0x180059634`
- `0x1800597b4`
- `0x18005a2dc`
- `0x18005a35c`
- `0x18005c644`
- `0x18005c958`
- `0x18005d6a4`
- `0x18005dae0`
- `0x18005dd88`
- `0x18005ec3c`
- `0x18005f714`
- `0x18005fc50`
- `0x1800625a8`
- `0x180062894`
- `0x180062cb8`
- `0x180063468`
- `0x180064c24`
- `0x18006805c`
- `0x18006c53c`
- `0x18006e4c8`
- `0x18006e7ec`
- `0x18006f250`
- `0x18006fe24`

## callees

- `0x18000c850`
- `0x18000c930`
- `0x18000c960`
- `0x18005fbb8`
- `0x18008b810`

## pseudocode

```c
__int64 __fastcall sqlite3ExprDeleteNN(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rsi
  __int64 v6; // rdx

  while ( (*(_DWORD *)(a2 + 4) & 0x810000) == 0 )
  {
    if ( *(_QWORD *)(a2 + 24) )
    {
      result = sqlite3ExprDeleteNN(a1);
    }
    else
    {
      v6 = *(_QWORD *)(a2 + 32);
      if ( (*(_DWORD *)(a2 + 4) & 0x1000) != 0 )
      {
        result = sqlite3SelectDelete(a1, v6);
      }
      else
      {
        result = sqlite3ExprListDeleteGeneric(a1, v6);
        if ( (*(_DWORD *)(a2 + 4) & 0x1000000) != 0 )
          result = sqlite3WindowDelete(a1, *(_QWORD *)(a2 + 64));
      }
    }
    v5 = *(_QWORD *)(a2 + 16);
    if ( !v5 || *(_BYTE *)a2 == 0xB2 )
      break;
    if ( (*(_DWORD *)(a2 + 4) & 0x8000000) != 0 || (*(_DWORD *)(v5 + 4) & 0x8000000) != 0 )
    {
      result = sqlite3ExprDeleteNN(a1);
      break;
    }
    result = sqlite3DbNNFreeNN(a1);
    a2 = v5;
  }
  if ( (*(_DWORD *)(a2 + 4) & 0x8000000) == 0 )
    return sqlite3DbNNFreeNN(a1);
  return result;
}

```

## disassembly

```asm
0x18000c960  mov     [rsp+arg_0], rbx
0x18000c965  mov     [rsp+arg_8], rsi
0x18000c96a  push    rdi
0x18000c96b  sub     rsp, 20h
0x18000c96f  mov     rbx, rdx
0x18000c972  mov     rdi, rcx
0x18000c975  test    dword ptr [rbx+4], 810000h
0x18000c97c  jnz     short loc_18000C9BA
0x18000c97e  mov     rdx, [rbx+18h]
0x18000c982  mov     rcx, rdi
0x18000c985  test    rdx, rdx
0x18000c988  jz      short loc_18000C9E0
0x18000c98a  call    sqlite3ExprDeleteNN
0x18000c98f  mov     rsi, [rbx+10h]
0x18000c993  test    rsi, rsi
0x18000c996  jz      short loc_18000C9BA
0x18000c998  cmp     byte ptr [rbx], 0B2h
0x18000c99b  jz      short loc_18000C9BA
0x18000c99d  test    dword ptr [rbx+4], 8000000h
0x18000c9a4  jnz     short loc_18000C9AF
0x18000c9a6  test    dword ptr [rsi+4], 8000000h
0x18000c9ad  jz      short loc_18000C9F4
0x18000c9af  mov     rdx, rsi
0x18000c9b2  mov     rcx, rdi
0x18000c9b5  call    sqlite3ExprDeleteNN
0x18000c9ba  test    dword ptr [rbx+4], 8000000h
0x18000c9c1  jz      short loc_18000C9D3
0x18000c9c3  mov     rbx, [rsp+28h+arg_0]
0x18000c9c8  mov     rsi, [rsp+28h+arg_8]
0x18000c9cd  add     rsp, 20h
0x18000c9d1  pop     rdi
0x18000c9d2  retn
0x18000c9d3  mov     rdx, rbx
0x18000c9d6  mov     rcx, rdi
0x18000c9d9  call    sqlite3DbNNFreeNN
0x18000c9de  jmp     short loc_18000C9C3
0x18000c9e0  test    dword ptr [rbx+4], 1000h
0x18000c9e7  mov     rdx, [rbx+20h]
0x18000c9eb  jz      short loc_18000CA07
0x18000c9ed  call    sqlite3SelectDelete
0x18000c9f2  jmp     short loc_18000C98F
0x18000c9f4  mov     rdx, rbx
0x18000c9f7  mov     rcx, rdi
0x18000c9fa  call    sqlite3DbNNFreeNN
0x18000c9ff  mov     rbx, rsi
0x18000ca02  jmp     loc_18000C975
0x18000ca07  call    sqlite3ExprListDeleteGeneric
0x18000ca0c  test    dword ptr [rbx+4], 1000000h
0x18000ca13  jz      loc_18000C98F
0x18000ca19  mov     rdx, [rbx+40h]
0x18000ca1d  mov     rcx, rdi
0x18000ca20  call    sqlite3WindowDelete
0x18000ca25  jmp     loc_18000C98F
```
