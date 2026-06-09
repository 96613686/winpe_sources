# WctGetObjectInfo(_WCT_CLIENT_HANDLE *,void *,tlx::unique_any<tlx::file_handle_traits> *,_WCT_OBJECT_TYPE *)

- ea: `0x18005dc78`
- end: `0x18005df62`
- name: `?WctGetObjectInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAW4_WCT_OBJECT_TYPE@@@Z`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001fe24`
- `0x180027884`
- `0x18002bed4`
- `0x18005dc78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dd8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dd8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005deb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005deb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005dce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005dce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dee1`
- `ntdll!NtQueryObject` at `0x18005dd66`
- `ntdll!NtQueryObject` at `0x18005ddd7`
- `ntdll!NtQueryObject` at `0x18005dd66`
- `ntdll!NtQueryObject` at `0x18005ddd7`
- `ntdll!RtlNtStatusToDosError` at `0x18005dd75`
- `ntdll!RtlNtStatusToDosError` at `0x18005dd75`
- `ntdll!RtlInitUnicodeString` at `0x18005ddf5`
- `ntdll!RtlInitUnicodeString` at `0x18005de26`
- `ntdll!RtlInitUnicodeString` at `0x18005de59`
- `ntdll!RtlInitUnicodeString` at `0x18005de87`
- `ntdll!RtlInitUnicodeString` at `0x18005ddf5`
- `ntdll!RtlInitUnicodeString` at `0x18005de26`
- `ntdll!RtlInitUnicodeString` at `0x18005de59`
- `ntdll!RtlInitUnicodeString` at `0x18005de87`
- `ntdll!RtlEqualUnicodeString` at `0x18005de05`
- `ntdll!RtlEqualUnicodeString` at `0x18005de36`
- `ntdll!RtlEqualUnicodeString` at `0x18005de69`
- `ntdll!RtlEqualUnicodeString` at `0x18005de97`
- `ntdll!RtlEqualUnicodeString` at `0x18005de05`
- `ntdll!RtlEqualUnicodeString` at `0x18005de36`
- `ntdll!RtlEqualUnicodeString` at `0x18005de69`
- `ntdll!RtlEqualUnicodeString` at `0x18005de97`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dd2e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005ded7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dd2e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005ded7`

## string_xrefs

- `0x18005de4e`: `Thread`

## pseudocode

```c
__int64 __fastcall WctGetObjectInfo(__int64 a1, HANDLE a2, __int64 a3, _DWORD *a4)
{
  DWORD dwDesiredAccess; // esi
  HANDLE CurrentProcess; // rax
  void *v10; // r12
  HANDLE *v11; // rbx
  HANDLE v12; // rax
  unsigned int v13; // edi
  int v14; // eax
  DWORD LastError; // eax
  UNICODE_STRING *v16; // rax
  UNICODE_STRING *v17; // rbx
  HANDLE *v18; // rbx
  HANDLE v19; // rax
  HANDLE Handle; // [rsp+40h] [rbp-38h] BYREF
  UNICODE_STRING *v22; // [rsp+48h] [rbp-30h] BYREF
  __int64 v23; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-20h] BYREF
  ULONG ReturnLength; // [rsp+C8h] [rbp+50h] BYREF

  dwDesiredAccess = 0;
  Handle = 0;
  v22 = 0;
  ReturnLength = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  tlx::unique_any<tlx::file_handle_traits>::reset(a3, 0);
  if ( a2 == GetCurrentThread() )
  {
    CurrentProcess = GetCurrentProcess();
    a2 = *(HANDLE *)a1;
    v10 = CurrentProcess;
  }
  else
  {
    v10 = *(void **)(a1 + 8);
  }
  v11 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
  v12 = GetCurrentProcess();
  if ( !DuplicateHandle(v10, a2, v12, v11, 0, 0, 2u) )
  {
LABEL_25:
    LastError = GetLastError();
LABEL_26:
    v13 = LastError;
    if ( LastError )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (unsigned __int64)Handle + 1 > 1 )
  {
    v14 = NtQueryObject(Handle, ObjectTypeInformation, 0, ReturnLength, &ReturnLength);
    if ( v14 != -1073741820 )
      goto LABEL_11;
    v16 = (UNICODE_STRING *)HeapAlloc(g_hWerheap, 0, ReturnLength);
    v22 = 0;
    v17 = v16;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v22);
    v23 = 0;
    v22 = v17;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v23);
    if ( !v17 )
    {
      v13 = 8;
      goto LABEL_30;
    }
    v14 = NtQueryObject(Handle, ObjectTypeInformation, v17, ReturnLength, &ReturnLength);
    if ( v14 < 0 )
    {
LABEL_11:
      LastError = RtlNtStatusToDosError(v14);
      goto LABEL_26;
    }
    *a4 = 10;
    v13 = 0;
    RtlInitUnicodeString(&DestinationString, L"Event");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 1;
      goto LABEL_29;
    }
    RtlInitUnicodeString(&DestinationString, L"Mutant");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 3;
      dwDesiredAccess = 2031617;
      goto LABEL_24;
    }
    RtlInitUnicodeString(&DestinationString, L"Thread");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 6;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"Process");
      if ( !RtlEqualUnicodeString(&DestinationString, v17, 0) )
        goto LABEL_24;
      *a4 = 7;
    }
    dwDesiredAccess = 0x1FFFFF;
LABEL_24:
    v18 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
    v19 = GetCurrentProcess();
    if ( DuplicateHandle(v10, a2, v19, v18, dwDesiredAccess, 0, 0) )
    {
      if ( Handle == (HANDLE)-1LL || (char *)Handle + 1 == HANDLE_FLAG_INHERIT )
        goto LABEL_9;
LABEL_29:
      tlx::unique_any<tlx::file_handle_traits>::operator=(a3, &Handle);
      goto LABEL_30;
    }
    goto LABEL_25;
  }
LABEL_9:
  v13 = 87;
LABEL_30:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v13);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v22);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  return v13;
}

```

## disassembly

```asm
0x18005dc78  push    rbp
0x18005dc7a  push    rbx
0x18005dc7b  push    rsi
0x18005dc7c  push    rdi
0x18005dc7d  push    r12
0x18005dc7f  push    r13
0x18005dc81  push    r14
0x18005dc83  push    r15
0x18005dc85  mov     rbp, rsp
0x18005dc88  sub     rsp, 78h
0x18005dc8c  xor     esi, esi
0x18005dc8e  xorps   xmm0, xmm0
0x18005dc91  mov     [rbp+Handle], rsi
0x18005dc95  mov     r14, r9
0x18005dc98  mov     [rbp+var_30], rsi
0x18005dc9c  mov     r13, r8
0x18005dc9f  mov     [rbp+ReturnLength], esi
0x18005dca2  mov     r15, rdx
0x18005dca5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005dca9  mov     rbx, rcx
0x18005dcac  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dcb3  lea     rax, WPP_GLOBAL_Control
0x18005dcba  cmp     rcx, rax
0x18005dcbd  jz      short loc_18005DCD8
0x18005dcbf  test    byte ptr [rcx+1Ch], 4
0x18005dcc3  jz      short loc_18005DCD8
0x18005dcc5  mov     rcx, [rcx+10h]
0x18005dcc9  lea     edx, [rsi+18h]
0x18005dccc  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005dcd3  call    WPP_SF_
0x18005dcd8  xor     edx, edx
0x18005dcda  mov     rcx, r13
0x18005dcdd  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005dce2  call    cs:__imp_GetCurrentThread
0x18005dce8  cmp     r15, rax
0x18005dceb  jnz     short loc_18005DCFB
0x18005dced  call    cs:__imp_GetCurrentProcess
0x18005dcf3  mov     r15, [rbx]
0x18005dcf6  mov     r12, rax
0x18005dcf9  jmp     short loc_18005DCFF
0x18005dcfb  mov     r12, [rbx+8]
0x18005dcff  lea     rcx, [rbp+Handle]
0x18005dd03  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005dd08  mov     rbx, rax
0x18005dd0b  call    cs:__imp_GetCurrentProcess
0x18005dd11  mov     edi, 2
0x18005dd16  mov     r9, rbx; lpTargetHandle
0x18005dd19  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005dd1d  mov     r8, rax; hTargetProcessHandle
0x18005dd20  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x18005dd24  mov     rdx, r15; hSourceHandle
0x18005dd27  mov     rcx, r12; hSourceProcessHandle
0x18005dd2a  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005dd2e  call    cs:__imp_DuplicateHandle
0x18005dd34  test    eax, eax
0x18005dd36  jz      loc_18005DEE1
0x18005dd3c  mov     rcx, [rbp+Handle]; Handle
0x18005dd40  lea     rax, [rcx+1]
0x18005dd44  cmp     rax, 1
0x18005dd48  ja      short loc_18005DD54
0x18005dd4a  mov     edi, 57h ; 'W'
0x18005dd4f  jmp     loc_18005DF0C
0x18005dd54  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x18005dd58  lea     rax, [rbp+ReturnLength]
0x18005dd5c  xor     r8d, r8d; ObjectInformation
0x18005dd5f  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005dd64  mov     edx, edi; ObjectInformationClass
0x18005dd66  call    cs:__imp_NtQueryObject
0x18005dd6c  cmp     eax, 0C0000004h
0x18005dd71  jz      short loc_18005DD80
0x18005dd73  mov     ecx, eax; Status
0x18005dd75  call    cs:__imp_RtlNtStatusToDosError
0x18005dd7b  jmp     loc_18005DEE7
0x18005dd80  mov     r8d, [rbp+ReturnLength]; dwBytes
0x18005dd84  xor     edx, edx; dwFlags
0x18005dd86  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005dd8d  call    cs:__imp_HeapAlloc
0x18005dd93  lea     rcx, [rbp+var_30]; void *
0x18005dd97  mov     [rbp+var_30], rsi
0x18005dd9b  mov     rbx, rax
0x18005dd9e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005dda3  lea     rcx, [rbp+var_28]; void *
0x18005dda7  mov     [rbp+var_28], rsi
0x18005ddab  mov     [rbp+var_30], rbx
0x18005ddaf  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005ddb4  test    rbx, rbx
0x18005ddb7  jnz     short loc_18005DDC1
0x18005ddb9  lea     edi, [rbx+8]
0x18005ddbc  jmp     loc_18005DF0C
0x18005ddc1  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x18005ddc5  lea     rax, [rbp+ReturnLength]
0x18005ddc9  mov     rcx, [rbp+Handle]; Handle
0x18005ddcd  mov     r8, rbx; ObjectInformation
0x18005ddd0  mov     edx, edi; ObjectInformationClass
0x18005ddd2  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005ddd7  call    cs:__imp_NtQueryObject
0x18005dddd  test    eax, eax
0x18005dddf  js      short loc_18005DD73
0x18005dde1  lea     rdx, aEvent_0; "Event"
0x18005dde8  mov     dword ptr [r14], 0Ah
0x18005ddef  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005ddf3  mov     edi, esi
0x18005ddf5  call    cs:__imp_RtlInitUnicodeString
0x18005ddfb  xor     r8d, r8d; CaseInsensitive
0x18005ddfe  lea     rcx, [rbp+DestinationString]; String1
0x18005de02  mov     rdx, rbx; String2
0x18005de05  call    cs:__imp_RtlEqualUnicodeString
0x18005de0b  test    al, al
0x18005de0d  jz      short loc_18005DE1B
0x18005de0f  mov     dword ptr [r14], 1
0x18005de16  jmp     loc_18005DF00
0x18005de1b  lea     rdx, aMutant; "Mutant"
0x18005de22  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005de26  call    cs:__imp_RtlInitUnicodeString
0x18005de2c  xor     r8d, r8d; CaseInsensitive
0x18005de2f  lea     rcx, [rbp+DestinationString]; String1
0x18005de33  mov     rdx, rbx; String2
0x18005de36  call    cs:__imp_RtlEqualUnicodeString
0x18005de3c  test    al, al
0x18005de3e  jz      short loc_18005DE4E
0x18005de40  mov     dword ptr [r14], 3
0x18005de47  mov     esi, 1F0001h
0x18005de4c  jmp     short loc_18005DEAD
0x18005de4e  lea     rdx, aThread; "Thread"
0x18005de55  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005de59  call    cs:__imp_RtlInitUnicodeString
0x18005de5f  xor     r8d, r8d; CaseInsensitive
0x18005de62  lea     rcx, [rbp+DestinationString]; String1
0x18005de66  mov     rdx, rbx; String2
0x18005de69  call    cs:__imp_RtlEqualUnicodeString
0x18005de6f  test    al, al
0x18005de71  jz      short loc_18005DE7C
0x18005de73  mov     dword ptr [r14], 6
0x18005de7a  jmp     short loc_18005DEA8
0x18005de7c  lea     rdx, aProcess; "Process"
0x18005de83  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005de87  call    cs:__imp_RtlInitUnicodeString
0x18005de8d  xor     r8d, r8d; CaseInsensitive
0x18005de90  lea     rcx, [rbp+DestinationString]; String1
0x18005de94  mov     rdx, rbx; String2
0x18005de97  call    cs:__imp_RtlEqualUnicodeString
0x18005de9d  test    al, al
0x18005de9f  jz      short loc_18005DEAD
0x18005dea1  mov     dword ptr [r14], 7
0x18005dea8  mov     esi, 1FFFFFh
0x18005dead  lea     rcx, [rbp+Handle]
0x18005deb1  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005deb6  mov     rbx, rax
0x18005deb9  call    cs:__imp_GetCurrentProcess
0x18005debf  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005dec3  mov     r9, rbx; lpTargetHandle
0x18005dec6  mov     r8, rax; hTargetProcessHandle
0x18005dec9  mov     [rsp+78h+bInheritHandle], edi; bInheritHandle
0x18005decd  mov     rdx, r15; hSourceHandle
0x18005ded0  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005ded4  mov     rcx, r12; hSourceProcessHandle
0x18005ded7  call    cs:__imp_DuplicateHandle
0x18005dedd  test    eax, eax
0x18005dedf  jnz     short loc_18005DEEF
0x18005dee1  call    cs:__imp_GetLastError
0x18005dee7  mov     edi, eax
0x18005dee9  test    eax, eax
0x18005deeb  jnz     short loc_18005DF0C
0x18005deed  jmp     short loc_18005DF00
0x18005deef  mov     rax, [rbp+Handle]
0x18005def3  inc     rax
0x18005def6  cmp     rax, 1
0x18005defa  jbe     loc_18005DD4A
0x18005df00  lea     rdx, [rbp+Handle]
0x18005df04  mov     rcx, r13
0x18005df07  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18005df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005df13  lea     rax, WPP_GLOBAL_Control
0x18005df1a  cmp     rcx, rax
0x18005df1d  jz      short loc_18005DF3D
0x18005df1f  test    byte ptr [rcx+1Ch], 4
0x18005df23  jz      short loc_18005DF3D
0x18005df25  mov     rcx, [rcx+10h]
0x18005df29  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005df30  mov     edx, 19h
0x18005df35  mov     r9d, edi
0x18005df38  call    WPP_SF_d
0x18005df3d  lea     rcx, [rbp+var_30]; void *
0x18005df41  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005df46  lea     rcx, [rbp+Handle]
0x18005df4a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005df4f  mov     eax, edi
0x18005df51  add     rsp, 78h
0x18005df55  pop     r15
0x18005df57  pop     r14
0x18005df59  pop     r13
0x18005df5b  pop     r12
0x18005df5d  pop     rdi
0x18005df5e  pop     rsi
0x18005df5f  pop     rbx
0x18005df60  pop     rbp
0x18005df61  retn
```
