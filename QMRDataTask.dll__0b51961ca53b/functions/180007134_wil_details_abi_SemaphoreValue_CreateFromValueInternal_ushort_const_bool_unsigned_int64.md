# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007134`
- end: `0x180007341`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006108`
- `0x1800064ac`

## callees

- `0x180007134`
- `0x180009d44`
- `0x18000df84`
- `0x180010548`
- `0x18001138c`
- `0x18001139c`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000722d`
- `KERNEL32!GetLastError` at `0x18000723b`
- `KERNEL32!GetLastError` at `0x1800072b7`
- `KERNEL32!GetLastError` at `0x1800072c6`
- `KERNEL32!GetLastError` at `0x18000722d`
- `KERNEL32!GetLastError` at `0x18000723b`
- `KERNEL32!GetLastError` at `0x1800072b7`
- `KERNEL32!GetLastError` at `0x1800072c6`
- `KERNEL32!CloseHandle` at `0x180007247`
- `KERNEL32!CloseHandle` at `0x1800072d1`
- `KERNEL32!CloseHandle` at `0x180007247`
- `KERNEL32!CloseHandle` at `0x1800072d1`
- `KERNEL32!CreateSemaphoreExW` at `0x1800071f8`
- `KERNEL32!CreateSemaphoreExW` at `0x180007294`
- `KERNEL32!CreateSemaphoreExW` at `0x1800071f8`
- `KERNEL32!CreateSemaphoreExW` at `0x180007294`
- `KERNEL32!SetLastError` at `0x180007258`
- `KERNEL32!SetLastError` at `0x1800072dd`
- `KERNEL32!SetLastError` at `0x180007258`
- `KERNEL32!SetLastError` at `0x1800072dd`

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
0x180007134  mov     [rsp+arg_8], rbx
0x180007139  mov     [rsp+arg_10], rbp
0x18000713e  push    rsi
0x18000713f  push    rdi
0x180007140  push    r12
0x180007142  push    r14
0x180007144  push    r15
0x180007146  sub     rsp, 250h
0x18000714d  mov     rax, cs:__security_cookie
0x180007154  xor     rax, rsp
0x180007157  mov     [rsp+278h+var_38], rax
0x18000715f  mov     rax, 0C000000000000000h
0x180007169  mov     rbp, r9
0x18000716c  mov     r8, rdx
0x18000716f  mov     rdi, rcx
0x180007172  test    rax, r9
0x180007175  jnz     loc_180007328
0x18000717b  xor     r12d, r12d
0x18000717e  lea     rax, [rsp+278h+Name]
0x180007183  mov     ecx, 7FFFFFFEh
0x180007188  mov     edx, 104h
0x18000718d  lea     esi, [r12+1]
0x180007192  test    rcx, rcx
0x180007195  jz      short loc_1800071B5
0x180007197  movzx   r9d, word ptr [r8]
0x18000719b  test    r9w, r9w
0x18000719f  jz      short loc_1800071B5
0x1800071a1  mov     [rax], r9w
0x1800071a5  add     r8, 2
0x1800071a9  add     rax, 2
0x1800071ad  sub     rcx, rsi
0x1800071b0  sub     rdx, rsi; unsigned __int64
0x1800071b3  jnz     short loc_180007192
0x1800071b5  test    rdx, rdx
0x1800071b8  lea     rcx, [rax-2]
0x1800071bc  lea     r8, aP0; "_p0"
0x1800071c3  cmovnz  rcx, rax
0x1800071c7  mov     [rcx], r12w
0x1800071cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800071d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071d5  mov     edx, ebp
0x1800071d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800071df  and     edx, 7FFFFFFFh; lInitialCount
0x1800071e5  mov     [rsp+278h+dwFlags], r12d; int
0x1800071ea  mov     r8d, esi
0x1800071ed  lea     r9, [rsp+278h+Name]; lpName
0x1800071f2  cmova   r8d, edx; lMaximumCount
0x1800071f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800071f8  call    cs:__imp_CreateSemaphoreExW
0x1800071fe  mov     r15, rax
0x180007201  test    rax, rax
0x180007204  jnz     short loc_18000722D
0x180007206  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000720b  mov     ebx, eax
0x18000720d  test    eax, eax
0x18000720f  jns     short loc_180007261
0x180007211  mov     edx, 8Bh; void *
0x180007216  mov     rcx, [rsp+278h]; this
0x18000721e  mov     r9d, ebx; char *
0x180007221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007226  mov     eax, ebx
0x180007228  jmp     loc_1800072E9
0x18000722d  call    cs:__imp_GetLastError
0x180007233  mov     rbx, [rdi]
0x180007236  test    rbx, rbx
0x180007239  jz      short loc_18000725E
0x18000723b  call    cs:__imp_GetLastError
0x180007241  mov     rcx, rbx; hObject
0x180007244  mov     r14d, eax
0x180007247  call    cs:__imp_CloseHandle
0x18000724d  test    eax, eax
0x18000724f  jz      loc_18000732E
0x180007255  mov     ecx, r14d; dwErrCode
0x180007258  call    cs:__imp_SetLastError
0x18000725e  mov     [rdi], r15
0x180007261  lea     r8, asc_180018C38; "h"
0x180007268  shr     rbp, 1Fh
0x18000726c  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007271  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007276  test    ebp, ebp
0x180007278  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007280  lea     r9, [rsp+278h+Name]; lpName
0x180007285  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000728a  cmovnz  esi, ebp
0x18000728d  mov     edx, ebp; lInitialCount
0x18000728f  mov     r8d, esi; lMaximumCount
0x180007292  xor     ecx, ecx; lpSemaphoreAttributes
0x180007294  call    cs:__imp_CreateSemaphoreExW
0x18000729a  mov     rsi, rax
0x18000729d  test    rax, rax
0x1800072a0  jnz     short loc_1800072B7
0x1800072a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800072a7  mov     ebx, eax
0x1800072a9  test    eax, eax
0x1800072ab  jns     short loc_1800072E7
0x1800072ad  mov     edx, 90h
0x1800072b2  jmp     loc_180007216
0x1800072b7  call    cs:__imp_GetLastError
0x1800072bd  mov     rbx, [rdi+8]
0x1800072c1  test    rbx, rbx
0x1800072c4  jz      short loc_1800072E3
0x1800072c6  call    cs:__imp_GetLastError
0x1800072cc  mov     rcx, rbx; hObject
0x1800072cf  mov     ebp, eax
0x1800072d1  call    cs:__imp_CloseHandle
0x1800072d7  test    eax, eax
0x1800072d9  jz      short loc_180007315
0x1800072db  mov     ecx, ebp; dwErrCode
0x1800072dd  call    cs:__imp_SetLastError
0x1800072e3  mov     [rdi+8], rsi
0x1800072e7  xor     eax, eax
0x1800072e9  mov     rcx, [rsp+278h+var_38]
0x1800072f1  xor     rcx, rsp; StackCookie
0x1800072f4  call    __security_check_cookie
0x1800072f9  lea     r11, [rsp+278h+var_28]
0x180007301  mov     rbx, [r11+38h]
0x180007305  mov     rbp, [r11+40h]
0x180007309  mov     rsp, r11
0x18000730c  pop     r15
0x18000730e  pop     r14
0x180007310  pop     r12
0x180007312  pop     rdi
0x180007313  pop     rsi
0x180007314  retn
0x180007315  mov     rcx, [rsp+278h]; this
0x18000731d  mov     edx, 0A0Bh; void *
0x180007322  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007328  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000732e  mov     rcx, [rsp+278h]; this
0x180007336  mov     edx, 0A0Bh; void *
0x18000733b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
