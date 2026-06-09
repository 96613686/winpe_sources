# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003288`
- end: `0x1800034b2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002eb8`

## callees

- `0x180001570`
- `0x180003288`
- `0x180003b28`
- `0x1800048e4`
- `0x1800051c0`
- `0x1800056ec`
- `0x1800056fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000334c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800033ef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000334c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800033ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000344e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000344e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003442`

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
0x180003288  mov     [rsp+arg_8], rbx
0x18000328d  mov     [rsp+arg_10], rbp
0x180003292  push    rsi
0x180003293  push    rdi
0x180003294  push    r12
0x180003296  push    r14
0x180003298  push    r15
0x18000329a  sub     rsp, 250h
0x1800032a1  mov     rax, cs:__security_cookie
0x1800032a8  xor     rax, rsp
0x1800032ab  mov     [rsp+278h+var_38], rax
0x1800032b3  mov     rax, 0C000000000000000h
0x1800032bd  mov     rbp, r9
0x1800032c0  mov     r8, rdx
0x1800032c3  mov     rbx, rcx
0x1800032c6  test    rax, r9
0x1800032c9  jnz     loc_180003499
0x1800032cf  xor     r12d, r12d
0x1800032d2  lea     rax, [rsp+278h+Name]
0x1800032d7  mov     ecx, 7FFFFFFEh
0x1800032dc  mov     edx, 104h
0x1800032e1  lea     esi, [r12+1]
0x1800032e6  test    rcx, rcx
0x1800032e9  jz      short loc_180003309
0x1800032eb  movzx   r9d, word ptr [r8]
0x1800032ef  test    r9w, r9w
0x1800032f3  jz      short loc_180003309
0x1800032f5  mov     [rax], r9w
0x1800032f9  add     r8, 2
0x1800032fd  add     rax, 2
0x180003301  sub     rcx, rsi
0x180003304  sub     rdx, rsi; unsigned __int64
0x180003307  jnz     short loc_1800032E6
0x180003309  test    rdx, rdx
0x18000330c  lea     rcx, [rax-2]
0x180003310  lea     r8, aP0; "_p0"
0x180003317  cmovnz  rcx, rax
0x18000331b  mov     [rcx], r12w
0x18000331f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003324  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003329  mov     edx, ebp
0x18000332b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003333  and     edx, 7FFFFFFFh; lInitialCount
0x180003339  mov     [rsp+278h+dwFlags], r12d; int
0x18000333e  mov     r8d, esi
0x180003341  lea     r9, [rsp+278h+Name]; lpName
0x180003346  cmova   r8d, edx; lMaximumCount
0x18000334a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000334c  call    cs:__imp_CreateSemaphoreExW
0x180003352  mov     r15, rax
0x180003355  test    rax, rax
0x180003358  jnz     short loc_180003388
0x18000335a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000335f  mov     edi, eax
0x180003361  test    eax, eax
0x180003363  jns     short loc_1800033BC
0x180003365  mov     rcx, [rsp+278h]; this
0x18000336d  lea     r8, aWil; "wil"
0x180003374  mov     r9d, eax; char *
0x180003377  mov     edx, 8Bh; void *
0x18000337c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003381  mov     eax, edi
0x180003383  jmp     loc_18000345A
0x180003388  call    cs:__imp_GetLastError
0x18000338e  mov     rdi, [rbx]
0x180003391  test    rdi, rdi
0x180003394  jz      short loc_1800033B9
0x180003396  call    cs:__imp_GetLastError
0x18000339c  mov     rcx, rdi; hObject
0x18000339f  mov     r14d, eax
0x1800033a2  call    cs:__imp_CloseHandle
0x1800033a8  test    eax, eax
0x1800033aa  jz      loc_18000349F
0x1800033b0  mov     ecx, r14d; dwErrCode
0x1800033b3  call    cs:__imp_SetLastError
0x1800033b9  mov     [rbx], r15
0x1800033bc  lea     r8, asc_18000F138; "h"
0x1800033c3  shr     rbp, 1Fh
0x1800033c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800033cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800033d1  test    ebp, ebp
0x1800033d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800033db  lea     r9, [rsp+278h+Name]; lpName
0x1800033e0  mov     [rsp+278h+dwFlags], r12d; int
0x1800033e5  cmovnz  esi, ebp
0x1800033e8  mov     edx, ebp; lInitialCount
0x1800033ea  mov     r8d, esi; lMaximumCount
0x1800033ed  xor     ecx, ecx; lpSemaphoreAttributes
0x1800033ef  call    cs:__imp_CreateSemaphoreExW
0x1800033f5  mov     rsi, rax
0x1800033f8  test    rax, rax
0x1800033fb  jnz     short loc_180003428
0x1800033fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003402  mov     ebx, eax
0x180003404  test    eax, eax
0x180003406  jns     short loc_180003458
0x180003408  mov     rcx, [rsp+278h]; this
0x180003410  lea     r8, aWil; "wil"
0x180003417  mov     r9d, eax; char *
0x18000341a  mov     edx, 90h; void *
0x18000341f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003424  mov     eax, ebx
0x180003426  jmp     short loc_18000345A
0x180003428  call    cs:__imp_GetLastError
0x18000342e  mov     rdi, [rbx+8]
0x180003432  test    rdi, rdi
0x180003435  jz      short loc_180003454
0x180003437  call    cs:__imp_GetLastError
0x18000343d  mov     rcx, rdi; hObject
0x180003440  mov     ebp, eax
0x180003442  call    cs:__imp_CloseHandle
0x180003448  test    eax, eax
0x18000344a  jz      short loc_180003486
0x18000344c  mov     ecx, ebp; dwErrCode
0x18000344e  call    cs:__imp_SetLastError
0x180003454  mov     [rbx+8], rsi
0x180003458  xor     eax, eax
0x18000345a  mov     rcx, [rsp+278h+var_38]
0x180003462  xor     rcx, rsp; StackCookie
0x180003465  call    __security_check_cookie
0x18000346a  lea     r11, [rsp+278h+var_28]
0x180003472  mov     rbx, [r11+38h]
0x180003476  mov     rbp, [r11+40h]
0x18000347a  mov     rsp, r11
0x18000347d  pop     r15
0x18000347f  pop     r14
0x180003481  pop     r12
0x180003483  pop     rdi
0x180003484  pop     rsi
0x180003485  retn
0x180003486  mov     rcx, [rsp+278h]; this
0x18000348e  mov     edx, 0A0Bh; void *
0x180003493  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003499  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000349f  mov     rcx, [rsp+278h]; this
0x1800034a7  mov     edx, 0A0Bh; void *
0x1800034ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
