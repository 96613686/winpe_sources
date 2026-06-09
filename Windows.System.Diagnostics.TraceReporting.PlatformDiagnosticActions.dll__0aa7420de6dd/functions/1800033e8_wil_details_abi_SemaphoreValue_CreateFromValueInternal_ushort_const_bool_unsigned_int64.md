# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800033e8`
- end: `0x180003612`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003018`

## callees

- `0x1800016a0`
- `0x1800033e8`
- `0x180003c78`
- `0x180004bc4`
- `0x1800054a0`
- `0x1800059cc`
- `0x1800059dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800034ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000354f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800034ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000354f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035a2`

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
0x1800033e8  mov     [rsp+arg_8], rbx
0x1800033ed  mov     [rsp+arg_10], rbp
0x1800033f2  push    rsi
0x1800033f3  push    rdi
0x1800033f4  push    r12
0x1800033f6  push    r14
0x1800033f8  push    r15
0x1800033fa  sub     rsp, 250h
0x180003401  mov     rax, cs:__security_cookie
0x180003408  xor     rax, rsp
0x18000340b  mov     [rsp+278h+var_38], rax
0x180003413  mov     rax, 0C000000000000000h
0x18000341d  mov     rbp, r9
0x180003420  mov     r8, rdx
0x180003423  mov     rbx, rcx
0x180003426  test    rax, r9
0x180003429  jnz     loc_1800035F9
0x18000342f  xor     r12d, r12d
0x180003432  lea     rax, [rsp+278h+Name]
0x180003437  mov     ecx, 7FFFFFFEh
0x18000343c  mov     edx, 104h
0x180003441  lea     esi, [r12+1]
0x180003446  test    rcx, rcx
0x180003449  jz      short loc_180003469
0x18000344b  movzx   r9d, word ptr [r8]
0x18000344f  test    r9w, r9w
0x180003453  jz      short loc_180003469
0x180003455  mov     [rax], r9w
0x180003459  add     r8, 2
0x18000345d  add     rax, 2
0x180003461  sub     rcx, rsi
0x180003464  sub     rdx, rsi; unsigned __int64
0x180003467  jnz     short loc_180003446
0x180003469  test    rdx, rdx
0x18000346c  lea     rcx, [rax-2]
0x180003470  lea     r8, aP0; "_p0"
0x180003477  cmovnz  rcx, rax
0x18000347b  mov     [rcx], r12w
0x18000347f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003484  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003489  mov     edx, ebp
0x18000348b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003493  and     edx, 7FFFFFFFh; lInitialCount
0x180003499  mov     [rsp+278h+dwFlags], r12d; int
0x18000349e  mov     r8d, esi
0x1800034a1  lea     r9, [rsp+278h+Name]; lpName
0x1800034a6  cmova   r8d, edx; lMaximumCount
0x1800034aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800034ac  call    cs:__imp_CreateSemaphoreExW
0x1800034b2  mov     r15, rax
0x1800034b5  test    rax, rax
0x1800034b8  jnz     short loc_1800034E8
0x1800034ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800034bf  mov     edi, eax
0x1800034c1  test    eax, eax
0x1800034c3  jns     short loc_18000351C
0x1800034c5  mov     rcx, [rsp+278h]; this
0x1800034cd  lea     r8, aWil; "wil"
0x1800034d4  mov     r9d, eax; char *
0x1800034d7  mov     edx, 8Bh; void *
0x1800034dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800034e1  mov     eax, edi
0x1800034e3  jmp     loc_1800035BA
0x1800034e8  call    cs:__imp_GetLastError
0x1800034ee  mov     rdi, [rbx]
0x1800034f1  test    rdi, rdi
0x1800034f4  jz      short loc_180003519
0x1800034f6  call    cs:__imp_GetLastError
0x1800034fc  mov     rcx, rdi; hObject
0x1800034ff  mov     r14d, eax
0x180003502  call    cs:__imp_CloseHandle
0x180003508  test    eax, eax
0x18000350a  jz      loc_1800035FF
0x180003510  mov     ecx, r14d; dwErrCode
0x180003513  call    cs:__imp_SetLastError
0x180003519  mov     [rbx], r15
0x18000351c  lea     r8, asc_18000FBA8; "h"
0x180003523  shr     rbp, 1Fh
0x180003527  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000352c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003531  test    ebp, ebp
0x180003533  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000353b  lea     r9, [rsp+278h+Name]; lpName
0x180003540  mov     [rsp+278h+dwFlags], r12d; int
0x180003545  cmovnz  esi, ebp
0x180003548  mov     edx, ebp; lInitialCount
0x18000354a  mov     r8d, esi; lMaximumCount
0x18000354d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000354f  call    cs:__imp_CreateSemaphoreExW
0x180003555  mov     rsi, rax
0x180003558  test    rax, rax
0x18000355b  jnz     short loc_180003588
0x18000355d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003562  mov     ebx, eax
0x180003564  test    eax, eax
0x180003566  jns     short loc_1800035B8
0x180003568  mov     rcx, [rsp+278h]; this
0x180003570  lea     r8, aWil; "wil"
0x180003577  mov     r9d, eax; char *
0x18000357a  mov     edx, 90h; void *
0x18000357f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003584  mov     eax, ebx
0x180003586  jmp     short loc_1800035BA
0x180003588  call    cs:__imp_GetLastError
0x18000358e  mov     rdi, [rbx+8]
0x180003592  test    rdi, rdi
0x180003595  jz      short loc_1800035B4
0x180003597  call    cs:__imp_GetLastError
0x18000359d  mov     rcx, rdi; hObject
0x1800035a0  mov     ebp, eax
0x1800035a2  call    cs:__imp_CloseHandle
0x1800035a8  test    eax, eax
0x1800035aa  jz      short loc_1800035E6
0x1800035ac  mov     ecx, ebp; dwErrCode
0x1800035ae  call    cs:__imp_SetLastError
0x1800035b4  mov     [rbx+8], rsi
0x1800035b8  xor     eax, eax
0x1800035ba  mov     rcx, [rsp+278h+var_38]
0x1800035c2  xor     rcx, rsp; StackCookie
0x1800035c5  call    __security_check_cookie
0x1800035ca  lea     r11, [rsp+278h+var_28]
0x1800035d2  mov     rbx, [r11+38h]
0x1800035d6  mov     rbp, [r11+40h]
0x1800035da  mov     rsp, r11
0x1800035dd  pop     r15
0x1800035df  pop     r14
0x1800035e1  pop     r12
0x1800035e3  pop     rdi
0x1800035e4  pop     rsi
0x1800035e5  retn
0x1800035e6  mov     rcx, [rsp+278h]; this
0x1800035ee  mov     edx, 0A0Bh; void *
0x1800035f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800035f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800035ff  mov     rcx, [rsp+278h]; this
0x180003607  mov     edx, 0A0Bh; void *
0x18000360c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
