# SetParameterV1Format

- ea: `0x18006a34c`
- end: `0x18006a485`
- name: `SetParameterV1Format`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069e28`

## callees

- `0x18000ecb0`
- `0x18001b67c`
- `0x1800497f0`
- `0x180056cf0`
- `0x18006a34c`

## string_xrefs

- `0x18006a42a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x18006a45c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall SetParameterV1Format(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v4; // r8d
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // r11
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v12; // [rsp+A8h] [rbp+10h] BYREF

  v12 = 0;
  v4 = *(_DWORD *)(a3 + 12);
  if ( a2 >= (unsigned __int64)(2 * v4) + 56 )
  {
    if ( *(_DWORD *)(a1 + 8) == v4 && v4 <= 0x80 )
    {
      v7 = a1 + 56;
      ReverseMemCopy(&v12, a1 + 12, 4);
      v9 = SymCryptDlgroupSetValue(
             v7,
             *(_DWORD *)(a3 + 12),
             (int)a1 + 36,
             20,
             v7 + v8,
             *(_DWORD *)(a3 + 12),
             2,
             0,
             a1 + 16,
             0x14u,
             v12,
             v12 != -1,
             *(_QWORD *)(a3 + 32));
      if ( v9 )
      {
        v10 = SymcryptErrorCodeToNtStatus(v9);
        DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 706);
        *(_DWORD *)(a3 + 28) |= 4u;
      }
      *(_DWORD *)(a3 + 28) |= 2u;
      v6 = 0;
      *(_DWORD *)(a3 + 20) = 0;
    }
    else
    {
      v6 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 673);
    }
  }
  else
  {
    return (unsigned int)-1073741789;
  }
  return v6;
}

```

## disassembly

```asm
0x18006a34c  mov     rax, rsp
0x18006a34f  push    rbx
0x18006a350  push    rbp
0x18006a351  push    rsi
0x18006a352  push    rdi
0x18006a353  sub     rsp, 78h
0x18006a357  mov     rsi, r8
0x18006a35a  mov     dword ptr [rax+10h], 0
0x18006a361  mov     r8d, [r8+0Ch]
0x18006a365  mov     rbp, rcx
0x18006a368  mov     eax, edx
0x18006a36a  lea     r9d, [r8+r8]
0x18006a36e  add     r9, 38h ; '8'
0x18006a372  cmp     rax, r9
0x18006a375  jnb     short loc_18006A381
0x18006a377  mov     ebx, 0C0000023h
0x18006a37c  jmp     loc_18006A479
0x18006a381  mov     r11d, [rcx+8]
0x18006a385  cmp     r11d, r8d
0x18006a388  jnz     loc_18006A456
0x18006a38e  cmp     r8d, 80h
0x18006a395  ja      loc_18006A456
0x18006a39b  lea     rdx, [rcx+0Ch]
0x18006a39f  mov     ebx, 1
0x18006a3a4  lea     rdi, [rcx+38h]
0x18006a3a8  lea     rcx, [rsp+98h+arg_8]
0x18006a3b0  lea     r8d, [rbx+3]
0x18006a3b4  call    ReverseMemCopy
0x18006a3b9  mov     r9d, [rsp+98h+arg_8]
0x18006a3c1  lea     r10, [rbp+10h]
0x18006a3c5  mov     edx, [rsi+0Ch]; int
0x18006a3c8  lea     r8, [rbp+24h]; int
0x18006a3cc  xor     eax, eax
0x18006a3ce  mov     rcx, rdi; int
0x18006a3d1  cmp     r9d, 0FFFFFFFFh
0x18006a3d5  cmovz   ebx, eax
0x18006a3d8  mov     rax, [rsi+20h]
0x18006a3dc  mov     [rsp+98h+var_38], rax; __int64
0x18006a3e1  add     r11, rdi
0x18006a3e4  mov     [rsp+98h+var_40], ebx; int
0x18006a3e8  mov     [rsp+98h+var_48], r9d; int
0x18006a3ed  mov     r9d, 14h; int
0x18006a3f3  mov     [rsp+98h+Size], r9; Size
0x18006a3f8  mov     [rsp+98h+var_58], r10; __int64
0x18006a3fd  mov     [rsp+98h+var_60], 0; __int64
0x18006a406  mov     [rsp+98h+var_68], 2; int
0x18006a40e  mov     qword ptr [rsp+98h+var_70], rdx; int
0x18006a413  mov     [rsp+98h+var_78], r11; __int64
0x18006a418  call    SymCryptDlgroupSetValue
0x18006a41d  test    eax, eax
0x18006a41f  jz      short loc_18006A447
0x18006a421  mov     ecx, eax
0x18006a423  call    SymcryptErrorCodeToNtStatus
0x18006a428  mov     ecx, eax
0x18006a42a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a431  mov     r9d, 2C2h
0x18006a437  lea     rdx, aStatus; "Status"
0x18006a43e  call    DebugTraceError
0x18006a443  or      dword ptr [rsi+1Ch], 4
0x18006a447  or      dword ptr [rsi+1Ch], 2
0x18006a44b  xor     ebx, ebx
0x18006a44d  mov     dword ptr [rsi+14h], 0
0x18006a454  jmp     short loc_18006A479
0x18006a456  mov     r9d, 2A1h
0x18006a45c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a463  lea     rdx, aStatus; "Status"
0x18006a46a  mov     ecx, 0C000000Dh
0x18006a46f  mov     ebx, 0C000000Dh
0x18006a474  call    DebugTraceError
0x18006a479  mov     eax, ebx
0x18006a47b  add     rsp, 78h
0x18006a47f  pop     rdi
0x18006a480  pop     rsi
0x18006a481  pop     rbp
0x18006a482  pop     rbx
0x18006a483  retn
```
