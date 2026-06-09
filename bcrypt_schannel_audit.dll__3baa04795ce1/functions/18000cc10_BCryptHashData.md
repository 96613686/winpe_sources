# BCryptHashData

- ea: `0x18000cc10`
- end: `0x18000cce1`
- name: `BCryptHashData`
- size: `209`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005470`
- `0x18000c1e0`
- `0x18000cb70`
- `0x180012cc4`
- `0x180016564`
- `0x1800168c8`
- `0x180016efc`
- `0x1800171b4`

## callees

- `0x180007a7c`
- `0x18000cc10`
- `0x1800124c4`
- `0x18001c010`

## string_xrefs

- `0x18000cc88`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptHashData(BCRYPT_HASH_HANDLE hHash, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)
{
  _QWORD *v8; // rcx

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, cbInput, hHash, pbInput, cbInput, dwFlags);
    v8 = WPP_GLOBAL_Control;
  }
  if ( hHash && *(_DWORD *)hHash >= 0x28u && *((_DWORD *)hHash + 1) == 1431655763 )
    return (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(*((_QWORD *)hHash + 1) + 96LL))(
             *((_QWORD *)hHash + 2),
             pbInput,
             cbInput,
             dwFlags);
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      v8[2],
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      cbInput,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      211);
  return -1073741816;
}

```

## disassembly

```asm
0x18000cc10  push    rbx
0x18000cc12  push    rbp
0x18000cc13  push    rsi
0x18000cc14  push    rdi
0x18000cc15  push    r14
0x18000cc17  sub     rsp, 40h
0x18000cc1b  mov     edi, r9d
0x18000cc1e  mov     esi, r8d
0x18000cc21  mov     rbp, rdx
0x18000cc24  mov     rbx, rcx
0x18000cc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc2e  lea     r14, WPP_GLOBAL_Control
0x18000cc35  cmp     rcx, r14
0x18000cc38  jz      short loc_18000CC40
0x18000cc3a  test    byte ptr [rcx+1Ch], 4
0x18000cc3e  jnz     short loc_18000CCB7
0x18000cc40  test    rbx, rbx
0x18000cc43  jz      short loc_18000CC79
0x18000cc45  cmp     dword ptr [rbx], 28h ; '('
0x18000cc48  jb      short loc_18000CC79
0x18000cc4a  cmp     dword ptr [rbx+4], 55555553h
0x18000cc51  jnz     short loc_18000CC79
0x18000cc53  mov     rax, [rbx+8]
0x18000cc57  mov     r9d, edi
0x18000cc5a  mov     rcx, [rbx+10h]
0x18000cc5e  mov     r8d, esi
0x18000cc61  mov     rdx, rbp
0x18000cc64  mov     rax, [rax+60h]
0x18000cc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc6d  add     rsp, 40h
0x18000cc71  pop     r14
0x18000cc73  pop     rdi
0x18000cc74  pop     rsi
0x18000cc75  pop     rbp
0x18000cc76  pop     rbx
0x18000cc77  retn
0x18000cc79  cmp     rcx, r14
0x18000cc7c  jz      short loc_18000CCB0
0x18000cc7e  test    byte ptr [rcx+1Ch], 1
0x18000cc82  jz      short loc_18000CCB0
0x18000cc84  mov     rcx, [rcx+10h]
0x18000cc88  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cc8f  mov     [rsp+68h+var_38], 17D3h
0x18000cc97  lea     r9, aStatus; "Status"
0x18000cc9e  mov     [rsp+68h+var_40], rdx
0x18000cca3  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000ccab  call    WPP_SF_sDsd
0x18000ccb0  mov     eax, 0C0000008h
0x18000ccb5  jmp     short loc_18000CC6D
0x18000ccb7  mov     rcx, [rcx+10h]
0x18000ccbb  mov     edx, 22h ; '"'
0x18000ccc0  mov     [rsp+68h+var_38], edi
0x18000ccc4  mov     r9, rbx
0x18000ccc7  mov     dword ptr [rsp+68h+var_40], esi
0x18000cccb  mov     [rsp+68h+var_48], rbp
0x18000ccd0  call    WPP_SF_qqdD
0x18000ccd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccdc  jmp     loc_18000CC40
```
