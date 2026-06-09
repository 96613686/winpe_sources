# StateRepository::Logging::_WriteLogToFile(char const *)

- ea: `0x1800ad3dc`
- end: `0x1800ad51d`
- name: `?_WriteLogToFile@Logging@StateRepository@@YAJPEBD@Z`
- size: `321`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800ad0a4`

## callees

- `0x1800094c0`
- `0x180016d54`
- `0x180021074`
- `0x1800a9434`
- `0x1800ac01c`
- `0x1800ad3dc`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad474`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4d6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ad4cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ad4cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad4a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad4a5`

## string_xrefs

- `0x1800ad44b`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall StateRepository::Logging::_WriteLogToFile(_BYTE *lpBuffer, const char *a2)
{
  unsigned __int64 v3; // rdx
  const wchar_t *v4; // r8
  signed int result; // eax
  int v6; // eax
  __int64 v7; // rsi
  HANDLE FileW; // rbx
  unsigned int v9; // edi
  void *v10; // rdx
  signed int LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-278h]
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( (unsigned int)((__int64 (__fastcall *)(__int64, WCHAR *))qword_180169030)(260, FileName) )
  {
    v6 = StringCchCatW(FileName, v3, v4);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)(unsigned int)v6,
        dwCreationDisposition);
    v7 = -1;
    do
      ++v7;
    while ( lpBuffer[v7] );
    AcquireSRWLockExclusive(&stru_180169078);
    v13 = &stru_180169078;
    FileW = CreateFileW(FileName, 4u, 1u, 0, 4u, 0x80u, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 || (v9 = 0, !WriteFile(FileW, lpBuffer, v7, 0, 0)) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    Common::CloseHandleHelper((Common *)FileW, v10);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800ad3dc  push    rbx
0x1800ad3de  push    rbp
0x1800ad3df  push    rsi
0x1800ad3e0  push    rdi
0x1800ad3e1  sub     rsp, 278h
0x1800ad3e8  mov     rax, cs:__security_cookie
0x1800ad3ef  xor     rax, rsp
0x1800ad3f2  mov     [rsp+298h+var_38], rax
0x1800ad3fa  mov     rbp, rcx
0x1800ad3fd  lea     rdx, [rsp+298h+FileName]
0x1800ad402  mov     ecx, 104h
0x1800ad407  mov     rax, cs:qword_180169030
0x1800ad40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad413  test    eax, eax
0x1800ad415  jnz     short loc_1800AD432
0x1800ad417  call    cs:__imp_GetLastError
0x1800ad41d  test    eax, eax
0x1800ad41f  jle     loc_1800AD501
0x1800ad425  movzx   eax, ax
0x1800ad428  or      eax, 80070000h
0x1800ad42d  jmp     loc_1800AD501
0x1800ad432  lea     rcx, [rsp+298h+FileName]; wchar_t *
0x1800ad437  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800ad43c  mov     rcx, [rsp+298h]; this
0x1800ad444  test    eax, eax
0x1800ad446  jns     short loc_1800AD45D
0x1800ad448  mov     r9d, eax; char *
0x1800ad44b  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x1800ad452  mov     edx, 119h; void *
0x1800ad457  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ad45d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ad461  inc     rsi
0x1800ad464  cmp     byte ptr [rsi+rbp], 0
0x1800ad468  jnz     short loc_1800AD461
0x1800ad46a  lea     rbx, stru_180169078
0x1800ad471  mov     rcx, rbx; SRWLock
0x1800ad474  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad47a  mov     [rsp+298h+var_258], rbx
0x1800ad47f  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1800ad488  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ad490  mov     edx, 4; dwDesiredAccess
0x1800ad495  mov     [rsp+298h+dwCreationDisposition], edx; dwCreationDisposition
0x1800ad499  xor     r9d, r9d; lpSecurityAttributes
0x1800ad49c  lea     r8d, [rdx-3]; dwShareMode
0x1800ad4a0  lea     rcx, [rsp+298h+FileName]; lpFileName
0x1800ad4a5  call    cs:__imp_CreateFileW
0x1800ad4ab  mov     rbx, rax
0x1800ad4ae  inc     rax
0x1800ad4b1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800ad4b7  jz      short loc_1800AD4D6
0x1800ad4b9  xor     edi, edi
0x1800ad4bb  mov     r8d, esi; nNumberOfBytesToWrite
0x1800ad4be  mov     qword ptr [rsp+298h+dwCreationDisposition], rdi; lpOverlapped
0x1800ad4c3  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800ad4c6  mov     rdx, rbp; lpBuffer
0x1800ad4c9  mov     rcx, rbx; hFile
0x1800ad4cc  call    cs:__imp_WriteFile
0x1800ad4d2  test    eax, eax
0x1800ad4d4  jnz     short loc_1800AD4EB
0x1800ad4d6  call    cs:__imp_GetLastError
0x1800ad4dc  test    eax, eax
0x1800ad4de  mov     edi, eax
0x1800ad4e0  jle     short loc_1800AD4EB
0x1800ad4e2  movzx   edi, ax
0x1800ad4e5  or      edi, 80070000h
0x1800ad4eb  mov     rcx, rbx; this
0x1800ad4ee  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800ad4f3  nop
0x1800ad4f4  lea     rcx, [rsp+298h+var_258]
0x1800ad4f9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ad4fe  nop
0x1800ad4ff  mov     eax, edi
0x1800ad501  mov     rcx, [rsp+298h+var_38]
0x1800ad509  xor     rcx, rsp; StackCookie
0x1800ad50c  call    __security_check_cookie
0x1800ad511  add     rsp, 278h
0x1800ad518  pop     rdi
0x1800ad519  pop     rsi
0x1800ad51a  pop     rbp
0x1800ad51b  pop     rbx
0x1800ad51c  retn
```
