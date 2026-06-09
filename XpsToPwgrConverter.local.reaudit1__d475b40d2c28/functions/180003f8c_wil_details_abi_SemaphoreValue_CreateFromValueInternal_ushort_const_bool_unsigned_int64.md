# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003f8c`
- end: `0x180004199`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003818`
- `0x180003bbc`

## callees

- `0x180001760`
- `0x180003f8c`
- `0x180004d08`
- `0x180006db4`
- `0x1800077f8`
- `0x1800083fc`
- `0x18000840c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004050`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800040ec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004050`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800040ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000410f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000411e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000410f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000411e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000409f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000409f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004129`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x180003f8c  mov     [rsp+arg_8], rbx
0x180003f91  mov     [rsp+arg_10], rbp
0x180003f96  push    rsi
0x180003f97  push    rdi
0x180003f98  push    r12
0x180003f9a  push    r14
0x180003f9c  push    r15
0x180003f9e  sub     rsp, 250h
0x180003fa5  mov     rax, cs:__security_cookie
0x180003fac  xor     rax, rsp
0x180003faf  mov     [rsp+278h+var_38], rax
0x180003fb7  mov     rax, 0C000000000000000h
0x180003fc1  mov     rbp, r9
0x180003fc4  mov     r8, rdx
0x180003fc7  mov     rdi, rcx
0x180003fca  test    rax, r9
0x180003fcd  jnz     loc_180004180
0x180003fd3  xor     r12d, r12d
0x180003fd6  lea     rax, [rsp+278h+Name]
0x180003fdb  mov     ecx, 7FFFFFFEh
0x180003fe0  mov     edx, 104h
0x180003fe5  lea     esi, [r12+1]
0x180003fea  test    rcx, rcx
0x180003fed  jz      short loc_18000400D
0x180003fef  movzx   r9d, word ptr [r8]
0x180003ff3  test    r9w, r9w
0x180003ff7  jz      short loc_18000400D
0x180003ff9  mov     [rax], r9w
0x180003ffd  add     r8, 2
0x180004001  add     rax, 2
0x180004005  sub     rcx, rsi
0x180004008  sub     rdx, rsi; unsigned __int64
0x18000400b  jnz     short loc_180003FEA
0x18000400d  test    rdx, rdx
0x180004010  lea     rcx, [rax-2]
0x180004014  lea     r8, aP0; "_p0"
0x18000401b  cmovnz  rcx, rax
0x18000401f  mov     [rcx], r12w
0x180004023  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004028  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000402d  mov     edx, ebp
0x18000402f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004037  and     edx, 7FFFFFFFh; lInitialCount
0x18000403d  mov     [rsp+278h+dwFlags], r12d; int
0x180004042  mov     r8d, esi
0x180004045  lea     r9, [rsp+278h+Name]; lpName
0x18000404a  cmova   r8d, edx; lMaximumCount
0x18000404e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004050  call    cs:__imp_CreateSemaphoreExW
0x180004056  mov     r15, rax
0x180004059  test    rax, rax
0x18000405c  jnz     short loc_180004085
0x18000405e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004063  mov     ebx, eax
0x180004065  test    eax, eax
0x180004067  jns     short loc_1800040B9
0x180004069  mov     edx, 8Bh; void *
0x18000406e  mov     rcx, [rsp+278h]; this
0x180004076  mov     r9d, ebx; char *
0x180004079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000407e  mov     eax, ebx
0x180004080  jmp     loc_180004141
0x180004085  call    cs:__imp_GetLastError
0x18000408b  mov     rbx, [rdi]
0x18000408e  test    rbx, rbx
0x180004091  jz      short loc_1800040B6
0x180004093  call    cs:__imp_GetLastError
0x180004099  mov     rcx, rbx; hObject
0x18000409c  mov     r14d, eax
0x18000409f  call    cs:__imp_CloseHandle
0x1800040a5  test    eax, eax
0x1800040a7  jz      loc_180004186
0x1800040ad  mov     ecx, r14d; dwErrCode
0x1800040b0  call    cs:__imp_SetLastError
0x1800040b6  mov     [rdi], r15
0x1800040b9  lea     r8, asc_180012FD8; "h"
0x1800040c0  shr     rbp, 1Fh
0x1800040c4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800040c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800040ce  test    ebp, ebp
0x1800040d0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800040d8  lea     r9, [rsp+278h+Name]; lpName
0x1800040dd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800040e2  cmovnz  esi, ebp
0x1800040e5  mov     edx, ebp; lInitialCount
0x1800040e7  mov     r8d, esi; lMaximumCount
0x1800040ea  xor     ecx, ecx; lpSemaphoreAttributes
0x1800040ec  call    cs:__imp_CreateSemaphoreExW
0x1800040f2  mov     rsi, rax
0x1800040f5  test    rax, rax
0x1800040f8  jnz     short loc_18000410F
0x1800040fa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800040ff  mov     ebx, eax
0x180004101  test    eax, eax
0x180004103  jns     short loc_18000413F
0x180004105  mov     edx, 90h
0x18000410a  jmp     loc_18000406E
0x18000410f  call    cs:__imp_GetLastError
0x180004115  mov     rbx, [rdi+8]
0x180004119  test    rbx, rbx
0x18000411c  jz      short loc_18000413B
0x18000411e  call    cs:__imp_GetLastError
0x180004124  mov     rcx, rbx; hObject
0x180004127  mov     ebp, eax
0x180004129  call    cs:__imp_CloseHandle
0x18000412f  test    eax, eax
0x180004131  jz      short loc_18000416D
0x180004133  mov     ecx, ebp; dwErrCode
0x180004135  call    cs:__imp_SetLastError
0x18000413b  mov     [rdi+8], rsi
0x18000413f  xor     eax, eax
0x180004141  mov     rcx, [rsp+278h+var_38]
0x180004149  xor     rcx, rsp; StackCookie
0x18000414c  call    __security_check_cookie
0x180004151  lea     r11, [rsp+278h+var_28]
0x180004159  mov     rbx, [r11+38h]
0x18000415d  mov     rbp, [r11+40h]
0x180004161  mov     rsp, r11
0x180004164  pop     r15
0x180004166  pop     r14
0x180004168  pop     r12
0x18000416a  pop     rdi
0x18000416b  pop     rsi
0x18000416c  retn
0x18000416d  mov     rcx, [rsp+278h]; this
0x180004175  mov     edx, 0A0Bh; void *
0x18000417a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004180  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004186  mov     rcx, [rsp+278h]; this
0x18000418e  mov     edx, 0A0Bh; void *
0x180004193  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
