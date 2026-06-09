# MSCryptAuditPrimitiveFailure

- ea: `0x1800215e4`
- end: `0x1800216d1`
- name: `MSCryptAuditPrimitiveFailure`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b36c`
- `0x18001fad0`
- `0x1800213d0`
- `0x180021490`
- `0x1800225d0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800215e4`
- `0x18005747c`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x180021642`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`
- `0x1800216a0`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 __fastcall MSCryptAuditPrimitiveFailure(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  int v6; // edx
  int v7; // ebx
  __int64 (__fastcall *v8)(const wchar_t *, __int64, _OWORD *, _QWORD); // rax
  int v9; // eax
  _OWORD v11[2]; // [rsp+40h] [rbp-48h] BYREF

  memset(v11, 0, sizeof(v11));
  v7 = CryptAuditTranslateString(a3, v11);
  if ( v7 >= 0 )
  {
    if ( g_pAuditingFuncs
      && (v8 = *(__int64 (__fastcall **)(const wchar_t *, __int64, _OWORD *, _QWORD))(g_pAuditingFuncs + 48)) != 0
      && (v9 = v8(L"Microsoft Primitive Provider", a2, v11, a4), v7 = v9, v9 < 0) )
    {
      DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 530);
    }
    else
    {
      return 0;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
      (unsigned int)"Status",
      v7,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
      5);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800215e4  push    rbx
0x1800215e6  push    rsi
0x1800215e7  push    rdi
0x1800215e8  sub     rsp, 70h
0x1800215ec  mov     rax, cs:__security_cookie
0x1800215f3  xor     rax, rsp
0x1800215f6  mov     [rsp+88h+var_28], rax
0x1800215fb  xorps   xmm0, xmm0
0x1800215fe  mov     rdi, rdx
0x180021601  lea     rdx, [rsp+88h+var_48]
0x180021606  mov     ecx, r8d
0x180021609  movups  [rsp+88h+var_48], xmm0
0x18002160e  mov     esi, r9d
0x180021611  movups  [rsp+88h+var_38], xmm0
0x180021616  call    CryptAuditTranslateString
0x18002161b  mov     ebx, eax
0x18002161d  test    eax, eax
0x18002161f  jns     short loc_180021668
0x180021621  mov     rcx, cs:WPP_GLOBAL_Control
0x180021628  lea     rax, WPP_GLOBAL_Control
0x18002162f  cmp     rcx, rax
0x180021632  jz      loc_1800216B9
0x180021638  test    byte ptr [rcx+1Ch], 1
0x18002163c  jz      short loc_1800216B9
0x18002163e  mov     rcx, [rcx+10h]
0x180021642  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021649  mov     [rsp+88h+var_58], 205h
0x180021651  lea     r9, aStatus; "Status"
0x180021658  mov     [rsp+88h+var_60], r8
0x18002165d  mov     [rsp+88h+var_68], ebx
0x180021661  call    WPP_SF_sDsd
0x180021666  jmp     short loc_1800216B9
0x180021668  mov     rax, cs:g_pAuditingFuncs
0x18002166f  test    rax, rax
0x180021672  jz      short loc_1800216B7
0x180021674  mov     rax, [rax+30h]
0x180021678  test    rax, rax
0x18002167b  jz      short loc_1800216B7
0x18002167d  mov     r9d, esi
0x180021680  lea     r8, [rsp+88h+var_48]
0x180021685  mov     rdx, rdi
0x180021688  lea     rcx, aMicrosoftPrimi; "Microsoft Primitive Provider"
0x18002168f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021694  mov     ebx, eax
0x180021696  test    eax, eax
0x180021698  jns     short loc_1800216B7
0x18002169a  mov     r9d, 212h
0x1800216a0  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800216a7  lea     rdx, aStatus; "Status"
0x1800216ae  mov     ecx, eax
0x1800216b0  call    DebugTraceError
0x1800216b5  jmp     short loc_1800216B9
0x1800216b7  xor     ebx, ebx
0x1800216b9  mov     eax, ebx
0x1800216bb  mov     rcx, [rsp+88h+var_28]
0x1800216c0  xor     rcx, rsp; StackCookie
0x1800216c3  call    __security_check_cookie
0x1800216c8  add     rsp, 70h
0x1800216cc  pop     rdi
0x1800216cd  pop     rsi
0x1800216ce  pop     rbx
0x1800216cf  retn
```
