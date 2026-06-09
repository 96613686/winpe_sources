# BCryptDestroySecret

- ea: `0x180004230`
- end: `0x18000437f`
- name: `BCryptDestroySecret`
- size: `335`
- prototype: `NTSTATUS __stdcall(BCRYPT_SECRET_HANDLE hSecret)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800041d0`
- `0x180004230`
- `0x180004648`
- `0x180005060`
- `0x1800050b0`
- `0x180007a7c`
- `0x18000d948`
- `0x18001b7a9`
- `0x18001c010`

## string_xrefs

- `0x1800042d6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004315`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004365`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDestroySecret(BCRYPT_SECRET_HANDLE hSecret)
{
  __int64 v2; // rax
  int v3; // edx
  __int64 v4; // r8
  unsigned int *v5; // rdi
  __int64 v6; // rsi
  int v7; // eax
  NTSTATUS v8; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_GLOBAL_Control);
  v2 = ValidateBaseSecretHandle(hSecret);
  v5 = (unsigned int *)v2;
  if ( v2 )
  {
    v6 = *(_QWORD *)(v2 + 8);
    if ( *(_DWORD *)(v6 + 36) == 4 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD))(v6 + 104))(*(_QWORD *)(v2 + 16));
      v8 = v7;
      if ( v7 < 0 )
      {
        DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      }
      else
      {
        memset_0(v5, 0, *v5);
        BCryptFree(v5);
      }
    }
    else
    {
      v8 = -1073741816;
      if ( (_UNKNOWN **)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v4 + 16),
          v3,
          v4,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          73);
    }
    if ( v6 && !v8 )
      DecrementReferenceCount((PVOID)v6);
  }
  else
  {
    v8 = -1073741816;
    if ( (_UNKNOWN **)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v4 + 16),
        v3,
        v4,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        55);
  }
  return v8;
}

```

## disassembly

```asm
0x180004230  push    rbx
0x180004232  push    rbp
0x180004233  push    rsi
0x180004234  push    rdi
0x180004235  sub     rsp, 48h
0x180004239  mov     rbx, rcx
0x18000423c  mov     r8, cs:WPP_GLOBAL_Control
0x180004243  lea     rbp, WPP_GLOBAL_Control
0x18000424a  cmp     r8, rbp
0x18000424d  jz      short loc_18000425A
0x18000424f  test    byte ptr [r8+1Ch], 4
0x180004254  jnz     loc_180004342
0x18000425a  mov     rcx, rbx
0x18000425d  call    ValidateBaseSecretHandle
0x180004262  mov     rdi, rax
0x180004265  test    rax, rax
0x180004268  jz      loc_180004300
0x18000426e  mov     rsi, [rax+8]
0x180004272  cmp     dword ptr [rsi+24h], 4
0x180004276  jnz     short loc_1800042C1
0x180004278  mov     rcx, [rax+10h]
0x18000427c  mov     rax, [rsi+68h]
0x180004280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004285  mov     ebx, eax
0x180004287  test    eax, eax
0x180004289  js      loc_18000435F
0x18000428f  mov     r8d, [rdi]; Size
0x180004292  xor     edx, edx; Val
0x180004294  mov     rcx, rdi; void *
0x180004297  call    memset_0
0x18000429c  mov     rcx, rdi
0x18000429f  call    BCryptFree
0x1800042a4  test    rsi, rsi
0x1800042a7  jz      short loc_1800042B5
0x1800042a9  test    ebx, ebx
0x1800042ab  jnz     short loc_1800042B5
0x1800042ad  mov     rcx, rsi; P
0x1800042b0  call    DecrementReferenceCount
0x1800042b5  mov     eax, ebx
0x1800042b7  add     rsp, 48h
0x1800042bb  pop     rdi
0x1800042bc  pop     rsi
0x1800042bd  pop     rbp
0x1800042be  pop     rbx
0x1800042bf  retn
0x1800042c1  mov     ebx, 0C0000008h
0x1800042c6  cmp     r8, rbp
0x1800042c9  jz      short loc_1800042A4
0x1800042cb  test    byte ptr [r8+1Ch], 1
0x1800042d0  jz      short loc_1800042A4
0x1800042d2  mov     rcx, [r8+10h]
0x1800042d6  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800042dd  mov     [rsp+68h+var_38], 1649h
0x1800042e5  lea     r9, aStatus; "Status"
0x1800042ec  mov     [rsp+68h+var_40], rax
0x1800042f1  mov     [rsp+68h+var_48], 0C0000008h
0x1800042f9  call    WPP_SF_sDsd
0x1800042fe  jmp     short loc_1800042A4
0x180004300  mov     ebx, 0C0000008h
0x180004305  cmp     r8, rbp
0x180004308  jz      short loc_1800042B5
0x18000430a  test    byte ptr [r8+1Ch], 1
0x18000430f  jz      short loc_1800042B5
0x180004311  mov     rcx, [r8+10h]
0x180004315  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000431c  mov     [rsp+68h+var_38], 1637h
0x180004324  lea     r9, aStatus; "Status"
0x18000432b  mov     [rsp+68h+var_40], rax
0x180004330  mov     [rsp+68h+var_48], 0C0000008h
0x180004338  call    WPP_SF_sDsd
0x18000433d  jmp     loc_1800042B5
0x180004342  mov     rcx, [r8+10h]
0x180004346  mov     edx, 20h ; ' '
0x18000434b  mov     r9, rbx
0x18000434e  call    WPP_SF_q
0x180004353  mov     r8, cs:WPP_GLOBAL_Control
0x18000435a  jmp     loc_18000425A
0x18000435f  mov     r9d, 1652h
0x180004365  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000436c  lea     rdx, aStatus; "Status"
0x180004373  mov     ecx, eax
0x180004375  call    DebugTraceError
0x18000437a  jmp     loc_1800042A4
```
