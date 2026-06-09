# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180098544`
- end: `0x18009878a`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009812c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c650`
- `0x18001daa8`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18003bf14`
- `0x18009737c`
- `0x180098544`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009859b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009859b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800985b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009869e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800985b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009869e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD LastError; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 unique_oversize_for; // rax
  PSID *v13; // rbx
  DWORD v14; // eax
  _BYTE v16[16]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  PSID v18; // [rsp+70h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+38h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  v18 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v9 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      goto LABEL_28;
    }
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v9 == 122 )
    {
      unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(v16, TokenInformationLength);
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        &TokenInformation,
        unique_oversize_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v16);
      v13 = (PSID *)TokenInformation;
      if ( TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               TokenInformation,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v9 = UtilDuplicateSid(*v13, &v18);
          if ( v9 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v18);
            v9 = 0;
            goto LABEL_28;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 14;
            goto LABEL_10;
          }
        }
        else
        {
          v14 = GetLastError();
          v9 = ERROR_HR_FROM_WIN32(v14);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 13;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v9 = -2147024882;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 11;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v9);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
LABEL_28:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&TokenInformation);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180098544  mov     [rsp-18h+arg_0], rbx
0x180098549  push    rbp
0x18009854a  push    rsi
0x18009854b  push    r14
0x18009854d  mov     rbp, rsp
0x180098550  sub     rsp, 40h
0x180098554  mov     rsi, rdx
0x180098557  mov     r14, rcx
0x18009855a  mov     [rbp+TokenInformation], 0
0x180098562  mov     [rbp+TokenInformationLength], 0
0x180098569  mov     [rbp+arg_10], 0
0x180098571  test    rdx, rdx
0x180098574  jz      loc_180098733
0x18009857a  test    rcx, rcx
0x18009857d  jz      loc_180098733
0x180098583  mov     r8, [rdx]; lpMem
0x180098586  mov     qword ptr [rdx], 0
0x18009858d  test    r8, r8
0x180098590  jz      short loc_1800985A1
0x180098592  xor     edx, edx; dwFlags
0x180098594  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18009859b  call    cs:__imp_HeapFree
0x1800985a1  lea     rax, [rbp+TokenInformationLength]
0x1800985a5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800985aa  xor     r9d, r9d; TokenInformationLength
0x1800985ad  xor     r8d, r8d; TokenInformation
0x1800985b0  lea     edx, [r9+1]; TokenInformationClass
0x1800985b4  mov     rcx, r14; TokenHandle
0x1800985b7  call    cs:__imp_GetTokenInformation
0x1800985bd  test    eax, eax
0x1800985bf  jnz     loc_180098727
0x1800985c5  call    cs:__imp_GetLastError
0x1800985cb  mov     ecx, eax; unsigned int
0x1800985cd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800985d2  mov     ebx, eax
0x1800985d4  cmp     ax, 7Ah ; 'z'
0x1800985d8  jz      short loc_180098618
0x1800985da  lea     rax, WPP_GLOBAL_Control
0x1800985e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800985e8  cmp     rcx, rax
0x1800985eb  jz      loc_180098767
0x1800985f1  test    byte ptr [rcx+1Ch], 1
0x1800985f5  jz      loc_180098767
0x1800985fb  mov     edx, 0Bh
0x180098600  mov     r9d, ebx
0x180098603  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009860a  mov     rcx, [rcx+10h]
0x18009860e  call    WPP_SF_d
0x180098613  jmp     loc_180098767
0x180098618  mov     edx, [rbp+TokenInformationLength]
0x18009861b  lea     rcx, [rbp+var_10]
0x18009861f  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180098624  mov     rdx, rax
0x180098627  lea     rcx, [rbp+TokenInformation]
0x18009862b  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180098630  lea     rcx, [rbp+var_10]; void *
0x180098634  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180098639  mov     rbx, [rbp+TokenInformation]
0x18009863d  test    rbx, rbx
0x180098640  jnz     short loc_180098686
0x180098642  mov     ebx, 8007000Eh
0x180098647  lea     rax, WPP_GLOBAL_Control
0x18009864e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098655  cmp     rcx, rax
0x180098658  jz      loc_180098767
0x18009865e  test    byte ptr [rcx+1Ch], 1
0x180098662  jz      loc_180098767
0x180098668  mov     edx, 0Ch
0x18009866d  mov     r9d, [rbp+TokenInformationLength]
0x180098671  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180098678  mov     rcx, [rcx+10h]
0x18009867c  call    WPP_SF_d
0x180098681  jmp     loc_180098767
0x180098686  lea     rax, [rbp+TokenInformationLength]
0x18009868a  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18009868f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180098693  mov     r8, rbx; TokenInformation
0x180098696  mov     edx, 1; TokenInformationClass
0x18009869b  mov     rcx, r14; TokenHandle
0x18009869e  call    cs:__imp_GetTokenInformation
0x1800986a4  test    eax, eax
0x1800986a6  jnz     short loc_1800986E2
0x1800986a8  call    cs:__imp_GetLastError
0x1800986ae  mov     ecx, eax; unsigned int
0x1800986b0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800986b5  mov     ebx, eax
0x1800986b7  lea     rax, WPP_GLOBAL_Control
0x1800986be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800986c5  cmp     rcx, rax
0x1800986c8  jz      loc_180098767
0x1800986ce  test    byte ptr [rcx+1Ch], 1
0x1800986d2  jz      loc_180098767
0x1800986d8  mov     edx, 0Dh
0x1800986dd  jmp     loc_180098600
0x1800986e2  lea     rdx, [rbp+arg_10]
0x1800986e6  mov     rcx, [rbx]; pSourceSid
0x1800986e9  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x1800986ee  mov     ebx, eax
0x1800986f0  test    eax, eax
0x1800986f2  jns     short loc_180098717
0x1800986f4  lea     rax, WPP_GLOBAL_Control
0x1800986fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180098702  cmp     rcx, rax
0x180098705  jz      short loc_180098767
0x180098707  test    byte ptr [rcx+1Ch], 1
0x18009870b  jz      short loc_180098767
0x18009870d  mov     edx, 0Eh
0x180098712  jmp     loc_180098600
0x180098717  lea     rdx, [rbp+arg_10]
0x18009871b  mov     rcx, rsi
0x18009871e  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180098723  xor     ebx, ebx
0x180098725  jmp     short loc_180098767
0x180098727  mov     ebx, 8000FFFFh
0x18009872c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180098731  jmp     short loc_180098767
0x180098733  mov     ebx, 80070057h
0x180098738  lea     rax, WPP_GLOBAL_Control
0x18009873f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098746  cmp     rcx, rax
0x180098749  jz      short loc_180098767
0x18009874b  test    byte ptr [rcx+1Ch], 1
0x18009874f  jz      short loc_180098767
0x180098751  mov     edx, 0Ah
0x180098756  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009875d  mov     rcx, [rcx+10h]
0x180098761  call    WPP_SF_
0x180098766  nop
0x180098767  lea     rcx, [rbp+arg_10]; void *
0x18009876b  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180098770  nop
0x180098771  lea     rcx, [rbp+TokenInformation]; void *
0x180098775  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009877a  mov     eax, ebx
0x18009877c  mov     rbx, [rsp+40h+arg_0]
0x180098781  add     rsp, 40h
0x180098785  pop     r14
0x180098787  pop     rsi
0x180098788  pop     rbp
0x180098789  retn
```
