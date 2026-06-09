# GetDHGroupParam

- ea: `0x180067f48`
- end: `0x18006803b`
- name: `GetDHGroupParam`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180068378`

## callees

- `0x18000ecb0`
- `0x1800525dc`
- `0x180056cf0`
- `0x180063180`
- `0x180067f48`

## string_xrefs

- `0x180068015`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall GetDHGroupParam(__int64 a1, _DWORD *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int Value; // eax
  int v12; // [rsp+40h] [rbp-28h]

  v4 = 0;
  v7 = 2 * *(_DWORD *)(a1 + 12) + 12;
  *a4 = v7;
  if ( a2 )
  {
    if ( a3 >= v7 )
    {
      if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
      {
        memset_0(a2, 0, a3);
        a2[1] = 1297107012;
        a2[2] = *(_DWORD *)(a1 + 12);
        *a2 = 2 * *(_DWORD *)(a1 + 12) + 12;
        Value = SymCryptDlgroupGetValue(
                  *(_QWORD *)(a1 + 24),
                  (int)a2 + 12,
                  *(_DWORD *)(a1 + 12),
                  0,
                  0,
                  (__int64)a2 + *(unsigned int *)(a1 + 12) + 12,
                  *(unsigned int *)(a1 + 12),
                  2,
                  v12,
                  0,
                  0,
                  0);
        if ( !Value )
          return v4;
        v4 = SymcryptErrorCodeToNtStatus(Value);
        v9 = v4;
        v8 = 444;
      }
      else
      {
        v4 = -1073741816;
        v8 = 413;
        v9 = 3221225480LL;
      }
      DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v8);
      return v4;
    }
    return (unsigned int)-1073741789;
  }
  return v4;
}

```

## disassembly

```asm
0x180067f48  mov     [rsp+arg_0], rbx
0x180067f4d  mov     [rsp+arg_8], rsi
0x180067f52  push    rdi
0x180067f53  sub     rsp, 60h
0x180067f57  mov     eax, [rcx+0Ch]
0x180067f5a  xor     ebx, ebx
0x180067f5c  mov     rsi, rdx
0x180067f5f  mov     rdi, rcx
0x180067f62  lea     eax, ds:0Ch[rax*2]
0x180067f69  mov     [r9], eax
0x180067f6c  test    rdx, rdx
0x180067f6f  jz      loc_180068028
0x180067f75  cmp     r8d, eax
0x180067f78  jnb     short loc_180067F84
0x180067f7a  mov     ebx, 0C0000023h
0x180067f7f  jmp     loc_180068028
0x180067f84  test    byte ptr [rcx+10h], 2
0x180067f88  jnz     short loc_180067F9C
0x180067f8a  mov     ebx, 0C0000008h
0x180067f8f  mov     r9d, 19Dh
0x180067f95  mov     ecx, 0C0000008h
0x180067f9a  jmp     short loc_180068015
0x180067f9c  mov     r8d, r8d; Size
0x180067f9f  xor     edx, edx; Val
0x180067fa1  mov     rcx, rsi; void *
0x180067fa4  call    memset_0
0x180067fa9  mov     [rsp+68h+var_10], rbx; __int64
0x180067fae  lea     rdx, [rsi+0Ch]; int
0x180067fb2  mov     dword ptr [rsi+4], 4D504844h
0x180067fb9  xor     r9d, r9d; int
0x180067fbc  mov     eax, [rdi+0Ch]
0x180067fbf  mov     [rsi+8], eax
0x180067fc2  mov     eax, [rdi+0Ch]
0x180067fc5  mov     [rsp+68h+var_18], rbx; __int64
0x180067fca  mov     [rsp+68h+var_20], rbx; void *
0x180067fcf  mov     [rsp+68h+var_30], 2; int
0x180067fd7  lea     eax, ds:0Ch[rax*2]
0x180067fde  mov     [rsi], eax
0x180067fe0  mov     r8d, [rdi+0Ch]; int
0x180067fe4  mov     rcx, [rdi+18h]; int
0x180067fe8  mov     [rsp+68h+var_38], r8; __int64
0x180067fed  lea     rax, [r8+rdx]
0x180067ff1  mov     [rsp+68h+var_40], rax; __int64
0x180067ff6  mov     [rsp+68h+var_48], rbx; __int64
0x180067ffb  call    SymCryptDlgroupGetValue
0x180068000  test    eax, eax
0x180068002  jz      short loc_180068028
0x180068004  mov     ecx, eax
0x180068006  call    SymcryptErrorCodeToNtStatus
0x18006800b  mov     ebx, eax
0x18006800d  mov     ecx, eax
0x18006800f  mov     r9d, 1BCh
0x180068015  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006801c  lea     rdx, aStatus; "Status"
0x180068023  call    DebugTraceError
0x180068028  mov     rsi, [rsp+68h+arg_8]
0x18006802d  mov     eax, ebx
0x18006802f  mov     rbx, [rsp+68h+arg_0]
0x180068034  add     rsp, 60h
0x180068038  pop     rdi
0x180068039  retn
```
