# BCryptCloseAlgorithmProvider

- ea: `0x180005b00`
- end: `0x180005bba`
- name: `BCryptCloseAlgorithmProvider`
- size: `186`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, ULONG dwFlags)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000466c`
- `0x180004800`
- `0x180006bd0`
- `0x18000e2c4`
- `0x18001267c`
- `0x18001620c`
- `0x180016318`

## callees

- `0x1800050b0`
- `0x180005b00`
- `0x180006bd0`
- `0x180007a7c`
- `0x180015484`

## string_xrefs

- `0x180005b4b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptCloseAlgorithmProvider(BCRYPT_ALG_HANDLE hAlgorithm, ULONG dwFlags)
{
  __int64 v2; // r8
  __int64 v4; // rax
  int v5; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v2, (_DWORD)hAlgorithm);
  v4 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v4 && *(int *)(v4 + 8) >= 0 )
  {
    DecrementReferenceCount((volatile signed __int32 *)v4);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        v5,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        144);
    return -1073741816;
  }
}

```

## disassembly

```asm
0x180005b00  mov     [rsp+arg_0], rbx
0x180005b05  push    rdi
0x180005b06  sub     rsp, 40h
0x180005b0a  mov     eax, edx
0x180005b0c  mov     rbx, rcx
0x180005b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b16  lea     rdi, WPP_GLOBAL_Control
0x180005b1d  cmp     rcx, rdi
0x180005b20  jz      short loc_180005B28
0x180005b22  test    byte ptr [rcx+1Ch], 4
0x180005b26  jnz     short loc_180005BA0
0x180005b28  mov     rcx, rbx
0x180005b2b  call    ValidateBaseAlgHandle
0x180005b30  test    rax, rax
0x180005b33  jnz     short loc_180005B84
0x180005b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b3c  cmp     rcx, rdi
0x180005b3f  jz      short loc_180005B73
0x180005b41  test    byte ptr [rcx+1Ch], 1
0x180005b45  jz      short loc_180005B73
0x180005b47  mov     rcx, [rcx+10h]
0x180005b4b  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b52  mov     [rsp+48h+var_18], 990h
0x180005b5a  lea     r9, aStatus; "Status"
0x180005b61  mov     [rsp+48h+var_20], rdx
0x180005b66  mov     [rsp+48h+var_28], 0C0000008h
0x180005b6e  call    WPP_SF_sDsd
0x180005b73  mov     eax, 0C0000008h
0x180005b78  mov     rbx, [rsp+48h+arg_0]
0x180005b7d  add     rsp, 40h
0x180005b81  pop     rdi
0x180005b82  retn
0x180005b84  cmp     dword ptr [rax+8], 0
0x180005b88  jl      short loc_180005B35
0x180005b8a  mov     rcx, rax; P
0x180005b8d  call    DecrementReferenceCount
0x180005b92  mov     rbx, [rsp+48h+arg_0]
0x180005b97  xor     eax, eax
0x180005b99  add     rsp, 40h
0x180005b9d  pop     rdi
0x180005b9e  retn
0x180005ba0  mov     rcx, [rcx+10h]
0x180005ba4  mov     edx, 0Eh
0x180005ba9  mov     r9, rbx
0x180005bac  mov     [rsp+48h+var_28], eax
0x180005bb0  call    WPP_SF_qD
0x180005bb5  jmp     loc_180005B28
```
