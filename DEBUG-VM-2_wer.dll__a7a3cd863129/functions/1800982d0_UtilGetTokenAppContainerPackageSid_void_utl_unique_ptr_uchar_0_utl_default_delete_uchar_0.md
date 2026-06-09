# UtilGetTokenAppContainerPackageSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x1800982d0`
- end: `0x18009853b`
- name: `?UtilGetTokenAppContainerPackageSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097ce0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c650`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18003bf14`
- `0x18009737c`
- `0x1800982d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180098326`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180098326`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800983c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800983c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009845a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009845a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098342`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098450`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098342`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098450`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenAppContainerPackageSid(HANDLE TokenHandle, void **a2)
{
  void *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD LastError; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  PSID *v12; // rbx
  DWORD v13; // eax
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  PSID v17; // [rsp+70h] [rbp+30h] BYREF
  PSID *v18; // [rsp+78h] [rbp+38h] BYREF

  v18 = 0;
  TokenInformationLength = 0;
  v17 = 0;
  if ( a2 && TokenHandle )
  {
    v4 = *a2;
    *a2 = 0;
    if ( v4 )
      HeapFree(g_hWerheap, 0, v4);
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      v9 = -2147418113;
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      goto LABEL_30;
    }
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    if ( (_WORD)v9 == 122 )
    {
      if ( TokenInformationLength == 8 )
      {
        v9 = -2147020646;
        goto LABEL_30;
      }
      v12 = (PSID *)HeapAlloc(g_hWerheap, 0, TokenInformationLength);
      v18 = 0;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
      v15 = 0;
      v18 = v12;
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v15);
      if ( v12 )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenAppContainerSid,
               v12,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          v9 = UtilDuplicateSid(*v12, &v17);
          if ( v9 >= 0 )
          {
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              a2,
              &v17);
            v9 = 0;
            goto LABEL_30;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 24;
            goto LABEL_10;
          }
        }
        else
        {
          v13 = GetLastError();
          v9 = ERROR_HR_FROM_WIN32(v13);
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 23;
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
            22,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            TokenInformationLength);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 21;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v9);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
LABEL_30:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v17);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800982d0  mov     [rsp-18h+arg_0], rbx
0x1800982d5  push    rbp
0x1800982d6  push    rsi
0x1800982d7  push    rdi
0x1800982d8  mov     rbp, rsp
0x1800982db  sub     rsp, 40h
0x1800982df  mov     rdi, rdx
0x1800982e2  mov     rsi, rcx
0x1800982e5  mov     [rbp+arg_18], 0
0x1800982ed  mov     [rbp+TokenInformationLength], 0
0x1800982f4  mov     [rbp+arg_10], 0
0x1800982fc  test    rdx, rdx
0x1800982ff  jz      loc_1800984E5
0x180098305  test    rcx, rcx
0x180098308  jz      loc_1800984E5
0x18009830e  mov     r8, [rdx]; lpMem
0x180098311  mov     qword ptr [rdx], 0
0x180098318  test    r8, r8
0x18009831b  jz      short loc_18009832C
0x18009831d  xor     edx, edx; dwFlags
0x18009831f  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180098326  call    cs:__imp_HeapFree
0x18009832c  lea     rax, [rbp+TokenInformationLength]
0x180098330  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180098335  xor     r9d, r9d; TokenInformationLength
0x180098338  xor     r8d, r8d; TokenInformation
0x18009833b  lea     edx, [r9+1Fh]; TokenInformationClass
0x18009833f  mov     rcx, rsi; TokenHandle
0x180098342  call    cs:__imp_GetTokenInformation
0x180098348  test    eax, eax
0x18009834a  jnz     loc_1800984D9
0x180098350  call    cs:__imp_GetLastError
0x180098356  mov     ecx, eax; unsigned int
0x180098358  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009835d  mov     ebx, eax
0x18009835f  cmp     ax, 7Ah ; 'z'
0x180098363  jz      short loc_1800983A3
0x180098365  lea     rax, WPP_GLOBAL_Control
0x18009836c  mov     rcx, cs:WPP_GLOBAL_Control
0x180098373  cmp     rcx, rax
0x180098376  jz      loc_180098519
0x18009837c  test    byte ptr [rcx+1Ch], 1
0x180098380  jz      loc_180098519
0x180098386  mov     edx, 15h
0x18009838b  mov     r9d, ebx
0x18009838e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180098395  mov     rcx, [rcx+10h]
0x180098399  call    WPP_SF_d
0x18009839e  jmp     loc_180098519
0x1800983a3  cmp     [rbp+TokenInformationLength], 8
0x1800983a7  jnz     short loc_1800983B3
0x1800983a9  mov     ebx, 8007109Ah
0x1800983ae  jmp     loc_180098519
0x1800983b3  mov     r8d, [rbp+TokenInformationLength]; dwBytes
0x1800983b7  xor     edx, edx; dwFlags
0x1800983b9  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800983c0  call    cs:__imp_HeapAlloc
0x1800983c6  mov     rbx, rax
0x1800983c9  mov     [rbp+arg_18], 0
0x1800983d1  lea     rcx, [rbp+arg_18]; void *
0x1800983d5  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800983da  mov     [rbp+var_10], 0
0x1800983e2  mov     [rbp+arg_18], rbx
0x1800983e6  lea     rcx, [rbp+var_10]; void *
0x1800983ea  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800983ef  test    rbx, rbx
0x1800983f2  jnz     short loc_180098438
0x1800983f4  mov     ebx, 8007000Eh
0x1800983f9  lea     rax, WPP_GLOBAL_Control
0x180098400  mov     rcx, cs:WPP_GLOBAL_Control
0x180098407  cmp     rcx, rax
0x18009840a  jz      loc_180098519
0x180098410  test    byte ptr [rcx+1Ch], 1
0x180098414  jz      loc_180098519
0x18009841a  mov     edx, 16h
0x18009841f  mov     r9d, [rbp+TokenInformationLength]
0x180098423  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009842a  mov     rcx, [rcx+10h]
0x18009842e  call    WPP_SF_d
0x180098433  jmp     loc_180098519
0x180098438  lea     rax, [rbp+TokenInformationLength]
0x18009843c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180098441  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180098445  mov     r8, rbx; TokenInformation
0x180098448  mov     edx, 1Fh; TokenInformationClass
0x18009844d  mov     rcx, rsi; TokenHandle
0x180098450  call    cs:__imp_GetTokenInformation
0x180098456  test    eax, eax
0x180098458  jnz     short loc_180098494
0x18009845a  call    cs:__imp_GetLastError
0x180098460  mov     ecx, eax; unsigned int
0x180098462  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098467  mov     ebx, eax
0x180098469  lea     rax, WPP_GLOBAL_Control
0x180098470  mov     rcx, cs:WPP_GLOBAL_Control
0x180098477  cmp     rcx, rax
0x18009847a  jz      loc_180098519
0x180098480  test    byte ptr [rcx+1Ch], 1
0x180098484  jz      loc_180098519
0x18009848a  mov     edx, 17h
0x18009848f  jmp     loc_18009838B
0x180098494  lea     rdx, [rbp+arg_10]
0x180098498  mov     rcx, [rbx]; pSourceSid
0x18009849b  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x1800984a0  mov     ebx, eax
0x1800984a2  test    eax, eax
0x1800984a4  jns     short loc_1800984C9
0x1800984a6  lea     rax, WPP_GLOBAL_Control
0x1800984ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800984b4  cmp     rcx, rax
0x1800984b7  jz      short loc_180098519
0x1800984b9  test    byte ptr [rcx+1Ch], 1
0x1800984bd  jz      short loc_180098519
0x1800984bf  mov     edx, 18h
0x1800984c4  jmp     loc_18009838B
0x1800984c9  lea     rdx, [rbp+arg_10]
0x1800984cd  mov     rcx, rdi
0x1800984d0  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x1800984d5  xor     ebx, ebx
0x1800984d7  jmp     short loc_180098519
0x1800984d9  mov     ebx, 8000FFFFh
0x1800984de  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800984e3  jmp     short loc_180098519
0x1800984e5  mov     ebx, 80070057h
0x1800984ea  lea     rax, WPP_GLOBAL_Control
0x1800984f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800984f8  cmp     rcx, rax
0x1800984fb  jz      short loc_180098519
0x1800984fd  test    byte ptr [rcx+1Ch], 1
0x180098501  jz      short loc_180098519
0x180098503  mov     edx, 14h
0x180098508  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009850f  mov     rcx, [rcx+10h]
0x180098513  call    WPP_SF_
0x180098518  nop
0x180098519  lea     rcx, [rbp+arg_10]; void *
0x18009851d  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180098522  nop
0x180098523  lea     rcx, [rbp+arg_18]; void *
0x180098527  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009852c  mov     eax, ebx
0x18009852e  mov     rbx, [rsp+40h+arg_0]
0x180098533  add     rsp, 40h
0x180098537  pop     rdi
0x180098538  pop     rsi
0x180098539  pop     rbp
0x18009853a  retn
```
