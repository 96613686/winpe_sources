# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800e73e8`
- end: `0x1800e7612`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800e6c08`
- `0x1800e6fe4`

## callees

- `0x180003060`
- `0x1800e73e8`
- `0x1800e82b8`
- `0x1800eabf4`
- `0x1800eb644`
- `0x1800ec608`
- `0x1800ec618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800e74ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800e754f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800e74ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800e754f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e7513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e75ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e7513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e75ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e74e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e74f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e74e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e74f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e75a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e75a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800e73e8  mov     [rsp+arg_8], rbx
0x1800e73ed  mov     [rsp+arg_10], rbp
0x1800e73f2  push    rsi
0x1800e73f3  push    rdi
0x1800e73f4  push    r12
0x1800e73f6  push    r14
0x1800e73f8  push    r15
0x1800e73fa  sub     rsp, 250h
0x1800e7401  mov     rax, cs:__security_cookie
0x1800e7408  xor     rax, rsp
0x1800e740b  mov     [rsp+278h+var_38], rax
0x1800e7413  mov     rax, 0C000000000000000h
0x1800e741d  mov     rbp, r9
0x1800e7420  mov     r8, rdx
0x1800e7423  mov     rbx, rcx
0x1800e7426  test    rax, r9
0x1800e7429  jnz     loc_1800E75F9
0x1800e742f  xor     r12d, r12d
0x1800e7432  lea     rax, [rsp+278h+Name]
0x1800e7437  mov     ecx, 7FFFFFFEh
0x1800e743c  mov     edx, 104h
0x1800e7441  lea     esi, [r12+1]
0x1800e7446  test    rcx, rcx
0x1800e7449  jz      short loc_1800E7469
0x1800e744b  movzx   r9d, word ptr [r8]
0x1800e744f  test    r9w, r9w
0x1800e7453  jz      short loc_1800E7469
0x1800e7455  mov     [rax], r9w
0x1800e7459  add     r8, 2
0x1800e745d  add     rax, 2
0x1800e7461  sub     rcx, rsi
0x1800e7464  sub     rdx, rsi; unsigned __int64
0x1800e7467  jnz     short loc_1800E7446
0x1800e7469  test    rdx, rdx
0x1800e746c  lea     rcx, [rax-2]
0x1800e7470  lea     r8, aP0; "_p0"
0x1800e7477  cmovnz  rcx, rax
0x1800e747b  mov     [rcx], r12w
0x1800e747f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800e7484  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e7489  mov     edx, ebp
0x1800e748b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800e7493  and     edx, 7FFFFFFFh; lInitialCount
0x1800e7499  mov     [rsp+278h+dwFlags], r12d; int
0x1800e749e  mov     r8d, esi
0x1800e74a1  lea     r9, [rsp+278h+Name]; lpName
0x1800e74a6  cmova   r8d, edx; lMaximumCount
0x1800e74aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800e74ac  call    cs:__imp_CreateSemaphoreExW
0x1800e74b2  mov     r15, rax
0x1800e74b5  test    rax, rax
0x1800e74b8  jnz     short loc_1800E74E8
0x1800e74ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e74bf  mov     edi, eax
0x1800e74c1  test    eax, eax
0x1800e74c3  jns     short loc_1800E751C
0x1800e74c5  mov     rcx, [rsp+278h]; this
0x1800e74cd  lea     r8, aWil; "wil"
0x1800e74d4  mov     r9d, eax; char *
0x1800e74d7  mov     edx, 8Bh; void *
0x1800e74dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e74e1  mov     eax, edi
0x1800e74e3  jmp     loc_1800E75BA
0x1800e74e8  call    cs:__imp_GetLastError
0x1800e74ee  mov     rdi, [rbx]
0x1800e74f1  test    rdi, rdi
0x1800e74f4  jz      short loc_1800E7519
0x1800e74f6  call    cs:__imp_GetLastError
0x1800e74fc  mov     rcx, rdi; hObject
0x1800e74ff  mov     r14d, eax
0x1800e7502  call    cs:__imp_CloseHandle
0x1800e7508  test    eax, eax
0x1800e750a  jz      loc_1800E75FF
0x1800e7510  mov     ecx, r14d; dwErrCode
0x1800e7513  call    cs:__imp_SetLastError
0x1800e7519  mov     [rbx], r15
0x1800e751c  lea     r8, asc_1801223E0; "h"
0x1800e7523  shr     rbp, 1Fh
0x1800e7527  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800e752c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e7531  test    ebp, ebp
0x1800e7533  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800e753b  lea     r9, [rsp+278h+Name]; lpName
0x1800e7540  mov     [rsp+278h+dwFlags], r12d; int
0x1800e7545  cmovnz  esi, ebp
0x1800e7548  mov     edx, ebp; lInitialCount
0x1800e754a  mov     r8d, esi; lMaximumCount
0x1800e754d  xor     ecx, ecx; lpSemaphoreAttributes
0x1800e754f  call    cs:__imp_CreateSemaphoreExW
0x1800e7555  mov     rsi, rax
0x1800e7558  test    rax, rax
0x1800e755b  jnz     short loc_1800E7588
0x1800e755d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e7562  mov     ebx, eax
0x1800e7564  test    eax, eax
0x1800e7566  jns     short loc_1800E75B8
0x1800e7568  mov     rcx, [rsp+278h]; this
0x1800e7570  lea     r8, aWil; "wil"
0x1800e7577  mov     r9d, eax; char *
0x1800e757a  mov     edx, 90h; void *
0x1800e757f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7584  mov     eax, ebx
0x1800e7586  jmp     short loc_1800E75BA
0x1800e7588  call    cs:__imp_GetLastError
0x1800e758e  mov     rdi, [rbx+8]
0x1800e7592  test    rdi, rdi
0x1800e7595  jz      short loc_1800E75B4
0x1800e7597  call    cs:__imp_GetLastError
0x1800e759d  mov     rcx, rdi; hObject
0x1800e75a0  mov     ebp, eax
0x1800e75a2  call    cs:__imp_CloseHandle
0x1800e75a8  test    eax, eax
0x1800e75aa  jz      short loc_1800E75E6
0x1800e75ac  mov     ecx, ebp; dwErrCode
0x1800e75ae  call    cs:__imp_SetLastError
0x1800e75b4  mov     [rbx+8], rsi
0x1800e75b8  xor     eax, eax
0x1800e75ba  mov     rcx, [rsp+278h+var_38]
0x1800e75c2  xor     rcx, rsp; StackCookie
0x1800e75c5  call    __security_check_cookie
0x1800e75ca  lea     r11, [rsp+278h+var_28]
0x1800e75d2  mov     rbx, [r11+38h]
0x1800e75d6  mov     rbp, [r11+40h]
0x1800e75da  mov     rsp, r11
0x1800e75dd  pop     r15
0x1800e75df  pop     r14
0x1800e75e1  pop     r12
0x1800e75e3  pop     rdi
0x1800e75e4  pop     rsi
0x1800e75e5  retn
0x1800e75e6  mov     rcx, [rsp+278h]; this
0x1800e75ee  mov     edx, 0A0Bh; void *
0x1800e75f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e75f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800e75ff  mov     rcx, [rsp+278h]; this
0x1800e7607  mov     edx, 0A0Bh; void *
0x1800e760c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
