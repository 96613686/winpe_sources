# BCryptDecapsulate

- ea: `0x180014510`
- end: `0x180014734`
- name: `BCryptDecapsulate`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005060`
- `0x180009740`
- `0x18000b094`
- `0x18000e150`
- `0x180010ed4`
- `0x180010f80`
- `0x180014510`
- `0x1800155e4`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001463d`
- `ntdll!RtlDllShutdownInProgress` at `0x18001463d`

## string_xrefs

- `0x1800145b5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptDecapsulate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7)
{
  unsigned int v8; // r14d
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  char TrustedEnvironment; // al
  __int64 v19; // r8
  int v20; // r9d
  int v21; // r8d
  int v22; // r10d
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  unsigned int *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char v37[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v38[16]; // [rsp+E0h] [rbp-20h] BYREF

  v8 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqDqDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3, a4, a5, a6, a7);
  v11 = ValidateBaseKeyHandle(a1);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
    v14 = -1073741816;
    v15 = 3221225480LL;
LABEL_6:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    goto LABEL_12;
  }
  v16 = *(_QWORD *)(v11 + 8);
  v13 = v16 + 444;
  if ( *(_DWORD *)(v16 + 36) != 8 )
  {
    v14 = -1073741637;
    v15 = 3221225659LL;
    goto LABEL_6;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, __int64, int))(v16 + 112))(
          *(_QWORD *)(v12 + 16),
          a2,
          v8,
          a4,
          a5,
          a6,
          a7);
  v14 = v17;
  if ( v17 < 0 )
  {
    v15 = (unsigned int)v17;
    goto LABEL_6;
  }
  v14 = 0;
LABEL_12:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x400000000000LL, v19, 0) )
  {
    v26 = 1;
    v29 = &v26;
    v30 = (unsigned int)(v20 + 8);
    v31 = &v27;
    v27 = 0x1000000;
    v33 = &v24;
    v32 = v30;
    v35 = &v25;
    v24 = v14;
    v34 = 4;
    v25 = v20;
    v36 = 4;
    tlgCreate1Sz_wchar_t(v37, g_processImageName);
    tlgCreate1Sz_wchar_t(v38, v13);
    tlgWriteAgg((unsigned int)v28, (unsigned int)word_18001F8D2, v21, v22, (__int64)v28);
  }
  return v14;
}

```

## disassembly

```asm
0x180014510  push    rbp
0x180014512  push    rbx
0x180014513  push    rsi
0x180014514  push    rdi
0x180014515  push    r12
0x180014517  push    r13
0x180014519  push    r14
0x18001451b  push    r15
0x18001451d  lea     rbp, [rsp-8]
0x180014522  sub     rsp, 108h
0x180014529  mov     rax, cs:__security_cookie
0x180014530  xor     rax, rsp
0x180014533  mov     [rbp+40h+var_50], rax
0x180014537  mov     r12, [rbp+40h+arg_28]
0x18001453b  mov     r15, r9
0x18001453e  mov     r14d, r8d
0x180014541  mov     rsi, rdx
0x180014544  mov     rbx, rcx
0x180014547  mov     rcx, cs:WPP_GLOBAL_Control
0x18001454e  lea     rax, WPP_GLOBAL_Control
0x180014555  mov     r13d, [rbp+40h+arg_30]
0x18001455c  cmp     rcx, rax
0x18001455f  jz      short loc_180014593
0x180014561  test    byte ptr [rcx+1Ch], 4
0x180014565  jz      short loc_180014593
0x180014567  mov     eax, [rbp+40h+arg_20]
0x18001456a  mov     rcx, [rcx+10h]
0x18001456e  mov     [rsp+140h+var_F8], r13d
0x180014573  mov     [rsp+140h+var_100], r12
0x180014578  mov     [rsp+140h+var_108], eax
0x18001457c  mov     [rsp+140h+var_110], r9
0x180014581  mov     r9, rbx
0x180014584  mov     dword ptr [rsp+140h+var_118], r8d
0x180014589  mov     [rsp+140h+var_120], rdx
0x18001458e  call    WPP_SF_qqDqDqD
0x180014593  mov     rcx, rbx
0x180014596  call    ValidateBaseKeyHandle
0x18001459b  mov     rcx, rax
0x18001459e  test    rax, rax
0x1800145a1  jnz     short loc_1800145CA
0x1800145a3  xor     edi, edi
0x1800145a5  mov     ebx, 0C0000008h
0x1800145aa  mov     r9d, 1EDCh
0x1800145b0  mov     ecx, 0C0000008h
0x1800145b5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800145bc  lea     rdx, aStatus; "Status"
0x1800145c3  call    DebugTraceError
0x1800145c8  jmp     short loc_180014626
0x1800145ca  mov     rax, [rax+8]
0x1800145ce  cmp     dword ptr [rax+24h], 8
0x1800145d2  lea     rdi, [rax+1BCh]
0x1800145d9  jz      short loc_1800145ED
0x1800145db  mov     ebx, 0C00000BBh
0x1800145e0  mov     r9d, 1EE6h
0x1800145e6  mov     ecx, 0C00000BBh
0x1800145eb  jmp     short loc_1800145B5
0x1800145ed  mov     edx, [rbp+40h+arg_20]
0x1800145f0  mov     r9, r15
0x1800145f3  mov     rcx, [rcx+10h]
0x1800145f7  mov     r8d, r14d
0x1800145fa  mov     rax, [rax+70h]
0x1800145fe  mov     dword ptr [rsp+140h+var_110], r13d
0x180014603  mov     [rsp+140h+var_118], r12
0x180014608  mov     dword ptr [rsp+140h+var_120], edx
0x18001460c  mov     rdx, rsi
0x18001460f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014614  mov     ebx, eax
0x180014616  test    eax, eax
0x180014618  jns     short loc_180014624
0x18001461a  mov     r9d, 1EF5h
0x180014620  mov     ecx, eax
0x180014622  jmp     short loc_1800145B5
0x180014624  xor     ebx, ebx
0x180014626  mov     eax, cs:g_TrustedEnvironment
0x18001462c  test    eax, eax
0x18001462e  jnz     short loc_180014635
0x180014630  call    GetTrustedEnvironment
0x180014635  test    al, 1
0x180014637  jz      loc_180014711
0x18001463d  call    cs:__imp_RtlDllShutdownInProgress
0x180014644  nop     dword ptr [rax+rax+00h]
0x180014649  xor     r9d, r9d
0x18001464c  test    al, al
0x18001464e  jnz     loc_180014711
0x180014654  mov     eax, cs:dword_180024050
0x18001465a  cmp     eax, 5
0x18001465d  jbe     loc_180014711
0x180014663  mov     rdx, 400000000000h
0x18001466d  lea     rcx, dword_180024050
0x180014674  call    _tlgKeywordOn
0x180014679  test    al, al
0x18001467b  jz      loc_180014711
0x180014681  lea     rax, [rsp+140h+var_E8]
0x180014686  mov     [rsp+140h+var_E8], 1
0x18001468f  mov     [rbp+40h+var_B0], rax
0x180014693  lea     r10d, [r9+8]
0x180014697  lea     rax, [rsp+140h+var_E0]
0x18001469c  mov     [rbp+40h+var_A8], r10
0x1800146a0  mov     [rbp+40h+var_A0], rax
0x1800146a4  lea     rdx, g_processImageName; "UNKNOWN"
0x1800146ab  lea     rax, [rsp+140h+var_F0]
0x1800146b0  mov     [rsp+140h+var_E0], 1000000h
0x1800146b9  mov     [rbp+40h+var_90], rax
0x1800146bd  lea     rcx, [rbp+40h+var_70]
0x1800146c1  lea     rax, [rsp+140h+var_EC]
0x1800146c6  mov     [rbp+40h+var_98], r10
0x1800146ca  mov     [rbp+40h+var_80], rax
0x1800146ce  mov     [rsp+140h+var_F0], ebx
0x1800146d2  mov     [rbp+40h+var_88], 4
0x1800146da  mov     [rsp+140h+var_EC], r9d
0x1800146df  mov     [rbp+40h+var_78], 4
0x1800146e7  call    _tlgCreate1Sz_wchar_t
0x1800146ec  mov     rdx, rdi
0x1800146ef  lea     rcx, [rbp+40h+var_60]
0x1800146f3  call    _tlgCreate1Sz_wchar_t
0x1800146f8  lea     rcx, [rsp+140h+var_D0]
0x1800146fd  mov     r9d, r10d
0x180014700  lea     rdx, word_18001F8D2
0x180014707  mov     [rsp+140h+var_120], rcx
0x18001470c  call    _tlgWriteAgg
0x180014711  mov     eax, ebx
0x180014713  mov     rcx, [rbp+40h+var_50]
0x180014717  xor     rcx, rsp; StackCookie
0x18001471a  call    __security_check_cookie
0x18001471f  add     rsp, 108h
0x180014726  pop     r15
0x180014728  pop     r14
0x18001472a  pop     r13
0x18001472c  pop     r12
0x18001472e  pop     rdi
0x18001472f  pop     rsi
0x180014730  pop     rbx
0x180014731  pop     rbp
0x180014732  retn
```
