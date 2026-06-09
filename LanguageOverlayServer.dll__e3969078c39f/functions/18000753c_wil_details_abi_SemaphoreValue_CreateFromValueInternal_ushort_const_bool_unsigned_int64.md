# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000753c`
- end: `0x180007774`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007168`
- `0x18000cbb8`

## callees

- `0x180003a00`
- `0x18000753c`
- `0x180007ed8`
- `0x180009084`
- `0x1800099c4`
- `0x180009ff8`
- `0x18000a008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800076a3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800076a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007702`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f6`

## string_xrefs

- `0x180007742`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007762`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000753c  mov     [rsp+arg_8], rbx
0x180007541  mov     [rsp+arg_10], rbp
0x180007546  push    rsi
0x180007547  push    rdi
0x180007548  push    r12
0x18000754a  push    r14
0x18000754c  push    r15
0x18000754e  sub     rsp, 250h
0x180007555  mov     rax, cs:__security_cookie
0x18000755c  xor     rax, rsp
0x18000755f  mov     [rsp+278h+var_38], rax
0x180007567  mov     rax, 0C000000000000000h
0x180007571  mov     rbp, r9
0x180007574  mov     r8, rdx
0x180007577  mov     rbx, rcx
0x18000757a  test    rax, r9
0x18000757d  jnz     loc_180007754
0x180007583  xor     r12d, r12d
0x180007586  lea     rax, [rsp+278h+Name]
0x18000758b  mov     ecx, 7FFFFFFEh
0x180007590  mov     edx, 104h
0x180007595  lea     esi, [r12+1]
0x18000759a  test    rcx, rcx
0x18000759d  jz      short loc_1800075BD
0x18000759f  movzx   r9d, word ptr [r8]
0x1800075a3  test    r9w, r9w
0x1800075a7  jz      short loc_1800075BD
0x1800075a9  mov     [rax], r9w
0x1800075ad  add     r8, 2
0x1800075b1  add     rax, 2
0x1800075b5  sub     rcx, rsi
0x1800075b8  sub     rdx, rsi; unsigned __int64
0x1800075bb  jnz     short loc_18000759A
0x1800075bd  test    rdx, rdx
0x1800075c0  lea     rcx, [rax-2]
0x1800075c4  lea     r8, aP0; "_p0"
0x1800075cb  cmovnz  rcx, rax
0x1800075cf  mov     [rcx], r12w
0x1800075d3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800075d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800075dd  mov     edx, ebp
0x1800075df  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800075e7  and     edx, 7FFFFFFFh; lInitialCount
0x1800075ed  mov     [rsp+278h+dwFlags], r12d; int
0x1800075f2  mov     r8d, esi
0x1800075f5  lea     r9, [rsp+278h+Name]; lpName
0x1800075fa  cmova   r8d, edx; lMaximumCount
0x1800075fe  xor     ecx, ecx; lpSemaphoreAttributes
0x180007600  call    cs:__imp_CreateSemaphoreExW
0x180007606  mov     r15, rax
0x180007609  test    rax, rax
0x18000760c  jnz     short loc_18000763C
0x18000760e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007613  mov     edi, eax
0x180007615  test    eax, eax
0x180007617  jns     short loc_180007670
0x180007619  mov     rcx, [rsp+278h]; this
0x180007621  lea     r8, aWil; "wil"
0x180007628  mov     r9d, eax; char *
0x18000762b  mov     edx, 8Bh; void *
0x180007630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007635  mov     eax, edi
0x180007637  jmp     loc_18000770E
0x18000763c  call    cs:__imp_GetLastError
0x180007642  mov     rdi, [rbx]
0x180007645  test    rdi, rdi
0x180007648  jz      short loc_18000766D
0x18000764a  call    cs:__imp_GetLastError
0x180007650  mov     rcx, rdi; hObject
0x180007653  mov     r14d, eax
0x180007656  call    cs:__imp_CloseHandle
0x18000765c  test    eax, eax
0x18000765e  jz      loc_18000775A
0x180007664  mov     ecx, r14d; dwErrCode
0x180007667  call    cs:__imp_SetLastError
0x18000766d  mov     [rbx], r15
0x180007670  lea     r8, asc_180070378; "h"
0x180007677  shr     rbp, 1Fh
0x18000767b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007680  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007685  test    ebp, ebp
0x180007687  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000768f  lea     r9, [rsp+278h+Name]; lpName
0x180007694  mov     [rsp+278h+dwFlags], r12d; int
0x180007699  cmovnz  esi, ebp
0x18000769c  mov     edx, ebp; lInitialCount
0x18000769e  mov     r8d, esi; lMaximumCount
0x1800076a1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800076a3  call    cs:__imp_CreateSemaphoreExW
0x1800076a9  mov     rsi, rax
0x1800076ac  test    rax, rax
0x1800076af  jnz     short loc_1800076DC
0x1800076b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800076b6  mov     ebx, eax
0x1800076b8  test    eax, eax
0x1800076ba  jns     short loc_18000770C
0x1800076bc  mov     rcx, [rsp+278h]; this
0x1800076c4  lea     r8, aWil; "wil"
0x1800076cb  mov     r9d, eax; char *
0x1800076ce  mov     edx, 90h; void *
0x1800076d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076d8  mov     eax, ebx
0x1800076da  jmp     short loc_18000770E
0x1800076dc  call    cs:__imp_GetLastError
0x1800076e2  mov     rdi, [rbx+8]
0x1800076e6  test    rdi, rdi
0x1800076e9  jz      short loc_180007708
0x1800076eb  call    cs:__imp_GetLastError
0x1800076f1  mov     rcx, rdi; hObject
0x1800076f4  mov     ebp, eax
0x1800076f6  call    cs:__imp_CloseHandle
0x1800076fc  test    eax, eax
0x1800076fe  jz      short loc_18000773A
0x180007700  mov     ecx, ebp; dwErrCode
0x180007702  call    cs:__imp_SetLastError
0x180007708  mov     [rbx+8], rsi
0x18000770c  xor     eax, eax
0x18000770e  mov     rcx, [rsp+278h+var_38]
0x180007716  xor     rcx, rsp; StackCookie
0x180007719  call    __security_check_cookie
0x18000771e  lea     r11, [rsp+278h+var_28]
0x180007726  mov     rbx, [r11+38h]
0x18000772a  mov     rbp, [r11+40h]
0x18000772e  mov     rsp, r11
0x180007731  pop     r15
0x180007733  pop     r14
0x180007735  pop     r12
0x180007737  pop     rdi
0x180007738  pop     rsi
0x180007739  retn
0x18000773a  mov     rcx, [rsp+278h]; this
0x180007742  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007749  mov     edx, 0A0Bh; void *
0x18000774e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007754  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000775a  mov     rcx, [rsp+278h]; this
0x180007762  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007769  mov     edx, 0A0Bh; void *
0x18000776e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
