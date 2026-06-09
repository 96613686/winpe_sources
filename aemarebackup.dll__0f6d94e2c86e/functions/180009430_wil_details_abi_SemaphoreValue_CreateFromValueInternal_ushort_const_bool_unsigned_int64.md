# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009430`
- end: `0x18000965a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008c68`
- `0x180009038`

## callees

- `0x180004ea0`
- `0x180009430`
- `0x18000a2a8`
- `0x18000cac4`
- `0x18000d508`
- `0x18000e53c`
- `0x18000e54c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800094f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009597`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800094f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009597`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000955b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000955b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000953e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000953e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000954a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000954a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095ea`

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
0x180009430  mov     [rsp+arg_8], rbx
0x180009435  mov     [rsp+arg_10], rbp
0x18000943a  push    rsi
0x18000943b  push    rdi
0x18000943c  push    r12
0x18000943e  push    r14
0x180009440  push    r15
0x180009442  sub     rsp, 250h
0x180009449  mov     rax, cs:__security_cookie
0x180009450  xor     rax, rsp
0x180009453  mov     [rsp+278h+var_38], rax
0x18000945b  mov     rax, 0C000000000000000h
0x180009465  mov     rbp, r9
0x180009468  mov     r8, rdx
0x18000946b  mov     rbx, rcx
0x18000946e  test    rax, r9
0x180009471  jnz     loc_180009641
0x180009477  xor     r12d, r12d
0x18000947a  lea     rax, [rsp+278h+Name]
0x18000947f  mov     ecx, 7FFFFFFEh
0x180009484  mov     edx, 104h
0x180009489  lea     esi, [r12+1]
0x18000948e  test    rcx, rcx
0x180009491  jz      short loc_1800094B1
0x180009493  movzx   r9d, word ptr [r8]
0x180009497  test    r9w, r9w
0x18000949b  jz      short loc_1800094B1
0x18000949d  mov     [rax], r9w
0x1800094a1  add     r8, 2
0x1800094a5  add     rax, 2
0x1800094a9  sub     rcx, rsi
0x1800094ac  sub     rdx, rsi; unsigned __int64
0x1800094af  jnz     short loc_18000948E
0x1800094b1  test    rdx, rdx
0x1800094b4  lea     rcx, [rax-2]
0x1800094b8  lea     r8, aP0; "_p0"
0x1800094bf  cmovnz  rcx, rax
0x1800094c3  mov     [rcx], r12w
0x1800094c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800094cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800094d1  mov     edx, ebp
0x1800094d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800094db  and     edx, 7FFFFFFFh; lInitialCount
0x1800094e1  mov     [rsp+278h+dwFlags], r12d; int
0x1800094e6  mov     r8d, esi
0x1800094e9  lea     r9, [rsp+278h+Name]; lpName
0x1800094ee  cmova   r8d, edx; lMaximumCount
0x1800094f2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800094f4  call    cs:__imp_CreateSemaphoreExW
0x1800094fa  mov     r15, rax
0x1800094fd  test    rax, rax
0x180009500  jnz     short loc_180009530
0x180009502  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009507  mov     edi, eax
0x180009509  test    eax, eax
0x18000950b  jns     short loc_180009564
0x18000950d  mov     rcx, [rsp+278h]; this
0x180009515  lea     r8, aWil; "wil"
0x18000951c  mov     r9d, eax; char *
0x18000951f  mov     edx, 8Bh; void *
0x180009524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009529  mov     eax, edi
0x18000952b  jmp     loc_180009602
0x180009530  call    cs:__imp_GetLastError
0x180009536  mov     rdi, [rbx]
0x180009539  test    rdi, rdi
0x18000953c  jz      short loc_180009561
0x18000953e  call    cs:__imp_GetLastError
0x180009544  mov     rcx, rdi; hObject
0x180009547  mov     r14d, eax
0x18000954a  call    cs:__imp_CloseHandle
0x180009550  test    eax, eax
0x180009552  jz      loc_180009647
0x180009558  mov     ecx, r14d; dwErrCode
0x18000955b  call    cs:__imp_SetLastError
0x180009561  mov     [rbx], r15
0x180009564  lea     r8, asc_1800F2F38; "h"
0x18000956b  shr     rbp, 1Fh
0x18000956f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180009574  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009579  test    ebp, ebp
0x18000957b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009583  lea     r9, [rsp+278h+Name]; lpName
0x180009588  mov     [rsp+278h+dwFlags], r12d; int
0x18000958d  cmovnz  esi, ebp
0x180009590  mov     edx, ebp; lInitialCount
0x180009592  mov     r8d, esi; lMaximumCount
0x180009595  xor     ecx, ecx; lpSemaphoreAttributes
0x180009597  call    cs:__imp_CreateSemaphoreExW
0x18000959d  mov     rsi, rax
0x1800095a0  test    rax, rax
0x1800095a3  jnz     short loc_1800095D0
0x1800095a5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800095aa  mov     ebx, eax
0x1800095ac  test    eax, eax
0x1800095ae  jns     short loc_180009600
0x1800095b0  mov     rcx, [rsp+278h]; this
0x1800095b8  lea     r8, aWil; "wil"
0x1800095bf  mov     r9d, eax; char *
0x1800095c2  mov     edx, 90h; void *
0x1800095c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095cc  mov     eax, ebx
0x1800095ce  jmp     short loc_180009602
0x1800095d0  call    cs:__imp_GetLastError
0x1800095d6  mov     rdi, [rbx+8]
0x1800095da  test    rdi, rdi
0x1800095dd  jz      short loc_1800095FC
0x1800095df  call    cs:__imp_GetLastError
0x1800095e5  mov     rcx, rdi; hObject
0x1800095e8  mov     ebp, eax
0x1800095ea  call    cs:__imp_CloseHandle
0x1800095f0  test    eax, eax
0x1800095f2  jz      short loc_18000962E
0x1800095f4  mov     ecx, ebp; dwErrCode
0x1800095f6  call    cs:__imp_SetLastError
0x1800095fc  mov     [rbx+8], rsi
0x180009600  xor     eax, eax
0x180009602  mov     rcx, [rsp+278h+var_38]
0x18000960a  xor     rcx, rsp; StackCookie
0x18000960d  call    __security_check_cookie
0x180009612  lea     r11, [rsp+278h+var_28]
0x18000961a  mov     rbx, [r11+38h]
0x18000961e  mov     rbp, [r11+40h]
0x180009622  mov     rsp, r11
0x180009625  pop     r15
0x180009627  pop     r14
0x180009629  pop     r12
0x18000962b  pop     rdi
0x18000962c  pop     rsi
0x18000962d  retn
0x18000962e  mov     rcx, [rsp+278h]; this
0x180009636  mov     edx, 0A0Bh; void *
0x18000963b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009641  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009647  mov     rcx, [rsp+278h]; this
0x18000964f  mov     edx, 0A0Bh; void *
0x180009654  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
