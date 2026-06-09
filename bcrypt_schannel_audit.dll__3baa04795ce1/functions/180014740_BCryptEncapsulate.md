# BCryptEncapsulate

- ea: `0x180014740`
- end: `0x180014980`
- name: `BCryptEncapsulate`
- size: `576`
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
- `0x180014740`
- `0x180015684`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001488a`
- `ntdll!RtlDllShutdownInProgress` at `0x18001488a`

## string_xrefs

- `0x1800147f5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptEncapsulate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8)
{
  unsigned int v9; // r14d
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  char TrustedEnvironment; // al
  __int64 v20; // r8
  int v21; // r9d
  int v22; // r8d
  int v23; // r10d
  unsigned int v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  __int64 *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  unsigned int *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  char v38[16]; // [rsp+E0h] [rbp-20h] BYREF
  char v39[16]; // [rsp+F0h] [rbp-10h] BYREF

  v9 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqDqqDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3, a4, a5, a6, a7, a8);
  v12 = ValidateBaseKeyHandle(a1);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 0;
    v15 = -1073741816;
    v16 = 3221225480LL;
LABEL_6:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    goto LABEL_12;
  }
  v17 = *(_QWORD *)(v12 + 8);
  v14 = v17 + 444;
  if ( *(_DWORD *)(v17 + 36) != 8 )
  {
    v15 = -1073741637;
    v16 = 3221225659LL;
    goto LABEL_6;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64, int, __int64, int))(v17 + 104))(
          *(_QWORD *)(v13 + 16),
          a2,
          v9,
          a4,
          a5,
          a6,
          a7,
          a8);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = (unsigned int)v18;
    goto LABEL_6;
  }
  v15 = 0;
LABEL_12:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x400000000000LL, v20, 0) )
  {
    v27 = 1;
    v30 = &v27;
    v31 = (unsigned int)(v21 + 8);
    v32 = &v28;
    v28 = 0x1000000;
    v34 = &v25;
    v33 = v31;
    v36 = &v26;
    v25 = v15;
    v35 = 4;
    v26 = v21;
    v37 = 4;
    tlgCreate1Sz_wchar_t(v38, g_processImageName);
    tlgCreate1Sz_wchar_t(v39, v14);
    tlgWriteAgg((unsigned int)v29, (unsigned int)byte_18001F6A9, v22, v23, (__int64)v29);
  }
  return v15;
}

```

## disassembly

```asm
0x180014740  push    rbp
0x180014742  push    rbx
0x180014743  push    rsi
0x180014744  push    rdi
0x180014745  push    r12
0x180014747  push    r13
0x180014749  push    r14
0x18001474b  push    r15
0x18001474d  lea     rbp, [rsp-18h]
0x180014752  sub     rsp, 118h
0x180014759  mov     rax, cs:__security_cookie
0x180014760  xor     rax, rsp
0x180014763  mov     [rbp+50h+var_50], rax
0x180014767  mov     r12, [rbp+50h+arg_20]
0x18001476e  mov     r15, r9
0x180014771  mov     r13, [rbp+50h+arg_30]
0x180014778  mov     r14d, r8d
0x18001477b  mov     rsi, rdx
0x18001477e  mov     rbx, rcx
0x180014781  mov     rcx, cs:WPP_GLOBAL_Control
0x180014788  lea     rax, WPP_GLOBAL_Control
0x18001478f  cmp     rcx, rax
0x180014792  jz      short loc_1800147D3
0x180014794  test    byte ptr [rcx+1Ch], 4
0x180014798  jz      short loc_1800147D3
0x18001479a  mov     eax, [rbp+50h+arg_38]
0x1800147a0  mov     rcx, [rcx+10h]
0x1800147a4  mov     [rsp+150h+var_100], eax
0x1800147a8  mov     eax, [rbp+50h+arg_28]
0x1800147ae  mov     [rsp+150h+var_108], r13
0x1800147b3  mov     [rsp+150h+var_110], eax
0x1800147b7  mov     [rsp+150h+var_118], r12
0x1800147bc  mov     [rsp+150h+var_120], r9
0x1800147c1  mov     r9, rbx
0x1800147c4  mov     [rsp+150h+var_128], r8d
0x1800147c9  mov     [rsp+150h+var_130], rdx
0x1800147ce  call    WPP_SF_qqDqqDqD
0x1800147d3  mov     rcx, rbx
0x1800147d6  call    ValidateBaseKeyHandle
0x1800147db  mov     rcx, rax
0x1800147de  test    rax, rax
0x1800147e1  jnz     short loc_18001480A
0x1800147e3  xor     edi, edi
0x1800147e5  mov     ebx, 0C0000008h
0x1800147ea  mov     r9d, 1E7Fh
0x1800147f0  mov     ecx, 0C0000008h
0x1800147f5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800147fc  lea     rdx, aStatus; "Status"
0x180014803  call    DebugTraceError
0x180014808  jmp     short loc_180014873
0x18001480a  mov     rax, [rax+8]
0x18001480e  cmp     dword ptr [rax+24h], 8
0x180014812  lea     rdi, [rax+1BCh]
0x180014819  jz      short loc_18001482D
0x18001481b  mov     ebx, 0C00000BBh
0x180014820  mov     r9d, 1E89h
0x180014826  mov     ecx, 0C00000BBh
0x18001482b  jmp     short loc_1800147F5
0x18001482d  mov     edx, [rbp+50h+arg_38]
0x180014833  mov     r9, r15
0x180014836  mov     rcx, [rcx+10h]
0x18001483a  mov     r8d, r14d
0x18001483d  mov     rax, [rax+68h]
0x180014841  mov     dword ptr [rsp+150h+var_118], edx
0x180014845  mov     edx, [rbp+50h+arg_28]
0x18001484b  mov     [rsp+150h+var_120], r13
0x180014850  mov     [rsp+150h+var_128], edx
0x180014854  mov     rdx, rsi
0x180014857  mov     [rsp+150h+var_130], r12
0x18001485c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014861  mov     ebx, eax
0x180014863  test    eax, eax
0x180014865  jns     short loc_180014871
0x180014867  mov     r9d, 1E99h
0x18001486d  mov     ecx, eax
0x18001486f  jmp     short loc_1800147F5
0x180014871  xor     ebx, ebx
0x180014873  mov     eax, cs:g_TrustedEnvironment
0x180014879  test    eax, eax
0x18001487b  jnz     short loc_180014882
0x18001487d  call    GetTrustedEnvironment
0x180014882  test    al, 1
0x180014884  jz      loc_18001495D
0x18001488a  call    cs:__imp_RtlDllShutdownInProgress
0x180014891  nop     dword ptr [rax+rax+00h]
0x180014896  xor     r9d, r9d
0x180014899  test    al, al
0x18001489b  jnz     loc_18001495D
0x1800148a1  mov     eax, cs:dword_180024050
0x1800148a7  cmp     eax, 5
0x1800148aa  jbe     loc_18001495D
0x1800148b0  mov     rdx, 400000000000h
0x1800148ba  lea     rcx, dword_180024050
0x1800148c1  call    _tlgKeywordOn
0x1800148c6  test    al, al
0x1800148c8  jz      loc_18001495D
0x1800148ce  lea     rax, [rsp+150h+var_E8]
0x1800148d3  mov     [rsp+150h+var_E8], 1
0x1800148dc  mov     [rbp+50h+var_B0], rax
0x1800148e0  lea     r10d, [r9+8]
0x1800148e4  lea     rax, [rsp+150h+var_E0]
0x1800148e9  mov     [rbp+50h+var_A8], r10
0x1800148ed  mov     [rbp+50h+var_A0], rax
0x1800148f1  lea     rdx, g_processImageName; "UNKNOWN"
0x1800148f8  lea     rax, [rsp+150h+var_F0]
0x1800148fd  mov     [rsp+150h+var_E0], 1000000h
0x180014906  mov     [rbp+50h+var_90], rax
0x18001490a  lea     rcx, [rbp+50h+var_70]
0x18001490e  lea     rax, [rsp+150h+var_EC]
0x180014913  mov     [rbp+50h+var_98], r10
0x180014917  mov     [rbp+50h+var_80], rax
0x18001491b  mov     [rsp+150h+var_F0], ebx
0x18001491f  mov     [rbp+50h+var_88], 4
0x180014927  mov     [rsp+150h+var_EC], r9d
0x18001492c  mov     [rbp+50h+var_78], 4
0x180014934  call    _tlgCreate1Sz_wchar_t
0x180014939  mov     rdx, rdi
0x18001493c  lea     rcx, [rbp+50h+var_60]
0x180014940  call    _tlgCreate1Sz_wchar_t
0x180014945  lea     rcx, [rbp+50h+var_D0]
0x180014949  mov     r9d, r10d
0x18001494c  lea     rdx, byte_18001F6A9
0x180014953  mov     [rsp+150h+var_130], rcx
0x180014958  call    _tlgWriteAgg
0x18001495d  mov     eax, ebx
0x18001495f  mov     rcx, [rbp+50h+var_50]
0x180014963  xor     rcx, rsp; StackCookie
0x180014966  call    __security_check_cookie
0x18001496b  add     rsp, 118h
0x180014972  pop     r15
0x180014974  pop     r14
0x180014976  pop     r13
0x180014978  pop     r12
0x18001497a  pop     rdi
0x18001497b  pop     rsi
0x18001497c  pop     rbx
0x18001497d  pop     rbp
0x18001497e  retn
```
