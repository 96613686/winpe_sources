# EdpPluginAction

- ea: `0x140003c8c`
- end: `0x140003dd1`
- name: `EdpPluginAction`
- size: `325`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, char, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140003e2c`
- `0x14002b5e0`
- `0x14002cd1c`

## callees

- `0x140003c8c`
- `0x14000540c`
- `0x140005544`
- `0x140005568`
- `0x140005634`
- `0x1400056d0`
- `0x1400058c8`
- `0x14002dda8`

## import_xrefs

- `fwpkclnt!NikEdpNotifyProcessTokenChange0` at `0x140003dac`
- `fwpkclnt!NikEdpNotifyProcessTokenChange0` at `0x140003dac`

## pseudocode

```c
__int64 __fastcall EdpPluginAction(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5, char a6, int a7)
{
  int EnterpriseContext; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // r15
  int EnterpriseContextToken; // ebx
  __int64 v14; // rcx
  bool v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rcx
  int v18; // eax
  _QWORD v20[7]; // [rsp+30h] [rbp-38h] BYREF

  v20[0] = 0;
  EnterpriseContext = SrpCreateEnterpriseContext(a3, a5, a4, v20);
  v12 = v20[0];
  EnterpriseContextToken = EnterpriseContext;
  if ( EnterpriseContext >= 0 )
  {
    v14 = *(_QWORD *)(a1 + 48);
    v15 = 0;
    if ( !a7 )
      goto LABEL_10;
    v20[0] = 0;
    EnterpriseContextToken = SrpGetEnterpriseContextToken(v14, v20);
    if ( EnterpriseContextToken < 0 )
      goto LABEL_15;
    v16 = v20[0];
    if ( (*(_BYTE *)(v20[0] + 8LL) & 1) != 0 )
    {
      v17 = *(_QWORD *)(a1 + 48);
      a6 = 0;
      EnterpriseContextToken = SrpGetExemptEnterpriseIdsPresent(v17, &a6);
      if ( EnterpriseContextToken < 0 )
        goto LABEL_15;
      if ( a6 )
        *(_QWORD *)(v16 + 8) |= 0x20uLL;
    }
    v15 = (unsigned __int8)SrpEnterpriseContextsEqual(v12, v16) == 0;
    SrpDeleteEnterpriseContext(v16);
    v14 = *(_QWORD *)(a1 + 48);
    if ( a7 == 2 )
    {
      v18 = SrpDeleteEnterpriseContextToken(v14);
    }
    else
    {
LABEL_10:
      LOBYTE(v10) = EdppSingleInstanceAttributes;
      v18 = SrpSetEnterpriseContextToken(v14, v9, v10, v11, v12, 0);
    }
    EnterpriseContextToken = v18;
    if ( v18 >= 0 && (!a7 || v15) )
      EnterpriseContextToken = NikEdpNotifyProcessTokenChange0(*(_QWORD *)(a1 + 8), a7 != 0);
  }
LABEL_15:
  SrpDeleteEnterpriseContext(v12);
  return (unsigned int)EnterpriseContextToken;
}

```

## disassembly

```asm
0x140003c8c  push    rbx
0x140003c8e  push    rbp
0x140003c8f  push    rdi
0x140003c90  push    r14
0x140003c92  push    r15
0x140003c94  sub     rsp, 40h
0x140003c98  mov     edx, [rsp+68h+arg_20]
0x140003c9f  mov     rax, r9
0x140003ca2  mov     r10, r8
0x140003ca5  mov     [rsp+68h+var_38], 0
0x140003cae  mov     rbp, rcx
0x140003cb1  lea     r9, [rsp+68h+var_38]
0x140003cb6  mov     r8, rax
0x140003cb9  mov     rcx, r10
0x140003cbc  call    SrpCreateEnterpriseContext
0x140003cc1  mov     r15, [rsp+68h+var_38]
0x140003cc6  mov     ebx, eax
0x140003cc8  test    eax, eax
0x140003cca  js      loc_140003DBA
0x140003cd0  mov     rcx, [rbp+30h]
0x140003cd4  xor     r14b, r14b
0x140003cd7  cmp     [rsp+68h+arg_30], 0
0x140003cdf  jz      loc_140003D6D
0x140003ce5  lea     rdx, [rsp+68h+var_38]
0x140003cea  mov     [rsp+68h+var_38], 0
0x140003cf3  call    SrpGetEnterpriseContextToken
0x140003cf8  mov     ebx, eax
0x140003cfa  test    eax, eax
0x140003cfc  js      loc_140003DBA
0x140003d02  mov     rdi, [rsp+68h+var_38]
0x140003d07  test    byte ptr [rdi+8], 1
0x140003d0b  jz      short loc_140003D3F
0x140003d0d  mov     rcx, [rbp+30h]
0x140003d11  lea     rdx, [rsp+68h+arg_28]
0x140003d19  mov     [rsp+68h+arg_28], r14b
0x140003d21  call    SrpGetExemptEnterpriseIdsPresent
0x140003d26  mov     ebx, eax
0x140003d28  test    eax, eax
0x140003d2a  js      loc_140003DBA
0x140003d30  cmp     [rsp+68h+arg_28], r14b
0x140003d38  jz      short loc_140003D3F
0x140003d3a  or      qword ptr [rdi+8], 20h
0x140003d3f  mov     rdx, rdi
0x140003d42  mov     rcx, r15
0x140003d45  call    SrpEnterpriseContextsEqual
0x140003d4a  test    al, al
0x140003d4c  mov     rcx, rdi
0x140003d4f  setz    r14b
0x140003d53  call    SrpDeleteEnterpriseContext
0x140003d58  cmp     [rsp+68h+arg_30], 2
0x140003d60  mov     rcx, [rbp+30h]
0x140003d64  jnz     short loc_140003D6D
0x140003d66  call    SrpDeleteEnterpriseContextToken
0x140003d6b  jmp     short loc_140003D87
0x140003d6d  mov     r8b, cs:EdppSingleInstanceAttributes
0x140003d74  mov     [rsp+68h+var_40], 0
0x140003d7d  mov     [rsp+68h+var_48], r15
0x140003d82  call    SrpSetEnterpriseContextToken
0x140003d87  mov     ebx, eax
0x140003d89  test    eax, eax
0x140003d8b  js      short loc_140003DBA
0x140003d8d  cmp     [rsp+68h+arg_30], 0
0x140003d95  jz      short loc_140003D9C
0x140003d97  test    r14b, r14b
0x140003d9a  jz      short loc_140003DBA
0x140003d9c  mov     rcx, [rbp+8]
0x140003da0  xor     edx, edx
0x140003da2  cmp     [rsp+68h+arg_30], edx
0x140003da9  setnz   dl
0x140003dac  call    cs:__imp_NikEdpNotifyProcessTokenChange0
0x140003db3  nop     dword ptr [rax+rax+00h]
0x140003db8  mov     ebx, eax
0x140003dba  mov     rcx, r15
0x140003dbd  call    SrpDeleteEnterpriseContext
0x140003dc2  mov     eax, ebx
0x140003dc4  add     rsp, 40h
0x140003dc8  pop     r15
0x140003dca  pop     r14
0x140003dcc  pop     rdi
0x140003dcd  pop     rbp
0x140003dce  pop     rbx
0x140003dcf  retn
```
