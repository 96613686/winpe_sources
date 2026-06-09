# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000b734`
- end: `0x18000b95e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b298`
- `0x180010e64`

## callees

- `0x1800060a0`
- `0x18000b734`
- `0x18000c1c8`
- `0x18000d294`
- `0x18000dbd4`
- `0x18000e58c`
- `0x18000e59c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b85f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b85f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8ee`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b7f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b89b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b7f8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b89b`

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
0x18000b734  mov     [rsp+arg_8], rbx
0x18000b739  mov     [rsp+arg_10], rbp
0x18000b73e  push    rsi
0x18000b73f  push    rdi
0x18000b740  push    r12
0x18000b742  push    r14
0x18000b744  push    r15
0x18000b746  sub     rsp, 250h
0x18000b74d  mov     rax, cs:__security_cookie
0x18000b754  xor     rax, rsp
0x18000b757  mov     [rsp+278h+var_38], rax
0x18000b75f  mov     rax, 0C000000000000000h
0x18000b769  mov     rbp, r9
0x18000b76c  mov     r8, rdx
0x18000b76f  mov     rbx, rcx
0x18000b772  test    rax, r9
0x18000b775  jnz     loc_18000B945
0x18000b77b  xor     r12d, r12d
0x18000b77e  lea     rax, [rsp+278h+Name]
0x18000b783  mov     ecx, 7FFFFFFEh
0x18000b788  mov     edx, 104h
0x18000b78d  lea     esi, [r12+1]
0x18000b792  test    rcx, rcx
0x18000b795  jz      short loc_18000B7B5
0x18000b797  movzx   r9d, word ptr [r8]
0x18000b79b  test    r9w, r9w
0x18000b79f  jz      short loc_18000B7B5
0x18000b7a1  mov     [rax], r9w
0x18000b7a5  add     r8, 2
0x18000b7a9  add     rax, 2
0x18000b7ad  sub     rcx, rsi
0x18000b7b0  sub     rdx, rsi; unsigned __int64
0x18000b7b3  jnz     short loc_18000B792
0x18000b7b5  test    rdx, rdx
0x18000b7b8  lea     rcx, [rax-2]
0x18000b7bc  lea     r8, aP0; "_p0"
0x18000b7c3  cmovnz  rcx, rax
0x18000b7c7  mov     [rcx], r12w
0x18000b7cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000b7d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b7d5  mov     edx, ebp
0x18000b7d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b7df  and     edx, 7FFFFFFFh; lInitialCount
0x18000b7e5  mov     [rsp+278h+dwFlags], r12d; int
0x18000b7ea  mov     r8d, esi
0x18000b7ed  lea     r9, [rsp+278h+Name]; lpName
0x18000b7f2  cmova   r8d, edx; lMaximumCount
0x18000b7f6  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b7f8  call    cs:__imp_CreateSemaphoreExW
0x18000b7fe  mov     r15, rax
0x18000b801  test    rax, rax
0x18000b804  jnz     short loc_18000B834
0x18000b806  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b80b  mov     edi, eax
0x18000b80d  test    eax, eax
0x18000b80f  jns     short loc_18000B868
0x18000b811  mov     rcx, [rsp+278h]; this
0x18000b819  lea     r8, aWil; "wil"
0x18000b820  mov     r9d, eax; char *
0x18000b823  mov     edx, 8Bh; void *
0x18000b828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b82d  mov     eax, edi
0x18000b82f  jmp     loc_18000B906
0x18000b834  call    cs:__imp_GetLastError
0x18000b83a  mov     rdi, [rbx]
0x18000b83d  test    rdi, rdi
0x18000b840  jz      short loc_18000B865
0x18000b842  call    cs:__imp_GetLastError
0x18000b848  mov     rcx, rdi; hObject
0x18000b84b  mov     r14d, eax
0x18000b84e  call    cs:__imp_CloseHandle
0x18000b854  test    eax, eax
0x18000b856  jz      loc_18000B94B
0x18000b85c  mov     ecx, r14d; dwErrCode
0x18000b85f  call    cs:__imp_SetLastError
0x18000b865  mov     [rbx], r15
0x18000b868  lea     r8, asc_1800B76E0; "h"
0x18000b86f  shr     rbp, 1Fh
0x18000b873  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000b878  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b87d  test    ebp, ebp
0x18000b87f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b887  lea     r9, [rsp+278h+Name]; lpName
0x18000b88c  mov     [rsp+278h+dwFlags], r12d; int
0x18000b891  cmovnz  esi, ebp
0x18000b894  mov     edx, ebp; lInitialCount
0x18000b896  mov     r8d, esi; lMaximumCount
0x18000b899  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b89b  call    cs:__imp_CreateSemaphoreExW
0x18000b8a1  mov     rsi, rax
0x18000b8a4  test    rax, rax
0x18000b8a7  jnz     short loc_18000B8D4
0x18000b8a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b8ae  mov     ebx, eax
0x18000b8b0  test    eax, eax
0x18000b8b2  jns     short loc_18000B904
0x18000b8b4  mov     rcx, [rsp+278h]; this
0x18000b8bc  lea     r8, aWil; "wil"
0x18000b8c3  mov     r9d, eax; char *
0x18000b8c6  mov     edx, 90h; void *
0x18000b8cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8d0  mov     eax, ebx
0x18000b8d2  jmp     short loc_18000B906
0x18000b8d4  call    cs:__imp_GetLastError
0x18000b8da  mov     rdi, [rbx+8]
0x18000b8de  test    rdi, rdi
0x18000b8e1  jz      short loc_18000B900
0x18000b8e3  call    cs:__imp_GetLastError
0x18000b8e9  mov     rcx, rdi; hObject
0x18000b8ec  mov     ebp, eax
0x18000b8ee  call    cs:__imp_CloseHandle
0x18000b8f4  test    eax, eax
0x18000b8f6  jz      short loc_18000B932
0x18000b8f8  mov     ecx, ebp; dwErrCode
0x18000b8fa  call    cs:__imp_SetLastError
0x18000b900  mov     [rbx+8], rsi
0x18000b904  xor     eax, eax
0x18000b906  mov     rcx, [rsp+278h+var_38]
0x18000b90e  xor     rcx, rsp; StackCookie
0x18000b911  call    __security_check_cookie
0x18000b916  lea     r11, [rsp+278h+var_28]
0x18000b91e  mov     rbx, [r11+38h]
0x18000b922  mov     rbp, [r11+40h]
0x18000b926  mov     rsp, r11
0x18000b929  pop     r15
0x18000b92b  pop     r14
0x18000b92d  pop     r12
0x18000b92f  pop     rdi
0x18000b930  pop     rsi
0x18000b931  retn
0x18000b932  mov     rcx, [rsp+278h]; this
0x18000b93a  mov     edx, 0A0Bh; void *
0x18000b93f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b945  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b94b  mov     rcx, [rsp+278h]; this
0x18000b953  mov     edx, 0A0Bh; void *
0x18000b958  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
