# RecursiveUtil::DeleteCallback(RecursiveUtil::SCAN_STATE,ushort const *,RecursiveUtil::NtObjectPath const &,_WIN32_FIND_DATAW *,ulong)

- ea: `0x18003af94`
- end: `0x18003b1ac`
- name: `?DeleteCallback@RecursiveUtil@@YAJW4SCAN_STATE@1@PEBGAEBVNtObjectPath@1@PEAU_WIN32_FIND_DATAW@@K@Z`
- size: `536`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18003b474`

## callees

- `0x18000d030`
- `0x180012714`
- `0x180012734`
- `0x180019d4c`
- `0x18001c208`
- `0x18001dcf4`
- `0x18003a8f8`
- `0x18003a9c4`
- `0x18003af94`
- `0x18003be84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b082`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b006`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b054`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b006`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b054`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003b137`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003b137`

## string_xrefs

- `0x18003b0af`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b0ed`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b14d`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RecursiveUtil::DeleteCallback(__int64 a1, const WCHAR *a2, __int64 a3, _DWORD *a4, unsigned int a5)
{
  char v7; // bl
  DWORD dwFlagsAndAttributes; // esi
  HANDLE FileW; // rax
  unsigned int v10; // r8d
  void *v11; // rdi
  HANDLE v12; // rax
  signed int v13; // eax
  unsigned int LastError; // ebx
  int v15; // eax
  const char *v16; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-78h]
  char FileInformation[8]; // [rsp+40h] [rbp-58h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v7 = a5 & 1;
  dwFlagsAndAttributes = (*a4 & 0x10 | 1) << 21;
  FileW = CreateFileW(a2, (a5 & 1) != 0 ? 65920 : 0x10000, 1u, 0, 3u, dwFlagsAndAttributes, 0);
  v11 = FileW;
  v20 = FileW;
  if ( (a5 & 1) != 0 && (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && GetLastError() == 5 )
  {
    v7 = 0;
    v12 = CreateFileW(a2, 0x10000u, 1u, 0, 3u, dwFlagsAndAttributes, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v20,
      v12);
    v11 = v20;
  }
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( v7 && (v15 = RecursiveUtil::RemoveReadOnly(v11, (void *)a5, v10), LastError = v15, v15 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
    }
    else
    {
      RecursiveUtil::NtObjectPath::NtObjectPath((RecursiveUtil::NtObjectPath *)v21, v11);
      if ( !(unsigned __int8)RecursiveUtil::operator==(v21, a3)
        || (FileInformation[0] = 1, SetFileInformationByHandle(v11, FileDispositionInfo, FileInformation, 1u))
        || (a5 & 4) != 0 )
      {
        std::wstring::_Tidy_deallocate(v21);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x118,
                      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                      v16);
        std::wstring::_Tidy_deallocate(v21);
      }
    }
  }
  else
  {
    v13 = GetLastError();
    LastError = v13;
    if ( (a5 & 4) != 0 || v13 == 2 )
    {
      LastError = 0;
    }
    else
    {
      if ( v13 > 0 )
        LastError = (unsigned __int16)v13 | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
          (const char *)LastError,
          dwCreationDisposition);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  return LastError;
}

```

## disassembly

```asm
0x18003af94  mov     [rsp+arg_0], rbx
0x18003af99  mov     [rsp+arg_18], rsi
0x18003af9e  push    rdi
0x18003af9f  push    r14
0x18003afa1  push    r15
0x18003afa3  sub     rsp, 80h
0x18003afaa  mov     rax, cs:__security_cookie
0x18003afb1  xor     rax, rsp
0x18003afb4  mov     [rsp+98h+var_28], rax
0x18003afb9  mov     r15, r8
0x18003afbc  mov     r14, rdx
0x18003afbf  mov     bl, byte ptr [rsp+98h+arg_20]
0x18003afc6  and     bl, 1
0x18003afc9  mov     esi, [r9]
0x18003afcc  and     esi, 10h
0x18003afcf  or      esi, 1
0x18003afd2  shl     esi, 15h
0x18003afd5  mov     al, bl
0x18003afd7  neg     al
0x18003afd9  sbb     edx, edx
0x18003afdb  and     edx, 180h
0x18003afe1  add     edx, 10000h; dwDesiredAccess
0x18003afe7  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18003aff0  mov     [rsp+98h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003aff4  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18003affc  xor     r9d, r9d; lpSecurityAttributes
0x18003afff  lea     r8d, [r9+1]; dwShareMode
0x18003b003  mov     rcx, r14; lpFileName
0x18003b006  call    cs:__imp_CreateFileW
0x18003b00c  mov     rdi, rax
0x18003b00f  mov     [rsp+98h+var_50], rax
0x18003b014  test    bl, bl
0x18003b016  jz      short loc_18003B06C
0x18003b018  inc     rax
0x18003b01b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003b021  jnz     short loc_18003B06C
0x18003b023  call    cs:__imp_GetLastError
0x18003b029  cmp     eax, 5
0x18003b02c  jnz     short loc_18003B06C
0x18003b02e  xor     bl, bl
0x18003b030  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18003b039  mov     [rsp+98h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003b03d  mov     [rsp+98h+dwCreationDisposition], 3; int
0x18003b045  xor     r9d, r9d; lpSecurityAttributes
0x18003b048  mov     edx, 10000h; dwDesiredAccess
0x18003b04d  lea     r8d, [rax-4]; dwShareMode
0x18003b051  mov     rcx, r14; lpFileName
0x18003b054  call    cs:__imp_CreateFileW
0x18003b05a  mov     rdx, rax
0x18003b05d  lea     rcx, [rsp+98h+var_50]
0x18003b062  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003b067  mov     rdi, [rsp+98h+var_50]
0x18003b06c  mov     esi, dword ptr [rsp+98h+arg_20]
0x18003b073  and     esi, 4
0x18003b076  lea     rax, [rdi+1]
0x18003b07a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003b080  jnz     short loc_18003B0C9
0x18003b082  call    cs:__imp_GetLastError
0x18003b088  mov     ebx, eax
0x18003b08a  test    esi, esi
0x18003b08c  jnz     short loc_18003B0C2
0x18003b08e  cmp     eax, 2
0x18003b091  jz      short loc_18003B0C2
0x18003b093  test    eax, eax
0x18003b095  jle     short loc_18003B0A0
0x18003b097  movzx   ebx, ax
0x18003b09a  or      ebx, 80070000h
0x18003b0a0  test    ebx, ebx
0x18003b0a2  jns     short loc_18003B0C4
0x18003b0a4  mov     rcx, [rsp+98h]; this
0x18003b0ac  mov     r9d, ebx; char *
0x18003b0af  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b0b6  mov     edx, 107h; void *
0x18003b0bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b0c0  jmp     short loc_18003B0C4
0x18003b0c2  xor     ebx, ebx
0x18003b0c4  jmp     loc_18003B17A
0x18003b0c9  test    bl, bl
0x18003b0cb  jz      short loc_18003B101
0x18003b0cd  mov     edx, dword ptr [rsp+98h+arg_20]; void *
0x18003b0d4  mov     rcx, rdi; hFile
0x18003b0d7  call    ?RemoveReadOnly@RecursiveUtil@@YAJPEAXK@Z; RecursiveUtil::RemoveReadOnly(void *,ulong)
0x18003b0dc  mov     ebx, eax
0x18003b0de  test    eax, eax
0x18003b0e0  jns     short loc_18003B101
0x18003b0e2  mov     rcx, [rsp+98h]; this
0x18003b0ea  mov     r9d, eax; char *
0x18003b0ed  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b0f4  mov     edx, 10Ch; void *
0x18003b0f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b0fe  nop
0x18003b0ff  jmp     short loc_18003B17A
0x18003b101  mov     rdx, rdi; void *
0x18003b104  lea     rcx, [rsp+98h+var_48]; this
0x18003b109  call    ??0NtObjectPath@RecursiveUtil@@QEAA@PEAX@Z; RecursiveUtil::NtObjectPath::NtObjectPath(void *)
0x18003b10e  nop
0x18003b10f  mov     rdx, r15
0x18003b112  lea     rcx, [rsp+98h+var_48]
0x18003b117  call    ??8RecursiveUtil@@YA_NAEBVNtObjectPath@0@0@Z; RecursiveUtil::operator==(RecursiveUtil::NtObjectPath const &,RecursiveUtil::NtObjectPath const &)
0x18003b11c  test    al, al
0x18003b11e  jz      short loc_18003B16D
0x18003b120  mov     [rsp+98h+FileInformation], 1
0x18003b125  mov     r9d, 1; dwBufferSize
0x18003b12b  lea     r8, [rsp+98h+FileInformation]; lpFileInformation
0x18003b130  lea     edx, [r9+3]; FileInformationClass
0x18003b134  mov     rcx, rdi; hFile
0x18003b137  call    cs:__imp_SetFileInformationByHandle
0x18003b13d  test    eax, eax
0x18003b13f  jnz     short loc_18003B16D
0x18003b141  test    esi, esi
0x18003b143  jnz     short loc_18003B16D
0x18003b145  mov     rcx, [rsp+98h]; this
0x18003b14d  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b154  mov     edx, 118h; void *
0x18003b159  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b15e  mov     ebx, eax
0x18003b160  lea     rcx, [rsp+98h+var_48]
0x18003b165  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b16a  nop
0x18003b16b  jmp     short loc_18003B17A
0x18003b16d  lea     rcx, [rsp+98h+var_48]
0x18003b172  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b177  nop
0x18003b178  xor     ebx, ebx
0x18003b17a  lea     rcx, [rsp+98h+var_50]
0x18003b17f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003b184  mov     eax, ebx
0x18003b186  mov     rcx, [rsp+98h+var_28]
0x18003b18b  xor     rcx, rsp; StackCookie
0x18003b18e  call    __security_check_cookie
0x18003b193  lea     r11, [rsp+98h+var_18]
0x18003b19b  mov     rbx, [r11+20h]
0x18003b19f  mov     rsi, [r11+38h]
0x18003b1a3  mov     rsp, r11
0x18003b1a6  pop     r15
0x18003b1a8  pop     r14
0x18003b1aa  pop     rdi
0x18003b1ab  retn
```
