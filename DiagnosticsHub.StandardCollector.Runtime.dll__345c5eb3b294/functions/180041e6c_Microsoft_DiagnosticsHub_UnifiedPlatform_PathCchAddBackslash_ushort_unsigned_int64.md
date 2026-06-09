# Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(ushort *,unsigned __int64)

- ea: `0x180041e6c`
- end: `0x180041faa`
- name: `?PathCchAddBackslash@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_K@Z`
- size: `318`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::UnifiedPlatform *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180032470`
- `0x180042e38`

## callees

- `0x180041e6c`
- `0x180049bac`
- `0x180049c18`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180041ef1`
- `KERNEL32!LoadLibraryExW` at `0x180041ef1`
- `KERNEL32!GetLastError` at `0x180041f1f`
- `KERNEL32!GetLastError` at `0x180041f1f`
- `KERNEL32!GetProcAddress` at `0x180041f0d`
- `KERNEL32!GetProcAddress` at `0x180041f0d`

## string_xrefs

- `0x180041edd`: `api-ms-win-core-path-l1-1-0.dll`
- `0x180041f03`: `PathCchAddBackslash`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(
        Microsoft::DiagnosticsHub::UnifiedPlatform *this,
        unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  HMODULE Library; // rax

  v3 = -1;
  if ( dword_180077AD0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180077AD0);
    if ( dword_180077AD0 == -1 )
    {
      qword_180077AE4 = 0;
      dword_180077AEC = 0;
      qword_180077AD8 = 0;
      dword_180077AE0 = 0;
      Library = LoadLibraryExW(L"api-ms-win-core-path-l1-1-0.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_180077AE4 + 4) = (__int64)Library;
      if ( !Library
        || (qword_180077AD8 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(Library, "PathCchAddBackslash")) == 0 )
      {
        dword_180077AE0 = GetLastError();
      }
      Init_thread_footer(&dword_180077AD0);
    }
  }
  if ( !dword_180077AE0 && qword_180077AD8 )
    return qword_180077AD8(this, a2);
  if ( this )
  {
    do
      ++v3;
    while ( *((_WORD *)this + v3) );
  }
  else
  {
    v3 = 0;
  }
  if ( v3 >= (unsigned __int64)a2 )
    return 2147942522LL;
  if ( !v3 || *((_WORD *)this + v3 - 1) == 92 )
    return 1;
  *(_DWORD *)((char *)this + 2 * v3) = 92;
  return 0;
}

```

## disassembly

```asm
0x180041e6c  mov     [rsp+arg_0], rbx
0x180041e71  mov     [rsp+arg_8], rbp
0x180041e76  mov     [rsp+arg_10], rsi
0x180041e7b  push    rdi
0x180041e7c  sub     rsp, 20h
0x180041e80  mov     r8d, cs:_tls_index
0x180041e87  mov     rdi, rcx
0x180041e8a  mov     rax, gs:58h
0x180041e93  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180041e97  mov     ecx, 4
0x180041e9c  xor     ebp, ebp
0x180041e9e  mov     rsi, rdx
0x180041ea1  mov     rax, [rax+r8*8]
0x180041ea5  mov     eax, [rcx+rax]
0x180041ea8  cmp     cs:dword_180077AD0, eax
0x180041eae  jle     loc_180041F37
0x180041eb4  lea     rcx, dword_180077AD0
0x180041ebb  call    _Init_thread_header
0x180041ec0  cmp     cs:dword_180077AD0, ebx
0x180041ec6  jnz     short loc_180041F37
0x180041ec8  xor     edx, edx; hFile
0x180041eca  mov     cs:qword_180077AE4, rbp
0x180041ed1  mov     r8d, 800h; dwFlags
0x180041ed7  mov     cs:dword_180077AEC, ebp
0x180041edd  lea     rcx, aApiMsWinCorePa; "api-ms-win-core-path-l1-1-0.dll"
0x180041ee4  mov     cs:qword_180077AD8, rbp
0x180041eeb  mov     cs:dword_180077AE0, ebp
0x180041ef1  call    cs:__imp_LoadLibraryExW
0x180041ef7  mov     cs:qword_180077AE4+4, rax
0x180041efe  test    rax, rax
0x180041f01  jz      short loc_180041F1F
0x180041f03  lea     rdx, aPathcchaddback; "PathCchAddBackslash"
0x180041f0a  mov     rcx, rax; hModule
0x180041f0d  call    cs:__imp_GetProcAddress
0x180041f13  mov     cs:qword_180077AD8, rax
0x180041f1a  test    rax, rax
0x180041f1d  jnz     short loc_180041F2B
0x180041f1f  call    cs:__imp_GetLastError
0x180041f25  mov     cs:dword_180077AE0, eax
0x180041f2b  lea     rcx, dword_180077AD0
0x180041f32  call    _Init_thread_footer
0x180041f37  cmp     cs:dword_180077AE0, ebp
0x180041f3d  jnz     short loc_180041F59
0x180041f3f  mov     rax, cs:qword_180077AD8
0x180041f46  test    rax, rax
0x180041f49  jz      short loc_180041F59
0x180041f4b  mov     rdx, rsi
0x180041f4e  mov     rcx, rdi
0x180041f51  call    cs:__guard_dispatch_icall_fptr
0x180041f57  jmp     short loc_180041F95
0x180041f59  test    rdi, rdi
0x180041f5c  jz      short loc_180041F69
0x180041f5e  inc     rbx
0x180041f61  cmp     [rdi+rbx*2], bp
0x180041f65  jnz     short loc_180041F5E
0x180041f67  jmp     short loc_180041F6C
0x180041f69  mov     rbx, rbp
0x180041f6c  cmp     rbx, rsi
0x180041f6f  jb      short loc_180041F78
0x180041f71  mov     eax, 8007007Ah
0x180041f76  jmp     short loc_180041F95
0x180041f78  test    rbx, rbx
0x180041f7b  jz      short loc_180041F90
0x180041f7d  mov     eax, 5Ch ; '\'
0x180041f82  cmp     [rdi+rbx*2-2], ax
0x180041f87  jz      short loc_180041F90
0x180041f89  mov     [rdi+rbx*2], eax
0x180041f8c  xor     eax, eax
0x180041f8e  jmp     short loc_180041F95
0x180041f90  mov     eax, 1
0x180041f95  mov     rbx, [rsp+28h+arg_0]
0x180041f9a  mov     rbp, [rsp+28h+arg_8]
0x180041f9f  mov     rsi, [rsp+28h+arg_10]
0x180041fa4  add     rsp, 20h
0x180041fa8  pop     rdi
0x180041fa9  retn
```
