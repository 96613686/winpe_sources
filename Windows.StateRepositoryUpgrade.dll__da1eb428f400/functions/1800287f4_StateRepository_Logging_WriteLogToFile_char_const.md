# StateRepository::Logging::_WriteLogToFile(char const *)

- ea: `0x1800287f4`
- end: `0x18002893f`
- name: `?_WriteLogToFile@Logging@StateRepository@@YAJPEBD@Z`
- size: `331`
- prototype: `signed int __fastcall(_BYTE *lpBuffer, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800284b4`

## callees

- `0x180003980`
- `0x18000a688`
- `0x18000f460`
- `0x180014ca0`
- `0x180026490`
- `0x1800287f4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028898`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800288c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800288c9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800288f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800288f0`

## string_xrefs

- `0x18002886c`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
signed int __fastcall StateRepository::Logging::_WriteLogToFile(_BYTE *lpBuffer, const char *a2)
{
  signed int result; // eax
  int v4; // eax
  __int64 v5; // rsi
  HANDLE FileW; // rbx
  unsigned int v7; // edi
  void *v8; // rdx
  signed int LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-278h]
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( (unsigned int)((__int64 (__fastcall *)(__int64, WCHAR *))qword_18004BFA8)(260, FileName) )
  {
    v4 = StringCchCatW(FileName, 0x104u, qword_18004BFE8);
    if ( v4 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)(unsigned int)v4,
        dwCreationDisposition);
    v5 = -1;
    do
      ++v5;
    while ( lpBuffer[v5] );
    AcquireSRWLockExclusive(&stru_18004BFF8);
    v11 = &stru_18004BFF8;
    FileW = CreateFileW(FileName, 4u, 1u, 0, 4u, 0x80u, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 || (v7 = 0, !WriteFile(FileW, lpBuffer, v5, 0, 0)) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    Common::CloseHandleHelper((Common *)FileW, v8);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    return v7;
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
0x1800287f4  push    rbx
0x1800287f6  push    rbp
0x1800287f7  push    rsi
0x1800287f8  push    rdi
0x1800287f9  sub     rsp, 278h
0x180028800  mov     rax, cs:__security_cookie
0x180028807  xor     rax, rsp
0x18002880a  mov     [rsp+298h+var_38], rax
0x180028812  mov     rax, cs:qword_18004BFA8
0x180028819  lea     rdx, [rsp+298h+FileName]
0x18002881e  mov     rbp, rcx
0x180028821  mov     ebx, 104h
0x180028826  mov     ecx, ebx
0x180028828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882d  test    eax, eax
0x18002882f  jnz     short loc_18002884C
0x180028831  call    cs:__imp_GetLastError
0x180028837  test    eax, eax
0x180028839  jle     loc_180028923
0x18002883f  movzx   eax, ax
0x180028842  or      eax, 80070000h
0x180028847  jmp     loc_180028923
0x18002884c  mov     r8, cs:qword_18004BFE8; unsigned __int16 *
0x180028853  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x180028858  mov     rdx, rbx; unsigned __int64
0x18002885b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028860  test    eax, eax
0x180028862  jns     short loc_180028881
0x180028864  mov     rcx, [rsp+298h]; this
0x18002886c  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180028873  mov     r9d, eax; char *
0x180028876  mov     edx, 119h; void *
0x18002887b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180028881  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028885  inc     rsi
0x180028888  cmp     byte ptr [rsi+rbp], 0
0x18002888c  jnz     short loc_180028885
0x18002888e  lea     rbx, stru_18004BFF8
0x180028895  mov     rcx, rbx; SRWLock
0x180028898  call    cs:__imp_AcquireSRWLockExclusive
0x18002889e  mov     edx, 4; dwDesiredAccess
0x1800288a3  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1800288ac  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800288b4  lea     rcx, [rsp+298h+FileName]; lpFileName
0x1800288b9  xor     r9d, r9d; lpSecurityAttributes
0x1800288bc  mov     [rsp+298h+var_258], rbx
0x1800288c1  mov     [rsp+298h+dwCreationDisposition], edx; dwCreationDisposition
0x1800288c5  lea     r8d, [rdx-3]; dwShareMode
0x1800288c9  call    cs:__imp_CreateFileW
0x1800288cf  mov     rbx, rax
0x1800288d2  inc     rax
0x1800288d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800288db  jz      short loc_1800288FA
0x1800288dd  xor     edi, edi
0x1800288df  mov     r8d, esi; nNumberOfBytesToWrite
0x1800288e2  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800288e5  mov     qword ptr [rsp+298h+dwCreationDisposition], rdi; lpOverlapped
0x1800288ea  mov     rdx, rbp; lpBuffer
0x1800288ed  mov     rcx, rbx; hFile
0x1800288f0  call    cs:__imp_WriteFile
0x1800288f6  test    eax, eax
0x1800288f8  jnz     short loc_18002890F
0x1800288fa  call    cs:__imp_GetLastError
0x180028900  mov     edi, eax
0x180028902  test    eax, eax
0x180028904  jle     short loc_18002890F
0x180028906  movzx   edi, ax
0x180028909  or      edi, 80070000h
0x18002890f  mov     rcx, rbx; this
0x180028912  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x180028917  lea     rcx, [rsp+298h+var_258]
0x18002891c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028921  mov     eax, edi
0x180028923  mov     rcx, [rsp+298h+var_38]
0x18002892b  xor     rcx, rsp; StackCookie
0x18002892e  call    __security_check_cookie
0x180028933  add     rsp, 278h
0x18002893a  pop     rdi
0x18002893b  pop     rsi
0x18002893c  pop     rbp
0x18002893d  pop     rbx
0x18002893e  retn
```
