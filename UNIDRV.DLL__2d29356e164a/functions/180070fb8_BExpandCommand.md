# BExpandCommand

- ea: `0x180070fb8`
- end: `0x1800711b7`
- name: `BExpandCommand`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800352c8`

## callees

- `0x180007220`
- `0x18000aa88`
- `0x1800335c8`
- `0x18004485c`
- `0x180070fb8`
- `0x18007154c`

## string_xrefs

- `0x180071177`: `Syntax error in *Command shortcut: %0.*s.`
- `0x180071182`: `BExpandCommand`

## pseudocode

```c
__int64 __fastcall BExpandCommand(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rdi
  __int64 v8; // rdi
  __int64 v9; // rsi
  _DWORD *v10; // rsi
  __int128 v11; // xmm0
  __int64 v12; // rsi
  _DWORD *v13; // rsi
  unsigned int v15; // [rsp+20h] [rbp-38h] BYREF
  int v16; // [rsp+24h] [rbp-34h] BYREF
  __int128 v17; // [rsp+28h] [rbp-30h] BYREF
  __int128 v18; // [rsp+38h] [rbp-20h] BYREF

  v4 = a3;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v15, a4) )
    goto LABEL_12;
  v8 = a1 + 56 * v4;
  v9 = 56LL * v15;
  *(_OWORD *)(v9 + a2) = *(_OWORD *)v8;
  *(_OWORD *)(v9 + a2 + 16) = *(_OWORD *)(v8 + 16);
  *(_OWORD *)(v9 + a2 + 32) = *(_OWORD *)(v8 + 32);
  *(_QWORD *)(v9 + a2 + 48) = *(_QWORD *)(v8 + 48);
  v18 = *(_OWORD *)(v8 + 24);
  if ( !(unsigned int)BdelimitToken(&v18, ":", &v17, &v16) || v16 )
  {
    vIdentifySource(v8, a4);
    WriteDbgTraceErrorGpd(
      "BExpandCommand",
      "Syntax error in *Command shortcut: %0.*s.",
      *(_DWORD *)(v8 + 32),
      *(const char **)(v8 + 24));
    return 0;
  }
  *(_OWORD *)(v9 + a2 + 24) = v17;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v15, a4) )
    goto LABEL_12;
  v10 = (_DWORD *)(a2 + 56LL * v15);
  *v10 = a4[632];
  v10[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v10, a4) )
    return 0;
  v10[11] = *(_DWORD *)(v8 + 44);
  v10[12] = *(_DWORD *)(v8 + 48);
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v15, a4) )
    goto LABEL_12;
  v11 = v18;
  v12 = a2 + 56LL * v15;
  *(_DWORD *)v12 = a4[637];
  *(_OWORD *)(v12 + 24) = v11;
  if ( !(unsigned int)BInitKeywordField(v12, a4) )
    return 0;
  *(_DWORD *)(v12 + 44) = *(_DWORD *)(v8 + 44);
  *(_DWORD *)(v12 + 48) = *(_DWORD *)(v8 + 48);
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v15, a4) )
  {
LABEL_12:
    a4[554] = 21;
    a4[555] = 2;
    a4[556] = 2;
    return 0;
  }
  v13 = (_DWORD *)(a2 + 56LL * v15);
  *v13 = a4[633];
  v13[8] = 0;
  if ( (unsigned int)BInitKeywordField(v13, a4) )
  {
    v13[11] = *(_DWORD *)(v8 + 44);
    v13[12] = *(_DWORD *)(v8 + 48);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180070fb8  push    rbp
0x180070fba  push    rbx
0x180070fbb  push    rsi
0x180070fbc  push    rdi
0x180070fbd  push    r12
0x180070fbf  push    r14
0x180070fc1  mov     rbp, rsp
0x180070fc4  sub     rsp, 58h
0x180070fc8  mov     edi, r8d
0x180070fcb  mov     r14, rdx
0x180070fce  mov     rsi, rcx
0x180070fd1  mov     [rbp+var_38], 0
0x180070fd8  xorps   xmm0, xmm0
0x180070fdb  mov     [rbp+var_34], 0
0x180070fe2  mov     r12d, 15h
0x180070fe8  lea     rdx, [rbp+var_38]
0x180070fec  mov     ecx, r12d
0x180070fef  mov     r8, r9
0x180070ff2  mov     rbx, r9
0x180070ff5  movups  [rbp+var_30], xmm0
0x180070ff9  call    BallocElementFromMasterTable
0x180070ffe  test    eax, eax
0x180071000  jz      loc_180071190
0x180071006  mov     eax, [rbp+var_38]
0x180071009  lea     r9, [rbp+var_34]
0x18007100d  imul    rdi, 38h ; '8'
0x180071011  lea     r8, [rbp+var_30]
0x180071015  add     rdi, rsi
0x180071018  lea     rdx, asc_1800868D8; ":"
0x18007101f  imul    rsi, rax, 38h ; '8'
0x180071023  movups  xmm0, xmmword ptr [rdi]
0x180071026  lea     rcx, [rbp+var_20]
0x18007102a  movups  xmmword ptr [rsi+r14], xmm0
0x18007102f  movups  xmm1, xmmword ptr [rdi+10h]
0x180071033  movups  xmmword ptr [rsi+r14+10h], xmm1
0x180071039  movups  xmm0, xmmword ptr [rdi+20h]
0x18007103d  movups  xmmword ptr [rsi+r14+20h], xmm0
0x180071043  movsd   xmm1, qword ptr [rdi+30h]
0x180071048  movsd   qword ptr [rsi+r14+30h], xmm1
0x18007104f  movups  xmm0, xmmword ptr [rdi+18h]
0x180071053  movdqu  [rbp+var_20], xmm0
0x180071058  call    BdelimitToken
0x18007105d  test    eax, eax
0x18007105f  jz      loc_180071168
0x180071065  cmp     [rbp+var_34], 0
0x180071069  jnz     loc_180071168
0x18007106f  movups  xmm0, [rbp+var_30]
0x180071073  mov     r8, rbx
0x180071076  lea     rdx, [rbp+var_38]
0x18007107a  mov     ecx, r12d
0x18007107d  movdqu  xmmword ptr [rsi+r14+18h], xmm0
0x180071084  call    BallocElementFromMasterTable
0x180071089  test    eax, eax
0x18007108b  jz      loc_180071190
0x180071091  mov     eax, [rbp+var_38]
0x180071094  mov     rdx, rbx
0x180071097  imul    rsi, rax, 38h ; '8'
0x18007109b  mov     eax, [rbx+9E0h]
0x1800710a1  add     rsi, r14
0x1800710a4  mov     rcx, rsi
0x1800710a7  mov     [rsi], eax
0x1800710a9  mov     dword ptr [rsi+20h], 0
0x1800710b0  call    BInitKeywordField
0x1800710b5  test    eax, eax
0x1800710b7  jz      loc_1800711A8
0x1800710bd  mov     eax, [rdi+2Ch]
0x1800710c0  lea     rdx, [rbp+var_38]
0x1800710c4  mov     [rsi+2Ch], eax
0x1800710c7  mov     r8, rbx
0x1800710ca  mov     eax, [rdi+30h]
0x1800710cd  mov     ecx, r12d
0x1800710d0  mov     [rsi+30h], eax
0x1800710d3  call    BallocElementFromMasterTable
0x1800710d8  test    eax, eax
0x1800710da  jz      loc_180071190
0x1800710e0  mov     eax, [rbp+var_38]
0x1800710e3  mov     rdx, rbx
0x1800710e6  movups  xmm0, [rbp+var_20]
0x1800710ea  imul    rsi, rax, 38h ; '8'
0x1800710ee  mov     eax, [rbx+9F4h]
0x1800710f4  add     rsi, r14
0x1800710f7  mov     rcx, rsi
0x1800710fa  mov     [rsi], eax
0x1800710fc  movdqu  xmmword ptr [rsi+18h], xmm0
0x180071101  call    BInitKeywordField
0x180071106  test    eax, eax
0x180071108  jz      loc_1800711A8
0x18007110e  mov     eax, [rdi+2Ch]
0x180071111  lea     rdx, [rbp+var_38]
0x180071115  mov     [rsi+2Ch], eax
0x180071118  mov     r8, rbx
0x18007111b  mov     eax, [rdi+30h]
0x18007111e  mov     ecx, r12d
0x180071121  mov     [rsi+30h], eax
0x180071124  call    BallocElementFromMasterTable
0x180071129  test    eax, eax
0x18007112b  jz      short loc_180071190
0x18007112d  mov     eax, [rbp+var_38]
0x180071130  mov     rdx, rbx
0x180071133  imul    rsi, rax, 38h ; '8'
0x180071137  mov     eax, [rbx+9E4h]
0x18007113d  add     rsi, r14
0x180071140  mov     rcx, rsi
0x180071143  mov     [rsi], eax
0x180071145  mov     dword ptr [rsi+20h], 0
0x18007114c  call    BInitKeywordField
0x180071151  test    eax, eax
0x180071153  jz      short loc_1800711A8
0x180071155  mov     eax, [rdi+2Ch]
0x180071158  mov     [rsi+2Ch], eax
0x18007115b  mov     eax, [rdi+30h]
0x18007115e  mov     [rsi+30h], eax
0x180071161  lea     eax, [r12-14h]
0x180071166  jmp     short loc_1800711AA
0x180071168  mov     rdx, rbx
0x18007116b  mov     rcx, rdi
0x18007116e  call    vIdentifySource
0x180071173  mov     r9, [rdi+18h]
0x180071177  lea     rdx, aSyntaxErrorInC; "Syntax error in *Command shortcut: %0.*"...
0x18007117e  mov     r8d, [rdi+20h]
0x180071182  lea     rcx, aBexpandcommand; "BExpandCommand"
0x180071189  call    WriteDbgTraceErrorGpd
0x18007118e  jmp     short loc_1800711A8
0x180071190  mov     eax, 2
0x180071195  mov     [rbx+8A8h], r12d
0x18007119c  mov     [rbx+8ACh], eax
0x1800711a2  mov     [rbx+8B0h], eax
0x1800711a8  xor     eax, eax
0x1800711aa  add     rsp, 58h
0x1800711ae  pop     r14
0x1800711b0  pop     r12
0x1800711b2  pop     rdi
0x1800711b3  pop     rsi
0x1800711b4  pop     rbx
0x1800711b5  pop     rbp
0x1800711b6  retn
```
