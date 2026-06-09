# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a96c`
- end: `0x18000ab79`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a1f8`
- `0x18000a59c`

## callees

- `0x1800028f0`
- `0x18000a96c`
- `0x18000bc98`
- `0x18000e354`
- `0x18000ed98`
- `0x18000fb7c`
- `0x18000fb8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000aa30`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000aacc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000aa30`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000aacc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aafe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab09`

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
0x18000a96c  mov     [rsp+arg_8], rbx
0x18000a971  mov     [rsp+arg_10], rbp
0x18000a976  push    rsi
0x18000a977  push    rdi
0x18000a978  push    r12
0x18000a97a  push    r14
0x18000a97c  push    r15
0x18000a97e  sub     rsp, 250h
0x18000a985  mov     rax, cs:__security_cookie
0x18000a98c  xor     rax, rsp
0x18000a98f  mov     [rsp+278h+var_38], rax
0x18000a997  mov     rax, 0C000000000000000h
0x18000a9a1  mov     rbp, r9
0x18000a9a4  mov     r8, rdx
0x18000a9a7  mov     rdi, rcx
0x18000a9aa  test    rax, r9
0x18000a9ad  jnz     loc_18000AB60
0x18000a9b3  xor     r12d, r12d
0x18000a9b6  lea     rax, [rsp+278h+Name]
0x18000a9bb  mov     ecx, 7FFFFFFEh
0x18000a9c0  mov     edx, 104h
0x18000a9c5  lea     esi, [r12+1]
0x18000a9ca  test    rcx, rcx
0x18000a9cd  jz      short loc_18000A9ED
0x18000a9cf  movzx   r9d, word ptr [r8]
0x18000a9d3  test    r9w, r9w
0x18000a9d7  jz      short loc_18000A9ED
0x18000a9d9  mov     [rax], r9w
0x18000a9dd  add     r8, 2
0x18000a9e1  add     rax, 2
0x18000a9e5  sub     rcx, rsi
0x18000a9e8  sub     rdx, rsi; unsigned __int64
0x18000a9eb  jnz     short loc_18000A9CA
0x18000a9ed  test    rdx, rdx
0x18000a9f0  lea     rcx, [rax-2]
0x18000a9f4  lea     r8, aP0; "_p0"
0x18000a9fb  cmovnz  rcx, rax
0x18000a9ff  mov     [rcx], r12w
0x18000aa03  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000aa08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aa0d  mov     edx, ebp
0x18000aa0f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000aa17  and     edx, 7FFFFFFFh; lInitialCount
0x18000aa1d  mov     [rsp+278h+dwFlags], r12d; int
0x18000aa22  mov     r8d, esi
0x18000aa25  lea     r9, [rsp+278h+Name]; lpName
0x18000aa2a  cmova   r8d, edx; lMaximumCount
0x18000aa2e  xor     ecx, ecx; lpSemaphoreAttributes
0x18000aa30  call    cs:__imp_CreateSemaphoreExW
0x18000aa36  mov     r15, rax
0x18000aa39  test    rax, rax
0x18000aa3c  jnz     short loc_18000AA65
0x18000aa3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aa43  mov     ebx, eax
0x18000aa45  test    eax, eax
0x18000aa47  jns     short loc_18000AA99
0x18000aa49  mov     edx, 8Bh; void *
0x18000aa4e  mov     rcx, [rsp+278h]; this
0x18000aa56  mov     r9d, ebx; char *
0x18000aa59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa5e  mov     eax, ebx
0x18000aa60  jmp     loc_18000AB21
0x18000aa65  call    cs:__imp_GetLastError
0x18000aa6b  mov     rbx, [rdi]
0x18000aa6e  test    rbx, rbx
0x18000aa71  jz      short loc_18000AA96
0x18000aa73  call    cs:__imp_GetLastError
0x18000aa79  mov     rcx, rbx; hObject
0x18000aa7c  mov     r14d, eax
0x18000aa7f  call    cs:__imp_CloseHandle
0x18000aa85  test    eax, eax
0x18000aa87  jz      loc_18000AB66
0x18000aa8d  mov     ecx, r14d; dwErrCode
0x18000aa90  call    cs:__imp_SetLastError
0x18000aa96  mov     [rdi], r15
0x18000aa99  lea     r8, asc_18002EE40; "h"
0x18000aaa0  shr     rbp, 1Fh
0x18000aaa4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000aaa9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aaae  test    ebp, ebp
0x18000aab0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000aab8  lea     r9, [rsp+278h+Name]; lpName
0x18000aabd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000aac2  cmovnz  esi, ebp
0x18000aac5  mov     edx, ebp; lInitialCount
0x18000aac7  mov     r8d, esi; lMaximumCount
0x18000aaca  xor     ecx, ecx; lpSemaphoreAttributes
0x18000aacc  call    cs:__imp_CreateSemaphoreExW
0x18000aad2  mov     rsi, rax
0x18000aad5  test    rax, rax
0x18000aad8  jnz     short loc_18000AAEF
0x18000aada  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aadf  mov     ebx, eax
0x18000aae1  test    eax, eax
0x18000aae3  jns     short loc_18000AB1F
0x18000aae5  mov     edx, 90h
0x18000aaea  jmp     loc_18000AA4E
0x18000aaef  call    cs:__imp_GetLastError
0x18000aaf5  mov     rbx, [rdi+8]
0x18000aaf9  test    rbx, rbx
0x18000aafc  jz      short loc_18000AB1B
0x18000aafe  call    cs:__imp_GetLastError
0x18000ab04  mov     rcx, rbx; hObject
0x18000ab07  mov     ebp, eax
0x18000ab09  call    cs:__imp_CloseHandle
0x18000ab0f  test    eax, eax
0x18000ab11  jz      short loc_18000AB4D
0x18000ab13  mov     ecx, ebp; dwErrCode
0x18000ab15  call    cs:__imp_SetLastError
0x18000ab1b  mov     [rdi+8], rsi
0x18000ab1f  xor     eax, eax
0x18000ab21  mov     rcx, [rsp+278h+var_38]
0x18000ab29  xor     rcx, rsp; StackCookie
0x18000ab2c  call    __security_check_cookie
0x18000ab31  lea     r11, [rsp+278h+var_28]
0x18000ab39  mov     rbx, [r11+38h]
0x18000ab3d  mov     rbp, [r11+40h]
0x18000ab41  mov     rsp, r11
0x18000ab44  pop     r15
0x18000ab46  pop     r14
0x18000ab48  pop     r12
0x18000ab4a  pop     rdi
0x18000ab4b  pop     rsi
0x18000ab4c  retn
0x18000ab4d  mov     rcx, [rsp+278h]; this
0x18000ab55  mov     edx, 0A0Bh; void *
0x18000ab5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ab60  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ab66  mov     rcx, [rsp+278h]; this
0x18000ab6e  mov     edx, 0A0Bh; void *
0x18000ab73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
