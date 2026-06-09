# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000744c`
- end: `0x180007684`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006c68`
- `0x180007048`

## callees

- `0x1800033d0`
- `0x18000744c`
- `0x1800082c8`
- `0x18000a894`
- `0x18000b2e4`
- `0x18000c258`
- `0x18000c268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007510`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800075b3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007510`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800075b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007577`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007612`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007577`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007606`

## string_xrefs

- `0x180007652`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007672`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000744c  mov     [rsp+arg_8], rbx
0x180007451  mov     [rsp+arg_10], rbp
0x180007456  push    rsi
0x180007457  push    rdi
0x180007458  push    r12
0x18000745a  push    r14
0x18000745c  push    r15
0x18000745e  sub     rsp, 250h
0x180007465  mov     rax, cs:__security_cookie
0x18000746c  xor     rax, rsp
0x18000746f  mov     [rsp+278h+var_38], rax
0x180007477  mov     rax, 0C000000000000000h
0x180007481  mov     rbp, r9
0x180007484  mov     r8, rdx
0x180007487  mov     rbx, rcx
0x18000748a  test    rax, r9
0x18000748d  jnz     loc_180007664
0x180007493  xor     r12d, r12d
0x180007496  lea     rax, [rsp+278h+Name]
0x18000749b  mov     ecx, 7FFFFFFEh
0x1800074a0  mov     edx, 104h
0x1800074a5  lea     esi, [r12+1]
0x1800074aa  test    rcx, rcx
0x1800074ad  jz      short loc_1800074CD
0x1800074af  movzx   r9d, word ptr [r8]
0x1800074b3  test    r9w, r9w
0x1800074b7  jz      short loc_1800074CD
0x1800074b9  mov     [rax], r9w
0x1800074bd  add     r8, 2
0x1800074c1  add     rax, 2
0x1800074c5  sub     rcx, rsi
0x1800074c8  sub     rdx, rsi; unsigned __int64
0x1800074cb  jnz     short loc_1800074AA
0x1800074cd  test    rdx, rdx
0x1800074d0  lea     rcx, [rax-2]
0x1800074d4  lea     r8, aP0; "_p0"
0x1800074db  cmovnz  rcx, rax
0x1800074df  mov     [rcx], r12w
0x1800074e3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800074e8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800074ed  mov     edx, ebp
0x1800074ef  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800074f7  and     edx, 7FFFFFFFh; lInitialCount
0x1800074fd  mov     [rsp+278h+dwFlags], r12d; int
0x180007502  mov     r8d, esi
0x180007505  lea     r9, [rsp+278h+Name]; lpName
0x18000750a  cmova   r8d, edx; lMaximumCount
0x18000750e  xor     ecx, ecx; lpSemaphoreAttributes
0x180007510  call    cs:__imp_CreateSemaphoreExW
0x180007516  mov     r15, rax
0x180007519  test    rax, rax
0x18000751c  jnz     short loc_18000754C
0x18000751e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007523  mov     edi, eax
0x180007525  test    eax, eax
0x180007527  jns     short loc_180007580
0x180007529  mov     rcx, [rsp+278h]; this
0x180007531  lea     r8, aWil; "wil"
0x180007538  mov     r9d, eax; char *
0x18000753b  mov     edx, 8Bh; void *
0x180007540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007545  mov     eax, edi
0x180007547  jmp     loc_18000761E
0x18000754c  call    cs:__imp_GetLastError
0x180007552  mov     rdi, [rbx]
0x180007555  test    rdi, rdi
0x180007558  jz      short loc_18000757D
0x18000755a  call    cs:__imp_GetLastError
0x180007560  mov     rcx, rdi; hObject
0x180007563  mov     r14d, eax
0x180007566  call    cs:__imp_CloseHandle
0x18000756c  test    eax, eax
0x18000756e  jz      loc_18000766A
0x180007574  mov     ecx, r14d; dwErrCode
0x180007577  call    cs:__imp_SetLastError
0x18000757d  mov     [rbx], r15
0x180007580  lea     r8, asc_18012C4E0; "h"
0x180007587  shr     rbp, 1Fh
0x18000758b  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180007590  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007595  test    ebp, ebp
0x180007597  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000759f  lea     r9, [rsp+278h+Name]; lpName
0x1800075a4  mov     [rsp+278h+dwFlags], r12d; int
0x1800075a9  cmovnz  esi, ebp
0x1800075ac  mov     edx, ebp; lInitialCount
0x1800075ae  mov     r8d, esi; lMaximumCount
0x1800075b1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800075b3  call    cs:__imp_CreateSemaphoreExW
0x1800075b9  mov     rsi, rax
0x1800075bc  test    rax, rax
0x1800075bf  jnz     short loc_1800075EC
0x1800075c1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800075c6  mov     ebx, eax
0x1800075c8  test    eax, eax
0x1800075ca  jns     short loc_18000761C
0x1800075cc  mov     rcx, [rsp+278h]; this
0x1800075d4  lea     r8, aWil; "wil"
0x1800075db  mov     r9d, eax; char *
0x1800075de  mov     edx, 90h; void *
0x1800075e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075e8  mov     eax, ebx
0x1800075ea  jmp     short loc_18000761E
0x1800075ec  call    cs:__imp_GetLastError
0x1800075f2  mov     rdi, [rbx+8]
0x1800075f6  test    rdi, rdi
0x1800075f9  jz      short loc_180007618
0x1800075fb  call    cs:__imp_GetLastError
0x180007601  mov     rcx, rdi; hObject
0x180007604  mov     ebp, eax
0x180007606  call    cs:__imp_CloseHandle
0x18000760c  test    eax, eax
0x18000760e  jz      short loc_18000764A
0x180007610  mov     ecx, ebp; dwErrCode
0x180007612  call    cs:__imp_SetLastError
0x180007618  mov     [rbx+8], rsi
0x18000761c  xor     eax, eax
0x18000761e  mov     rcx, [rsp+278h+var_38]
0x180007626  xor     rcx, rsp; StackCookie
0x180007629  call    __security_check_cookie
0x18000762e  lea     r11, [rsp+278h+var_28]
0x180007636  mov     rbx, [r11+38h]
0x18000763a  mov     rbp, [r11+40h]
0x18000763e  mov     rsp, r11
0x180007641  pop     r15
0x180007643  pop     r14
0x180007645  pop     r12
0x180007647  pop     rdi
0x180007648  pop     rsi
0x180007649  retn
0x18000764a  mov     rcx, [rsp+278h]; this
0x180007652  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007659  mov     edx, 0A0Bh; void *
0x18000765e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007664  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000766a  mov     rcx, [rsp+278h]; this
0x180007672  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007679  mov     edx, 0A0Bh; void *
0x18000767e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
