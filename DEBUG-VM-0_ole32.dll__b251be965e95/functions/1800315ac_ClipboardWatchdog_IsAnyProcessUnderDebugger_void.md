# ClipboardWatchdog::IsAnyProcessUnderDebugger(void)

- ea: `0x1800315ac`
- end: `0x1800316a1`
- name: `?IsAnyProcessUnderDebugger@ClipboardWatchdog@@CA_NXZ`
- size: `245`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031520`

## callees

- `0x1800315ac`
- `0x180036370`
- `0x180041554`
- `0x18008e4c0`
- `0x18008ea98`
- `0x18008f6c8`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800315ce`
- `ntdll!NtQuerySystemInformation` at `0x18003161a`
- `ntdll!NtQuerySystemInformation` at `0x1800315ce`
- `ntdll!NtQuerySystemInformation` at `0x18003161a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031660`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003163b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003163b`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18003166f`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18003166f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800315e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800315e1`

## pseudocode

```c
char __fastcall ClipboardWatchdog::IsAnyProcessUnderDebugger()
{
  __int16 v0; // dx
  ULONG v1; // r8d
  _SYSTEM_BASICPROCESS_INFORMATION *value; // rdi
  HANDLE v3; // rax
  void *v4; // rbx
  char v5; // bl
  unsigned int bufferSize; // [rsp+40h] [rbp+20h] BYREF
  int result; // [rsp+48h] [rbp+28h] BYREF
  wistd::unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > basicInfo; // [rsp+50h] [rbp+30h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > processHandle; // [rsp+58h] [rbp+38h] BYREF

  bufferSize = 0;
  NtQuerySystemInformation(SystemBasicProcessInformation, 0, 0, &bufferSize);
  bufferSize += 1024;
  CoTaskMemAlloc(bufferSize);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>((CBrokeredClipDataObject *)&basicInfo);
  if ( bufferSize )
  {
    if ( wistd::operator!=<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
           &basicInfo,
           v0) )
    {
      value = basicInfo.__ptr_.__value_;
      if ( !NtQuerySystemInformation(SystemBasicProcessInformation, basicInfo.__ptr_.__value_, v1, &bufferSize) )
      {
        while ( value )
        {
          result = 0;
          v3 = OpenProcess(0x400u, 0, (DWORD)value->UniqueProcessId);
          processHandle.m_ptr = v3;
          v4 = v3;
          if ( v3 && CheckRemoteDebuggerPresent(v3, &result) && result )
          {
            wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&processHandle);
            v5 = 1;
            goto LABEL_12;
          }
          value = ClipboardWatchdog::NextSPI(value);
          if ( v4 )
            CloseHandle(v4);
        }
      }
    }
  }
  v5 = 0;
LABEL_12:
  wistd::unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(&basicInfo);
  return v5;
}

```

## disassembly

```asm
0x1800315ac  push    rbp
0x1800315ae  push    rbx
0x1800315af  push    rdi
0x1800315b0  mov     rbp, rsp
0x1800315b3  sub     rsp, 20h
0x1800315b7  mov     ebx, 0FCh
0x1800315bc  mov     [rbp+bufferSize], 0
0x1800315c3  mov     ecx, ebx; SystemInformationClass
0x1800315c5  lea     r9, [rbp+bufferSize]; ReturnLength
0x1800315c9  xor     r8d, r8d; SystemInformationLength
0x1800315cc  xor     edx, edx; SystemInformation
0x1800315ce  call    cs:__imp_NtQuerySystemInformation
0x1800315d4  mov     eax, [rbp+bufferSize]
0x1800315d7  add     eax, 400h
0x1800315dc  mov     ecx, eax; cb
0x1800315de  mov     [rbp+bufferSize], eax
0x1800315e1  call    cs:__imp_CoTaskMemAlloc
0x1800315e7  mov     rdx, rax
0x1800315ea  lea     rcx, [rbp+basicInfo]; _This
0x1800315ee  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800315f3  mov     r8d, [rbp+bufferSize]
0x1800315f7  test    r8d, r8d
0x1800315fa  jz      loc_18003168C
0x180031600  lea     rcx, [rbp+basicInfo]; __x
0x180031604  call    ??$?9U_SYSTEM_BASICPROCESS_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@YA_NAEBV?$unique_ptr@U_SYSTEM_BASICPROCESS_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@0@$$T@Z; wistd::operator!=<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> const &,std::nullptr_t)
0x180031609  test    al, al
0x18003160b  jz      short loc_18003168C
0x18003160d  mov     rdi, [rbp+basicInfo.__ptr_.__value_]
0x180031611  lea     r9, [rbp+bufferSize]; ReturnLength
0x180031615  mov     rdx, rdi; SystemInformation
0x180031618  mov     ecx, ebx; SystemInformationClass
0x18003161a  call    cs:__imp_NtQuerySystemInformation
0x180031620  test    eax, eax
0x180031622  jnz     short loc_18003168C
0x180031624  test    rdi, rdi
0x180031627  jz      short loc_18003168C
0x180031629  mov     [rbp+result], 0
0x180031630  xor     edx, edx; bInheritHandle
0x180031632  mov     r8d, [rdi+8]; dwProcessId
0x180031636  mov     ecx, 400h; dwDesiredAccess
0x18003163b  call    cs:__imp_OpenProcess
0x180031641  mov     [rbp+processHandle.m_ptr], rax
0x180031645  mov     rbx, rax
0x180031648  test    rax, rax
0x18003164b  jnz     short loc_180031668
0x18003164d  mov     rcx, rdi; current
0x180031650  call    ?NextSPI@ClipboardWatchdog@@CAPEAU_SYSTEM_BASICPROCESS_INFORMATION@@PEAU2@@Z; ClipboardWatchdog::NextSPI(_SYSTEM_BASICPROCESS_INFORMATION *)
0x180031655  mov     rdi, rax
0x180031658  test    rbx, rbx
0x18003165b  jz      short loc_180031624
0x18003165d  mov     rcx, rbx; hObject
0x180031660  call    cs:__imp_CloseHandle
0x180031666  jmp     short loc_180031624
0x180031668  lea     rdx, [rbp+result]; pbDebuggerPresent
0x18003166c  mov     rcx, rbx; hProcess
0x18003166f  call    cs:__imp_CheckRemoteDebuggerPresent
0x180031675  test    eax, eax
0x180031677  jz      short loc_18003164D
0x180031679  cmp     [rbp+result], 0
0x18003167d  jz      short loc_18003164D
0x18003167f  lea     rcx, [rbp+processHandle]; this
0x180031683  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031688  mov     bl, 1
0x18003168a  jmp     short loc_18003168E
0x18003168c  xor     ebx, ebx
0x18003168e  lea     rcx, [rbp+basicInfo]; this
0x180031692  call    ??1?$unique_ptr@U_SYSTEM_BASICPROCESS_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_SYSTEM_BASICPROCESS_INFORMATION,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)
0x180031697  mov     al, bl
0x180031699  add     rsp, 20h
0x18003169d  pop     rdi
0x18003169e  pop     rbx
0x18003169f  pop     rbp
0x1800316a0  retn
```
