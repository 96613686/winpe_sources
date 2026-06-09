# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004140`
- end: `0x18000434d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003940`
- `0x180003ce4`

## callees

- `0x180004140`
- `0x180005908`
- `0x180008a34`
- `0x1800093d0`
- `0x18000ab0c`
- `0x18000ab1c`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004204`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042a0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004204`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042dd`

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
0x180004140  mov     [rsp+arg_8], rbx
0x180004145  mov     [rsp+arg_10], rbp
0x18000414a  push    rsi
0x18000414b  push    rdi
0x18000414c  push    r12
0x18000414e  push    r14
0x180004150  push    r15
0x180004152  sub     rsp, 250h
0x180004159  mov     rax, cs:__security_cookie
0x180004160  xor     rax, rsp
0x180004163  mov     [rsp+278h+var_38], rax
0x18000416b  mov     rax, 0C000000000000000h
0x180004175  mov     rbp, r9
0x180004178  mov     r8, rdx
0x18000417b  mov     rdi, rcx
0x18000417e  test    rax, r9
0x180004181  jnz     loc_180004334
0x180004187  xor     r12d, r12d
0x18000418a  lea     rax, [rsp+278h+Name]
0x18000418f  mov     ecx, 7FFFFFFEh
0x180004194  mov     edx, 104h
0x180004199  lea     esi, [r12+1]
0x18000419e  test    rcx, rcx
0x1800041a1  jz      short loc_1800041C1
0x1800041a3  movzx   r9d, word ptr [r8]
0x1800041a7  test    r9w, r9w
0x1800041ab  jz      short loc_1800041C1
0x1800041ad  mov     [rax], r9w
0x1800041b1  add     r8, 2
0x1800041b5  add     rax, 2
0x1800041b9  sub     rcx, rsi
0x1800041bc  sub     rdx, rsi; unsigned __int64
0x1800041bf  jnz     short loc_18000419E
0x1800041c1  test    rdx, rdx
0x1800041c4  lea     rcx, [rax-2]
0x1800041c8  lea     r8, aP0; "_p0"
0x1800041cf  cmovnz  rcx, rax
0x1800041d3  mov     [rcx], r12w
0x1800041d7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800041dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800041e1  mov     edx, ebp
0x1800041e3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800041eb  and     edx, 7FFFFFFFh; lInitialCount
0x1800041f1  mov     [rsp+278h+dwFlags], r12d; int
0x1800041f6  mov     r8d, esi
0x1800041f9  lea     r9, [rsp+278h+Name]; lpName
0x1800041fe  cmova   r8d, edx; lMaximumCount
0x180004202  xor     ecx, ecx; lpSemaphoreAttributes
0x180004204  call    cs:__imp_CreateSemaphoreExW
0x18000420a  mov     r15, rax
0x18000420d  test    rax, rax
0x180004210  jnz     short loc_180004239
0x180004212  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004217  mov     ebx, eax
0x180004219  test    eax, eax
0x18000421b  jns     short loc_18000426D
0x18000421d  mov     edx, 8Bh; void *
0x180004222  mov     rcx, [rsp+278h]; this
0x18000422a  mov     r9d, ebx; char *
0x18000422d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004232  mov     eax, ebx
0x180004234  jmp     loc_1800042F5
0x180004239  call    cs:__imp_GetLastError
0x18000423f  mov     rbx, [rdi]
0x180004242  test    rbx, rbx
0x180004245  jz      short loc_18000426A
0x180004247  call    cs:__imp_GetLastError
0x18000424d  mov     rcx, rbx; hObject
0x180004250  mov     r14d, eax
0x180004253  call    cs:__imp_CloseHandle
0x180004259  test    eax, eax
0x18000425b  jz      loc_18000433A
0x180004261  mov     ecx, r14d; dwErrCode
0x180004264  call    cs:__imp_SetLastError
0x18000426a  mov     [rdi], r15
0x18000426d  lea     r8, asc_180010258; "h"
0x180004274  shr     rbp, 1Fh
0x180004278  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000427d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004282  test    ebp, ebp
0x180004284  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000428c  lea     r9, [rsp+278h+Name]; lpName
0x180004291  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004296  cmovnz  esi, ebp
0x180004299  mov     edx, ebp; lInitialCount
0x18000429b  mov     r8d, esi; lMaximumCount
0x18000429e  xor     ecx, ecx; lpSemaphoreAttributes
0x1800042a0  call    cs:__imp_CreateSemaphoreExW
0x1800042a6  mov     rsi, rax
0x1800042a9  test    rax, rax
0x1800042ac  jnz     short loc_1800042C3
0x1800042ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800042b3  mov     ebx, eax
0x1800042b5  test    eax, eax
0x1800042b7  jns     short loc_1800042F3
0x1800042b9  mov     edx, 90h
0x1800042be  jmp     loc_180004222
0x1800042c3  call    cs:__imp_GetLastError
0x1800042c9  mov     rbx, [rdi+8]
0x1800042cd  test    rbx, rbx
0x1800042d0  jz      short loc_1800042EF
0x1800042d2  call    cs:__imp_GetLastError
0x1800042d8  mov     rcx, rbx; hObject
0x1800042db  mov     ebp, eax
0x1800042dd  call    cs:__imp_CloseHandle
0x1800042e3  test    eax, eax
0x1800042e5  jz      short loc_180004321
0x1800042e7  mov     ecx, ebp; dwErrCode
0x1800042e9  call    cs:__imp_SetLastError
0x1800042ef  mov     [rdi+8], rsi
0x1800042f3  xor     eax, eax
0x1800042f5  mov     rcx, [rsp+278h+var_38]
0x1800042fd  xor     rcx, rsp; StackCookie
0x180004300  call    __security_check_cookie
0x180004305  lea     r11, [rsp+278h+var_28]
0x18000430d  mov     rbx, [r11+38h]
0x180004311  mov     rbp, [r11+40h]
0x180004315  mov     rsp, r11
0x180004318  pop     r15
0x18000431a  pop     r14
0x18000431c  pop     r12
0x18000431e  pop     rdi
0x18000431f  pop     rsi
0x180004320  retn
0x180004321  mov     rcx, [rsp+278h]; this
0x180004329  mov     edx, 0A0Bh; void *
0x18000432e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004334  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000433a  mov     rcx, [rsp+278h]; this
0x180004342  mov     edx, 0A0Bh; void *
0x180004347  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
