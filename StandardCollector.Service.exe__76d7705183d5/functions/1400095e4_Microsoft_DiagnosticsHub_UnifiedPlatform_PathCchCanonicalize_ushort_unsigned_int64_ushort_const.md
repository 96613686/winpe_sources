# Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400095e4`
- end: `0x1400097cf`
- name: `?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::UnifiedPlatform *__hidden this, unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000e7fc`
- `0x14000eaec`

## callees

- `0x1400095e4`
- `0x1400138ac`
- `0x140013918`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009683`
- `KERNEL32!GetProcAddress` at `0x14000973c`
- `KERNEL32!GetProcAddress` at `0x140009683`
- `KERNEL32!GetProcAddress` at `0x14000973c`
- `KERNEL32!LoadLibraryExW` at `0x140009667`
- `KERNEL32!LoadLibraryExW` at `0x140009720`
- `KERNEL32!LoadLibraryExW` at `0x140009667`
- `KERNEL32!LoadLibraryExW` at `0x140009720`
- `KERNEL32!GetLastError` at `0x140009695`
- `KERNEL32!GetLastError` at `0x14000974e`
- `KERNEL32!GetLastError` at `0x14000978a`
- `KERNEL32!GetLastError` at `0x140009794`
- `KERNEL32!GetLastError` at `0x14000979e`
- `KERNEL32!GetLastError` at `0x140009695`
- `KERNEL32!GetLastError` at `0x14000974e`
- `KERNEL32!GetLastError` at `0x14000978a`
- `KERNEL32!GetLastError` at `0x140009794`
- `KERNEL32!GetLastError` at `0x14000979e`

## string_xrefs

- `0x14000970c`: `Shlwapi.dll`
- `0x140009653`: `api-ms-win-core-path-l1-1-0.dll`
- `0x140009679`: `PathCchCanonicalize`
- `0x140009732`: `PathCanonicalizeW`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(
        Microsoft::DiagnosticsHub::UnifiedPlatform *this,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 *ThreadLocalStoragePointer; // rax
  unsigned int v5; // ebx
  __int64 v9; // rdi
  HMODULE Library; // rax
  HMODULE v12; // rax

  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = 0;
  v9 = *ThreadLocalStoragePointer;
  if ( dword_140024AF4 > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&dword_140024AF4);
    if ( dword_140024AF4 == -1 )
    {
      qword_140024B04 = 0;
      dword_140024B0C = 0;
      qword_140024AF8 = 0;
      dword_140024B00 = 0;
      Library = LoadLibraryExW(L"api-ms-win-core-path-l1-1-0.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_140024B04 + 4) = (__int64)Library;
      if ( !Library
        || (qword_140024AF8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                        Library,
                                                                                        "PathCchCanonicalize")) == 0 )
      {
        dword_140024B00 = GetLastError();
      }
      Init_thread_footer(&dword_140024AF4);
    }
  }
  if ( !dword_140024B00 && qword_140024AF8 )
    return qword_140024AF8(this, a2, a3, a4);
  if ( dword_140024B10 > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&dword_140024B10);
    if ( dword_140024B10 == -1 )
    {
      qword_140024B24 = 0;
      dword_140024B2C = 0;
      qword_140024B18 = 0;
      dword_140024B20 = 0;
      v12 = LoadLibraryExW(L"Shlwapi.dll", 0, 0);
      *(__int64 *)((char *)&qword_140024B24 + 4) = (__int64)v12;
      if ( !v12
        || (qword_140024B18 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                        v12,
                                                                                        "PathCanonicalizeW")) == 0 )
      {
        dword_140024B20 = GetLastError();
      }
      Init_thread_footer(&dword_140024B10);
    }
  }
  if ( dword_140024B20 || !qword_140024B18 )
    return 2147549183LL;
  if ( !(unsigned int)qword_140024B18(this, a3, a3, a4) )
  {
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0x80070000;
    else
      return GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x1400095e4  mov     [rsp+arg_0], rbx
0x1400095e9  mov     [rsp+arg_8], rbp
0x1400095ee  mov     [rsp+arg_10], rsi
0x1400095f3  push    rdi
0x1400095f4  push    r14
0x1400095f6  push    r15
0x1400095f8  sub     rsp, 20h
0x1400095fc  mov     rax, gs:58h
0x140009605  xor     ebx, ebx
0x140009607  mov     r15d, 4
0x14000960d  mov     rbp, r8
0x140009610  mov     rsi, rdx
0x140009613  mov     r14, rcx
0x140009616  mov     rdi, [rax]
0x140009619  mov     eax, [r15+rdi]
0x14000961d  cmp     cs:dword_140024AF4, eax
0x140009623  jle     loc_1400096AD
0x140009629  lea     rcx, dword_140024AF4
0x140009630  call    _Init_thread_header
0x140009635  cmp     cs:dword_140024AF4, 0FFFFFFFFh
0x14000963c  jnz     short loc_1400096AD
0x14000963e  xor     edx, edx; hFile
0x140009640  mov     cs:qword_140024B04, rbx
0x140009647  mov     r8d, 800h; dwFlags
0x14000964d  mov     cs:dword_140024B0C, ebx
0x140009653  lea     rcx, aApiMsWinCorePa; "api-ms-win-core-path-l1-1-0.dll"
0x14000965a  mov     cs:qword_140024AF8, rbx
0x140009661  mov     cs:dword_140024B00, ebx
0x140009667  call    cs:__imp_LoadLibraryExW
0x14000966d  mov     cs:qword_140024B04+4, rax
0x140009674  test    rax, rax
0x140009677  jz      short loc_140009695
0x140009679  lea     rdx, aPathcchcanonic; "PathCchCanonicalize"
0x140009680  mov     rcx, rax; hModule
0x140009683  call    cs:__imp_GetProcAddress
0x140009689  mov     cs:qword_140024AF8, rax
0x140009690  test    rax, rax
0x140009693  jnz     short loc_1400096A1
0x140009695  call    cs:__imp_GetLastError
0x14000969b  mov     cs:dword_140024B00, eax
0x1400096a1  lea     rcx, dword_140024AF4
0x1400096a8  call    _Init_thread_footer
0x1400096ad  cmp     cs:dword_140024B00, ebx
0x1400096b3  jnz     short loc_1400096D5
0x1400096b5  mov     rax, cs:qword_140024AF8
0x1400096bc  test    rax, rax
0x1400096bf  jz      short loc_1400096D5
0x1400096c1  mov     r8, rbp
0x1400096c4  mov     rdx, rsi
0x1400096c7  mov     rcx, r14
0x1400096ca  call    cs:__guard_dispatch_icall_fptr
0x1400096d0  jmp     loc_1400097B6
0x1400096d5  mov     eax, [r15+rdi]
0x1400096d9  cmp     cs:dword_140024B10, eax
0x1400096df  jle     loc_140009766
0x1400096e5  lea     rcx, dword_140024B10
0x1400096ec  call    _Init_thread_header
0x1400096f1  cmp     cs:dword_140024B10, 0FFFFFFFFh
0x1400096f8  jnz     short loc_140009766
0x1400096fa  xor     r8d, r8d; dwFlags
0x1400096fd  mov     cs:qword_140024B24, rbx
0x140009704  xor     edx, edx; hFile
0x140009706  mov     cs:dword_140024B2C, ebx
0x14000970c  lea     rcx, aShlwapiDll_0; "Shlwapi.dll"
0x140009713  mov     cs:qword_140024B18, rbx
0x14000971a  mov     cs:dword_140024B20, ebx
0x140009720  call    cs:__imp_LoadLibraryExW
0x140009726  mov     cs:qword_140024B24+4, rax
0x14000972d  test    rax, rax
0x140009730  jz      short loc_14000974E
0x140009732  lea     rdx, aPathcanonicali; "PathCanonicalizeW"
0x140009739  mov     rcx, rax; hModule
0x14000973c  call    cs:__imp_GetProcAddress
0x140009742  mov     cs:qword_140024B18, rax
0x140009749  test    rax, rax
0x14000974c  jnz     short loc_14000975A
0x14000974e  call    cs:__imp_GetLastError
0x140009754  mov     cs:dword_140024B20, eax
0x14000975a  lea     rcx, dword_140024B10
0x140009761  call    _Init_thread_footer
0x140009766  cmp     cs:dword_140024B20, ebx
0x14000976c  jnz     short loc_1400097B1
0x14000976e  mov     rax, cs:qword_140024B18
0x140009775  test    rax, rax
0x140009778  jz      short loc_1400097B1
0x14000977a  mov     rdx, rbp
0x14000977d  mov     rcx, r14
0x140009780  call    cs:__guard_dispatch_icall_fptr
0x140009786  test    eax, eax
0x140009788  jnz     short loc_1400097AD
0x14000978a  call    cs:__imp_GetLastError
0x140009790  test    eax, eax
0x140009792  jg      short loc_14000979E
0x140009794  call    cs:__imp_GetLastError
0x14000979a  mov     ebx, eax
0x14000979c  jmp     short loc_1400097AD
0x14000979e  call    cs:__imp_GetLastError
0x1400097a4  movzx   ebx, ax
0x1400097a7  or      ebx, 80070000h
0x1400097ad  mov     eax, ebx
0x1400097af  jmp     short loc_1400097B6
0x1400097b1  mov     eax, 8000FFFFh
0x1400097b6  mov     rbx, [rsp+38h+arg_0]
0x1400097bb  mov     rbp, [rsp+38h+arg_8]
0x1400097c0  mov     rsi, [rsp+38h+arg_10]
0x1400097c5  add     rsp, 20h
0x1400097c9  pop     r15
0x1400097cb  pop     r14
0x1400097cd  pop     rdi
0x1400097ce  retn
```
