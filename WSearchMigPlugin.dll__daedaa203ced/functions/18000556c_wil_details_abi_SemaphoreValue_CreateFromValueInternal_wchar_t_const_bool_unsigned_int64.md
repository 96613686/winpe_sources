# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000556c`
- end: `0x180005779`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004df8`
- `0x18000519c`

## callees

- `0x1800026f0`
- `0x18000556c`
- `0x1800063f0`
- `0x1800086cc`
- `0x180009134`
- `0x180009efc`
- `0x180009f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005630`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800056cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005630`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800056cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005690`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005715`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005690`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000567f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000567f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005709`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000556c  mov     [rsp+arg_8], rbx
0x180005571  mov     [rsp+arg_10], rbp
0x180005576  push    rsi
0x180005577  push    rdi
0x180005578  push    r12
0x18000557a  push    r14
0x18000557c  push    r15
0x18000557e  sub     rsp, 250h
0x180005585  mov     rax, cs:__security_cookie
0x18000558c  xor     rax, rsp
0x18000558f  mov     [rsp+278h+var_38], rax
0x180005597  mov     rax, 0C000000000000000h
0x1800055a1  mov     rbp, r9
0x1800055a4  mov     r8, rdx
0x1800055a7  mov     rdi, rcx
0x1800055aa  test    rax, r9
0x1800055ad  jnz     loc_180005760
0x1800055b3  xor     r12d, r12d
0x1800055b6  lea     rax, [rsp+278h+Name]
0x1800055bb  mov     ecx, 7FFFFFFEh
0x1800055c0  mov     edx, 104h
0x1800055c5  lea     esi, [r12+1]
0x1800055ca  test    rcx, rcx
0x1800055cd  jz      short loc_1800055ED
0x1800055cf  movzx   r9d, word ptr [r8]
0x1800055d3  test    r9w, r9w
0x1800055d7  jz      short loc_1800055ED
0x1800055d9  mov     [rax], r9w
0x1800055dd  add     r8, 2
0x1800055e1  add     rax, 2
0x1800055e5  sub     rcx, rsi
0x1800055e8  sub     rdx, rsi; unsigned __int64
0x1800055eb  jnz     short loc_1800055CA
0x1800055ed  test    rdx, rdx
0x1800055f0  lea     rcx, [rax-2]
0x1800055f4  lea     r8, aP0; "_p0"
0x1800055fb  cmovnz  rcx, rax
0x1800055ff  mov     [rcx], r12w
0x180005603  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180005608  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000560d  mov     edx, ebp
0x18000560f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005617  and     edx, 7FFFFFFFh; lInitialCount
0x18000561d  mov     [rsp+278h+dwFlags], r12d; int
0x180005622  mov     r8d, esi
0x180005625  lea     r9, [rsp+278h+Name]; lpName
0x18000562a  cmova   r8d, edx; lMaximumCount
0x18000562e  xor     ecx, ecx; lpSemaphoreAttributes
0x180005630  call    cs:__imp_CreateSemaphoreExW
0x180005636  mov     r15, rax
0x180005639  test    rax, rax
0x18000563c  jnz     short loc_180005665
0x18000563e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005643  mov     ebx, eax
0x180005645  test    eax, eax
0x180005647  jns     short loc_180005699
0x180005649  mov     edx, 8Bh; void *
0x18000564e  mov     rcx, [rsp+278h]; this
0x180005656  mov     r9d, ebx; char *
0x180005659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000565e  mov     eax, ebx
0x180005660  jmp     loc_180005721
0x180005665  call    cs:__imp_GetLastError
0x18000566b  mov     rbx, [rdi]
0x18000566e  test    rbx, rbx
0x180005671  jz      short loc_180005696
0x180005673  call    cs:__imp_GetLastError
0x180005679  mov     rcx, rbx; hObject
0x18000567c  mov     r14d, eax
0x18000567f  call    cs:__imp_CloseHandle
0x180005685  test    eax, eax
0x180005687  jz      loc_180005766
0x18000568d  mov     ecx, r14d; dwErrCode
0x180005690  call    cs:__imp_SetLastError
0x180005696  mov     [rdi], r15
0x180005699  lea     r8, asc_18001AC50; "h"
0x1800056a0  shr     rbp, 1Fh
0x1800056a4  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800056a9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800056ae  test    ebp, ebp
0x1800056b0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800056b8  lea     r9, [rsp+278h+Name]; lpName
0x1800056bd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800056c2  cmovnz  esi, ebp
0x1800056c5  mov     edx, ebp; lInitialCount
0x1800056c7  mov     r8d, esi; lMaximumCount
0x1800056ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1800056cc  call    cs:__imp_CreateSemaphoreExW
0x1800056d2  mov     rsi, rax
0x1800056d5  test    rax, rax
0x1800056d8  jnz     short loc_1800056EF
0x1800056da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800056df  mov     ebx, eax
0x1800056e1  test    eax, eax
0x1800056e3  jns     short loc_18000571F
0x1800056e5  mov     edx, 90h
0x1800056ea  jmp     loc_18000564E
0x1800056ef  call    cs:__imp_GetLastError
0x1800056f5  mov     rbx, [rdi+8]
0x1800056f9  test    rbx, rbx
0x1800056fc  jz      short loc_18000571B
0x1800056fe  call    cs:__imp_GetLastError
0x180005704  mov     rcx, rbx; hObject
0x180005707  mov     ebp, eax
0x180005709  call    cs:__imp_CloseHandle
0x18000570f  test    eax, eax
0x180005711  jz      short loc_18000574D
0x180005713  mov     ecx, ebp; dwErrCode
0x180005715  call    cs:__imp_SetLastError
0x18000571b  mov     [rdi+8], rsi
0x18000571f  xor     eax, eax
0x180005721  mov     rcx, [rsp+278h+var_38]
0x180005729  xor     rcx, rsp; StackCookie
0x18000572c  call    __security_check_cookie
0x180005731  lea     r11, [rsp+278h+var_28]
0x180005739  mov     rbx, [r11+38h]
0x18000573d  mov     rbp, [r11+40h]
0x180005741  mov     rsp, r11
0x180005744  pop     r15
0x180005746  pop     r14
0x180005748  pop     r12
0x18000574a  pop     rdi
0x18000574b  pop     rsi
0x18000574c  retn
0x18000574d  mov     rcx, [rsp+278h]; this
0x180005755  mov     edx, 0A0Bh; void *
0x18000575a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005760  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005766  mov     rcx, [rsp+278h]; this
0x18000576e  mov     edx, 0A0Bh; void *
0x180005773  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
