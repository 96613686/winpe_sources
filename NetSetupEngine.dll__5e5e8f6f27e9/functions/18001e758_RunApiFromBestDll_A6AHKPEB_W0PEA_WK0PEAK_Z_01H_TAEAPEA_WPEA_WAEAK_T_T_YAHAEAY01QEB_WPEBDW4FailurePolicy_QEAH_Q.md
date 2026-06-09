# ??$RunApiFromBestDll@$$A6AHKPEB_W0PEA_WK0PEAK@Z$01H$$TAEAPEA_WPEA_WAEAK$$T$$T@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@$$QEAH$$QEA$$TAEAPEA_W$$QEAPEA_WAEAK44@Z

- ea: `0x18001e758`
- end: `0x18001e993`
- name: `??$RunApiFromBestDll@$$A6AHKPEB_W0PEA_WK0PEAK@Z$01H$$TAEAPEA_WPEA_WAEAK$$T$$T@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@$$QEAH$$QEA$$TAEAPEA_W$$QEAPEA_WAEAK44@Z`
- size: `571`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, _QWORD *, _QWORD *, _QWORD *, _DWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001e110`

## callees

- `0x18001dee8`
- `0x18001e758`
- `0x18005097c`
- `0x18005b188`
- `0x180065035`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001e977`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001e977`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001e867`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001e867`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001e7d7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001e7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e82c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e82c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RunApiFromBestDll<int (unsigned long,wchar_t const *,wchar_t const *,wchar_t *,unsigned long,wchar_t const *,unsigned long *),2,int,std::nullptr_t,wchar_t * &,wchar_t *,unsigned long &,std::nullptr_t,std::nullptr_t>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  void **i; // rbx
  void *v12; // rsi
  HMODULE Library; // rax
  HMODULE v14; // rdi
  DWORD LastError; // eax
  signed int v16; // eax
  FARPROC ProcAddress; // r10
  unsigned int v18; // ebx
  _BYTE pExceptionObject[280]; // [rsp+60h] [rbp-118h] BYREF

  for ( i = (void **)off_180090150; ; ++i )
  {
    if ( i == &NetSetupBindPath::`vftable'{for `INetSetupObjectRelationsProvider'} )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
          "LoadStringByReference");
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024770);
      throw (HResultException *)pExceptionObject;
    }
    v12 = *i;
    Library = LoadLibraryExW((LPCWSTR)*i, 0, 0x800u);
    v14 = Library;
    if ( Library )
      break;
    LastError = GetLastError();
    if ( LastError != 2 && LastError != 126 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids, v12);
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v16);
      throw (HResultException *)pExceptionObject;
    }
  }
  ProcAddress = GetProcAddress(Library, "LoadStringByReference");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
        "LoadStringByReference");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024769);
    throw (HResultException *)pExceptionObject;
  }
  v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD))ProcAddress)(
          *a4,
          *a5,
          *a6,
          *a7,
          *a8,
          *a9,
          *a10);
  FreeLibrary(v14);
  return v18;
}

```

## disassembly

```asm
0x18001e758  push    rbx
0x18001e75a  push    rbp
0x18001e75b  push    rsi
0x18001e75c  push    rdi
0x18001e75d  push    r12
0x18001e75f  push    r13
0x18001e761  push    r14
0x18001e763  push    r15
0x18001e765  sub     rsp, 138h
0x18001e76c  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFEh
0x18001e775  mov     r14, r9
0x18001e778  mov     r15, [rsp+178h+arg_20]
0x18001e780  mov     rbp, [rsp+178h+arg_28]
0x18001e788  mov     r12, [rsp+178h+arg_30]
0x18001e790  mov     r13, [rsp+178h+arg_38]
0x18001e798  mov     rax, [rsp+178h+arg_40]
0x18001e7a0  mov     [rsp+178h+var_130], rax
0x18001e7a5  mov     rax, [rsp+178h+arg_48]
0x18001e7ad  mov     [rsp+178h+var_138], rax
0x18001e7b2  lea     rbx, off_180090150; "api-ms-win-core-localization-private-l1"...
0x18001e7b9  lea     rax, ??_7NetSetupBindPath@@6BINetSetupObjectRelationsProvider@@@; const NetSetupBindPath::`vftable'{for `INetSetupObjectRelationsProvider'}
0x18001e7c0  cmp     rbx, rax
0x18001e7c3  jz      loc_18001E8CE
0x18001e7c9  mov     rsi, [rbx]
0x18001e7cc  xor     edx, edx; hFile
0x18001e7ce  mov     r8d, 800h; dwFlags
0x18001e7d4  mov     rcx, rsi; lpLibFileName
0x18001e7d7  call    cs:__imp_LoadLibraryExW
0x18001e7dd  mov     rdi, rax
0x18001e7e0  test    rax, rax
0x18001e7e3  jnz     short loc_18001E858
0x18001e7e5  call    cs:__imp_GetLastError
0x18001e7eb  cmp     eax, 2
0x18001e7ee  jz      loc_18001E924
0x18001e7f4  cmp     eax, 7Eh ; '~'
0x18001e7f7  jz      loc_18001E924
0x18001e7fd  lea     rax, WPP_GLOBAL_Control
0x18001e804  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e80b  cmp     rcx, rax
0x18001e80e  jz      short loc_18001E82C
0x18001e810  cmp     byte ptr [rcx+19h], 2
0x18001e814  jb      short loc_18001E82C
0x18001e816  lea     edx, [rdi+0Ch]
0x18001e819  mov     r9, rsi
0x18001e81c  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18001e823  mov     rcx, [rcx+10h]
0x18001e827  call    WPP_SF_S
0x18001e82c  call    cs:__imp_GetLastError
0x18001e832  test    eax, eax
0x18001e834  jg      loc_18001E92D
0x18001e83a  mov     edx, eax; int
0x18001e83c  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18001e841  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001e846  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001e84d  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18001e852  call    _CxxThrowException_0
0x18001e858  mov     [rsp+178h+var_120], rdi
0x18001e85d  lea     rdx, aLoadstringbyre; "LoadStringByReference"
0x18001e864  mov     rcx, rdi; hModule
0x18001e867  call    cs:__imp_GetProcAddress
0x18001e86d  mov     r10, rax
0x18001e870  test    rax, rax
0x18001e873  jnz     loc_18001E93A
0x18001e879  lea     rax, WPP_GLOBAL_Control
0x18001e880  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e887  cmp     rcx, rax
0x18001e88a  jz      short loc_18001E8AD
0x18001e88c  cmp     byte ptr [rcx+19h], 2
0x18001e890  jb      short loc_18001E8AD
0x18001e892  lea     edx, [r10+0Bh]
0x18001e896  lea     r9, aLoadstringbyre; "LoadStringByReference"
0x18001e89d  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18001e8a4  mov     rcx, [rcx+10h]
0x18001e8a8  call    WPP_SF_s
0x18001e8ad  mov     edx, 8007007Fh; int
0x18001e8b2  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18001e8b7  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001e8bc  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001e8c3  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18001e8c8  call    _CxxThrowException_0
0x18001e8ce  lea     rax, WPP_GLOBAL_Control
0x18001e8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8dc  cmp     rcx, rax
0x18001e8df  jz      short loc_18001E903
0x18001e8e1  cmp     byte ptr [rcx+19h], 2
0x18001e8e5  jb      short loc_18001E903
0x18001e8e7  mov     edx, 0Dh
0x18001e8ec  lea     r9, aLoadstringbyre; "LoadStringByReference"
0x18001e8f3  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18001e8fa  mov     rcx, [rcx+10h]
0x18001e8fe  call    WPP_SF_s
0x18001e903  mov     edx, 8007007Eh; int
0x18001e908  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18001e90d  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001e912  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001e919  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18001e91e  call    _CxxThrowException_0
0x18001e924  add     rbx, 8
0x18001e928  jmp     loc_18001E7B9
0x18001e92d  movzx   eax, ax
0x18001e930  or      eax, 80070000h
0x18001e935  jmp     loc_18001E83A
0x18001e93a  mov     rax, [rsp+178h+var_138]
0x18001e93f  mov     rax, [rax]
0x18001e942  mov     [rsp+178h+var_148], rax
0x18001e947  mov     rax, [rsp+178h+var_130]
0x18001e94c  mov     rax, [rax]
0x18001e94f  mov     [rsp+178h+var_150], rax
0x18001e954  mov     eax, [r13+0]
0x18001e958  mov     [rsp+178h+var_158], eax
0x18001e95c  mov     r9, [r12]
0x18001e960  mov     r8, [rbp+0]
0x18001e964  mov     rdx, [r15]
0x18001e967  mov     ecx, [r14]
0x18001e96a  mov     rax, r10
0x18001e96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e972  mov     ebx, eax
0x18001e974  mov     rcx, rdi; hLibModule
0x18001e977  call    cs:__imp_FreeLibrary
0x18001e97d  mov     eax, ebx
0x18001e97f  add     rsp, 138h
0x18001e986  pop     r15
0x18001e988  pop     r14
0x18001e98a  pop     r13
0x18001e98c  pop     r12
0x18001e98e  pop     rdi
0x18001e98f  pop     rsi
0x18001e990  pop     rbp
0x18001e991  pop     rbx
0x18001e992  retn
```
