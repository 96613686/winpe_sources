# MSCryptGetDHAlgProperty

- ea: `0x18005229c`
- end: `0x180052399`
- name: `MSCryptGetDHAlgProperty`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800685a0`

## callees

- `0x18000ecb0`
- `0x18005229c`
- `0x18007f765`

## string_xrefs

- `0x18005234a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x18005237a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetDHAlgProperty(
        _DWORD *a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        _DWORD *a5,
        int a6)
{
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx

  if ( !a1 || !a2 || !a5 || a6 )
  {
    v9 = 320;
    goto LABEL_16;
  }
  if ( *a1 != 16 || a1[1] != 1297301836 || a1[2] != 196610 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", 151);
    v9 = 330;
LABEL_16:
    v10 = 3221225485LL;
    v8 = -1073741811;
    goto LABEL_17;
  }
  if ( wcscmp_0(a2, L"KeyLengths") )
  {
    v8 = -1073741637;
    v9 = 367;
    v10 = 3221225659LL;
LABEL_17:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v9);
    return v8;
  }
  v8 = 0;
  *a5 = 12;
  if ( a3 )
  {
    if ( a4 >= 0xC )
    {
      *a3 = 512;
      a3[1] = 4096;
      a3[2] = 8;
    }
    else
    {
      return (unsigned int)-1073741789;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18005229c  push    rbx
0x18005229e  push    rbp
0x18005229f  push    rsi
0x1800522a0  push    rdi
0x1800522a1  sub     rsp, 28h
0x1800522a5  mov     ebp, r9d
0x1800522a8  mov     rdi, r8
0x1800522ab  mov     rax, rdx
0x1800522ae  test    rcx, rcx
0x1800522b1  jz      loc_18005236A
0x1800522b7  test    rax, rax
0x1800522ba  jz      loc_18005236A
0x1800522c0  mov     rsi, [rsp+48h+arg_20]
0x1800522c5  test    rsi, rsi
0x1800522c8  jz      loc_18005236A
0x1800522ce  cmp     [rsp+48h+arg_28], 0
0x1800522d3  jnz     loc_18005236A
0x1800522d9  cmp     dword ptr [rcx], 10h
0x1800522dc  jnz     short loc_180052344
0x1800522de  cmp     dword ptr [rcx+4], 4D53414Ch
0x1800522e5  jnz     short loc_180052344
0x1800522e7  cmp     dword ptr [rcx+8], 30002h
0x1800522ee  jnz     short loc_180052344
0x1800522f0  lea     rdx, aKeylengths; "KeyLengths"
0x1800522f7  mov     rcx, rax; String1
0x1800522fa  call    wcscmp_0
0x1800522ff  test    eax, eax
0x180052301  jnz     short loc_180052332
0x180052303  xor     ebx, ebx
0x180052305  mov     dword ptr [rsi], 0Ch
0x18005230b  test    rdi, rdi
0x18005230e  jz      short loc_18005238D
0x180052310  cmp     ebp, 0Ch
0x180052313  jnb     short loc_18005231C
0x180052315  mov     ebx, 0C0000023h
0x18005231a  jmp     short loc_18005238D
0x18005231c  mov     dword ptr [rdi], 200h
0x180052322  mov     dword ptr [rdi+4], 1000h
0x180052329  mov     dword ptr [rdi+8], 8
0x180052330  jmp     short loc_18005238D
0x180052332  mov     ebx, 0C00000BBh
0x180052337  mov     r9d, 16Fh
0x18005233d  mov     ecx, 0C00000BBh
0x180052342  jmp     short loc_18005237A
0x180052344  mov     r9d, 97h
0x18005234a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052351  lea     rdx, aStatus; "Status"
0x180052358  mov     ecx, 0C000000Dh
0x18005235d  call    DebugTraceError
0x180052362  mov     r9d, 14Ah
0x180052368  jmp     short loc_180052370
0x18005236a  mov     r9d, 140h
0x180052370  mov     ecx, 0C000000Dh
0x180052375  mov     ebx, 0C000000Dh
0x18005237a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052381  lea     rdx, aStatus; "Status"
0x180052388  call    DebugTraceError
0x18005238d  mov     eax, ebx
0x18005238f  add     rsp, 28h
0x180052393  pop     rdi
0x180052394  pop     rsi
0x180052395  pop     rbp
0x180052396  pop     rbx
0x180052397  retn
```
