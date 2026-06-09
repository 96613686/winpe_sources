# SetParameterV2Format

- ea: `0x18006a48c`
- end: `0x18006a63d`
- name: `SetParameterV2Format`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180069e28`

## callees

- `0x18000ecb0`
- `0x18001b67c`
- `0x1800497f0`
- `0x180056cf0`
- `0x1800693ac`
- `0x18006a48c`

## string_xrefs

- `0x18006a5cf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x18006a604`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall SetParameterV2Format(_DWORD *a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // ecx
  unsigned int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rbp
  __int64 v11; // r14
  __int64 v12; // r15
  int v13; // esi
  __int64 v14; // r9
  size_t Size; // rbx
  __int64 SymCryptDlgroupHashAlgorithm; // rax
  int v17; // edx
  int v18; // r10d
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v22; // [rsp+A8h] [rbp+10h] BYREF

  v22 = 0;
  if ( a2 < 0x20 )
    return (unsigned int)-1073741789;
  v6 = *(_DWORD *)(a3 + 12);
  v7 = *(_DWORD *)(a3 + 16);
  v8 = 2 * (v7 + v6) + 32;
  if ( a2 < v8 )
  {
    return (unsigned int)-1073741789;
  }
  else if ( *a1 == v8
         && (v9 = (unsigned int)a1[2], (_DWORD)v9 == v6)
         && a1[6] == v7
         && a1[5] == v7
         && (unsigned int)v9 > 0x80
         && a1[3] == *(_DWORD *)(a3 + 24)
         && a1[4] == *(_DWORD *)(a3 + 20) )
  {
    v10 = (__int64)(a1 + 8);
    v11 = (__int64)a1 + (unsigned int)a1[5] + 32;
    v12 = v11 + (unsigned int)a1[6];
    ReverseMemCopy(&v22, a1 + 7, 4);
    v13 = v22;
    Size = *(unsigned int *)(v14 + 20);
    SymCryptDlgroupHashAlgorithm = GetSymCryptDlgroupHashAlgorithm(
                                     *(unsigned int *)(a3 + 24),
                                     *(unsigned int *)(a3 + 12));
    v19 = SymCryptDlgroupSetValue(
            v12,
            v17,
            v11,
            *(_DWORD *)(a3 + 16),
            v12 + v9,
            v17,
            2,
            SymCryptDlgroupHashAlgorithm,
            v10,
            Size,
            v13,
            v18,
            *(_QWORD *)(a3 + 32));
    if ( v19 )
    {
      v20 = SymcryptErrorCodeToNtStatus(v19);
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 805);
      *(_DWORD *)(a3 + 28) |= 4u;
    }
    *(_DWORD *)(a3 + 28) |= 2u;
    v5 = 0;
    *(_DWORD *)(a3 + 20) = 1;
  }
  else
  {
    v5 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 772);
  }
  return v5;
}

```

## disassembly

```asm
0x18006a48c  mov     rax, rsp
0x18006a48f  mov     [rax+8], rbx
0x18006a493  mov     [rax+18h], rbp
0x18006a497  push    rsi
0x18006a498  push    rdi
0x18006a499  push    r13
0x18006a49b  push    r14
0x18006a49d  push    r15
0x18006a49f  sub     rsp, 70h
0x18006a4a3  mov     dword ptr [rax+10h], 0
0x18006a4aa  mov     r13, r8
0x18006a4ad  mov     r9, rcx
0x18006a4b0  cmp     edx, 20h ; ' '
0x18006a4b3  jnb     short loc_18006A4BF
0x18006a4b5  mov     ebx, 0C0000023h
0x18006a4ba  jmp     loc_18006A621
0x18006a4bf  mov     r8d, [r8+0Ch]
0x18006a4c3  mov     ecx, [r13+10h]
0x18006a4c7  lea     eax, [rcx+r8]
0x18006a4cb  lea     eax, ds:20h[rax*2]
0x18006a4d2  cmp     edx, eax
0x18006a4d4  jb      short loc_18006A4B5
0x18006a4d6  cmp     [r9], eax
0x18006a4d9  jnz     loc_18006A5FE
0x18006a4df  mov     edi, [r9+8]
0x18006a4e3  cmp     edi, r8d
0x18006a4e6  jnz     loc_18006A5FE
0x18006a4ec  cmp     [r9+18h], ecx
0x18006a4f0  jnz     loc_18006A5FE
0x18006a4f6  cmp     [r9+14h], ecx
0x18006a4fa  jnz     loc_18006A5FE
0x18006a500  cmp     edi, 80h
0x18006a506  jbe     loc_18006A5FE
0x18006a50c  mov     eax, [r13+18h]
0x18006a510  cmp     [r9+0Ch], eax
0x18006a514  jnz     loc_18006A5FE
0x18006a51a  mov     eax, [r13+14h]
0x18006a51e  cmp     [r9+10h], eax
0x18006a522  jnz     loc_18006A5FE
0x18006a528  mov     r14d, [r9+14h]
0x18006a52c  lea     rbp, [r9+20h]
0x18006a530  mov     r15d, [r9+18h]
0x18006a534  lea     rdx, [r9+1Ch]
0x18006a538  add     r14, rbp
0x18006a53b  lea     rcx, [rsp+98h+arg_8]
0x18006a543  mov     r8d, 4
0x18006a549  add     r15, r14
0x18006a54c  call    ReverseMemCopy
0x18006a551  mov     esi, [rsp+98h+arg_8]
0x18006a558  xor     eax, eax
0x18006a55a  mov     edx, [r13+0Ch]
0x18006a55e  cmp     esi, 0FFFFFFFFh
0x18006a561  mov     ebx, [r9+14h]
0x18006a565  mov     ecx, 1
0x18006a56a  cmovz   ecx, eax
0x18006a56d  lea     r10d, [rcx+rcx]
0x18006a571  mov     ecx, [r13+18h]
0x18006a575  call    GetSymCryptDlgroupHashAlgorithm
0x18006a57a  mov     r9d, [r13+10h]; int
0x18006a57e  mov     r11, rax
0x18006a581  mov     rax, [r13+20h]
0x18006a585  add     rdi, r15
0x18006a588  mov     [rsp+98h+var_38], rax; __int64
0x18006a58d  mov     r8, r14; int
0x18006a590  mov     [rsp+98h+var_40], r10d; int
0x18006a595  mov     rcx, r15; int
0x18006a598  mov     [rsp+98h+var_48], esi; int
0x18006a59c  mov     [rsp+98h+Size], rbx; Size
0x18006a5a1  mov     [rsp+98h+var_58], rbp; __int64
0x18006a5a6  mov     [rsp+98h+var_60], r11; __int64
0x18006a5ab  mov     [rsp+98h+var_68], 2; int
0x18006a5b3  mov     qword ptr [rsp+98h+var_70], rdx; int
0x18006a5b8  mov     [rsp+98h+var_78], rdi; __int64
0x18006a5bd  call    SymCryptDlgroupSetValue
0x18006a5c2  test    eax, eax
0x18006a5c4  jz      short loc_18006A5ED
0x18006a5c6  mov     ecx, eax
0x18006a5c8  call    SymcryptErrorCodeToNtStatus
0x18006a5cd  mov     ecx, eax
0x18006a5cf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a5d6  mov     r9d, 325h
0x18006a5dc  lea     rdx, aStatus; "Status"
0x18006a5e3  call    DebugTraceError
0x18006a5e8  or      dword ptr [r13+1Ch], 4
0x18006a5ed  or      dword ptr [r13+1Ch], 2
0x18006a5f2  xor     ebx, ebx
0x18006a5f4  mov     dword ptr [r13+14h], 1
0x18006a5fc  jmp     short loc_18006A621
0x18006a5fe  mov     r9d, 304h
0x18006a604  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a60b  lea     rdx, aStatus; "Status"
0x18006a612  mov     ecx, 0C000000Dh
0x18006a617  mov     ebx, 0C000000Dh
0x18006a61c  call    DebugTraceError
0x18006a621  lea     r11, [rsp+98h+var_28]
0x18006a626  mov     eax, ebx
0x18006a628  mov     rbx, [r11+30h]
0x18006a62c  mov     rbp, [r11+40h]
0x18006a630  mov     rsp, r11
0x18006a633  pop     r15
0x18006a635  pop     r14
0x18006a637  pop     r13
0x18006a639  pop     rdi
0x18006a63a  pop     rsi
0x18006a63b  retn
```
