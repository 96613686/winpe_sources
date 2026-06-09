# AllocateSymcryptRsakey

- ea: `0x180043050`
- end: `0x1800430b9`
- name: `AllocateSymcryptRsakey`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004a3b0`
- `0x180056b80`

## callees

- `0x18000ecb0`
- `0x180043050`
- `0x1800430c0`

## string_xrefs

- `0x18004309a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall AllocateSymcryptRsakey(__int64 a1)
{
  int v1; // eax
  __int64 v3; // rax
  _DWORD v5[6]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_DWORD *)(a1 + 12);
  v5[0] = 1;
  v5[1] = v1;
  v5[2] = 2;
  v5[3] = 1;
  v3 = SymCryptRsakeyAllocate(v5);
  *(_QWORD *)(a1 + 32) = v3;
  if ( v3 )
    return 0;
  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 386);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180043050  push    rbx
0x180043052  sub     rsp, 30h
0x180043056  mov     eax, [rcx+0Ch]
0x180043059  mov     rbx, rcx
0x18004305c  lea     rcx, [rsp+38h+var_18]
0x180043061  mov     [rsp+38h+var_18], 1
0x180043069  mov     [rsp+38h+var_14], eax
0x18004306d  mov     [rsp+38h+var_10], 2
0x180043075  mov     [rsp+38h+var_C], 1
0x18004307d  call    SymCryptRsakeyAllocate
0x180043082  mov     [rbx+20h], rax
0x180043086  test    rax, rax
0x180043089  jz      short loc_180043094
0x18004308b  xor     eax, eax
0x18004308d  add     rsp, 30h
0x180043091  pop     rbx
0x180043092  retn
0x180043094  mov     r9d, 182h
0x18004309a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800430a1  lea     rdx, aStatus; "Status"
0x1800430a8  mov     ecx, 0C0000017h
0x1800430ad  call    DebugTraceError
0x1800430b2  mov     eax, 0C0000017h
0x1800430b7  jmp     short loc_18004308D
```
