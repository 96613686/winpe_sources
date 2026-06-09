# WctGetObjectInfo(_WCT_CLIENT_HANDLE *,void *,tlx::unique_any<tlx::file_handle_traits> *,_WCT_OBJECT_TYPE *)

- ea: `0x18005eecc`
- end: `0x18005f1ba`
- name: `?WctGetObjectInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAW4_WCT_OBJECT_TYPE@@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005e660`

## callees

- `0x18003ac90`
- `0x18003b1f8`
- `0x18003b57c`
- `0x18003b728`
- `0x18003b748`
- `0x18003d048`
- `0x18005ddd0`
- `0x18005eecc`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18005f055`
- `ntdll!RtlEqualUnicodeString` at `0x18005f086`
- `ntdll!RtlEqualUnicodeString` at `0x18005f0b9`
- `ntdll!RtlEqualUnicodeString` at `0x18005f0e7`
- `ntdll!RtlEqualUnicodeString` at `0x18005f055`
- `ntdll!RtlEqualUnicodeString` at `0x18005f086`
- `ntdll!RtlEqualUnicodeString` at `0x18005f0b9`
- `ntdll!RtlEqualUnicodeString` at `0x18005f0e7`
- `ntdll!NtQueryObject` at `0x18005efba`
- `ntdll!NtQueryObject` at `0x18005f027`
- `ntdll!NtQueryObject` at `0x18005efba`
- `ntdll!NtQueryObject` at `0x18005f027`
- `ntdll!RtlNtStatusToDosError` at `0x18005efc9`
- `ntdll!RtlNtStatusToDosError` at `0x18005efc9`
- `ntdll!RtlInitUnicodeString` at `0x18005f045`
- `ntdll!RtlInitUnicodeString` at `0x18005f076`
- `ntdll!RtlInitUnicodeString` at `0x18005f0a9`
- `ntdll!RtlInitUnicodeString` at `0x18005f0d7`
- `ntdll!RtlInitUnicodeString` at `0x18005f045`
- `ntdll!RtlInitUnicodeString` at `0x18005f076`
- `ntdll!RtlInitUnicodeString` at `0x18005f0a9`
- `ntdll!RtlInitUnicodeString` at `0x18005f0d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ef5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ef36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ef36`
- `KERNEL32!GetLastError` at `0x18005f133`
- `KERNEL32!GetLastError` at `0x18005f133`
- `KERNEL32!DuplicateHandle` at `0x18005ef82`
- `KERNEL32!DuplicateHandle` at `0x18005f127`
- `KERNEL32!DuplicateHandle` at `0x18005ef82`
- `KERNEL32!DuplicateHandle` at `0x18005f127`

## string_xrefs

- `0x18005f09e`: `Thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WctGetObjectInfo(__int64 a1, HANDLE a2, __int64 a3, _DWORD *a4)
{
  DWORD dwDesiredAccess; // esi
  HANDLE CurrentProcess; // r12
  HANDLE *v10; // rbx
  HANDLE v11; // rax
  unsigned int v12; // edi
  int v13; // eax
  DWORD LastError; // eax
  UNICODE_STRING *v15; // rbx
  HANDLE *v16; // rbx
  HANDLE v17; // rax
  HANDLE v18; // rdx
  HANDLE Handle; // [rsp+40h] [rbp-38h] BYREF
  UNICODE_STRING *v21; // [rsp+48h] [rbp-30h] BYREF
  __int64 v22; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-20h] BYREF
  ULONG ObjectInformationLength; // [rsp+C8h] [rbp+50h] BYREF

  dwDesiredAccess = 0;
  Handle = 0;
  v21 = 0;
  ObjectInformationLength = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  tlx::unique_any<tlx::file_handle_traits>::reset(a3, 0);
  if ( a2 == GetCurrentThread() )
  {
    CurrentProcess = GetCurrentProcess();
    a2 = *(HANDLE *)a1;
  }
  else
  {
    CurrentProcess = *(HANDLE *)(a1 + 8);
  }
  v10 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
  v11 = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, a2, v11, v10, 0, 0, 2u) )
  {
LABEL_25:
    LastError = GetLastError();
LABEL_26:
    v12 = LastError;
    if ( LastError )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (unsigned __int64)Handle + 1 > 1 )
  {
    v13 = NtQueryObject(Handle, ObjectTypeInformation, 0, ObjectInformationLength, &ObjectInformationLength);
    if ( v13 != -1073741820 )
      goto LABEL_11;
    v15 = (UNICODE_STRING *)operator new(ObjectInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    v21 = 0;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v21);
    v22 = 0;
    v21 = v15;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v22);
    if ( !v15 )
    {
      v12 = 8;
      goto LABEL_30;
    }
    v13 = NtQueryObject(Handle, ObjectTypeInformation, v15, ObjectInformationLength, &ObjectInformationLength);
    if ( v13 < 0 )
    {
LABEL_11:
      LastError = RtlNtStatusToDosError(v13);
      goto LABEL_26;
    }
    v12 = 0;
    *a4 = 10;
    RtlInitUnicodeString(&DestinationString, L"Event");
    if ( RtlEqualUnicodeString(&DestinationString, v15, 0) )
    {
      *a4 = 1;
      goto LABEL_29;
    }
    RtlInitUnicodeString(&DestinationString, L"Mutant");
    if ( RtlEqualUnicodeString(&DestinationString, v15, 0) )
    {
      *a4 = 3;
      dwDesiredAccess = 2031617;
      goto LABEL_24;
    }
    RtlInitUnicodeString(&DestinationString, L"Thread");
    if ( RtlEqualUnicodeString(&DestinationString, v15, 0) )
    {
      *a4 = 6;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"Process");
      if ( !RtlEqualUnicodeString(&DestinationString, v15, 0) )
        goto LABEL_24;
      *a4 = 7;
    }
    dwDesiredAccess = 0x1FFFFF;
LABEL_24:
    v16 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
    v17 = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, a2, v17, v16, dwDesiredAccess, 0, 0) )
    {
      if ( Handle == (HANDLE)-1LL || (char *)Handle + 1 == HANDLE_FLAG_INHERIT )
        goto LABEL_9;
LABEL_29:
      v18 = Handle;
      Handle = 0;
      tlx::unique_any<tlx::file_handle_traits>::reset(a3, v18);
      goto LABEL_30;
    }
    goto LABEL_25;
  }
LABEL_9:
  v12 = 87;
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v12);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v21);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  return v12;
}

```

## disassembly

```asm
0x18005eecc  push    rbp
0x18005eece  push    rbx
0x18005eecf  push    rsi
0x18005eed0  push    rdi
0x18005eed1  push    r12
0x18005eed3  push    r13
0x18005eed5  push    r14
0x18005eed7  push    r15
0x18005eed9  mov     rbp, rsp
0x18005eedc  sub     rsp, 78h
0x18005eee0  mov     r14, r9
0x18005eee3  mov     r13, r8
0x18005eee6  mov     r15, rdx
0x18005eee9  mov     rbx, rcx
0x18005eeec  xor     esi, esi
0x18005eeee  mov     [rbp+Handle], rsi
0x18005eef2  mov     [rbp+var_30], rsi
0x18005eef6  mov     [rbp+ObjectInformationLength], esi
0x18005eef9  xorps   xmm0, xmm0
0x18005eefc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005ef00  lea     rax, WPP_GLOBAL_Control
0x18005ef07  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef0e  cmp     rcx, rax
0x18005ef11  jz      short loc_18005EF2C
0x18005ef13  test    byte ptr [rcx+1Ch], 4
0x18005ef17  jz      short loc_18005EF2C
0x18005ef19  lea     edx, [rsi+18h]
0x18005ef1c  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005ef23  mov     rcx, [rcx+10h]
0x18005ef27  call    WPP_SF_
0x18005ef2c  xor     edx, edx
0x18005ef2e  mov     rcx, r13
0x18005ef31  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005ef36  call    cs:__imp_GetCurrentThread
0x18005ef3c  cmp     r15, rax
0x18005ef3f  jnz     short loc_18005EF4F
0x18005ef41  call    cs:__imp_GetCurrentProcess
0x18005ef47  mov     r12, rax
0x18005ef4a  mov     r15, [rbx]
0x18005ef4d  jmp     short loc_18005EF53
0x18005ef4f  mov     r12, [rbx+8]
0x18005ef53  lea     rcx, [rbp+Handle]
0x18005ef57  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005ef5c  mov     rbx, rax
0x18005ef5f  call    cs:__imp_GetCurrentProcess
0x18005ef65  mov     edi, 2
0x18005ef6a  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005ef6e  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x18005ef72  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005ef76  mov     r9, rbx; lpTargetHandle
0x18005ef79  mov     r8, rax; hTargetProcessHandle
0x18005ef7c  mov     rdx, r15; hSourceHandle
0x18005ef7f  mov     rcx, r12; hSourceProcessHandle
0x18005ef82  call    cs:__imp_DuplicateHandle
0x18005ef88  test    eax, eax
0x18005ef8a  jz      loc_18005F133
0x18005ef90  mov     rcx, [rbp+Handle]; Handle
0x18005ef94  lea     rax, [rcx+1]
0x18005ef98  cmp     rax, 1
0x18005ef9c  ja      short loc_18005EFA8
0x18005ef9e  mov     edi, 57h ; 'W'
0x18005efa3  jmp     loc_18005F162
0x18005efa8  lea     rax, [rbp+ObjectInformationLength]
0x18005efac  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005efb1  mov     r9d, [rbp+ObjectInformationLength]; ObjectInformationLength
0x18005efb5  xor     r8d, r8d; ObjectInformation
0x18005efb8  mov     edx, edi; ObjectInformationClass
0x18005efba  call    cs:__imp_NtQueryObject
0x18005efc0  cmp     eax, 0C0000004h
0x18005efc5  jz      short loc_18005EFD4
0x18005efc7  mov     ecx, eax; Status
0x18005efc9  call    cs:__imp_RtlNtStatusToDosError
0x18005efcf  jmp     loc_18005F139
0x18005efd4  mov     ecx, [rbp+ObjectInformationLength]; unsigned __int64
0x18005efd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005efde  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005efe3  mov     rbx, rax
0x18005efe6  mov     [rbp+var_30], rsi
0x18005efea  lea     rcx, [rbp+var_30]
0x18005efee  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005eff3  mov     [rbp+var_28], rsi
0x18005eff7  mov     [rbp+var_30], rbx
0x18005effb  lea     rcx, [rbp+var_28]
0x18005efff  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005f004  test    rbx, rbx
0x18005f007  jnz     short loc_18005F011
0x18005f009  lea     edi, [rbx+8]
0x18005f00c  jmp     loc_18005F162
0x18005f011  lea     rax, [rbp+ObjectInformationLength]
0x18005f015  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005f01a  mov     r9d, [rbp+ObjectInformationLength]; ObjectInformationLength
0x18005f01e  mov     r8, rbx; ObjectInformation
0x18005f021  mov     edx, edi; ObjectInformationClass
0x18005f023  mov     rcx, [rbp+Handle]; Handle
0x18005f027  call    cs:__imp_NtQueryObject
0x18005f02d  test    eax, eax
0x18005f02f  js      short loc_18005EFC7
0x18005f031  mov     edi, esi
0x18005f033  mov     dword ptr [r14], 0Ah
0x18005f03a  lea     rdx, aEvent; "Event"
0x18005f041  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005f045  call    cs:__imp_RtlInitUnicodeString
0x18005f04b  xor     r8d, r8d; CaseInsensitive
0x18005f04e  mov     rdx, rbx; String2
0x18005f051  lea     rcx, [rbp+DestinationString]; String1
0x18005f055  call    cs:__imp_RtlEqualUnicodeString
0x18005f05b  test    al, al
0x18005f05d  jz      short loc_18005F06B
0x18005f05f  mov     dword ptr [r14], 1
0x18005f066  jmp     loc_18005F152
0x18005f06b  lea     rdx, aMutant; "Mutant"
0x18005f072  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005f076  call    cs:__imp_RtlInitUnicodeString
0x18005f07c  xor     r8d, r8d; CaseInsensitive
0x18005f07f  mov     rdx, rbx; String2
0x18005f082  lea     rcx, [rbp+DestinationString]; String1
0x18005f086  call    cs:__imp_RtlEqualUnicodeString
0x18005f08c  test    al, al
0x18005f08e  jz      short loc_18005F09E
0x18005f090  mov     dword ptr [r14], 3
0x18005f097  mov     esi, 1F0001h
0x18005f09c  jmp     short loc_18005F0FD
0x18005f09e  lea     rdx, aThread; "Thread"
0x18005f0a5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005f0a9  call    cs:__imp_RtlInitUnicodeString
0x18005f0af  xor     r8d, r8d; CaseInsensitive
0x18005f0b2  mov     rdx, rbx; String2
0x18005f0b5  lea     rcx, [rbp+DestinationString]; String1
0x18005f0b9  call    cs:__imp_RtlEqualUnicodeString
0x18005f0bf  test    al, al
0x18005f0c1  jz      short loc_18005F0CC
0x18005f0c3  mov     dword ptr [r14], 6
0x18005f0ca  jmp     short loc_18005F0F8
0x18005f0cc  lea     rdx, aProcess; "Process"
0x18005f0d3  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005f0d7  call    cs:__imp_RtlInitUnicodeString
0x18005f0dd  xor     r8d, r8d; CaseInsensitive
0x18005f0e0  mov     rdx, rbx; String2
0x18005f0e3  lea     rcx, [rbp+DestinationString]; String1
0x18005f0e7  call    cs:__imp_RtlEqualUnicodeString
0x18005f0ed  test    al, al
0x18005f0ef  jz      short loc_18005F0FD
0x18005f0f1  mov     dword ptr [r14], 7
0x18005f0f8  mov     esi, 1FFFFFh
0x18005f0fd  lea     rcx, [rbp+Handle]
0x18005f101  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005f106  mov     rbx, rax
0x18005f109  call    cs:__imp_GetCurrentProcess
0x18005f10f  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005f113  mov     [rsp+78h+bInheritHandle], edi; bInheritHandle
0x18005f117  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005f11b  mov     r9, rbx; lpTargetHandle
0x18005f11e  mov     r8, rax; hTargetProcessHandle
0x18005f121  mov     rdx, r15; hSourceHandle
0x18005f124  mov     rcx, r12; hSourceProcessHandle
0x18005f127  call    cs:__imp_DuplicateHandle
0x18005f12d  xor     esi, esi
0x18005f12f  test    eax, eax
0x18005f131  jnz     short loc_18005F141
0x18005f133  call    cs:__imp_GetLastError
0x18005f139  mov     edi, eax
0x18005f13b  test    eax, eax
0x18005f13d  jnz     short loc_18005F162
0x18005f13f  jmp     short loc_18005F152
0x18005f141  mov     rax, [rbp+Handle]
0x18005f145  inc     rax
0x18005f148  cmp     rax, 1
0x18005f14c  jbe     loc_18005EF9E
0x18005f152  mov     rdx, [rbp+Handle]
0x18005f156  mov     [rbp+Handle], rsi
0x18005f15a  mov     rcx, r13
0x18005f15d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f162  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f169  lea     rax, WPP_GLOBAL_Control
0x18005f170  cmp     rcx, rax
0x18005f173  jz      short loc_18005F194
0x18005f175  test    byte ptr [rcx+1Ch], 4
0x18005f179  jz      short loc_18005F194
0x18005f17b  mov     edx, 19h
0x18005f180  mov     r9d, edi
0x18005f183  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005f18a  mov     rcx, [rcx+10h]
0x18005f18e  call    WPP_SF_d
0x18005f193  nop
0x18005f194  lea     rcx, [rbp+var_30]
0x18005f198  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005f19d  nop
0x18005f19e  lea     rcx, [rbp+Handle]
0x18005f1a2  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f1a7  mov     eax, edi
0x18005f1a9  add     rsp, 78h
0x18005f1ad  pop     r15
0x18005f1af  pop     r14
0x18005f1b1  pop     r13
0x18005f1b3  pop     r12
0x18005f1b5  pop     rdi
0x18005f1b6  pop     rsi
0x18005f1b7  pop     rbx
0x18005f1b8  pop     rbp
0x18005f1b9  retn
```
