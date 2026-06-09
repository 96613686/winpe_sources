# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x14001c9c0`
- end: `0x14001cbcd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001c61c`

## callees

- `0x140003e50`
- `0x14001c9c0`
- `0x14001d244`
- `0x14001dff4`
- `0x14001e8d0`
- `0x14001ee5c`
- `0x14001ee6c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001cad3`
- `KERNEL32!CloseHandle` at `0x14001cb5d`
- `KERNEL32!CloseHandle` at `0x14001cad3`
- `KERNEL32!CloseHandle` at `0x14001cb5d`
- `KERNEL32!GetLastError` at `0x14001cab9`
- `KERNEL32!GetLastError` at `0x14001cac7`
- `KERNEL32!GetLastError` at `0x14001cb43`
- `KERNEL32!GetLastError` at `0x14001cb52`
- `KERNEL32!GetLastError` at `0x14001cab9`
- `KERNEL32!GetLastError` at `0x14001cac7`
- `KERNEL32!GetLastError` at `0x14001cb43`
- `KERNEL32!GetLastError` at `0x14001cb52`
- `KERNEL32!SetLastError` at `0x14001cae4`
- `KERNEL32!SetLastError` at `0x14001cb69`
- `KERNEL32!SetLastError` at `0x14001cae4`
- `KERNEL32!SetLastError` at `0x14001cb69`
- `KERNEL32!CreateSemaphoreExW` at `0x14001ca84`
- `KERNEL32!CreateSemaphoreExW` at `0x14001cb20`
- `KERNEL32!CreateSemaphoreExW` at `0x14001ca84`
- `KERNEL32!CreateSemaphoreExW` at `0x14001cb20`

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
0x14001c9c0  mov     [rsp+arg_8], rbx
0x14001c9c5  mov     [rsp+arg_10], rbp
0x14001c9ca  push    rsi
0x14001c9cb  push    rdi
0x14001c9cc  push    r12
0x14001c9ce  push    r14
0x14001c9d0  push    r15
0x14001c9d2  sub     rsp, 250h
0x14001c9d9  mov     rax, cs:__security_cookie
0x14001c9e0  xor     rax, rsp
0x14001c9e3  mov     [rsp+278h+var_38], rax
0x14001c9eb  mov     rax, 0C000000000000000h
0x14001c9f5  mov     rbp, r9
0x14001c9f8  mov     r8, rdx
0x14001c9fb  mov     rdi, rcx
0x14001c9fe  test    rax, r9
0x14001ca01  jnz     loc_14001CBB4
0x14001ca07  xor     r12d, r12d
0x14001ca0a  lea     rax, [rsp+278h+Name]
0x14001ca0f  mov     ecx, 7FFFFFFEh
0x14001ca14  mov     edx, 104h
0x14001ca19  lea     esi, [r12+1]
0x14001ca1e  test    rcx, rcx
0x14001ca21  jz      short loc_14001CA41
0x14001ca23  movzx   r9d, word ptr [r8]
0x14001ca27  test    r9w, r9w
0x14001ca2b  jz      short loc_14001CA41
0x14001ca2d  mov     [rax], r9w
0x14001ca31  add     r8, 2
0x14001ca35  add     rax, 2
0x14001ca39  sub     rcx, rsi
0x14001ca3c  sub     rdx, rsi; unsigned __int64
0x14001ca3f  jnz     short loc_14001CA1E
0x14001ca41  test    rdx, rdx
0x14001ca44  lea     rcx, [rax-2]
0x14001ca48  lea     r8, aP0; "_p0"
0x14001ca4f  cmovnz  rcx, rax
0x14001ca53  mov     [rcx], r12w
0x14001ca57  lea     rcx, [rsp+278h+Name]; wchar_t *
0x14001ca5c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001ca61  mov     edx, ebp
0x14001ca63  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14001ca6b  and     edx, 7FFFFFFFh; lInitialCount
0x14001ca71  mov     [rsp+278h+dwFlags], r12d; int
0x14001ca76  mov     r8d, esi
0x14001ca79  lea     r9, [rsp+278h+Name]; lpName
0x14001ca7e  cmova   r8d, edx; lMaximumCount
0x14001ca82  xor     ecx, ecx; lpSemaphoreAttributes
0x14001ca84  call    cs:__imp_CreateSemaphoreExW
0x14001ca8a  mov     r15, rax
0x14001ca8d  test    rax, rax
0x14001ca90  jnz     short loc_14001CAB9
0x14001ca92  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001ca97  mov     ebx, eax
0x14001ca99  test    eax, eax
0x14001ca9b  jns     short loc_14001CAED
0x14001ca9d  mov     edx, 8Bh; void *
0x14001caa2  mov     rcx, [rsp+278h]; this
0x14001caaa  mov     r9d, ebx; char *
0x14001caad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001cab2  mov     eax, ebx
0x14001cab4  jmp     loc_14001CB75
0x14001cab9  call    cs:__imp_GetLastError
0x14001cabf  mov     rbx, [rdi]
0x14001cac2  test    rbx, rbx
0x14001cac5  jz      short loc_14001CAEA
0x14001cac7  call    cs:__imp_GetLastError
0x14001cacd  mov     rcx, rbx; hObject
0x14001cad0  mov     r14d, eax
0x14001cad3  call    cs:__imp_CloseHandle
0x14001cad9  test    eax, eax
0x14001cadb  jz      loc_14001CBBA
0x14001cae1  mov     ecx, r14d; dwErrCode
0x14001cae4  call    cs:__imp_SetLastError
0x14001caea  mov     [rdi], r15
0x14001caed  lea     r8, asc_1400A77A8; "h"
0x14001caf4  shr     rbp, 1Fh
0x14001caf8  lea     rcx, [rsp+278h+Name]; wchar_t *
0x14001cafd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001cb02  test    ebp, ebp
0x14001cb04  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14001cb0c  lea     r9, [rsp+278h+Name]; lpName
0x14001cb11  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14001cb16  cmovnz  esi, ebp
0x14001cb19  mov     edx, ebp; lInitialCount
0x14001cb1b  mov     r8d, esi; lMaximumCount
0x14001cb1e  xor     ecx, ecx; lpSemaphoreAttributes
0x14001cb20  call    cs:__imp_CreateSemaphoreExW
0x14001cb26  mov     rsi, rax
0x14001cb29  test    rax, rax
0x14001cb2c  jnz     short loc_14001CB43
0x14001cb2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001cb33  mov     ebx, eax
0x14001cb35  test    eax, eax
0x14001cb37  jns     short loc_14001CB73
0x14001cb39  mov     edx, 90h
0x14001cb3e  jmp     loc_14001CAA2
0x14001cb43  call    cs:__imp_GetLastError
0x14001cb49  mov     rbx, [rdi+8]
0x14001cb4d  test    rbx, rbx
0x14001cb50  jz      short loc_14001CB6F
0x14001cb52  call    cs:__imp_GetLastError
0x14001cb58  mov     rcx, rbx; hObject
0x14001cb5b  mov     ebp, eax
0x14001cb5d  call    cs:__imp_CloseHandle
0x14001cb63  test    eax, eax
0x14001cb65  jz      short loc_14001CBA1
0x14001cb67  mov     ecx, ebp; dwErrCode
0x14001cb69  call    cs:__imp_SetLastError
0x14001cb6f  mov     [rdi+8], rsi
0x14001cb73  xor     eax, eax
0x14001cb75  mov     rcx, [rsp+278h+var_38]
0x14001cb7d  xor     rcx, rsp; StackCookie
0x14001cb80  call    __security_check_cookie
0x14001cb85  lea     r11, [rsp+278h+var_28]
0x14001cb8d  mov     rbx, [r11+38h]
0x14001cb91  mov     rbp, [r11+40h]
0x14001cb95  mov     rsp, r11
0x14001cb98  pop     r15
0x14001cb9a  pop     r14
0x14001cb9c  pop     r12
0x14001cb9e  pop     rdi
0x14001cb9f  pop     rsi
0x14001cba0  retn
0x14001cba1  mov     rcx, [rsp+278h]; this
0x14001cba9  mov     edx, 0A0Bh; void *
0x14001cbae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001cbb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14001cbba  mov     rcx, [rsp+278h]; this
0x14001cbc2  mov     edx, 0A0Bh; void *
0x14001cbc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
