# SetPrivateKeyVal

- ea: `0x180068e60`
- end: `0x180068f4a`
- name: `SetPrivateKeyVal`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180068ab8`

## callees

- `0x18000ecb0`
- `0x18001bf34`
- `0x18001bf88`
- `0x180056cf0`
- `0x1800581c0`
- `0x180068e60`

## string_xrefs

- `0x180068f24`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall SetPrivateKeyVal(__int64 a1, __int64 a2, unsigned int a3)
{
  int v3; // esi
  __int64 v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax

  v3 = a2;
  if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
  {
    v6 = 709;
LABEL_3:
    v7 = -1073741816;
    v8 = 3221225480LL;
LABEL_15:
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v6);
    return v7;
  }
  if ( (*(_BYTE *)(a1 + 16) & 2) == 0 )
  {
    v6 = 717;
    goto LABEL_3;
  }
  if ( !a3 || a3 > *(_DWORD *)(a1 + 12) )
  {
    v7 = -1073741811;
    v6 = 726;
    v8 = 3221225485LL;
    goto LABEL_15;
  }
  if ( *(_QWORD *)(a1 + 32) )
    SymCryptDlkeyFree();
  v9 = SymCryptDlkeyAllocate(*(_QWORD *)(a1 + 24), a2);
  *(_QWORD *)(a1 + 32) = v9;
  if ( !v9 )
  {
    v7 = -1073741801;
    v6 = 740;
    v8 = 3221225495LL;
    goto LABEL_15;
  }
  v7 = 0;
  v10 = SymCryptDlkeySetValue(v3, a3, 0, 0);
  if ( v10 )
  {
    v7 = SymcryptErrorCodeToNtStatus(v10);
    v8 = v7;
    v6 = 755;
    goto LABEL_15;
  }
  return v7;
}

```

## disassembly

```asm
0x180068e60  mov     [rsp+arg_0], rbx
0x180068e65  mov     [rsp+arg_8], rsi
0x180068e6a  push    rdi
0x180068e6b  sub     rsp, 40h
0x180068e6f  test    byte ptr [rcx+10h], 1
0x180068e73  mov     rsi, rdx
0x180068e76  mov     edi, r8d
0x180068e79  mov     rbx, rcx
0x180068e7c  jz      short loc_180068E93
0x180068e7e  mov     r9d, 2C5h
0x180068e84  mov     ebx, 0C0000008h
0x180068e89  mov     ecx, 0C0000008h
0x180068e8e  jmp     loc_180068F24
0x180068e93  test    byte ptr [rcx+10h], 2
0x180068e97  jnz     short loc_180068EA1
0x180068e99  mov     r9d, 2CDh
0x180068e9f  jmp     short loc_180068E84
0x180068ea1  cmp     edi, 1
0x180068ea4  jb      short loc_180068F14
0x180068ea6  cmp     edi, [rcx+0Ch]
0x180068ea9  ja      short loc_180068F14
0x180068eab  mov     rcx, [rcx+20h]
0x180068eaf  test    rcx, rcx
0x180068eb2  jz      short loc_180068EB9
0x180068eb4  call    SymCryptDlkeyFree
0x180068eb9  mov     rcx, [rbx+18h]
0x180068ebd  call    SymCryptDlkeyAllocate
0x180068ec2  mov     [rbx+20h], rax
0x180068ec6  test    rax, rax
0x180068ec9  jnz     short loc_180068EDD
0x180068ecb  mov     ebx, 0C0000017h
0x180068ed0  mov     r9d, 2E4h
0x180068ed6  mov     ecx, 0C0000017h
0x180068edb  jmp     short loc_180068F24
0x180068edd  mov     [rsp+48h+var_18], rax
0x180068ee2  mov     rdx, rdi
0x180068ee5  xor     r9d, r9d
0x180068ee8  mov     [rsp+48h+var_20], 2100h
0x180068ef0  xor     r8d, r8d
0x180068ef3  mov     rcx, rsi
0x180068ef6  xor     ebx, ebx
0x180068ef8  call    SymCryptDlkeySetValue
0x180068efd  test    eax, eax
0x180068eff  jz      short loc_180068F37
0x180068f01  mov     ecx, eax
0x180068f03  call    SymcryptErrorCodeToNtStatus
0x180068f08  mov     ebx, eax
0x180068f0a  mov     ecx, eax
0x180068f0c  mov     r9d, 2F3h
0x180068f12  jmp     short loc_180068F24
0x180068f14  mov     ebx, 0C000000Dh
0x180068f19  mov     r9d, 2D6h
0x180068f1f  mov     ecx, 0C000000Dh
0x180068f24  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068f2b  lea     rdx, aStatus; "Status"
0x180068f32  call    DebugTraceError
0x180068f37  mov     rsi, [rsp+48h+arg_8]
0x180068f3c  mov     eax, ebx
0x180068f3e  mov     rbx, [rsp+48h+arg_0]
0x180068f43  add     rsp, 40h
0x180068f47  pop     rdi
0x180068f48  retn
```
