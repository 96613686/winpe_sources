# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800071a0`
- end: `0x1800073ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006238`

## callees

- `0x180004180`
- `0x1800071a0`
- `0x180007e98`
- `0x18000a024`
- `0x18000a9b4`
- `0x18000b1c4`
- `0x18000b1d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007307`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007366`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800072cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000734f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000734f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735a`

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
0x1800071a0  mov     [rsp+arg_8], rbx
0x1800071a5  mov     [rsp+arg_10], rbp
0x1800071aa  push    rsi
0x1800071ab  push    rdi
0x1800071ac  push    r12
0x1800071ae  push    r14
0x1800071b0  push    r15
0x1800071b2  sub     rsp, 250h
0x1800071b9  mov     rax, cs:__security_cookie
0x1800071c0  xor     rax, rsp
0x1800071c3  mov     [rsp+278h+var_38], rax
0x1800071cb  mov     rax, 0C000000000000000h
0x1800071d5  mov     rbp, r9
0x1800071d8  mov     r8, rdx
0x1800071db  mov     rbx, rcx
0x1800071de  test    rax, r9
0x1800071e1  jnz     loc_1800073B1
0x1800071e7  xor     r12d, r12d
0x1800071ea  lea     rax, [rsp+278h+Name]
0x1800071ef  mov     ecx, 7FFFFFFEh
0x1800071f4  mov     edx, 104h
0x1800071f9  lea     esi, [r12+1]
0x1800071fe  test    rcx, rcx
0x180007201  jz      short loc_180007221
0x180007203  movzx   r9d, word ptr [r8]
0x180007207  test    r9w, r9w
0x18000720b  jz      short loc_180007221
0x18000720d  mov     [rax], r9w
0x180007211  add     r8, 2
0x180007215  add     rax, 2
0x180007219  sub     rcx, rsi
0x18000721c  sub     rdx, rsi; unsigned __int64
0x18000721f  jnz     short loc_1800071FE
0x180007221  test    rdx, rdx
0x180007224  lea     rcx, [rax-2]
0x180007228  lea     r8, aP0; "_p0"
0x18000722f  cmovnz  rcx, rax
0x180007233  mov     [rcx], r12w
0x180007237  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000723c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007241  mov     edx, ebp
0x180007243  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000724b  and     edx, 7FFFFFFFh; lInitialCount
0x180007251  mov     [rsp+278h+dwFlags], r12d; int
0x180007256  mov     r8d, esi
0x180007259  lea     r9, [rsp+278h+Name]; lpName
0x18000725e  cmova   r8d, edx; lMaximumCount
0x180007262  xor     ecx, ecx; lpSemaphoreAttributes
0x180007264  call    cs:__imp_CreateSemaphoreExW
0x18000726a  mov     r15, rax
0x18000726d  test    rax, rax
0x180007270  jnz     short loc_1800072A0
0x180007272  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007277  mov     edi, eax
0x180007279  test    eax, eax
0x18000727b  jns     short loc_1800072D4
0x18000727d  mov     rcx, [rsp+278h]; this
0x180007285  lea     r8, aWil; "wil"
0x18000728c  mov     r9d, eax; char *
0x18000728f  mov     edx, 8Bh; void *
0x180007294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007299  mov     eax, edi
0x18000729b  jmp     loc_180007372
0x1800072a0  call    cs:__imp_GetLastError
0x1800072a6  mov     rdi, [rbx]
0x1800072a9  test    rdi, rdi
0x1800072ac  jz      short loc_1800072D1
0x1800072ae  call    cs:__imp_GetLastError
0x1800072b4  mov     rcx, rdi; hObject
0x1800072b7  mov     r14d, eax
0x1800072ba  call    cs:__imp_CloseHandle
0x1800072c0  test    eax, eax
0x1800072c2  jz      loc_1800073B7
0x1800072c8  mov     ecx, r14d; dwErrCode
0x1800072cb  call    cs:__imp_SetLastError
0x1800072d1  mov     [rbx], r15
0x1800072d4  lea     r8, asc_180051C18; "h"
0x1800072db  shr     rbp, 1Fh
0x1800072df  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800072e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800072e9  test    ebp, ebp
0x1800072eb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800072f3  lea     r9, [rsp+278h+Name]; lpName
0x1800072f8  mov     [rsp+278h+dwFlags], r12d; int
0x1800072fd  cmovnz  esi, ebp
0x180007300  mov     edx, ebp; lInitialCount
0x180007302  mov     r8d, esi; lMaximumCount
0x180007305  xor     ecx, ecx; lpSemaphoreAttributes
0x180007307  call    cs:__imp_CreateSemaphoreExW
0x18000730d  mov     rsi, rax
0x180007310  test    rax, rax
0x180007313  jnz     short loc_180007340
0x180007315  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000731a  mov     ebx, eax
0x18000731c  test    eax, eax
0x18000731e  jns     short loc_180007370
0x180007320  mov     rcx, [rsp+278h]; this
0x180007328  lea     r8, aWil; "wil"
0x18000732f  mov     r9d, eax; char *
0x180007332  mov     edx, 90h; void *
0x180007337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000733c  mov     eax, ebx
0x18000733e  jmp     short loc_180007372
0x180007340  call    cs:__imp_GetLastError
0x180007346  mov     rdi, [rbx+8]
0x18000734a  test    rdi, rdi
0x18000734d  jz      short loc_18000736C
0x18000734f  call    cs:__imp_GetLastError
0x180007355  mov     rcx, rdi; hObject
0x180007358  mov     ebp, eax
0x18000735a  call    cs:__imp_CloseHandle
0x180007360  test    eax, eax
0x180007362  jz      short loc_18000739E
0x180007364  mov     ecx, ebp; dwErrCode
0x180007366  call    cs:__imp_SetLastError
0x18000736c  mov     [rbx+8], rsi
0x180007370  xor     eax, eax
0x180007372  mov     rcx, [rsp+278h+var_38]
0x18000737a  xor     rcx, rsp; StackCookie
0x18000737d  call    __security_check_cookie
0x180007382  lea     r11, [rsp+278h+var_28]
0x18000738a  mov     rbx, [r11+38h]
0x18000738e  mov     rbp, [r11+40h]
0x180007392  mov     rsp, r11
0x180007395  pop     r15
0x180007397  pop     r14
0x180007399  pop     r12
0x18000739b  pop     rdi
0x18000739c  pop     rsi
0x18000739d  retn
0x18000739e  mov     rcx, [rsp+278h]; this
0x1800073a6  mov     edx, 0A0Bh; void *
0x1800073ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800073b7  mov     rcx, [rsp+278h]; this
0x1800073bf  mov     edx, 0A0Bh; void *
0x1800073c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
