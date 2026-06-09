# CSecurity::GetSecurityDescriptorForHandle(void *,AutoDeleteVector<uchar> &)

- ea: `0x1800c6918`
- end: `0x1800c6a8d`
- name: `?GetSecurityDescriptorForHandle@CSecurity@@CAHPEAXAEAV?$AutoDeleteVector@E@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(struct IRequestContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c6320`

## callees

- `0x180005d10`
- `0x180013760`
- `0x1800621e0`
- `0x1800c6918`
- `0x1801123a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6a2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c69fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c69fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6a56`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800c6985`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800c69cf`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800c6985`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800c69cf`

## pseudocode

```c
__int64 __fastcall CSecurity::GetSecurityDescriptorForHandle(struct IRequestContext *a1, PSECURITY_DESCRIPTOR *a2)
{
  PSECURITY_DESCRIPTOR v5; // r8
  unsigned int KernelObjectSecurity; // esi
  __int64 v7; // rax
  DWORD LastError; // eax
  DWORD v9; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 702, L"702", 0x54Fu, 0);
    return 0;
  }
  AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(a2, 0);
  v5 = *a2;
  nLengthNeeded = 0;
  KernelObjectSecurity = GetKernelObjectSecurity(a1, 4u, v5, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v7 = WSManMemory::Alloc(nLengthNeeded, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(a2, v7);
    if ( !*a2 )
    {
      SetLastError(0xEu);
      return 0;
    }
    KernelObjectSecurity = GetKernelObjectSecurity(a1, 4u, *a2, nLengthNeeded, &nLengthNeeded);
    if ( !KernelObjectSecurity )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, LastError);
      }
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(a2, 0);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    v9 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v9);
  }
  return KernelObjectSecurity;
}

```

## disassembly

```asm
0x1800c6918  mov     [rsp+arg_8], rbx
0x1800c691d  mov     [rsp+arg_10], rsi
0x1800c6922  push    rdi
0x1800c6923  sub     rsp, 30h
0x1800c6927  mov     rbx, rdx
0x1800c692a  mov     rdi, rcx
0x1800c692d  test    rcx, rcx
0x1800c6930  jnz     short loc_1800C695C
0x1800c6932  mov     [rsp+38h+lpnLengthNeeded], rcx; struct IRequestContext *
0x1800c6937  lea     r8, a702; "702"
0x1800c693e  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x1800c6945  mov     r9d, 54Fh; unsigned int
0x1800c694b  mov     edx, 2BEh; unsigned int
0x1800c6950  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c6955  xor     eax, eax
0x1800c6957  jmp     loc_1800C6A7D
0x1800c695c  xor     edx, edx
0x1800c695e  mov     rcx, rbx
0x1800c6961  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1800c6966  mov     r8, [rbx]; pSecurityDescriptor
0x1800c6969  lea     rax, [rsp+38h+nLengthNeeded]
0x1800c696e  xor     r9d, r9d; nLength
0x1800c6971  mov     [rsp+38h+nLengthNeeded], 0
0x1800c6979  mov     rcx, rdi; Handle
0x1800c697c  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800c6981  lea     edx, [r9+4]; RequestedInformation
0x1800c6985  call    cs:__imp_GetKernelObjectSecurity
0x1800c698b  mov     esi, eax
0x1800c698d  mov     eax, [rsp+38h+nLengthNeeded]
0x1800c6991  test    eax, eax
0x1800c6993  jz      loc_1800C6A3A
0x1800c6999  mov     ecx, eax
0x1800c699b  xor     r8d, r8d
0x1800c699e  xor     edx, edx
0x1800c69a0  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800c69a5  mov     rdx, rax
0x1800c69a8  mov     rcx, rbx
0x1800c69ab  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1800c69b0  mov     r8, [rbx]; pSecurityDescriptor
0x1800c69b3  test    r8, r8
0x1800c69b6  jz      short loc_1800C6A2A
0x1800c69b8  mov     r9d, [rsp+38h+nLengthNeeded]; nLength
0x1800c69bd  lea     rax, [rsp+38h+nLengthNeeded]
0x1800c69c2  mov     edx, 4; RequestedInformation
0x1800c69c7  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800c69cc  mov     rcx, rdi; Handle
0x1800c69cf  call    cs:__imp_GetKernelObjectSecurity
0x1800c69d5  mov     esi, eax
0x1800c69d7  test    eax, eax
0x1800c69d9  jnz     loc_1800C6A7B
0x1800c69df  mov     rdx, cs:WPP_GLOBAL_Control
0x1800c69e6  lea     rcx, WPP_GLOBAL_Control
0x1800c69ed  cmp     rdx, rcx
0x1800c69f0  jz      short loc_1800C6A1E
0x1800c69f2  test    dword ptr [rdx+1Ch], 10000000h
0x1800c69f9  jz      short loc_1800C6A1E
0x1800c69fb  call    cs:__imp_GetLastError
0x1800c6a01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6a08  lea     edx, [rsi+21h]
0x1800c6a0b  mov     r9d, eax
0x1800c6a0e  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800c6a15  mov     rcx, [rcx+10h]
0x1800c6a19  call    WPP_SF_d
0x1800c6a1e  xor     edx, edx
0x1800c6a20  mov     rcx, rbx
0x1800c6a23  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1800c6a28  jmp     short loc_1800C6A7B
0x1800c6a2a  mov     ecx, 0Eh; dwErrCode
0x1800c6a2f  call    cs:__imp_SetLastError
0x1800c6a35  jmp     loc_1800C6955
0x1800c6a3a  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6a41  lea     rcx, WPP_GLOBAL_Control
0x1800c6a48  cmp     rax, rcx
0x1800c6a4b  jz      short loc_1800C6A7B
0x1800c6a4d  test    dword ptr [rax+1Ch], 10000000h
0x1800c6a54  jz      short loc_1800C6A7B
0x1800c6a56  call    cs:__imp_GetLastError
0x1800c6a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6a63  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800c6a6a  mov     edx, 22h ; '"'
0x1800c6a6f  mov     r9d, eax
0x1800c6a72  mov     rcx, [rcx+10h]
0x1800c6a76  call    WPP_SF_d
0x1800c6a7b  mov     eax, esi
0x1800c6a7d  mov     rbx, [rsp+38h+arg_8]
0x1800c6a82  mov     rsi, [rsp+38h+arg_10]
0x1800c6a87  add     rsp, 30h
0x1800c6a8b  pop     rdi
0x1800c6a8c  retn
```
