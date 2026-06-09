# FwDiagnoseDisabledProgramRule

- ea: `0x180008040`
- end: `0x18000829b`
- name: `FwDiagnoseDisabledProgramRule`
- size: `603`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800049d0`

## callees

- `0x180007a60`
- `0x180008040`
- `0x1800084a0`
- `0x1800085a0`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800081c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800081c9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180008197`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180008197`

## pseudocode

```c
__int64 __fastcall FwDiagnoseDisabledProgramRule(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v3; // rax
  const WCHAR *v4; // rsi
  char v8; // al
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // edx
  __int64 v12; // rcx
  BOOL IsRuleInActiveProfiles; // ebp
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r8
  int v17; // ecx
  int v18; // edx
  BOOL v19; // edi
  HRESULT v20; // eax
  _WORD *v21; // rcx
  WCHAR pszOutBuf[1024]; // [rsp+30h] [rbp-848h] BYREF

  v3 = *(_QWORD *)(a1 + 312);
  LODWORD(v4) = 0;
  if ( *(_DWORD *)(v3 + 96) != 1 )
    return (unsigned int)v4;
  v8 = *(_BYTE *)(v3 + 104);
  if ( v8 != 8 && v8 != 3 )
    return (unsigned int)v4;
  if ( !*(_QWORD *)(a1 + 288) )
    return (unsigned int)v4;
  v9 = *(_QWORD *)(a1 + 336);
  if ( !v9 )
    return (unsigned int)v4;
  while ( 1 )
  {
    if ( *(_QWORD *)(v9 + 272) && *(_DWORD *)(v9 + 44) == *(_DWORD *)(a1 + 320) && *(_DWORD *)(v9 + 288) == 3 )
    {
      v10 = *(_QWORD *)(v9 + 360);
      if ( !v10 || (v11 = *(_DWORD *)(v10 + 8)) == 0 )
      {
LABEL_14:
        if ( FwDiagIsRuleInActiveProfiles(v9) )
          return (unsigned int)v4;
        goto LABEL_15;
      }
      v12 = 0;
      while ( *(_DWORD *)(*(_QWORD *)(v10 + 16) + 4 * v12) != 4 )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v11 )
          goto LABEL_14;
      }
      IsRuleInActiveProfiles = FwDiagIsRuleInActiveProfiles(v9);
      v14 = *(unsigned __int16 **)(a1 + 304);
      if ( !v14 )
        break;
      v15 = *(_QWORD *)(v9 + 312);
      if ( v15 )
      {
        v16 = v15 - (_QWORD)v14;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v14 + v16);
          v18 = *v14 - v17;
          if ( v18 )
            break;
          ++v14;
        }
        while ( v17 );
        if ( !v18 )
          break;
      }
    }
LABEL_15:
    v9 = *(_QWORD *)v9;
    if ( !v9 )
      return (unsigned int)v4;
  }
  v4 = *(const WCHAR **)(v9 + 312);
  v19 = 0;
  if ( v4 )
  {
    v20 = SHLoadIndirectString(*(PCWSTR *)(v9 + 312), pszOutBuf, 0x400u, 0);
    if ( v20 >= 0 )
    {
      v19 = CompareStringW(0x7Fu, 1u, v4, -1, pszOutBuf, -1) != 2 || (*v4 & 0xFFBF) != 0;
      LODWORD(v4) = 0;
      goto LABEL_31;
    }
    LODWORD(v4) = (unsigned __int16)v20;
  }
  if ( (_DWORD)v4 )
    return (unsigned int)v4;
LABEL_31:
  if ( !v19 )
  {
    if ( !(unsigned int)FwDiagIsRuleAdvanced(v9) )
    {
      *(_DWORD *)a2 = 3;
      *(_DWORD *)(a2 + 4) = 2;
      *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 320) == 1;
      v21 = *(_WORD **)(a1 + 288);
      goto LABEL_36;
    }
    goto LABEL_15;
  }
  if ( !IsRuleInActiveProfiles )
    goto LABEL_15;
  *(_DWORD *)a2 = 3;
  *(_DWORD *)(a2 + 4) = 4;
  v21 = *(_WORD **)(v9 + 312);
LABEL_36:
  LODWORD(v4) = FwDiagCopyString(v21, (_QWORD *)(a2 + 16));
  if ( !(_DWORD)v4 )
    *a3 = 1;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008040  push    rsi
0x180008042  push    r12
0x180008044  push    r14
0x180008046  push    r15
0x180008048  sub     rsp, 858h
0x18000804f  mov     rax, cs:__security_cookie
0x180008056  xor     rax, rsp
0x180008059  mov     [rsp+878h+var_48], rax
0x180008061  mov     rax, [rcx+138h]
0x180008068  xor     esi, esi
0x18000806a  mov     r12, r8
0x18000806d  mov     r15, rdx
0x180008070  mov     r14, rcx
0x180008073  cmp     dword ptr [rax+60h], 1
0x180008077  jnz     loc_18000827A
0x18000807d  movzx   eax, byte ptr [rax+68h]
0x180008081  cmp     al, 8
0x180008083  jz      short loc_18000808D
0x180008085  cmp     al, 3
0x180008087  jnz     loc_18000827A
0x18000808d  cmp     [rcx+120h], rsi
0x180008094  jz      loc_18000827A
0x18000809a  mov     [rsp+878h+arg_18], rbx
0x1800080a2  mov     rbx, [rcx+150h]
0x1800080a9  test    rbx, rbx
0x1800080ac  jz      loc_180008272
0x1800080b2  mov     [rsp+878h+var_38], r13
0x1800080ba  mov     r13d, 1
0x1800080c0  mov     [rsp+878h+var_28], rbp
0x1800080c8  mov     [rsp+878h+var_30], rdi
0x1800080d0  cmp     qword ptr [rbx+110h], 0
0x1800080d8  jz      short loc_180008125
0x1800080da  mov     eax, [r14+140h]
0x1800080e1  cmp     [rbx+2Ch], eax
0x1800080e4  jnz     short loc_180008125
0x1800080e6  cmp     dword ptr [rbx+120h], 3
0x1800080ed  jnz     short loc_180008125
0x1800080ef  mov     rax, [rbx+168h]
0x1800080f6  test    rax, rax
0x1800080f9  jz      short loc_180008115
0x1800080fb  mov     edx, [rax+8]
0x1800080fe  test    edx, edx
0x180008100  jz      short loc_180008115
0x180008102  mov     r8, [rax+10h]
0x180008106  xor     ecx, ecx
0x180008108  cmp     dword ptr [r8+rcx*4], 4
0x18000810d  jz      short loc_180008132
0x18000810f  inc     ecx
0x180008111  cmp     ecx, edx
0x180008113  jb      short loc_180008108
0x180008115  mov     rcx, rbx
0x180008118  call    FwDiagIsRuleInActiveProfiles
0x18000811d  test    eax, eax
0x18000811f  jnz     loc_18000825A
0x180008125  mov     rbx, [rbx]
0x180008128  test    rbx, rbx
0x18000812b  jnz     short loc_1800080D0
0x18000812d  jmp     loc_18000825A
0x180008132  mov     rcx, rbx
0x180008135  call    FwDiagIsRuleInActiveProfiles
0x18000813a  mov     ebp, eax
0x18000813c  mov     rax, [r14+130h]
0x180008143  test    rax, rax
0x180008146  jz      short loc_180008178
0x180008148  mov     r8, [rbx+138h]
0x18000814f  test    r8, r8
0x180008152  jz      short loc_180008125
0x180008154  sub     r8, rax
0x180008157  nop     word ptr [rax+rax+00000000h]
0x180008160  movzx   edx, word ptr [rax]
0x180008163  movzx   ecx, word ptr [rax+r8]
0x180008168  sub     edx, ecx
0x18000816a  jnz     short loc_180008174
0x18000816c  add     rax, 2
0x180008170  test    ecx, ecx
0x180008172  jnz     short loc_180008160
0x180008174  test    edx, edx
0x180008176  jnz     short loc_180008125
0x180008178  mov     rsi, [rbx+138h]
0x18000817f  xor     edi, edi
0x180008181  test    rsi, rsi
0x180008184  jz      short loc_1800081EB
0x180008186  xor     r9d, r9d; ppvReserved
0x180008189  lea     rdx, [rsp+878h+pszOutBuf]; pszOutBuf
0x18000818e  mov     r8d, 400h; cchOutBuf
0x180008194  mov     rcx, rsi; pszSource
0x180008197  call    cs:__imp_SHLoadIndirectString
0x18000819d  test    eax, eax
0x18000819f  jns     short loc_1800081A6
0x1800081a1  movzx   esi, ax
0x1800081a4  jmp     short loc_1800081EB
0x1800081a6  lea     rax, [rsp+878h+pszOutBuf]
0x1800081ab  mov     [rsp+878h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800081b3  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800081b9  mov     [rsp+878h+lpString2], rax; lpString2
0x1800081be  mov     r8, rsi; lpString1
0x1800081c1  mov     edx, r13d; dwCmpFlags
0x1800081c4  mov     ecx, 7Fh; Locale
0x1800081c9  call    cs:__imp_CompareStringW
0x1800081cf  cmp     eax, 2
0x1800081d2  jz      short loc_1800081DB
0x1800081d4  mov     edi, r13d
0x1800081d7  xor     esi, esi
0x1800081d9  jmp     short loc_1800081EF
0x1800081db  mov     eax, 0FFBFh
0x1800081e0  test    [rsi], ax
0x1800081e3  cmovnz  edi, r13d
0x1800081e7  xor     esi, esi
0x1800081e9  jmp     short loc_1800081EF
0x1800081eb  test    esi, esi
0x1800081ed  jnz     short loc_18000825A
0x1800081ef  test    edi, edi
0x1800081f1  jnz     short loc_180008229
0x1800081f3  mov     rcx, rbx
0x1800081f6  call    FwDiagIsRuleAdvanced
0x1800081fb  test    eax, eax
0x1800081fd  jnz     loc_180008125
0x180008203  mov     dword ptr [r15], 3
0x18000820a  mov     dword ptr [r15+4], 2
0x180008212  cmp     [r14+140h], r13d
0x180008219  setz    al
0x18000821c  mov     [r15+8], eax
0x180008220  mov     rcx, [r14+120h]
0x180008227  jmp     short loc_180008247
0x180008229  test    ebp, ebp
0x18000822b  jz      loc_180008125
0x180008231  mov     dword ptr [r15], 3
0x180008238  mov     dword ptr [r15+4], 4
0x180008240  mov     rcx, [rbx+138h]; Src
0x180008247  lea     rdx, [r15+10h]
0x18000824b  call    FwDiagCopyString
0x180008250  mov     esi, eax
0x180008252  test    eax, eax
0x180008254  jnz     short loc_18000825A
0x180008256  mov     [r12], r13d
0x18000825a  mov     rdi, [rsp+878h+var_30]
0x180008262  mov     rbp, [rsp+878h+var_28]
0x18000826a  mov     r13, [rsp+878h+var_38]
0x180008272  mov     rbx, [rsp+878h+arg_18]
0x18000827a  mov     eax, esi
0x18000827c  mov     rcx, [rsp+878h+var_48]
0x180008284  xor     rcx, rsp; StackCookie
0x180008287  call    __security_check_cookie
0x18000828c  add     rsp, 858h
0x180008293  pop     r15
0x180008295  pop     r14
0x180008297  pop     r12
0x180008299  pop     rsi
0x18000829a  retn
```
