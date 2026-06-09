# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400059c4`
- end: `0x140005bf5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005150`
- `0x14000b964`

## callees

- `0x140002600`
- `0x1400059c4`
- `0x140006898`
- `0x140007dc8`
- `0x140008dd4`
- `0x1400093e8`
- `0x1400093f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005a8d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005b33`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005a8d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005af4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005af4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005b86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005b86`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
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
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400059c4  mov     [rsp+arg_8], rbx
0x1400059c9  push    rbp
0x1400059ca  push    rsi
0x1400059cb  push    rdi
0x1400059cc  push    r12
0x1400059ce  push    r13
0x1400059d0  push    r14
0x1400059d2  push    r15
0x1400059d4  sub     rsp, 250h
0x1400059db  mov     rax, cs:__security_cookie
0x1400059e2  xor     rax, rsp
0x1400059e5  mov     [rsp+288h+var_48], rax
0x1400059ed  mov     rax, 0C000000000000000h
0x1400059f7  mov     rsi, r9
0x1400059fa  mov     r8, rdx
0x1400059fd  mov     rbx, rcx
0x140005a00  test    rax, r9
0x140005a03  jnz     loc_140005BDC
0x140005a09  xor     r12d, r12d
0x140005a0c  lea     rax, [rsp+288h+Name]
0x140005a11  mov     r13d, 104h
0x140005a17  mov     ecx, 7FFFFFFEh
0x140005a1c  mov     edx, r13d
0x140005a1f  lea     ebp, [r12+1]
0x140005a24  test    rcx, rcx
0x140005a27  jz      short loc_140005A47
0x140005a29  movzx   r9d, word ptr [r8]
0x140005a2d  test    r9w, r9w
0x140005a31  jz      short loc_140005A47
0x140005a33  mov     [rax], r9w
0x140005a37  add     r8, 2
0x140005a3b  add     rax, 2
0x140005a3f  sub     rcx, rbp
0x140005a42  sub     rdx, rbp
0x140005a45  jnz     short loc_140005A24
0x140005a47  test    rdx, rdx
0x140005a4a  lea     rcx, [rax-2]
0x140005a4e  lea     r8, aP0; "_p0"
0x140005a55  mov     rdx, r13; unsigned __int64
0x140005a58  cmovnz  rcx, rax
0x140005a5c  mov     [rcx], r12w
0x140005a60  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140005a65  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005a6a  mov     edx, esi
0x140005a6c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005a74  and     edx, 7FFFFFFFh; lInitialCount
0x140005a7a  mov     [rsp+288h+dwFlags], r12d; int
0x140005a7f  mov     r8d, ebp
0x140005a82  lea     r9, [rsp+288h+Name]; lpName
0x140005a87  cmova   r8d, edx; lMaximumCount
0x140005a8b  xor     ecx, ecx; lpSemaphoreAttributes
0x140005a8d  call    cs:__imp_CreateSemaphoreExW
0x140005a93  mov     r15, rax
0x140005a96  test    rax, rax
0x140005a99  jnz     short loc_140005AC9
0x140005a9b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005aa0  mov     edi, eax
0x140005aa2  test    eax, eax
0x140005aa4  jns     short loc_140005AFD
0x140005aa6  mov     rcx, [rsp+288h]; this
0x140005aae  lea     r8, aWil; "wil"
0x140005ab5  mov     r9d, eax; char *
0x140005ab8  mov     edx, 8Bh; void *
0x140005abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005ac2  mov     eax, edi
0x140005ac4  jmp     loc_140005B9E
0x140005ac9  call    cs:__imp_GetLastError
0x140005acf  mov     rdi, [rbx]
0x140005ad2  test    rdi, rdi
0x140005ad5  jz      short loc_140005AFA
0x140005ad7  call    cs:__imp_GetLastError
0x140005add  mov     rcx, rdi; hObject
0x140005ae0  mov     r14d, eax
0x140005ae3  call    cs:__imp_CloseHandle
0x140005ae9  test    eax, eax
0x140005aeb  jz      loc_140005BE2
0x140005af1  mov     ecx, r14d; dwErrCode
0x140005af4  call    cs:__imp_SetLastError
0x140005afa  mov     [rbx], r15
0x140005afd  lea     r8, asc_14001F2F0; "h"
0x140005b04  shr     rsi, 1Fh
0x140005b08  mov     rdx, r13; unsigned __int64
0x140005b0b  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140005b10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005b15  test    esi, esi
0x140005b17  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005b1f  lea     r9, [rsp+288h+Name]; lpName
0x140005b24  mov     [rsp+288h+dwFlags], r12d; int
0x140005b29  cmovnz  ebp, esi
0x140005b2c  mov     edx, esi; lInitialCount
0x140005b2e  mov     r8d, ebp; lMaximumCount
0x140005b31  xor     ecx, ecx; lpSemaphoreAttributes
0x140005b33  call    cs:__imp_CreateSemaphoreExW
0x140005b39  mov     rbp, rax
0x140005b3c  test    rax, rax
0x140005b3f  jnz     short loc_140005B6C
0x140005b41  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005b46  mov     ebx, eax
0x140005b48  test    eax, eax
0x140005b4a  jns     short loc_140005B9C
0x140005b4c  mov     rcx, [rsp+288h]; this
0x140005b54  lea     r8, aWil; "wil"
0x140005b5b  mov     r9d, eax; char *
0x140005b5e  mov     edx, 90h; void *
0x140005b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005b68  mov     eax, ebx
0x140005b6a  jmp     short loc_140005B9E
0x140005b6c  call    cs:__imp_GetLastError
0x140005b72  mov     rdi, [rbx+8]
0x140005b76  test    rdi, rdi
0x140005b79  jz      short loc_140005B98
0x140005b7b  call    cs:__imp_GetLastError
0x140005b81  mov     rcx, rdi; hObject
0x140005b84  mov     esi, eax
0x140005b86  call    cs:__imp_CloseHandle
0x140005b8c  test    eax, eax
0x140005b8e  jz      short loc_140005BC9
0x140005b90  mov     ecx, esi; dwErrCode
0x140005b92  call    cs:__imp_SetLastError
0x140005b98  mov     [rbx+8], rbp
0x140005b9c  xor     eax, eax
0x140005b9e  mov     rcx, [rsp+288h+var_48]
0x140005ba6  xor     rcx, rsp; StackCookie
0x140005ba9  call    __security_check_cookie
0x140005bae  mov     rbx, [rsp+288h+arg_8]
0x140005bb6  add     rsp, 250h
0x140005bbd  pop     r15
0x140005bbf  pop     r14
0x140005bc1  pop     r13
0x140005bc3  pop     r12
0x140005bc5  pop     rdi
0x140005bc6  pop     rsi
0x140005bc7  pop     rbp
0x140005bc8  retn
0x140005bc9  mov     rcx, [rsp+288h]; this
0x140005bd1  mov     edx, 0A0Bh; void *
0x140005bd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005bdc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005be2  mov     rcx, [rsp+288h]; this
0x140005bea  mov     edx, 0A0Bh; void *
0x140005bef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
