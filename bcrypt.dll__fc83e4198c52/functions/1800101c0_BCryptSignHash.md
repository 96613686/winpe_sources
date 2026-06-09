# BCryptSignHash

- ea: `0x1800101c0`
- end: `0x18001066f`
- name: `BCryptSignHash`
- size: `1199`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005060`
- `0x1800066f0`
- `0x180009740`
- `0x18000b094`
- `0x18000cae4`
- `0x18000dc28`
- `0x18000e150`
- `0x18000f8f8`
- `0x1800101c0`
- `0x180010ed4`
- `0x180010f80`
- `0x180016b60`
- `0x18001b785`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001054e`
- `ntdll!RtlDllShutdownInProgress` at `0x18001054e`

## string_xrefs

- `0x180010293`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180010520`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptSignHash(
        BCRYPT_KEY_HANDLE hKey,
        void *pPaddingInfo,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  UCHAR *v8; // rdi
  __int64 v9; // rsi
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // r15
  __int64 v16; // rsi
  bool v17; // zf
  __int64 (__fastcall *v18)(_QWORD, __int64, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG); // rsi
  int Property; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  NTSTATUS v22; // r14d
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  UCHAR *v29; // rax
  char TrustedEnvironment; // al
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // r8d
  __int64 v35; // [rsp+0h] [rbp-60h] BYREF
  UCHAR v36[4]; // [rsp+60h] [rbp+0h] BYREF
  ULONG v37; // [rsp+64h] [rbp+4h] BYREF
  __int64 v38; // [rsp+68h] [rbp+8h] BYREF
  NTSTATUS v39; // [rsp+70h] [rbp+10h] BYREF
  __int64 v40; // [rsp+78h] [rbp+18h] BYREF
  __int64 v41; // [rsp+80h] [rbp+20h] BYREF
  ULONG v42; // [rsp+88h] [rbp+28h] BYREF
  _BYTE v43[32]; // [rsp+90h] [rbp+30h] BYREF
  __int64 *v44; // [rsp+B0h] [rbp+50h]
  __int64 v45; // [rsp+B8h] [rbp+58h]
  __int64 *v46; // [rsp+C0h] [rbp+60h]
  __int64 v47; // [rsp+C8h] [rbp+68h]
  NTSTATUS *v48; // [rsp+D0h] [rbp+70h]
  __int64 v49; // [rsp+D8h] [rbp+78h]
  ULONG *v50; // [rsp+E0h] [rbp+80h]
  __int64 v51; // [rsp+E8h] [rbp+88h]
  char v52[16]; // [rsp+F0h] [rbp+90h] BYREF
  char v53[16]; // [rsp+100h] [rbp+A0h] BYREF

  v8 = 0;
  v40 = (__int64)pbInput;
  v9 = 0;
  *(_DWORD *)v36 = 0;
  v42 = 0;
  v37 = cbInput;
  v41 = (__int64)pPaddingInfo;
  v39 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      cbOutput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
  if ( !pcbResult )
  {
    v11 = -1073741811;
    v12 = 6642;
    v13 = 3221225485LL;
LABEL_6:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    goto LABEL_46;
  }
  v14 = ValidateBaseKeyHandle(hKey);
  v15 = (_QWORD *)v14;
  if ( !v14 )
  {
    v11 = -1073741816;
    v12 = 6650;
    v13 = 3221225480LL;
    goto LABEL_6;
  }
  v16 = *(_QWORD *)(v14 + 8);
  v17 = *(_DWORD *)(v16 + 36) == 5;
  v38 = v16 + 444;
  if ( v17 )
  {
    v18 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 104);
LABEL_11:
    Property = v18(v15[2], v41, v40, v37, pbOutput, cbOutput, pcbResult, dwFlags);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6783;
LABEL_16:
      v21 = (unsigned int)Property;
LABEL_44:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
      goto LABEL_45;
    }
    goto LABEL_42;
  }
  if ( *(_DWORD *)(v16 + 36) != 3 )
  {
    v11 = -1073741637;
    v20 = 6705;
    v21 = 3221225659LL;
    goto LABEL_44;
  }
  Property = ShouldRouterPadSignature(*(unsigned int *)(v16 + 440), dwFlags, &v39);
  v11 = Property;
  if ( Property < 0 )
  {
    v20 = 6678;
    goto LABEL_16;
  }
  v22 = v39;
  if ( v39 )
  {
    Property = BCryptGetProperty(v15, L"KeyStrength", v36, 4u, &v42, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6693;
      goto LABEL_16;
    }
    *(_DWORD *)v36 = (unsigned int)(*(_DWORD *)v36 + 7) >> 3;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, PUCHAR, ULONG, ULONG *, ULONG))(v16 + 144);
  if ( !v22 )
    goto LABEL_11;
  if ( !pbOutput )
  {
    Property = v18(v15[2], 0, v40, v37, 0, cbOutput, pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6724;
      goto LABEL_16;
    }
    goto LABEL_42;
  }
  v23 = *(unsigned int *)v36;
  if ( !*(_DWORD *)v36 )
    goto LABEL_59;
  if ( *(unsigned int *)v36 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_59;
  v24 = *(unsigned int *)v36 + g_ulAdditionalProbeSize + 8;
  if ( v24 < *(unsigned int *)v36 || !(unsigned int)VerifyStackAvailable(v24) )
    goto LABEL_59;
  v25 = v23 + 23;
  if ( v23 + 23 <= v23 + 8 )
    v25 = 0xFFFFFFFFFFFFFF0LL;
  v26 = v25 & 0xFFFFFFFFFFFFFFF0uLL;
  v27 = alloca(v26);
  v28 = alloca(v26);
  v8 = v36;
  if ( &v35 == (__int64 *)-96LL || (*(_DWORD *)v36 = 1801679955, (v8 = (UCHAR *)&v38) == 0) )
  {
LABEL_59:
    if ( v23 + 8 >= v23 )
    {
      v29 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v8 = v29;
      if ( v29 )
      {
        *(_DWORD *)v29 = 1885431112;
        v8 = v29 + 8;
      }
    }
  }
  if ( v8 )
  {
    Property = ApplySignaturePadding(dwFlags, (_QWORD *)v41, (const void *)v40, v37, v8, *(unsigned int *)v36);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6752;
      goto LABEL_16;
    }
    Property = v18(v15[2], 0, (__int64)v8, *(unsigned int *)v36, pbOutput, cbOutput, pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v20 = 6766;
      goto LABEL_16;
    }
LABEL_42:
    v11 = 0;
    goto LABEL_45;
  }
  v11 = -1073741801;
LABEL_45:
  v9 = v38;
LABEL_46:
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x400000000000LL, v31, v32) )
  {
    v41 = 1;
    v44 = &v41;
    v45 = 8;
    v46 = &v40;
    v40 = 0x1000000;
    v48 = &v39;
    v50 = &v37;
    v47 = 8;
    v39 = v11;
    v49 = 4;
    v37 = 0;
    v51 = 4;
    tlgCreate1Sz_wchar_t(v52, g_processImageName);
    tlgCreate1Sz_wchar_t(v53, v9);
    tlgWriteAgg((unsigned int)v43, (unsigned int)&dword_18001F75C, v33, 8, (__int64)v43);
  }
  if ( v8 && *((_DWORD *)v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v11;
}

```

## disassembly

```asm
0x1800101c0  push    rbp
0x1800101c2  push    rbx
0x1800101c3  push    rsi
0x1800101c4  push    rdi
0x1800101c5  push    r12
0x1800101c7  push    r13
0x1800101c9  push    r14
0x1800101cb  push    r15
0x1800101cd  sub     rsp, 128h
0x1800101d4  lea     rbp, [rsp+60h]
0x1800101d9  mov     rax, cs:__security_cookie
0x1800101e0  xor     rax, rbp
0x1800101e3  mov     [rbp+100h+var_50], rax
0x1800101ea  mov     r13, [rbp+100h+pbOutput]
0x1800101f1  xor     edi, edi
0x1800101f3  mov     r12, [rbp+100h+pcbResult]
0x1800101fa  mov     rax, r8
0x1800101fd  mov     [rbp+100h+var_E8], rax
0x180010201  xor     esi, esi
0x180010203  mov     dword ptr [rbp+100h+var_100], edi
0x180010206  mov     r10, rdx
0x180010209  mov     [rbp+100h+var_D8], edi
0x18001020c  mov     rbx, rcx
0x18001020f  mov     [rbp+100h+var_FC], r9d
0x180010213  mov     [rbp+100h+var_E0], rdx
0x180010217  mov     [rbp+100h+var_F0], 0
0x18001021e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010225  lea     rdx, WPP_GLOBAL_Control
0x18001022c  mov     r14d, [rbp+100h+dwFlags]
0x180010233  cmp     rcx, rdx
0x180010236  jz      short loc_180010277
0x180010238  test    byte ptr [rcx+1Ch], 4
0x18001023c  jz      short loc_180010277
0x18001023e  mov     r8d, [rbp+100h+cbOutput]
0x180010245  lea     edx, [rdi+26h]
0x180010248  mov     rcx, [rcx+10h]
0x18001024c  mov     [rsp+160h+var_110], r14d
0x180010251  mov     [rsp+160h+var_118], r12
0x180010256  mov     [rsp+160h+var_120], r8d
0x18001025b  mov     [rsp+160h+var_128], r13
0x180010260  mov     dword ptr [rsp+160h+var_130], r9d
0x180010265  mov     r9, rbx
0x180010268  mov     qword ptr [rsp+160h+var_138], rax
0x18001026d  mov     [rsp+160h+var_140], r10
0x180010272  call    WPP_SF_qqqdqdqD
0x180010277  test    r12, r12
0x18001027a  jnz     short loc_1800102A4
0x18001027c  mov     ebx, 0C000000Dh
0x180010281  mov     r9d, 19F2h
0x180010287  mov     ecx, 0C000000Dh
0x18001028c  lea     rdx, aStatus; "Status"
0x180010293  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001029a  call    DebugTraceError
0x18001029f  jmp     loc_180010537
0x1800102a4  mov     rcx, rbx
0x1800102a7  call    ValidateBaseKeyHandle
0x1800102ac  mov     r15, rax
0x1800102af  test    rax, rax
0x1800102b2  jnz     short loc_1800102C6
0x1800102b4  mov     ebx, 0C0000008h
0x1800102b9  mov     r9d, 19FAh
0x1800102bf  mov     ecx, 0C0000008h
0x1800102c4  jmp     short loc_18001028C
0x1800102c6  mov     rsi, [rax+8]
0x1800102ca  cmp     dword ptr [rsi+24h], 5
0x1800102ce  lea     rax, [rsi+1BCh]
0x1800102d5  mov     [rbp+100h+var_F8], rax
0x1800102d9  jnz     short loc_180010327
0x1800102db  mov     rsi, [rsi+68h]
0x1800102df  mov     eax, [rbp+100h+dwFlags]
0x1800102e5  mov     r9d, [rbp+100h+var_FC]
0x1800102e9  mov     r8, [rbp+100h+var_E8]
0x1800102ed  mov     rdx, [rbp+100h+var_E0]
0x1800102f1  mov     rcx, [r15+10h]
0x1800102f5  mov     dword ptr [rsp+160h+var_128], eax
0x1800102f9  mov     eax, [rbp+100h+cbOutput]
0x1800102ff  mov     [rsp+160h+var_130], r12
0x180010304  mov     [rsp+160h+var_138], eax
0x180010308  mov     rax, rsi
0x18001030b  mov     [rsp+160h+var_140], r13
0x180010310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010315  mov     ebx, eax
0x180010317  test    eax, eax
0x180010319  jns     loc_18001050C
0x18001031f  mov     r9d, 1A7Fh
0x180010325  jmp     short loc_18001034F
0x180010327  cmp     dword ptr [rsi+24h], 3
0x18001032b  jnz     loc_180010510
0x180010331  mov     ecx, [rsi+1B8h]
0x180010337  lea     r8, [rbp+100h+var_F0]
0x18001033b  mov     edx, r14d
0x18001033e  call    ShouldRouterPadSignature
0x180010343  mov     ebx, eax
0x180010345  test    eax, eax
0x180010347  jns     short loc_180010356
0x180010349  mov     r9d, 1A16h
0x18001034f  mov     ecx, eax
0x180010351  jmp     loc_180010520
0x180010356  mov     r14d, [rbp+100h+var_F0]
0x18001035a  test    r14d, r14d
0x18001035d  jz      short loc_18001039F
0x18001035f  lea     rax, [rbp+100h+var_D8]
0x180010363  mov     [rsp+160h+var_138], edi; dwFlags
0x180010367  mov     r9d, 4; cbOutput
0x18001036d  mov     [rsp+160h+var_140], rax; pcbResult
0x180010372  lea     r8, [rbp+100h+var_100]; pbOutput
0x180010376  mov     rcx, r15; hObject
0x180010379  lea     rdx, pszProperty; "KeyStrength"
0x180010380  call    BCryptGetProperty
0x180010385  mov     ebx, eax
0x180010387  test    eax, eax
0x180010389  jns     short loc_180010393
0x18001038b  mov     r9d, 1A25h
0x180010391  jmp     short loc_18001034F
0x180010393  mov     eax, dword ptr [rbp+100h+var_100]
0x180010396  add     eax, 7
0x180010399  shr     eax, 3
0x18001039c  mov     dword ptr [rbp+100h+var_100], eax
0x18001039f  mov     rsi, [rsi+90h]
0x1800103a6  test    r14d, r14d
0x1800103a9  jz      loc_1800102DF
0x1800103af  test    r13, r13
0x1800103b2  jnz     short loc_1800103F7
0x1800103b4  mov     eax, [rbp+100h+cbOutput]
0x1800103ba  xor     edx, edx
0x1800103bc  mov     r9d, [rbp+100h+var_FC]
0x1800103c0  mov     r8, [rbp+100h+var_E8]
0x1800103c4  mov     rcx, [r15+10h]
0x1800103c8  mov     dword ptr [rsp+160h+var_128], edi
0x1800103cc  mov     [rsp+160h+var_130], r12
0x1800103d1  mov     [rsp+160h+var_138], eax
0x1800103d5  mov     rax, rsi
0x1800103d8  mov     [rsp+160h+var_140], rdi
0x1800103dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e2  mov     ebx, eax
0x1800103e4  test    eax, eax
0x1800103e6  jns     loc_18001050C
0x1800103ec  mov     r9d, 1A44h
0x1800103f2  jmp     loc_18001034F
0x1800103f7  mov     ebx, dword ptr [rbp+100h+var_100]
0x1800103fa  test    rbx, rbx
0x1800103fd  jz      short loc_180010460
0x1800103ff  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180010406  ja      short loc_180010460
0x180010408  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001040f  add     rcx, 8
0x180010413  add     rcx, rbx
0x180010416  cmp     rcx, rbx
0x180010419  jb      short loc_180010460
0x18001041b  call    VerifyStackAvailable
0x180010420  test    eax, eax
0x180010422  jz      short loc_180010460
0x180010424  lea     rax, [rbx+8]
0x180010428  lea     rcx, [rax+0Fh]
0x18001042c  cmp     rcx, rax
0x18001042f  ja      short loc_18001043B
0x180010431  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001043b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001043f  mov     rax, rcx
0x180010442  call    __chkstk_0
0x180010447  sub     rsp, rcx
0x18001044a  lea     rdi, [rsp+160h+var_100]
0x18001044f  test    rdi, rdi
0x180010452  jz      short loc_180010460
0x180010454  mov     dword ptr [rdi], 6B637453h
0x18001045a  add     rdi, 8
0x18001045e  jnz     short loc_180010487
0x180010460  lea     rcx, [rbx+8]
0x180010464  cmp     rcx, rbx
0x180010467  jb      short loc_180010487
0x180010469  mov     rax, cs:g_pfnAllocate
0x180010470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010475  mov     rdi, rax
0x180010478  test    rax, rax
0x18001047b  jz      short loc_180010487
0x18001047d  mov     dword ptr [rax], 70616548h
0x180010483  add     rdi, 8
0x180010487  test    rdi, rdi
0x18001048a  jnz     short loc_180010496
0x18001048c  mov     ebx, 0C0000017h
0x180010491  jmp     loc_180010533
0x180010496  mov     eax, dword ptr [rbp+100h+var_100]
0x180010499  mov     r9d, [rbp+100h+var_FC]
0x18001049d  mov     r8, [rbp+100h+var_E8]
0x1800104a1  mov     rdx, [rbp+100h+var_E0]
0x1800104a5  mov     ecx, [rbp+100h+dwFlags]
0x1800104ab  mov     [rsp+160h+var_138], eax
0x1800104af  mov     [rsp+160h+var_140], rdi
0x1800104b4  call    ApplySignaturePadding
0x1800104b9  mov     ebx, eax
0x1800104bb  test    eax, eax
0x1800104bd  jns     short loc_1800104CA
0x1800104bf  mov     r9d, 1A60h
0x1800104c5  jmp     loc_18001034F
0x1800104ca  mov     eax, [rbp+100h+cbOutput]
0x1800104d0  mov     r8, rdi
0x1800104d3  mov     r9d, dword ptr [rbp+100h+var_100]
0x1800104d7  xor     edx, edx
0x1800104d9  mov     rcx, [r15+10h]
0x1800104dd  mov     dword ptr [rsp+160h+var_128], 0
0x1800104e5  mov     [rsp+160h+var_130], r12
0x1800104ea  mov     [rsp+160h+var_138], eax
0x1800104ee  mov     rax, rsi
0x1800104f1  mov     [rsp+160h+var_140], r13
0x1800104f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104fb  mov     ebx, eax
0x1800104fd  test    eax, eax
0x1800104ff  jns     short loc_18001050C
0x180010501  mov     r9d, 1A6Eh
0x180010507  jmp     loc_18001034F
0x18001050c  xor     ebx, ebx
0x18001050e  jmp     short loc_180010533
0x180010510  mov     ebx, 0C00000BBh
0x180010515  mov     r9d, 1A31h
0x18001051b  mov     ecx, 0C00000BBh
0x180010520  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010527  lea     rdx, aStatus; "Status"
0x18001052e  call    DebugTraceError
0x180010533  mov     rsi, [rbp+100h+var_F8]
0x180010537  mov     eax, cs:g_TrustedEnvironment
0x18001053d  test    eax, eax
0x18001053f  jnz     short loc_180010546
0x180010541  call    GetTrustedEnvironment
0x180010546  test    al, 1
0x180010548  jz      loc_18001062C
0x18001054e  call    cs:__imp_RtlDllShutdownInProgress
0x180010555  nop     dword ptr [rax+rax+00h]
0x18001055a  test    al, al
0x18001055c  jnz     loc_18001062C
0x180010562  mov     eax, cs:dword_180024050
0x180010568  cmp     eax, 5
0x18001056b  jbe     loc_18001062C
0x180010571  mov     rdx, 400000000000h
0x18001057b  lea     rcx, dword_180024050
0x180010582  call    _tlgKeywordOn
0x180010587  test    al, al
0x180010589  jz      loc_18001062C
0x18001058f  lea     rax, [rbp+100h+var_E0]
0x180010593  mov     [rbp+100h+var_E0], 1
0x18001059b  mov     [rbp+100h+var_B0], rax
0x18001059f  lea     rdx, g_processImageName; "UNKNOWN"
0x1800105a6  lea     rax, [rbp+100h+var_E8]
0x1800105aa  mov     [rbp+100h+var_A8], 8
0x1800105b2  mov     [rbp+100h+var_A0], rax
0x1800105b6  lea     rcx, [rbp+100h+var_70]
0x1800105bd  lea     rax, [rbp+100h+var_F0]
0x1800105c1  mov     [rbp+100h+var_E8], 1000000h
0x1800105c9  mov     [rbp+100h+var_90], rax
0x1800105cd  lea     rax, [rbp+100h+var_FC]
0x1800105d1  mov     [rbp+100h+var_80], rax
0x1800105d8  mov     [rbp+100h+var_98], 8
0x1800105e0  mov     [rbp+100h+var_F0], ebx
0x1800105e3  mov     [rbp+100h+var_88], 4
0x1800105eb  mov     [rbp+100h+var_FC], 0
0x1800105f2  mov     [rbp+100h+var_78], 4
0x1800105fd  call    _tlgCreate1Sz_wchar_t
0x180010602  mov     rdx, rsi
0x180010605  lea     rcx, [rbp+100h+var_60]
0x18001060c  call    _tlgCreate1Sz_wchar_t
0x180010611  lea     rcx, [rbp+100h+var_D0]
0x180010615  mov     r9d, 8
0x18001061b  lea     rdx, dword_18001F75C
0x180010622  mov     [rsp+160h+var_140], rcx
0x180010627  call    _tlgWriteAgg
0x18001062c  test    rdi, rdi
0x18001062f  jz      short loc_180010649
0x180010631  lea     rcx, [rdi-8]
0x180010635  cmp     dword ptr [rcx], 70616548h
0x18001063b  jnz     short loc_180010649
0x18001063d  mov     rax, cs:g_pfnFree
0x180010644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010649  mov     eax, ebx
0x18001064b  mov     rcx, [rbp+100h+var_50]
0x180010652  xor     rcx, rbp; StackCookie
0x180010655  call    __security_check_cookie
0x18001065a  lea     rsp, [rbp+0C8h]
0x180010661  pop     r15
0x180010663  pop     r14
0x180010665  pop     r13
0x180010667  pop     r12
0x180010669  pop     rdi
0x18001066a  pop     rsi
0x18001066b  pop     rbx
0x18001066c  pop     rbp
0x18001066d  retn
```
