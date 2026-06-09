# FwDiagnoseDisabledPortRule

- ea: `0x180007d60`
- end: `0x180008035`
- name: `FwDiagnoseDisabledPortRule`
- size: `725`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800049d0`

## callees

- `0x180007a60`
- `0x180007d60`
- `0x1800084a0`
- `0x1800085a0`
- `0x18000c5b0`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180007dd6`
- `WS2_32!__imp_ntohs` at `0x180007dd6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007f5d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007f5d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180007f27`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180007f27`

## pseudocode

```c
__int64 __fastcall FwDiagnoseDisabledPortRule(__int64 a1, __int64 a2, _DWORD *a3)
{
  const WCHAR *v4; // rdi
  u_short v5; // r9
  u_short v8; // r12
  __int16 v9; // ax
  u_short v10; // cx
  __int16 v11; // ax
  __int64 v12; // rax
  char v13; // cl
  __int64 v14; // rbx
  bool v15; // zf
  __int64 v16; // rax
  unsigned int v17; // edx
  __int64 v18; // rcx
  BOOL IsRuleInActiveProfiles; // ebp
  unsigned __int16 *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r8
  int v23; // ecx
  int v24; // edx
  BOOL v25; // esi
  HRESULT v26; // eax
  WCHAR pszOutBuf[1024]; // [rsp+30h] [rbp-848h] BYREF

  LODWORD(v4) = 0;
  v5 = 0;
  if ( *(_DWORD *)(a1 + 320) == 1 )
  {
    v11 = *(_WORD *)(a1 + 24);
    if ( v11 != 2 && v11 != 23 )
      goto LABEL_11;
    v10 = *(_WORD *)(a1 + 26);
    goto LABEL_10;
  }
  if ( *(_DWORD *)(a1 + 320) != 2 )
  {
    v8 = 0;
    goto LABEL_12;
  }
  v9 = *(_WORD *)(a1 + 24);
  if ( v9 == 2 || v9 == 23 )
  {
    v10 = *(_WORD *)(a1 + 154);
LABEL_10:
    v5 = ntohs(v10);
  }
LABEL_11:
  v8 = v5;
LABEL_12:
  v12 = *(_QWORD *)(a1 + 312);
  if ( *(_DWORD *)(v12 + 96) != 1 )
    return (unsigned int)v4;
  v13 = *(_BYTE *)(v12 + 104);
  if ( v13 != 8 && v13 != 3 )
    return (unsigned int)v4;
  if ( !v8 )
    return (unsigned int)v4;
  if ( !*(_BYTE *)(a1 + 16) )
    return (unsigned int)v4;
  v14 = *(_QWORD *)(a1 + 336);
  if ( !v14 )
    return (unsigned int)v4;
  while ( 1 )
  {
    if ( *(_DWORD *)(a1 + 320) == 1 )
    {
      v15 = *(_DWORD *)(v14 + 64) == 0;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 320) != 2 )
        goto LABEL_31;
      v15 = *(_DWORD *)(v14 + 88) == 0;
    }
    if ( !v15 && *(_DWORD *)(v14 + 44) == *(_DWORD *)(a1 + 320) && *(_DWORD *)(v14 + 288) == 3 )
    {
      v16 = *(_QWORD *)(v14 + 360);
      if ( !v16 || (v17 = *(_DWORD *)(v16 + 8)) == 0 )
      {
LABEL_30:
        if ( FwDiagIsRuleInActiveProfiles(v14) )
          return (unsigned int)v4;
        goto LABEL_31;
      }
      v18 = 0;
      while ( *(_DWORD *)(*(_QWORD *)(v16 + 16) + 4 * v18) != 4 )
      {
        v18 = (unsigned int)(v18 + 1);
        if ( (unsigned int)v18 >= v17 )
          goto LABEL_30;
      }
      IsRuleInActiveProfiles = FwDiagIsRuleInActiveProfiles(v14);
      v20 = *(unsigned __int16 **)(a1 + 304);
      if ( !v20 )
        break;
      v21 = *(_QWORD *)(v14 + 312);
      if ( v21 )
      {
        v22 = v21 - (_QWORD)v20;
        do
        {
          v23 = *(unsigned __int16 *)((char *)v20 + v22);
          v24 = *v20 - v23;
          if ( v24 )
            break;
          ++v20;
        }
        while ( v23 );
        if ( !v24 )
          break;
      }
    }
LABEL_31:
    v14 = *(_QWORD *)v14;
    if ( !v14 )
      return (unsigned int)v4;
  }
  v4 = *(const WCHAR **)(v14 + 312);
  v25 = 0;
  if ( v4 )
  {
    v26 = SHLoadIndirectString(v4, pszOutBuf, 0x400u, 0);
    if ( v26 >= 0 )
    {
      v25 = 1;
      if ( CompareStringW(0x7Fu, 1u, v4, -1, pszOutBuf, -1) == 2 )
        v25 = (*v4 & 0xFFBF) != 0;
      LODWORD(v4) = 0;
      goto LABEL_46;
    }
    LODWORD(v4) = (unsigned __int16)v26;
  }
  if ( (_DWORD)v4 )
    return (unsigned int)v4;
LABEL_46:
  if ( !v25 )
  {
    if ( !(unsigned int)FwDiagIsRuleAdvanced(v14) )
    {
      *(_DWORD *)a2 = 3;
      *(_DWORD *)(a2 + 4) = 3;
      v15 = *(_DWORD *)(a1 + 320) == 1;
      *(_WORD *)(a2 + 16) = v8;
      *(_DWORD *)(a2 + 8) = v15;
      *(_WORD *)(a2 + 18) = *(unsigned __int8 *)(a1 + 16);
      goto LABEL_51;
    }
    goto LABEL_31;
  }
  if ( !IsRuleInActiveProfiles )
    goto LABEL_31;
  *(_DWORD *)a2 = 3;
  *(_DWORD *)(a2 + 4) = 4;
  LODWORD(v4) = FwDiagCopyString(*(_WORD **)(v14 + 312), (_QWORD *)(a2 + 16));
  if ( (_DWORD)v4 )
    return (unsigned int)v4;
LABEL_51:
  *a3 = 1;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007d60  push    rdi
0x180007d62  push    r12
0x180007d64  push    r13
0x180007d66  push    r14
0x180007d68  push    r15
0x180007d6a  sub     rsp, 850h
0x180007d71  mov     rax, cs:__security_cookie
0x180007d78  xor     rax, rsp
0x180007d7b  mov     [rsp+878h+var_48], rax
0x180007d83  mov     r13, r8
0x180007d86  xor     edi, edi
0x180007d88  mov     r8d, [rcx+140h]
0x180007d8f  xor     r9d, r9d
0x180007d92  mov     r15, rdx
0x180007d95  mov     r14, rcx
0x180007d98  sub     r8d, 1
0x180007d9c  jz      short loc_180007DC2
0x180007d9e  cmp     r8d, 1
0x180007da2  jz      short loc_180007DA9
0x180007da4  xor     r12d, r12d
0x180007da7  jmp     short loc_180007DE4
0x180007da9  movzx   eax, word ptr [rcx+18h]
0x180007dad  cmp     ax, 2
0x180007db1  jz      short loc_180007DB9
0x180007db3  cmp     ax, 17h
0x180007db7  jnz     short loc_180007DE0
0x180007db9  movzx   ecx, word ptr [rcx+9Ah]
0x180007dc0  jmp     short loc_180007DD6
0x180007dc2  movzx   eax, word ptr [rcx+18h]
0x180007dc6  cmp     ax, 2
0x180007dca  jz      short loc_180007DD2
0x180007dcc  cmp     ax, 17h
0x180007dd0  jnz     short loc_180007DE0
0x180007dd2  movzx   ecx, word ptr [rcx+1Ah]; netshort
0x180007dd6  call    cs:__imp_ntohs
0x180007ddc  movzx   r9d, ax
0x180007de0  movzx   r12d, r9w
0x180007de4  mov     rax, [r14+138h]
0x180007deb  cmp     dword ptr [rax+60h], 1
0x180007def  jnz     loc_180008012
0x180007df5  movzx   ecx, byte ptr [rax+68h]
0x180007df9  cmp     cl, 8
0x180007dfc  jz      short loc_180007E07
0x180007dfe  cmp     cl, 3
0x180007e01  jnz     loc_180008012
0x180007e07  test    r12w, r12w
0x180007e0b  jz      loc_180008012
0x180007e11  cmp     [r14+10h], dil
0x180007e15  jz      loc_180008012
0x180007e1b  mov     [rsp+878h+arg_18], rbx
0x180007e23  mov     rbx, [r14+150h]
0x180007e2a  test    rbx, rbx
0x180007e2d  jz      loc_18000800A
0x180007e33  mov     [rsp+878h+var_30], rbp
0x180007e3b  mov     [rsp+878h+var_38], rsi
0x180007e43  nop     dword ptr [rax+00h]
0x180007e47  nop     word ptr [rax+rax+00000000h]
0x180007e50  mov     edx, [r14+140h]
0x180007e57  mov     ecx, edx
0x180007e59  sub     ecx, 1
0x180007e5c  jz      short loc_180007E69
0x180007e5e  cmp     ecx, 1
0x180007e61  jnz     short loc_180007EB3
0x180007e63  cmp     dword ptr [rbx+58h], 0
0x180007e67  jmp     short loc_180007E6D
0x180007e69  cmp     dword ptr [rbx+40h], 0
0x180007e6d  jbe     short loc_180007EB3
0x180007e6f  cmp     [rbx+2Ch], edx
0x180007e72  jnz     short loc_180007EB3
0x180007e74  cmp     dword ptr [rbx+120h], 3
0x180007e7b  jnz     short loc_180007EB3
0x180007e7d  mov     rax, [rbx+168h]
0x180007e84  test    rax, rax
0x180007e87  jz      short loc_180007EA3
0x180007e89  mov     edx, [rax+8]
0x180007e8c  test    edx, edx
0x180007e8e  jz      short loc_180007EA3
0x180007e90  mov     r8, [rax+10h]
0x180007e94  xor     ecx, ecx
0x180007e96  cmp     dword ptr [r8+rcx*4], 4
0x180007e9b  jz      short loc_180007EC0
0x180007e9d  inc     ecx
0x180007e9f  cmp     ecx, edx
0x180007ea1  jb      short loc_180007E96
0x180007ea3  mov     rcx, rbx
0x180007ea6  call    FwDiagIsRuleInActiveProfiles
0x180007eab  test    eax, eax
0x180007ead  jnz     loc_180007FFA
0x180007eb3  mov     rbx, [rbx]
0x180007eb6  test    rbx, rbx
0x180007eb9  jnz     short loc_180007E50
0x180007ebb  jmp     loc_180007FFA
0x180007ec0  mov     rcx, rbx
0x180007ec3  call    FwDiagIsRuleInActiveProfiles
0x180007ec8  mov     ebp, eax
0x180007eca  mov     rax, [r14+130h]
0x180007ed1  test    rax, rax
0x180007ed4  jz      short loc_180007F08
0x180007ed6  mov     r8, [rbx+138h]
0x180007edd  test    r8, r8
0x180007ee0  jz      short loc_180007EB3
0x180007ee2  sub     r8, rax
0x180007ee5  nop     word ptr [rax+rax+00000000h]
0x180007ef0  movzx   edx, word ptr [rax]
0x180007ef3  movzx   ecx, word ptr [rax+r8]
0x180007ef8  sub     edx, ecx
0x180007efa  jnz     short loc_180007F04
0x180007efc  add     rax, 2
0x180007f00  test    ecx, ecx
0x180007f02  jnz     short loc_180007EF0
0x180007f04  test    edx, edx
0x180007f06  jnz     short loc_180007EB3
0x180007f08  mov     rdi, [rbx+138h]
0x180007f0f  xor     esi, esi
0x180007f11  test    rdi, rdi
0x180007f14  jz      short loc_180007F7E
0x180007f16  xor     r9d, r9d; ppvReserved
0x180007f19  lea     rdx, [rsp+878h+pszOutBuf]; pszOutBuf
0x180007f1e  mov     r8d, 400h; cchOutBuf
0x180007f24  mov     rcx, rdi; pszSource
0x180007f27  call    cs:__imp_SHLoadIndirectString
0x180007f2d  test    eax, eax
0x180007f2f  jns     short loc_180007F36
0x180007f31  movzx   edi, ax
0x180007f34  jmp     short loc_180007F7E
0x180007f36  lea     rax, [rsp+878h+pszOutBuf]
0x180007f3b  mov     [rsp+878h+cchCount2], 0FFFFFFFFh; cchCount2
0x180007f43  mov     esi, 1
0x180007f48  mov     [rsp+878h+lpString2], rax; lpString2
0x180007f4d  mov     edx, esi; dwCmpFlags
0x180007f4f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180007f55  mov     r8, rdi; lpString1
0x180007f58  mov     ecx, 7Fh; Locale
0x180007f5d  call    cs:__imp_CompareStringW
0x180007f63  cmp     eax, 2
0x180007f66  jnz     short loc_180007F7A
0x180007f68  xor     esi, esi
0x180007f6a  mov     eax, 0FFBFh
0x180007f6f  test    [rdi], ax
0x180007f72  mov     eax, 1
0x180007f77  cmovnz  esi, eax
0x180007f7a  xor     edi, edi
0x180007f7c  jmp     short loc_180007F82
0x180007f7e  test    edi, edi
0x180007f80  jnz     short loc_180007FFA
0x180007f82  test    esi, esi
0x180007f84  jnz     short loc_180007FC5
0x180007f86  mov     rcx, rbx
0x180007f89  call    FwDiagIsRuleAdvanced
0x180007f8e  test    eax, eax
0x180007f90  jnz     loc_180007EB3
0x180007f96  mov     dword ptr [r15], 3
0x180007f9d  mov     dword ptr [r15+4], 3
0x180007fa5  cmp     dword ptr [r14+140h], 1
0x180007fad  mov     [r15+10h], r12w
0x180007fb2  setz    al
0x180007fb5  mov     [r15+8], eax
0x180007fb9  movzx   eax, byte ptr [r14+10h]
0x180007fbe  mov     [r15+12h], ax
0x180007fc3  jmp     short loc_180007FF2
0x180007fc5  test    ebp, ebp
0x180007fc7  jz      loc_180007EB3
0x180007fcd  mov     dword ptr [r15], 3
0x180007fd4  lea     rdx, [r15+10h]
0x180007fd8  mov     dword ptr [r15+4], 4
0x180007fe0  mov     rcx, [rbx+138h]; Src
0x180007fe7  call    FwDiagCopyString
0x180007fec  mov     edi, eax
0x180007fee  test    eax, eax
0x180007ff0  jnz     short loc_180007FFA
0x180007ff2  mov     dword ptr [r13+0], 1
0x180007ffa  mov     rbp, [rsp+878h+var_30]
0x180008002  mov     rsi, [rsp+878h+var_38]
0x18000800a  mov     rbx, [rsp+878h+arg_18]
0x180008012  mov     eax, edi
0x180008014  mov     rcx, [rsp+878h+var_48]
0x18000801c  xor     rcx, rsp; StackCookie
0x18000801f  call    __security_check_cookie
0x180008024  add     rsp, 850h
0x18000802b  pop     r15
0x18000802d  pop     r14
0x18000802f  pop     r13
0x180008031  pop     r12
0x180008033  pop     rdi
0x180008034  retn
```
