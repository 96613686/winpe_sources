# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000438c`
- end: `0x1800045b6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bc4`
- `0x180003f94`

## callees

- `0x180001ac0`
- `0x18000438c`
- `0x1800051f8`
- `0x180007434`
- `0x18000784c`
- `0x1800086ec`
- `0x1800086fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004450`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044f3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004450`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004552`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000448c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000449a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000448c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000449a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004546`

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
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
  const char *v31; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
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
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000438c  mov     [rsp+arg_8], rbx
0x180004391  mov     [rsp+arg_10], rbp
0x180004396  push    rsi
0x180004397  push    rdi
0x180004398  push    r12
0x18000439a  push    r14
0x18000439c  push    r15
0x18000439e  sub     rsp, 250h
0x1800043a5  mov     rax, cs:__security_cookie
0x1800043ac  xor     rax, rsp
0x1800043af  mov     [rsp+278h+var_38], rax
0x1800043b7  mov     rax, 0C000000000000000h
0x1800043c1  mov     rbp, r9
0x1800043c4  mov     r8, rdx
0x1800043c7  mov     rbx, rcx
0x1800043ca  test    rax, r9
0x1800043cd  jnz     loc_18000459D
0x1800043d3  xor     r12d, r12d
0x1800043d6  lea     rax, [rsp+278h+Name]
0x1800043db  mov     ecx, 7FFFFFFEh
0x1800043e0  mov     edx, 104h
0x1800043e5  lea     esi, [r12+1]
0x1800043ea  test    rcx, rcx
0x1800043ed  jz      short loc_18000440D
0x1800043ef  movzx   r9d, word ptr [r8]
0x1800043f3  test    r9w, r9w
0x1800043f7  jz      short loc_18000440D
0x1800043f9  mov     [rax], r9w
0x1800043fd  add     r8, 2
0x180004401  add     rax, 2
0x180004405  sub     rcx, rsi
0x180004408  sub     rdx, rsi; unsigned __int64
0x18000440b  jnz     short loc_1800043EA
0x18000440d  test    rdx, rdx
0x180004410  lea     rcx, [rax-2]
0x180004414  lea     r8, aP0; "_p0"
0x18000441b  cmovnz  rcx, rax
0x18000441f  mov     [rcx], r12w
0x180004423  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004428  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000442d  mov     edx, ebp
0x18000442f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004437  and     edx, 7FFFFFFFh; lInitialCount
0x18000443d  mov     [rsp+278h+dwFlags], r12d; int
0x180004442  mov     r8d, esi
0x180004445  lea     r9, [rsp+278h+Name]; lpName
0x18000444a  cmova   r8d, edx; lMaximumCount
0x18000444e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004450  call    cs:__imp_CreateSemaphoreExW
0x180004456  mov     r15, rax
0x180004459  test    rax, rax
0x18000445c  jnz     short loc_18000448C
0x18000445e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004463  mov     edi, eax
0x180004465  test    eax, eax
0x180004467  jns     short loc_1800044C0
0x180004469  mov     rcx, [rsp+278h]; this
0x180004471  lea     r8, aWil; "wil"
0x180004478  mov     r9d, eax; char *
0x18000447b  mov     edx, 8Bh; void *
0x180004480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004485  mov     eax, edi
0x180004487  jmp     loc_18000455E
0x18000448c  call    cs:__imp_GetLastError
0x180004492  mov     rdi, [rbx]
0x180004495  test    rdi, rdi
0x180004498  jz      short loc_1800044BD
0x18000449a  call    cs:__imp_GetLastError
0x1800044a0  mov     rcx, rdi; hObject
0x1800044a3  mov     r14d, eax
0x1800044a6  call    cs:__imp_CloseHandle
0x1800044ac  test    eax, eax
0x1800044ae  jz      loc_1800045A3
0x1800044b4  mov     ecx, r14d; dwErrCode
0x1800044b7  call    cs:__imp_SetLastError
0x1800044bd  mov     [rbx], r15
0x1800044c0  lea     r8, asc_180026CE0; "h"
0x1800044c7  shr     rbp, 1Fh
0x1800044cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800044d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800044d5  test    ebp, ebp
0x1800044d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800044df  lea     r9, [rsp+278h+Name]; lpName
0x1800044e4  mov     [rsp+278h+dwFlags], r12d; int
0x1800044e9  cmovnz  esi, ebp
0x1800044ec  mov     edx, ebp; lInitialCount
0x1800044ee  mov     r8d, esi; lMaximumCount
0x1800044f1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044f3  call    cs:__imp_CreateSemaphoreExW
0x1800044f9  mov     rsi, rax
0x1800044fc  test    rax, rax
0x1800044ff  jnz     short loc_18000452C
0x180004501  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004506  mov     ebx, eax
0x180004508  test    eax, eax
0x18000450a  jns     short loc_18000455C
0x18000450c  mov     rcx, [rsp+278h]; this
0x180004514  lea     r8, aWil; "wil"
0x18000451b  mov     r9d, eax; char *
0x18000451e  mov     edx, 90h; void *
0x180004523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004528  mov     eax, ebx
0x18000452a  jmp     short loc_18000455E
0x18000452c  call    cs:__imp_GetLastError
0x180004532  mov     rdi, [rbx+8]
0x180004536  test    rdi, rdi
0x180004539  jz      short loc_180004558
0x18000453b  call    cs:__imp_GetLastError
0x180004541  mov     rcx, rdi; hObject
0x180004544  mov     ebp, eax
0x180004546  call    cs:__imp_CloseHandle
0x18000454c  test    eax, eax
0x18000454e  jz      short loc_18000458A
0x180004550  mov     ecx, ebp; dwErrCode
0x180004552  call    cs:__imp_SetLastError
0x180004558  mov     [rbx+8], rsi
0x18000455c  xor     eax, eax
0x18000455e  mov     rcx, [rsp+278h+var_38]
0x180004566  xor     rcx, rsp; StackCookie
0x180004569  call    __security_check_cookie
0x18000456e  lea     r11, [rsp+278h+var_28]
0x180004576  mov     rbx, [r11+38h]
0x18000457a  mov     rbp, [r11+40h]
0x18000457e  mov     rsp, r11
0x180004581  pop     r15
0x180004583  pop     r14
0x180004585  pop     r12
0x180004587  pop     rdi
0x180004588  pop     rsi
0x180004589  retn
0x18000458a  mov     rcx, [rsp+278h]; this
0x180004592  mov     edx, 0A0Bh; void *
0x180004597  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000459d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800045a3  mov     rcx, [rsp+278h]; this
0x1800045ab  mov     edx, 0A0Bh; void *
0x1800045b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
