# CDtcTransactionsConfig::GetTransactionsList(void * *,ulong *,void * *,ulong *)

- ea: `0x180017c94`
- end: `0x180017efb`
- name: `?GetTransactionsList@CDtcTransactionsConfig@@QEAAJPEAPEAXPEAK01@Z`
- size: `615`
- prototype: `__int64 __usercall@<rax>(CDtcTransactionsConfig *__hidden this@<rcx>, void **@<rdx>, unsigned int *@<r8>, void **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b3d0`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180014ac8`
- `0x180017c94`
- `0x180017f04`
- `0x180070740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017de7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017df6`

## string_xrefs

- `0x180017cc6`: `CDtcTransactionsConfig::GetTransactionsList`
- `0x180017d91`: `CDtcTransactionsConfig::GetTransactionsList`
- `0x180017dc2`: `CDtcTransactionsConfig::GetTransactionsList`
- `0x180017e49`: `CDtcTransactionsConfig::GetTransactionsList`
- `0x180017ecc`: `CDtcTransactionsConfig::GetTransactionsList`
- `0x180017cde`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180017d68`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180017e18`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180017e42`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180017ec5`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180017cef`: `CDtcTransactionsConfig::GetTransactionsList (com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp@269): ppTxStats shouldn't be NULL`
- `0x180017d01`: `CDtcTransactionsConfig::GetTransactionsList (com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp@270): pdwTxStats shouldn't be NULL`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::GetTransactionsList(
        CDtcTransactionsConfig *this,
        void **a2,
        unsigned int *a3,
        void **a4,
        unsigned int *a5)
{
  const unsigned __int16 *v9; // rcx
  int v10; // eax
  unsigned int LocalDTCProfileInt; // r12d
  signed int started; // ebx
  const wchar_t *v13; // rax
  __int64 v14; // r9
  signed int LastError; // eax
  __int64 v17; // [rsp+28h] [rbp-50h]
  __int64 v18; // [rsp+28h] [rbp-50h]

  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    267,
    L"CDtcTransactionsConfig::GetTransactionsList",
    0,
    L"In");
  if ( !a2 )
    DtcInternalErrorW(
      L"CDtcTransactionsConfig::GetTransactionsList (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp@269): ppTxStat"
       "s shouldn't be NULL");
  if ( !a3 )
    DtcInternalErrorW(
      L"CDtcTransactionsConfig::GetTransactionsList (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp@270): pdwTxSta"
       "ts shouldn't be NULL");
  *a2 = 0;
  *a3 = 0;
  if ( a4 && a5 )
  {
    *a4 = 0;
    v10 = 1;
    *a5 = 0;
  }
  else
  {
    v10 = 0;
  }
  *((_DWORD *)this + 35) = v10;
  LocalDTCProfileInt = GetLocalDTCProfileIntExW(v9, L"TxListTimeoutInS", 0x3Cu);
  started = CDtcTransactionsConfig::StartConnection(this);
  if ( started < 0 )
  {
    v13 = L" StartConnection failed";
    v14 = 291;
LABEL_11:
    LODWORD(v17) = started;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      v14,
      L"CDtcTransactionsConfig::GetTransactionsList",
      v17,
      v13);
    goto LABEL_22;
  }
  TraceStringInline(
    15,
    3,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    295,
    L"CDtcTransactionsConfig::GetTransactionsList",
    0,
    L"Connection started.");
  LastError = WaitForSingleObject(*((HANDLE *)this + 7), 1000 * LocalDTCProfileInt);
  if ( LastError )
  {
    if ( LastError == -1 )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError <= 0 )
      {
LABEL_16:
        v13 = L" WaitForSingleObject failed while waiting for Transaction list and stats";
        v14 = 309;
        goto LABEL_11;
      }
    }
    else if ( LastError <= 0 )
    {
      started = LastError;
      goto LABEL_16;
    }
    started = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  TraceStringInline(
    15,
    3,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    313,
    L"CDtcTransactionsConfig::GetTransactionsList",
    0,
    L"Data receive signaled.");
  *a2 = (void *)*((_QWORD *)this + 9);
  *a3 = 96;
  if ( *((_DWORD *)this + 35) == 1 )
  {
    *a4 = (void *)*((_QWORD *)this + 8);
    *a5 = *((_QWORD *)this + 8) != 0 ? 0x148 : 0;
  }
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 8) = 0;
LABEL_22:
  CDtcTransactionsConfig::ReleaseConnection(this);
  LODWORD(v18) = started;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    327,
    L"CDtcTransactionsConfig::GetTransactionsList",
    v18,
    L"Out");
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180017c94  push    rbx
0x180017c96  push    rbp
0x180017c97  push    rsi
0x180017c98  push    rdi
0x180017c99  push    r12
0x180017c9b  push    r14
0x180017c9d  push    r15
0x180017c9f  sub     rsp, 40h
0x180017ca3  mov     rbp, rdx
0x180017ca6  lea     rax, aIn_0; "In"
0x180017cad  mov     [rsp+78h+var_48], rax
0x180017cb2  mov     edx, 6
0x180017cb7  mov     r14, r9
0x180017cba  mov     [rsp+78h+var_50], 0
0x180017cc3  mov     r15, r8
0x180017cc6  lea     rax, aCdtctransactio_7; "CDtcTransactionsConfig::GetTransactions"...
0x180017ccd  mov     rdi, rcx
0x180017cd0  mov     [rsp+78h+var_58], rax
0x180017cd5  lea     ecx, [rdx+9]
0x180017cd8  mov     r9d, 10Bh
0x180017cde  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017ce5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017cea  test    rbp, rbp
0x180017ced  jnz     short loc_180017CFC
0x180017cef  lea     rcx, aCdtctransactio_11; "CDtcTransactionsConfig::GetTransactions"...
0x180017cf6  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180017cfc  test    r15, r15
0x180017cff  jnz     short loc_180017D0E
0x180017d01  lea     rcx, aCdtctransactio_6; "CDtcTransactionsConfig::GetTransactions"...
0x180017d08  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180017d0e  mov     rsi, [rsp+78h+arg_20]
0x180017d16  mov     qword ptr [rbp+0], 0
0x180017d1e  mov     dword ptr [r15], 0
0x180017d25  test    r14, r14
0x180017d28  jz      short loc_180017D43
0x180017d2a  test    rsi, rsi
0x180017d2d  jz      short loc_180017D43
0x180017d2f  mov     qword ptr [r14], 0
0x180017d36  mov     eax, 1
0x180017d3b  mov     dword ptr [rsi], 0
0x180017d41  jmp     short loc_180017D45
0x180017d43  xor     eax, eax
0x180017d45  mov     r8d, 3Ch ; '<'; unsigned int
0x180017d4b  mov     [rdi+8Ch], eax
0x180017d51  lea     rdx, aTxlisttimeouti; "TxListTimeoutInS"
0x180017d58  call    ?GetLocalDTCProfileIntExW@@YAKPEBG0K@Z; GetLocalDTCProfileIntExW(ushort const *,ushort const *,ulong)
0x180017d5d  mov     rcx, rdi; this
0x180017d60  mov     r12d, eax
0x180017d63  call    ?StartConnection@CDtcTransactionsConfig@@AEAAJXZ; CDtcTransactionsConfig::StartConnection(void)
0x180017d68  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017d6f  mov     ebx, eax
0x180017d71  mov     ecx, 0Fh
0x180017d76  test    eax, eax
0x180017d78  jns     short loc_180017DAB
0x180017d7a  lea     rax, aStartconnectio; " StartConnection failed"
0x180017d81  mov     r9d, 123h
0x180017d87  mov     [rsp+78h+var_48], rax
0x180017d8c  mov     edx, 1
0x180017d91  lea     rax, aCdtctransactio_7; "CDtcTransactionsConfig::GetTransactions"...
0x180017d98  mov     dword ptr [rsp+78h+var_50], ebx
0x180017d9c  mov     [rsp+78h+var_58], rax
0x180017da1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017da6  jmp     loc_180017EAC
0x180017dab  lea     rax, aConnectionStar; "Connection started."
0x180017db2  mov     r9d, 127h
0x180017db8  mov     [rsp+78h+var_48], rax
0x180017dbd  mov     edx, 3
0x180017dc2  lea     rax, aCdtctransactio_7; "CDtcTransactionsConfig::GetTransactions"...
0x180017dc9  mov     [rsp+78h+var_50], 0
0x180017dd2  mov     [rsp+78h+var_58], rax
0x180017dd7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017ddc  mov     rcx, [rdi+38h]; hHandle
0x180017de0  imul    edx, r12d, 3E8h; dwMilliseconds
0x180017de7  call    cs:__imp_WaitForSingleObject
0x180017ded  test    eax, eax
0x180017def  jz      short loc_180017E31
0x180017df1  cmp     eax, 0FFFFFFFFh
0x180017df4  jnz     short loc_180017E29
0x180017df6  call    cs:__imp_GetLastError
0x180017dfc  mov     ebx, eax
0x180017dfe  test    eax, eax
0x180017e00  jle     short loc_180017E0B
0x180017e02  movzx   ebx, ax
0x180017e05  or      ebx, 80070000h
0x180017e0b  lea     rax, aWaitforsingleo_2; " WaitForSingleObject failed while waiti"...
0x180017e12  mov     r9d, 135h
0x180017e18  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017e1f  mov     ecx, 0Fh
0x180017e24  jmp     loc_180017D87
0x180017e29  test    eax, eax
0x180017e2b  jg      short loc_180017E02
0x180017e2d  mov     ebx, eax
0x180017e2f  jmp     short loc_180017E0B
0x180017e31  mov     edx, 3
0x180017e36  lea     rax, aDataReceiveSig; "Data receive signaled."
0x180017e3d  mov     [rsp+78h+var_48], rax
0x180017e42  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017e49  lea     rax, aCdtctransactio_7; "CDtcTransactionsConfig::GetTransactions"...
0x180017e50  mov     [rsp+78h+var_50], 0
0x180017e59  mov     r9d, 139h
0x180017e5f  mov     [rsp+78h+var_58], rax
0x180017e64  lea     ecx, [rdx+0Ch]
0x180017e67  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017e6c  mov     rax, [rdi+48h]
0x180017e70  mov     [rbp+0], rax
0x180017e74  mov     dword ptr [r15], 60h ; '`'
0x180017e7b  cmp     dword ptr [rdi+8Ch], 1
0x180017e82  jnz     short loc_180017E9C
0x180017e84  mov     rax, [rdi+40h]
0x180017e88  mov     [r14], rax
0x180017e8b  mov     rax, [rdi+40h]
0x180017e8f  neg     rax
0x180017e92  sbb     ecx, ecx
0x180017e94  and     ecx, 148h
0x180017e9a  mov     [rsi], ecx
0x180017e9c  mov     qword ptr [rdi+48h], 0
0x180017ea4  mov     qword ptr [rdi+40h], 0
0x180017eac  mov     rcx, rdi; this
0x180017eaf  call    ?ReleaseConnection@CDtcTransactionsConfig@@AEAAJXZ; CDtcTransactionsConfig::ReleaseConnection(void)
0x180017eb4  mov     edx, 6
0x180017eb9  lea     rax, aOut; "Out"
0x180017ec0  mov     [rsp+78h+var_48], rax
0x180017ec5  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017ecc  lea     rax, aCdtctransactio_7; "CDtcTransactionsConfig::GetTransactions"...
0x180017ed3  mov     dword ptr [rsp+78h+var_50], ebx
0x180017ed7  mov     r9d, 147h
0x180017edd  mov     [rsp+78h+var_58], rax
0x180017ee2  lea     ecx, [rdx+9]
0x180017ee5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017eea  mov     eax, ebx
0x180017eec  add     rsp, 40h
0x180017ef0  pop     r15
0x180017ef2  pop     r14
0x180017ef4  pop     r12
0x180017ef6  pop     rdi
0x180017ef7  pop     rsi
0x180017ef8  pop     rbp
0x180017ef9  pop     rbx
0x180017efa  retn
```
