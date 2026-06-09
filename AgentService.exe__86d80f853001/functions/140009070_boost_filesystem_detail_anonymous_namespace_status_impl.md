# boost::filesystem::detail::_anonymous_namespace_::status_impl

- ea: `0x140009070`
- end: `0x1400091f4`
- name: `boost::filesystem::detail::_anonymous_namespace_::status_impl`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x1400082b0`
- `0x140008e60`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140008ba0`
- `0x140008e90`
- `0x140009070`
- `0x140009200`
- `0x14000ac03`
- `0x14000c2b8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400091c4`
- `KERNEL32!CloseHandle` at `0x1400091c4`
- `KERNEL32!GetLastError` at `0x140009192`
- `KERNEL32!GetLastError` at `0x140009192`
- `KERNEL32!CreateFileW` at `0x140009123`
- `KERNEL32!CreateFileW` at `0x140009123`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall boost::filesystem::detail::_anonymous_namespace_::status_impl(
        _QWORD *a1,
        const wchar_t *a2,
        __int64 a3)
{
  HANDLE v6; // rbx
  const wchar_t *v7; // rbx
  size_t v8; // rax
  const WCHAR *v9; // rcx
  HANDLE FileW; // rdi
  WCHAR *v11; // rcx
  DWORD LastError; // eax
  HANDLE v14; // [rsp+40h] [rbp-68h] BYREF
  char v15[8]; // [rsp+48h] [rbp-60h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v17; // [rsp+60h] [rbp-48h]
  unsigned __int64 v18; // [rsp+68h] [rbp-40h]

  boost::filesystem::detail::_anonymous_namespace_::symlink_status_impl((unsigned int *)&v14, (__int64)a2, a3);
  v6 = v14;
  if ( (_DWORD)v14 != 4 )
    goto LABEL_16;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v7 = a2;
  else
    v7 = *(const wchar_t **)a2;
  *(_OWORD *)lpFileName = 0;
  v17 = 0;
  v18 = 0;
  v8 = wcslen_0(v7);
  std::wstring::_Construct<1,wchar_t *>(lpFileName, v7, v8);
  v9 = (const WCHAR *)lpFileName;
  if ( v18 > 7 )
    v9 = lpFileName[0];
  FileW = CreateFileW(v9, 0x80u, 7u, 0, 3u, 0x2000000u, 0);
  v14 = FileW;
  if ( v18 > 7 )
  {
    if ( 2 * v18 + 2 < 0x1000 )
    {
      v11 = (WCHAR *)lpFileName[0];
    }
    else
    {
      v11 = (WCHAR *)*((_QWORD *)lpFileName[0] - 1);
      if ( (unsigned __int64)((char *)lpFileName[0] - (char *)v11 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v11);
  }
  v17 = 0;
  v18 = 7;
  LOWORD(lpFileName[0]) = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    v6 = *(HANDLE *)boost::filesystem::detail::_anonymous_namespace_::status_by_handle(v15, FileW, a2, a3);
    CloseHandle(FileW);
LABEL_16:
    *a1 = v6;
    return a1;
  }
  LastError = GetLastError();
  boost::filesystem::detail::_anonymous_namespace_::process_status_failure(a1, LastError, a2, a3);
  return a1;
}

```

## disassembly

```asm
0x140009070  mov     [rsp+arg_18], rbx
0x140009075  push    rbp
0x140009076  push    rsi
0x140009077  push    rdi
0x140009078  push    r14
0x14000907a  push    r15
0x14000907c  sub     rsp, 80h
0x140009083  mov     rax, cs:__security_cookie
0x14000908a  xor     rax, rsp
0x14000908d  mov     [rsp+0A8h+var_38], rax
0x140009092  mov     rbp, r8
0x140009095  mov     rsi, rdx
0x140009098  mov     r14, rcx
0x14000909b  lea     rcx, [rsp+0A8h+var_68]
0x1400090a0  call    boost__filesystem__detail___anonymous_namespace___symlink_status_impl
0x1400090a5  mov     rbx, [rsp+0A8h+var_68]
0x1400090aa  cmp     ebx, 4
0x1400090ad  jnz     loc_1400091CA
0x1400090b3  cmp     qword ptr [rsi+18h], 7
0x1400090b8  jbe     short loc_1400090BF
0x1400090ba  mov     rbx, [rsi]
0x1400090bd  jmp     short loc_1400090C2
0x1400090bf  mov     rbx, rsi
0x1400090c2  xorps   xmm0, xmm0
0x1400090c5  movups  xmmword ptr [rsp+0A8h+lpFileName], xmm0
0x1400090ca  xor     r15d, r15d
0x1400090cd  mov     [rsp+0A8h+var_48], r15
0x1400090d2  mov     [rsp+0A8h+var_40], r15
0x1400090d7  mov     rcx, rbx; String
0x1400090da  call    wcslen_0
0x1400090df  mov     r8, rax
0x1400090e2  mov     rdx, rbx
0x1400090e5  lea     rcx, [rsp+0A8h+lpFileName]
0x1400090ea  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400090ef  lea     rcx, [rsp+0A8h+lpFileName]
0x1400090f4  cmp     [rsp+0A8h+var_40], 7
0x1400090fa  cmova   rcx, [rsp+0A8h+lpFileName]; lpFileName
0x140009100  mov     [rsp+0A8h+hTemplateFile], r15; hTemplateFile
0x140009105  mov     [rsp+0A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14000910d  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x140009115  xor     r9d, r9d; lpSecurityAttributes
0x140009118  mov     edx, 80h; dwDesiredAccess
0x14000911d  mov     r8d, 7; dwShareMode
0x140009123  call    cs:__imp_CreateFileW
0x140009129  mov     rdi, rax
0x14000912c  mov     [rsp+0A8h+var_68], rax
0x140009131  mov     rdx, [rsp+0A8h+var_40]
0x140009136  cmp     rdx, 7
0x14000913a  jbe     short loc_140009178
0x14000913c  mov     rax, [rsp+0A8h+lpFileName]
0x140009141  lea     rdx, ds:2[rdx*2]
0x140009149  cmp     rdx, 1000h
0x140009150  jb      short loc_140009170
0x140009152  mov     rcx, [rax-8]
0x140009156  sub     rax, rcx
0x140009159  sub     rax, 8
0x14000915d  cmp     rax, 1Fh
0x140009161  ja      short loc_140009169
0x140009163  add     rdx, 27h ; '''
0x140009167  jmp     short loc_140009173
0x140009169  mov     ecx, 5
0x14000916e  int     29h; Win8: RtlFailFast(ecx)
0x140009170  mov     rcx, rax; Block
0x140009173  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009178  mov     [rsp+0A8h+var_48], r15
0x14000917d  mov     [rsp+0A8h+var_40], 7
0x140009186  mov     word ptr [rsp+0A8h+lpFileName], r15w
0x14000918c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140009190  jnz     short loc_1400091AB
0x140009192  call    cs:__imp_GetLastError
0x140009198  mov     edx, eax
0x14000919a  mov     r9, rbp
0x14000919d  mov     r8, rsi
0x1400091a0  mov     rcx, r14
0x1400091a3  call    boost__filesystem__detail___anonymous_namespace___process_status_failure
0x1400091a8  nop
0x1400091a9  jmp     short loc_1400091CD
0x1400091ab  mov     r9, rbp
0x1400091ae  mov     r8, rsi
0x1400091b1  mov     rdx, rdi
0x1400091b4  lea     rcx, [rsp+0A8h+var_60]
0x1400091b9  call    boost__filesystem__detail___anonymous_namespace___status_by_handle
0x1400091be  mov     rbx, [rax]
0x1400091c1  mov     rcx, rdi; hObject
0x1400091c4  call    cs:__imp_CloseHandle
0x1400091ca  mov     [r14], rbx
0x1400091cd  mov     rax, r14
0x1400091d0  mov     rcx, [rsp+0A8h+var_38]
0x1400091d5  xor     rcx, rsp; StackCookie
0x1400091d8  call    __security_check_cookie
0x1400091dd  mov     rbx, [rsp+0A8h+arg_18]
0x1400091e5  add     rsp, 80h
0x1400091ec  pop     r15
0x1400091ee  pop     r14
0x1400091f0  pop     rdi
0x1400091f1  pop     rsi
0x1400091f2  pop     rbp
0x1400091f3  retn
```
