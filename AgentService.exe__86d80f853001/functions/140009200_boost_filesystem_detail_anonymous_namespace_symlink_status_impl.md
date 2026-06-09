# boost::filesystem::detail::_anonymous_namespace_::symlink_status_impl

- ea: `0x140009200`
- end: `0x140009398`
- name: `boost::filesystem::detail::_anonymous_namespace_::symlink_status_impl`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x140009070`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x1400089a0`
- `0x140008ba0`
- `0x140008e90`
- `0x140009200`
- `0x14000ac03`
- `0x14000c2b8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140009377`
- `KERNEL32!CloseHandle` at `0x140009377`
- `KERNEL32!GetLastError` at `0x1400092fe`
- `KERNEL32!GetLastError` at `0x140009347`
- `KERNEL32!GetLastError` at `0x1400092fe`
- `KERNEL32!GetLastError` at `0x140009347`
- `KERNEL32!GetFileAttributesW` at `0x14000931a`
- `KERNEL32!GetFileAttributesW` at `0x14000931a`
- `KERNEL32!CreateFileW` at `0x140009290`
- `KERNEL32!CreateFileW` at `0x140009290`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int *__fastcall boost::filesystem::detail::_anonymous_namespace_::symlink_status_impl(
        unsigned int *a1,
        __int64 a2,
        __int64 a3)
{
  const wchar_t *v6; // rbx
  size_t v7; // rax
  const WCHAR *v8; // rcx
  HANDLE FileW; // rbx
  WCHAR *v10; // rcx
  DWORD LastError; // ebp
  const WCHAR *v12; // rcx
  DWORD FileAttributesW; // eax
  char v14; // bl
  unsigned int permissions; // eax
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+58h] [rbp-40h]
  unsigned __int64 v19; // [rsp+60h] [rbp-38h]

  v6 = (const wchar_t *)a2;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v6 = *(const wchar_t **)a2;
  *(_OWORD *)lpFileName = 0;
  v18 = 0;
  v19 = 0;
  v7 = wcslen_0(v6);
  std::wstring::_Construct<1,wchar_t *>(lpFileName, v6, v7);
  v8 = (const WCHAR *)lpFileName;
  if ( v19 > 7 )
    v8 = lpFileName[0];
  FileW = CreateFileW(v8, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( v19 > 7 )
  {
    if ( 2 * v19 + 2 < 0x1000 )
    {
      v10 = (WCHAR *)lpFileName[0];
    }
    else
    {
      v10 = (WCHAR *)*((_QWORD *)lpFileName[0] - 1);
      if ( (unsigned __int64)((char *)lpFileName[0] - (char *)v10 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v10);
  }
  v18 = 0;
  v19 = 7;
  LOWORD(lpFileName[0]) = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    boost::filesystem::detail::_anonymous_namespace_::status_by_handle(a1, FileW, a2, a3);
    CloseHandle(FileW);
    return a1;
  }
  LastError = GetLastError();
  if ( LastError != 5 )
    goto LABEL_20;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v12 = (const WCHAR *)a2;
  else
    v12 = *(const WCHAR **)a2;
  FileAttributesW = GetFileAttributesW(v12);
  v14 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    goto LABEL_20;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
LABEL_20:
    boost::filesystem::detail::_anonymous_namespace_::process_status_failure(a1, LastError, a2, a3);
    return a1;
  }
  permissions = boost::filesystem::detail::make_permissions(a2, FileAttributesW);
  *a1 = (v14 & 0x10 | 0x20u) >> 4;
  a1[1] = permissions;
  return a1;
}

```

## disassembly

```asm
0x140009200  push    rbx
0x140009202  push    rbp
0x140009203  push    rsi
0x140009204  push    rdi
0x140009205  push    r14
0x140009207  sub     rsp, 70h
0x14000920b  mov     rax, cs:__security_cookie
0x140009212  xor     rax, rsp
0x140009215  mov     [rsp+98h+var_30], rax
0x14000921a  mov     r14, r8
0x14000921d  mov     rdi, rdx
0x140009220  mov     rsi, rcx
0x140009223  mov     rbx, rdx
0x140009226  cmp     qword ptr [rdx+18h], 7
0x14000922b  jbe     short loc_140009230
0x14000922d  mov     rbx, [rdx]
0x140009230  xorps   xmm0, xmm0
0x140009233  movups  xmmword ptr [rsp+98h+lpFileName], xmm0
0x140009238  xor     ebp, ebp
0x14000923a  mov     [rsp+98h+var_40], rbp
0x14000923f  mov     [rsp+98h+var_38], rbp
0x140009244  mov     rcx, rbx; String
0x140009247  call    wcslen_0
0x14000924c  mov     r8, rax
0x14000924f  mov     rdx, rbx
0x140009252  lea     rcx, [rsp+98h+lpFileName]
0x140009257  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14000925c  lea     rcx, [rsp+98h+lpFileName]
0x140009261  cmp     [rsp+98h+var_38], 7
0x140009267  cmova   rcx, [rsp+98h+lpFileName]; lpFileName
0x14000926d  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x140009272  mov     [rsp+98h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x14000927a  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x140009282  xor     r9d, r9d; lpSecurityAttributes
0x140009285  mov     edx, 80h; dwDesiredAccess
0x14000928a  mov     r8d, 7; dwShareMode
0x140009290  call    cs:__imp_CreateFileW
0x140009296  mov     rbx, rax
0x140009299  mov     [rsp+98h+var_58], rax
0x14000929e  mov     rdx, [rsp+98h+var_38]
0x1400092a3  cmp     rdx, 7
0x1400092a7  jbe     short loc_1400092E5
0x1400092a9  mov     rax, [rsp+98h+lpFileName]
0x1400092ae  lea     rdx, ds:2[rdx*2]
0x1400092b6  cmp     rdx, 1000h
0x1400092bd  jb      short loc_1400092DD
0x1400092bf  mov     rcx, [rax-8]
0x1400092c3  sub     rax, rcx
0x1400092c6  sub     rax, 8
0x1400092ca  cmp     rax, 1Fh
0x1400092ce  ja      short loc_1400092D6
0x1400092d0  add     rdx, 27h ; '''
0x1400092d4  jmp     short loc_1400092E0
0x1400092d6  mov     ecx, 5
0x1400092db  int     29h; Win8: RtlFailFast(ecx)
0x1400092dd  mov     rcx, rax; Block
0x1400092e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400092e5  mov     [rsp+98h+var_40], rbp
0x1400092ea  mov     [rsp+98h+var_38], 7
0x1400092f3  mov     word ptr [rsp+98h+lpFileName], bp
0x1400092f8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400092fc  jnz     short loc_140009362
0x1400092fe  call    cs:__imp_GetLastError
0x140009304  mov     ebp, eax
0x140009306  cmp     eax, 5
0x140009309  jnz     short loc_14000934F
0x14000930b  cmp     qword ptr [rdi+18h], 7
0x140009310  jbe     short loc_140009317
0x140009312  mov     rcx, [rdi]
0x140009315  jmp     short loc_14000931A
0x140009317  mov     rcx, rdi; lpFileName
0x14000931a  call    cs:__imp_GetFileAttributesW
0x140009320  mov     ebx, eax
0x140009322  cmp     eax, 0FFFFFFFFh
0x140009325  jz      short loc_140009347
0x140009327  bt      eax, 0Ah
0x14000932b  jb      short loc_14000934F
0x14000932d  mov     edx, eax
0x14000932f  mov     rcx, rdi
0x140009332  call    ?make_permissions@detail@filesystem@boost@@YA?AW4perms@23@AEBVpath@23@K@Z; boost::filesystem::detail::make_permissions(boost::filesystem::path const &,ulong)
0x140009337  and     ebx, 10h
0x14000933a  or      ebx, 20h
0x14000933d  shr     ebx, 4
0x140009340  mov     [rsi], ebx
0x140009342  mov     [rsi+4], eax
0x140009345  jmp     short loc_14000937D
0x140009347  call    cs:__imp_GetLastError
0x14000934d  mov     ebp, eax
0x14000934f  mov     r9, r14
0x140009352  mov     r8, rdi
0x140009355  mov     edx, ebp
0x140009357  mov     rcx, rsi
0x14000935a  call    boost__filesystem__detail___anonymous_namespace___process_status_failure
0x14000935f  nop
0x140009360  jmp     short loc_14000937D
0x140009362  mov     r9, r14
0x140009365  mov     r8, rdi
0x140009368  mov     rdx, rbx
0x14000936b  mov     rcx, rsi
0x14000936e  call    boost__filesystem__detail___anonymous_namespace___status_by_handle
0x140009373  nop
0x140009374  mov     rcx, rbx; hObject
0x140009377  call    cs:__imp_CloseHandle
0x14000937d  mov     rax, rsi
0x140009380  mov     rcx, [rsp+98h+var_30]
0x140009385  xor     rcx, rsp; StackCookie
0x140009388  call    __security_check_cookie
0x14000938d  add     rsp, 70h
0x140009391  pop     r14
0x140009393  pop     rdi
0x140009394  pop     rsi
0x140009395  pop     rbp
0x140009396  pop     rbx
0x140009397  retn
```
