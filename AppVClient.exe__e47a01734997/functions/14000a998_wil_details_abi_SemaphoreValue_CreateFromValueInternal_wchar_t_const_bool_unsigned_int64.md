# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x14000a998`
- end: `0x14000aba5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140009d54`
- `0x14005f364`

## callees

- `0x140004280`
- `0x14000a998`
- `0x14000ca7c`
- `0x140011564`
- `0x140013260`
- `0x140013c48`
- `0x140013c58`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000aaab`
- `KERNEL32!CloseHandle` at `0x14000ab35`
- `KERNEL32!CloseHandle` at `0x14000aaab`
- `KERNEL32!CloseHandle` at `0x14000ab35`
- `KERNEL32!GetLastError` at `0x14000aa91`
- `KERNEL32!GetLastError` at `0x14000aa9f`
- `KERNEL32!GetLastError` at `0x14000ab1b`
- `KERNEL32!GetLastError` at `0x14000ab2a`
- `KERNEL32!GetLastError` at `0x14000aa91`
- `KERNEL32!GetLastError` at `0x14000aa9f`
- `KERNEL32!GetLastError` at `0x14000ab1b`
- `KERNEL32!GetLastError` at `0x14000ab2a`
- `KERNEL32!SetLastError` at `0x14000aabc`
- `KERNEL32!SetLastError` at `0x14000ab41`
- `KERNEL32!SetLastError` at `0x14000aabc`
- `KERNEL32!SetLastError` at `0x14000ab41`
- `KERNEL32!CreateSemaphoreExW` at `0x14000aa5c`
- `KERNEL32!CreateSemaphoreExW` at `0x14000aaf8`
- `KERNEL32!CreateSemaphoreExW` at `0x14000aa5c`
- `KERNEL32!CreateSemaphoreExW` at `0x14000aaf8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000a998  mov     [rsp+arg_8], rbx
0x14000a99d  mov     [rsp+arg_10], rbp
0x14000a9a2  push    rsi
0x14000a9a3  push    rdi
0x14000a9a4  push    r12
0x14000a9a6  push    r14
0x14000a9a8  push    r15
0x14000a9aa  sub     rsp, 250h
0x14000a9b1  mov     rax, cs:__security_cookie
0x14000a9b8  xor     rax, rsp
0x14000a9bb  mov     [rsp+278h+var_38], rax
0x14000a9c3  mov     rax, 0C000000000000000h
0x14000a9cd  mov     rbp, r9
0x14000a9d0  mov     r8, rdx
0x14000a9d3  mov     rdi, rcx
0x14000a9d6  test    rax, r9
0x14000a9d9  jnz     loc_14000AB8C
0x14000a9df  xor     r12d, r12d
0x14000a9e2  lea     rax, [rsp+278h+Name]
0x14000a9e7  mov     ecx, 7FFFFFFEh
0x14000a9ec  mov     edx, 104h
0x14000a9f1  lea     esi, [r12+1]
0x14000a9f6  test    rcx, rcx
0x14000a9f9  jz      short loc_14000AA19
0x14000a9fb  movzx   r9d, word ptr [r8]
0x14000a9ff  test    r9w, r9w
0x14000aa03  jz      short loc_14000AA19
0x14000aa05  mov     [rax], r9w
0x14000aa09  add     r8, 2
0x14000aa0d  add     rax, 2
0x14000aa11  sub     rcx, rsi
0x14000aa14  sub     rdx, rsi; unsigned __int64
0x14000aa17  jnz     short loc_14000A9F6
0x14000aa19  test    rdx, rdx
0x14000aa1c  lea     rcx, [rax-2]
0x14000aa20  lea     r8, aP0; "_p0"
0x14000aa27  cmovnz  rcx, rax
0x14000aa2b  mov     [rcx], r12w
0x14000aa2f  lea     rcx, [rsp+278h+Name]; wchar_t *
0x14000aa34  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000aa39  mov     edx, ebp
0x14000aa3b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000aa43  and     edx, 7FFFFFFFh; lInitialCount
0x14000aa49  mov     [rsp+278h+dwFlags], r12d; int
0x14000aa4e  mov     r8d, esi
0x14000aa51  lea     r9, [rsp+278h+Name]; lpName
0x14000aa56  cmova   r8d, edx; lMaximumCount
0x14000aa5a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000aa5c  call    cs:__imp_CreateSemaphoreExW
0x14000aa62  mov     r15, rax
0x14000aa65  test    rax, rax
0x14000aa68  jnz     short loc_14000AA91
0x14000aa6a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000aa6f  mov     ebx, eax
0x14000aa71  test    eax, eax
0x14000aa73  jns     short loc_14000AAC5
0x14000aa75  mov     edx, 8Bh; void *
0x14000aa7a  mov     rcx, [rsp+278h]; this
0x14000aa82  mov     r9d, ebx; char *
0x14000aa85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000aa8a  mov     eax, ebx
0x14000aa8c  jmp     loc_14000AB4D
0x14000aa91  call    cs:__imp_GetLastError
0x14000aa97  mov     rbx, [rdi]
0x14000aa9a  test    rbx, rbx
0x14000aa9d  jz      short loc_14000AAC2
0x14000aa9f  call    cs:__imp_GetLastError
0x14000aaa5  mov     rcx, rbx; hObject
0x14000aaa8  mov     r14d, eax
0x14000aaab  call    cs:__imp_CloseHandle
0x14000aab1  test    eax, eax
0x14000aab3  jz      loc_14000AB92
0x14000aab9  mov     ecx, r14d; dwErrCode
0x14000aabc  call    cs:__imp_SetLastError
0x14000aac2  mov     [rdi], r15
0x14000aac5  lea     r8, asc_1400853D8; "h"
0x14000aacc  shr     rbp, 1Fh
0x14000aad0  lea     rcx, [rsp+278h+Name]; wchar_t *
0x14000aad5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000aada  test    ebp, ebp
0x14000aadc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000aae4  lea     r9, [rsp+278h+Name]; lpName
0x14000aae9  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14000aaee  cmovnz  esi, ebp
0x14000aaf1  mov     edx, ebp; lInitialCount
0x14000aaf3  mov     r8d, esi; lMaximumCount
0x14000aaf6  xor     ecx, ecx; lpSemaphoreAttributes
0x14000aaf8  call    cs:__imp_CreateSemaphoreExW
0x14000aafe  mov     rsi, rax
0x14000ab01  test    rax, rax
0x14000ab04  jnz     short loc_14000AB1B
0x14000ab06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000ab0b  mov     ebx, eax
0x14000ab0d  test    eax, eax
0x14000ab0f  jns     short loc_14000AB4B
0x14000ab11  mov     edx, 90h
0x14000ab16  jmp     loc_14000AA7A
0x14000ab1b  call    cs:__imp_GetLastError
0x14000ab21  mov     rbx, [rdi+8]
0x14000ab25  test    rbx, rbx
0x14000ab28  jz      short loc_14000AB47
0x14000ab2a  call    cs:__imp_GetLastError
0x14000ab30  mov     rcx, rbx; hObject
0x14000ab33  mov     ebp, eax
0x14000ab35  call    cs:__imp_CloseHandle
0x14000ab3b  test    eax, eax
0x14000ab3d  jz      short loc_14000AB79
0x14000ab3f  mov     ecx, ebp; dwErrCode
0x14000ab41  call    cs:__imp_SetLastError
0x14000ab47  mov     [rdi+8], rsi
0x14000ab4b  xor     eax, eax
0x14000ab4d  mov     rcx, [rsp+278h+var_38]
0x14000ab55  xor     rcx, rsp; StackCookie
0x14000ab58  call    __security_check_cookie
0x14000ab5d  lea     r11, [rsp+278h+var_28]
0x14000ab65  mov     rbx, [r11+38h]
0x14000ab69  mov     rbp, [r11+40h]
0x14000ab6d  mov     rsp, r11
0x14000ab70  pop     r15
0x14000ab72  pop     r14
0x14000ab74  pop     r12
0x14000ab76  pop     rdi
0x14000ab77  pop     rsi
0x14000ab78  retn
0x14000ab79  mov     rcx, [rsp+278h]; this
0x14000ab81  mov     edx, 0A0Bh; void *
0x14000ab86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ab8c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ab92  mov     rcx, [rsp+278h]; this
0x14000ab9a  mov     edx, 0A0Bh; void *
0x14000ab9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
