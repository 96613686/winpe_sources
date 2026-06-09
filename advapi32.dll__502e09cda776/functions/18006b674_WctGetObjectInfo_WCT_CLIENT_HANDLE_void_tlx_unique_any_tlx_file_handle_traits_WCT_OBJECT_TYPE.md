# WctGetObjectInfo(_WCT_CLIENT_HANDLE *,void *,tlx::unique_any<tlx::file_handle_traits> *,_WCT_OBJECT_TYPE *)

- ea: `0x18006b674`
- end: `0x18006b9dd`
- name: `?WctGetObjectInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAW4_WCT_OBJECT_TYPE@@@Z`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18006ae08`

## callees

- `0x18003faec`
- `0x18003fb18`
- `0x18003fcdc`
- `0x18003fd04`
- `0x18004165c`
- `0x18006a520`
- `0x18006b674`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18006b831`
- `ntdll!RtlEqualUnicodeString` at `0x18006b86e`
- `ntdll!RtlEqualUnicodeString` at `0x18006b8ad`
- `ntdll!RtlEqualUnicodeString` at `0x18006b8e7`
- `ntdll!RtlEqualUnicodeString` at `0x18006b831`
- `ntdll!RtlEqualUnicodeString` at `0x18006b86e`
- `ntdll!RtlEqualUnicodeString` at `0x18006b8ad`
- `ntdll!RtlEqualUnicodeString` at `0x18006b8e7`
- `ntdll!NtQueryObject` at `0x18006b77e`
- `ntdll!NtQueryObject` at `0x18006b7f7`
- `ntdll!NtQueryObject` at `0x18006b77e`
- `ntdll!NtQueryObject` at `0x18006b7f7`
- `ntdll!RtlNtStatusToDosError` at `0x18006b793`
- `ntdll!RtlNtStatusToDosError` at `0x18006b793`
- `ntdll!RtlInitUnicodeString` at `0x18006b81b`
- `ntdll!RtlInitUnicodeString` at `0x18006b858`
- `ntdll!RtlInitUnicodeString` at `0x18006b897`
- `ntdll!RtlInitUnicodeString` at `0x18006b8d1`
- `ntdll!RtlInitUnicodeString` at `0x18006b81b`
- `ntdll!RtlInitUnicodeString` at `0x18006b858`
- `ntdll!RtlInitUnicodeString` at `0x18006b897`
- `ntdll!RtlInitUnicodeString` at `0x18006b8d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b90f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b90f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b6e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b6e2`
- `KERNEL32!GetLastError` at `0x18006b945`
- `KERNEL32!GetLastError` at `0x18006b945`
- `KERNEL32!DuplicateHandle` at `0x18006b740`
- `KERNEL32!DuplicateHandle` at `0x18006b933`
- `KERNEL32!DuplicateHandle` at `0x18006b740`
- `KERNEL32!DuplicateHandle` at `0x18006b933`

## string_xrefs

- `0x18006b88c`: `Thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WctGetObjectInfo(__int64 a1, HANDLE a2, __int64 *a3, _DWORD *a4)
{
  DWORD dwDesiredAccess; // esi
  void *v9; // rcx
  __int64 v10; // rdx
  HANDLE CurrentProcess; // r13
  HANDLE *v12; // rbx
  HANDLE v13; // rax
  unsigned int v14; // edi
  int v15; // eax
  DWORD LastError; // eax
  __int64 v17; // rcx
  UNICODE_STRING *v18; // rbx
  HANDLE *v19; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  UNICODE_STRING *v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  ULONG ObjectInformationLength; // [rsp+A8h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+50h] BYREF

  dwDesiredAccess = 0;
  Handle = 0;
  v25 = 0;
  ObjectInformationLength = 0;
  DestinationString = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v10 = *a3;
  *a3 = 0;
  tlx::file_handle_traits::operator()(v9, v10);
  if ( a2 == GetCurrentThread() )
  {
    CurrentProcess = GetCurrentProcess();
    a2 = *(HANDLE *)a1;
  }
  else
  {
    CurrentProcess = *(HANDLE *)(a1 + 8);
  }
  v12 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
  v13 = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, a2, v13, v12, 0, 0, 2u) )
  {
LABEL_25:
    LastError = GetLastError();
LABEL_26:
    v14 = LastError;
    if ( LastError )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (unsigned __int64)Handle + 1 > 1 )
  {
    v15 = NtQueryObject(Handle, ObjectTypeInformation, 0, ObjectInformationLength, &ObjectInformationLength);
    if ( v15 != -1073741820 )
      goto LABEL_11;
    v18 = (UNICODE_STRING *)operator new(ObjectInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    v25 = 0;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v25);
    v26 = 0;
    v25 = v18;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v26);
    if ( !v18 )
    {
      v14 = 8;
      goto LABEL_30;
    }
    v15 = NtQueryObject(Handle, ObjectTypeInformation, v18, ObjectInformationLength, &ObjectInformationLength);
    if ( v15 < 0 )
    {
LABEL_11:
      LastError = RtlNtStatusToDosError(v15);
      goto LABEL_26;
    }
    v14 = 0;
    *a4 = 10;
    RtlInitUnicodeString(&DestinationString, L"Event");
    if ( RtlEqualUnicodeString(&DestinationString, v18, 0) )
    {
      *a4 = 1;
      goto LABEL_29;
    }
    RtlInitUnicodeString(&DestinationString, L"Mutant");
    if ( RtlEqualUnicodeString(&DestinationString, v18, 0) )
    {
      *a4 = 3;
      dwDesiredAccess = 2031617;
      goto LABEL_24;
    }
    RtlInitUnicodeString(&DestinationString, L"Thread");
    if ( RtlEqualUnicodeString(&DestinationString, v18, 0) )
    {
      *a4 = 6;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"Process");
      if ( !RtlEqualUnicodeString(&DestinationString, v18, 0) )
        goto LABEL_24;
      *a4 = 7;
    }
    dwDesiredAccess = 0x1FFFFF;
LABEL_24:
    v19 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
    v20 = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, a2, v20, v19, dwDesiredAccess, 0, 0) )
    {
      if ( Handle == (HANDLE)-1LL || (char *)Handle + 1 == HANDLE_FLAG_INHERIT )
        goto LABEL_9;
LABEL_29:
      v21 = Handle;
      Handle = 0;
      v22 = *a3;
      *a3 = (__int64)v21;
      tlx::file_handle_traits::operator()(v17, v22);
      goto LABEL_30;
    }
    goto LABEL_25;
  }
LABEL_9:
  v14 = 87;
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v14);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v25);
  tlx::file_handle_traits::operator()(v23, Handle);
  return v14;
}

```

## disassembly

```asm
0x18006b674  mov     [rsp-38h+arg_0], rbx
0x18006b679  push    rbp
0x18006b67a  push    rsi
0x18006b67b  push    rdi
0x18006b67c  push    r12
0x18006b67e  push    r13
0x18006b680  push    r14
0x18006b682  push    r15
0x18006b684  mov     rbp, rsp
0x18006b687  sub     rsp, 60h
0x18006b68b  mov     r14, r9
0x18006b68e  mov     r15, r8
0x18006b691  mov     r12, rdx
0x18006b694  mov     rbx, rcx
0x18006b697  xor     esi, esi
0x18006b699  mov     [rbp+Handle], rsi
0x18006b69d  mov     [rbp+var_20], rsi
0x18006b6a1  mov     [rbp+ObjectInformationLength], esi
0x18006b6a4  xorps   xmm0, xmm0
0x18006b6a7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006b6ab  lea     rax, WPP_GLOBAL_Control
0x18006b6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6b9  cmp     rcx, rax
0x18006b6bc  jz      short loc_18006B6D7
0x18006b6be  test    byte ptr [rcx+1Ch], 4
0x18006b6c2  jz      short loc_18006B6D7
0x18006b6c4  lea     edx, [rsi+18h]
0x18006b6c7  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006b6ce  mov     rcx, [rcx+10h]
0x18006b6d2  call    WPP_SF_
0x18006b6d7  mov     rdx, [r15]
0x18006b6da  mov     [r15], rsi
0x18006b6dd  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18006b6e2  call    cs:__imp_GetCurrentThread
0x18006b6e9  nop     dword ptr [rax+rax+00h]
0x18006b6ee  cmp     r12, rax
0x18006b6f1  jnz     short loc_18006B707
0x18006b6f3  call    cs:__imp_GetCurrentProcess
0x18006b6fa  nop     dword ptr [rax+rax+00h]
0x18006b6ff  mov     r13, rax
0x18006b702  mov     r12, [rbx]
0x18006b705  jmp     short loc_18006B70B
0x18006b707  mov     r13, [rbx+8]
0x18006b70b  lea     rcx, [rbp+Handle]
0x18006b70f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18006b714  mov     rbx, rax
0x18006b717  call    cs:__imp_GetCurrentProcess
0x18006b71e  nop     dword ptr [rax+rax+00h]
0x18006b723  mov     edi, 2
0x18006b728  mov     [rsp+60h+dwOptions], edi; dwOptions
0x18006b72c  mov     [rsp+60h+bInheritHandle], esi; bInheritHandle
0x18006b730  mov     [rsp+60h+dwDesiredAccess], esi; dwDesiredAccess
0x18006b734  mov     r9, rbx; lpTargetHandle
0x18006b737  mov     r8, rax; hTargetProcessHandle
0x18006b73a  mov     rdx, r12; hSourceHandle
0x18006b73d  mov     rcx, r13; hSourceProcessHandle
0x18006b740  call    cs:__imp_DuplicateHandle
0x18006b747  nop     dword ptr [rax+rax+00h]
0x18006b74c  test    eax, eax
0x18006b74e  jz      loc_18006B945
0x18006b754  mov     rcx, [rbp+Handle]; Handle
0x18006b758  lea     rax, [rcx+1]
0x18006b75c  cmp     rax, 1
0x18006b760  ja      short loc_18006B76C
0x18006b762  mov     edi, 57h ; 'W'
0x18006b767  jmp     loc_18006B97D
0x18006b76c  lea     rax, [rbp+ObjectInformationLength]
0x18006b770  mov     qword ptr [rsp+60h+dwDesiredAccess], rax; ReturnLength
0x18006b775  mov     r9d, [rbp+ObjectInformationLength]; ObjectInformationLength
0x18006b779  xor     r8d, r8d; ObjectInformation
0x18006b77c  mov     edx, edi; ObjectInformationClass
0x18006b77e  call    cs:__imp_NtQueryObject
0x18006b785  nop     dword ptr [rax+rax+00h]
0x18006b78a  cmp     eax, 0C0000004h
0x18006b78f  jz      short loc_18006B7A4
0x18006b791  mov     ecx, eax; Status
0x18006b793  call    cs:__imp_RtlNtStatusToDosError
0x18006b79a  nop     dword ptr [rax+rax+00h]
0x18006b79f  jmp     loc_18006B951
0x18006b7a4  mov     ecx, [rbp+ObjectInformationLength]; unsigned __int64
0x18006b7a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b7ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006b7b3  mov     rbx, rax
0x18006b7b6  mov     [rbp+var_20], rsi
0x18006b7ba  lea     rcx, [rbp+var_20]
0x18006b7be  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006b7c3  mov     [rbp+var_18], rsi
0x18006b7c7  mov     [rbp+var_20], rbx
0x18006b7cb  lea     rcx, [rbp+var_18]
0x18006b7cf  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006b7d4  test    rbx, rbx
0x18006b7d7  jnz     short loc_18006B7E1
0x18006b7d9  lea     edi, [rbx+8]
0x18006b7dc  jmp     loc_18006B97D
0x18006b7e1  lea     rax, [rbp+ObjectInformationLength]
0x18006b7e5  mov     qword ptr [rsp+60h+dwDesiredAccess], rax; ReturnLength
0x18006b7ea  mov     r9d, [rbp+ObjectInformationLength]; ObjectInformationLength
0x18006b7ee  mov     r8, rbx; ObjectInformation
0x18006b7f1  mov     edx, edi; ObjectInformationClass
0x18006b7f3  mov     rcx, [rbp+Handle]; Handle
0x18006b7f7  call    cs:__imp_NtQueryObject
0x18006b7fe  nop     dword ptr [rax+rax+00h]
0x18006b803  test    eax, eax
0x18006b805  js      short loc_18006B791
0x18006b807  mov     edi, esi
0x18006b809  mov     dword ptr [r14], 0Ah
0x18006b810  lea     rdx, aEvent; "Event"
0x18006b817  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006b81b  call    cs:__imp_RtlInitUnicodeString
0x18006b822  nop     dword ptr [rax+rax+00h]
0x18006b827  xor     r8d, r8d; CaseInsensitive
0x18006b82a  mov     rdx, rbx; String2
0x18006b82d  lea     rcx, [rbp+DestinationString]; String1
0x18006b831  call    cs:__imp_RtlEqualUnicodeString
0x18006b838  nop     dword ptr [rax+rax+00h]
0x18006b83d  test    al, al
0x18006b83f  jz      short loc_18006B84D
0x18006b841  mov     dword ptr [r14], 1
0x18006b848  jmp     loc_18006B96A
0x18006b84d  lea     rdx, aMutant; "Mutant"
0x18006b854  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006b858  call    cs:__imp_RtlInitUnicodeString
0x18006b85f  nop     dword ptr [rax+rax+00h]
0x18006b864  xor     r8d, r8d; CaseInsensitive
0x18006b867  mov     rdx, rbx; String2
0x18006b86a  lea     rcx, [rbp+DestinationString]; String1
0x18006b86e  call    cs:__imp_RtlEqualUnicodeString
0x18006b875  nop     dword ptr [rax+rax+00h]
0x18006b87a  test    al, al
0x18006b87c  jz      short loc_18006B88C
0x18006b87e  mov     dword ptr [r14], 3
0x18006b885  mov     esi, 1F0001h
0x18006b88a  jmp     short loc_18006B903
0x18006b88c  lea     rdx, aThread; "Thread"
0x18006b893  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006b897  call    cs:__imp_RtlInitUnicodeString
0x18006b89e  nop     dword ptr [rax+rax+00h]
0x18006b8a3  xor     r8d, r8d; CaseInsensitive
0x18006b8a6  mov     rdx, rbx; String2
0x18006b8a9  lea     rcx, [rbp+DestinationString]; String1
0x18006b8ad  call    cs:__imp_RtlEqualUnicodeString
0x18006b8b4  nop     dword ptr [rax+rax+00h]
0x18006b8b9  test    al, al
0x18006b8bb  jz      short loc_18006B8C6
0x18006b8bd  mov     dword ptr [r14], 6
0x18006b8c4  jmp     short loc_18006B8FE
0x18006b8c6  lea     rdx, aProcess; "Process"
0x18006b8cd  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006b8d1  call    cs:__imp_RtlInitUnicodeString
0x18006b8d8  nop     dword ptr [rax+rax+00h]
0x18006b8dd  xor     r8d, r8d; CaseInsensitive
0x18006b8e0  mov     rdx, rbx; String2
0x18006b8e3  lea     rcx, [rbp+DestinationString]; String1
0x18006b8e7  call    cs:__imp_RtlEqualUnicodeString
0x18006b8ee  nop     dword ptr [rax+rax+00h]
0x18006b8f3  test    al, al
0x18006b8f5  jz      short loc_18006B903
0x18006b8f7  mov     dword ptr [r14], 7
0x18006b8fe  mov     esi, 1FFFFFh
0x18006b903  lea     rcx, [rbp+Handle]
0x18006b907  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18006b90c  mov     rbx, rax
0x18006b90f  call    cs:__imp_GetCurrentProcess
0x18006b916  nop     dword ptr [rax+rax+00h]
0x18006b91b  mov     [rsp+60h+dwOptions], edi; dwOptions
0x18006b91f  mov     [rsp+60h+bInheritHandle], edi; bInheritHandle
0x18006b923  mov     [rsp+60h+dwDesiredAccess], esi; dwDesiredAccess
0x18006b927  mov     r9, rbx; lpTargetHandle
0x18006b92a  mov     r8, rax; hTargetProcessHandle
0x18006b92d  mov     rdx, r12; hSourceHandle
0x18006b930  mov     rcx, r13; hSourceProcessHandle
0x18006b933  call    cs:__imp_DuplicateHandle
0x18006b93a  nop     dword ptr [rax+rax+00h]
0x18006b93f  xor     esi, esi
0x18006b941  test    eax, eax
0x18006b943  jnz     short loc_18006B959
0x18006b945  call    cs:__imp_GetLastError
0x18006b94c  nop     dword ptr [rax+rax+00h]
0x18006b951  mov     edi, eax
0x18006b953  test    eax, eax
0x18006b955  jnz     short loc_18006B97D
0x18006b957  jmp     short loc_18006B96A
0x18006b959  mov     rax, [rbp+Handle]
0x18006b95d  inc     rax
0x18006b960  cmp     rax, 1
0x18006b964  jbe     loc_18006B762
0x18006b96a  mov     rax, [rbp+Handle]
0x18006b96e  mov     [rbp+Handle], rsi
0x18006b972  mov     rdx, [r15]
0x18006b975  mov     [r15], rax
0x18006b978  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18006b97d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b984  lea     rax, WPP_GLOBAL_Control
0x18006b98b  cmp     rcx, rax
0x18006b98e  jz      short loc_18006B9AF
0x18006b990  test    byte ptr [rcx+1Ch], 4
0x18006b994  jz      short loc_18006B9AF
0x18006b996  mov     edx, 19h
0x18006b99b  mov     r9d, edi
0x18006b99e  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006b9a5  mov     rcx, [rcx+10h]
0x18006b9a9  call    WPP_SF_d
0x18006b9ae  nop
0x18006b9af  lea     rcx, [rbp+var_20]
0x18006b9b3  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006b9b8  nop
0x18006b9b9  mov     rdx, [rbp+Handle]
0x18006b9bd  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18006b9c2  mov     eax, edi
0x18006b9c4  mov     rbx, [rsp+60h+arg_0]
0x18006b9cc  add     rsp, 60h
0x18006b9d0  pop     r15
0x18006b9d2  pop     r14
0x18006b9d4  pop     r13
0x18006b9d6  pop     r12
0x18006b9d8  pop     rdi
0x18006b9d9  pop     rsi
0x18006b9da  pop     rbp
0x18006b9db  retn
```
