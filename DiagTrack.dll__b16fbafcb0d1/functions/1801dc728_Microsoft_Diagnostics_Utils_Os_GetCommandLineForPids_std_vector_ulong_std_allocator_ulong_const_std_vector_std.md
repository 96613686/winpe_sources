# Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(std::vector<ulong,std::allocator<ulong>> const &,std::vector<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>>> &)

- ea: `0x1801dc728`
- end: `0x1801dc9ad`
- name: `?GetCommandLineForPids@Os@Utils@Diagnostics@Microsoft@@SAJAEBV?$vector@KV?$allocator@K@std@@@std@@AEAV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@6@@Z`
- size: `645`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801dc418`
- `0x1801e4348`

## callees

- `0x1800202a4`
- `0x18002df00`
- `0x1800e99a0`
- `0x18013a510`
- `0x180142fcc`
- `0x1801d1b14`
- `0x1801dc728`
- `0x18020aac0`
- `0x1802595f0`
- `0x1802ac984`
- `0x1802ace7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc8ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc8ca`
- `ntdll!NtQueryInformationProcess` at `0x1801dc7bc`
- `ntdll!NtQueryInformationProcess` at `0x1801dc7bc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801dc77f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801dc77f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc811`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc863`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc8c0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc811`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc863`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1801dc8c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(DWORD **a1, __int64 a2)
{
  DWORD *v3; // rdi
  DWORD *v4; // r15
  __m128i si128; // xmm6
  DWORD v6; // r14d
  HANDLE v7; // rax
  void *v8; // rbx
  NTSTATUS InformationProcess; // eax
  DWORD v10; // eax
  __int64 v11; // rdx
  LPVOID *v12; // r8
  DWORD LastError; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // r8d
  int v17; // r9d
  int ReturnLength; // [rsp+28h] [rbp-79h]
  unsigned int ReturnLengtha; // [rsp+28h] [rbp-79h]
  unsigned int ReturnLengthb; // [rsp+28h] [rbp-79h]
  DWORD v22; // [rsp+38h] [rbp-69h] BYREF
  HANDLE v23; // [rsp+40h] [rbp-61h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-59h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-51h] BYREF
  LPCVOID lpBaseAddress[2]; // [rsp+58h] [rbp-49h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  LPVOID lpBuffer[2]; // [rsp+98h] [rbp-9h] BYREF
  __m128i v29; // [rsp+A8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v3 = *a1;
  v4 = a1[1];
  if ( *a1 != v4 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v6 = *v3;
      v22 = v6;
      v7 = OpenProcess(0x410u, 0, v6);
      v8 = v7;
      v23 = v7;
      if ( !v7 )
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x20000) )
        {
          v22 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)word_1803F13DA,
            v16,
            v17,
            (__int64)&v22);
        }
        goto LABEL_22;
      }
      memset(ProcessInformation, 0, sizeof(ProcessInformation));
      InformationProcess = NtQueryInformationProcess(v7, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
      if ( InformationProcess >= 0 )
      {
        Buffer = 0;
        NumberOfBytesRead = 0;
        if ( ReadProcessMemory(
               v8,
               (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
               &Buffer,
               8u,
               &NumberOfBytesRead) )
        {
          *(_OWORD *)lpBaseAddress = 0;
          if ( ReadProcessMemory(v8, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead) )
          {
            *(_OWORD *)lpBuffer = 0;
            v29 = si128;
            LOWORD(lpBuffer[0]) = 0;
            std::wstring::resize(lpBuffer, LOWORD(lpBaseAddress[0]) + 2LL);
            v12 = lpBuffer;
            if ( v29.m128i_i64[1] > 7uLL )
              v12 = (LPVOID *)lpBuffer[0];
            if ( ReadProcessMemory(v8, lpBaseAddress[1], v12, LOWORD(lpBaseAddress[0]), &NumberOfBytesRead) )
            {
              std::wstring::resize(lpBuffer, NumberOfBytesRead >> 1);
              v15 = *(_QWORD *)(a2 + 8);
              if ( v15 == *(_QWORD *)(a2 + 16) )
              {
                std::vector<std::pair<std::wstring,unsigned long>>::_Emplace_reallocate<std::wstring &,unsigned long const &>(
                  a2,
                  v15,
                  lpBuffer,
                  &v22);
              }
              else
              {
                std::_Default_allocator_traits<std::allocator<std::pair<std::wstring,unsigned long>>>::construct<std::pair<std::wstring,unsigned long>,std::wstring &,unsigned long const &>(
                  v14,
                  v15,
                  lpBuffer,
                  &v22);
                *(_QWORD *)(a2 + 8) += 40LL;
              }
            }
            else
            {
              LastError = GetLastError();
              wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)0xCE9,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                (const char *)LastError,
                ReturnLengthb);
            }
            std::wstring::_Tidy_deallocate(lpBuffer);
            goto LABEL_22;
          }
          v10 = GetLastError();
          v11 = 3292;
        }
        else
        {
          v10 = GetLastError();
          v11 = 3281;
        }
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)v10,
          ReturnLengtha);
      }
      else
      {
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0xCC1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)(unsigned int)InformationProcess,
          ReturnLength);
      }
LABEL_22:
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      ++v3;
    }
    while ( v3 != v4 );
  }
  return 0;
}

```

## disassembly

```asm
0x1801dc728  mov     rax, rsp
0x1801dc72b  mov     [rax+18h], rbx
0x1801dc72f  push    rbp
0x1801dc730  push    rsi
0x1801dc731  push    rdi
0x1801dc732  push    r14
0x1801dc734  push    r15
0x1801dc736  lea     rbp, [rax-5Fh]
0x1801dc73a  sub     rsp, 0D0h
0x1801dc741  movaps  xmmword ptr [rax-38h], xmm6
0x1801dc745  mov     rax, cs:__security_cookie
0x1801dc74c  xor     rax, rsp
0x1801dc74f  mov     [rbp+57h+var_40], rax
0x1801dc753  mov     rsi, rdx
0x1801dc756  mov     rdi, [rcx]
0x1801dc759  mov     r15, [rcx+8]
0x1801dc75d  cmp     rdi, r15
0x1801dc760  jz      loc_1801DC983
0x1801dc766  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801dc76e  mov     r14d, [rdi]
0x1801dc771  mov     [rbp+57h+var_C0], r14d
0x1801dc775  mov     r8d, r14d; dwProcessId
0x1801dc778  xor     edx, edx; bInheritHandle
0x1801dc77a  mov     ecx, 410h; dwDesiredAccess
0x1801dc77f  call    cs:__imp_OpenProcess
0x1801dc785  mov     rbx, rax
0x1801dc788  mov     [rbp+57h+var_B8], rax
0x1801dc78c  test    rax, rax
0x1801dc78f  jz      loc_1801DC92C
0x1801dc795  xorps   xmm0, xmm0
0x1801dc798  movups  [rbp+57h+ProcessInformation], xmm0
0x1801dc79c  movups  [rbp+57h+var_80], xmm0
0x1801dc7a0  movups  [rbp+57h+var_70], xmm0
0x1801dc7a4  mov     qword ptr [rsp+0F0h+ReturnLength], 0; int
0x1801dc7ad  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1801dc7b3  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1801dc7b7  xor     edx, edx; ProcessInformationClass
0x1801dc7b9  mov     rcx, rax; ProcessHandle
0x1801dc7bc  call    cs:__imp_NtQueryInformationProcess
0x1801dc7c2  test    eax, eax
0x1801dc7c4  jns     short loc_1801DC7E3
0x1801dc7c6  mov     rcx, [rbp+5Fh]; this
0x1801dc7ca  mov     r9d, eax; char *
0x1801dc7cd  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801dc7d4  mov     edx, 0CC1h; void *
0x1801dc7d9  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1801dc7de  jmp     loc_1801DC96D
0x1801dc7e3  mov     [rbp+57h+Buffer], 0
0x1801dc7eb  mov     [rbp+57h+NumberOfBytesRead], 0
0x1801dc7f3  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x1801dc7f7  add     rdx, 20h ; ' '; lpBaseAddress
0x1801dc7fb  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1801dc7ff  mov     qword ptr [rsp+0F0h+ReturnLength], rax; unsigned int
0x1801dc804  mov     r9d, 8; nSize
0x1801dc80a  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1801dc80e  mov     rcx, rbx; hProcess
0x1801dc811  call    cs:__imp_ReadProcessMemory
0x1801dc817  test    eax, eax
0x1801dc819  jnz     short loc_1801DC83E
0x1801dc81b  call    cs:__imp_GetLastError
0x1801dc821  mov     edx, 0CD1h; void *
0x1801dc826  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801dc82d  mov     rcx, [rbp+5Fh]; this
0x1801dc831  mov     r9d, eax; char *
0x1801dc834  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801dc839  jmp     loc_1801DC96D
0x1801dc83e  xorps   xmm0, xmm0
0x1801dc841  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x1801dc845  mov     rdx, [rbp+57h+Buffer]
0x1801dc849  add     rdx, 70h ; 'p'; lpBaseAddress
0x1801dc84d  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1801dc851  mov     qword ptr [rsp+0F0h+ReturnLength], rax; lpNumberOfBytesRead
0x1801dc856  mov     r9d, 10h; nSize
0x1801dc85c  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x1801dc860  mov     rcx, rbx; hProcess
0x1801dc863  call    cs:__imp_ReadProcessMemory
0x1801dc869  test    eax, eax
0x1801dc86b  jnz     short loc_1801DC87A
0x1801dc86d  call    cs:__imp_GetLastError
0x1801dc873  mov     edx, 0CDCh
0x1801dc878  jmp     short loc_1801DC826
0x1801dc87a  xorps   xmm0, xmm0
0x1801dc87d  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x1801dc881  movdqu  [rbp+57h+var_50], xmm6
0x1801dc886  xor     eax, eax
0x1801dc888  mov     word ptr [rbp+57h+lpBuffer], ax
0x1801dc88c  movzx   edx, word ptr [rbp+57h+lpBaseAddress]
0x1801dc890  add     rdx, 2
0x1801dc894  lea     rcx, [rbp+57h+lpBuffer]
0x1801dc898  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801dc89d  lea     r8, [rbp+57h+lpBuffer]
0x1801dc8a1  cmp     qword ptr [rbp+57h+var_50+8], 7
0x1801dc8a6  cmova   r8, [rbp+57h+lpBuffer]; lpBuffer
0x1801dc8ab  movzx   r9d, word ptr [rbp+57h+lpBaseAddress]; nSize
0x1801dc8b0  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1801dc8b4  mov     qword ptr [rsp+0F0h+ReturnLength], rax; unsigned int
0x1801dc8b9  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x1801dc8bd  mov     rcx, rbx; hProcess
0x1801dc8c0  call    cs:__imp_ReadProcessMemory
0x1801dc8c6  test    eax, eax
0x1801dc8c8  jnz     short loc_1801DC8EA
0x1801dc8ca  call    cs:__imp_GetLastError
0x1801dc8d0  mov     r9d, eax; char *
0x1801dc8d3  mov     rcx, [rbp+5Fh]; this
0x1801dc8d7  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801dc8de  mov     edx, 0CE9h; void *
0x1801dc8e3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801dc8e8  jmp     short loc_1801DC921
0x1801dc8ea  mov     rdx, [rbp+57h+NumberOfBytesRead]
0x1801dc8ee  shr     rdx, 1
0x1801dc8f1  lea     rcx, [rbp+57h+lpBuffer]
0x1801dc8f5  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801dc8fa  mov     rdx, [rsi+8]
0x1801dc8fe  lea     r9, [rbp+57h+var_C0]
0x1801dc902  lea     r8, [rbp+57h+lpBuffer]
0x1801dc906  cmp     rdx, [rsi+10h]
0x1801dc90a  jz      short loc_1801DC918
0x1801dc90c  call    ??$construct@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEBK@?$_Default_allocator_traits@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@SAXAEAV?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@1@QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBK@Z; std::_Default_allocator_traits<std::allocator<std::pair<std::wstring,ulong>>>::construct<std::pair<std::wstring,ulong>,std::wstring &,ulong const &>(std::allocator<std::pair<std::wstring,ulong>> &,std::pair<std::wstring,ulong> * const,std::wstring &,ulong const &)
0x1801dc911  add     qword ptr [rsi+8], 28h ; '('
0x1801dc916  jmp     short loc_1801DC921
0x1801dc918  mov     rcx, rsi
0x1801dc91b  call    ??$_Emplace_reallocate@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@1@QEAU21@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBK@Z; std::vector<std::pair<std::wstring,ulong>>::_Emplace_reallocate<std::wstring &,ulong const &>(std::pair<std::wstring,ulong> * const,std::wstring &,ulong const &)
0x1801dc920  nop
0x1801dc921  lea     rcx, [rbp+57h+lpBuffer]
0x1801dc925  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801dc92a  jmp     short loc_1801DC96D
0x1801dc92c  mov     eax, cs:dword_1804543B0
0x1801dc932  cmp     eax, 4
0x1801dc935  jbe     short loc_1801DC96D
0x1801dc937  mov     edx, 20000h
0x1801dc93c  lea     rcx, dword_1804543B0
0x1801dc943  call    _tlgKeywordOn
0x1801dc948  test    al, al
0x1801dc94a  jz      short loc_1801DC96D
0x1801dc94c  mov     [rbp+57h+var_C0], r14d
0x1801dc950  lea     rax, [rbp+57h+var_C0]
0x1801dc954  mov     qword ptr [rsp+0F0h+ReturnLength], rax
0x1801dc959  lea     rdx, word_1803F13DA
0x1801dc960  lea     rcx, dword_1804543B0
0x1801dc967  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801dc96c  nop
0x1801dc96d  lea     rcx, [rbp+57h+var_B8]
0x1801dc971  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801dc976  add     rdi, 4
0x1801dc97a  cmp     rdi, r15
0x1801dc97d  jnz     loc_1801DC76E
0x1801dc983  xor     eax, eax
0x1801dc985  mov     rcx, [rbp+57h+var_40]
0x1801dc989  xor     rcx, rsp; StackCookie
0x1801dc98c  call    __security_check_cookie
0x1801dc991  lea     r11, [rsp+0F0h+var_20]
0x1801dc999  mov     rbx, [r11+40h]
0x1801dc99d  movaps  xmm6, xmmword ptr [r11-10h]
0x1801dc9a2  mov     rsp, r11
0x1801dc9a5  pop     r15
0x1801dc9a7  pop     r14
0x1801dc9a9  pop     rdi
0x1801dc9aa  pop     rsi
0x1801dc9ab  pop     rbp
0x1801dc9ac  retn
```
