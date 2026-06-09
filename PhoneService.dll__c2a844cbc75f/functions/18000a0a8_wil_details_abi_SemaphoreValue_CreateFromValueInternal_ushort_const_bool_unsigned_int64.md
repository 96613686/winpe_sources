# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a0a8`
- end: `0x18000a2d9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009cd8`
- `0x180021c08`

## callees

- `0x18000a0a8`
- `0x18000a9e8`
- `0x18000b760`
- `0x18000ba7c`
- `0x18000c02c`
- `0x18000c03c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a171`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a217`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a171`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a217`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a276`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a25f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a25f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a26a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a26a`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
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
0x18000a0a8  mov     [rsp+arg_8], rbx
0x18000a0ad  push    rbp
0x18000a0ae  push    rsi
0x18000a0af  push    rdi
0x18000a0b0  push    r12
0x18000a0b2  push    r13
0x18000a0b4  push    r14
0x18000a0b6  push    r15
0x18000a0b8  sub     rsp, 250h
0x18000a0bf  mov     rax, cs:__security_cookie
0x18000a0c6  xor     rax, rsp
0x18000a0c9  mov     [rsp+288h+var_48], rax
0x18000a0d1  mov     rax, 0C000000000000000h
0x18000a0db  mov     rsi, r9
0x18000a0de  mov     r8, rdx
0x18000a0e1  mov     rbx, rcx
0x18000a0e4  test    rax, r9
0x18000a0e7  jnz     loc_18000A2C0
0x18000a0ed  xor     r12d, r12d
0x18000a0f0  lea     rax, [rsp+288h+Name]
0x18000a0f5  mov     r13d, 104h
0x18000a0fb  mov     ecx, 7FFFFFFEh
0x18000a100  mov     edx, r13d
0x18000a103  lea     ebp, [r12+1]
0x18000a108  test    rcx, rcx
0x18000a10b  jz      short loc_18000A12B
0x18000a10d  movzx   r9d, word ptr [r8]
0x18000a111  test    r9w, r9w
0x18000a115  jz      short loc_18000A12B
0x18000a117  mov     [rax], r9w
0x18000a11b  add     r8, 2
0x18000a11f  add     rax, 2
0x18000a123  sub     rcx, rbp
0x18000a126  sub     rdx, rbp
0x18000a129  jnz     short loc_18000A108
0x18000a12b  test    rdx, rdx
0x18000a12e  lea     rcx, [rax-2]
0x18000a132  lea     r8, aP0; "_p0"
0x18000a139  mov     rdx, r13; unsigned __int64
0x18000a13c  cmovnz  rcx, rax
0x18000a140  mov     [rcx], r12w
0x18000a144  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a149  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a14e  mov     edx, esi
0x18000a150  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a158  and     edx, 7FFFFFFFh; lInitialCount
0x18000a15e  mov     [rsp+288h+dwFlags], r12d; int
0x18000a163  mov     r8d, ebp
0x18000a166  lea     r9, [rsp+288h+Name]; lpName
0x18000a16b  cmova   r8d, edx; lMaximumCount
0x18000a16f  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a171  call    cs:__imp_CreateSemaphoreExW
0x18000a177  mov     r15, rax
0x18000a17a  test    rax, rax
0x18000a17d  jnz     short loc_18000A1AD
0x18000a17f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a184  mov     edi, eax
0x18000a186  test    eax, eax
0x18000a188  jns     short loc_18000A1E1
0x18000a18a  mov     rcx, [rsp+288h]; this
0x18000a192  lea     r8, aWil; "wil"
0x18000a199  mov     r9d, eax; char *
0x18000a19c  mov     edx, 8Bh; void *
0x18000a1a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1a6  mov     eax, edi
0x18000a1a8  jmp     loc_18000A282
0x18000a1ad  call    cs:__imp_GetLastError
0x18000a1b3  mov     rdi, [rbx]
0x18000a1b6  test    rdi, rdi
0x18000a1b9  jz      short loc_18000A1DE
0x18000a1bb  call    cs:__imp_GetLastError
0x18000a1c1  mov     rcx, rdi; hObject
0x18000a1c4  mov     r14d, eax
0x18000a1c7  call    cs:__imp_CloseHandle
0x18000a1cd  test    eax, eax
0x18000a1cf  jz      loc_18000A2C6
0x18000a1d5  mov     ecx, r14d; dwErrCode
0x18000a1d8  call    cs:__imp_SetLastError
0x18000a1de  mov     [rbx], r15
0x18000a1e1  lea     r8, asc_18009AB78; "h"
0x18000a1e8  shr     rsi, 1Fh
0x18000a1ec  mov     rdx, r13; unsigned __int64
0x18000a1ef  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a1f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a1f9  test    esi, esi
0x18000a1fb  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a203  lea     r9, [rsp+288h+Name]; lpName
0x18000a208  mov     [rsp+288h+dwFlags], r12d; int
0x18000a20d  cmovnz  ebp, esi
0x18000a210  mov     edx, esi; lInitialCount
0x18000a212  mov     r8d, ebp; lMaximumCount
0x18000a215  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a217  call    cs:__imp_CreateSemaphoreExW
0x18000a21d  mov     rbp, rax
0x18000a220  test    rax, rax
0x18000a223  jnz     short loc_18000A250
0x18000a225  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a22a  mov     ebx, eax
0x18000a22c  test    eax, eax
0x18000a22e  jns     short loc_18000A280
0x18000a230  mov     rcx, [rsp+288h]; this
0x18000a238  lea     r8, aWil; "wil"
0x18000a23f  mov     r9d, eax; char *
0x18000a242  mov     edx, 90h; void *
0x18000a247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a24c  mov     eax, ebx
0x18000a24e  jmp     short loc_18000A282
0x18000a250  call    cs:__imp_GetLastError
0x18000a256  mov     rdi, [rbx+8]
0x18000a25a  test    rdi, rdi
0x18000a25d  jz      short loc_18000A27C
0x18000a25f  call    cs:__imp_GetLastError
0x18000a265  mov     rcx, rdi; hObject
0x18000a268  mov     esi, eax
0x18000a26a  call    cs:__imp_CloseHandle
0x18000a270  test    eax, eax
0x18000a272  jz      short loc_18000A2AD
0x18000a274  mov     ecx, esi; dwErrCode
0x18000a276  call    cs:__imp_SetLastError
0x18000a27c  mov     [rbx+8], rbp
0x18000a280  xor     eax, eax
0x18000a282  mov     rcx, [rsp+288h+var_48]
0x18000a28a  xor     rcx, rsp; StackCookie
0x18000a28d  call    __security_check_cookie
0x18000a292  mov     rbx, [rsp+288h+arg_8]
0x18000a29a  add     rsp, 250h
0x18000a2a1  pop     r15
0x18000a2a3  pop     r14
0x18000a2a5  pop     r13
0x18000a2a7  pop     r12
0x18000a2a9  pop     rdi
0x18000a2aa  pop     rsi
0x18000a2ab  pop     rbp
0x18000a2ac  retn
0x18000a2ad  mov     rcx, [rsp+288h]; this
0x18000a2b5  mov     edx, 0A0Bh; void *
0x18000a2ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a2c6  mov     rcx, [rsp+288h]; this
0x18000a2ce  mov     edx, 0A0Bh; void *
0x18000a2d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
