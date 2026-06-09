# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18001a64c`
- end: `0x18001a86f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180019770`
- `0x180019b14`

## callees

- `0x18001a64c`
- `0x18001be4c`
- `0x180021f38`
- `0x180022e70`
- `0x1800247e4`
- `0x1800247f4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001a715`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001a7b4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001a715`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001a7b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a80c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a764`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a764`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a800`

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
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  __int64 v31; // r8
  const char *v32; // r9
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001a64c  mov     [rsp+arg_8], rbx
0x18001a651  push    rbp
0x18001a652  push    rsi
0x18001a653  push    rdi
0x18001a654  push    r12
0x18001a656  push    r13
0x18001a658  push    r14
0x18001a65a  push    r15
0x18001a65c  sub     rsp, 250h
0x18001a663  mov     rax, cs:__security_cookie
0x18001a66a  xor     rax, rsp
0x18001a66d  mov     [rsp+288h+var_48], rax
0x18001a675  mov     rax, 0C000000000000000h
0x18001a67f  mov     rsi, r9
0x18001a682  mov     r8, rdx
0x18001a685  mov     rbx, rcx
0x18001a688  test    rax, r9
0x18001a68b  jnz     loc_18001A856
0x18001a691  xor     r12d, r12d
0x18001a694  lea     rax, [rsp+288h+Name]
0x18001a699  mov     r13d, 104h
0x18001a69f  mov     ecx, 7FFFFFFEh
0x18001a6a4  mov     edx, r13d
0x18001a6a7  lea     ebp, [r12+1]
0x18001a6ac  test    rcx, rcx
0x18001a6af  jz      short loc_18001A6CF
0x18001a6b1  movzx   r9d, word ptr [r8]
0x18001a6b5  test    r9w, r9w
0x18001a6b9  jz      short loc_18001A6CF
0x18001a6bb  mov     [rax], r9w
0x18001a6bf  add     r8, 2
0x18001a6c3  add     rax, 2
0x18001a6c7  sub     rcx, rbp
0x18001a6ca  sub     rdx, rbp
0x18001a6cd  jnz     short loc_18001A6AC
0x18001a6cf  test    rdx, rdx
0x18001a6d2  lea     rcx, [rax-2]
0x18001a6d6  lea     r8, aP0; "_p0"
0x18001a6dd  mov     rdx, r13; unsigned __int64
0x18001a6e0  cmovnz  rcx, rax
0x18001a6e4  mov     [rcx], r12w
0x18001a6e8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001a6ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a6f2  mov     edx, esi
0x18001a6f4  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001a6fc  and     edx, 7FFFFFFFh; lInitialCount
0x18001a702  mov     [rsp+288h+dwFlags], r12d; int
0x18001a707  mov     r8d, ebp
0x18001a70a  lea     r9, [rsp+288h+Name]; lpName
0x18001a70f  cmova   r8d, edx; lMaximumCount
0x18001a713  xor     ecx, ecx; lpSemaphoreAttributes
0x18001a715  call    cs:__imp_CreateSemaphoreExW
0x18001a71b  mov     r15, rax
0x18001a71e  test    rax, rax
0x18001a721  jnz     short loc_18001A74A
0x18001a723  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a728  mov     edi, eax
0x18001a72a  test    eax, eax
0x18001a72c  jns     short loc_18001A77E
0x18001a72e  mov     rcx, [rsp+288h]; this
0x18001a736  mov     r9d, eax; char *
0x18001a739  mov     edx, 8Bh; void *
0x18001a73e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a743  mov     eax, edi
0x18001a745  jmp     loc_18001A818
0x18001a74a  call    cs:__imp_GetLastError
0x18001a750  mov     rdi, [rbx]
0x18001a753  test    rdi, rdi
0x18001a756  jz      short loc_18001A77B
0x18001a758  call    cs:__imp_GetLastError
0x18001a75e  mov     rcx, rdi; hObject
0x18001a761  mov     r14d, eax
0x18001a764  call    cs:__imp_CloseHandle
0x18001a76a  test    eax, eax
0x18001a76c  jz      loc_18001A85C
0x18001a772  mov     ecx, r14d; dwErrCode
0x18001a775  call    cs:__imp_SetLastError
0x18001a77b  mov     [rbx], r15
0x18001a77e  lea     r8, asc_180041280; "h"
0x18001a785  shr     rsi, 1Fh
0x18001a789  mov     rdx, r13; unsigned __int64
0x18001a78c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001a791  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a796  test    esi, esi
0x18001a798  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001a7a0  lea     r9, [rsp+288h+Name]; lpName
0x18001a7a5  mov     [rsp+288h+dwFlags], r12d; int
0x18001a7aa  cmovnz  ebp, esi
0x18001a7ad  mov     edx, esi; lInitialCount
0x18001a7af  mov     r8d, ebp; lMaximumCount
0x18001a7b2  xor     ecx, ecx; lpSemaphoreAttributes
0x18001a7b4  call    cs:__imp_CreateSemaphoreExW
0x18001a7ba  mov     rbp, rax
0x18001a7bd  test    rax, rax
0x18001a7c0  jnz     short loc_18001A7E6
0x18001a7c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a7c7  mov     ebx, eax
0x18001a7c9  test    eax, eax
0x18001a7cb  jns     short loc_18001A816
0x18001a7cd  mov     rcx, [rsp+288h]; this
0x18001a7d5  mov     r9d, eax; char *
0x18001a7d8  mov     edx, 90h; void *
0x18001a7dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7e2  mov     eax, ebx
0x18001a7e4  jmp     short loc_18001A818
0x18001a7e6  call    cs:__imp_GetLastError
0x18001a7ec  mov     rdi, [rbx+8]
0x18001a7f0  test    rdi, rdi
0x18001a7f3  jz      short loc_18001A812
0x18001a7f5  call    cs:__imp_GetLastError
0x18001a7fb  mov     rcx, rdi; hObject
0x18001a7fe  mov     esi, eax
0x18001a800  call    cs:__imp_CloseHandle
0x18001a806  test    eax, eax
0x18001a808  jz      short loc_18001A843
0x18001a80a  mov     ecx, esi; dwErrCode
0x18001a80c  call    cs:__imp_SetLastError
0x18001a812  mov     [rbx+8], rbp
0x18001a816  xor     eax, eax
0x18001a818  mov     rcx, [rsp+288h+var_48]
0x18001a820  xor     rcx, rsp; StackCookie
0x18001a823  call    __security_check_cookie
0x18001a828  mov     rbx, [rsp+288h+arg_8]
0x18001a830  add     rsp, 250h
0x18001a837  pop     r15
0x18001a839  pop     r14
0x18001a83b  pop     r13
0x18001a83d  pop     r12
0x18001a83f  pop     rdi
0x18001a840  pop     rsi
0x18001a841  pop     rbp
0x18001a842  retn
0x18001a843  mov     rcx, [rsp+288h]; this
0x18001a84b  mov     edx, 0A0Bh; void *
0x18001a850  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a856  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001a85c  mov     rcx, [rsp+288h]; this
0x18001a864  mov     edx, 0A0Bh; void *
0x18001a869  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
