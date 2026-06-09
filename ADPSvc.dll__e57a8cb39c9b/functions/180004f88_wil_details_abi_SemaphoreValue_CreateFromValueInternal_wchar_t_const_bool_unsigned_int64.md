# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004f88`
- end: `0x1800051c0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004ba8`
- `0x180008b94`

## callees

- `0x180002250`
- `0x180004f88`
- `0x1800058e8`
- `0x180006844`
- `0x180007184`
- `0x18000770c`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000504c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800050ef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000504c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800050ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000514e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000514e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005137`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005142`

## string_xrefs

- `0x18000518e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800051ae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
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
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004f88  mov     [rsp+arg_8], rbx
0x180004f8d  mov     [rsp+arg_10], rbp
0x180004f92  push    rsi
0x180004f93  push    rdi
0x180004f94  push    r12
0x180004f96  push    r14
0x180004f98  push    r15
0x180004f9a  sub     rsp, 250h
0x180004fa1  mov     rax, cs:__security_cookie
0x180004fa8  xor     rax, rsp
0x180004fab  mov     [rsp+278h+var_38], rax
0x180004fb3  mov     rax, 0C000000000000000h
0x180004fbd  mov     rbp, r9
0x180004fc0  mov     r8, rdx
0x180004fc3  mov     rbx, rcx
0x180004fc6  test    rax, r9
0x180004fc9  jnz     loc_1800051A0
0x180004fcf  xor     r12d, r12d
0x180004fd2  lea     rax, [rsp+278h+Name]
0x180004fd7  mov     ecx, 7FFFFFFEh
0x180004fdc  mov     edx, 104h
0x180004fe1  lea     esi, [r12+1]
0x180004fe6  test    rcx, rcx
0x180004fe9  jz      short loc_180005009
0x180004feb  movzx   r9d, word ptr [r8]
0x180004fef  test    r9w, r9w
0x180004ff3  jz      short loc_180005009
0x180004ff5  mov     [rax], r9w
0x180004ff9  add     r8, 2
0x180004ffd  add     rax, 2
0x180005001  sub     rcx, rsi
0x180005004  sub     rdx, rsi; unsigned __int64
0x180005007  jnz     short loc_180004FE6
0x180005009  test    rdx, rdx
0x18000500c  lea     rcx, [rax-2]
0x180005010  lea     r8, aP0; "_p0"
0x180005017  cmovnz  rcx, rax
0x18000501b  mov     [rcx], r12w
0x18000501f  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180005024  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005029  mov     edx, ebp
0x18000502b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005033  and     edx, 7FFFFFFFh; lInitialCount
0x180005039  mov     [rsp+278h+dwFlags], r12d; int
0x18000503e  mov     r8d, esi
0x180005041  lea     r9, [rsp+278h+Name]; lpName
0x180005046  cmova   r8d, edx; lMaximumCount
0x18000504a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000504c  call    cs:__imp_CreateSemaphoreExW
0x180005052  mov     r15, rax
0x180005055  test    rax, rax
0x180005058  jnz     short loc_180005088
0x18000505a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000505f  mov     edi, eax
0x180005061  test    eax, eax
0x180005063  jns     short loc_1800050BC
0x180005065  mov     rcx, [rsp+278h]; this
0x18000506d  lea     r8, aWil; "wil"
0x180005074  mov     r9d, eax; char *
0x180005077  mov     edx, 8Bh; void *
0x18000507c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005081  mov     eax, edi
0x180005083  jmp     loc_18000515A
0x180005088  call    cs:__imp_GetLastError
0x18000508e  mov     rdi, [rbx]
0x180005091  test    rdi, rdi
0x180005094  jz      short loc_1800050B9
0x180005096  call    cs:__imp_GetLastError
0x18000509c  mov     rcx, rdi; hObject
0x18000509f  mov     r14d, eax
0x1800050a2  call    cs:__imp_CloseHandle
0x1800050a8  test    eax, eax
0x1800050aa  jz      loc_1800051A6
0x1800050b0  mov     ecx, r14d; dwErrCode
0x1800050b3  call    cs:__imp_SetLastError
0x1800050b9  mov     [rbx], r15
0x1800050bc  lea     r8, asc_1800ED060; "h"
0x1800050c3  shr     rbp, 1Fh
0x1800050c7  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800050cc  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800050d1  test    ebp, ebp
0x1800050d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800050db  lea     r9, [rsp+278h+Name]; lpName
0x1800050e0  mov     [rsp+278h+dwFlags], r12d; int
0x1800050e5  cmovnz  esi, ebp
0x1800050e8  mov     edx, ebp; lInitialCount
0x1800050ea  mov     r8d, esi; lMaximumCount
0x1800050ed  xor     ecx, ecx; lpSemaphoreAttributes
0x1800050ef  call    cs:__imp_CreateSemaphoreExW
0x1800050f5  mov     rsi, rax
0x1800050f8  test    rax, rax
0x1800050fb  jnz     short loc_180005128
0x1800050fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005102  mov     ebx, eax
0x180005104  test    eax, eax
0x180005106  jns     short loc_180005158
0x180005108  mov     rcx, [rsp+278h]; this
0x180005110  lea     r8, aWil; "wil"
0x180005117  mov     r9d, eax; char *
0x18000511a  mov     edx, 90h; void *
0x18000511f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005124  mov     eax, ebx
0x180005126  jmp     short loc_18000515A
0x180005128  call    cs:__imp_GetLastError
0x18000512e  mov     rdi, [rbx+8]
0x180005132  test    rdi, rdi
0x180005135  jz      short loc_180005154
0x180005137  call    cs:__imp_GetLastError
0x18000513d  mov     rcx, rdi; hObject
0x180005140  mov     ebp, eax
0x180005142  call    cs:__imp_CloseHandle
0x180005148  test    eax, eax
0x18000514a  jz      short loc_180005186
0x18000514c  mov     ecx, ebp; dwErrCode
0x18000514e  call    cs:__imp_SetLastError
0x180005154  mov     [rbx+8], rsi
0x180005158  xor     eax, eax
0x18000515a  mov     rcx, [rsp+278h+var_38]
0x180005162  xor     rcx, rsp; StackCookie
0x180005165  call    __security_check_cookie
0x18000516a  lea     r11, [rsp+278h+var_28]
0x180005172  mov     rbx, [r11+38h]
0x180005176  mov     rbp, [r11+40h]
0x18000517a  mov     rsp, r11
0x18000517d  pop     r15
0x18000517f  pop     r14
0x180005181  pop     r12
0x180005183  pop     rdi
0x180005184  pop     rsi
0x180005185  retn
0x180005186  mov     rcx, [rsp+278h]; this
0x18000518e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005195  mov     edx, 0A0Bh; void *
0x18000519a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051a0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800051a6  mov     rcx, [rsp+278h]; this
0x1800051ae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800051b5  mov     edx, 0A0Bh; void *
0x1800051ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
