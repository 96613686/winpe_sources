# BCryptFinishHash

- ea: `0x1800078e0`
- end: `0x180007a75`
- name: `BCryptFinishHash`
- size: `405`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbOutput, ULONG cbOutput, ULONG dwFlags)`
- caller_count: `8`
- callee_count: `5`
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

- `0x180005060`
- `0x1800078e0`
- `0x180007a7c`
- `0x1800124c4`
- `0x18001c010`

## string_xrefs

- `0x18000798f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800079bf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007a39`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptFinishHash(BCRYPT_HASH_HANDLE hHash, PUCHAR pbOutput, ULONG cbOutput, ULONG dwFlags)
{
  _QWORD *v8; // rcx
  __int64 v9; // rsi
  int v10; // edx
  int v11; // edi
  int v12; // r8d
  int v14; // eax
  __int64 v15; // r9

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, cbOutput, hHash, pbOutput, cbOutput, dwFlags);
    v8 = WPP_GLOBAL_Control;
  }
  if ( hHash && *(_DWORD *)hHash >= 0x28u && *((_DWORD *)hHash + 1) == 1431655763 )
  {
    v9 = *((_QWORD *)hHash + 1);
    v11 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v9 + 104))(
            *((_QWORD *)hHash + 2),
            pbOutput,
            cbOutput,
            dwFlags);
    if ( v11 >= 0 )
    {
      if ( (*(_BYTE *)(v9 + 8) & 8) == 0 )
        return 0;
      v14 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v9 + 96))(
              *((_QWORD *)hHash + 3),
              pbOutput,
              cbOutput,
              dwFlags);
      v11 = v14;
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v9 + 104))(
                *((_QWORD *)hHash + 3),
                pbOutput,
                cbOutput,
                dwFlags);
        v11 = v14;
        if ( v14 >= 0 )
          return 0;
        v15 = 6164;
      }
      else
      {
        v15 = 6155;
      }
      DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v15);
      return v11;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v12,
        (unsigned int)"Status",
        v11,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        255);
  }
  else
  {
    v11 = -1073741816;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v8[2],
        (_DWORD)pbOutput,
        cbOutput,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        245);
  }
  return v11;
}

```

## disassembly

```asm
0x1800078e0  push    rbx
0x1800078e2  push    rbp
0x1800078e3  push    rdi
0x1800078e4  push    r12
0x1800078e6  push    r14
0x1800078e8  push    r15
0x1800078ea  sub     rsp, 48h
0x1800078ee  mov     ebp, r9d
0x1800078f1  mov     r14d, r8d
0x1800078f4  mov     r15, rdx
0x1800078f7  mov     rbx, rcx
0x1800078fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007901  lea     r12, WPP_GLOBAL_Control
0x180007908  cmp     rcx, r12
0x18000790b  jz      short loc_180007917
0x18000790d  test    byte ptr [rcx+1Ch], 4
0x180007911  jnz     loc_1800079E4
0x180007917  mov     [rsp+78h+arg_0], rsi
0x18000791f  test    rbx, rbx
0x180007922  jz      short loc_180007977
0x180007924  cmp     dword ptr [rbx], 28h ; '('
0x180007927  jb      short loc_180007977
0x180007929  cmp     dword ptr [rbx+4], 55555553h
0x180007930  jnz     short loc_180007977
0x180007932  mov     rsi, [rbx+8]
0x180007936  mov     r9d, ebp
0x180007939  mov     rcx, [rbx+10h]
0x18000793d  mov     r8d, r14d
0x180007940  mov     rdx, r15
0x180007943  mov     rax, [rsi+68h]
0x180007947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000794c  mov     edi, eax
0x18000794e  test    eax, eax
0x180007950  js      short loc_1800079A5
0x180007952  test    byte ptr [rsi+8], 8
0x180007956  jnz     loc_180007A0F
0x18000795c  xor     edi, edi
0x18000795e  mov     rsi, [rsp+78h+arg_0]
0x180007966  mov     eax, edi
0x180007968  add     rsp, 48h
0x18000796c  pop     r15
0x18000796e  pop     r14
0x180007970  pop     r12
0x180007972  pop     rdi
0x180007973  pop     rbp
0x180007974  pop     rbx
0x180007975  retn
0x180007977  mov     edi, 0C0000008h
0x18000797c  cmp     rcx, r12
0x18000797f  jz      short loc_18000795E
0x180007981  test    byte ptr [rcx+1Ch], 1
0x180007985  jz      short loc_18000795E
0x180007987  mov     [rsp+78h+var_48], 17F5h
0x18000798f  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007996  mov     [rsp+78h+var_50], rax
0x18000799b  mov     dword ptr [rsp+78h+var_58], 0C0000008h
0x1800079a3  jmp     short loc_1800079CF
0x1800079a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ac  cmp     rcx, r12
0x1800079af  jz      short loc_18000795E
0x1800079b1  test    byte ptr [rcx+1Ch], 1
0x1800079b5  jz      short loc_18000795E
0x1800079b7  mov     [rsp+78h+var_48], 17FFh
0x1800079bf  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800079c6  mov     [rsp+78h+var_50], rax
0x1800079cb  mov     dword ptr [rsp+78h+var_58], edi
0x1800079cf  mov     rcx, [rcx+10h]
0x1800079d3  lea     r9, aStatus; "Status"
0x1800079da  call    WPP_SF_sDsd
0x1800079df  jmp     loc_18000795E
0x1800079e4  mov     rcx, [rcx+10h]
0x1800079e8  mov     edx, 23h ; '#'
0x1800079ed  mov     [rsp+78h+var_48], ebp
0x1800079f1  mov     r9, rbx
0x1800079f4  mov     dword ptr [rsp+78h+var_50], r14d
0x1800079f9  mov     [rsp+78h+var_58], r15
0x1800079fe  call    WPP_SF_qqdD
0x180007a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a0a  jmp     loc_180007917
0x180007a0f  mov     rcx, [rbx+18h]
0x180007a13  mov     r9d, ebp
0x180007a16  mov     rax, [rsi+60h]
0x180007a1a  mov     r8d, r14d
0x180007a1d  mov     rdx, r15
0x180007a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a25  mov     edi, eax
0x180007a27  test    eax, eax
0x180007a29  jns     short loc_180007A53
0x180007a2b  mov     r9d, 180Bh
0x180007a31  jmp     short loc_180007A39
0x180007a33  mov     r9d, 1814h
0x180007a39  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007a40  mov     ecx, eax
0x180007a42  lea     rdx, aStatus; "Status"
0x180007a49  call    DebugTraceError
0x180007a4e  jmp     loc_18000795E
0x180007a53  mov     rcx, [rbx+18h]
0x180007a57  mov     r9d, ebp
0x180007a5a  mov     rax, [rsi+68h]
0x180007a5e  mov     r8d, r14d
0x180007a61  mov     rdx, r15
0x180007a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a69  mov     edi, eax
0x180007a6b  test    eax, eax
0x180007a6d  jns     loc_18000795C
0x180007a73  jmp     short loc_180007A33
```
