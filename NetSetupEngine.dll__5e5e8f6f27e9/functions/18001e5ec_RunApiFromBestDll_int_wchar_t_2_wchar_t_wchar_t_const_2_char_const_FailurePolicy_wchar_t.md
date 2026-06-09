# RunApiFromBestDll<int (wchar_t *),2,wchar_t * &>(wchar_t const * (&)[2],char const *,FailurePolicy,wchar_t * &)

- ea: `0x18001e5ec`
- end: `0x18001e750`
- name: `??$RunApiFromBestDll@$$A6AHPEA_W@Z$01AEAPEA_W@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@AEAPEA_W@Z`
- size: `356`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e110`

## callees

- `0x18001dee8`
- `0x18001e5ec`
- `0x18005097c`
- `0x18005b188`
- `0x180065035`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001e72c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001e72c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001e6be`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001e6be`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001e62a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001e62a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e73b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e73b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RunApiFromBestDll<int (wchar_t *),2,wchar_t * &>(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  wchar_t **i; // rbx
  wchar_t *v6; // rsi
  HMODULE Library; // rax
  HMODULE v8; // rdi
  DWORD LastError; // eax
  signed int v10; // eax
  FARPROC ProcAddress; // rax
  unsigned int v12; // ebx
  _BYTE pExceptionObject[248]; // [rsp+30h] [rbp-F8h] BYREF

  for ( i = off_180090140; ; ++i )
  {
    if ( i == off_180090150 )
    {
      SetLastError(0x7Eu);
      return 0;
    }
    v6 = *i;
    Library = LoadLibraryExW(*i, 0, 0x800u);
    v8 = Library;
    if ( Library )
      break;
    LastError = GetLastError();
    if ( LastError != 2 && LastError != 126 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids, v6);
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v10);
      throw (HResultException *)pExceptionObject;
    }
  }
  ProcAddress = GetProcAddress(Library, "SpInfIsIndirectString");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
        "SpInfIsIndirectString");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024769);
    throw (HResultException *)pExceptionObject;
  }
  v12 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(*a4);
  FreeLibrary(v8);
  return v12;
}

```

## disassembly

```asm
0x18001e5ec  push    rbx
0x18001e5ee  push    rsi
0x18001e5ef  push    rdi
0x18001e5f0  push    r14
0x18001e5f2  sub     rsp, 108h
0x18001e5f9  mov     [rsp+128h+var_108], 0FFFFFFFFFFFFFFFEh
0x18001e602  mov     r14, r9
0x18001e605  lea     rbx, off_180090140; "ext-ms-win-spinf-inf-l1-1-0.dll"
0x18001e60c  lea     rax, off_180090150; "api-ms-win-core-localization-private-l1"...
0x18001e613  cmp     rbx, rax
0x18001e616  jz      loc_18001E736
0x18001e61c  mov     rsi, [rbx]
0x18001e61f  xor     edx, edx; hFile
0x18001e621  mov     r8d, 800h; dwFlags
0x18001e627  mov     rcx, rsi; lpLibFileName
0x18001e62a  call    cs:__imp_LoadLibraryExW
0x18001e630  mov     rdi, rax
0x18001e633  test    rax, rax
0x18001e636  jnz     short loc_18001E6AF
0x18001e638  call    cs:__imp_GetLastError
0x18001e63e  cmp     eax, 2
0x18001e641  jz      short loc_18001E648
0x18001e643  cmp     eax, 7Eh ; '~'
0x18001e646  jnz     short loc_18001E64E
0x18001e648  add     rbx, 8
0x18001e64c  jmp     short loc_18001E60C
0x18001e64e  lea     rax, WPP_GLOBAL_Control
0x18001e655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e65c  cmp     rcx, rax
0x18001e65f  jz      short loc_18001E67F
0x18001e661  cmp     byte ptr [rcx+19h], 2
0x18001e665  jb      short loc_18001E67F
0x18001e667  mov     edx, 0Ch
0x18001e66c  mov     r9, rsi
0x18001e66f  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18001e676  mov     rcx, [rcx+10h]
0x18001e67a  call    WPP_SF_S
0x18001e67f  call    cs:__imp_GetLastError
0x18001e685  test    eax, eax
0x18001e687  jle     short loc_18001E691
0x18001e689  movzx   eax, ax
0x18001e68c  or      eax, 80070000h
0x18001e691  mov     edx, eax; int
0x18001e693  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18001e698  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001e69d  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001e6a4  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18001e6a9  call    _CxxThrowException_0
0x18001e6af  mov     [rsp+128h+var_100], rdi
0x18001e6b4  lea     rdx, aSpinfisindirec; "SpInfIsIndirectString"
0x18001e6bb  mov     rcx, rdi; hModule
0x18001e6be  call    cs:__imp_GetProcAddress
0x18001e6c4  test    rax, rax
0x18001e6c7  jnz     short loc_18001E71F
0x18001e6c9  lea     rax, WPP_GLOBAL_Control
0x18001e6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6d7  cmp     rcx, rax
0x18001e6da  jz      short loc_18001E6FE
0x18001e6dc  cmp     byte ptr [rcx+19h], 2
0x18001e6e0  jb      short loc_18001E6FE
0x18001e6e2  mov     edx, 0Bh
0x18001e6e7  lea     r9, aSpinfisindirec; "SpInfIsIndirectString"
0x18001e6ee  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18001e6f5  mov     rcx, [rcx+10h]
0x18001e6f9  call    WPP_SF_s
0x18001e6fe  mov     edx, 8007007Fh; int
0x18001e703  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18001e708  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001e70d  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001e714  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18001e719  call    _CxxThrowException_0
0x18001e71f  mov     rcx, [r14]
0x18001e722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e727  mov     ebx, eax
0x18001e729  mov     rcx, rdi; hLibModule
0x18001e72c  call    cs:__imp_FreeLibrary
0x18001e732  mov     eax, ebx
0x18001e734  jmp     short loc_18001E743
0x18001e736  mov     ecx, 7Eh ; '~'; dwErrCode
0x18001e73b  call    cs:__imp_SetLastError
0x18001e741  xor     eax, eax
0x18001e743  add     rsp, 108h
0x18001e74a  pop     r14
0x18001e74c  pop     rdi
0x18001e74d  pop     rsi
0x18001e74e  pop     rbx
0x18001e74f  retn
```
