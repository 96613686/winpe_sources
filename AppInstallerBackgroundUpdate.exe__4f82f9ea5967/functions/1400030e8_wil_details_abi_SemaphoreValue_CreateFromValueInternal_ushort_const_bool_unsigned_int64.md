# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400030e8`
- end: `0x140003312`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d18`
- `0x140006064`

## callees

- `0x140001530`
- `0x1400030e8`
- `0x140003a28`
- `0x140004764`
- `0x1400050a4`
- `0x1400055dc`
- `0x1400055ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400031ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000324f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400031ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000324f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003297`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003213`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003213`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032a2`

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
0x1400030e8  mov     [rsp+arg_8], rbx
0x1400030ed  mov     [rsp+arg_10], rbp
0x1400030f2  push    rsi
0x1400030f3  push    rdi
0x1400030f4  push    r12
0x1400030f6  push    r14
0x1400030f8  push    r15
0x1400030fa  sub     rsp, 250h
0x140003101  mov     rax, cs:__security_cookie
0x140003108  xor     rax, rsp
0x14000310b  mov     [rsp+278h+var_38], rax
0x140003113  mov     rax, 0C000000000000000h
0x14000311d  mov     rbp, r9
0x140003120  mov     r8, rdx
0x140003123  mov     rbx, rcx
0x140003126  test    rax, r9
0x140003129  jnz     loc_1400032F9
0x14000312f  xor     r12d, r12d
0x140003132  lea     rax, [rsp+278h+Name]
0x140003137  mov     ecx, 7FFFFFFEh
0x14000313c  mov     edx, 104h
0x140003141  lea     esi, [r12+1]
0x140003146  test    rcx, rcx
0x140003149  jz      short loc_140003169
0x14000314b  movzx   r9d, word ptr [r8]
0x14000314f  test    r9w, r9w
0x140003153  jz      short loc_140003169
0x140003155  mov     [rax], r9w
0x140003159  add     r8, 2
0x14000315d  add     rax, 2
0x140003161  sub     rcx, rsi
0x140003164  sub     rdx, rsi; unsigned __int64
0x140003167  jnz     short loc_140003146
0x140003169  test    rdx, rdx
0x14000316c  lea     rcx, [rax-2]
0x140003170  lea     r8, aP0; "_p0"
0x140003177  cmovnz  rcx, rax
0x14000317b  mov     [rcx], r12w
0x14000317f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003184  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003189  mov     edx, ebp
0x14000318b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003193  and     edx, 7FFFFFFFh; lInitialCount
0x140003199  mov     [rsp+278h+dwFlags], r12d; int
0x14000319e  mov     r8d, esi
0x1400031a1  lea     r9, [rsp+278h+Name]; lpName
0x1400031a6  cmova   r8d, edx; lMaximumCount
0x1400031aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1400031ac  call    cs:__imp_CreateSemaphoreExW
0x1400031b2  mov     r15, rax
0x1400031b5  test    rax, rax
0x1400031b8  jnz     short loc_1400031E8
0x1400031ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400031bf  mov     edi, eax
0x1400031c1  test    eax, eax
0x1400031c3  jns     short loc_14000321C
0x1400031c5  mov     rcx, [rsp+278h]; this
0x1400031cd  lea     r8, aWil; "wil"
0x1400031d4  mov     r9d, eax; char *
0x1400031d7  mov     edx, 8Bh; void *
0x1400031dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031e1  mov     eax, edi
0x1400031e3  jmp     loc_1400032BA
0x1400031e8  call    cs:__imp_GetLastError
0x1400031ee  mov     rdi, [rbx]
0x1400031f1  test    rdi, rdi
0x1400031f4  jz      short loc_140003219
0x1400031f6  call    cs:__imp_GetLastError
0x1400031fc  mov     rcx, rdi; hObject
0x1400031ff  mov     r14d, eax
0x140003202  call    cs:__imp_CloseHandle
0x140003208  test    eax, eax
0x14000320a  jz      loc_1400032FF
0x140003210  mov     ecx, r14d; dwErrCode
0x140003213  call    cs:__imp_SetLastError
0x140003219  mov     [rbx], r15
0x14000321c  lea     r8, asc_14000A900; "h"
0x140003223  shr     rbp, 1Fh
0x140003227  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000322c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003231  test    ebp, ebp
0x140003233  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000323b  lea     r9, [rsp+278h+Name]; lpName
0x140003240  mov     [rsp+278h+dwFlags], r12d; int
0x140003245  cmovnz  esi, ebp
0x140003248  mov     edx, ebp; lInitialCount
0x14000324a  mov     r8d, esi; lMaximumCount
0x14000324d  xor     ecx, ecx; lpSemaphoreAttributes
0x14000324f  call    cs:__imp_CreateSemaphoreExW
0x140003255  mov     rsi, rax
0x140003258  test    rax, rax
0x14000325b  jnz     short loc_140003288
0x14000325d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003262  mov     ebx, eax
0x140003264  test    eax, eax
0x140003266  jns     short loc_1400032B8
0x140003268  mov     rcx, [rsp+278h]; this
0x140003270  lea     r8, aWil; "wil"
0x140003277  mov     r9d, eax; char *
0x14000327a  mov     edx, 90h; void *
0x14000327f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003284  mov     eax, ebx
0x140003286  jmp     short loc_1400032BA
0x140003288  call    cs:__imp_GetLastError
0x14000328e  mov     rdi, [rbx+8]
0x140003292  test    rdi, rdi
0x140003295  jz      short loc_1400032B4
0x140003297  call    cs:__imp_GetLastError
0x14000329d  mov     rcx, rdi; hObject
0x1400032a0  mov     ebp, eax
0x1400032a2  call    cs:__imp_CloseHandle
0x1400032a8  test    eax, eax
0x1400032aa  jz      short loc_1400032E6
0x1400032ac  mov     ecx, ebp; dwErrCode
0x1400032ae  call    cs:__imp_SetLastError
0x1400032b4  mov     [rbx+8], rsi
0x1400032b8  xor     eax, eax
0x1400032ba  mov     rcx, [rsp+278h+var_38]
0x1400032c2  xor     rcx, rsp; StackCookie
0x1400032c5  call    __security_check_cookie
0x1400032ca  lea     r11, [rsp+278h+var_28]
0x1400032d2  mov     rbx, [r11+38h]
0x1400032d6  mov     rbp, [r11+40h]
0x1400032da  mov     rsp, r11
0x1400032dd  pop     r15
0x1400032df  pop     r14
0x1400032e1  pop     r12
0x1400032e3  pop     rdi
0x1400032e4  pop     rsi
0x1400032e5  retn
0x1400032e6  mov     rcx, [rsp+278h]; this
0x1400032ee  mov     edx, 0A0Bh; void *
0x1400032f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400032f9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400032ff  mov     rcx, [rsp+278h]; this
0x140003307  mov     edx, 0A0Bh; void *
0x14000330c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
