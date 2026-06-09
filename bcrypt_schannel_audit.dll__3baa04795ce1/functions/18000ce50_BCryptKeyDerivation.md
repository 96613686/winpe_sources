# BCryptKeyDerivation

- ea: `0x18000ce50`
- end: `0x18000cff7`
- name: `BCryptKeyDerivation`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18000ce50`
- `0x180013a40`
- `0x18001c010`

## string_xrefs

- `0x18000cedd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000cf53`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000cf91`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000cfdd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptKeyDerivation(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, int a6)
{
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3, a4, a5, a6);
    v10 = WPP_GLOBAL_Control;
  }
  if ( a5 && a3 && a4 )
  {
    if ( a1 && *(_DWORD *)a1 >= 0x20u && *(_DWORD *)(a1 + 4) == 1431655762 )
    {
      v12 = *(_QWORD *)(a1 + 8);
      if ( *(_DWORD *)(v12 + 36) == 7 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int))(v12 + 104))(
                *(_QWORD *)(a1 + 16),
                a2,
                a3,
                a4,
                a5,
                a6);
        v11 = v13;
        if ( v13 < 0 )
          DebugTraceError((unsigned int)v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
        else
          return 0;
      }
      else
      {
        v11 = -1073741637;
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            v10[2],
            a2,
            a3,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            20);
      }
    }
    else
    {
      v11 = -1073741816;
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          v10[2],
          a2,
          a3,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          7);
    }
  }
  else
  {
    v11 = -1073741811;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v10[2],
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        255);
  }
  return v11;
}

```

## disassembly

```asm
0x18000ce50  push    rbx
0x18000ce52  push    rbp
0x18000ce53  push    rsi
0x18000ce54  push    rdi
0x18000ce55  push    r12
0x18000ce57  push    r14
0x18000ce59  push    r15
0x18000ce5b  sub     rsp, 50h
0x18000ce5f  mov     edi, r9d
0x18000ce62  mov     rsi, r8
0x18000ce65  mov     r14, rdx
0x18000ce68  mov     rbx, rcx
0x18000ce6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce72  lea     r12, WPP_GLOBAL_Control
0x18000ce79  mov     r15d, [rsp+88h+arg_28]
0x18000ce81  mov     rbp, [rsp+88h+arg_20]
0x18000ce89  cmp     rcx, r12
0x18000ce8c  jz      short loc_18000CE98
0x18000ce8e  test    byte ptr [rcx+1Ch], 4
0x18000ce92  jnz     loc_18000CFA7
0x18000ce98  test    rbp, rbp
0x18000ce9b  jz      loc_18000CF79
0x18000cea1  test    rsi, rsi
0x18000cea4  jz      loc_18000CF79
0x18000ceaa  test    edi, edi
0x18000ceac  jz      loc_18000CF79
0x18000ceb2  test    rbx, rbx
0x18000ceb5  jz      short loc_18000CEC5
0x18000ceb7  cmp     dword ptr [rbx], 20h ; ' '
0x18000ceba  jb      short loc_18000CEC5
0x18000cebc  cmp     dword ptr [rbx+4], 55555552h
0x18000cec3  jz      short loc_18000CEF3
0x18000cec5  mov     ebx, 0C0000008h
0x18000ceca  cmp     rcx, r12
0x18000cecd  jz      short loc_18000CF29
0x18000cecf  test    byte ptr [rcx+1Ch], 1
0x18000ced3  jz      short loc_18000CF29
0x18000ced5  mov     [rsp+88h+var_58], 1E07h
0x18000cedd  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cee4  mov     [rsp+88h+var_60], rax
0x18000cee9  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000cef1  jmp     short loc_18000CF67
0x18000cef3  mov     rax, [rbx+8]
0x18000cef7  cmp     dword ptr [rax+24h], 7
0x18000cefb  jnz     short loc_18000CF3B
0x18000cefd  mov     rcx, [rbx+10h]
0x18000cf01  mov     r9d, edi
0x18000cf04  mov     rax, [rax+68h]
0x18000cf08  mov     r8, rsi
0x18000cf0b  mov     dword ptr [rsp+88h+var_60], r15d
0x18000cf10  mov     rdx, r14
0x18000cf13  mov     [rsp+88h+var_68], rbp
0x18000cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1d  mov     ebx, eax
0x18000cf1f  test    eax, eax
0x18000cf21  js      loc_18000CFD7
0x18000cf27  xor     ebx, ebx
0x18000cf29  mov     eax, ebx
0x18000cf2b  add     rsp, 50h
0x18000cf2f  pop     r15
0x18000cf31  pop     r14
0x18000cf33  pop     r12
0x18000cf35  pop     rdi
0x18000cf36  pop     rsi
0x18000cf37  pop     rbp
0x18000cf38  pop     rbx
0x18000cf39  retn
0x18000cf3b  mov     ebx, 0C00000BBh
0x18000cf40  cmp     rcx, r12
0x18000cf43  jz      short loc_18000CF29
0x18000cf45  test    byte ptr [rcx+1Ch], 1
0x18000cf49  jz      short loc_18000CF29
0x18000cf4b  mov     [rsp+88h+var_58], 1E14h
0x18000cf53  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf5a  mov     [rsp+88h+var_60], rax
0x18000cf5f  mov     dword ptr [rsp+88h+var_68], 0C00000BBh
0x18000cf67  mov     rcx, [rcx+10h]
0x18000cf6b  lea     r9, aStatus; "Status"
0x18000cf72  call    WPP_SF_sDsd
0x18000cf77  jmp     short loc_18000CF29
0x18000cf79  mov     ebx, 0C000000Dh
0x18000cf7e  cmp     rcx, r12
0x18000cf81  jz      short loc_18000CF29
0x18000cf83  test    byte ptr [rcx+1Ch], 1
0x18000cf87  jz      short loc_18000CF29
0x18000cf89  mov     [rsp+88h+var_58], 1DFFh
0x18000cf91  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf98  mov     [rsp+88h+var_60], rax
0x18000cf9d  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x18000cfa5  jmp     short loc_18000CF67
0x18000cfa7  mov     rcx, [rcx+10h]
0x18000cfab  mov     r9, rbx
0x18000cfae  mov     [rsp+88h+var_48], r15d
0x18000cfb3  mov     [rsp+88h+var_50], rbp
0x18000cfb8  mov     [rsp+88h+var_58], edi
0x18000cfbc  mov     [rsp+88h+var_60], rsi
0x18000cfc1  mov     [rsp+88h+var_68], r14
0x18000cfc6  call    WPP_SF_qqqDqD
0x18000cfcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd2  jmp     loc_18000CE98
0x18000cfd7  mov     r9d, 1E20h
0x18000cfdd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cfe4  lea     rdx, aStatus; "Status"
0x18000cfeb  mov     ecx, eax
0x18000cfed  call    DebugTraceError
0x18000cff2  jmp     loc_18000CF29
```
