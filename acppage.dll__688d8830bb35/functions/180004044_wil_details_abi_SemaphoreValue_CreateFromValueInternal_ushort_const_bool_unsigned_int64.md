# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004044`
- end: `0x180004267`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038a8`
- `0x180003c4c`

## callees

- `0x180004044`
- `0x180005024`
- `0x180007274`
- `0x1800082c4`
- `0x1800082d4`
- `0x180008878`
- `0x180016280`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x18000410d`
- `KERNEL32!CreateSemaphoreExW` at `0x1800041ac`
- `KERNEL32!CreateSemaphoreExW` at `0x18000410d`
- `KERNEL32!CreateSemaphoreExW` at `0x1800041ac`
- `KERNEL32!SetLastError` at `0x18000416d`
- `KERNEL32!SetLastError` at `0x180004204`
- `KERNEL32!SetLastError` at `0x18000416d`
- `KERNEL32!SetLastError` at `0x180004204`
- `KERNEL32!GetLastError` at `0x180004142`
- `KERNEL32!GetLastError` at `0x180004150`
- `KERNEL32!GetLastError` at `0x1800041de`
- `KERNEL32!GetLastError` at `0x1800041ed`
- `KERNEL32!GetLastError` at `0x180004142`
- `KERNEL32!GetLastError` at `0x180004150`
- `KERNEL32!GetLastError` at `0x1800041de`
- `KERNEL32!GetLastError` at `0x1800041ed`
- `KERNEL32!CloseHandle` at `0x18000415c`
- `KERNEL32!CloseHandle` at `0x1800041f8`
- `KERNEL32!CloseHandle` at `0x18000415c`
- `KERNEL32!CloseHandle` at `0x1800041f8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // ebp
  wchar_t *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  unsigned int v31; // r8d
  const char *v32; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  wchar_t pszDest[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = pszDest;
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
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, pszDest, 0, 0x1F0003u);
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(pszDest, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, pszDest, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004044  mov     [rsp+arg_8], rbx
0x180004049  push    rbp
0x18000404a  push    rsi
0x18000404b  push    rdi
0x18000404c  push    r12
0x18000404e  push    r13
0x180004050  push    r14
0x180004052  push    r15
0x180004054  sub     rsp, 250h
0x18000405b  mov     rax, cs:__security_cookie
0x180004062  xor     rax, rsp
0x180004065  mov     [rsp+288h+var_48], rax
0x18000406d  mov     rax, 0C000000000000000h
0x180004077  mov     rsi, r9
0x18000407a  mov     r8, rdx
0x18000407d  mov     rbx, rcx
0x180004080  test    rax, r9
0x180004083  jnz     loc_18000424E
0x180004089  xor     r12d, r12d
0x18000408c  lea     rax, [rsp+288h+pszDest]
0x180004091  mov     r13d, 104h
0x180004097  mov     ecx, 7FFFFFFEh
0x18000409c  mov     edx, r13d
0x18000409f  lea     ebp, [r12+1]
0x1800040a4  test    rcx, rcx
0x1800040a7  jz      short loc_1800040C7
0x1800040a9  movzx   r9d, word ptr [r8]
0x1800040ad  test    r9w, r9w
0x1800040b1  jz      short loc_1800040C7
0x1800040b3  mov     [rax], r9w
0x1800040b7  add     r8, 2
0x1800040bb  add     rax, 2
0x1800040bf  sub     rcx, rbp
0x1800040c2  sub     rdx, rbp
0x1800040c5  jnz     short loc_1800040A4
0x1800040c7  test    rdx, rdx
0x1800040ca  lea     rcx, [rax-2]
0x1800040ce  lea     r8, aP0; "_p0"
0x1800040d5  mov     rdx, r13; cchDest
0x1800040d8  cmovnz  rcx, rax
0x1800040dc  mov     [rcx], r12w
0x1800040e0  lea     rcx, [rsp+288h+pszDest]; pszDest
0x1800040e5  call    StringCchCatW
0x1800040ea  mov     edx, esi
0x1800040ec  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800040f4  and     edx, 7FFFFFFFh; lInitialCount
0x1800040fa  mov     [rsp+288h+dwFlags], r12d; int
0x1800040ff  mov     r8d, ebp
0x180004102  lea     r9, [rsp+288h+pszDest]; lpName
0x180004107  cmova   r8d, edx; lMaximumCount
0x18000410b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000410d  call    cs:__imp_CreateSemaphoreExW
0x180004113  mov     r15, rax
0x180004116  test    rax, rax
0x180004119  jnz     short loc_180004142
0x18000411b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004120  mov     edi, eax
0x180004122  test    eax, eax
0x180004124  jns     short loc_180004176
0x180004126  mov     rcx, [rsp+288h]; this
0x18000412e  mov     r9d, eax; char *
0x180004131  mov     edx, 8Bh; void *
0x180004136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000413b  mov     eax, edi
0x18000413d  jmp     loc_180004210
0x180004142  call    cs:__imp_GetLastError
0x180004148  mov     rdi, [rbx]
0x18000414b  test    rdi, rdi
0x18000414e  jz      short loc_180004173
0x180004150  call    cs:__imp_GetLastError
0x180004156  mov     rcx, rdi; hObject
0x180004159  mov     r14d, eax
0x18000415c  call    cs:__imp_CloseHandle
0x180004162  test    eax, eax
0x180004164  jz      loc_180004254
0x18000416a  mov     ecx, r14d; dwErrCode
0x18000416d  call    cs:__imp_SetLastError
0x180004173  mov     [rbx], r15
0x180004176  lea     r8, asc_180019A28; "h"
0x18000417d  shr     rsi, 1Fh
0x180004181  mov     rdx, r13; cchDest
0x180004184  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180004189  call    StringCchCatW
0x18000418e  test    esi, esi
0x180004190  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004198  lea     r9, [rsp+288h+pszDest]; lpName
0x18000419d  mov     [rsp+288h+dwFlags], r12d; int
0x1800041a2  cmovnz  ebp, esi
0x1800041a5  mov     edx, esi; lInitialCount
0x1800041a7  mov     r8d, ebp; lMaximumCount
0x1800041aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800041ac  call    cs:__imp_CreateSemaphoreExW
0x1800041b2  mov     rbp, rax
0x1800041b5  test    rax, rax
0x1800041b8  jnz     short loc_1800041DE
0x1800041ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800041bf  mov     ebx, eax
0x1800041c1  test    eax, eax
0x1800041c3  jns     short loc_18000420E
0x1800041c5  mov     rcx, [rsp+288h]; this
0x1800041cd  mov     r9d, eax; char *
0x1800041d0  mov     edx, 90h; void *
0x1800041d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041da  mov     eax, ebx
0x1800041dc  jmp     short loc_180004210
0x1800041de  call    cs:__imp_GetLastError
0x1800041e4  mov     rdi, [rbx+8]
0x1800041e8  test    rdi, rdi
0x1800041eb  jz      short loc_18000420A
0x1800041ed  call    cs:__imp_GetLastError
0x1800041f3  mov     rcx, rdi; hObject
0x1800041f6  mov     esi, eax
0x1800041f8  call    cs:__imp_CloseHandle
0x1800041fe  test    eax, eax
0x180004200  jz      short loc_18000423B
0x180004202  mov     ecx, esi; dwErrCode
0x180004204  call    cs:__imp_SetLastError
0x18000420a  mov     [rbx+8], rbp
0x18000420e  xor     eax, eax
0x180004210  mov     rcx, [rsp+288h+var_48]
0x180004218  xor     rcx, rsp; StackCookie
0x18000421b  call    __security_check_cookie
0x180004220  mov     rbx, [rsp+288h+arg_8]
0x180004228  add     rsp, 250h
0x18000422f  pop     r15
0x180004231  pop     r14
0x180004233  pop     r13
0x180004235  pop     r12
0x180004237  pop     rdi
0x180004238  pop     rsi
0x180004239  pop     rbp
0x18000423a  retn
0x18000423b  mov     rcx, [rsp+288h]; this
0x180004243  mov     edx, 0A0Bh; void *
0x180004248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000424e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004254  mov     rcx, [rsp+288h]; this
0x18000425c  mov     edx, 0A0Bh; void *
0x180004261  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
