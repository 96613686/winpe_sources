# TpmKey20Hmac::ExportKey(TpmKey *,ushort const *,uchar *,uint,uint *,uint)

- ea: `0x18005a5a0`
- end: `0x18005a872`
- name: `?ExportKey@TpmKey20Hmac@@UEAAJPEAVTpmKey@@PEBGPEAEIPEAII@Z`
- size: `722`
- prototype: `__int64 __fastcall(TpmKey20Hmac *__hidden this, struct TpmKey *, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800133c4`
- `0x180014830`
- `0x180014a60`
- `0x1800157c0`
- `0x18002c830`
- `0x18005a5a0`
- `0x18005a880`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18005a620`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18005a620`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18005a60d`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18005a60d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a648`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a648`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005a5ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005a5ff`

## string_xrefs

- `0x18005a73c`: `Completed`
- `0x18005a7f1`: `Completed`
- `0x18005a822`: `Completed`
- `0x18005a748`: `CompletedWithWarning`
- `0x18005a7fd`: `CompletedWithWarning`
- `0x18005a831`: `CompletedWithWarning`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey20Hmac::ExportKey(
        TpmKey20Hmac *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7)
{
  struct TpmKey *v9; // rdi
  signed __int8 v11; // si
  KspFlowLogger *v12; // rbx
  DWORD TickCount; // eax
  unsigned int *v14; // r15
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // r9d
  signed __int8 v20; // r8
  const char *v21; // rdx
  int v22; // eax
  int v23; // r9d
  signed __int8 v24; // r8
  const char *v25; // rdx
  const char *v26; // rdx
  int v27; // r9d
  unsigned int v29; // [rsp+20h] [rbp-50h]
  unsigned int v30; // [rsp+20h] [rbp-50h]
  unsigned int v31; // [rsp+40h] [rbp-30h] BYREF
  char *v32; // [rsp+48h] [rbp-28h]
  int *v33; // [rsp+50h] [rbp-20h]
  _BYTE v34[24]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v36; // [rsp+B0h] [rbp+40h] BYREF
  struct TpmKey *v37; // [rsp+B8h] [rbp+48h]

  v37 = a2;
  v9 = a2;
  v11 = 1;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v34, L"TpmKey20Hmac::ExportKey", 1);
  v36 = 0;
  v12 = (TpmKey20Hmac *)((char *)this + 56);
  v32 = (char *)this + 56;
  v33 = &v36;
  if ( !byte_180109AF0 )
  {
    TickCount = GetTickCount();
    _o_srand(TickCount);
    byte_180109AF0 = 1;
  }
  if ( rand() < 327 )
  {
    *(_QWORD *)v12 = "TpmKey20Hmac::ExportKey";
    *((_QWORD *)this + 8) = "Start";
    *((_QWORD *)this + 9) = GetTickCount64();
    *((_WORD *)this + 40) = 1;
  }
  v14 = a6;
  *a6 = 0;
  if ( !*((_QWORD *)this + 12) && *((_QWORD *)this + 81) )
  {
    KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "NeedToImportBeforeExporting", 0, 0);
    *((_BYTE *)this + 81) = 0;
    v15 = TpmKey20Hmac::PerformKeyImport(this);
    v16 = v15;
    v36 = v15;
    if ( v15 < 0 )
    {
      v17 = (unsigned int)v15;
      v18 = 996;
      goto LABEL_13;
    }
    v9 = v37;
  }
  if ( !wcscmp_0(a3, L"OpaqueKeyBlob") || !wcscmp_0(a3, L"OpaqueTransport") )
  {
    v31 = 0;
    v22 = TpmKey20::ExportKey(this, v9, a3, a4, a5, &v31, a7);
    v16 = v22;
    v36 = v22;
    if ( v22 >= 0 )
    {
      *v14 = v31;
      if ( !*((_BYTE *)this + 80) )
        goto LABEL_37;
      if ( v22 )
      {
        v26 = "CompletedWithWarning";
        v27 = v22;
      }
      else
      {
        v26 = "Completed";
        v11 = 0;
        v27 = 0;
      }
      KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v26, v11, v27);
      *((_BYTE *)this + 81) = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F3,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
        (const char *)(unsigned int)v22,
        v30);
      if ( !*((_BYTE *)this + 80) )
        goto LABEL_37;
      v23 = v36;
      if ( v36 >= 0 )
      {
        if ( v36 )
        {
          v24 = 1;
          v25 = "CompletedWithWarning";
        }
        else
        {
          v23 = 0;
          v24 = 0;
          v25 = "Completed";
        }
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), v25, v24, v23);
        *((_BYTE *)this + 81) = 0;
      }
      else if ( !*((_BYTE *)this + 81) )
      {
        KspFlowLogger::LogTransition((TpmKey20Hmac *)((char *)this + 56), "FailedWithUnspecificError", 255, v36);
        *((_BYTE *)this + 81) = 1;
      }
    }
    *((_BYTE *)this + 80) = 0;
    goto LABEL_37;
  }
  v16 = -2144795643;
  v36 = -2144795643;
  v17 = 2150171653LL;
  v18 = 1002;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
    (const char *)v17,
    v29);
  if ( *((_BYTE *)this + 80) )
  {
    v19 = v36;
    if ( v36 >= 0 )
    {
      if ( v36 )
      {
        v20 = 1;
        v21 = "CompletedWithWarning";
      }
      else
      {
        v19 = 0;
        v20 = 0;
        v21 = "Completed";
      }
      KspFlowLogger::LogTransition(v12, v21, v20, v19);
      *((_BYTE *)this + 81) = 0;
    }
    else if ( !*((_BYTE *)this + 81) )
    {
      KspFlowLogger::LogTransition(v12, "FailedWithUnspecificError", 255, v36);
      *((_BYTE *)this + 81) = 1;
    }
    *((_BYTE *)this + 80) = 0;
  }
LABEL_37:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v34);
  return v16;
}

```

## disassembly

```asm
0x18005a5a0  mov     [rsp-38h+arg_10], rbx
0x18005a5a5  mov     [rsp-38h+arg_8], rdx
0x18005a5aa  push    rbp
0x18005a5ab  push    rsi
0x18005a5ac  push    rdi
0x18005a5ad  push    r12
0x18005a5af  push    r13
0x18005a5b1  push    r14
0x18005a5b3  push    r15
0x18005a5b5  mov     rbp, rsp
0x18005a5b8  sub     rsp, 70h
0x18005a5bc  mov     r13, r9
0x18005a5bf  mov     r12, r8
0x18005a5c2  mov     rdi, rdx
0x18005a5c5  mov     r14, rcx
0x18005a5c8  mov     sil, 1
0x18005a5cb  mov     r8b, sil; bool
0x18005a5ce  lea     rdx, aTpmkey20hmacEx; "TpmKey20Hmac::ExportKey"
0x18005a5d5  lea     rcx, [rbp+var_18]; this
0x18005a5d9  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18005a5de  nop
0x18005a5df  xor     r15d, r15d
0x18005a5e2  mov     [rbp+arg_0], r15d
0x18005a5e6  lea     rbx, [r14+38h]
0x18005a5ea  mov     [rbp+var_28], rbx
0x18005a5ee  lea     rax, [rbp+arg_0]
0x18005a5f2  mov     [rbp+var_20], rax
0x18005a5f6  cmp     cs:byte_180109AF0, r15b
0x18005a5fd  jnz     short loc_18005A620
0x18005a5ff  call    cs:__imp_GetTickCount
0x18005a606  nop     dword ptr [rax+rax+00h]
0x18005a60b  mov     ecx, eax
0x18005a60d  call    cs:__imp__o_srand
0x18005a614  nop     dword ptr [rax+rax+00h]
0x18005a619  mov     cs:byte_180109AF0, sil
0x18005a620  call    cs:__imp_rand
0x18005a627  nop     dword ptr [rax+rax+00h]
0x18005a62c  cmp     eax, 147h
0x18005a631  jge     short loc_18005A65E
0x18005a633  lea     rax, aTpmkey20hmacEx_0; "TpmKey20Hmac::ExportKey"
0x18005a63a  mov     [rbx], rax
0x18005a63d  lea     rax, aStart; "Start"
0x18005a644  mov     [rbx+8], rax
0x18005a648  call    cs:__imp_GetTickCount64
0x18005a64f  nop     dword ptr [rax+rax+00h]
0x18005a654  mov     [rbx+10h], rax
0x18005a658  mov     word ptr [rbx+18h], 1
0x18005a65e  mov     r15, [rbp+arg_28]
0x18005a662  xor     eax, eax
0x18005a664  mov     [r15], eax
0x18005a667  cmp     [r14+60h], rax
0x18005a66b  jnz     short loc_18005A6AE
0x18005a66d  cmp     [r14+288h], rax
0x18005a674  jz      short loc_18005A6AE
0x18005a676  xor     r9d, r9d; int
0x18005a679  xor     r8d, r8d; signed __int8
0x18005a67c  lea     rdx, aNeedtoimportbe; "NeedToImportBeforeExporting"
0x18005a683  mov     rcx, rbx; this
0x18005a686  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a68b  mov     byte ptr [rbx+19h], 0
0x18005a68f  mov     rcx, r14; this
0x18005a692  call    ?PerformKeyImport@TpmKey20Hmac@@MEAAJXZ; TpmKey20Hmac::PerformKeyImport(void)
0x18005a697  mov     edi, eax
0x18005a699  mov     [rbp+arg_0], eax
0x18005a69c  test    eax, eax
0x18005a69e  jns     short loc_18005A6AA
0x18005a6a0  mov     r9d, eax
0x18005a6a3  mov     edx, 3E4h
0x18005a6a8  jmp     short loc_18005A6EC
0x18005a6aa  mov     rdi, [rbp+arg_8]
0x18005a6ae  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18005a6b5  mov     rcx, r12; String1
0x18005a6b8  call    wcscmp_0
0x18005a6bd  test    eax, eax
0x18005a6bf  jz      loc_18005A761
0x18005a6c5  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x18005a6cc  mov     rcx, r12; String1
0x18005a6cf  call    wcscmp_0
0x18005a6d4  test    eax, eax
0x18005a6d6  jz      loc_18005A761
0x18005a6dc  mov     edi, 80290405h
0x18005a6e1  mov     [rbp+arg_0], edi
0x18005a6e4  mov     r9d, edi; char *
0x18005a6e7  mov     edx, 3EAh; void *
0x18005a6ec  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a6f3  mov     rcx, [rbp+38h]; this
0x18005a6f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a6fc  nop
0x18005a6fd  xor     r14d, r14d
0x18005a700  cmp     [rbx+18h], r14b
0x18005a704  jz      loc_18005A84E
0x18005a70a  mov     r9d, [rbp+arg_0]; int
0x18005a70e  test    r9d, r9d
0x18005a711  jns     short loc_18005A731
0x18005a713  cmp     [rbx+19h], r14b
0x18005a717  jnz     short loc_18005A758
0x18005a719  mov     r8b, 0FFh; signed __int8
0x18005a71c  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18005a723  mov     rcx, rbx; this
0x18005a726  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a72b  mov     [rbx+19h], sil
0x18005a72f  jmp     short loc_18005A758
0x18005a731  mov     rcx, rbx; this
0x18005a734  jnz     short loc_18005A745
0x18005a736  xor     r9d, r9d
0x18005a739  xor     r8d, r8d
0x18005a73c  lea     rdx, aCompleted; "Completed"
0x18005a743  jmp     short loc_18005A74F
0x18005a745  mov     r8b, sil; signed __int8
0x18005a748  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18005a74f  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a754  mov     [rbx+19h], r14b
0x18005a758  mov     [rbx+18h], r14b
0x18005a75c  jmp     loc_18005A84E
0x18005a761  mov     [rbp+var_30], 0
0x18005a768  mov     eax, [rbp+arg_30]
0x18005a76b  mov     [rsp+70h+var_40], eax; unsigned int
0x18005a76f  lea     rax, [rbp+var_30]
0x18005a773  mov     [rsp+70h+var_48], rax; unsigned int *
0x18005a778  mov     eax, [rbp+arg_20]
0x18005a77b  mov     [rsp+70h+var_50], eax; int
0x18005a77f  mov     r9, r13; unsigned __int8 *
0x18005a782  mov     r8, r12; unsigned __int16 *
0x18005a785  mov     rdx, rdi; struct TpmKey *
0x18005a788  mov     rcx, r14; this
0x18005a78b  call    ?ExportKey@TpmKey20@@UEAAJPEAVTpmKey@@PEBGPEAEIPEAII@Z; TpmKey20::ExportKey(TpmKey *,ushort const *,uchar *,uint,uint *,uint)
0x18005a790  mov     edi, eax
0x18005a792  mov     [rbp+arg_0], eax
0x18005a795  xor     r13d, r13d
0x18005a798  test    eax, eax
0x18005a79a  jns     short loc_18005A80F
0x18005a79c  mov     rcx, [rbp+38h]; this
0x18005a7a0  mov     r9d, eax; char *
0x18005a7a3  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005a7aa  mov     edx, 3F3h; void *
0x18005a7af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a7b4  nop
0x18005a7b5  cmp     [rbx+18h], r13b
0x18005a7b9  jz      loc_18005A84E
0x18005a7bf  mov     r9d, [rbp+arg_0]; int
0x18005a7c3  test    r9d, r9d
0x18005a7c6  jns     short loc_18005A7E6
0x18005a7c8  cmp     [rbx+19h], r13b
0x18005a7cc  jnz     short loc_18005A84A
0x18005a7ce  mov     r8b, 0FFh; signed __int8
0x18005a7d1  lea     rdx, aFailedwithunsp; "FailedWithUnspecificError"
0x18005a7d8  mov     rcx, rbx; this
0x18005a7db  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a7e0  mov     [rbx+19h], sil
0x18005a7e4  jmp     short loc_18005A84A
0x18005a7e6  mov     rcx, rbx; this
0x18005a7e9  jnz     short loc_18005A7FA
0x18005a7eb  xor     r9d, r9d
0x18005a7ee  xor     r8d, r8d
0x18005a7f1  lea     rdx, aCompleted; "Completed"
0x18005a7f8  jmp     short loc_18005A804
0x18005a7fa  mov     r8b, sil; signed __int8
0x18005a7fd  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18005a804  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a809  mov     [rbx+19h], r13b
0x18005a80d  jmp     short loc_18005A84A
0x18005a80f  mov     eax, [rbp+var_30]
0x18005a812  mov     [r15], eax
0x18005a815  cmp     [rbx+18h], r13b
0x18005a819  jz      short loc_18005A84E
0x18005a81b  mov     r12b, r13b
0x18005a81e  test    edi, edi
0x18005a820  jnz     short loc_18005A831
0x18005a822  lea     rdx, aCompleted; "Completed"
0x18005a829  mov     sil, r13b
0x18005a82c  mov     r9d, r13d
0x18005a82f  jmp     short loc_18005A83B
0x18005a831  lea     rdx, aCompletedwithw; "CompletedWithWarning"
0x18005a838  mov     r9d, edi; int
0x18005a83b  mov     r8b, sil; signed __int8
0x18005a83e  mov     rcx, rbx; this
0x18005a841  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18005a846  mov     [rbx+19h], r12b
0x18005a84a  mov     [rbx+18h], r13b
0x18005a84e  lea     rcx, [rbp+var_18]; this
0x18005a852  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18005a857  mov     eax, edi
0x18005a859  mov     rbx, [rsp+70h+arg_10]
0x18005a861  add     rsp, 70h
0x18005a865  pop     r15
0x18005a867  pop     r14
0x18005a869  pop     r13
0x18005a86b  pop     r12
0x18005a86d  pop     rdi
0x18005a86e  pop     rsi
0x18005a86f  pop     rbp
0x18005a870  retn
```
