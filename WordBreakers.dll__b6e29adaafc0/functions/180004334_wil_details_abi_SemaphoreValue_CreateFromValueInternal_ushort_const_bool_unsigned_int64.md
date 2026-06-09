# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004334`
- end: `0x180004541`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f90`
- `0x180007dd8`

## callees

- `0x180004334`
- `0x180004b98`
- `0x1800058d4`
- `0x180006054`
- `0x18000669c`
- `0x1800066ac`
- `0x18000b640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000443b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000443b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044dd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004494`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d1`

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
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
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
0x180004334  mov     [rsp+arg_8], rbx
0x180004339  mov     [rsp+arg_10], rbp
0x18000433e  push    rsi
0x18000433f  push    rdi
0x180004340  push    r12
0x180004342  push    r14
0x180004344  push    r15
0x180004346  sub     rsp, 250h
0x18000434d  mov     rax, cs:__security_cookie
0x180004354  xor     rax, rsp
0x180004357  mov     [rsp+278h+var_38], rax
0x18000435f  mov     rax, 0C000000000000000h
0x180004369  mov     rbp, r9
0x18000436c  mov     r8, rdx
0x18000436f  mov     rdi, rcx
0x180004372  test    rax, r9
0x180004375  jnz     loc_180004528
0x18000437b  xor     r12d, r12d
0x18000437e  lea     rax, [rsp+278h+Name]
0x180004383  mov     ecx, 7FFFFFFEh
0x180004388  mov     edx, 104h
0x18000438d  lea     esi, [r12+1]
0x180004392  test    rcx, rcx
0x180004395  jz      short loc_1800043B5
0x180004397  movzx   r9d, word ptr [r8]
0x18000439b  test    r9w, r9w
0x18000439f  jz      short loc_1800043B5
0x1800043a1  mov     [rax], r9w
0x1800043a5  add     r8, 2
0x1800043a9  add     rax, 2
0x1800043ad  sub     rcx, rsi
0x1800043b0  sub     rdx, rsi; unsigned __int64
0x1800043b3  jnz     short loc_180004392
0x1800043b5  test    rdx, rdx
0x1800043b8  lea     rcx, [rax-2]
0x1800043bc  lea     r8, aP0; "_p0"
0x1800043c3  cmovnz  rcx, rax
0x1800043c7  mov     [rcx], r12w
0x1800043cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800043d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043d5  mov     edx, ebp
0x1800043d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043df  and     edx, 7FFFFFFFh; lInitialCount
0x1800043e5  mov     [rsp+278h+dwFlags], r12d; int
0x1800043ea  mov     r8d, esi
0x1800043ed  lea     r9, [rsp+278h+Name]; lpName
0x1800043f2  cmova   r8d, edx; lMaximumCount
0x1800043f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800043f8  call    cs:__imp_CreateSemaphoreExW
0x1800043fe  mov     r15, rax
0x180004401  test    rax, rax
0x180004404  jnz     short loc_18000442D
0x180004406  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000440b  mov     ebx, eax
0x18000440d  test    eax, eax
0x18000440f  jns     short loc_180004461
0x180004411  mov     edx, 8Bh; void *
0x180004416  mov     rcx, [rsp+278h]; this
0x18000441e  mov     r9d, ebx; char *
0x180004421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004426  mov     eax, ebx
0x180004428  jmp     loc_1800044E9
0x18000442d  call    cs:__imp_GetLastError
0x180004433  mov     rbx, [rdi]
0x180004436  test    rbx, rbx
0x180004439  jz      short loc_18000445E
0x18000443b  call    cs:__imp_GetLastError
0x180004441  mov     rcx, rbx; hObject
0x180004444  mov     r14d, eax
0x180004447  call    cs:__imp_CloseHandle
0x18000444d  test    eax, eax
0x18000444f  jz      loc_18000452E
0x180004455  mov     ecx, r14d; dwErrCode
0x180004458  call    cs:__imp_SetLastError
0x18000445e  mov     [rdi], r15
0x180004461  lea     r8, asc_18000F310; "h"
0x180004468  shr     rbp, 1Fh
0x18000446c  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004471  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004476  test    ebp, ebp
0x180004478  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004480  lea     r9, [rsp+278h+Name]; lpName
0x180004485  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000448a  cmovnz  esi, ebp
0x18000448d  mov     edx, ebp; lInitialCount
0x18000448f  mov     r8d, esi; lMaximumCount
0x180004492  xor     ecx, ecx; lpSemaphoreAttributes
0x180004494  call    cs:__imp_CreateSemaphoreExW
0x18000449a  mov     rsi, rax
0x18000449d  test    rax, rax
0x1800044a0  jnz     short loc_1800044B7
0x1800044a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044a7  mov     ebx, eax
0x1800044a9  test    eax, eax
0x1800044ab  jns     short loc_1800044E7
0x1800044ad  mov     edx, 90h
0x1800044b2  jmp     loc_180004416
0x1800044b7  call    cs:__imp_GetLastError
0x1800044bd  mov     rbx, [rdi+8]
0x1800044c1  test    rbx, rbx
0x1800044c4  jz      short loc_1800044E3
0x1800044c6  call    cs:__imp_GetLastError
0x1800044cc  mov     rcx, rbx; hObject
0x1800044cf  mov     ebp, eax
0x1800044d1  call    cs:__imp_CloseHandle
0x1800044d7  test    eax, eax
0x1800044d9  jz      short loc_180004515
0x1800044db  mov     ecx, ebp; dwErrCode
0x1800044dd  call    cs:__imp_SetLastError
0x1800044e3  mov     [rdi+8], rsi
0x1800044e7  xor     eax, eax
0x1800044e9  mov     rcx, [rsp+278h+var_38]
0x1800044f1  xor     rcx, rsp; StackCookie
0x1800044f4  call    __security_check_cookie
0x1800044f9  lea     r11, [rsp+278h+var_28]
0x180004501  mov     rbx, [r11+38h]
0x180004505  mov     rbp, [r11+40h]
0x180004509  mov     rsp, r11
0x18000450c  pop     r15
0x18000450e  pop     r14
0x180004510  pop     r12
0x180004512  pop     rdi
0x180004513  pop     rsi
0x180004514  retn
0x180004515  mov     rcx, [rsp+278h]; this
0x18000451d  mov     edx, 0A0Bh; void *
0x180004522  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004528  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000452e  mov     rcx, [rsp+278h]; this
0x180004536  mov     edx, 0A0Bh; void *
0x18000453b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
