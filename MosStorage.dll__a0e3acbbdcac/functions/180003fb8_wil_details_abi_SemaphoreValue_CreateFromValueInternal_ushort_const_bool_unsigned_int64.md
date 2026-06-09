# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003fb8`
- end: `0x1800041c5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003c14`

## callees

- `0x180001c80`
- `0x180003fb8`
- `0x180004838`
- `0x180005774`
- `0x180006050`
- `0x18000656c`
- `0x18000657c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000407c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004118`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000407c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000413b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000413b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004155`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003fb8  mov     [rsp+arg_8], rbx
0x180003fbd  mov     [rsp+arg_10], rbp
0x180003fc2  push    rsi
0x180003fc3  push    rdi
0x180003fc4  push    r12
0x180003fc6  push    r14
0x180003fc8  push    r15
0x180003fca  sub     rsp, 250h
0x180003fd1  mov     rax, cs:__security_cookie
0x180003fd8  xor     rax, rsp
0x180003fdb  mov     [rsp+278h+var_38], rax
0x180003fe3  mov     rax, 0C000000000000000h
0x180003fed  mov     rbp, r9
0x180003ff0  mov     r8, rdx
0x180003ff3  mov     rdi, rcx
0x180003ff6  test    rax, r9
0x180003ff9  jnz     loc_1800041AC
0x180003fff  xor     r12d, r12d
0x180004002  lea     rax, [rsp+278h+Name]
0x180004007  mov     ecx, 7FFFFFFEh
0x18000400c  mov     edx, 104h
0x180004011  lea     esi, [r12+1]
0x180004016  test    rcx, rcx
0x180004019  jz      short loc_180004039
0x18000401b  movzx   r9d, word ptr [r8]
0x18000401f  test    r9w, r9w
0x180004023  jz      short loc_180004039
0x180004025  mov     [rax], r9w
0x180004029  add     r8, 2
0x18000402d  add     rax, 2
0x180004031  sub     rcx, rsi
0x180004034  sub     rdx, rsi; unsigned __int64
0x180004037  jnz     short loc_180004016
0x180004039  test    rdx, rdx
0x18000403c  lea     rcx, [rax-2]
0x180004040  lea     r8, aP0; "_p0"
0x180004047  cmovnz  rcx, rax
0x18000404b  mov     [rcx], r12w
0x18000404f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004054  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004059  mov     edx, ebp
0x18000405b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004063  and     edx, 7FFFFFFFh; lInitialCount
0x180004069  mov     [rsp+278h+dwFlags], r12d; int
0x18000406e  mov     r8d, esi
0x180004071  lea     r9, [rsp+278h+Name]; lpName
0x180004076  cmova   r8d, edx; lMaximumCount
0x18000407a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000407c  call    cs:__imp_CreateSemaphoreExW
0x180004082  mov     r15, rax
0x180004085  test    rax, rax
0x180004088  jnz     short loc_1800040B1
0x18000408a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000408f  mov     ebx, eax
0x180004091  test    eax, eax
0x180004093  jns     short loc_1800040E5
0x180004095  mov     edx, 8Bh; void *
0x18000409a  mov     rcx, [rsp+278h]; this
0x1800040a2  mov     r9d, ebx; char *
0x1800040a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040aa  mov     eax, ebx
0x1800040ac  jmp     loc_18000416D
0x1800040b1  call    cs:__imp_GetLastError
0x1800040b7  mov     rbx, [rdi]
0x1800040ba  test    rbx, rbx
0x1800040bd  jz      short loc_1800040E2
0x1800040bf  call    cs:__imp_GetLastError
0x1800040c5  mov     rcx, rbx; hObject
0x1800040c8  mov     r14d, eax
0x1800040cb  call    cs:__imp_CloseHandle
0x1800040d1  test    eax, eax
0x1800040d3  jz      loc_1800041B2
0x1800040d9  mov     ecx, r14d; dwErrCode
0x1800040dc  call    cs:__imp_SetLastError
0x1800040e2  mov     [rdi], r15
0x1800040e5  lea     r8, asc_180012048; "h"
0x1800040ec  shr     rbp, 1Fh
0x1800040f0  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800040f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800040fa  test    ebp, ebp
0x1800040fc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004104  lea     r9, [rsp+278h+Name]; lpName
0x180004109  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000410e  cmovnz  esi, ebp
0x180004111  mov     edx, ebp; lInitialCount
0x180004113  mov     r8d, esi; lMaximumCount
0x180004116  xor     ecx, ecx; lpSemaphoreAttributes
0x180004118  call    cs:__imp_CreateSemaphoreExW
0x18000411e  mov     rsi, rax
0x180004121  test    rax, rax
0x180004124  jnz     short loc_18000413B
0x180004126  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000412b  mov     ebx, eax
0x18000412d  test    eax, eax
0x18000412f  jns     short loc_18000416B
0x180004131  mov     edx, 90h
0x180004136  jmp     loc_18000409A
0x18000413b  call    cs:__imp_GetLastError
0x180004141  mov     rbx, [rdi+8]
0x180004145  test    rbx, rbx
0x180004148  jz      short loc_180004167
0x18000414a  call    cs:__imp_GetLastError
0x180004150  mov     rcx, rbx; hObject
0x180004153  mov     ebp, eax
0x180004155  call    cs:__imp_CloseHandle
0x18000415b  test    eax, eax
0x18000415d  jz      short loc_180004199
0x18000415f  mov     ecx, ebp; dwErrCode
0x180004161  call    cs:__imp_SetLastError
0x180004167  mov     [rdi+8], rsi
0x18000416b  xor     eax, eax
0x18000416d  mov     rcx, [rsp+278h+var_38]
0x180004175  xor     rcx, rsp; StackCookie
0x180004178  call    __security_check_cookie
0x18000417d  lea     r11, [rsp+278h+var_28]
0x180004185  mov     rbx, [r11+38h]
0x180004189  mov     rbp, [r11+40h]
0x18000418d  mov     rsp, r11
0x180004190  pop     r15
0x180004192  pop     r14
0x180004194  pop     r12
0x180004196  pop     rdi
0x180004197  pop     rsi
0x180004198  retn
0x180004199  mov     rcx, [rsp+278h]; this
0x1800041a1  mov     edx, 0A0Bh; void *
0x1800041a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041ac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041b2  mov     rcx, [rsp+278h]; this
0x1800041ba  mov     edx, 0A0Bh; void *
0x1800041bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
