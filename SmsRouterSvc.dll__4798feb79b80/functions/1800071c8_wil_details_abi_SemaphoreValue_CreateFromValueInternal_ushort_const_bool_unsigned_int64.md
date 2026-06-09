# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800071c8`
- end: `0x1800073f2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006df8`
- `0x180039194`

## callees

- `0x180003a60`
- `0x1800071c8`
- `0x180007b18`
- `0x1800089e4`
- `0x180009324`
- `0x18000986c`
- `0x18000987c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000732f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000732f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000738e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000738e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007382`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x1800071c8  mov     [rsp+arg_8], rbx
0x1800071cd  mov     [rsp+arg_10], rbp
0x1800071d2  push    rsi
0x1800071d3  push    rdi
0x1800071d4  push    r12
0x1800071d6  push    r14
0x1800071d8  push    r15
0x1800071da  sub     rsp, 250h
0x1800071e1  mov     rax, cs:__security_cookie
0x1800071e8  xor     rax, rsp
0x1800071eb  mov     [rsp+278h+var_38], rax
0x1800071f3  mov     rax, 0C000000000000000h
0x1800071fd  mov     rbp, r9
0x180007200  mov     r8, rdx
0x180007203  mov     rbx, rcx
0x180007206  test    rax, r9
0x180007209  jnz     loc_1800073D9
0x18000720f  xor     r12d, r12d
0x180007212  lea     rax, [rsp+278h+Name]
0x180007217  mov     ecx, 7FFFFFFEh
0x18000721c  mov     edx, 104h
0x180007221  lea     esi, [r12+1]
0x180007226  test    rcx, rcx
0x180007229  jz      short loc_180007249
0x18000722b  movzx   r9d, word ptr [r8]
0x18000722f  test    r9w, r9w
0x180007233  jz      short loc_180007249
0x180007235  mov     [rax], r9w
0x180007239  add     r8, 2
0x18000723d  add     rax, 2
0x180007241  sub     rcx, rsi
0x180007244  sub     rdx, rsi; unsigned __int64
0x180007247  jnz     short loc_180007226
0x180007249  test    rdx, rdx
0x18000724c  lea     rcx, [rax-2]
0x180007250  lea     r8, aP0; "_p0"
0x180007257  cmovnz  rcx, rax
0x18000725b  mov     [rcx], r12w
0x18000725f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007264  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007269  mov     edx, ebp
0x18000726b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007273  and     edx, 7FFFFFFFh; lInitialCount
0x180007279  mov     [rsp+278h+dwFlags], r12d; int
0x18000727e  mov     r8d, esi
0x180007281  lea     r9, [rsp+278h+Name]; lpName
0x180007286  cmova   r8d, edx; lMaximumCount
0x18000728a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000728c  call    cs:__imp_CreateSemaphoreExW
0x180007292  mov     r15, rax
0x180007295  test    rax, rax
0x180007298  jnz     short loc_1800072C8
0x18000729a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000729f  mov     edi, eax
0x1800072a1  test    eax, eax
0x1800072a3  jns     short loc_1800072FC
0x1800072a5  mov     rcx, [rsp+278h]; this
0x1800072ad  lea     r8, aWil; "wil"
0x1800072b4  mov     r9d, eax; char *
0x1800072b7  mov     edx, 8Bh; void *
0x1800072bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072c1  mov     eax, edi
0x1800072c3  jmp     loc_18000739A
0x1800072c8  call    cs:__imp_GetLastError
0x1800072ce  mov     rdi, [rbx]
0x1800072d1  test    rdi, rdi
0x1800072d4  jz      short loc_1800072F9
0x1800072d6  call    cs:__imp_GetLastError
0x1800072dc  mov     rcx, rdi; hObject
0x1800072df  mov     r14d, eax
0x1800072e2  call    cs:__imp_CloseHandle
0x1800072e8  test    eax, eax
0x1800072ea  jz      loc_1800073DF
0x1800072f0  mov     ecx, r14d; dwErrCode
0x1800072f3  call    cs:__imp_SetLastError
0x1800072f9  mov     [rbx], r15
0x1800072fc  lea     r8, asc_180073990; "h"
0x180007303  shr     rbp, 1Fh
0x180007307  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000730c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007311  test    ebp, ebp
0x180007313  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000731b  lea     r9, [rsp+278h+Name]; lpName
0x180007320  mov     [rsp+278h+dwFlags], r12d; int
0x180007325  cmovnz  esi, ebp
0x180007328  mov     edx, ebp; lInitialCount
0x18000732a  mov     r8d, esi; lMaximumCount
0x18000732d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000732f  call    cs:__imp_CreateSemaphoreExW
0x180007335  mov     rsi, rax
0x180007338  test    rax, rax
0x18000733b  jnz     short loc_180007368
0x18000733d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007342  mov     ebx, eax
0x180007344  test    eax, eax
0x180007346  jns     short loc_180007398
0x180007348  mov     rcx, [rsp+278h]; this
0x180007350  lea     r8, aWil; "wil"
0x180007357  mov     r9d, eax; char *
0x18000735a  mov     edx, 90h; void *
0x18000735f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007364  mov     eax, ebx
0x180007366  jmp     short loc_18000739A
0x180007368  call    cs:__imp_GetLastError
0x18000736e  mov     rdi, [rbx+8]
0x180007372  test    rdi, rdi
0x180007375  jz      short loc_180007394
0x180007377  call    cs:__imp_GetLastError
0x18000737d  mov     rcx, rdi; hObject
0x180007380  mov     ebp, eax
0x180007382  call    cs:__imp_CloseHandle
0x180007388  test    eax, eax
0x18000738a  jz      short loc_1800073C6
0x18000738c  mov     ecx, ebp; dwErrCode
0x18000738e  call    cs:__imp_SetLastError
0x180007394  mov     [rbx+8], rsi
0x180007398  xor     eax, eax
0x18000739a  mov     rcx, [rsp+278h+var_38]
0x1800073a2  xor     rcx, rsp; StackCookie
0x1800073a5  call    __security_check_cookie
0x1800073aa  lea     r11, [rsp+278h+var_28]
0x1800073b2  mov     rbx, [r11+38h]
0x1800073b6  mov     rbp, [r11+40h]
0x1800073ba  mov     rsp, r11
0x1800073bd  pop     r15
0x1800073bf  pop     r14
0x1800073c1  pop     r12
0x1800073c3  pop     rdi
0x1800073c4  pop     rsi
0x1800073c5  retn
0x1800073c6  mov     rcx, [rsp+278h]; this
0x1800073ce  mov     edx, 0A0Bh; void *
0x1800073d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073d9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800073df  mov     rcx, [rsp+278h]; this
0x1800073e7  mov     edx, 0A0Bh; void *
0x1800073ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
