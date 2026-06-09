# Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(ushort *,unsigned __int64)

- ea: `0x1400097d0`
- end: `0x140009906`
- name: `?PathCchAddBackslash@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_K@Z`
- size: `310`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::UnifiedPlatform *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000f510`

## callees

- `0x1400097d0`
- `0x1400138ac`
- `0x140013918`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009869`
- `KERNEL32!GetProcAddress` at `0x140009869`
- `KERNEL32!LoadLibraryExW` at `0x14000984d`
- `KERNEL32!LoadLibraryExW` at `0x14000984d`
- `KERNEL32!GetLastError` at `0x14000987b`
- `KERNEL32!GetLastError` at `0x14000987b`

## string_xrefs

- `0x140009839`: `api-ms-win-core-path-l1-1-0.dll`
- `0x14000985f`: `PathCchAddBackslash`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(
        Microsoft::DiagnosticsHub::UnifiedPlatform *this,
        unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  HMODULE Library; // rax

  v3 = -1;
  if ( dword_140024B30 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_140024B30);
    if ( dword_140024B30 == -1 )
    {
      qword_140024B44 = 0;
      dword_140024B4C = 0;
      qword_140024B38 = 0;
      dword_140024B40 = 0;
      Library = LoadLibraryExW(L"api-ms-win-core-path-l1-1-0.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_140024B44 + 4) = (__int64)Library;
      if ( !Library
        || (qword_140024B38 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(Library, "PathCchAddBackslash")) == 0 )
      {
        dword_140024B40 = GetLastError();
      }
      Init_thread_footer(&dword_140024B30);
    }
  }
  if ( !dword_140024B40 && qword_140024B38 )
    return qword_140024B38(this, a2);
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
0x1400097d0  mov     [rsp+arg_0], rbx
0x1400097d5  mov     [rsp+arg_8], rbp
0x1400097da  mov     [rsp+arg_10], rsi
0x1400097df  push    rdi
0x1400097e0  sub     rsp, 20h
0x1400097e4  mov     rax, gs:58h
0x1400097ed  mov     rdi, rcx
0x1400097f0  mov     ecx, 4
0x1400097f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400097f9  xor     ebp, ebp
0x1400097fb  mov     rsi, rdx
0x1400097fe  mov     rax, [rax]
0x140009801  mov     eax, [rcx+rax]
0x140009804  cmp     cs:dword_140024B30, eax
0x14000980a  jle     loc_140009893
0x140009810  lea     rcx, dword_140024B30
0x140009817  call    _Init_thread_header
0x14000981c  cmp     cs:dword_140024B30, ebx
0x140009822  jnz     short loc_140009893
0x140009824  xor     edx, edx; hFile
0x140009826  mov     cs:qword_140024B44, rbp
0x14000982d  mov     r8d, 800h; dwFlags
0x140009833  mov     cs:dword_140024B4C, ebp
0x140009839  lea     rcx, aApiMsWinCorePa; "api-ms-win-core-path-l1-1-0.dll"
0x140009840  mov     cs:qword_140024B38, rbp
0x140009847  mov     cs:dword_140024B40, ebp
0x14000984d  call    cs:__imp_LoadLibraryExW
0x140009853  mov     cs:qword_140024B44+4, rax
0x14000985a  test    rax, rax
0x14000985d  jz      short loc_14000987B
0x14000985f  lea     rdx, aPathcchaddback; "PathCchAddBackslash"
0x140009866  mov     rcx, rax; hModule
0x140009869  call    cs:__imp_GetProcAddress
0x14000986f  mov     cs:qword_140024B38, rax
0x140009876  test    rax, rax
0x140009879  jnz     short loc_140009887
0x14000987b  call    cs:__imp_GetLastError
0x140009881  mov     cs:dword_140024B40, eax
0x140009887  lea     rcx, dword_140024B30
0x14000988e  call    _Init_thread_footer
0x140009893  cmp     cs:dword_140024B40, ebp
0x140009899  jnz     short loc_1400098B5
0x14000989b  mov     rax, cs:qword_140024B38
0x1400098a2  test    rax, rax
0x1400098a5  jz      short loc_1400098B5
0x1400098a7  mov     rdx, rsi
0x1400098aa  mov     rcx, rdi
0x1400098ad  call    cs:__guard_dispatch_icall_fptr
0x1400098b3  jmp     short loc_1400098F1
0x1400098b5  test    rdi, rdi
0x1400098b8  jz      short loc_1400098C5
0x1400098ba  inc     rbx
0x1400098bd  cmp     [rdi+rbx*2], bp
0x1400098c1  jnz     short loc_1400098BA
0x1400098c3  jmp     short loc_1400098C8
0x1400098c5  mov     rbx, rbp
0x1400098c8  cmp     rbx, rsi
0x1400098cb  jb      short loc_1400098D4
0x1400098cd  mov     eax, 8007007Ah
0x1400098d2  jmp     short loc_1400098F1
0x1400098d4  test    rbx, rbx
0x1400098d7  jz      short loc_1400098EC
0x1400098d9  mov     eax, 5Ch ; '\'
0x1400098de  cmp     [rdi+rbx*2-2], ax
0x1400098e3  jz      short loc_1400098EC
0x1400098e5  mov     [rdi+rbx*2], eax
0x1400098e8  xor     eax, eax
0x1400098ea  jmp     short loc_1400098F1
0x1400098ec  mov     eax, 1
0x1400098f1  mov     rbx, [rsp+28h+arg_0]
0x1400098f6  mov     rbp, [rsp+28h+arg_8]
0x1400098fb  mov     rsi, [rsp+28h+arg_10]
0x140009900  add     rsp, 20h
0x140009904  pop     rdi
0x140009905  retn
```
