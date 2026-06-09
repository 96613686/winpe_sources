# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800049f0`
- end: `0x180004c1a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a88`

## callees

- `0x180002000`
- `0x1800049f0`
- `0x1800056c8`
- `0x180007864`
- `0x1800081f4`
- `0x180008a04`
- `0x180008a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ab4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004b57`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ab4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004b57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004baa`

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
0x1800049f0  mov     [rsp+arg_8], rbx
0x1800049f5  mov     [rsp+arg_10], rbp
0x1800049fa  push    rsi
0x1800049fb  push    rdi
0x1800049fc  push    r12
0x1800049fe  push    r14
0x180004a00  push    r15
0x180004a02  sub     rsp, 250h
0x180004a09  mov     rax, cs:__security_cookie
0x180004a10  xor     rax, rsp
0x180004a13  mov     [rsp+278h+var_38], rax
0x180004a1b  mov     rax, 0C000000000000000h
0x180004a25  mov     rbp, r9
0x180004a28  mov     r8, rdx
0x180004a2b  mov     rbx, rcx
0x180004a2e  test    rax, r9
0x180004a31  jnz     loc_180004C01
0x180004a37  xor     r12d, r12d
0x180004a3a  lea     rax, [rsp+278h+Name]
0x180004a3f  mov     ecx, 7FFFFFFEh
0x180004a44  mov     edx, 104h
0x180004a49  lea     esi, [r12+1]
0x180004a4e  test    rcx, rcx
0x180004a51  jz      short loc_180004A71
0x180004a53  movzx   r9d, word ptr [r8]
0x180004a57  test    r9w, r9w
0x180004a5b  jz      short loc_180004A71
0x180004a5d  mov     [rax], r9w
0x180004a61  add     r8, 2
0x180004a65  add     rax, 2
0x180004a69  sub     rcx, rsi
0x180004a6c  sub     rdx, rsi; unsigned __int64
0x180004a6f  jnz     short loc_180004A4E
0x180004a71  test    rdx, rdx
0x180004a74  lea     rcx, [rax-2]
0x180004a78  lea     r8, aP0; "_p0"
0x180004a7f  cmovnz  rcx, rax
0x180004a83  mov     [rcx], r12w
0x180004a87  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004a8c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a91  mov     edx, ebp
0x180004a93  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a9b  and     edx, 7FFFFFFFh; lInitialCount
0x180004aa1  mov     [rsp+278h+dwFlags], r12d; int
0x180004aa6  mov     r8d, esi
0x180004aa9  lea     r9, [rsp+278h+Name]; lpName
0x180004aae  cmova   r8d, edx; lMaximumCount
0x180004ab2  xor     ecx, ecx; lpSemaphoreAttributes
0x180004ab4  call    cs:__imp_CreateSemaphoreExW
0x180004aba  mov     r15, rax
0x180004abd  test    rax, rax
0x180004ac0  jnz     short loc_180004AF0
0x180004ac2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ac7  mov     edi, eax
0x180004ac9  test    eax, eax
0x180004acb  jns     short loc_180004B24
0x180004acd  mov     rcx, [rsp+278h]; this
0x180004ad5  lea     r8, aWil; "wil"
0x180004adc  mov     r9d, eax; char *
0x180004adf  mov     edx, 8Bh; void *
0x180004ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ae9  mov     eax, edi
0x180004aeb  jmp     loc_180004BC2
0x180004af0  call    cs:__imp_GetLastError
0x180004af6  mov     rdi, [rbx]
0x180004af9  test    rdi, rdi
0x180004afc  jz      short loc_180004B21
0x180004afe  call    cs:__imp_GetLastError
0x180004b04  mov     rcx, rdi; hObject
0x180004b07  mov     r14d, eax
0x180004b0a  call    cs:__imp_CloseHandle
0x180004b10  test    eax, eax
0x180004b12  jz      loc_180004C07
0x180004b18  mov     ecx, r14d; dwErrCode
0x180004b1b  call    cs:__imp_SetLastError
0x180004b21  mov     [rbx], r15
0x180004b24  lea     r8, asc_180010080; "h"
0x180004b2b  shr     rbp, 1Fh
0x180004b2f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004b34  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b39  test    ebp, ebp
0x180004b3b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004b43  lea     r9, [rsp+278h+Name]; lpName
0x180004b48  mov     [rsp+278h+dwFlags], r12d; int
0x180004b4d  cmovnz  esi, ebp
0x180004b50  mov     edx, ebp; lInitialCount
0x180004b52  mov     r8d, esi; lMaximumCount
0x180004b55  xor     ecx, ecx; lpSemaphoreAttributes
0x180004b57  call    cs:__imp_CreateSemaphoreExW
0x180004b5d  mov     rsi, rax
0x180004b60  test    rax, rax
0x180004b63  jnz     short loc_180004B90
0x180004b65  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004b6a  mov     ebx, eax
0x180004b6c  test    eax, eax
0x180004b6e  jns     short loc_180004BC0
0x180004b70  mov     rcx, [rsp+278h]; this
0x180004b78  lea     r8, aWil; "wil"
0x180004b7f  mov     r9d, eax; char *
0x180004b82  mov     edx, 90h; void *
0x180004b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b8c  mov     eax, ebx
0x180004b8e  jmp     short loc_180004BC2
0x180004b90  call    cs:__imp_GetLastError
0x180004b96  mov     rdi, [rbx+8]
0x180004b9a  test    rdi, rdi
0x180004b9d  jz      short loc_180004BBC
0x180004b9f  call    cs:__imp_GetLastError
0x180004ba5  mov     rcx, rdi; hObject
0x180004ba8  mov     ebp, eax
0x180004baa  call    cs:__imp_CloseHandle
0x180004bb0  test    eax, eax
0x180004bb2  jz      short loc_180004BEE
0x180004bb4  mov     ecx, ebp; dwErrCode
0x180004bb6  call    cs:__imp_SetLastError
0x180004bbc  mov     [rbx+8], rsi
0x180004bc0  xor     eax, eax
0x180004bc2  mov     rcx, [rsp+278h+var_38]
0x180004bca  xor     rcx, rsp; StackCookie
0x180004bcd  call    __security_check_cookie
0x180004bd2  lea     r11, [rsp+278h+var_28]
0x180004bda  mov     rbx, [r11+38h]
0x180004bde  mov     rbp, [r11+40h]
0x180004be2  mov     rsp, r11
0x180004be5  pop     r15
0x180004be7  pop     r14
0x180004be9  pop     r12
0x180004beb  pop     rdi
0x180004bec  pop     rsi
0x180004bed  retn
0x180004bee  mov     rcx, [rsp+278h]; this
0x180004bf6  mov     edx, 0A0Bh; void *
0x180004bfb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c01  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c07  mov     rcx, [rsp+278h]; this
0x180004c0f  mov     edx, 0A0Bh; void *
0x180004c14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
