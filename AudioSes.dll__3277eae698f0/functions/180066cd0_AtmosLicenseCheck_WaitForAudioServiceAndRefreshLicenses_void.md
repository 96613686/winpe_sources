# AtmosLicenseCheck::WaitForAudioServiceAndRefreshLicenses(void)

- ea: `0x180066cd0`
- end: `0x180066e08`
- name: `?WaitForAudioServiceAndRefreshLicenses@AtmosLicenseCheck@@UEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(AtmosLicenseCheck *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18004a818`
- `0x180052be0`
- `0x180066cd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180066d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180066d84`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066dec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066dec`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180066ce8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180066d18`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180066ce8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180066d18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066d2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066d2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066d04`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066dc5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066daf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066df5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066df5`

## string_xrefs

- `0x180066dd9`: `Error opening Global\Client_Atmos_Check_Event`

## pseudocode

```c
__int64 __fastcall AtmosLicenseCheck::WaitForAudioServiceAndRefreshLicenses(AtmosLicenseCheck *this)
{
  HANDLE v1; // rax
  int i; // edi
  void *v3; // rbx
  DWORD v4; // eax
  int v5; // r8d
  int v6; // r9d
  DWORD v7; // edi
  HANDLE Thread; // rax
  signed int LastError; // eax
  BOOL v11; // [rsp+48h] [rbp+10h] BYREF
  HMODULE phModule; // [rsp+50h] [rbp+18h] BYREF

  v1 = OpenEventW(0x1F0003u, 0, L"Global\\Client_Atmos_Check_Event");
  for ( i = 10; ; --i )
  {
    v3 = v1;
    if ( v1 )
    {
      v4 = WaitForSingleObject(v1, 0);
      v7 = v4;
      phModule = 0;
      if ( (unsigned int)dword_18018A668 > 5 )
      {
        v11 = v4 == 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18018A668,
          (unsigned int)&byte_180172EAF,
          v5,
          v6,
          (__int64)&v11);
      }
      if ( v7 && GetModuleHandleExW(4u, (LPCWSTR)AtmosCheckThread, &phModule) )
      {
        Thread = CreateThread(0, 0, AtmosCheckThread, phModule, 0, 0);
        if ( Thread )
          CloseHandle(Thread);
        else
          FreeLibrary(phModule);
      }
      CloseHandle(v3);
      return 0;
    }
    if ( !i )
      break;
    Sleep(0x64u);
    v1 = OpenEventW(0x1F0003u, 0, L"Global\\Client_Atmos_Check_Event");
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  AtmosLicenseCheck::Trace("Error opening Global\\Client_Atmos_Check_Event", LastError);
  return 0;
}

```

## disassembly

```asm
0x180066cd0  mov     [rsp+arg_0], rbx
0x180066cd5  push    rdi
0x180066cd6  sub     rsp, 30h
0x180066cda  lea     r8, Name; "Global\\Client_Atmos_Check_Event"
0x180066ce1  xor     edx, edx; bInheritHandle
0x180066ce3  mov     ecx, 1F0003h; dwDesiredAccess
0x180066ce8  call    cs:__imp_OpenEventW
0x180066cee  mov     edi, 0Ah
0x180066cf3  jmp     short loc_180066D1E
0x180066cf5  test    edi, edi
0x180066cf7  jz      loc_180066DC5
0x180066cfd  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180066d02  dec     edi
0x180066d04  call    cs:__imp_Sleep
0x180066d0a  lea     r8, Name; "Global\\Client_Atmos_Check_Event"
0x180066d11  xor     edx, edx; bInheritHandle
0x180066d13  mov     ecx, 1F0003h; dwDesiredAccess
0x180066d18  call    cs:__imp_OpenEventW
0x180066d1e  mov     rbx, rax
0x180066d21  test    rax, rax
0x180066d24  jz      short loc_180066CF5
0x180066d26  xor     edx, edx; dwMilliseconds
0x180066d28  mov     rcx, rax; hHandle
0x180066d2b  call    cs:__imp_WaitForSingleObject
0x180066d31  mov     ecx, cs:dword_18018A668
0x180066d37  mov     edi, eax
0x180066d39  mov     [rsp+38h+phModule], 0
0x180066d42  cmp     ecx, 5
0x180066d45  jbe     short loc_180066D6F
0x180066d47  xor     ecx, ecx
0x180066d49  lea     rdx, byte_180172EAF
0x180066d50  test    eax, eax
0x180066d52  lea     rax, [rsp+38h+arg_8]
0x180066d57  mov     qword ptr [rsp+38h+dwCreationFlags], rax
0x180066d5c  setz    cl
0x180066d5f  mov     [rsp+38h+arg_8], ecx
0x180066d63  lea     rcx, dword_18018A668
0x180066d6a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180066d6f  test    edi, edi
0x180066d71  jz      short loc_180066DF2
0x180066d73  lea     r8, [rsp+38h+phModule]; phModule
0x180066d78  mov     ecx, 4; dwFlags
0x180066d7d  lea     rdx, AtmosCheckThread; lpModuleName
0x180066d84  call    cs:__imp_GetModuleHandleExW
0x180066d8a  test    eax, eax
0x180066d8c  jz      short loc_180066DF2
0x180066d8e  mov     r9, [rsp+38h+phModule]; lpParameter
0x180066d93  lea     r8, AtmosCheckThread; lpStartAddress
0x180066d9a  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180066da3  xor     edx, edx; dwStackSize
0x180066da5  xor     ecx, ecx; lpThreadAttributes
0x180066da7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180066daf  call    cs:__imp_CreateThread
0x180066db5  test    rax, rax
0x180066db8  jz      short loc_180066DE7
0x180066dba  mov     rcx, rax; hObject
0x180066dbd  call    cs:__imp_CloseHandle
0x180066dc3  jmp     short loc_180066DF2
0x180066dc5  call    cs:__imp_GetLastError
0x180066dcb  test    eax, eax
0x180066dcd  jle     short loc_180066DD7
0x180066dcf  movzx   eax, ax
0x180066dd2  or      eax, 80070000h
0x180066dd7  mov     edx, eax; int
0x180066dd9  lea     rcx, aErrorOpeningGl; "Error opening Global\\Client_Atmos_Chec"...
0x180066de0  call    ?Trace@AtmosLicenseCheck@@CAXPEBDJ@Z; AtmosLicenseCheck::Trace(char const *,long)
0x180066de5  jmp     short loc_180066DFB
0x180066de7  mov     rcx, [rsp+38h+phModule]; hLibModule
0x180066dec  call    cs:__imp_FreeLibrary
0x180066df2  mov     rcx, rbx; hObject
0x180066df5  call    cs:__imp_CloseHandle
0x180066dfb  mov     rbx, [rsp+38h+arg_0]
0x180066e00  xor     eax, eax
0x180066e02  add     rsp, 30h
0x180066e06  pop     rdi
0x180066e07  retn
```
