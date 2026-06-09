# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800034f0`
- end: `0x1800036fd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000314c`
- `0x18001085c`

## callees

- `0x1800034f0`
- `0x180003e18`
- `0x180004b30`
- `0x180004e4c`
- `0x18000533c`
- `0x18000534c`
- `0x180012e00`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800035b4`
- `KERNEL32!CreateSemaphoreExW` at `0x180003650`
- `KERNEL32!CreateSemaphoreExW` at `0x1800035b4`
- `KERNEL32!CreateSemaphoreExW` at `0x180003650`
- `KERNEL32!SetLastError` at `0x180003614`
- `KERNEL32!SetLastError` at `0x180003699`
- `KERNEL32!SetLastError` at `0x180003614`
- `KERNEL32!SetLastError` at `0x180003699`
- `KERNEL32!GetLastError` at `0x1800035e9`
- `KERNEL32!GetLastError` at `0x1800035f7`
- `KERNEL32!GetLastError` at `0x180003673`
- `KERNEL32!GetLastError` at `0x180003682`
- `KERNEL32!GetLastError` at `0x1800035e9`
- `KERNEL32!GetLastError` at `0x1800035f7`
- `KERNEL32!GetLastError` at `0x180003673`
- `KERNEL32!GetLastError` at `0x180003682`
- `KERNEL32!CloseHandle` at `0x180003603`
- `KERNEL32!CloseHandle` at `0x18000368d`
- `KERNEL32!CloseHandle` at `0x180003603`
- `KERNEL32!CloseHandle` at `0x18000368d`

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
0x1800034f0  mov     [rsp+arg_8], rbx
0x1800034f5  mov     [rsp+arg_10], rbp
0x1800034fa  push    rsi
0x1800034fb  push    rdi
0x1800034fc  push    r12
0x1800034fe  push    r14
0x180003500  push    r15
0x180003502  sub     rsp, 250h
0x180003509  mov     rax, cs:__security_cookie
0x180003510  xor     rax, rsp
0x180003513  mov     [rsp+278h+var_38], rax
0x18000351b  mov     rax, 0C000000000000000h
0x180003525  mov     rbp, r9
0x180003528  mov     r8, rdx
0x18000352b  mov     rdi, rcx
0x18000352e  test    rax, r9
0x180003531  jnz     loc_1800036E4
0x180003537  xor     r12d, r12d
0x18000353a  lea     rax, [rsp+278h+Name]
0x18000353f  mov     ecx, 7FFFFFFEh
0x180003544  mov     edx, 104h
0x180003549  lea     esi, [r12+1]
0x18000354e  test    rcx, rcx
0x180003551  jz      short loc_180003571
0x180003553  movzx   r9d, word ptr [r8]
0x180003557  test    r9w, r9w
0x18000355b  jz      short loc_180003571
0x18000355d  mov     [rax], r9w
0x180003561  add     r8, 2
0x180003565  add     rax, 2
0x180003569  sub     rcx, rsi
0x18000356c  sub     rdx, rsi; unsigned __int64
0x18000356f  jnz     short loc_18000354E
0x180003571  test    rdx, rdx
0x180003574  lea     rcx, [rax-2]
0x180003578  lea     r8, aP0; "_p0"
0x18000357f  cmovnz  rcx, rax
0x180003583  mov     [rcx], r12w
0x180003587  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000358c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003591  mov     edx, ebp
0x180003593  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000359b  and     edx, 7FFFFFFFh; lInitialCount
0x1800035a1  mov     [rsp+278h+dwFlags], r12d; int
0x1800035a6  mov     r8d, esi
0x1800035a9  lea     r9, [rsp+278h+Name]; lpName
0x1800035ae  cmova   r8d, edx; lMaximumCount
0x1800035b2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035b4  call    cs:__imp_CreateSemaphoreExW
0x1800035ba  mov     r15, rax
0x1800035bd  test    rax, rax
0x1800035c0  jnz     short loc_1800035E9
0x1800035c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035c7  mov     ebx, eax
0x1800035c9  test    eax, eax
0x1800035cb  jns     short loc_18000361D
0x1800035cd  mov     edx, 8Bh; void *
0x1800035d2  mov     rcx, [rsp+278h]; this
0x1800035da  mov     r9d, ebx; char *
0x1800035dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035e2  mov     eax, ebx
0x1800035e4  jmp     loc_1800036A5
0x1800035e9  call    cs:__imp_GetLastError
0x1800035ef  mov     rbx, [rdi]
0x1800035f2  test    rbx, rbx
0x1800035f5  jz      short loc_18000361A
0x1800035f7  call    cs:__imp_GetLastError
0x1800035fd  mov     rcx, rbx; hObject
0x180003600  mov     r14d, eax
0x180003603  call    cs:__imp_CloseHandle
0x180003609  test    eax, eax
0x18000360b  jz      loc_1800036EA
0x180003611  mov     ecx, r14d; dwErrCode
0x180003614  call    cs:__imp_SetLastError
0x18000361a  mov     [rdi], r15
0x18000361d  lea     r8, asc_180016548; "h"
0x180003624  shr     rbp, 1Fh
0x180003628  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000362d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003632  test    ebp, ebp
0x180003634  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000363c  lea     r9, [rsp+278h+Name]; lpName
0x180003641  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003646  cmovnz  esi, ebp
0x180003649  mov     edx, ebp; lInitialCount
0x18000364b  mov     r8d, esi; lMaximumCount
0x18000364e  xor     ecx, ecx; lpSemaphoreAttributes
0x180003650  call    cs:__imp_CreateSemaphoreExW
0x180003656  mov     rsi, rax
0x180003659  test    rax, rax
0x18000365c  jnz     short loc_180003673
0x18000365e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003663  mov     ebx, eax
0x180003665  test    eax, eax
0x180003667  jns     short loc_1800036A3
0x180003669  mov     edx, 90h
0x18000366e  jmp     loc_1800035D2
0x180003673  call    cs:__imp_GetLastError
0x180003679  mov     rbx, [rdi+8]
0x18000367d  test    rbx, rbx
0x180003680  jz      short loc_18000369F
0x180003682  call    cs:__imp_GetLastError
0x180003688  mov     rcx, rbx; hObject
0x18000368b  mov     ebp, eax
0x18000368d  call    cs:__imp_CloseHandle
0x180003693  test    eax, eax
0x180003695  jz      short loc_1800036D1
0x180003697  mov     ecx, ebp; dwErrCode
0x180003699  call    cs:__imp_SetLastError
0x18000369f  mov     [rdi+8], rsi
0x1800036a3  xor     eax, eax
0x1800036a5  mov     rcx, [rsp+278h+var_38]
0x1800036ad  xor     rcx, rsp; StackCookie
0x1800036b0  call    __security_check_cookie
0x1800036b5  lea     r11, [rsp+278h+var_28]
0x1800036bd  mov     rbx, [r11+38h]
0x1800036c1  mov     rbp, [r11+40h]
0x1800036c5  mov     rsp, r11
0x1800036c8  pop     r15
0x1800036ca  pop     r14
0x1800036cc  pop     r12
0x1800036ce  pop     rdi
0x1800036cf  pop     rsi
0x1800036d0  retn
0x1800036d1  mov     rcx, [rsp+278h]; this
0x1800036d9  mov     edx, 0A0Bh; void *
0x1800036de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036e4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800036ea  mov     rcx, [rsp+278h]; this
0x1800036f2  mov     edx, 0A0Bh; void *
0x1800036f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
