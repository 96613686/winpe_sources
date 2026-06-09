# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000427c`
- end: `0x180004489`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b08`
- `0x180003eac`

## callees

- `0x180001670`
- `0x18000427c`
- `0x180005288`
- `0x180007964`
- `0x1800083a8`
- `0x18000916c`
- `0x18000917c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004425`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004340`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004340`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000438f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000438f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004419`

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
0x18000427c  mov     [rsp+arg_8], rbx
0x180004281  mov     [rsp+arg_10], rbp
0x180004286  push    rsi
0x180004287  push    rdi
0x180004288  push    r12
0x18000428a  push    r14
0x18000428c  push    r15
0x18000428e  sub     rsp, 250h
0x180004295  mov     rax, cs:__security_cookie
0x18000429c  xor     rax, rsp
0x18000429f  mov     [rsp+278h+var_38], rax
0x1800042a7  mov     rax, 0C000000000000000h
0x1800042b1  mov     rbp, r9
0x1800042b4  mov     r8, rdx
0x1800042b7  mov     rdi, rcx
0x1800042ba  test    rax, r9
0x1800042bd  jnz     loc_180004470
0x1800042c3  xor     r12d, r12d
0x1800042c6  lea     rax, [rsp+278h+Name]
0x1800042cb  mov     ecx, 7FFFFFFEh
0x1800042d0  mov     edx, 104h
0x1800042d5  lea     esi, [r12+1]
0x1800042da  test    rcx, rcx
0x1800042dd  jz      short loc_1800042FD
0x1800042df  movzx   r9d, word ptr [r8]
0x1800042e3  test    r9w, r9w
0x1800042e7  jz      short loc_1800042FD
0x1800042e9  mov     [rax], r9w
0x1800042ed  add     r8, 2
0x1800042f1  add     rax, 2
0x1800042f5  sub     rcx, rsi
0x1800042f8  sub     rdx, rsi; unsigned __int64
0x1800042fb  jnz     short loc_1800042DA
0x1800042fd  test    rdx, rdx
0x180004300  lea     rcx, [rax-2]
0x180004304  lea     r8, aP0; "_p0"
0x18000430b  cmovnz  rcx, rax
0x18000430f  mov     [rcx], r12w
0x180004313  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004318  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000431d  mov     edx, ebp
0x18000431f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004327  and     edx, 7FFFFFFFh; lInitialCount
0x18000432d  mov     [rsp+278h+dwFlags], r12d; int
0x180004332  mov     r8d, esi
0x180004335  lea     r9, [rsp+278h+Name]; lpName
0x18000433a  cmova   r8d, edx; lMaximumCount
0x18000433e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004340  call    cs:__imp_CreateSemaphoreExW
0x180004346  mov     r15, rax
0x180004349  test    rax, rax
0x18000434c  jnz     short loc_180004375
0x18000434e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004353  mov     ebx, eax
0x180004355  test    eax, eax
0x180004357  jns     short loc_1800043A9
0x180004359  mov     edx, 8Bh; void *
0x18000435e  mov     rcx, [rsp+278h]; this
0x180004366  mov     r9d, ebx; char *
0x180004369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000436e  mov     eax, ebx
0x180004370  jmp     loc_180004431
0x180004375  call    cs:__imp_GetLastError
0x18000437b  mov     rbx, [rdi]
0x18000437e  test    rbx, rbx
0x180004381  jz      short loc_1800043A6
0x180004383  call    cs:__imp_GetLastError
0x180004389  mov     rcx, rbx; hObject
0x18000438c  mov     r14d, eax
0x18000438f  call    cs:__imp_CloseHandle
0x180004395  test    eax, eax
0x180004397  jz      loc_180004476
0x18000439d  mov     ecx, r14d; dwErrCode
0x1800043a0  call    cs:__imp_SetLastError
0x1800043a6  mov     [rdi], r15
0x1800043a9  lea     r8, asc_180016458; "h"
0x1800043b0  shr     rbp, 1Fh
0x1800043b4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800043b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043be  test    ebp, ebp
0x1800043c0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043c8  lea     r9, [rsp+278h+Name]; lpName
0x1800043cd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800043d2  cmovnz  esi, ebp
0x1800043d5  mov     edx, ebp; lInitialCount
0x1800043d7  mov     r8d, esi; lMaximumCount
0x1800043da  xor     ecx, ecx; lpSemaphoreAttributes
0x1800043dc  call    cs:__imp_CreateSemaphoreExW
0x1800043e2  mov     rsi, rax
0x1800043e5  test    rax, rax
0x1800043e8  jnz     short loc_1800043FF
0x1800043ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800043ef  mov     ebx, eax
0x1800043f1  test    eax, eax
0x1800043f3  jns     short loc_18000442F
0x1800043f5  mov     edx, 90h
0x1800043fa  jmp     loc_18000435E
0x1800043ff  call    cs:__imp_GetLastError
0x180004405  mov     rbx, [rdi+8]
0x180004409  test    rbx, rbx
0x18000440c  jz      short loc_18000442B
0x18000440e  call    cs:__imp_GetLastError
0x180004414  mov     rcx, rbx; hObject
0x180004417  mov     ebp, eax
0x180004419  call    cs:__imp_CloseHandle
0x18000441f  test    eax, eax
0x180004421  jz      short loc_18000445D
0x180004423  mov     ecx, ebp; dwErrCode
0x180004425  call    cs:__imp_SetLastError
0x18000442b  mov     [rdi+8], rsi
0x18000442f  xor     eax, eax
0x180004431  mov     rcx, [rsp+278h+var_38]
0x180004439  xor     rcx, rsp; StackCookie
0x18000443c  call    __security_check_cookie
0x180004441  lea     r11, [rsp+278h+var_28]
0x180004449  mov     rbx, [r11+38h]
0x18000444d  mov     rbp, [r11+40h]
0x180004451  mov     rsp, r11
0x180004454  pop     r15
0x180004456  pop     r14
0x180004458  pop     r12
0x18000445a  pop     rdi
0x18000445b  pop     rsi
0x18000445c  retn
0x18000445d  mov     rcx, [rsp+278h]; this
0x180004465  mov     edx, 0A0Bh; void *
0x18000446a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004470  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004476  mov     rcx, [rsp+278h]; this
0x18000447e  mov     edx, 0A0Bh; void *
0x180004483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
