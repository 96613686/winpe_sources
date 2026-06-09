# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005ac0`
- end: `0x180005cea`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b58`

## callees

- `0x180002e70`
- `0x180005ac0`
- `0x180006798`
- `0x180008924`
- `0x1800092b4`
- `0x180009ac4`
- `0x180009ad4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b84`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005c27`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b84`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005beb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005beb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c7a`

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
0x180005ac0  mov     [rsp+arg_8], rbx
0x180005ac5  mov     [rsp+arg_10], rbp
0x180005aca  push    rsi
0x180005acb  push    rdi
0x180005acc  push    r12
0x180005ace  push    r14
0x180005ad0  push    r15
0x180005ad2  sub     rsp, 250h
0x180005ad9  mov     rax, cs:__security_cookie
0x180005ae0  xor     rax, rsp
0x180005ae3  mov     [rsp+278h+var_38], rax
0x180005aeb  mov     rax, 0C000000000000000h
0x180005af5  mov     rbp, r9
0x180005af8  mov     r8, rdx
0x180005afb  mov     rbx, rcx
0x180005afe  test    rax, r9
0x180005b01  jnz     loc_180005CD1
0x180005b07  xor     r12d, r12d
0x180005b0a  lea     rax, [rsp+278h+Name]
0x180005b0f  mov     ecx, 7FFFFFFEh
0x180005b14  mov     edx, 104h
0x180005b19  lea     esi, [r12+1]
0x180005b1e  test    rcx, rcx
0x180005b21  jz      short loc_180005B41
0x180005b23  movzx   r9d, word ptr [r8]
0x180005b27  test    r9w, r9w
0x180005b2b  jz      short loc_180005B41
0x180005b2d  mov     [rax], r9w
0x180005b31  add     r8, 2
0x180005b35  add     rax, 2
0x180005b39  sub     rcx, rsi
0x180005b3c  sub     rdx, rsi; unsigned __int64
0x180005b3f  jnz     short loc_180005B1E
0x180005b41  test    rdx, rdx
0x180005b44  lea     rcx, [rax-2]
0x180005b48  lea     r8, aP0; "_p0"
0x180005b4f  cmovnz  rcx, rax
0x180005b53  mov     [rcx], r12w
0x180005b57  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005b5c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005b61  mov     edx, ebp
0x180005b63  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005b6b  and     edx, 7FFFFFFFh; lInitialCount
0x180005b71  mov     [rsp+278h+dwFlags], r12d; int
0x180005b76  mov     r8d, esi
0x180005b79  lea     r9, [rsp+278h+Name]; lpName
0x180005b7e  cmova   r8d, edx; lMaximumCount
0x180005b82  xor     ecx, ecx; lpSemaphoreAttributes
0x180005b84  call    cs:__imp_CreateSemaphoreExW
0x180005b8a  mov     r15, rax
0x180005b8d  test    rax, rax
0x180005b90  jnz     short loc_180005BC0
0x180005b92  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b97  mov     edi, eax
0x180005b99  test    eax, eax
0x180005b9b  jns     short loc_180005BF4
0x180005b9d  mov     rcx, [rsp+278h]; this
0x180005ba5  lea     r8, aWil; "wil"
0x180005bac  mov     r9d, eax; char *
0x180005baf  mov     edx, 8Bh; void *
0x180005bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bb9  mov     eax, edi
0x180005bbb  jmp     loc_180005C92
0x180005bc0  call    cs:__imp_GetLastError
0x180005bc6  mov     rdi, [rbx]
0x180005bc9  test    rdi, rdi
0x180005bcc  jz      short loc_180005BF1
0x180005bce  call    cs:__imp_GetLastError
0x180005bd4  mov     rcx, rdi; hObject
0x180005bd7  mov     r14d, eax
0x180005bda  call    cs:__imp_CloseHandle
0x180005be0  test    eax, eax
0x180005be2  jz      loc_180005CD7
0x180005be8  mov     ecx, r14d; dwErrCode
0x180005beb  call    cs:__imp_SetLastError
0x180005bf1  mov     [rbx], r15
0x180005bf4  lea     r8, asc_180015510; "h"
0x180005bfb  shr     rbp, 1Fh
0x180005bff  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005c04  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005c09  test    ebp, ebp
0x180005c0b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005c13  lea     r9, [rsp+278h+Name]; lpName
0x180005c18  mov     [rsp+278h+dwFlags], r12d; int
0x180005c1d  cmovnz  esi, ebp
0x180005c20  mov     edx, ebp; lInitialCount
0x180005c22  mov     r8d, esi; lMaximumCount
0x180005c25  xor     ecx, ecx; lpSemaphoreAttributes
0x180005c27  call    cs:__imp_CreateSemaphoreExW
0x180005c2d  mov     rsi, rax
0x180005c30  test    rax, rax
0x180005c33  jnz     short loc_180005C60
0x180005c35  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005c3a  mov     ebx, eax
0x180005c3c  test    eax, eax
0x180005c3e  jns     short loc_180005C90
0x180005c40  mov     rcx, [rsp+278h]; this
0x180005c48  lea     r8, aWil; "wil"
0x180005c4f  mov     r9d, eax; char *
0x180005c52  mov     edx, 90h; void *
0x180005c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c5c  mov     eax, ebx
0x180005c5e  jmp     short loc_180005C92
0x180005c60  call    cs:__imp_GetLastError
0x180005c66  mov     rdi, [rbx+8]
0x180005c6a  test    rdi, rdi
0x180005c6d  jz      short loc_180005C8C
0x180005c6f  call    cs:__imp_GetLastError
0x180005c75  mov     rcx, rdi; hObject
0x180005c78  mov     ebp, eax
0x180005c7a  call    cs:__imp_CloseHandle
0x180005c80  test    eax, eax
0x180005c82  jz      short loc_180005CBE
0x180005c84  mov     ecx, ebp; dwErrCode
0x180005c86  call    cs:__imp_SetLastError
0x180005c8c  mov     [rbx+8], rsi
0x180005c90  xor     eax, eax
0x180005c92  mov     rcx, [rsp+278h+var_38]
0x180005c9a  xor     rcx, rsp; StackCookie
0x180005c9d  call    __security_check_cookie
0x180005ca2  lea     r11, [rsp+278h+var_28]
0x180005caa  mov     rbx, [r11+38h]
0x180005cae  mov     rbp, [r11+40h]
0x180005cb2  mov     rsp, r11
0x180005cb5  pop     r15
0x180005cb7  pop     r14
0x180005cb9  pop     r12
0x180005cbb  pop     rdi
0x180005cbc  pop     rsi
0x180005cbd  retn
0x180005cbe  mov     rcx, [rsp+278h]; this
0x180005cc6  mov     edx, 0A0Bh; void *
0x180005ccb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cd1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005cd7  mov     rcx, [rsp+278h]; this
0x180005cdf  mov     edx, 0A0Bh; void *
0x180005ce4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
