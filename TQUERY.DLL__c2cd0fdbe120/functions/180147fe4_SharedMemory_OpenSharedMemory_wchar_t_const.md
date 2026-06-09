# SharedMemory::OpenSharedMemory(wchar_t const *)

- ea: `0x180147fe4`
- end: `0x1801480b7`
- name: `?OpenSharedMemory@SharedMemory@@QEAAHPEB_W@Z`
- size: `211`
- prototype: `int(SharedMemory *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180116f0c`
- `0x18019b5c4`

## callees

- `0x180147fe4`
- `0x1801480fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014800a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014800a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148098`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180147ffc`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180147ffc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180148055`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180148055`

## string_xrefs

- `0x180148023`: `[PerfCounter] MSFTESQL: Cannot open shared memory "%ls".  Error 0x%08x in OpenFileMappingW.`
- `0x18014807d`: `[PerfCounter] MSFTESQL: Cannot open shared memory "%ls".  Error 0x%08x in MapViewOfFile.`
- `0x18014802f`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`
- `0x180148089`: `"onecoreuap\\base\\appmodel\\search\\tquery\\dll\\pkmcntrs.cxx"`

## pseudocode

```c
__int64 __fastcall SharedMemory::OpenSharedMemory(SharedMemory *this, const wchar_t *a2)
{
  HANDLE v4; // rax
  signed int LastError; // eax
  LPVOID v7; // rax
  signed int v8; // eax
  signed int dwNumberOfBytesToMapa; // [rsp+20h] [rbp-18h]
  SIZE_T dwNumberOfBytesToMap; // [rsp+20h] [rbp-18h]

  v4 = OpenFileMappingW(4u, 0, a2);
  *(_QWORD *)this = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    dwNumberOfBytesToMapa = LastError;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x40,
      (unsigned int)L"[PerfCounter] MSFTESQL: Cannot open shared memory \"%ls\".  Error 0x%08x in OpenFileMappingW.",
      a2,
      dwNumberOfBytesToMapa);
    return 0;
  }
  v7 = MapViewOfFile(v4, 4u, 0, 0, 0);
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    LODWORD(dwNumberOfBytesToMap) = v8;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\dll\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x4A,
      (unsigned int)L"[PerfCounter] MSFTESQL: Cannot open shared memory \"%ls\".  Error 0x%08x in MapViewOfFile.",
      a2,
      dwNumberOfBytesToMap);
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180147fe4  mov     [rsp+arg_0], rbx
0x180147fe9  push    rdi
0x180147fea  sub     rsp, 30h
0x180147fee  mov     rdi, rdx
0x180147ff1  mov     r8, rdx; lpName
0x180147ff4  xor     edx, edx; bInheritHandle
0x180147ff6  mov     rbx, rcx
0x180147ff9  lea     ecx, [rdx+4]; dwDesiredAccess
0x180147ffc  call    cs:__imp_OpenFileMappingW
0x180148002  mov     [rbx], rax
0x180148005  test    rax, rax
0x180148008  jnz     short loc_18014803F
0x18014800a  call    cs:__imp_GetLastError
0x180148010  test    eax, eax
0x180148012  jle     short loc_18014801C
0x180148014  movzx   eax, ax
0x180148017  or      eax, 80070000h
0x18014801c  mov     r9, rdi; wchar_t *
0x18014801f  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x180148023  lea     r8, aPerfcounterMsf_21; "[PerfCounter] MSFTESQL: Cannot open sha"...
0x18014802a  mov     edx, 40h ; '@'; wchar_t *
0x18014802f  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180148036  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18014803b  xor     eax, eax
0x18014803d  jmp     short loc_1801480AC
0x18014803f  xor     r9d, r9d; dwFileOffsetLow
0x180148042  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18014804b  xor     r8d, r8d; dwFileOffsetHigh
0x18014804e  mov     rcx, rax; hFileMappingObject
0x180148051  lea     edx, [r9+4]; dwDesiredAccess
0x180148055  call    cs:__imp_MapViewOfFile
0x18014805b  mov     [rbx+8], rax
0x18014805f  test    rax, rax
0x180148062  jnz     short loc_1801480A7
0x180148064  call    cs:__imp_GetLastError
0x18014806a  test    eax, eax
0x18014806c  jle     short loc_180148076
0x18014806e  movzx   eax, ax
0x180148071  or      eax, 80070000h
0x180148076  mov     r9, rdi; wchar_t *
0x180148079  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x18014807d  lea     r8, aPerfcounterMsf_11; "[PerfCounter] MSFTESQL: Cannot open sha"...
0x180148084  mov     edx, 4Ah ; 'J'; wchar_t *
0x180148089  lea     rcx, aOnecoreuapBase_279; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180148090  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180148095  mov     rcx, [rbx]; hObject
0x180148098  call    cs:__imp_CloseHandle
0x18014809e  mov     qword ptr [rbx], 0
0x1801480a5  jmp     short loc_18014803B
0x1801480a7  mov     eax, 1
0x1801480ac  mov     rbx, [rsp+38h+arg_0]
0x1801480b1  add     rsp, 30h
0x1801480b5  pop     rdi
0x1801480b6  retn
```
