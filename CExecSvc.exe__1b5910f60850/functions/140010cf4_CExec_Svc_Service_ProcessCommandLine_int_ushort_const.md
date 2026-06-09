# CExec::Svc::Service::ProcessCommandLine(int,ushort * * const)

- ea: `0x140010cf4`
- end: `0x140010f73`
- name: `?ProcessCommandLine@Service@Svc@CExec@@QEAAHHQEAPEAG@Z`
- size: `639`
- prototype: `__int64 __fastcall(CExec::Svc::Service *__hidden this, int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140014ac0`

## callees

- `0x140002310`
- `0x1400068ac`
- `0x140007a18`
- `0x140008160`
- `0x14000e828`
- `0x14000f3c0`
- `0x14001095c`
- `0x140010cf4`
- `0x1400126b0`
- `0x1400130d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010ecd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010dcd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010e8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010dcd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010e8a`

## string_xrefs

- `0x140010efd`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`
- `0x140010f27`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`
- `0x140010f60`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`
- `0x140010e33`: `write`
- `0x140010f0f`: `onecore\vm\compute\service\cexec\service\cexectools.cpp`
- `0x140010f39`: `onecore\vm\compute\service\cexec\service\cexectools.cpp`

## pseudocode

```c
__int64 __fastcall CExec::Svc::Service::ProcessCommandLine(
        CExec::Svc::Service *this,
        int a2,
        unsigned __int16 **const a3)
{
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const wchar_t *v9; // rcx
  wchar_t *v10; // rax
  unsigned __int64 v11; // rdx
  unsigned int v12; // edx
  void *StandardHandle; // rdi
  char *FileW; // rbx
  void *v15; // r8
  const char *v16; // r9
  wchar_t **v17; // rcx
  void *v18; // rdi
  void *v19; // r8
  const char *v20; // r9
  wil *v21; // rcx
  const char *v22; // r9
  int v23; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-78h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v26; // [rsp+58h] [rbp-40h]
  unsigned __int64 v27; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !a2 )
    return 1;
  v6 = (__int64)*a3;
  *(_OWORD *)S1 = 0;
  v26 = 0;
  v27 = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  try
  {
    std::wstring::_Construct<1,unsigned short const *>(S1, v6, v7);
    v8 = v26;
    v9 = (const wchar_t *)S1;
    v10 = S1[0];
    v11 = v27;
    if ( v27 > 7 )
      v9 = S1[0];
    if ( v26 == 4 )
    {
      if ( !wmemcmp(v9, L"read", 4u) )
      {
        StandardHandle = CExec::Svc::GetStandardHandle((CExec::Svc *)0xFFFFFFF5LL, v12);
        if ( a2 == 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
            (const char *)0x80070057LL,
            dwCreationDisposition);
        FileW = (char *)CreateFileW(a3[1], 0x80000000, 7u, 0, 3u, 0x80u, 0);
        if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x47,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexectools.cpp",
            v16);
        CExec::Tools::CopyData(FileW, StandardHandle, v15);
LABEL_21:
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
        std::wstring::~wstring(S1);
        return 0;
      }
      v11 = v27;
      v8 = v26;
      v10 = S1[0];
    }
    v17 = S1;
    if ( v11 > 7 )
      v17 = (wchar_t **)v10;
    if ( v8 != 5 || wmemcmp((const wchar_t *)v17, L"write", 5u) )
    {
      v22 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL, v11);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
        v22,
        dwCreationDisposition);
    }
    v18 = CExec::Svc::GetStandardHandle((CExec::Svc *)0xFFFFFFF6LL, v11);
    if ( a2 == 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    FileW = (char *)CreateFileW(a3[1], 0x40000000u, 7u, 0, 2u, 0x80u, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexectools.cpp",
        v20);
    CExec::Tools::CopyData(v18, FileW, v19);
    goto LABEL_21;
  }
  catch ( ... )
  {
    v23 = wil::ResultFromCaughtException(v21);
    exit(v23);
  }
  return result;
}

```

## disassembly

```asm
0x140010cf4  push    rbx
0x140010cf6  push    rsi
0x140010cf7  push    rdi
0x140010cf8  push    r14
0x140010cfa  sub     rsp, 78h
0x140010cfe  mov     rax, cs:__security_cookie
0x140010d05  xor     rax, rsp
0x140010d08  mov     [rsp+98h+var_30], rax
0x140010d0d  mov     rsi, r8
0x140010d10  mov     ebx, edx
0x140010d12  xor     r14d, r14d
0x140010d15  test    edx, edx
0x140010d17  jnz     short loc_140010D21
0x140010d19  lea     eax, [rdx+1]
0x140010d1c  jmp     loc_140010EE0
0x140010d21  mov     rdx, [r8]
0x140010d24  xorps   xmm0, xmm0
0x140010d27  movups  xmmword ptr [rsp+98h+S1], xmm0
0x140010d2c  mov     [rsp+98h+var_40], r14
0x140010d31  mov     [rsp+98h+var_38], r14
0x140010d36  or      r8, 0FFFFFFFFFFFFFFFFh
0x140010d3a  inc     r8
0x140010d3d  cmp     [rdx+r8*2], r14w
0x140010d42  jnz     short loc_140010D3A
0x140010d44  lea     rcx, [rsp+98h+S1]
0x140010d49  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010d4e  nop
0x140010d4f  mov     r9, [rsp+98h+var_40]
0x140010d54  lea     rcx, [rsp+98h+S1]
0x140010d59  mov     rax, [rsp+98h+S1]
0x140010d5e  mov     rdx, [rsp+98h+var_38]
0x140010d63  cmp     rdx, 7
0x140010d67  cmova   rcx, rax; S1
0x140010d6b  mov     r8d, 4; N
0x140010d71  cmp     r9, r8
0x140010d74  jnz     loc_140010E17
0x140010d7a  lea     rdx, aRead; "read"
0x140010d81  call    wmemcmp
0x140010d86  test    eax, eax
0x140010d88  jnz     short loc_140010E08
0x140010d8a  mov     ecx, 0FFFFFFF5h; this
0x140010d8f  call    ?GetStandardHandle@Svc@CExec@@YAPEAXK@Z; CExec::Svc::GetStandardHandle(ulong)
0x140010d94  mov     rdi, rax
0x140010d97  mov     rcx, [rsp+98h]; this
0x140010d9f  cmp     ebx, 1
0x140010da2  jz      loc_140010EF7
0x140010da8  mov     [rsp+98h+hTemplateFile], r14; hTemplateFile
0x140010dad  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140010db5  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x140010dbd  xor     r9d, r9d; lpSecurityAttributes
0x140010dc0  mov     edx, 80000000h; dwDesiredAccess
0x140010dc5  lea     r8d, [r9+7]; dwShareMode
0x140010dc9  mov     rcx, [rsi+8]; lpFileName
0x140010dcd  call    cs:__imp_CreateFileW
0x140010dd3  mov     rbx, rax
0x140010dd6  mov     [rsp+98h+var_58], rax
0x140010ddb  inc     rax
0x140010dde  test    rax, 0FFFFFFFFFFFFFFFEh
0x140010de4  setz    al
0x140010de7  mov     rcx, [rsp+98h]; this
0x140010def  test    al, al
0x140010df1  jnz     loc_140010F0F
0x140010df7  mov     rdx, rdi; HANDLE
0x140010dfa  mov     rcx, rbx; hFile
0x140010dfd  call    ?CopyData@Tools@CExec@@YAXPEAX0@Z; CExec::Tools::CopyData(void *,void *)
0x140010e02  nop
0x140010e03  jmp     loc_140010EC0
0x140010e08  mov     rdx, [rsp+98h+var_38]
0x140010e0d  mov     r9, [rsp+98h+var_40]
0x140010e12  mov     rax, [rsp+98h+S1]
0x140010e17  lea     rcx, [rsp+98h+S1]
0x140010e1c  cmp     rdx, 7
0x140010e20  cmova   rcx, rax; S1
0x140010e24  mov     r8d, 5; N
0x140010e2a  cmp     r9, r8
0x140010e2d  jnz     loc_140010F4B
0x140010e33  lea     rdx, aWrite; "write"
0x140010e3a  call    wmemcmp
0x140010e3f  test    eax, eax
0x140010e41  jnz     loc_140010F4B
0x140010e47  mov     ecx, 0FFFFFFF6h; this
0x140010e4c  call    ?GetStandardHandle@Svc@CExec@@YAPEAXK@Z; CExec::Svc::GetStandardHandle(ulong)
0x140010e51  mov     rdi, rax
0x140010e54  mov     rcx, [rsp+98h]; this
0x140010e5c  cmp     ebx, 1
0x140010e5f  jz      loc_140010F21
0x140010e65  mov     [rsp+98h+hTemplateFile], r14; hTemplateFile
0x140010e6a  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140010e72  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x140010e7a  xor     r9d, r9d; lpSecurityAttributes
0x140010e7d  mov     edx, 40000000h; dwDesiredAccess
0x140010e82  lea     r8d, [r9+7]; dwShareMode
0x140010e86  mov     rcx, [rsi+8]; lpFileName
0x140010e8a  call    cs:__imp_CreateFileW
0x140010e90  mov     rbx, rax
0x140010e93  mov     [rsp+98h+var_58], rax
0x140010e98  inc     rax
0x140010e9b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140010ea1  setz    al
0x140010ea4  mov     rcx, [rsp+98h]; this
0x140010eac  test    al, al
0x140010eae  jnz     loc_140010F39
0x140010eb4  mov     rdx, rbx; HANDLE
0x140010eb7  mov     rcx, rdi; hFile
0x140010eba  call    ?CopyData@Tools@CExec@@YAXPEAX0@Z; CExec::Tools::CopyData(void *,void *)
0x140010ebf  nop
0x140010ec0  lea     rax, [rbx-1]
0x140010ec4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140010ec8  ja      short loc_140010ED4
0x140010eca  mov     rcx, rbx; hObject
0x140010ecd  call    cs:__imp_CloseHandle
0x140010ed3  nop
0x140010ed4  lea     rcx, [rsp+98h+S1]
0x140010ed9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010ede  xor     eax, eax
0x140010ee0  mov     rcx, [rsp+98h+var_30]
0x140010ee5  xor     rcx, rsp; StackCookie
0x140010ee8  call    __security_check_cookie
0x140010eed  add     rsp, 78h
0x140010ef1  pop     r14
0x140010ef3  pop     rdi
0x140010ef4  pop     rsi
0x140010ef5  pop     rbx
0x140010ef6  retn
0x140010ef7  mov     r9d, 80070057h; char *
0x140010efd  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010f04  mov     edx, 0D6h; void *
0x140010f09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010f0f  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010f16  mov     edx, 47h ; 'G'; void *
0x140010f1b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140010f21  mov     r9d, 80070057h; char *
0x140010f27  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010f2e  mov     edx, 0D6h; void *
0x140010f33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010f39  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010f40  mov     edx, 57h ; 'W'; void *
0x140010f45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140010f4b  mov     ecx, 80070057h
0x140010f50  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140010f55  mov     r9d, eax; char *
0x140010f58  mov     rcx, [rsp+98h]; this
0x140010f60  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010f67  mov     edx, 0E5h; void *
0x140010f6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
