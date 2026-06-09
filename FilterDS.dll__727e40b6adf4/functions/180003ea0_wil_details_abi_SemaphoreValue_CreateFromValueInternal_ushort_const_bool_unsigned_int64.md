# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003ea0`
- end: `0x1800040ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ad0`
- `0x180008f1c`

## callees

- `0x180003ea0`
- `0x1800049d8`
- `0x180005ca4`
- `0x180006424`
- `0x180006ba4`
- `0x180006bb4`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f64`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004007`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f64`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000404f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000404f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003fcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000405a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000405a`

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
0x180003ea0  mov     [rsp+arg_8], rbx
0x180003ea5  mov     [rsp+arg_10], rbp
0x180003eaa  push    rsi
0x180003eab  push    rdi
0x180003eac  push    r12
0x180003eae  push    r14
0x180003eb0  push    r15
0x180003eb2  sub     rsp, 250h
0x180003eb9  mov     rax, cs:__security_cookie
0x180003ec0  xor     rax, rsp
0x180003ec3  mov     [rsp+278h+var_38], rax
0x180003ecb  mov     rax, 0C000000000000000h
0x180003ed5  mov     rbp, r9
0x180003ed8  mov     r8, rdx
0x180003edb  mov     rbx, rcx
0x180003ede  test    rax, r9
0x180003ee1  jnz     loc_1800040B1
0x180003ee7  xor     r12d, r12d
0x180003eea  lea     rax, [rsp+278h+Name]
0x180003eef  mov     ecx, 7FFFFFFEh
0x180003ef4  mov     edx, 104h
0x180003ef9  lea     esi, [r12+1]
0x180003efe  test    rcx, rcx
0x180003f01  jz      short loc_180003F21
0x180003f03  movzx   r9d, word ptr [r8]
0x180003f07  test    r9w, r9w
0x180003f0b  jz      short loc_180003F21
0x180003f0d  mov     [rax], r9w
0x180003f11  add     r8, 2
0x180003f15  add     rax, 2
0x180003f19  sub     rcx, rsi
0x180003f1c  sub     rdx, rsi; unsigned __int64
0x180003f1f  jnz     short loc_180003EFE
0x180003f21  test    rdx, rdx
0x180003f24  lea     rcx, [rax-2]
0x180003f28  lea     r8, aP0; "_p0"
0x180003f2f  cmovnz  rcx, rax
0x180003f33  mov     [rcx], r12w
0x180003f37  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003f3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003f41  mov     edx, ebp
0x180003f43  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003f4b  and     edx, 7FFFFFFFh; lInitialCount
0x180003f51  mov     [rsp+278h+dwFlags], r12d; int
0x180003f56  mov     r8d, esi
0x180003f59  lea     r9, [rsp+278h+Name]; lpName
0x180003f5e  cmova   r8d, edx; lMaximumCount
0x180003f62  xor     ecx, ecx; lpSemaphoreAttributes
0x180003f64  call    cs:__imp_CreateSemaphoreExW
0x180003f6a  mov     r15, rax
0x180003f6d  test    rax, rax
0x180003f70  jnz     short loc_180003FA0
0x180003f72  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f77  mov     edi, eax
0x180003f79  test    eax, eax
0x180003f7b  jns     short loc_180003FD4
0x180003f7d  mov     rcx, [rsp+278h]; this
0x180003f85  lea     r8, aWil; "wil"
0x180003f8c  mov     r9d, eax; char *
0x180003f8f  mov     edx, 8Bh; void *
0x180003f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f99  mov     eax, edi
0x180003f9b  jmp     loc_180004072
0x180003fa0  call    cs:__imp_GetLastError
0x180003fa6  mov     rdi, [rbx]
0x180003fa9  test    rdi, rdi
0x180003fac  jz      short loc_180003FD1
0x180003fae  call    cs:__imp_GetLastError
0x180003fb4  mov     rcx, rdi; hObject
0x180003fb7  mov     r14d, eax
0x180003fba  call    cs:__imp_CloseHandle
0x180003fc0  test    eax, eax
0x180003fc2  jz      loc_1800040B7
0x180003fc8  mov     ecx, r14d; dwErrCode
0x180003fcb  call    cs:__imp_SetLastError
0x180003fd1  mov     [rbx], r15
0x180003fd4  lea     r8, asc_1800284A8; "h"
0x180003fdb  shr     rbp, 1Fh
0x180003fdf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003fe4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003fe9  test    ebp, ebp
0x180003feb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003ff3  lea     r9, [rsp+278h+Name]; lpName
0x180003ff8  mov     [rsp+278h+dwFlags], r12d; int
0x180003ffd  cmovnz  esi, ebp
0x180004000  mov     edx, ebp; lInitialCount
0x180004002  mov     r8d, esi; lMaximumCount
0x180004005  xor     ecx, ecx; lpSemaphoreAttributes
0x180004007  call    cs:__imp_CreateSemaphoreExW
0x18000400d  mov     rsi, rax
0x180004010  test    rax, rax
0x180004013  jnz     short loc_180004040
0x180004015  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000401a  mov     ebx, eax
0x18000401c  test    eax, eax
0x18000401e  jns     short loc_180004070
0x180004020  mov     rcx, [rsp+278h]; this
0x180004028  lea     r8, aWil; "wil"
0x18000402f  mov     r9d, eax; char *
0x180004032  mov     edx, 90h; void *
0x180004037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000403c  mov     eax, ebx
0x18000403e  jmp     short loc_180004072
0x180004040  call    cs:__imp_GetLastError
0x180004046  mov     rdi, [rbx+8]
0x18000404a  test    rdi, rdi
0x18000404d  jz      short loc_18000406C
0x18000404f  call    cs:__imp_GetLastError
0x180004055  mov     rcx, rdi; hObject
0x180004058  mov     ebp, eax
0x18000405a  call    cs:__imp_CloseHandle
0x180004060  test    eax, eax
0x180004062  jz      short loc_18000409E
0x180004064  mov     ecx, ebp; dwErrCode
0x180004066  call    cs:__imp_SetLastError
0x18000406c  mov     [rbx+8], rsi
0x180004070  xor     eax, eax
0x180004072  mov     rcx, [rsp+278h+var_38]
0x18000407a  xor     rcx, rsp; StackCookie
0x18000407d  call    __security_check_cookie
0x180004082  lea     r11, [rsp+278h+var_28]
0x18000408a  mov     rbx, [r11+38h]
0x18000408e  mov     rbp, [r11+40h]
0x180004092  mov     rsp, r11
0x180004095  pop     r15
0x180004097  pop     r14
0x180004099  pop     r12
0x18000409b  pop     rdi
0x18000409c  pop     rsi
0x18000409d  retn
0x18000409e  mov     rcx, [rsp+278h]; this
0x1800040a6  mov     edx, 0A0Bh; void *
0x1800040ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800040b7  mov     rcx, [rsp+278h]; this
0x1800040bf  mov     edx, 0A0Bh; void *
0x1800040c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
