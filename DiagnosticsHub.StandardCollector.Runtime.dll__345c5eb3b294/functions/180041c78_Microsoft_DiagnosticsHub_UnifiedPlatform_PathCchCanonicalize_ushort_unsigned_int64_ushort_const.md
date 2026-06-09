# Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)

- ea: `0x180041c78`
- end: `0x180041e6b`
- name: `?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z`
- size: `499`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::UnifiedPlatform *__hidden this, unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180006b54`
- `0x180043bd8`
- `0x180043ef8`

## callees

- `0x180041c78`
- `0x180049bac`
- `0x180049c18`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180041d03`
- `KERNEL32!LoadLibraryExW` at `0x180041dbc`
- `KERNEL32!LoadLibraryExW` at `0x180041d03`
- `KERNEL32!LoadLibraryExW` at `0x180041dbc`
- `KERNEL32!GetLastError` at `0x180041d31`
- `KERNEL32!GetLastError` at `0x180041dea`
- `KERNEL32!GetLastError` at `0x180041e26`
- `KERNEL32!GetLastError` at `0x180041e30`
- `KERNEL32!GetLastError` at `0x180041e3a`
- `KERNEL32!GetLastError` at `0x180041d31`
- `KERNEL32!GetLastError` at `0x180041dea`
- `KERNEL32!GetLastError` at `0x180041e26`
- `KERNEL32!GetLastError` at `0x180041e30`
- `KERNEL32!GetLastError` at `0x180041e3a`
- `KERNEL32!GetProcAddress` at `0x180041d1f`
- `KERNEL32!GetProcAddress` at `0x180041dd8`
- `KERNEL32!GetProcAddress` at `0x180041d1f`
- `KERNEL32!GetProcAddress` at `0x180041dd8`

## string_xrefs

- `0x180041da8`: `Shlwapi.dll`
- `0x180041cef`: `api-ms-win-core-path-l1-1-0.dll`
- `0x180041d15`: `PathCchCanonicalize`
- `0x180041dce`: `PathCanonicalizeW`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(
        Microsoft::DiagnosticsHub::UnifiedPlatform *this,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rdi
  HMODULE Library; // rax
  HMODULE v11; // rax

  v4 = 0;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180077A90 > *(_DWORD *)(v8 + 4) )
  {
    Init_thread_header(&dword_180077A90);
    if ( dword_180077A90 == -1 )
    {
      qword_180077AA4 = 0;
      dword_180077AAC = 0;
      qword_180077A98 = 0;
      dword_180077AA0 = 0;
      Library = LoadLibraryExW(L"api-ms-win-core-path-l1-1-0.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_180077AA4 + 4) = (__int64)Library;
      if ( !Library
        || (qword_180077A98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                Library,
                                                                                "PathCchCanonicalize")) == 0 )
      {
        dword_180077AA0 = GetLastError();
      }
      Init_thread_footer(&dword_180077A90);
    }
  }
  if ( !dword_180077AA0 && qword_180077A98 )
    return qword_180077A98(this, a2, a3);
  if ( dword_180077AB0 > *(_DWORD *)(v8 + 4) )
  {
    Init_thread_header(&dword_180077AB0);
    if ( dword_180077AB0 == -1 )
    {
      qword_180077AC4 = 0;
      dword_180077ACC = 0;
      qword_180077AB8 = 0;
      dword_180077AC0 = 0;
      v11 = LoadLibraryExW(L"Shlwapi.dll", 0, 0);
      *(__int64 *)((char *)&qword_180077AC4 + 4) = (__int64)v11;
      if ( !v11
        || (qword_180077AB8 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(v11, "PathCanonicalizeW")) == 0 )
      {
        dword_180077AC0 = GetLastError();
      }
      Init_thread_footer(&dword_180077AB0);
    }
  }
  if ( dword_180077AC0 || !qword_180077AB8 )
    return 2147549183LL;
  if ( !(unsigned int)qword_180077AB8(this, a3) )
  {
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0x80070000;
    else
      return GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x180041c78  mov     [rsp+arg_0], rbx
0x180041c7d  mov     [rsp+arg_8], rbp
0x180041c82  mov     [rsp+arg_10], rsi
0x180041c87  push    rdi
0x180041c88  push    r14
0x180041c8a  push    r15
0x180041c8c  sub     rsp, 20h
0x180041c90  mov     rax, gs:58h
0x180041c99  xor     ebx, ebx
0x180041c9b  mov     r9d, cs:_tls_index
0x180041ca2  mov     rsi, r8
0x180041ca5  mov     r15d, 4
0x180041cab  mov     r14, rdx
0x180041cae  mov     rbp, rcx
0x180041cb1  mov     rdi, [rax+r9*8]
0x180041cb5  mov     eax, [rdi+r15]
0x180041cb9  cmp     cs:dword_180077A90, eax
0x180041cbf  jle     loc_180041D49
0x180041cc5  lea     rcx, dword_180077A90
0x180041ccc  call    _Init_thread_header
0x180041cd1  cmp     cs:dword_180077A90, 0FFFFFFFFh
0x180041cd8  jnz     short loc_180041D49
0x180041cda  xor     edx, edx; hFile
0x180041cdc  mov     cs:qword_180077AA4, rbx
0x180041ce3  mov     r8d, 800h; dwFlags
0x180041ce9  mov     cs:dword_180077AAC, ebx
0x180041cef  lea     rcx, aApiMsWinCorePa; "api-ms-win-core-path-l1-1-0.dll"
0x180041cf6  mov     cs:qword_180077A98, rbx
0x180041cfd  mov     cs:dword_180077AA0, ebx
0x180041d03  call    cs:__imp_LoadLibraryExW
0x180041d09  mov     cs:qword_180077AA4+4, rax
0x180041d10  test    rax, rax
0x180041d13  jz      short loc_180041D31
0x180041d15  lea     rdx, aPathcchcanonic; "PathCchCanonicalize"
0x180041d1c  mov     rcx, rax; hModule
0x180041d1f  call    cs:__imp_GetProcAddress
0x180041d25  mov     cs:qword_180077A98, rax
0x180041d2c  test    rax, rax
0x180041d2f  jnz     short loc_180041D3D
0x180041d31  call    cs:__imp_GetLastError
0x180041d37  mov     cs:dword_180077AA0, eax
0x180041d3d  lea     rcx, dword_180077A90
0x180041d44  call    _Init_thread_footer
0x180041d49  cmp     cs:dword_180077AA0, ebx
0x180041d4f  jnz     short loc_180041D71
0x180041d51  mov     rax, cs:qword_180077A98
0x180041d58  test    rax, rax
0x180041d5b  jz      short loc_180041D71
0x180041d5d  mov     r8, rsi
0x180041d60  mov     rdx, r14
0x180041d63  mov     rcx, rbp
0x180041d66  call    cs:__guard_dispatch_icall_fptr
0x180041d6c  jmp     loc_180041E52
0x180041d71  mov     eax, [rdi+r15]
0x180041d75  cmp     cs:dword_180077AB0, eax
0x180041d7b  jle     loc_180041E02
0x180041d81  lea     rcx, dword_180077AB0
0x180041d88  call    _Init_thread_header
0x180041d8d  cmp     cs:dword_180077AB0, 0FFFFFFFFh
0x180041d94  jnz     short loc_180041E02
0x180041d96  xor     r8d, r8d; dwFlags
0x180041d99  mov     cs:qword_180077AC4, rbx
0x180041da0  xor     edx, edx; hFile
0x180041da2  mov     cs:dword_180077ACC, ebx
0x180041da8  lea     rcx, aShlwapiDll_0; "Shlwapi.dll"
0x180041daf  mov     cs:qword_180077AB8, rbx
0x180041db6  mov     cs:dword_180077AC0, ebx
0x180041dbc  call    cs:__imp_LoadLibraryExW
0x180041dc2  mov     cs:qword_180077AC4+4, rax
0x180041dc9  test    rax, rax
0x180041dcc  jz      short loc_180041DEA
0x180041dce  lea     rdx, aPathcanonicali; "PathCanonicalizeW"
0x180041dd5  mov     rcx, rax; hModule
0x180041dd8  call    cs:__imp_GetProcAddress
0x180041dde  mov     cs:qword_180077AB8, rax
0x180041de5  test    rax, rax
0x180041de8  jnz     short loc_180041DF6
0x180041dea  call    cs:__imp_GetLastError
0x180041df0  mov     cs:dword_180077AC0, eax
0x180041df6  lea     rcx, dword_180077AB0
0x180041dfd  call    _Init_thread_footer
0x180041e02  cmp     cs:dword_180077AC0, ebx
0x180041e08  jnz     short loc_180041E4D
0x180041e0a  mov     rax, cs:qword_180077AB8
0x180041e11  test    rax, rax
0x180041e14  jz      short loc_180041E4D
0x180041e16  mov     rdx, rsi
0x180041e19  mov     rcx, rbp
0x180041e1c  call    cs:__guard_dispatch_icall_fptr
0x180041e22  test    eax, eax
0x180041e24  jnz     short loc_180041E49
0x180041e26  call    cs:__imp_GetLastError
0x180041e2c  test    eax, eax
0x180041e2e  jg      short loc_180041E3A
0x180041e30  call    cs:__imp_GetLastError
0x180041e36  mov     ebx, eax
0x180041e38  jmp     short loc_180041E49
0x180041e3a  call    cs:__imp_GetLastError
0x180041e40  movzx   ebx, ax
0x180041e43  or      ebx, 80070000h
0x180041e49  mov     eax, ebx
0x180041e4b  jmp     short loc_180041E52
0x180041e4d  mov     eax, 8000FFFFh
0x180041e52  mov     rbx, [rsp+38h+arg_0]
0x180041e57  mov     rbp, [rsp+38h+arg_8]
0x180041e5c  mov     rsi, [rsp+38h+arg_10]
0x180041e61  add     rsp, 20h
0x180041e65  pop     r15
0x180041e67  pop     r14
0x180041e69  pop     rdi
0x180041e6a  retn
```
