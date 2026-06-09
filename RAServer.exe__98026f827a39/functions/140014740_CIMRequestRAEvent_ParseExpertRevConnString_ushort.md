# CIMRequestRAEvent::ParseExpertRevConnString(ushort *)

- ea: `0x140014740`
- end: `0x14001488e`
- name: `?ParseExpertRevConnString@CIMRequestRAEvent@@QEAAJPEAG@Z`
- size: `334`
- prototype: `__int64 __fastcall(BSTR *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x14000e6a0`
- `0x140014740`
- `0x140015240`
- `0x1400156c8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14001481a`
- `KERNEL32!GetProcessHeap` at `0x140014865`
- `KERNEL32!GetProcessHeap` at `0x14001481a`
- `KERNEL32!GetProcessHeap` at `0x140014865`
- `KERNEL32!HeapFree` at `0x14001482a`
- `KERNEL32!HeapFree` at `0x140014875`
- `KERNEL32!HeapFree` at `0x14001482a`
- `KERNEL32!HeapFree` at `0x140014875`
- `OLEAUT32!__imp_SysStringLen` at `0x140014794`
- `OLEAUT32!__imp_SysStringLen` at `0x1400147d5`
- `OLEAUT32!__imp_SysStringLen` at `0x140014794`
- `OLEAUT32!__imp_SysStringLen` at `0x1400147d5`

## string_xrefs

- `0x1400147fc`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140014847`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::ParseExpertRevConnString(BSTR *this, unsigned __int16 *a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  unsigned int v6; // r9d
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // r9d
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  LPVOID lpMem; // [rsp+50h] [rbp+18h] BYREF
  LPVOID v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  lpMem = 0;
  if ( !(unsigned int)GetPropertyValueFromBlob(a2, (const struct _EVENT_DESCRIPTOR *)L"ET", (unsigned __int16 **)&v15) )
  {
    v6 = 537;
    goto LABEL_12;
  }
  ATL::CComBSTR::operator=(this + 11, (const OLECHAR *)v15);
  if ( !SysStringLen(this[11]) )
  {
    v6 = 528;
LABEL_12:
    v9 = -2147024809;
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v6,
      L"CIMRequestRAEvent::ParseExpertRevConnString",
      0x80070057);
    goto LABEL_13;
  }
  if ( (unsigned int)GetPropertyValueFromBlob(a2, (const struct _EVENT_DESCRIPTOR *)L"PK", (unsigned __int16 **)&lpMem) )
  {
    v9 = 0;
    ATL::CComBSTR::operator=(this + 12, (const OLECHAR *)lpMem);
    if ( SysStringLen(this[12]) )
      goto LABEL_9;
    v10 = 555;
  }
  else
  {
    v10 = 563;
  }
  v9 = -2147024809;
  CEventLogger::LogError(
    v8,
    v7,
    L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
    v10,
    L"CIMRequestRAEvent::ParseExpertRevConnString",
    0x80070057);
LABEL_9:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
LABEL_13:
  if ( v15 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v15);
  }
  return v9;
}

```

## disassembly

```asm
0x140014740  mov     rax, rsp
0x140014743  mov     [rax+8], rbx
0x140014747  mov     [rax+10h], rdi
0x14001474b  push    r14
0x14001474d  sub     rsp, 30h
0x140014751  mov     rdi, rdx
0x140014754  mov     qword ptr [rax+20h], 0
0x14001475c  mov     r14, rcx
0x14001475f  mov     qword ptr [rax+18h], 0
0x140014767  mov     rcx, rdi; String
0x14001476a  lea     r8, [rax+20h]; unsigned __int16 **
0x14001476e  lea     rdx, aEt; "ET"
0x140014775  call    ?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z; GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)
0x14001477a  test    eax, eax
0x14001477c  jz      loc_140014832
0x140014782  mov     rdx, [rsp+38h+arg_18]
0x140014787  lea     rcx, [r14+58h]
0x14001478b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140014790  mov     rcx, [r14+58h]; pbstr
0x140014794  call    cs:__imp_SysStringLen
0x14001479a  test    eax, eax
0x14001479c  jnz     short loc_1400147A9
0x14001479e  mov     r9d, 210h
0x1400147a4  jmp     loc_140014838
0x1400147a9  lea     r8, [rsp+38h+lpMem]; unsigned __int16 **
0x1400147ae  mov     rcx, rdi; String
0x1400147b1  lea     rdx, aPk; "PK"
0x1400147b8  call    ?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z; GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)
0x1400147bd  test    eax, eax
0x1400147bf  jz      short loc_1400147E7
0x1400147c1  mov     rdx, [rsp+38h+lpMem]
0x1400147c6  lea     rcx, [r14+60h]
0x1400147ca  xor     edi, edi
0x1400147cc  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400147d1  mov     rcx, [r14+60h]; pbstr
0x1400147d5  call    cs:__imp_SysStringLen
0x1400147db  test    eax, eax
0x1400147dd  jnz     short loc_140014812
0x1400147df  mov     r9d, 22Bh
0x1400147e5  jmp     short loc_1400147ED
0x1400147e7  mov     r9d, 233h; unsigned int
0x1400147ed  lea     rax, aCimrequestraev_0; "CIMRequestRAEvent::ParseExpertRevConnSt"...
0x1400147f4  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x1400147fc  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014803  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140014808  mov     edi, 80070057h
0x14001480d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014812  cmp     [rsp+38h+lpMem], 0
0x140014818  jz      short loc_14001485D
0x14001481a  call    cs:__imp_GetProcessHeap
0x140014820  mov     r8, [rsp+38h+lpMem]; lpMem
0x140014825  xor     edx, edx; dwFlags
0x140014827  mov     rcx, rax; hHeap
0x14001482a  call    cs:__imp_HeapFree
0x140014830  jmp     short loc_14001485D
0x140014832  mov     r9d, 219h; unsigned int
0x140014838  lea     rax, aCimrequestraev_0; "CIMRequestRAEvent::ParseExpertRevConnSt"...
0x14001483f  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x140014847  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x14001484e  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140014853  mov     edi, 80070057h
0x140014858  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001485d  cmp     [rsp+38h+arg_18], 0
0x140014863  jz      short loc_14001487B
0x140014865  call    cs:__imp_GetProcessHeap
0x14001486b  mov     r8, [rsp+38h+arg_18]; lpMem
0x140014870  xor     edx, edx; dwFlags
0x140014872  mov     rcx, rax; hHeap
0x140014875  call    cs:__imp_HeapFree
0x14001487b  mov     rbx, [rsp+38h+arg_0]
0x140014880  mov     eax, edi
0x140014882  mov     rdi, [rsp+38h+arg_8]
0x140014887  add     rsp, 30h
0x14001488b  pop     r14
0x14001488d  retn
```
