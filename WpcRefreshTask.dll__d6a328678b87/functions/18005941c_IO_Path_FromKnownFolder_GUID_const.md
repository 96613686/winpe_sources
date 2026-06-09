# IO::Path::FromKnownFolder(_GUID const &)

- ea: `0x18005941c`
- end: `0x1800595b8`
- name: `?FromKnownFolder@Path@IO@@SA?AV12@AEBU_GUID@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ed0`
- `0x18005c6e8`
- `0x180092c78`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000947c`
- `0x180035048`
- `0x180035e0c`
- `0x180046618`
- `0x180059348`
- `0x18005941c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005944f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005944f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005953f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005953f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18005945c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18005945c`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800594dc`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800594dc`

## string_xrefs

- `0x1800594b3`: `%CommonProgramW6432%`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IO::Path::FromKnownFolder(__int64 a1, const KNOWNFOLDERID *a2)
{
  HANDLE CurrentProcess; // rax
  const wchar_t *v5; // rdx
  PWSTR *v6; // rax
  HRESULT v7; // esi
  _BYTE *v8; // rdx
  WINBOOL Wow64Process; // [rsp+30h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+40h] [rbp-59h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v14; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v15[56]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE *v16; // [rsp+C0h] [rbp+27h]

  v12 = a1;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  IsWow64Process(CurrentProcess, &Wow64Process);
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)FOLDERID_ProgramFilesX64.Data4
    && Wow64Process )
  {
    v5 = L"%ProgramW6432%";
LABEL_5:
    IO::Path::Expand(a1, v5);
    return a1;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)FOLDERID_ProgramFilesCommonX64.Data4
    && Wow64Process )
  {
    v5 = L"%CommonProgramW6432%";
    goto LABEL_5;
  }
  pv = 0;
  v6 = (PWSTR *)stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v14, (__int64)&pv);
  v7 = SHGetKnownFolderPath(a2, 0, 0, v6);
  if ( v16 )
  {
    v12 = v14;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v16 + 16LL))(v16, &v12);
    if ( v16 )
    {
      v8 = v15;
      LOBYTE(v8) = v16 != v15;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v8);
    }
  }
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF__guid_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_87d25b4ffdd3312c856701944764eac7_Traceguids,
        a2,
        v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  std::wstring::wstring(a1, pv);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x18005941c  mov     [rsp-8+arg_10], rbx
0x180059421  push    rbp
0x180059422  push    rsi
0x180059423  push    rdi
0x180059424  lea     rbp, [rsp-47h]
0x180059429  sub     rsp, 0E0h
0x180059430  mov     rax, cs:__security_cookie
0x180059437  xor     rax, rsp
0x18005943a  mov     [rbp+57h+var_20], rax
0x18005943e  mov     rdi, rdx
0x180059441  mov     rbx, rcx
0x180059444  mov     [rbp+57h+var_B0], rcx
0x180059448  mov     [rbp+57h+Wow64Process], 0
0x18005944f  call    cs:__imp_GetCurrentProcess
0x180059455  mov     rcx, rax; hProcess
0x180059458  lea     rdx, [rbp+57h+Wow64Process]; Wow64Process
0x18005945c  call    cs:__imp_IsWow64Process
0x180059462  mov     rcx, [rdi]
0x180059465  mov     edx, [rbp+57h+Wow64Process]
0x180059468  cmp     rcx, qword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x18005946f  jnz     short loc_180059496
0x180059471  mov     rcx, [rdi+8]
0x180059475  cmp     rcx, qword ptr cs:FOLDERID_ProgramFilesX64.Data4
0x18005947c  jnz     short loc_180059496
0x18005947e  test    edx, edx
0x180059480  jz      short loc_180059496
0x180059482  lea     rdx, aProgramw6432; "%ProgramW6432%"
0x180059489  mov     rcx, rbx
0x18005948c  call    ?Expand@Path@IO@@SA?AV12@PEBG@Z; IO::Path::Expand(ushort const *)
0x180059491  jmp     loc_180059545
0x180059496  mov     rax, [rdi]
0x180059499  cmp     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data1
0x1800594a0  jnz     short loc_1800594BC
0x1800594a2  mov     rax, [rdi+8]
0x1800594a6  cmp     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data4
0x1800594ad  jnz     short loc_1800594BC
0x1800594af  test    edx, edx
0x1800594b1  jz      short loc_1800594BC
0x1800594b3  lea     rdx, aCommonprogramw; "%CommonProgramW6432%"
0x1800594ba  jmp     short loc_180059489
0x1800594bc  mov     [rbp+57h+pv], 0
0x1800594c4  lea     rdx, [rbp+57h+pv]
0x1800594c8  lea     rcx, [rbp+57h+var_70]
0x1800594cc  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x1800594d1  mov     r9, rax; ppszPath
0x1800594d4  xor     r8d, r8d; hToken
0x1800594d7  xor     edx, edx; dwFlags
0x1800594d9  mov     rcx, rdi; rfid
0x1800594dc  call    cs:__imp_SHGetKnownFolderPath
0x1800594e2  mov     esi, eax
0x1800594e4  mov     rcx, [rbp+57h+var_30]
0x1800594e8  test    rcx, rcx
0x1800594eb  jz      short loc_180059525
0x1800594ed  mov     rdx, [rbp+57h+var_70]
0x1800594f1  mov     [rbp+57h+var_B0], rdx
0x1800594f5  mov     rdx, [rcx]
0x1800594f8  mov     rax, [rdx+10h]
0x1800594fc  lea     rdx, [rbp+57h+var_B0]
0x180059500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059505  mov     rcx, [rbp+57h+var_30]
0x180059509  test    rcx, rcx
0x18005950c  jz      short loc_180059525
0x18005950e  mov     rax, [rcx]
0x180059511  lea     rdx, [rbp+57h+var_68]
0x180059515  cmp     rcx, rdx
0x180059518  setnz   dl
0x18005951b  mov     rax, [rax+20h]
0x18005951f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059524  nop
0x180059525  test    esi, esi
0x180059527  js      short loc_180059567
0x180059529  mov     rdx, [rbp+57h+pv]
0x18005952d  mov     rcx, rbx
0x180059530  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180059535  nop
0x180059536  mov     rcx, [rbp+57h+pv]; pv
0x18005953a  test    rcx, rcx
0x18005953d  jz      short loc_180059545
0x18005953f  call    cs:__imp_CoTaskMemFree
0x180059545  mov     rax, rbx
0x180059548  mov     rcx, [rbp+57h+var_20]
0x18005954c  xor     rcx, rsp; StackCookie
0x18005954f  call    __security_check_cookie
0x180059554  mov     rbx, [rsp+0F0h+arg_10]
0x18005955c  add     rsp, 0E0h
0x180059563  pop     rdi
0x180059564  pop     rsi
0x180059565  pop     rbp
0x180059566  retn
0x180059567  lea     rax, WPP_GLOBAL_Control
0x18005956e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059575  cmp     rcx, rax
0x180059578  jz      short loc_18005959C
0x18005957a  test    byte ptr [rcx+1Ch], 1
0x18005957e  jz      short loc_18005959C
0x180059580  mov     edx, 0Ch
0x180059585  mov     [rsp+0F0h+var_D0], esi
0x180059589  mov     r9, rdi
0x18005958c  lea     r8, WPP_87d25b4ffdd3312c856701944764eac7_Traceguids
0x180059593  mov     rcx, [rcx+10h]
0x180059597  call    WPP_SF__guid_d
0x18005959c  mov     edx, esi; int
0x18005959e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800595a2  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800595a7  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800595ae  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800595b2  call    _CxxThrowException_0
```
