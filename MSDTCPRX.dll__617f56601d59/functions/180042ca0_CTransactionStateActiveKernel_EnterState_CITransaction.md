# CTransactionStateActiveKernel::EnterState(CITransaction *)

- ea: `0x180042ca0`
- end: `0x180042f81`
- name: `?EnterState@CTransactionStateActiveKernel@@UEAAJPEAVCITransaction@@@Z`
- size: `737`
- prototype: `int(CTransactionStateActiveKernel *__hidden this, struct CITransaction *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000ee9c`
- `0x1800104c0`
- `0x180028d40`
- `0x180029434`
- `0x1800429a0`
- `0x180042ca0`
- `0x180044280`
- `0x1800446f4`
- `0x180081dd0`

## import_xrefs

- `ntdll!NtSetInformationTransaction` at `0x180042eaf`
- `ntdll!NtSetInformationTransaction` at `0x180042f30`
- `ntdll!NtSetInformationTransaction` at `0x180042eaf`
- `ntdll!NtSetInformationTransaction` at `0x180042f30`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180042d01`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180042d01`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042e52`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042e52`
- `ktmw32!PrivCreateTransaction` at `0x180042e87`
- `ktmw32!PrivCreateTransaction` at `0x180042e87`

## string_xrefs

- `0x180042d9a`: `com\complus\dtc\dtc\msdtcprx\src\transactionstate.cpp`
- `0x180042e0a`: `com\complus\dtc\dtc\msdtcprx\src\transactionstate.cpp`
- `0x180042ee6`: `com\complus\dtc\dtc\msdtcprx\src\transactionstate.cpp`
- `0x180042f5c`: `com\complus\dtc\dtc\msdtcprx\src\transactionstate.cpp`

## pseudocode

```c
int __fastcall CTransactionStateActiveKernel::EnterState(CTransactionStateActiveKernel *this, struct CITransaction *a2)
{
  char *v2; // rsi
  unsigned __int64 v4; // rax
  int result; // eax
  CTimeoutTableRow *TimeoutTableRowReference; // rax
  unsigned int v7; // r14d
  CTimeoutTableRow *v8; // r8
  int KtmRmTmHandle; // edi
  void *v10; // r15
  __int64 v11; // r9
  __int64 Transaction; // rax
  int v13; // edi
  const wchar_t *v14; // rax
  __int64 v15; // r9
  int v16; // ebx
  int v17; // ebx
  __int64 cchWideChar; // [rsp+28h] [rbp-81h]
  __int64 cchWideChara; // [rsp+28h] [rbp-81h]
  void *v20; // [rsp+40h] [rbp-69h] BYREF
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+48h] [rbp-61h] BYREF
  void *v22; // [rsp+50h] [rbp-59h] BYREF
  struct _GUID v23; // [rsp+58h] [rbp-51h] BYREF
  WCHAR WideCharStr[40]; // [rsp+70h] [rbp-39h] BYREF

  v2 = (char *)a2 + 1112;
  v20 = (void *)-1LL;
  v23 = GUID_NULL;
  v4 = *(_QWORD *)&GUID_NULL.Data1 - *((_QWORD *)a2 + 139);
  if ( *(_QWORD *)&GUID_NULL.Data1 == *((_QWORD *)a2 + 139) )
    v4 = _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0] - *((_QWORD *)a2 + 140);
  if ( v4 || (result = CoCreateGuid((GUID *)((char *)a2 + 1112))) == 0 )
  {
    TimeoutTableRowReference = CITransaction::GetTimeoutTableRowReference(a2);
    v7 = 0;
    if ( TimeoutTableRowReference )
    {
      v7 = CTimeoutTableRow::CalculateAdjustedTimeout(TimeoutTableRowReference);
      if ( !v7 )
      {
        CITransaction::ChangeState(a2, (struct CTransactionState *)&g_CTransactionStateAborted);
        return -2147168231;
      }
      CTimeoutTableRow::Release(v8);
    }
    v21 = 0;
    result = CITransaction::GetTransactionSecurityAttributes(&v21);
    if ( !result )
    {
      KtmRmTmHandle = CTmProxyCore::GetKtmRmTmHandle(*((CTmProxyCore **)a2 + 29), 0, &v20);
      if ( KtmRmTmHandle < 0 )
      {
        LODWORD(cchWideChar) = KtmRmTmHandle;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\transactionstate.cpp",
          1589,
          L"CTransactionStateActiveKernel::EnterState",
          cchWideChar,
          L"Error from GetKtmRmTmHandle");
        CITransaction::ChangeState(a2, (struct CTransactionState *)&g_CTransactionStateAborting);
        return KtmRmTmHandle;
      }
      v10 = v20;
      if ( v20 == (void *)-1LL )
      {
        LODWORD(cchWideChar) = KtmRmTmHandle;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\transactionstate.cpp",
          1596,
          L"CTransactionStateActiveKernel::EnterState",
          cchWideChar,
          L"Unable to obtain KtmRm TM Handle.");
      }
      else
      {
        WideCharStr[0] = 0;
        MultiByteToWideChar(0, 0, (LPCCH)a2 + 188, 40, WideCharStr, 40);
        v11 = *((unsigned int *)a2 + 44);
        WideCharStr[39] = 0;
        Transaction = PrivCreateTransaction(v21, v2, 0, v11, *((_DWORD *)a2 + 45), v7, WideCharStr);
        *((_QWORD *)a2 + 128) = Transaction;
        if ( Transaction != -1 )
        {
          v22 = v10;
          v13 = NtSetInformationTransaction(Transaction, 4, &v22);
          if ( v13 )
          {
            KtmRmTmHandle = v13 | 0x10000000;
            v14 = L"CTransactionStateActiveKernel::EnterState - error from NtSetInformationTransaction";
            v15 = 1637;
          }
          else
          {
            KtmRmTmHandle = CITransaction::GetKtmCookie(a2, &v23);
            if ( KtmRmTmHandle >= 0 )
            {
              v16 = NtSetInformationTransaction(*((_QWORD *)a2 + 128), 5, &v23);
              if ( v16 )
              {
                v17 = v16 | 0x10000000;
                LODWORD(cchWideChara) = v17;
                TraceStringInline(
                  15,
                  1,
                  L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\transactionstate.cpp",
                  1659,
                  L"CTransactionStateActiveKernel::EnterState",
                  cchWideChara,
                  L"error from NtSetInformationTransaction - TM id");
                return v17;
              }
              return KtmRmTmHandle;
            }
            v14 = L"error from GetKtmCookie";
            v15 = 1645;
          }
          LODWORD(cchWideChara) = KtmRmTmHandle;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\transactionstate.cpp",
            v15,
            L"CTransactionStateActiveKernel::EnterState",
            cchWideChara,
            v14);
          return KtmRmTmHandle;
        }
      }
      return CITransaction::ChangeState(a2, (struct CTransactionState *)&g_CTransactionStateAborting);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180042ca0  push    rbp
0x180042ca2  push    rbx
0x180042ca3  push    rsi
0x180042ca4  push    rdi
0x180042ca5  push    r14
0x180042ca7  push    r15
0x180042ca9  lea     rbp, [rsp-2Fh]
0x180042cae  sub     rsp, 0D8h
0x180042cb5  mov     rax, cs:__security_cookie
0x180042cbc  xor     rax, rsp
0x180042cbf  mov     [rbp+57h+var_40], rax
0x180042cc3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042cca  lea     rsi, [rdx+458h]
0x180042cd1  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFFh
0x180042cd9  mov     rbx, rdx
0x180042cdc  movq    rax, xmm0
0x180042ce1  movdqu  xmmword ptr [rbp+57h+var_A8.Data1], xmm0
0x180042ce6  sub     rax, [rsi]
0x180042ce9  jnz     short loc_180042CF9
0x180042ceb  psrldq  xmm0, 8
0x180042cf0  movq    rax, xmm0
0x180042cf5  sub     rax, [rsi+8]
0x180042cf9  test    rax, rax
0x180042cfc  jnz     short loc_180042D0F
0x180042cfe  mov     rcx, rsi; pguid
0x180042d01  call    cs:__imp_CoCreateGuid
0x180042d07  test    eax, eax
0x180042d09  jnz     loc_180042DC3
0x180042d0f  mov     rcx, rbx; this
0x180042d12  call    ?GetTimeoutTableRowReference@CITransaction@@QEAAPEAVCTimeoutTableRow@@XZ; CITransaction::GetTimeoutTableRowReference(void)
0x180042d17  xor     r14d, r14d
0x180042d1a  mov     r8, rax
0x180042d1d  test    rax, rax
0x180042d20  jz      short loc_180042D4F
0x180042d22  mov     rcx, rax; this
0x180042d25  call    ?CalculateAdjustedTimeout@CTimeoutTableRow@@QEAAKXZ; CTimeoutTableRow::CalculateAdjustedTimeout(void)
0x180042d2a  mov     r14d, eax
0x180042d2d  test    eax, eax
0x180042d2f  jnz     short loc_180042D47
0x180042d31  lea     rdx, ?g_CTransactionStateAborted@@3VCTransactionStateAborted@@A; struct CTransactionState *
0x180042d38  mov     rcx, rbx; this
0x180042d3b  call    ?ChangeState@CITransaction@@AEAAJPEAVCTransactionState@@@Z; CITransaction::ChangeState(CTransactionState *)
0x180042d40  mov     eax, 8004D019h
0x180042d45  jmp     short loc_180042DC3
0x180042d47  mov     rcx, r8; this
0x180042d4a  call    ?Release@CTimeoutTableRow@@QEAAXXZ; CTimeoutTableRow::Release(void)
0x180042d4f  lea     rcx, [rbp+57h+var_B8]; struct _SECURITY_ATTRIBUTES **
0x180042d53  mov     [rbp+57h+var_B8], 0
0x180042d5b  call    ?GetTransactionSecurityAttributes@CITransaction@@SAJPEAPEAU_SECURITY_ATTRIBUTES@@@Z; CITransaction::GetTransactionSecurityAttributes(_SECURITY_ATTRIBUTES * *)
0x180042d60  test    eax, eax
0x180042d62  jnz     short loc_180042DC3
0x180042d64  mov     rcx, [rbx+0E8h]; this
0x180042d6b  lea     r8, [rbp+57h+var_C0]; void **
0x180042d6f  xor     edx, edx; int
0x180042d71  call    ?GetKtmRmTmHandle@CTmProxyCore@@QEAAJHPEAPEAX@Z; CTmProxyCore::GetKtmRmTmHandle(int,void * *)
0x180042d76  mov     edi, eax
0x180042d78  test    eax, eax
0x180042d7a  jns     short loc_180042DDF
0x180042d7c  lea     rcx, aCtransactionst_3; "CTransactionStateActiveKernel::EnterSta"...
0x180042d83  mov     edx, 1
0x180042d88  lea     rax, aErrorFromGetkt_0; "Error from GetKtmRmTmHandle"
0x180042d8f  mov     r9d, 635h
0x180042d95  mov     [rsp+100h+var_D0], rax
0x180042d9a  lea     r8, aComComplusDtcD_43; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180042da1  mov     dword ptr [rsp+100h+cchWideChar], edi
0x180042da5  mov     [rsp+100h+lpWideCharStr], rcx
0x180042daa  lea     ecx, [rdx+0Eh]
0x180042dad  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180042db2  lea     rdx, ?g_CTransactionStateAborting@@3VCTransactionStateAborting@@A; struct CTransactionState *
0x180042db9  mov     rcx, rbx; this
0x180042dbc  call    ?ChangeState@CITransaction@@AEAAJPEAVCTransactionState@@@Z; CITransaction::ChangeState(CTransactionState *)
0x180042dc1  mov     eax, edi
0x180042dc3  mov     rcx, [rbp+57h+var_40]
0x180042dc7  xor     rcx, rsp; StackCookie
0x180042dca  call    __security_check_cookie
0x180042dcf  add     rsp, 0D8h
0x180042dd6  pop     r15
0x180042dd8  pop     r14
0x180042dda  pop     rdi
0x180042ddb  pop     rsi
0x180042ddc  pop     rbx
0x180042ddd  pop     rbp
0x180042dde  retn
0x180042ddf  mov     r15, [rbp+57h+var_C0]
0x180042de3  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180042de7  jnz     short loc_180042E2F
0x180042de9  lea     rcx, aCtransactionst_3; "CTransactionStateActiveKernel::EnterSta"...
0x180042df0  mov     r9d, 63Ch
0x180042df6  lea     rax, aUnableToObtain_0; "Unable to obtain KtmRm TM Handle."
0x180042dfd  mov     [rsp+100h+var_D0], rax
0x180042e02  lea     edx, [r15+2]
0x180042e06  mov     dword ptr [rsp+100h+cchWideChar], edi
0x180042e0a  lea     r8, aComComplusDtcD_43; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180042e11  mov     [rsp+100h+lpWideCharStr], rcx
0x180042e16  lea     ecx, [rdx+0Eh]
0x180042e19  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180042e1e  lea     rdx, ?g_CTransactionStateAborting@@3VCTransactionStateAborting@@A; struct CTransactionState *
0x180042e25  mov     rcx, rbx; this
0x180042e28  call    ?ChangeState@CITransaction@@AEAAJPEAVCTransactionState@@@Z; CITransaction::ChangeState(CTransactionState *)
0x180042e2d  jmp     short loc_180042DC3
0x180042e2f  xor     eax, eax
0x180042e31  lea     r8, [rbx+0BCh]; lpMultiByteStr
0x180042e38  mov     [rbp+57h+WideCharStr], ax
0x180042e3c  xor     edx, edx; dwFlags
0x180042e3e  xor     ecx, ecx; CodePage
0x180042e40  lea     r9d, [rax+28h]; cbMultiByte
0x180042e44  lea     rax, [rbp+57h+WideCharStr]
0x180042e48  mov     dword ptr [rsp+100h+cchWideChar], r9d; cchWideChar
0x180042e4d  mov     [rsp+100h+lpWideCharStr], rax; lpWideCharStr
0x180042e52  call    cs:__imp_MultiByteToWideChar
0x180042e58  mov     r9d, [rbx+0B0h]
0x180042e5f  xor     eax, eax
0x180042e61  mov     rcx, [rbp+57h+var_B8]
0x180042e65  xor     r8d, r8d
0x180042e68  mov     [rbp+57h+var_42], ax
0x180042e6c  mov     rdx, rsi
0x180042e6f  lea     rax, [rbp+57h+WideCharStr]
0x180042e73  mov     [rsp+100h+var_D0], rax
0x180042e78  mov     eax, [rbx+0B4h]
0x180042e7e  mov     dword ptr [rsp+100h+cchWideChar], r14d
0x180042e83  mov     dword ptr [rsp+100h+lpWideCharStr], eax
0x180042e87  call    cs:__imp_PrivCreateTransaction
0x180042e8d  mov     [rbx+400h], rax
0x180042e94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042e98  jz      short loc_180042E1E
0x180042e9a  mov     r9d, 8
0x180042ea0  mov     [rbp+57h+var_B0], r15
0x180042ea4  lea     r8, [rbp+57h+var_B0]
0x180042ea8  mov     rcx, rax
0x180042eab  lea     edx, [r9-4]
0x180042eaf  call    cs:__imp_NtSetInformationTransaction
0x180042eb5  mov     edi, eax
0x180042eb7  test    eax, eax
0x180042eb9  jz      short loc_180042EFA
0x180042ebb  bts     edi, 1Ch
0x180042ebf  lea     rax, aCtransactionst_15; "CTransactionStateActiveKernel::EnterSta"...
0x180042ec6  mov     r9d, 665h
0x180042ecc  mov     [rsp+100h+var_D0], rax
0x180042ed1  lea     rcx, aCtransactionst_3; "CTransactionStateActiveKernel::EnterSta"...
0x180042ed8  mov     edx, 1
0x180042edd  mov     dword ptr [rsp+100h+cchWideChar], edi
0x180042ee1  mov     [rsp+100h+lpWideCharStr], rcx
0x180042ee6  lea     r8, aComComplusDtcD_43; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180042eed  lea     ecx, [rdx+0Eh]
0x180042ef0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180042ef5  jmp     loc_180042DC1
0x180042efa  lea     rdx, [rbp+57h+var_A8]; struct _GUID *
0x180042efe  mov     rcx, rbx; this
0x180042f01  call    ?GetKtmCookie@CITransaction@@AEAAJPEAU_GUID@@@Z; CITransaction::GetKtmCookie(_GUID *)
0x180042f06  mov     edi, eax
0x180042f08  test    eax, eax
0x180042f0a  jns     short loc_180042F1B
0x180042f0c  lea     rax, aErrorFromGetkt; "error from GetKtmCookie"
0x180042f13  mov     r9d, 66Dh
0x180042f19  jmp     short loc_180042ECC
0x180042f1b  mov     rcx, [rbx+400h]
0x180042f22  lea     r8, [rbp+57h+var_A8]
0x180042f26  mov     r9d, 10h
0x180042f2c  lea     edx, [r9-0Bh]
0x180042f30  call    cs:__imp_NtSetInformationTransaction
0x180042f36  mov     ebx, eax
0x180042f38  test    eax, eax
0x180042f3a  jz      loc_180042DC1
0x180042f40  lea     rcx, aCtransactionst_3; "CTransactionStateActiveKernel::EnterSta"...
0x180042f47  mov     edx, 1
0x180042f4c  lea     rax, aErrorFromNtset_0; "error from NtSetInformationTransaction "...
0x180042f53  bts     ebx, 1Ch
0x180042f57  mov     [rsp+100h+var_D0], rax
0x180042f5c  lea     r8, aComComplusDtcD_43; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180042f63  mov     dword ptr [rsp+100h+cchWideChar], ebx
0x180042f67  mov     r9d, 67Bh
0x180042f6d  mov     [rsp+100h+lpWideCharStr], rcx
0x180042f72  lea     ecx, [rdx+0Eh]
0x180042f75  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180042f7a  mov     eax, ebx
0x180042f7c  jmp     loc_180042DC3
```
