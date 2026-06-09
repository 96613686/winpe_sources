# BExpandCommand

- ea: `0x18007302c`
- end: `0x18007322c`
- name: `BExpandCommand`
- size: `512`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035ca0`

## callees

- `0x180007150`
- `0x18000aa88`
- `0x180033f3c`
- `0x180045aa4`
- `0x18007302c`
- `0x1800735c0`

## string_xrefs

- `0x1800731eb`: `Syntax error in *Command shortcut: %0.*s.`
- `0x1800731f6`: `BExpandCommand`

## pseudocode

```c
__int64 __fastcall BExpandCommand(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rdi
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // r8
  unsigned int *v11; // rsi
  __int128 v12; // xmm0
  __int64 v13; // rsi
  unsigned int *v14; // rsi
  unsigned int v16; // [rsp+20h] [rbp-38h] BYREF
  int v17; // [rsp+24h] [rbp-34h] BYREF
  __int128 v18; // [rsp+28h] [rbp-30h] BYREF
  __int128 v19; // [rsp+38h] [rbp-20h] BYREF

  v4 = a3;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v16, a4) )
    goto LABEL_12;
  v8 = a1 + 56 * v4;
  v9 = 56LL * v16;
  *(_OWORD *)(v9 + a2) = *(_OWORD *)v8;
  *(_OWORD *)(v9 + a2 + 16) = *(_OWORD *)(v8 + 16);
  *(_OWORD *)(v9 + a2 + 32) = *(_OWORD *)(v8 + 32);
  *(_QWORD *)(v9 + a2 + 48) = *(_QWORD *)(v8 + 48);
  v19 = *(_OWORD *)(v8 + 24);
  if ( !(unsigned int)BdelimitToken((__int64)&v19, (__int64)":", (__int64)&v18, &v17) || v17 )
  {
    vIdentifySource((_DWORD *)v8, (__int64)a4, v10);
    WriteDbgTraceErrorGpd(
      (__int64)"BExpandCommand",
      "Syntax error in *Command shortcut: %0.*s.",
      *(_DWORD *)(v8 + 32),
      *(const char **)(v8 + 24));
    return 0;
  }
  *(_OWORD *)(v9 + a2 + 24) = v18;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v16, a4) )
    goto LABEL_12;
  v11 = (unsigned int *)(a2 + 56LL * v16);
  *v11 = a4[632];
  v11[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v11, (__int64)a4) )
    return 0;
  v11[11] = *(_DWORD *)(v8 + 44);
  v11[12] = *(_DWORD *)(v8 + 48);
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v16, a4) )
    goto LABEL_12;
  v12 = v19;
  v13 = a2 + 56LL * v16;
  *(_DWORD *)v13 = a4[637];
  *(_OWORD *)(v13 + 24) = v12;
  if ( !(unsigned int)BInitKeywordField((unsigned int *)v13, (__int64)a4) )
    return 0;
  *(_DWORD *)(v13 + 44) = *(_DWORD *)(v8 + 44);
  *(_DWORD *)(v13 + 48) = *(_DWORD *)(v8 + 48);
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v16, a4) )
  {
LABEL_12:
    a4[554] = 21;
    a4[555] = 2;
    a4[556] = 2;
    return 0;
  }
  v14 = (unsigned int *)(a2 + 56LL * v16);
  *v14 = a4[633];
  v14[8] = 0;
  if ( (unsigned int)BInitKeywordField(v14, (__int64)a4) )
  {
    v14[11] = *(_DWORD *)(v8 + 44);
    v14[12] = *(_DWORD *)(v8 + 48);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18007302c  push    rbp
0x18007302e  push    rbx
0x18007302f  push    rsi
0x180073030  push    rdi
0x180073031  push    r12
0x180073033  push    r14
0x180073035  mov     rbp, rsp
0x180073038  sub     rsp, 58h
0x18007303c  mov     edi, r8d
0x18007303f  mov     r14, rdx
0x180073042  mov     rsi, rcx
0x180073045  mov     [rbp+var_38], 0
0x18007304c  xorps   xmm0, xmm0
0x18007304f  mov     [rbp+var_34], 0
0x180073056  mov     r12d, 15h
0x18007305c  lea     rdx, [rbp+var_38]
0x180073060  mov     ecx, r12d
0x180073063  mov     r8, r9
0x180073066  mov     rbx, r9
0x180073069  movups  [rbp+var_30], xmm0
0x18007306d  call    BallocElementFromMasterTable
0x180073072  test    eax, eax
0x180073074  jz      loc_180073204
0x18007307a  mov     eax, [rbp+var_38]
0x18007307d  lea     r9, [rbp+var_34]
0x180073081  imul    rdi, 38h ; '8'
0x180073085  lea     r8, [rbp+var_30]
0x180073089  add     rdi, rsi
0x18007308c  lea     rdx, asc_1800888B8; ":"
0x180073093  imul    rsi, rax, 38h ; '8'
0x180073097  movups  xmm0, xmmword ptr [rdi]
0x18007309a  lea     rcx, [rbp+var_20]
0x18007309e  movups  xmmword ptr [rsi+r14], xmm0
0x1800730a3  movups  xmm1, xmmword ptr [rdi+10h]
0x1800730a7  movups  xmmword ptr [rsi+r14+10h], xmm1
0x1800730ad  movups  xmm0, xmmword ptr [rdi+20h]
0x1800730b1  movups  xmmword ptr [rsi+r14+20h], xmm0
0x1800730b7  movsd   xmm1, qword ptr [rdi+30h]
0x1800730bc  movsd   qword ptr [rsi+r14+30h], xmm1
0x1800730c3  movups  xmm0, xmmword ptr [rdi+18h]
0x1800730c7  movdqu  [rbp+var_20], xmm0
0x1800730cc  call    BdelimitToken
0x1800730d1  test    eax, eax
0x1800730d3  jz      loc_1800731DC
0x1800730d9  cmp     [rbp+var_34], 0
0x1800730dd  jnz     loc_1800731DC
0x1800730e3  movups  xmm0, [rbp+var_30]
0x1800730e7  mov     r8, rbx
0x1800730ea  lea     rdx, [rbp+var_38]
0x1800730ee  mov     ecx, r12d
0x1800730f1  movdqu  xmmword ptr [rsi+r14+18h], xmm0
0x1800730f8  call    BallocElementFromMasterTable
0x1800730fd  test    eax, eax
0x1800730ff  jz      loc_180073204
0x180073105  mov     eax, [rbp+var_38]
0x180073108  mov     rdx, rbx
0x18007310b  imul    rsi, rax, 38h ; '8'
0x18007310f  mov     eax, [rbx+9E0h]
0x180073115  add     rsi, r14
0x180073118  mov     rcx, rsi
0x18007311b  mov     [rsi], eax
0x18007311d  mov     dword ptr [rsi+20h], 0
0x180073124  call    BInitKeywordField
0x180073129  test    eax, eax
0x18007312b  jz      loc_18007321C
0x180073131  mov     eax, [rdi+2Ch]
0x180073134  lea     rdx, [rbp+var_38]
0x180073138  mov     [rsi+2Ch], eax
0x18007313b  mov     r8, rbx
0x18007313e  mov     eax, [rdi+30h]
0x180073141  mov     ecx, r12d
0x180073144  mov     [rsi+30h], eax
0x180073147  call    BallocElementFromMasterTable
0x18007314c  test    eax, eax
0x18007314e  jz      loc_180073204
0x180073154  mov     eax, [rbp+var_38]
0x180073157  mov     rdx, rbx
0x18007315a  movups  xmm0, [rbp+var_20]
0x18007315e  imul    rsi, rax, 38h ; '8'
0x180073162  mov     eax, [rbx+9F4h]
0x180073168  add     rsi, r14
0x18007316b  mov     rcx, rsi
0x18007316e  mov     [rsi], eax
0x180073170  movdqu  xmmword ptr [rsi+18h], xmm0
0x180073175  call    BInitKeywordField
0x18007317a  test    eax, eax
0x18007317c  jz      loc_18007321C
0x180073182  mov     eax, [rdi+2Ch]
0x180073185  lea     rdx, [rbp+var_38]
0x180073189  mov     [rsi+2Ch], eax
0x18007318c  mov     r8, rbx
0x18007318f  mov     eax, [rdi+30h]
0x180073192  mov     ecx, r12d
0x180073195  mov     [rsi+30h], eax
0x180073198  call    BallocElementFromMasterTable
0x18007319d  test    eax, eax
0x18007319f  jz      short loc_180073204
0x1800731a1  mov     eax, [rbp+var_38]
0x1800731a4  mov     rdx, rbx
0x1800731a7  imul    rsi, rax, 38h ; '8'
0x1800731ab  mov     eax, [rbx+9E4h]
0x1800731b1  add     rsi, r14
0x1800731b4  mov     rcx, rsi
0x1800731b7  mov     [rsi], eax
0x1800731b9  mov     dword ptr [rsi+20h], 0
0x1800731c0  call    BInitKeywordField
0x1800731c5  test    eax, eax
0x1800731c7  jz      short loc_18007321C
0x1800731c9  mov     eax, [rdi+2Ch]
0x1800731cc  mov     [rsi+2Ch], eax
0x1800731cf  mov     eax, [rdi+30h]
0x1800731d2  mov     [rsi+30h], eax
0x1800731d5  lea     eax, [r12-14h]
0x1800731da  jmp     short loc_18007321E
0x1800731dc  mov     rdx, rbx
0x1800731df  mov     rcx, rdi
0x1800731e2  call    vIdentifySource
0x1800731e7  mov     r9, [rdi+18h]
0x1800731eb  lea     rdx, aSyntaxErrorInC; "Syntax error in *Command shortcut: %0.*"...
0x1800731f2  mov     r8d, [rdi+20h]
0x1800731f6  lea     rcx, aBexpandcommand; "BExpandCommand"
0x1800731fd  call    WriteDbgTraceErrorGpd
0x180073202  jmp     short loc_18007321C
0x180073204  mov     eax, 2
0x180073209  mov     [rbx+8A8h], r12d
0x180073210  mov     [rbx+8ACh], eax
0x180073216  mov     [rbx+8B0h], eax
0x18007321c  xor     eax, eax
0x18007321e  add     rsp, 58h
0x180073222  pop     r14
0x180073224  pop     r12
0x180073226  pop     rdi
0x180073227  pop     rsi
0x180073228  pop     rbx
0x180073229  pop     rbp
0x18007322a  retn
```
