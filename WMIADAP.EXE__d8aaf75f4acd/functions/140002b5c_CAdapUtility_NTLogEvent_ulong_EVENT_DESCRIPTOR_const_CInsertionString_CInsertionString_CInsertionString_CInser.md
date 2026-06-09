# CAdapUtility::NTLogEvent(ulong,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)

- ea: `0x140002b5c`
- end: `0x140002ddc`
- name: `?NTLogEvent@CAdapUtility@@SAJKAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z`
- size: `640`
- prototype: `__int64 __fastcall(__int64, __int64, const struct CInsertionString *, const struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *, struct CInsertionString *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003360`
- `0x1400037f0`
- `0x140004620`

## callees

- `0x140002ae4`
- `0x140002b1c`
- `0x140002b5c`

## import_xrefs

- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x140002d30`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x140002d30`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x140002d11`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x140002d11`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x140002bae`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x140002bae`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x140002d3b`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x140002d3b`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x140002ba3`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x140002ba3`

## pseudocode

```c
__int64 __fastcall CAdapUtility::NTLogEvent(
        __int64 a1,
        __int64 a2,
        const struct CInsertionString *a3,
        const struct CInsertionString *a4,
        struct CInsertionString *a5,
        struct CInsertionString *a6,
        struct CInsertionString *a7,
        struct CInsertionString *a8,
        struct CInsertionString *a9,
        struct CInsertionString *a10,
        struct CInsertionString *a11,
        struct CInsertionString *a12)
{
  const struct CInsertionString *v12; // rbx
  unsigned int v13; // edi
  CInsertionString *v14; // r13
  CInsertionString *v15; // r12
  CInsertionString *v16; // r15
  CInsertionString *v17; // r14
  CInsertionString *v18; // rsi
  CInsertionString *v19; // rdi
  CInsertionString *v20; // rbx
  CInsertionString *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  CInsertionString *v25; // [rsp+78h] [rbp-90h]
  CInsertionString *v26; // [rsp+80h] [rbp-88h]
  _BYTE v27[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v28[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v29[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v30[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v31[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v32[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v33[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v34[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v35[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v36[16]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v37[144]; // [rsp+178h] [rbp+70h] BYREF

  v12 = a4;
  v13 = -2147217407;
  CEventLog::CEventLog((CEventLog *)v37, 0, (const struct _GUID *)S_WinMgmtR, 0xAu);
  if ( CEventLog::Open((CEventLog *)v37) )
  {
    v25 = CInsertionString::CInsertionString((CInsertionString *)v27, a12);
    v26 = CInsertionString::CInsertionString((CInsertionString *)v28, a11);
    v14 = CInsertionString::CInsertionString((CInsertionString *)v29, a10);
    v15 = CInsertionString::CInsertionString((CInsertionString *)v30, a9);
    v16 = CInsertionString::CInsertionString((CInsertionString *)v31, a8);
    v17 = CInsertionString::CInsertionString((CInsertionString *)v32, a7);
    v18 = CInsertionString::CInsertionString((CInsertionString *)v33, a6);
    v19 = CInsertionString::CInsertionString((CInsertionString *)v34, a5);
    v20 = CInsertionString::CInsertionString((CInsertionString *)v35, v12);
    v21 = CInsertionString::CInsertionString((CInsertionString *)v36, a3);
    LOWORD(v22) = 2;
    v23 = CEventLog::Report(v37, v22, a2, v21, v20, v19, v18, v17, v16, v15, v14, v26, v25);
    v13 = -2147217407;
    if ( v23 )
      v13 = 0;
    v12 = a4;
  }
  CEventLog::Close((CEventLog *)v37);
  CEventLog::~CEventLog((CEventLog *)v37);
  CInsertionString::~CInsertionString((unsigned __int16 **)a3);
  CInsertionString::~CInsertionString((unsigned __int16 **)v12);
  CInsertionString::~CInsertionString((unsigned __int16 **)a5);
  CInsertionString::~CInsertionString((unsigned __int16 **)a6);
  CInsertionString::~CInsertionString((unsigned __int16 **)a7);
  CInsertionString::~CInsertionString((unsigned __int16 **)a8);
  CInsertionString::~CInsertionString((unsigned __int16 **)a9);
  CInsertionString::~CInsertionString((unsigned __int16 **)a10);
  CInsertionString::~CInsertionString((unsigned __int16 **)a11);
  CInsertionString::~CInsertionString((unsigned __int16 **)a12);
  return v13;
}

```

## disassembly

```asm
0x140002b5c  mov     rax, rsp
0x140002b5f  mov     [rax+8], rbx
0x140002b63  mov     [rax+20h], r9
0x140002b67  mov     [rax+18h], r8
0x140002b6b  mov     [rax+10h], rdx
0x140002b6f  push    rbp
0x140002b70  push    rsi
0x140002b71  push    rdi
0x140002b72  push    r12
0x140002b74  push    r13
0x140002b76  push    r14
0x140002b78  push    r15
0x140002b7a  lea     rbp, [rax-108h]
0x140002b81  sub     rsp, 1D0h
0x140002b88  mov     rbx, r9
0x140002b8b  mov     edi, 80041001h
0x140002b90  mov     r9d, 0Ah
0x140002b96  lea     r8, S_WinMgmtR
0x140002b9d  xor     edx, edx
0x140002b9f  lea     rcx, [rbp+100h+var_90]
0x140002ba3  call    cs:__imp_??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z; CEventLog::CEventLog(ushort const *,_GUID const &,ulong)
0x140002ba9  nop
0x140002baa  lea     rcx, [rbp+100h+var_90]
0x140002bae  call    cs:__imp_?Open@CEventLog@@QEAAHXZ; CEventLog::Open(void)
0x140002bb4  test    eax, eax
0x140002bb6  jz      loc_140002D2C
0x140002bbc  lea     rax, [rbp+100h+var_130]
0x140002bc0  mov     [rbp+100h+var_180], rax
0x140002bc4  mov     rdx, [rbp+100h+arg_58]; struct CInsertionString *
0x140002bcb  lea     rcx, [rbp+100h+var_130]; this
0x140002bcf  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002bd4  mov     [rsp+200h+var_190], rax
0x140002bd9  lea     rax, [rbp+100h+var_120]
0x140002bdd  mov     [rbp+100h+var_178], rax
0x140002be1  mov     rdx, [rbp+100h+arg_50]; struct CInsertionString *
0x140002be8  lea     rcx, [rbp+100h+var_120]; this
0x140002bec  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002bf1  mov     [rsp+78h], rax
0x140002bf6  lea     rax, [rbp+100h+var_110]
0x140002bfa  mov     [rbp+100h+var_170], rax
0x140002bfe  mov     rdx, [rbp+100h+arg_48]; struct CInsertionString *
0x140002c05  lea     rcx, [rbp+100h+var_110]; this
0x140002c09  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c0e  mov     r13, rax
0x140002c11  lea     rax, [rbp+100h+var_100]
0x140002c15  mov     [rbp+100h+var_168], rax
0x140002c19  mov     rdx, [rbp+100h+arg_40]; struct CInsertionString *
0x140002c20  lea     rcx, [rbp+100h+var_100]; this
0x140002c24  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c29  mov     r12, rax
0x140002c2c  lea     rax, [rbp+100h+var_F0]
0x140002c30  mov     [rbp+100h+var_160], rax
0x140002c34  mov     rdx, [rbp+100h+arg_38]; struct CInsertionString *
0x140002c3b  lea     rcx, [rbp+100h+var_F0]; this
0x140002c3f  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c44  mov     r15, rax
0x140002c47  lea     rax, [rbp+100h+var_E0]
0x140002c4b  mov     [rbp+100h+var_158], rax
0x140002c4f  mov     rdx, [rbp+100h+arg_30]; struct CInsertionString *
0x140002c56  lea     rcx, [rbp+100h+var_E0]; this
0x140002c5a  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c5f  mov     r14, rax
0x140002c62  lea     rax, [rbp+100h+var_D0]
0x140002c66  mov     [rbp+100h+var_150], rax
0x140002c6a  mov     rdx, [rbp+100h+arg_28]; struct CInsertionString *
0x140002c71  lea     rcx, [rbp+100h+var_D0]; this
0x140002c75  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c7a  mov     rsi, rax
0x140002c7d  lea     rax, [rbp+100h+var_C0]
0x140002c81  mov     [rbp+100h+var_148], rax
0x140002c85  mov     rdx, [rbp+100h+arg_20]; struct CInsertionString *
0x140002c8c  lea     rcx, [rbp+100h+var_C0]; this
0x140002c90  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002c95  mov     rdi, rax
0x140002c98  lea     rax, [rbp+100h+var_B0]
0x140002c9c  mov     [rbp+100h+var_140], rax
0x140002ca0  mov     rdx, rbx; struct CInsertionString *
0x140002ca3  lea     rcx, [rbp+100h+var_B0]; this
0x140002ca7  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002cac  mov     rbx, rax
0x140002caf  lea     rax, [rbp+100h+var_A0]
0x140002cb3  mov     [rbp+100h+var_138], rax
0x140002cb7  mov     rdx, [rbp+100h+arg_10]; struct CInsertionString *
0x140002cbe  lea     rcx, [rbp+100h+var_A0]; this
0x140002cc2  call    ??0CInsertionString@@QEAA@AEBV0@@Z; CInsertionString::CInsertionString(CInsertionString const &)
0x140002cc7  nop
0x140002cc8  mov     rcx, [rsp+200h+var_190]
0x140002ccd  mov     [rsp+60h], rcx
0x140002cd2  mov     rcx, [rsp+78h]
0x140002cd7  mov     [rsp+200h+var_1A8], rcx
0x140002cdc  mov     [rsp+200h+var_1B0], r13
0x140002ce1  mov     [rsp+200h+var_1B8], r12
0x140002ce6  mov     [rsp+200h+var_1C0], r15
0x140002ceb  mov     [rsp+200h+var_1C8], r14
0x140002cf0  mov     [rsp+200h+var_1D0], rsi
0x140002cf5  mov     [rsp+200h+var_1D8], rdi
0x140002cfa  mov     [rsp+200h+var_1E0], rbx
0x140002cff  mov     r9, rax
0x140002d02  mov     r8, [rbp+100h+arg_8]
0x140002d09  mov     dx, 2
0x140002d0d  lea     rcx, [rbp+100h+var_90]
0x140002d11  call    cs:__imp_?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CEventLog::Report(ushort,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x140002d17  mov     ecx, eax
0x140002d19  mov     edi, 80041001h
0x140002d1e  xor     eax, eax
0x140002d20  test    ecx, ecx
0x140002d22  cmovnz  edi, eax
0x140002d25  mov     rbx, [rbp+100h+arg_18]
0x140002d2c  lea     rcx, [rbp+100h+var_90]
0x140002d30  call    cs:__imp_?Close@CEventLog@@QEAAHXZ; CEventLog::Close(void)
0x140002d36  nop
0x140002d37  lea     rcx, [rbp+100h+var_90]
0x140002d3b  call    cs:__imp_??1CEventLog@@QEAA@XZ; CEventLog::~CEventLog(void)
0x140002d41  nop
0x140002d42  mov     rcx, [rbp+100h+arg_10]; this
0x140002d49  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d4e  nop
0x140002d4f  mov     rcx, rbx; this
0x140002d52  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d57  nop
0x140002d58  mov     rcx, [rbp+100h+arg_20]; this
0x140002d5f  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d64  nop
0x140002d65  mov     rcx, [rbp+100h+arg_28]; this
0x140002d6c  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d71  nop
0x140002d72  mov     rcx, [rbp+100h+arg_30]; this
0x140002d79  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d7e  nop
0x140002d7f  mov     rcx, [rbp+100h+arg_38]; this
0x140002d86  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d8b  nop
0x140002d8c  mov     rcx, [rbp+100h+arg_40]; this
0x140002d93  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002d98  nop
0x140002d99  mov     rcx, [rbp+100h+arg_48]; this
0x140002da0  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002da5  nop
0x140002da6  mov     rcx, [rbp+100h+arg_50]; this
0x140002dad  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002db2  nop
0x140002db3  mov     rcx, [rbp+100h+arg_58]; this
0x140002dba  call    ??1CInsertionString@@QEAA@XZ; CInsertionString::~CInsertionString(void)
0x140002dbf  mov     eax, edi
0x140002dc1  mov     rbx, [rsp+200h+arg_0]
0x140002dc9  add     rsp, 1D0h
0x140002dd0  pop     r15
0x140002dd2  pop     r14
0x140002dd4  pop     r13
0x140002dd6  pop     r12
0x140002dd8  pop     rdi
0x140002dd9  pop     rsi
0x140002dda  pop     rbp
0x140002ddb  retn
```
