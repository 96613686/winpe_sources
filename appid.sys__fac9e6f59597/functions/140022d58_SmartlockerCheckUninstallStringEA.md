# SmartlockerCheckUninstallStringEA

- ea: `0x140022d58`
- end: `0x140022f73`
- name: `SmartlockerCheckUninstallStringEA`
- size: `539`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f560`

## callees

- `0x140020a70`
- `0x140020c28`
- `0x140022d58`
- `0x140022f7c`
- `0x140023110`
- `0x140024e30`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140022f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022f27`
- `ntoskrnl!PsQueryProcessCommandLine` at `0x140022dee`
- `ntoskrnl!PsQueryProcessCommandLine` at `0x140022e37`
- `ntoskrnl!PsQueryProcessCommandLine` at `0x140022dee`
- `ntoskrnl!PsQueryProcessCommandLine` at `0x140022e37`

## pseudocode

```c
__int64 __fastcall SmartlockerCheckUninstallStringEA(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        _QWORD *a6)
{
  unsigned __int16 *v6; // r14
  _OWORD *v7; // rdi
  unsigned int v8; // esi
  int UninstallStringEa; // ebx
  __int64 v12; // r15
  int IsStringNoQuotePrefixedByDelimitedUninstallString; // eax
  __int64 v14; // rdx
  int v15; // r8d
  char v16; // r12
  int v17; // eax
  _OWORD *v18; // r8
  __int64 v19; // rdx
  char v21[4]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-31h] BYREF
  int v24; // [rsp+4Ch] [rbp-2Dh] BYREF
  _OWORD *v25; // [rsp+50h] [rbp-29h] BYREF
  __int64 v26; // [rsp+58h] [rbp-21h] BYREF
  void *v27; // [rsp+60h] [rbp-19h] BYREF
  __int128 v28[5]; // [rsp+68h] [rbp-11h] BYREF

  v26 = 0;
  v24 = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v22 = 0;
  v8 = 0;
  v25 = 0;
  v23 = 0;
  v21[0] = 0;
  v28[0] = 0;
  UninstallStringEa = AiGetUninstallStringEa(a4, &v26, &v24, (__int64 *)&v27);
  if ( UninstallStringEa < 0 )
    goto LABEL_20;
  v12 = v26;
  if ( !v26 || !v24 )
  {
    UninstallStringEa = -1073741275;
    goto LABEL_20;
  }
  UninstallStringEa = PsQueryProcessCommandLine(a3, 0, 0, 0, &v22);
  if ( UninstallStringEa == -1073741820 )
  {
    v6 = (unsigned __int16 *)AiAlloc(v22);
    if ( !v6 )
    {
      UninstallStringEa = -1073741801;
LABEL_20:
      v7 = 0;
      v8 = 0;
      goto LABEL_21;
    }
    UninstallStringEa = PsQueryProcessCommandLine(a3, v6, v22, 0, &v22);
    if ( UninstallStringEa < 0 )
      goto LABEL_20;
    *((_QWORD *)&v28[0] + 1) = v12 + 40;
    WORD1(v28[0]) = *(_WORD *)(v12 + 36);
    LOWORD(v28[0]) = WORD1(v28[0]);
    IsStringNoQuotePrefixedByDelimitedUninstallString = AiIsStringNoQuotePrefixedByDelimitedUninstallString(
                                                          v6,
                                                          v28,
                                                          v21);
    v16 = v21[0];
    UninstallStringEa = IsStringNoQuotePrefixedByDelimitedUninstallString;
    if ( IsStringNoQuotePrefixedByDelimitedUninstallString >= 0 )
    {
      if ( v21[0] )
      {
        v17 = SmartlockerConstructOriginClaim(1, 4, v15, 0, (__int64)v6, (__int64)&v23, (__int64)&v25);
        v7 = v25;
        UninstallStringEa = v17;
        v8 = v23;
        if ( v17 >= 0 )
        {
          v18 = v25;
          v19 = v23;
          v25[1] = *(_OWORD *)(v12 + 4);
          v7[2] = *(_OWORD *)(v12 + 20);
          UninstallStringEa = SmartlockerTagProcessToken(a1, v19, v18);
          if ( UninstallStringEa >= 0 && a1 != a2 )
            UninstallStringEa = SmartlockerTagProcessToken(a2, v8, v7);
        }
      }
      else
      {
        UninstallStringEa = -1073741823;
      }
    }
    AiLogCheckCmdlineAgainstUninstallString(qword_1400196F8, v14, (unsigned __int16 *)v28, v6, v16, UninstallStringEa);
  }
  if ( UninstallStringEa < 0 )
  {
    if ( v7 )
      ExFreePoolWithTag(v7, 0x41746D73u);
    goto LABEL_20;
  }
LABEL_21:
  *a5 = v8;
  *a6 = v7;
  AiFree(v6);
  AiFree(v27);
  return (unsigned int)UninstallStringEa;
}

```

## disassembly

```asm
0x140022d58  mov     [rsp-8+arg_0], rcx
0x140022d5d  push    rbp
0x140022d5e  push    rbx
0x140022d5f  push    rsi
0x140022d60  push    rdi
0x140022d61  push    r12
0x140022d63  push    r13
0x140022d65  push    r14
0x140022d67  push    r15
0x140022d69  lea     rbp, [rsp-0Fh]
0x140022d6e  sub     rsp, 88h
0x140022d75  xor     ecx, ecx
0x140022d77  mov     rax, r9
0x140022d7a  mov     [rbp+47h+var_68], rcx
0x140022d7e  lea     r9, [rbp+47h+var_60]
0x140022d82  mov     [rbp+47h+var_74], ecx
0x140022d85  mov     r14d, ecx
0x140022d88  mov     [rbp+47h+var_60], rcx
0x140022d8c  mov     edi, ecx
0x140022d8e  mov     [rbp+47h+var_7C], ecx
0x140022d91  mov     esi, ecx
0x140022d93  mov     [rbp+47h+var_70], rcx
0x140022d97  mov     r12, r8
0x140022d9a  mov     [rbp+47h+var_78], ecx
0x140022d9d  lea     r8, [rbp+47h+var_74]
0x140022da1  mov     [rbp+47h+var_80], cl
0x140022da4  mov     r13, rdx
0x140022da7  xorps   xmm0, xmm0
0x140022daa  lea     rdx, [rbp+47h+var_68]
0x140022dae  mov     rcx, rax
0x140022db1  movups  [rbp+47h+var_58], xmm0
0x140022db5  call    AiGetUninstallStringEa
0x140022dba  mov     ebx, eax
0x140022dbc  test    eax, eax
0x140022dbe  js      loc_140022F3A
0x140022dc4  mov     r15, [rbp+47h+var_68]
0x140022dc8  test    r15, r15
0x140022dcb  jz      loc_140022F35
0x140022dd1  cmp     [rbp+47h+var_74], esi
0x140022dd4  jz      loc_140022F35
0x140022dda  lea     rax, [rbp+47h+var_7C]
0x140022dde  xor     r9d, r9d
0x140022de1  xor     r8d, r8d
0x140022de4  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140022de9  xor     edx, edx
0x140022deb  mov     rcx, r12
0x140022dee  call    cs:__imp_PsQueryProcessCommandLine
0x140022df5  nop     dword ptr [rax+rax+00h]
0x140022dfa  mov     ebx, eax
0x140022dfc  cmp     eax, 0C0000004h
0x140022e01  jnz     loc_140022F16
0x140022e07  mov     ecx, [rbp+47h+var_7C]
0x140022e0a  call    AiAlloc
0x140022e0f  mov     r14, rax
0x140022e12  test    rax, rax
0x140022e15  jnz     short loc_140022E21
0x140022e17  mov     ebx, 0C0000017h
0x140022e1c  jmp     loc_140022F3A
0x140022e21  mov     r8d, [rbp+47h+var_7C]
0x140022e25  lea     rax, [rbp+47h+var_7C]
0x140022e29  xor     r9d, r9d
0x140022e2c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140022e31  mov     rdx, r14
0x140022e34  mov     rcx, r12
0x140022e37  call    cs:__imp_PsQueryProcessCommandLine
0x140022e3e  nop     dword ptr [rax+rax+00h]
0x140022e43  mov     ebx, eax
0x140022e45  test    eax, eax
0x140022e47  js      loc_140022F3A
0x140022e4d  lea     rax, [r15+28h]
0x140022e51  mov     rcx, r14
0x140022e54  mov     qword ptr [rbp+47h+var_58+8], rax
0x140022e58  lea     r8, [rbp+47h+var_80]
0x140022e5c  movzx   eax, word ptr [r15+24h]
0x140022e61  lea     rdx, [rbp+47h+var_58]
0x140022e65  mov     word ptr [rbp+47h+var_58+2], ax
0x140022e69  mov     word ptr [rbp+47h+var_58], ax
0x140022e6d  call    AiIsStringNoQuotePrefixedByDelimitedUninstallString
0x140022e72  mov     r12b, [rbp+47h+var_80]
0x140022e76  mov     ebx, eax
0x140022e78  test    eax, eax
0x140022e7a  js      short loc_140022EFA
0x140022e7c  test    r12b, r12b
0x140022e7f  jnz     short loc_140022E88
0x140022e81  mov     ebx, 0C0000001h
0x140022e86  jmp     short loc_140022EFA
0x140022e88  xor     r9d, r9d
0x140022e8b  lea     rax, [rbp+47h+var_70]
0x140022e8f  mov     [rsp+0C0h+var_90], rax
0x140022e94  lea     rax, [rbp+47h+var_78]
0x140022e98  mov     qword ptr [rsp+0C0h+var_98], rax
0x140022e9d  mov     qword ptr [rsp+0C0h+var_A0], r14
0x140022ea2  lea     edx, [r9+4]
0x140022ea6  lea     ecx, [rdx-3]
0x140022ea9  call    SmartlockerConstructOriginClaim
0x140022eae  mov     rdi, [rbp+47h+var_70]
0x140022eb2  mov     ebx, eax
0x140022eb4  mov     esi, [rbp+47h+var_78]
0x140022eb7  test    eax, eax
0x140022eb9  js      short loc_140022EFA
0x140022ebb  movups  xmm0, xmmword ptr [r15+4]
0x140022ec0  mov     r8, rdi
0x140022ec3  mov     edx, esi
0x140022ec5  movdqu  xmmword ptr [rdi+10h], xmm0
0x140022eca  movups  xmm0, xmmword ptr [r15+14h]
0x140022ecf  mov     r15, [rbp+47h+arg_0]
0x140022ed3  mov     rcx, r15
0x140022ed6  movdqu  xmmword ptr [rdi+20h], xmm0
0x140022edb  call    SmartlockerTagProcessToken
0x140022ee0  mov     ebx, eax
0x140022ee2  test    eax, eax
0x140022ee4  js      short loc_140022EFA
0x140022ee6  cmp     r15, r13
0x140022ee9  jz      short loc_140022EFA
0x140022eeb  mov     r8, rdi
0x140022eee  mov     edx, esi
0x140022ef0  mov     rcx, r13
0x140022ef3  call    SmartlockerTagProcessToken
0x140022ef8  mov     ebx, eax
0x140022efa  mov     rcx, cs:qword_1400196F8; RegHandle
0x140022f01  lea     r8, [rbp+47h+var_58]
0x140022f05  mov     [rsp+0C0h+var_98], ebx; int
0x140022f09  mov     r9, r14
0x140022f0c  mov     [rsp+0C0h+var_A0], r12b; char
0x140022f11  call    AiLogCheckCmdlineAgainstUninstallString
0x140022f16  test    ebx, ebx
0x140022f18  jns     short loc_140022F3E
0x140022f1a  test    rdi, rdi
0x140022f1d  jz      short loc_140022F3A
0x140022f1f  mov     edx, 41746D73h; Tag
0x140022f24  mov     rcx, rdi; P
0x140022f27  call    cs:__imp_ExFreePoolWithTag
0x140022f2e  nop     dword ptr [rax+rax+00h]
0x140022f33  jmp     short loc_140022F3A
0x140022f35  mov     ebx, 0C0000225h
0x140022f3a  xor     edi, edi
0x140022f3c  xor     esi, esi
0x140022f3e  mov     rax, [rbp+47h+arg_20]
0x140022f42  mov     rcx, r14
0x140022f45  mov     [rax], esi
0x140022f47  mov     rax, [rbp+47h+arg_28]
0x140022f4b  mov     [rax], rdi
0x140022f4e  call    AiFree
0x140022f53  mov     rcx, [rbp+47h+var_60]
0x140022f57  call    AiFree
0x140022f5c  mov     eax, ebx
0x140022f5e  add     rsp, 88h
0x140022f65  pop     r15
0x140022f67  pop     r14
0x140022f69  pop     r13
0x140022f6b  pop     r12
0x140022f6d  pop     rdi
0x140022f6e  pop     rsi
0x140022f6f  pop     rbx
0x140022f70  pop     rbp
0x140022f71  retn
```
