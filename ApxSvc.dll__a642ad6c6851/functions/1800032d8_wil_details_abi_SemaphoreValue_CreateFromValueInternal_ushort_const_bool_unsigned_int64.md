# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800032d8`
- end: `0x180003502`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002f08`

## callees

- `0x180001560`
- `0x1800032d8`
- `0x180003b68`
- `0x180004924`
- `0x180005200`
- `0x18000572c`
- `0x18000573c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000339c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000343f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000339c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000343f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003487`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000349e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000349e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003492`

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
0x1800032d8  mov     [rsp+arg_8], rbx
0x1800032dd  mov     [rsp+arg_10], rbp
0x1800032e2  push    rsi
0x1800032e3  push    rdi
0x1800032e4  push    r12
0x1800032e6  push    r14
0x1800032e8  push    r15
0x1800032ea  sub     rsp, 250h
0x1800032f1  mov     rax, cs:__security_cookie
0x1800032f8  xor     rax, rsp
0x1800032fb  mov     [rsp+278h+var_38], rax
0x180003303  mov     rax, 0C000000000000000h
0x18000330d  mov     rbp, r9
0x180003310  mov     r8, rdx
0x180003313  mov     rbx, rcx
0x180003316  test    rax, r9
0x180003319  jnz     loc_1800034E9
0x18000331f  xor     r12d, r12d
0x180003322  lea     rax, [rsp+278h+Name]
0x180003327  mov     ecx, 7FFFFFFEh
0x18000332c  mov     edx, 104h
0x180003331  lea     esi, [r12+1]
0x180003336  test    rcx, rcx
0x180003339  jz      short loc_180003359
0x18000333b  movzx   r9d, word ptr [r8]
0x18000333f  test    r9w, r9w
0x180003343  jz      short loc_180003359
0x180003345  mov     [rax], r9w
0x180003349  add     r8, 2
0x18000334d  add     rax, 2
0x180003351  sub     rcx, rsi
0x180003354  sub     rdx, rsi; unsigned __int64
0x180003357  jnz     short loc_180003336
0x180003359  test    rdx, rdx
0x18000335c  lea     rcx, [rax-2]
0x180003360  lea     r8, aP0; "_p0"
0x180003367  cmovnz  rcx, rax
0x18000336b  mov     [rcx], r12w
0x18000336f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003374  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003379  mov     edx, ebp
0x18000337b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003383  and     edx, 7FFFFFFFh; lInitialCount
0x180003389  mov     [rsp+278h+dwFlags], r12d; int
0x18000338e  mov     r8d, esi
0x180003391  lea     r9, [rsp+278h+Name]; lpName
0x180003396  cmova   r8d, edx; lMaximumCount
0x18000339a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000339c  call    cs:__imp_CreateSemaphoreExW
0x1800033a2  mov     r15, rax
0x1800033a5  test    rax, rax
0x1800033a8  jnz     short loc_1800033D8
0x1800033aa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800033af  mov     edi, eax
0x1800033b1  test    eax, eax
0x1800033b3  jns     short loc_18000340C
0x1800033b5  mov     rcx, [rsp+278h]; this
0x1800033bd  lea     r8, aWil; "wil"
0x1800033c4  mov     r9d, eax; char *
0x1800033c7  mov     edx, 8Bh; void *
0x1800033cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033d1  mov     eax, edi
0x1800033d3  jmp     loc_1800034AA
0x1800033d8  call    cs:__imp_GetLastError
0x1800033de  mov     rdi, [rbx]
0x1800033e1  test    rdi, rdi
0x1800033e4  jz      short loc_180003409
0x1800033e6  call    cs:__imp_GetLastError
0x1800033ec  mov     rcx, rdi; hObject
0x1800033ef  mov     r14d, eax
0x1800033f2  call    cs:__imp_CloseHandle
0x1800033f8  test    eax, eax
0x1800033fa  jz      loc_1800034EF
0x180003400  mov     ecx, r14d; dwErrCode
0x180003403  call    cs:__imp_SetLastError
0x180003409  mov     [rbx], r15
0x18000340c  lea     r8, asc_18000AEE0; "h"
0x180003413  shr     rbp, 1Fh
0x180003417  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000341c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003421  test    ebp, ebp
0x180003423  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000342b  lea     r9, [rsp+278h+Name]; lpName
0x180003430  mov     [rsp+278h+dwFlags], r12d; int
0x180003435  cmovnz  esi, ebp
0x180003438  mov     edx, ebp; lInitialCount
0x18000343a  mov     r8d, esi; lMaximumCount
0x18000343d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000343f  call    cs:__imp_CreateSemaphoreExW
0x180003445  mov     rsi, rax
0x180003448  test    rax, rax
0x18000344b  jnz     short loc_180003478
0x18000344d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003452  mov     ebx, eax
0x180003454  test    eax, eax
0x180003456  jns     short loc_1800034A8
0x180003458  mov     rcx, [rsp+278h]; this
0x180003460  lea     r8, aWil; "wil"
0x180003467  mov     r9d, eax; char *
0x18000346a  mov     edx, 90h; void *
0x18000346f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003474  mov     eax, ebx
0x180003476  jmp     short loc_1800034AA
0x180003478  call    cs:__imp_GetLastError
0x18000347e  mov     rdi, [rbx+8]
0x180003482  test    rdi, rdi
0x180003485  jz      short loc_1800034A4
0x180003487  call    cs:__imp_GetLastError
0x18000348d  mov     rcx, rdi; hObject
0x180003490  mov     ebp, eax
0x180003492  call    cs:__imp_CloseHandle
0x180003498  test    eax, eax
0x18000349a  jz      short loc_1800034D6
0x18000349c  mov     ecx, ebp; dwErrCode
0x18000349e  call    cs:__imp_SetLastError
0x1800034a4  mov     [rbx+8], rsi
0x1800034a8  xor     eax, eax
0x1800034aa  mov     rcx, [rsp+278h+var_38]
0x1800034b2  xor     rcx, rsp; StackCookie
0x1800034b5  call    __security_check_cookie
0x1800034ba  lea     r11, [rsp+278h+var_28]
0x1800034c2  mov     rbx, [r11+38h]
0x1800034c6  mov     rbp, [r11+40h]
0x1800034ca  mov     rsp, r11
0x1800034cd  pop     r15
0x1800034cf  pop     r14
0x1800034d1  pop     r12
0x1800034d3  pop     rdi
0x1800034d4  pop     rsi
0x1800034d5  retn
0x1800034d6  mov     rcx, [rsp+278h]; this
0x1800034de  mov     edx, 0A0Bh; void *
0x1800034e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034e9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800034ef  mov     rcx, [rsp+278h]; this
0x1800034f7  mov     edx, 0A0Bh; void *
0x1800034fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
