# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140009108`
- end: `0x140009315`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008a58`
- `0x14000fe64`

## callees

- `0x140002310`
- `0x140009108`
- `0x140009b40`
- `0x14000bf34`
- `0x14000d0cc`
- `0x14000e394`
- `0x14000e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400091cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009268`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400091cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000920f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000928b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000929a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000920f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000928b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000929a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000922c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400092b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000922c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400092b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000921b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000921b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092a5`

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
0x140009108  mov     [rsp+arg_8], rbx
0x14000910d  mov     [rsp+arg_10], rbp
0x140009112  push    rsi
0x140009113  push    rdi
0x140009114  push    r12
0x140009116  push    r14
0x140009118  push    r15
0x14000911a  sub     rsp, 250h
0x140009121  mov     rax, cs:__security_cookie
0x140009128  xor     rax, rsp
0x14000912b  mov     [rsp+278h+var_38], rax
0x140009133  mov     rax, 0C000000000000000h
0x14000913d  mov     rbp, r9
0x140009140  mov     r8, rdx
0x140009143  mov     rdi, rcx
0x140009146  test    rax, r9
0x140009149  jnz     loc_1400092FC
0x14000914f  xor     r12d, r12d
0x140009152  lea     rax, [rsp+278h+Name]
0x140009157  mov     ecx, 7FFFFFFEh
0x14000915c  mov     edx, 104h
0x140009161  lea     esi, [r12+1]
0x140009166  test    rcx, rcx
0x140009169  jz      short loc_140009189
0x14000916b  movzx   r9d, word ptr [r8]
0x14000916f  test    r9w, r9w
0x140009173  jz      short loc_140009189
0x140009175  mov     [rax], r9w
0x140009179  add     r8, 2
0x14000917d  add     rax, 2
0x140009181  sub     rcx, rsi
0x140009184  sub     rdx, rsi; unsigned __int64
0x140009187  jnz     short loc_140009166
0x140009189  test    rdx, rdx
0x14000918c  lea     rcx, [rax-2]
0x140009190  lea     r8, aP0; "_p0"
0x140009197  cmovnz  rcx, rax
0x14000919b  mov     [rcx], r12w
0x14000919f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400091a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400091a9  mov     edx, ebp
0x1400091ab  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400091b3  and     edx, 7FFFFFFFh; lInitialCount
0x1400091b9  mov     [rsp+278h+dwFlags], r12d; int
0x1400091be  mov     r8d, esi
0x1400091c1  lea     r9, [rsp+278h+Name]; lpName
0x1400091c6  cmova   r8d, edx; lMaximumCount
0x1400091ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1400091cc  call    cs:__imp_CreateSemaphoreExW
0x1400091d2  mov     r15, rax
0x1400091d5  test    rax, rax
0x1400091d8  jnz     short loc_140009201
0x1400091da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400091df  mov     ebx, eax
0x1400091e1  test    eax, eax
0x1400091e3  jns     short loc_140009235
0x1400091e5  mov     edx, 8Bh; void *
0x1400091ea  mov     rcx, [rsp+278h]; this
0x1400091f2  mov     r9d, ebx; char *
0x1400091f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091fa  mov     eax, ebx
0x1400091fc  jmp     loc_1400092BD
0x140009201  call    cs:__imp_GetLastError
0x140009207  mov     rbx, [rdi]
0x14000920a  test    rbx, rbx
0x14000920d  jz      short loc_140009232
0x14000920f  call    cs:__imp_GetLastError
0x140009215  mov     rcx, rbx; hObject
0x140009218  mov     r14d, eax
0x14000921b  call    cs:__imp_CloseHandle
0x140009221  test    eax, eax
0x140009223  jz      loc_140009302
0x140009229  mov     ecx, r14d; dwErrCode
0x14000922c  call    cs:__imp_SetLastError
0x140009232  mov     [rdi], r15
0x140009235  lea     r8, asc_140027680; "h"
0x14000923c  shr     rbp, 1Fh
0x140009240  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140009245  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000924a  test    ebp, ebp
0x14000924c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009254  lea     r9, [rsp+278h+Name]; lpName
0x140009259  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14000925e  cmovnz  esi, ebp
0x140009261  mov     edx, ebp; lInitialCount
0x140009263  mov     r8d, esi; lMaximumCount
0x140009266  xor     ecx, ecx; lpSemaphoreAttributes
0x140009268  call    cs:__imp_CreateSemaphoreExW
0x14000926e  mov     rsi, rax
0x140009271  test    rax, rax
0x140009274  jnz     short loc_14000928B
0x140009276  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000927b  mov     ebx, eax
0x14000927d  test    eax, eax
0x14000927f  jns     short loc_1400092BB
0x140009281  mov     edx, 90h
0x140009286  jmp     loc_1400091EA
0x14000928b  call    cs:__imp_GetLastError
0x140009291  mov     rbx, [rdi+8]
0x140009295  test    rbx, rbx
0x140009298  jz      short loc_1400092B7
0x14000929a  call    cs:__imp_GetLastError
0x1400092a0  mov     rcx, rbx; hObject
0x1400092a3  mov     ebp, eax
0x1400092a5  call    cs:__imp_CloseHandle
0x1400092ab  test    eax, eax
0x1400092ad  jz      short loc_1400092E9
0x1400092af  mov     ecx, ebp; dwErrCode
0x1400092b1  call    cs:__imp_SetLastError
0x1400092b7  mov     [rdi+8], rsi
0x1400092bb  xor     eax, eax
0x1400092bd  mov     rcx, [rsp+278h+var_38]
0x1400092c5  xor     rcx, rsp; StackCookie
0x1400092c8  call    __security_check_cookie
0x1400092cd  lea     r11, [rsp+278h+var_28]
0x1400092d5  mov     rbx, [r11+38h]
0x1400092d9  mov     rbp, [r11+40h]
0x1400092dd  mov     rsp, r11
0x1400092e0  pop     r15
0x1400092e2  pop     r14
0x1400092e4  pop     r12
0x1400092e6  pop     rdi
0x1400092e7  pop     rsi
0x1400092e8  retn
0x1400092e9  mov     rcx, [rsp+278h]; this
0x1400092f1  mov     edx, 0A0Bh; void *
0x1400092f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400092fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009302  mov     rcx, [rsp+278h]; this
0x14000930a  mov     edx, 0A0Bh; void *
0x14000930f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
