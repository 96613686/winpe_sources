# WBemUtil::GetWbemObjectBSTR(IWbemClassObject *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x14003e598`
- end: `0x14003e80d`
- name: `?GetWbemObjectBSTR@WBemUtil@@YAJPEAUIWbemClassObject@@PEB_W1PEAPEA_W@Z`
- size: `629`
- prototype: `int(WBemUtil *__hidden this, struct IWbemClassObject *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003e814`

## callees

- `0x140008de4`
- `0x1400154b4`
- `0x14003e598`
- `0x14004484c`
- `0x14004489c`
- `0x140044994`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14003e7df`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e7df`
- `OLEAUT32!__imp_VariantInit` at `0x14003e5d0`
- `OLEAUT32!__imp_VariantInit` at `0x14003e5db`
- `OLEAUT32!__imp_VariantInit` at `0x14003e5d0`
- `OLEAUT32!__imp_VariantInit` at `0x14003e5db`
- `OLEAUT32!__imp_VariantClear` at `0x14003e790`
- `OLEAUT32!__imp_VariantClear` at `0x14003e790`

## string_xrefs

- `0x14003e61b`: `ComTimeout::MakeComCall [%hs]`
- `0x14003e6ba`: `COM call timed out`
- `0x14003e66a`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x14003e6f0`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x14003e72a`: `COM call [%hs, from %hs:%u] timed out after %u seconds`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WBemUtil::GetWbemObjectBSTR(
        WBemUtil *this,
        struct IWbemClassObject *a2,
        const wchar_t *a3,
        wchar_t *a4)
{
  unsigned int v8; // edi
  int v9; // ebx
  int v10; // eax
  BSTR v12; // rax
  int v13; // [rsp+20h] [rbp-60h]
  int v14; // [rsp+20h] [rbp-60h]
  int v15[2]; // [rsp+20h] [rbp-60h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  __int128 pv; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  VariantInit(&pvarg);
  VariantInit(&pvarg);
  if ( !this )
  {
    v8 = 90;
LABEL_7:
    v9 = -2147467261;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wbemutil.cpp",
      (const char *)(unsigned int)v9,
      v13);
    goto LABEL_17;
  }
  if ( !a2 )
  {
    v8 = 91;
    goto LABEL_7;
  }
  if ( !a4 )
  {
    v8 = 92;
    goto LABEL_7;
  }
  *(_QWORD *)a4 = 0;
  WUTrace(0, 0, 0x10000, 5, 0, L"ComTimeout::MakeComCall [%hs]");
  pv = 0u;
  WORD6(pv) = 0;
  v10 = WUComTimeout::ComTimeout::SetTimer(&pv);
  v9 = v10;
  v8 = 97;
  if ( v10 >= 0 )
  {
    v13 = 0;
    v9 = (*(__int64 (__fastcall **)(WBemUtil *, struct IWbemClassObject *, _QWORD, VARIANTARG *))(*(_QWORD *)this + 32LL))(
           this,
           a2,
           0,
           &pvarg);
    if ( v9 < 0 && BYTE13(pv) )
    {
      WUTrace("WUComTimeout::ComTimeout::MakeComCall", 52, 32, 3, 0, L"TelemetryAssert (%ws): %ws");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      v15[0] = v9;
      WUTrace(0, 0, 0x10000, 1, *(_QWORD *)v15, L"COM call [%hs, from %hs:%u] timed out after %u seconds");
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\ComTimeout.h",
      (const char *)(unsigned int)v10,
      v14);
  }
  WUComTimeout::ComTimeout::~ComTimeout((PTP_TIMER *)&pv);
  if ( v9 < 0 )
    goto LABEL_24;
  if ( pvarg.vt == 8 )
  {
    *(_QWORD *)a4 = pvarg.llVal;
    pvarg.llVal = 0;
    pvarg.vt = 0;
  }
  else
  {
    if ( pvarg.vt && (pvarg.vt != 1 || !a3) )
    {
      v9 = -2147467259;
      v8 = 113;
      goto LABEL_24;
    }
    v12 = SysAllocString(a3);
    *(_QWORD *)a4 = v12;
    if ( !v12 )
    {
      v9 = -2147217366;
      v8 = 109;
      goto LABEL_24;
    }
  }
  v9 = 0;
LABEL_17:
  VariantClear(&pvarg);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003e598  mov     [rsp-38h+arg_0], rbx
0x14003e59d  push    rbp
0x14003e59e  push    rsi
0x14003e59f  push    rdi
0x14003e5a0  push    r12
0x14003e5a2  push    r13
0x14003e5a4  push    r14
0x14003e5a6  push    r15
0x14003e5a8  mov     rbp, rsp
0x14003e5ab  sub     rsp, 80h
0x14003e5b2  mov     rax, cs:__security_cookie
0x14003e5b9  xor     rax, rsp
0x14003e5bc  mov     [rbp+var_8], rax
0x14003e5c0  mov     rsi, r9
0x14003e5c3  mov     r12, r8
0x14003e5c6  mov     r15, rdx
0x14003e5c9  mov     r14, rcx
0x14003e5cc  lea     rcx, [rbp+pvarg]; pvarg
0x14003e5d0  call    cs:__imp_VariantInit
0x14003e5d6  nop
0x14003e5d7  lea     rcx, [rbp+pvarg]; pvarg
0x14003e5db  call    cs:__imp_VariantInit
0x14003e5e1  xor     r13d, r13d
0x14003e5e4  test    r14, r14
0x14003e5e7  jnz     short loc_14003E5EF
0x14003e5e9  lea     edi, [r13+5Ah]
0x14003e5ed  jmp     short loc_14003E602
0x14003e5ef  test    r15, r15
0x14003e5f2  jnz     short loc_14003E5FA
0x14003e5f4  lea     edi, [r15+5Bh]
0x14003e5f8  jmp     short loc_14003E602
0x14003e5fa  test    rsi, rsi
0x14003e5fd  jnz     short loc_14003E60C
0x14003e5ff  lea     edi, [rsi+5Ch]
0x14003e602  mov     ebx, 80004003h
0x14003e607  jmp     loc_14003E7F5
0x14003e60c  mov     [rsi], r13
0x14003e60f  lea     rax, aPobjectGetPszn; "pObject->Get(pszName, 0L, &var, nullptr"...
0x14003e616  mov     [rsp+80h+var_50], rax
0x14003e61b  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x14003e622  mov     [rsp+80h+var_58], rax
0x14003e627  mov     qword ptr [rsp+80h+var_60], r13; int
0x14003e62c  xor     edx, edx
0x14003e62e  xor     ecx, ecx
0x14003e630  lea     r9d, [rdx+5]
0x14003e634  mov     r8d, 10000h
0x14003e63a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003e63f  xorps   xmm0, xmm0
0x14003e642  movups  [rbp+pv], xmm0
0x14003e646  mov     qword ptr [rbp+pv], r13
0x14003e64a  mov     word ptr [rbp+pv+0Ch], r13w
0x14003e64f  lea     rcx, [rbp+pv]; pv
0x14003e653  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x14003e658  mov     ebx, eax
0x14003e65a  mov     edi, 61h ; 'a'
0x14003e65f  test    eax, eax
0x14003e661  jns     short loc_14003E683
0x14003e663  mov     rcx, [rbp+38h]; this
0x14003e667  mov     r9d, eax; char *
0x14003e66a  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x14003e671  lea     edx, [rdi-33h]; void *
0x14003e674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e679  nop
0x14003e67a  lea     r14d, [rdi-60h]
0x14003e67e  jmp     loc_14003E75A
0x14003e683  mov     rax, [r14]
0x14003e686  mov     [rsp+80h+var_58], r13
0x14003e68b  mov     qword ptr [rsp+80h+var_60], r13; int
0x14003e690  lea     r9, [rbp+pvarg]
0x14003e694  xor     r8d, r8d
0x14003e697  mov     rdx, r15
0x14003e69a  mov     rcx, r14
0x14003e69d  mov     rax, [rax+20h]
0x14003e6a1  call    _guard_dispatch_icall
0x14003e6a6  mov     ebx, eax
0x14003e6a8  test    eax, eax
0x14003e6aa  jns     loc_14003E754
0x14003e6b0  cmp     byte ptr [rbp+pv+0Dh], r13b
0x14003e6b4  jz      loc_14003E754
0x14003e6ba  lea     rax, aComCallTimedOu; "COM call timed out"
0x14003e6c1  mov     [rsp+80h+var_48], rax
0x14003e6c6  lea     rax, aFalse; "false"
0x14003e6cd  mov     [rsp+80h+var_50], rax
0x14003e6d2  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x14003e6d9  mov     [rsp+80h+var_58], rax
0x14003e6de  mov     qword ptr [rsp+80h+var_60], r13
0x14003e6e3  mov     edx, 34h ; '4'
0x14003e6e8  lea     r9d, [rdx-31h]
0x14003e6ec  lea     r8d, [rdx-14h]
0x14003e6f0  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x14003e6f7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003e6fc  or      ecx, 0FFFFFFFFh; unsigned int
0x14003e6ff  mov     edx, ecx; unsigned int
0x14003e701  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003e706  mov     [rsp+80h+var_38], 0Fh
0x14003e70e  mov     [rsp+80h+var_40], edi
0x14003e712  lea     rax, aWbemutilGetwbe; "WBemUtil::GetWbemObjectBSTR"
0x14003e719  mov     [rsp+80h+var_48], rax
0x14003e71e  lea     rax, aPobjectGetPszn; "pObject->Get(pszName, 0L, &var, nullptr"...
0x14003e725  mov     [rsp+80h+var_50], rax
0x14003e72a  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x14003e731  mov     [rsp+80h+var_58], rax
0x14003e736  mov     [rsp+80h+var_60], ebx
0x14003e73a  mov     r14d, 1
0x14003e740  mov     r9d, r14d
0x14003e743  xor     edx, edx
0x14003e745  xor     ecx, ecx
0x14003e747  mov     r8d, 10000h
0x14003e74d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003e752  jmp     short loc_14003E75A
0x14003e754  mov     r14d, 1
0x14003e75a  lea     rcx, [rbp+pv]; this
0x14003e75e  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x14003e763  test    ebx, ebx
0x14003e765  js      loc_14003E7F5
0x14003e76b  mov     ecx, 8
0x14003e770  movzx   eax, word ptr [rbp+pvarg]
0x14003e774  cmp     cx, ax
0x14003e777  jnz     short loc_14003E7BF
0x14003e779  mov     rax, qword ptr [rbp+pvarg+8]
0x14003e77d  mov     [rsi], rax
0x14003e780  mov     qword ptr [rbp+pvarg+8], r13
0x14003e784  mov     word ptr [rbp+pvarg], r13w
0x14003e789  mov     ebx, r13d
0x14003e78c  lea     rcx, [rbp+pvarg]; pvarg
0x14003e790  call    cs:__imp_VariantClear
0x14003e796  mov     eax, ebx
0x14003e798  mov     rcx, [rbp+var_8]
0x14003e79c  xor     rcx, rsp; StackCookie
0x14003e79f  call    __security_check_cookie
0x14003e7a4  mov     rbx, [rsp+80h+arg_0]
0x14003e7ac  add     rsp, 80h
0x14003e7b3  pop     r15
0x14003e7b5  pop     r14
0x14003e7b7  pop     r13
0x14003e7b9  pop     r12
0x14003e7bb  pop     rdi
0x14003e7bc  pop     rsi
0x14003e7bd  pop     rbp
0x14003e7be  retn
0x14003e7bf  cmp     r13w, ax
0x14003e7c3  jz      short loc_14003E7DC
0x14003e7c5  cmp     r14w, ax
0x14003e7c9  jnz     short loc_14003E7D0
0x14003e7cb  test    r12, r12
0x14003e7ce  jnz     short loc_14003E7DC
0x14003e7d0  mov     ebx, 80004005h
0x14003e7d5  mov     edi, 71h ; 'q'
0x14003e7da  jmp     short loc_14003E7F5
0x14003e7dc  mov     rcx, r12; psz
0x14003e7df  call    cs:__imp_SysAllocString
0x14003e7e5  mov     [rsi], rax
0x14003e7e8  test    rax, rax
0x14003e7eb  jnz     short loc_14003E789
0x14003e7ed  mov     ebx, 8004102Ah
0x14003e7f2  lea     edi, [rax+6Dh]
0x14003e7f5  mov     rcx, [rbp+38h]; this
0x14003e7f9  mov     r9d, ebx; char *
0x14003e7fc  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003e803  mov     edx, edi; void *
0x14003e805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e80a  jmp     short loc_14003E78C
```
