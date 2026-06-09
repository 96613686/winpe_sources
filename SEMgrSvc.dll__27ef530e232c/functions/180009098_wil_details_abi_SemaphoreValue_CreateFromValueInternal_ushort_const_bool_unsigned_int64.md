# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009098`
- end: `0x1800092c9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800088b8`
- `0x180008c94`

## callees

- `0x1800049a0`
- `0x180009098`
- `0x18000a0f8`
- `0x18000c964`
- `0x18000d3b4`
- `0x18000e4b8`
- `0x18000e4c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009161`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009207`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009161`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009266`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000925a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000925a`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
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
0x180009098  mov     [rsp+arg_8], rbx
0x18000909d  push    rbp
0x18000909e  push    rsi
0x18000909f  push    rdi
0x1800090a0  push    r12
0x1800090a2  push    r13
0x1800090a4  push    r14
0x1800090a6  push    r15
0x1800090a8  sub     rsp, 250h
0x1800090af  mov     rax, cs:__security_cookie
0x1800090b6  xor     rax, rsp
0x1800090b9  mov     [rsp+288h+var_48], rax
0x1800090c1  mov     rax, 0C000000000000000h
0x1800090cb  mov     rsi, r9
0x1800090ce  mov     r8, rdx
0x1800090d1  mov     rbx, rcx
0x1800090d4  test    rax, r9
0x1800090d7  jnz     loc_1800092B0
0x1800090dd  xor     r12d, r12d
0x1800090e0  lea     rax, [rsp+288h+Name]
0x1800090e5  mov     r13d, 104h
0x1800090eb  mov     ecx, 7FFFFFFEh
0x1800090f0  mov     edx, r13d
0x1800090f3  lea     ebp, [r12+1]
0x1800090f8  test    rcx, rcx
0x1800090fb  jz      short loc_18000911B
0x1800090fd  movzx   r9d, word ptr [r8]
0x180009101  test    r9w, r9w
0x180009105  jz      short loc_18000911B
0x180009107  mov     [rax], r9w
0x18000910b  add     r8, 2
0x18000910f  add     rax, 2
0x180009113  sub     rcx, rbp
0x180009116  sub     rdx, rbp
0x180009119  jnz     short loc_1800090F8
0x18000911b  test    rdx, rdx
0x18000911e  lea     rcx, [rax-2]
0x180009122  lea     r8, aP0; "_p0"
0x180009129  mov     rdx, r13; unsigned __int64
0x18000912c  cmovnz  rcx, rax
0x180009130  mov     [rcx], r12w
0x180009134  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180009139  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000913e  mov     edx, esi
0x180009140  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009148  and     edx, 7FFFFFFFh; lInitialCount
0x18000914e  mov     [rsp+288h+dwFlags], r12d; int
0x180009153  mov     r8d, ebp
0x180009156  lea     r9, [rsp+288h+Name]; lpName
0x18000915b  cmova   r8d, edx; lMaximumCount
0x18000915f  xor     ecx, ecx; lpSemaphoreAttributes
0x180009161  call    cs:__imp_CreateSemaphoreExW
0x180009167  mov     r15, rax
0x18000916a  test    rax, rax
0x18000916d  jnz     short loc_18000919D
0x18000916f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009174  mov     edi, eax
0x180009176  test    eax, eax
0x180009178  jns     short loc_1800091D1
0x18000917a  mov     rcx, [rsp+288h]; this
0x180009182  lea     r8, aWil; "wil"
0x180009189  mov     r9d, eax; char *
0x18000918c  mov     edx, 8Bh; void *
0x180009191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009196  mov     eax, edi
0x180009198  jmp     loc_180009272
0x18000919d  call    cs:__imp_GetLastError
0x1800091a3  mov     rdi, [rbx]
0x1800091a6  test    rdi, rdi
0x1800091a9  jz      short loc_1800091CE
0x1800091ab  call    cs:__imp_GetLastError
0x1800091b1  mov     rcx, rdi; hObject
0x1800091b4  mov     r14d, eax
0x1800091b7  call    cs:__imp_CloseHandle
0x1800091bd  test    eax, eax
0x1800091bf  jz      loc_1800092B6
0x1800091c5  mov     ecx, r14d; dwErrCode
0x1800091c8  call    cs:__imp_SetLastError
0x1800091ce  mov     [rbx], r15
0x1800091d1  lea     r8, asc_1800A5EC8; "h"
0x1800091d8  shr     rsi, 1Fh
0x1800091dc  mov     rdx, r13; unsigned __int64
0x1800091df  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800091e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800091e9  test    esi, esi
0x1800091eb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800091f3  lea     r9, [rsp+288h+Name]; lpName
0x1800091f8  mov     [rsp+288h+dwFlags], r12d; int
0x1800091fd  cmovnz  ebp, esi
0x180009200  mov     edx, esi; lInitialCount
0x180009202  mov     r8d, ebp; lMaximumCount
0x180009205  xor     ecx, ecx; lpSemaphoreAttributes
0x180009207  call    cs:__imp_CreateSemaphoreExW
0x18000920d  mov     rbp, rax
0x180009210  test    rax, rax
0x180009213  jnz     short loc_180009240
0x180009215  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000921a  mov     ebx, eax
0x18000921c  test    eax, eax
0x18000921e  jns     short loc_180009270
0x180009220  mov     rcx, [rsp+288h]; this
0x180009228  lea     r8, aWil; "wil"
0x18000922f  mov     r9d, eax; char *
0x180009232  mov     edx, 90h; void *
0x180009237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000923c  mov     eax, ebx
0x18000923e  jmp     short loc_180009272
0x180009240  call    cs:__imp_GetLastError
0x180009246  mov     rdi, [rbx+8]
0x18000924a  test    rdi, rdi
0x18000924d  jz      short loc_18000926C
0x18000924f  call    cs:__imp_GetLastError
0x180009255  mov     rcx, rdi; hObject
0x180009258  mov     esi, eax
0x18000925a  call    cs:__imp_CloseHandle
0x180009260  test    eax, eax
0x180009262  jz      short loc_18000929D
0x180009264  mov     ecx, esi; dwErrCode
0x180009266  call    cs:__imp_SetLastError
0x18000926c  mov     [rbx+8], rbp
0x180009270  xor     eax, eax
0x180009272  mov     rcx, [rsp+288h+var_48]
0x18000927a  xor     rcx, rsp; StackCookie
0x18000927d  call    __security_check_cookie
0x180009282  mov     rbx, [rsp+288h+arg_8]
0x18000928a  add     rsp, 250h
0x180009291  pop     r15
0x180009293  pop     r14
0x180009295  pop     r13
0x180009297  pop     r12
0x180009299  pop     rdi
0x18000929a  pop     rsi
0x18000929b  pop     rbp
0x18000929c  retn
0x18000929d  mov     rcx, [rsp+288h]; this
0x1800092a5  mov     edx, 0A0Bh; void *
0x1800092aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800092b6  mov     rcx, [rsp+288h]; this
0x1800092be  mov     edx, 0A0Bh; void *
0x1800092c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
