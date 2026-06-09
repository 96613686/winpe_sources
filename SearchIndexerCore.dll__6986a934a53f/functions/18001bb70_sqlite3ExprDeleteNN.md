# sqlite3ExprDeleteNN

- ea: `0x18001bb70`
- end: `0x18001bc36`
- name: `sqlite3ExprDeleteNN`
- size: `198`
- prototype: ``
- caller_count: `62`
- callee_count: `5`
- tags: ``

## callers

- `0x180001214`
- `0x180005650`
- `0x180008c0c`
- `0x18000a954`
- `0x18000d254`
- `0x18000ebc4`
- `0x180013ed8`
- `0x180015118`
- `0x180015540`
- `0x180017938`
- `0x1800192e0`
- `0x180019470`
- `0x18001bb60`
- `0x18001bb70`
- `0x18001bd68`
- `0x18001cb6c`
- `0x18001d1c8`
- `0x18002edb0`
- `0x18002f6b0`
- `0x18004cbec`
- `0x18004f3a4`
- `0x18005166c`
- `0x180051740`
- `0x180051808`
- `0x180051f78`
- `0x1800576e0`
- `0x180057818`
- `0x180057dec`
- `0x1800583d0`
- `0x180058b64`
- `0x18005a538`
- `0x18005dc20`
- `0x18005e21c`
- `0x18005f764`
- `0x180060ddc`
- `0x180064df4`
- `0x18006565c`
- `0x1800658bc`
- `0x180067af4`
- `0x1800692d0`
- `0x18006af8c`
- `0x18006b410`
- `0x18006d68c`
- `0x18006fafc`
- `0x180070218`
- `0x1800711f4`
- `0x180071d4c`
- `0x180073978`
- `0x180074294`
- `0x180074440`

## callees

- `0x18001b818`
- `0x18001bb70`
- `0x18001bc40`
- `0x180025770`
- `0x180060370`

## pseudocode

```c
__int64 __fastcall sqlite3ExprDeleteNN(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rsi
  __int64 *v6; // rdx

  while ( (*(_DWORD *)(a2 + 4) & 0x810000) == 0 )
  {
    if ( *(_QWORD *)(a2 + 24) )
    {
      result = sqlite3ExprDeleteNN(a1);
    }
    else
    {
      v6 = *(__int64 **)(a2 + 32);
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
    result = sqlite3DbNNFreeNN(a1, a2);
    a2 = v5;
  }
  if ( (*(_DWORD *)(a2 + 4) & 0x8000000) == 0 )
    return sqlite3DbNNFreeNN(a1, a2);
  return result;
}

```

## disassembly

```asm
0x18001bb70  mov     [rsp+arg_0], rbx
0x18001bb75  mov     [rsp+arg_8], rsi
0x18001bb7a  push    rdi
0x18001bb7b  sub     rsp, 20h
0x18001bb7f  mov     rbx, rdx
0x18001bb82  mov     rdi, rcx
0x18001bb85  test    dword ptr [rbx+4], 810000h
0x18001bb8c  jnz     short loc_18001BBCA
0x18001bb8e  mov     rdx, [rbx+18h]
0x18001bb92  mov     rcx, rdi
0x18001bb95  test    rdx, rdx
0x18001bb98  jz      short loc_18001BBF0
0x18001bb9a  call    sqlite3ExprDeleteNN
0x18001bb9f  mov     rsi, [rbx+10h]
0x18001bba3  test    rsi, rsi
0x18001bba6  jz      short loc_18001BBCA
0x18001bba8  cmp     byte ptr [rbx], 0B2h
0x18001bbab  jz      short loc_18001BBCA
0x18001bbad  test    dword ptr [rbx+4], 8000000h
0x18001bbb4  jnz     short loc_18001BBBF
0x18001bbb6  test    dword ptr [rsi+4], 8000000h
0x18001bbbd  jz      short loc_18001BC19
0x18001bbbf  mov     rdx, rsi
0x18001bbc2  mov     rcx, rdi
0x18001bbc5  call    sqlite3ExprDeleteNN
0x18001bbca  test    dword ptr [rbx+4], 8000000h
0x18001bbd1  jz      short loc_18001BBE3
0x18001bbd3  mov     rbx, [rsp+28h+arg_0]
0x18001bbd8  mov     rsi, [rsp+28h+arg_8]
0x18001bbdd  add     rsp, 20h
0x18001bbe1  pop     rdi
0x18001bbe2  retn
0x18001bbe3  mov     rdx, rbx
0x18001bbe6  mov     rcx, rdi
0x18001bbe9  call    sqlite3DbNNFreeNN
0x18001bbee  jmp     short loc_18001BBD3
0x18001bbf0  test    dword ptr [rbx+4], 1000h
0x18001bbf7  mov     rdx, [rbx+20h]
0x18001bbfb  jnz     short loc_18001BC2C
0x18001bbfd  call    sqlite3ExprListDeleteGeneric
0x18001bc02  test    dword ptr [rbx+4], 1000000h
0x18001bc09  jz      short loc_18001BB9F
0x18001bc0b  mov     rdx, [rbx+40h]
0x18001bc0f  mov     rcx, rdi
0x18001bc12  call    sqlite3WindowDelete
0x18001bc17  jmp     short loc_18001BB9F
0x18001bc19  mov     rdx, rbx
0x18001bc1c  mov     rcx, rdi
0x18001bc1f  call    sqlite3DbNNFreeNN
0x18001bc24  mov     rbx, rsi
0x18001bc27  jmp     loc_18001BB85
0x18001bc2c  call    sqlite3SelectDelete
0x18001bc31  jmp     loc_18001BB9F
```
