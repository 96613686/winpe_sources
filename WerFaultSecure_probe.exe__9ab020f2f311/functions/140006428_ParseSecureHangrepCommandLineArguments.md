# ParseSecureHangrepCommandLineArguments

- ea: `0x140006428`
- end: `0x1400068b7`
- name: `ParseSecureHangrepCommandLineArguments`
- size: `1167`
- prototype: `__int64 __fastcall(int, __int64, int *, int *, int *piRet, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400068c0`

## callees

- `0x140005128`
- `0x140006428`
- `0x14000e598`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006804`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x14000667c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x14000667c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x140006756`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x1400067de`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x140006756`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToInt64ExW` at `0x1400067de`

## string_xrefs

- `0x140006873`: `Illegal command line`
- `0x14000687f`: `ParseSecureHangrepCommandLineArguments`

## pseudocode

```c
__int64 __fastcall ParseSecureHangrepCommandLineArguments(
        __int64 a1,
        __int64 a2,
        int *a3,
        int *a4,
        int *piRet,
        void **a6,
        void **a7)
{
  __int64 v9; // rdi
  int v10; // r15d
  int *v11; // r12
  void **v12; // rsi
  void **v13; // rbx
  void *v14; // rcx
  void *v15; // rcx
  int v16; // r14d
  unsigned int v17; // ebp
  __int64 v18; // r10
  wchar_t *v19; // r11
  __int64 v20; // rdi
  int v21; // ecx
  int v22; // r9d
  int v23; // r8d
  int v24; // edx
  int *v25; // r8
  __int64 v26; // r9
  int v27; // ecx
  int v28; // r8d
  int v29; // edx
  int v30; // ecx
  __int64 v31; // r9
  int v32; // ecx
  int v33; // r8d
  int v34; // edx
  int v35; // ecx
  void *v36; // rcx
  void *v37; // rcx
  __int64 v39; // r9
  int v40; // ecx
  int v41; // r8d
  int v42; // edx
  int v43; // ecx
  void *v44; // rcx
  __int64 v45; // r9
  int v46; // ecx
  int v47; // r8d
  int v48; // edx
  int v49; // ecx
  __int64 v50; // rdx
  wil::details *v51; // [rsp+20h] [rbp-48h]
  const char *v52; // [rsp+30h] [rbp-38h]
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+0h]
  LONGLONG pllRet; // [rsp+80h] [rbp+18h] BYREF
  int *v56; // [rsp+88h] [rbp+20h]

  v56 = a4;
  v9 = a2;
  v10 = a1;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, 0, a4);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v11 = piRet;
  if ( !piRet )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v12 = a6;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v13 = a7;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  *a3 = 0;
  *a4 = 0;
  v14 = *v12;
  *v12 = 0;
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  v15 = *v13;
  *v13 = 0;
  if ( (unsigned __int64)v15 + 1 > 1 )
    CloseHandle(v15);
  pllRet = 0;
  v16 = 0;
  v17 = -2147024809;
  if ( v10 > 0 )
  {
    while ( 1 )
    {
      v18 = -1;
      v19 = *(wchar_t **)(v9 + 8LL * (unsigned int)v16);
      do
        ++v18;
      while ( v19[v18] );
      switch ( v18 )
      {
        case 4LL:
          if ( v19 == L"/pid" )
          {
LABEL_28:
            if ( v16 >= v10 - 1 )
            {
              v50 = 85;
              goto LABEL_93;
            }
            v25 = a3;
LABEL_52:
            if ( !StrToIntExW(*(PCWSTR *)(v9 + 8LL * (unsigned int)v16 + 8), 0, v25) )
              goto LABEL_53;
            break;
          }
          v20 = 0;
          while ( 1 )
          {
            v21 = v19[v20];
            v22 = aPid[v20];
            v23 = v21 - 32;
            if ( (unsigned int)(v21 - 97) >= 0x1A )
              v23 = v19[v20];
            v24 = v22 - 32;
            if ( (unsigned int)(v22 - 97) >= 0x1A )
              v24 = aPid[v20];
            if ( v23 != v24 )
              break;
            if ( ++v20 == 4 )
            {
              v9 = a2;
              goto LABEL_28;
            }
          }
          v9 = a2;
          if ( v19 == L"/tid" )
          {
LABEL_39:
            if ( v16 >= v10 - 1 )
            {
              v50 = 100;
              goto LABEL_93;
            }
            v25 = v56;
            goto LABEL_52;
          }
          v26 = 0;
          while ( 1 )
          {
            v27 = aTid[v26];
            v28 = v19[v26];
            v29 = v27 - 32;
            if ( (unsigned int)(v27 - 97) >= 0x1A )
              v29 = aTid[v26];
            v30 = v28 - 32;
            if ( (unsigned int)(v28 - 97) >= 0x1A )
              v30 = v19[v26];
            if ( v30 != v29 )
              break;
            if ( ++v26 == 4 )
              goto LABEL_39;
          }
          break;
        case 5LL:
          if ( v19 == L"/type" )
          {
LABEL_50:
            if ( v16 >= v10 - 1 )
            {
              v50 = 115;
              goto LABEL_93;
            }
            v25 = piRet;
            goto LABEL_52;
          }
          v31 = 0;
          while ( 1 )
          {
            v32 = aType[v31];
            v33 = v19[v31];
            v34 = v32 - 32;
            if ( (unsigned int)(v32 - 97) >= 0x1A )
              v34 = aType[v31];
            v35 = v33 - 32;
            if ( (unsigned int)(v33 - 97) >= 0x1A )
              v35 = v19[v31];
            if ( v35 != v34 )
              break;
            if ( ++v31 == 5 )
              goto LABEL_50;
          }
          break;
        case 8LL:
          if ( v19 != L"/encfile" )
          {
            v39 = 0;
            do
            {
              v40 = aEncfile[v39];
              v41 = v19[v39];
              v42 = v40 - 32;
              if ( (unsigned int)(v40 - 97) >= 0x1A )
                v42 = aEncfile[v39];
              v43 = v41 - 32;
              if ( (unsigned int)(v41 - 97) >= 0x1A )
                v43 = v19[v39];
              if ( v43 != v42 )
                goto LABEL_84;
            }
            while ( ++v39 != 8 );
          }
          if ( v16 >= v10 - 1 )
          {
            v50 = 131;
            goto LABEL_93;
          }
          if ( !StrToInt64ExW(*(PCWSTR *)(v9 + 8LL * (unsigned int)v16 + 8), 0, &pllRet) )
            goto LABEL_53;
          v44 = *v12;
          *v12 = (void *)pllRet;
          goto LABEL_82;
        case 7LL:
          if ( v19 != L"/cancel" )
          {
            v45 = 0;
            do
            {
              v46 = aCancel[v45];
              v47 = v19[v45];
              v48 = v46 - 32;
              if ( (unsigned int)(v46 - 97) >= 0x1A )
                v48 = aCancel[v45];
              v49 = v47 - 32;
              if ( (unsigned int)(v47 - 97) >= 0x1A )
                v49 = v19[v45];
              if ( v49 != v48 )
                goto LABEL_84;
            }
            while ( ++v45 != 7 );
          }
          if ( v16 >= v10 - 1 )
          {
            v50 = 147;
LABEL_93:
            LODWORD(v51) = -2147024809;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)v50,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\securedump.cpp",
              "ParseSecureHangrepCommandLineArguments",
              v51,
              (int)"Illegal command line",
              v52);
LABEL_53:
            *v56 = 0;
            *a3 = 0;
            v36 = *v12;
            *v12 = 0;
            if ( (unsigned __int64)v36 + 1 > 1 )
              CloseHandle(v36);
            v37 = *v13;
            *v13 = 0;
            if ( (unsigned __int64)v37 + 1 > 1 )
              CloseHandle(v37);
            return v17;
          }
          if ( !StrToInt64ExW(*(PCWSTR *)(v9 + 8LL * (unsigned int)v16 + 8), 0, &pllRet) )
            goto LABEL_53;
          v44 = *v13;
          *v13 = (void *)pllRet;
LABEL_82:
          if ( (unsigned __int64)v44 + 1 > 1 )
            CloseHandle(v44);
          break;
      }
LABEL_84:
      if ( ++v16 >= v10 )
      {
        v11 = piRet;
        break;
      }
    }
  }
  if ( !*a3
    || !*v11
    || *v13 == (void *)-1LL
    || (char *)*v13 + 1 == (void *)1
    || *v12 == (void *)-1LL
    || (char *)*v12 + 1 == (void *)1
    || (*v11 & 0xFA000000) != 0 )
  {
    goto LABEL_53;
  }
  return 0;
}

```

## disassembly

```asm
0x140006428  mov     [rsp+arg_0], rbx
0x14000642d  mov     [rsp+arg_18], r9
0x140006432  mov     [rsp+arg_8], rdx
0x140006437  push    rbp
0x140006438  push    rsi
0x140006439  push    rdi
0x14000643a  push    r12
0x14000643c  push    r13
0x14000643e  push    r14
0x140006440  push    r15; char *
0x140006442  sub     rsp, 30h
0x140006446  xor     ebp, ebp
0x140006448  mov     r14, r9
0x14000644b  mov     r13, r8
0x14000644e  mov     rdi, rdx
0x140006451  mov     r15d, ecx
0x140006454  test    r8, r8
0x140006457  jnz     short loc_14000645E
0x140006459  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000645e  test    r14, r14
0x140006461  jnz     short loc_140006468
0x140006463  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140006468  mov     r12, [rsp+68h+piRet]
0x140006470  test    r12, r12
0x140006473  jnz     short loc_14000647A
0x140006475  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000647a  mov     rsi, [rsp+68h+arg_28]
0x140006482  test    rsi, rsi
0x140006485  jnz     short loc_14000648C
0x140006487  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000648c  mov     rbx, [rsp+68h+arg_30]
0x140006494  test    rbx, rbx
0x140006497  jnz     short loc_14000649E
0x140006499  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000649e  mov     [r13+0], ebp
0x1400064a2  mov     [r14], ebp
0x1400064a5  mov     rcx, [rsi]; hObject
0x1400064a8  mov     [rsi], rbp
0x1400064ab  lea     rax, [rcx+1]
0x1400064af  cmp     rax, 1
0x1400064b3  jbe     short loc_1400064BB
0x1400064b5  call    cs:__imp_CloseHandle
0x1400064bb  mov     rcx, [rbx]; hObject
0x1400064be  mov     [rbx], rbp
0x1400064c1  lea     rax, [rcx+1]
0x1400064c5  cmp     rax, 1
0x1400064c9  jbe     short loc_1400064D1
0x1400064cb  call    cs:__imp_CloseHandle
0x1400064d1  xor     eax, eax
0x1400064d3  mov     [rsp+68h+pllRet], rbp
0x1400064db  mov     r14d, ebp
0x1400064de  mov     ebp, 80070057h
0x1400064e3  test    r15d, r15d
0x1400064e6  jle     loc_140006820
0x1400064ec  mov     r12d, r14d
0x1400064ef  lea     r9, aCancel; "/cancel"
0x1400064f6  lea     r8, aEncfile; "/encfile"
0x1400064fd  or      r10, 0FFFFFFFFFFFFFFFFh
0x140006501  lea     rdx, aType; "/type"
0x140006508  lea     rcx, aTid; "/tid"
0x14000650f  mov     r11, [rdi+r12*8]
0x140006513  inc     r10
0x140006516  cmp     [r11+r10*2], ax
0x14000651b  jnz     short loc_140006513
0x14000651d  cmp     r10, 4
0x140006521  jnz     loc_140006611
0x140006527  lea     rdx, aPid; "/pid"
0x14000652e  cmp     r11, rdx
0x140006531  jz      short loc_140006577
0x140006533  mov     rdi, rax
0x140006536  movzx   ecx, word ptr [r11+rdi*2]
0x14000653b  movzx   r9d, word ptr [rdx+rdi*2]
0x140006540  lea     eax, [rcx-61h]
0x140006543  cmp     eax, 1Ah
0x140006546  lea     r8d, [rcx-20h]
0x14000654a  lea     eax, [r9-61h]
0x14000654e  cmovnb  r8d, ecx
0x140006552  lea     edx, [r9-20h]
0x140006556  cmp     eax, 1Ah
0x140006559  cmovnb  edx, r9d
0x14000655d  cmp     r8d, edx
0x140006560  jnz     short loc_14000658C
0x140006562  inc     rdi
0x140006565  lea     rdx, aPid; "/pid"
0x14000656c  cmp     rdi, 4
0x140006570  jnz     short loc_140006536
0x140006572  mov     rdi, [rsp+68h+arg_8]
0x140006577  lea     eax, [r15-1]
0x14000657b  cmp     r14d, eax
0x14000657e  jge     loc_140006869
0x140006584  mov     r8, r13
0x140006587  jmp     loc_140006675
0x14000658c  mov     rdi, [rsp+68h+arg_8]
0x140006591  lea     rcx, aTid; "/tid"
0x140006598  xor     eax, eax
0x14000659a  lea     rdx, aType; "/type"
0x1400065a1  lea     r8, aEncfile; "/encfile"
0x1400065a8  lea     r9, aCancel; "/cancel"
0x1400065af  cmp     r10, 4
0x1400065b3  jnz     short loc_140006611
0x1400065b5  cmp     r11, rcx
0x1400065b8  jz      short loc_1400065FA
0x1400065ba  mov     r9d, eax
0x1400065bd  movzx   ecx, word ptr [rcx+r9*2]
0x1400065c2  movzx   r8d, word ptr [r11+r9*2]
0x1400065c7  lea     eax, [rcx-61h]
0x1400065ca  cmp     eax, 1Ah
0x1400065cd  lea     edx, [rcx-20h]
0x1400065d0  lea     eax, [r8-61h]
0x1400065d4  cmovnb  edx, ecx
0x1400065d7  cmp     eax, 1Ah
0x1400065da  lea     ecx, [r8-20h]
0x1400065de  cmovnb  ecx, r8d
0x1400065e2  cmp     ecx, edx
0x1400065e4  jnz     loc_14000680A
0x1400065ea  inc     r9
0x1400065ed  lea     rcx, aTid; "/tid"
0x1400065f4  cmp     r9, 4
0x1400065f8  jnz     short loc_1400065BD
0x1400065fa  lea     eax, [r15-1]
0x1400065fe  cmp     r14d, eax
0x140006601  jge     loc_14000689B
0x140006607  mov     r8, [rsp+68h+arg_18]
0x14000660f  jmp     short loc_140006675
0x140006611  cmp     r10, 5
0x140006615  jnz     loc_1400066EB
0x14000661b  cmp     r11, rdx
0x14000661e  jz      short loc_140006660
0x140006620  mov     r9, rax
0x140006623  movzx   ecx, word ptr [rdx+r9*2]
0x140006628  movzx   r8d, word ptr [r11+r9*2]
0x14000662d  lea     eax, [rcx-61h]
0x140006630  cmp     eax, 1Ah
0x140006633  lea     edx, [rcx-20h]
0x140006636  lea     eax, [r8-61h]
0x14000663a  cmovnb  edx, ecx
0x14000663d  cmp     eax, 1Ah
0x140006640  lea     ecx, [r8-20h]
0x140006644  cmovnb  ecx, r8d
0x140006648  cmp     ecx, edx
0x14000664a  jnz     loc_14000680A
0x140006650  inc     r9
0x140006653  lea     rdx, aType; "/type"
0x14000665a  cmp     r9, 5
0x14000665e  jnz     short loc_140006623
0x140006660  lea     eax, [r15-1]
0x140006664  cmp     r14d, eax
0x140006667  jge     loc_1400068A2
0x14000666d  mov     r8, [rsp+68h+piRet]; piRet
0x140006675  mov     rcx, [rdi+r12*8+8]; pszString
0x14000667a  xor     edx, edx; dwFlags
0x14000667c  call    cs:__imp_StrToIntExW
0x140006682  test    eax, eax
0x140006684  jnz     loc_14000680A
0x14000668a  mov     rax, [rsp+68h+arg_18]
0x140006692  mov     dword ptr [rax], 0
0x140006698  mov     dword ptr [r13+0], 0
0x1400066a0  mov     rcx, [rsi]; hObject
0x1400066a3  mov     qword ptr [rsi], 0
0x1400066aa  lea     rax, [rcx+1]
0x1400066ae  cmp     rax, 1
0x1400066b2  jbe     short loc_1400066BA
0x1400066b4  call    cs:__imp_CloseHandle
0x1400066ba  mov     rcx, [rbx]; hObject
0x1400066bd  mov     qword ptr [rbx], 0
0x1400066c4  lea     rdx, [rcx+1]
0x1400066c8  cmp     rdx, 1
0x1400066cc  jbe     short loc_1400066D4
0x1400066ce  call    cs:__imp_CloseHandle
0x1400066d4  mov     rbx, [rsp+68h+arg_0]
0x1400066d9  mov     eax, ebp
0x1400066db  add     rsp, 30h
0x1400066df  pop     r15
0x1400066e1  pop     r14
0x1400066e3  pop     r13
0x1400066e5  pop     r12
0x1400066e7  pop     rdi
0x1400066e8  pop     rsi
0x1400066e9  pop     rbp
0x1400066ea  retn
0x1400066eb  cmp     r10, 8
0x1400066ef  jnz     loc_140006777
0x1400066f5  cmp     r11, r8
0x1400066f8  jz      short loc_14000673A
0x1400066fa  mov     r9, rax
0x1400066fd  lea     r10, aEncfile; "/encfile"
0x140006704  movzx   ecx, word ptr [r10+r9*2]
0x140006709  movzx   r8d, word ptr [r11+r9*2]
0x14000670e  lea     eax, [rcx-61h]
0x140006711  cmp     eax, 1Ah
0x140006714  lea     edx, [rcx-20h]
0x140006717  lea     eax, [r8-61h]
0x14000671b  cmovnb  edx, ecx
0x14000671e  cmp     eax, 1Ah
0x140006721  lea     ecx, [r8-20h]
0x140006725  cmovnb  ecx, r8d
0x140006729  cmp     ecx, edx
0x14000672b  jnz     loc_14000680A
0x140006731  inc     r9
0x140006734  cmp     r9, 8
0x140006738  jnz     short loc_140006704
0x14000673a  lea     eax, [r15-1]
0x14000673e  cmp     r14d, eax
0x140006741  jge     loc_1400068A9
0x140006747  mov     rcx, [rdi+r12*8+8]; pszString
0x14000674c  lea     r8, [rsp+68h+pllRet]; pllRet
0x140006754  xor     edx, edx; dwFlags
0x140006756  call    cs:__imp_StrToInt64ExW
0x14000675c  test    eax, eax
0x14000675e  jz      loc_14000668A
0x140006764  mov     rax, [rsp+68h+pllRet]
0x14000676c  mov     rcx, [rsi]
0x14000676f  mov     [rsi], rax
0x140006772  jmp     loc_1400067FA
0x140006777  cmp     r10, 7
0x14000677b  jnz     loc_14000680A
0x140006781  cmp     r11, r9
0x140006784  jz      short loc_1400067C2
0x140006786  mov     r9, rax
0x140006789  lea     r10, aCancel; "/cancel"
0x140006790  movzx   ecx, word ptr [r10+r9*2]
0x140006795  movzx   r8d, word ptr [r11+r9*2]
0x14000679a  lea     eax, [rcx-61h]
0x14000679d  cmp     eax, 1Ah
0x1400067a0  lea     edx, [rcx-20h]
0x1400067a3  lea     eax, [r8-61h]
0x1400067a7  cmovnb  edx, ecx
0x1400067aa  cmp     eax, 1Ah
0x1400067ad  lea     ecx, [r8-20h]
0x1400067b1  cmovnb  ecx, r8d
0x1400067b5  cmp     ecx, edx
0x1400067b7  jnz     short loc_14000680A
0x1400067b9  inc     r9
0x1400067bc  cmp     r9, 7
0x1400067c0  jnz     short loc_140006790
0x1400067c2  lea     eax, [r15-1]
0x1400067c6  cmp     r14d, eax
0x1400067c9  jge     loc_1400068B0
0x1400067cf  mov     rcx, [rdi+r12*8+8]; pszString
0x1400067d4  lea     r8, [rsp+68h+pllRet]; pllRet
0x1400067dc  xor     edx, edx; dwFlags
0x1400067de  call    cs:__imp_StrToInt64ExW
0x1400067e4  test    eax, eax
0x1400067e6  jz      loc_14000668A
0x1400067ec  mov     rax, [rsp+68h+pllRet]
0x1400067f4  mov     rcx, [rbx]; hObject
0x1400067f7  mov     [rbx], rax
0x1400067fa  lea     rax, [rcx+1]
0x1400067fe  cmp     rax, 1
0x140006802  jbe     short loc_14000680A
0x140006804  call    cs:__imp_CloseHandle
0x14000680a  inc     r14d
0x14000680d  xor     eax, eax
0x14000680f  cmp     r14d, r15d
0x140006812  jl      loc_1400064EC
0x140006818  mov     r12, [rsp+68h+piRet]
0x140006820  cmp     [r13+0], eax
0x140006824  jz      loc_14000668A
0x14000682a  cmp     [r12], eax
0x14000682e  jz      loc_14000668A
0x140006834  mov     rax, [rbx]
0x140006837  inc     rax
0x14000683a  cmp     rax, 1
0x14000683e  jbe     loc_14000668A
0x140006844  mov     rax, [rsi]
0x140006847  inc     rax
0x14000684a  cmp     rax, 1
0x14000684e  jbe     loc_14000668A
0x140006854  test    dword ptr [r12], 0FA000000h
0x14000685c  jnz     loc_14000668A
0x140006862  xor     ebp, ebp
0x140006864  jmp     loc_1400066D4
0x140006869  mov     edx, 55h ; 'U'; void *
0x14000686e  mov     rcx, [rsp+68h]; this
0x140006873  lea     rax, aIllegalCommand; "Illegal command line"
0x14000687a  mov     qword ptr [rsp+68h+var_40], rax; int
0x14000687f  lea     r9, aParsesecurehan; "ParseSecureHangrepCommandLineArguments"
0x140006886  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\werfa"...
0x14000688d  mov     dword ptr [rsp+68h+var_48], ebp; wil::details *
0x140006891  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140006896  jmp     loc_14000668A
0x14000689b  mov     edx, 64h ; 'd'
0x1400068a0  jmp     short loc_14000686E
0x1400068a2  mov     edx, 73h ; 's'
0x1400068a7  jmp     short loc_14000686E
0x1400068a9  mov     edx, 83h
0x1400068ae  jmp     short loc_14000686E
0x1400068b0  mov     edx, 93h
0x1400068b5  jmp     short loc_14000686E
```
