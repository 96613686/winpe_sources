# ZtRegReadSingleRule

- ea: `0x180007f4c`
- end: `0x180008187`
- name: `ZtRegReadSingleRule`
- size: `571`
- prototype: `__int64 __fastcall(HKEY hKey, _WORD *Src, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007b64`

## callees

- `0x180007988`
- `0x180007f4c`
- `0x180008bec`
- `0x18000c704`
- `0x18000e3c8`
- `0x18000f9c8`
- `0x1800125d4`
- `0x180015008`
- `0x180015694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800080b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800080b0`

## pseudocode

```c
__int64 __fastcall ZtRegReadSingleRule(HKEY hKey, _WORD *Src, __int64 a3)
{
  BYTE *v3; // r14
  __int64 v7; // rcx
  _BYTE *v8; // rax
  unsigned int v9; // edi
  signed int v10; // ebx
  __int64 StringCopy_W; // rax
  __int64 v12; // r8
  int v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // r8
  signed int RuleSubnets; // eax
  int v17; // eax
  BYTE *v19; // [rsp+30h] [rbp-10h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  v19 = 0;
  v23 = 0;
  *(_QWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qSq(1026, 0x1Eu, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, hKey, Src, a3);
  if ( a3 )
  {
    v7 = 48;
    v8 = (_BYTE *)a3;
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
  }
  if ( !hKey )
  {
    v9 = -2147024809;
    HIDWORD(v23) = 313;
    v10 = -2147024809;
    goto LABEL_35;
  }
  if ( !Src )
  {
    v9 = -2147024809;
    HIDWORD(v23) = 314;
    v10 = -2147024809;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    HIDWORD(v23) = 315;
    v10 = -2147024809;
    goto LABEL_35;
  }
  *(_DWORD *)a3 = 1;
  StringCopy_W = Dns_CreateStringCopy_W(Src);
  if ( !StringCopy_W )
  {
    v9 = -2147024809;
    HIDWORD(v23) = 326;
    v10 = -2147024809;
LABEL_33:
    DnsFreeZtRuleMembers(a3);
    goto LABEL_35;
  }
  *(_QWORD *)(a3 + 16) = StringCopy_W;
  v13 = privateRegReadStringValueW(hKey, L"Description", v12, &v19, (DWORD *)&v23);
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( v10 < 0 )
  {
    v3 = v19;
    HIDWORD(v23) = 338;
LABEL_32:
    v9 = v10;
    goto LABEL_33;
  }
  *(_QWORD *)(a3 + 24) = v19;
  cbData = 8;
  v14 = RegQueryValueExW(hKey, L"Flags", 0, &Type, Data, &cbData);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( v10 < 0 )
  {
    HIDWORD(v23) = 353;
    goto LABEL_32;
  }
  if ( Type != 11 )
  {
    v9 = -2147024809;
    HIDWORD(v23) = 355;
    v10 = -2147024809;
    goto LABEL_33;
  }
  *(_QWORD *)(a3 + 8) = *(_QWORD *)Data;
  RuleSubnets = ZtReadRuleSubnets(hKey, a3, v15);
  v10 = RuleSubnets;
  if ( RuleSubnets > 0 )
    v10 = (unsigned __int16)RuleSubnets | 0x80070000;
  if ( v10 < 0 )
  {
    HIDWORD(v23) = 359;
    goto LABEL_32;
  }
  v17 = ZtValidateRules(1, a3);
  v10 = v17;
  if ( v17 > 0 )
    v10 = (unsigned __int16)v17 | 0x80070000;
  if ( v10 < 0 )
  {
    HIDWORD(v23) = 361;
    goto LABEL_32;
  }
  v9 = v10;
LABEL_35:
  Dns_Free(0);
  Dns_Free(v3);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x1Fu, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v10);
  return v9;
}

```

## disassembly

```asm
0x180007f4c  mov     [rsp-28h+arg_8], rbx
0x180007f51  push    rbp
0x180007f52  push    rsi
0x180007f53  push    rdi
0x180007f54  push    r12
0x180007f56  push    r14
0x180007f58  mov     rbp, rsp
0x180007f5b  sub     rsp, 40h
0x180007f5f  xor     r14d, r14d
0x180007f62  mov     dword ptr [rbp+arg_18+4], 0
0x180007f69  mov     [rbp+var_10], r14
0x180007f6d  mov     rsi, r8
0x180007f70  mov     dword ptr [rbp+arg_18], r14d
0x180007f74  mov     rbx, rdx
0x180007f77  mov     qword ptr [rbp+Data], r14
0x180007f7b  mov     rdi, rcx
0x180007f7e  mov     [rbp+cbData], r14d
0x180007f82  mov     [rbp+Type], r14d
0x180007f86  test    byte ptr cs:xmmword_18001F260, 4
0x180007f8d  jz      short loc_180007FB1
0x180007f8f  mov     [rsp+40h+lpcbData], r8
0x180007f94  lea     edx, [r14+1Eh]
0x180007f98  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007f9f  mov     [rsp+40h+lpData], rbx
0x180007fa4  mov     ecx, 402h
0x180007fa9  mov     r9, rdi
0x180007fac  call    WPP_SF_qSq
0x180007fb1  test    rsi, rsi
0x180007fb4  jz      short loc_180007FCA
0x180007fb6  mov     ecx, 30h ; '0'
0x180007fbb  mov     rax, rsi
0x180007fbe  mov     [rax], r14b
0x180007fc1  inc     rax
0x180007fc4  sub     rcx, 1
0x180007fc8  jnz     short loc_180007FBE
0x180007fca  test    rdi, rdi
0x180007fcd  jnz     short loc_180007FE2
0x180007fcf  mov     edi, 80070057h
0x180007fd4  mov     dword ptr [rbp+arg_18+4], 139h
0x180007fdb  mov     ebx, edi
0x180007fdd  jmp     loc_180008143
0x180007fe2  test    rbx, rbx
0x180007fe5  jnz     short loc_180007FFA
0x180007fe7  mov     edi, 80070057h
0x180007fec  mov     dword ptr [rbp+arg_18+4], 13Ah
0x180007ff3  mov     ebx, edi
0x180007ff5  jmp     loc_180008143
0x180007ffa  test    rsi, rsi
0x180007ffd  jnz     short loc_180008012
0x180007fff  mov     edi, 80070057h
0x180008004  mov     dword ptr [rbp+arg_18+4], 13Bh
0x18000800b  mov     ebx, edi
0x18000800d  jmp     loc_180008143
0x180008012  mov     rcx, rbx; Src
0x180008015  mov     dword ptr [rsi], 1
0x18000801b  call    Dns_CreateStringCopy_W
0x180008020  test    rax, rax
0x180008023  jnz     short loc_180008038
0x180008025  mov     edi, 80070057h
0x18000802a  mov     dword ptr [rbp+arg_18+4], 146h
0x180008031  mov     ebx, edi
0x180008033  jmp     loc_180008137
0x180008038  mov     [rsi+10h], rax
0x18000803c  lea     r9, [rbp+var_10]
0x180008040  lea     rax, [rbp+arg_18]
0x180008044  mov     rcx, rdi; hKey
0x180008047  lea     rdx, aDescription; "Description"
0x18000804e  mov     [rsp+40h+lpData], rax; __int64
0x180008053  call    privateRegReadStringValueW
0x180008058  mov     ebx, eax
0x18000805a  mov     r12d, 80070000h
0x180008060  test    eax, eax
0x180008062  jle     short loc_18000806A
0x180008064  movzx   ebx, ax
0x180008067  or      ebx, r12d
0x18000806a  test    ebx, ebx
0x18000806c  jns     short loc_18000807E
0x18000806e  mov     r14, [rbp+var_10]
0x180008072  mov     dword ptr [rbp+arg_18+4], 152h
0x180008079  jmp     loc_180008135
0x18000807e  mov     rax, [rbp+var_10]
0x180008082  lea     r9, [rbp+Type]; lpType
0x180008086  mov     [rsi+18h], rax
0x18000808a  lea     rdx, aFlags; "Flags"
0x180008091  lea     rax, [rbp+cbData]
0x180008095  mov     [rbp+cbData], 8
0x18000809c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800080a1  xor     r8d, r8d; lpReserved
0x1800080a4  lea     rax, [rbp+Data]
0x1800080a8  mov     rcx, rdi; hKey
0x1800080ab  mov     [rsp+40h+lpData], rax; lpData
0x1800080b0  call    cs:__imp_RegQueryValueExW
0x1800080b6  mov     ebx, eax
0x1800080b8  test    eax, eax
0x1800080ba  jle     short loc_1800080C2
0x1800080bc  movzx   ebx, ax
0x1800080bf  or      ebx, r12d
0x1800080c2  test    ebx, ebx
0x1800080c4  jns     short loc_1800080CF
0x1800080c6  mov     dword ptr [rbp+arg_18+4], 161h
0x1800080cd  jmp     short loc_180008135
0x1800080cf  cmp     [rbp+Type], 0Bh
0x1800080d3  jz      short loc_1800080E5
0x1800080d5  mov     edi, 80070057h
0x1800080da  mov     dword ptr [rbp+arg_18+4], 163h
0x1800080e1  mov     ebx, edi
0x1800080e3  jmp     short loc_180008137
0x1800080e5  mov     rax, qword ptr [rbp+Data]
0x1800080e9  mov     rdx, rsi
0x1800080ec  mov     rcx, rdi; hKey
0x1800080ef  mov     [rsi+8], rax
0x1800080f3  call    ZtReadRuleSubnets
0x1800080f8  mov     ebx, eax
0x1800080fa  test    eax, eax
0x1800080fc  jle     short loc_180008104
0x1800080fe  movzx   ebx, ax
0x180008101  or      ebx, r12d
0x180008104  test    ebx, ebx
0x180008106  jns     short loc_180008111
0x180008108  mov     dword ptr [rbp+arg_18+4], 167h
0x18000810f  jmp     short loc_180008135
0x180008111  mov     rdx, rsi
0x180008114  mov     ecx, 1
0x180008119  call    ZtValidateRules
0x18000811e  mov     ebx, eax
0x180008120  test    eax, eax
0x180008122  jle     short loc_18000812A
0x180008124  movzx   ebx, ax
0x180008127  or      ebx, r12d
0x18000812a  test    ebx, ebx
0x18000812c  jns     short loc_180008141
0x18000812e  mov     dword ptr [rbp+arg_18+4], 169h
0x180008135  mov     edi, ebx
0x180008137  mov     rcx, rsi
0x18000813a  call    DnsFreeZtRuleMembers
0x18000813f  jmp     short loc_180008143
0x180008141  mov     edi, ebx
0x180008143  xor     ecx, ecx; lpMem
0x180008145  call    Dns_Free
0x18000814a  mov     rcx, r14; lpMem
0x18000814d  call    Dns_Free
0x180008152  test    byte ptr cs:xmmword_18001F260, 4
0x180008159  jz      short loc_180008174
0x18000815b  mov     edx, 1Fh
0x180008160  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008167  mov     ecx, 402h
0x18000816c  mov     r9d, ebx
0x18000816f  call    WPP_SF_d
0x180008174  mov     rbx, [rsp+40h+arg_8]
0x180008179  mov     eax, edi
0x18000817b  add     rsp, 40h
0x18000817f  pop     r14
0x180008181  pop     r12
0x180008183  pop     rdi
0x180008184  pop     rsi
0x180008185  pop     rbp
0x180008186  retn
```
