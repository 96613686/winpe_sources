# CDtcTransactionsConfig::UpdateTransactionList(ulong,uchar *)

- ea: `0x18004d8fc`
- end: `0x18004dafd`
- name: `?UpdateTransactionList@CDtcTransactionsConfig@@AEAAJKPEAE@Z`
- size: `513`
- prototype: `int(CDtcTransactionsConfig *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d310`

## callees

- `0x180003cf0`
- `0x18001de26`
- `0x18004d8fc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004da33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004da33`

## string_xrefs

- `0x18004d91e`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004d928`: `CDtcTransactionsConfig::UpdateTransactionList`
- `0x18004d971`: `CDtcTransactionsConfig::UpdateTransactionList`
- `0x18004d99b`: `CDtcTransactionsConfig::UpdateTransactionList`
- `0x18004d9f0`: `CDtcTransactionsConfig::UpdateTransactionList`
- `0x18004dab1`: `CDtcTransactionsConfig::UpdateTransactionList`
- `0x18004d957`: `UpdateTransactionList called with cbTranList = 0`
- `0x18004da41`: `CoTaskMemAlloc failed to allocate memory`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::UpdateTransactionList(
        CDtcTransactionsConfig *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  unsigned int v3; // ebp
  SIZE_T v4; // rsi
  unsigned __int8 *v7; // rdi
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int8 *v10; // rax
  __int64 v12; // [rsp+28h] [rbp-60h]
  const wchar_t *v13; // [rsp+30h] [rbp-58h]

  v3 = 0;
  v4 = a2;
  v7 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    337,
    L"CDtcTransactionsConfig::UpdateTransactionList",
    0,
    L"In");
  if ( !(_DWORD)v4 )
  {
    v8 = 343;
    v13 = L"UpdateTransactionList called with cbTranList = 0";
    v9 = 3;
    v12 = 0;
LABEL_3:
    TraceStringInline(
      15,
      v9,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      v8,
      L"CDtcTransactionsConfig::UpdateTransactionList",
      v12,
      v13);
    goto LABEL_16;
  }
  if ( (unsigned int)v4 < 0x148 )
  {
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      354,
      L"CDtcTransactionsConfig::UpdateTransactionList",
      0,
      L"Received a corrupt transaction list: got %d bytes, expected at least %d bytes",
      v4,
      328);
LABEL_6:
    v3 = -2147467259;
    goto LABEL_16;
  }
  if ( 324 * *(_DWORD *)a3 + 4 != (_DWORD)v4 )
  {
    v7 = a3;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      371,
      L"CDtcTransactionsConfig::UpdateTransactionList",
      0,
      L"Received a corrupt transaction list: has %d elements, expected %d bytes, got %d bytes.",
      *(_DWORD *)a3,
      324 * *(_DWORD *)a3 + 4,
      v4);
    goto LABEL_6;
  }
  v10 = (unsigned __int8 *)CoTaskMemAlloc(v4);
  v7 = v10;
  if ( !v10 )
  {
    v3 = -2147024882;
    v13 = L"CoTaskMemAlloc failed to allocate memory";
    v9 = 1;
    LODWORD(v12) = -2147024882;
    v8 = 380;
    goto LABEL_3;
  }
  memcpy_0(v10, a3, v4);
  (**((void (__fastcall ***)(char *))this + 10))((char *)this + 80);
  if ( !*((_DWORD *)this + 8) && !*((_QWORD *)this + 8) )
  {
    *((_QWORD *)this + 8) = v7;
    v7 = 0;
    if ( *((_QWORD *)this + 9) )
      *((_DWORD *)this + 8) = 1;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
LABEL_16:
  LODWORD(v12) = v3;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    397,
    L"CDtcTransactionsConfig::UpdateTransactionList",
    v12,
    L"Out");
  CoTaskMemFree(v7);
  return v3;
}

```

## disassembly

```asm
0x18004d8fc  push    rbx
0x18004d8fe  push    rbp
0x18004d8ff  push    rsi
0x18004d900  push    rdi
0x18004d901  push    r12
0x18004d903  push    r13
0x18004d905  push    r14
0x18004d907  sub     rsp, 50h
0x18004d90b  xor     ebp, ebp
0x18004d90d  mov     esi, edx
0x18004d90f  lea     rax, aIn_0; "In"
0x18004d916  mov     r14, r8
0x18004d919  mov     [rsp+88h+var_58], rax
0x18004d91e  lea     r12, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004d925  mov     rbx, rcx
0x18004d928  lea     rax, aCdtctransactio_9; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004d92f  lea     r13d, [rbp+0Fh]
0x18004d933  xor     edi, edi
0x18004d935  mov     ecx, r13d
0x18004d938  mov     [rsp+88h+var_60], rdi
0x18004d93d  mov     r9d, 151h
0x18004d943  mov     [rsp+88h+var_68], rax
0x18004d948  mov     r8, r12
0x18004d94b  lea     edx, [rbp+6]
0x18004d94e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d953  test    esi, esi
0x18004d955  jnz     short loc_18004D98D
0x18004d957  lea     rax, aUpdatetransact; "UpdateTransactionList called with cbTra"...
0x18004d95e  mov     r9d, 157h
0x18004d964  mov     [rsp+88h+var_58], rax
0x18004d969  lea     edx, [rbp+3]
0x18004d96c  mov     [rsp+88h+var_60], rdi
0x18004d971  lea     rbx, aCdtctransactio_9; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004d978  mov     r8, r12
0x18004d97b  mov     ecx, r13d
0x18004d97e  mov     [rsp+88h+var_68], rbx
0x18004d983  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d988  jmp     loc_18004DAB8
0x18004d98d  mov     eax, 148h
0x18004d992  cmp     esi, eax
0x18004d994  jnb     short loc_18004D9DC
0x18004d996  mov     [rsp+88h+var_48], rax
0x18004d99b  lea     rbx, aCdtctransactio_9; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004d9a2  mov     [rsp+88h+var_50], esi
0x18004d9a6  lea     rax, aReceivedACorru; "Received a corrupt transaction list: go"...
0x18004d9ad  mov     [rsp+88h+var_58], rax
0x18004d9b2  mov     r9d, 162h
0x18004d9b8  mov     [rsp+88h+var_60], rdi
0x18004d9bd  mov     r8, r12
0x18004d9c0  mov     edx, 1
0x18004d9c5  mov     [rsp+88h+var_68], rbx
0x18004d9ca  mov     ecx, r13d
0x18004d9cd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004d9d2  mov     ebp, 80004005h
0x18004d9d7  jmp     loc_18004DAB8
0x18004d9dc  mov     ecx, [r14]
0x18004d9df  imul    eax, ecx, 144h
0x18004d9e5  add     eax, 4
0x18004d9e8  cmp     eax, esi
0x18004d9ea  jz      short loc_18004DA30
0x18004d9ec  mov     [rsp+88h+var_40], esi
0x18004d9f0  lea     rbx, aCdtctransactio_9; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004d9f7  mov     dword ptr [rsp+88h+var_48], eax
0x18004d9fb  mov     r9d, 173h
0x18004da01  mov     [rsp+88h+var_50], ecx
0x18004da05  lea     rax, aReceivedACorru_0; "Received a corrupt transaction list: ha"...
0x18004da0c  mov     [rsp+88h+var_58], rax
0x18004da11  mov     r8, r12
0x18004da14  mov     [rsp+88h+var_60], rbp
0x18004da19  mov     edx, 1
0x18004da1e  mov     ecx, r13d
0x18004da21  mov     [rsp+88h+var_68], rbx
0x18004da26  mov     rdi, r14
0x18004da29  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004da2e  jmp     short loc_18004D9D2
0x18004da30  mov     rcx, rsi; cb
0x18004da33  call    cs:__imp_CoTaskMemAlloc
0x18004da39  mov     rdi, rax
0x18004da3c  test    rax, rax
0x18004da3f  jnz     short loc_18004DA64
0x18004da41  lea     rax, aCotaskmemalloc_1; "CoTaskMemAlloc failed to allocate memor"...
0x18004da48  mov     ebp, 8007000Eh
0x18004da4d  mov     [rsp+88h+var_58], rax
0x18004da52  lea     edx, [rdi+1]
0x18004da55  mov     dword ptr [rsp+88h+var_60], ebp
0x18004da59  mov     r9d, 17Ch
0x18004da5f  jmp     loc_18004D971
0x18004da64  mov     r8, rsi; Size
0x18004da67  mov     rdx, r14; Src
0x18004da6a  mov     rcx, rdi; void *
0x18004da6d  call    memcpy_0
0x18004da72  lea     rsi, [rbx+50h]
0x18004da76  mov     rax, [rsi]
0x18004da79  mov     rcx, rsi
0x18004da7c  mov     rax, [rax]
0x18004da7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da84  cmp     [rbx+20h], ebp
0x18004da87  jnz     short loc_18004DAA2
0x18004da89  cmp     [rbx+40h], rbp
0x18004da8d  jnz     short loc_18004DAA2
0x18004da8f  mov     [rbx+40h], rdi
0x18004da93  xor     edi, edi
0x18004da95  cmp     [rbx+48h], rdi
0x18004da99  jz      short loc_18004DAA2
0x18004da9b  mov     dword ptr [rbx+20h], 1
0x18004daa2  mov     rax, [rsi]
0x18004daa5  mov     rcx, rsi
0x18004daa8  mov     rax, [rax+10h]
0x18004daac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dab1  lea     rbx, aCdtctransactio_9; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004dab8  lea     rax, aOut; "Out"
0x18004dabf  mov     r9d, 18Dh
0x18004dac5  mov     [rsp+88h+var_58], rax
0x18004daca  mov     r8, r12
0x18004dacd  mov     dword ptr [rsp+88h+var_60], ebp
0x18004dad1  mov     edx, 6
0x18004dad6  mov     ecx, r13d
0x18004dad9  mov     [rsp+88h+var_68], rbx
0x18004dade  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004dae3  mov     rcx, rdi; pv
0x18004dae6  call    cs:__imp_CoTaskMemFree
0x18004daec  mov     eax, ebp
0x18004daee  add     rsp, 50h
0x18004daf2  pop     r14
0x18004daf4  pop     r13
0x18004daf6  pop     r12
0x18004daf8  pop     rdi
0x18004daf9  pop     rsi
0x18004dafa  pop     rbp
0x18004dafb  pop     rbx
0x18004dafc  retn
```
