# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140007920`
- end: `0x140007b51`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400074e8`
- `0x14000d1ac`

## callees

- `0x1400042f0`
- `0x140007920`
- `0x140008298`
- `0x1400095b4`
- `0x140009fc4`
- `0x14000a698`
- `0x14000a6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400079e9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007a8f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400079e9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007ad7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007a50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007aee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007a50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ae2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ae2`

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
0x140007920  mov     [rsp+arg_8], rbx
0x140007925  push    rbp
0x140007926  push    rsi
0x140007927  push    rdi
0x140007928  push    r12
0x14000792a  push    r13
0x14000792c  push    r14
0x14000792e  push    r15
0x140007930  sub     rsp, 250h
0x140007937  mov     rax, cs:__security_cookie
0x14000793e  xor     rax, rsp
0x140007941  mov     [rsp+288h+var_48], rax
0x140007949  mov     rax, 0C000000000000000h
0x140007953  mov     rsi, r9
0x140007956  mov     r8, rdx
0x140007959  mov     rbx, rcx
0x14000795c  test    rax, r9
0x14000795f  jnz     loc_140007B38
0x140007965  xor     r12d, r12d
0x140007968  lea     rax, [rsp+288h+Name]
0x14000796d  mov     r13d, 104h
0x140007973  mov     ecx, 7FFFFFFEh
0x140007978  mov     edx, r13d
0x14000797b  lea     ebp, [r12+1]
0x140007980  test    rcx, rcx
0x140007983  jz      short loc_1400079A3
0x140007985  movzx   r9d, word ptr [r8]
0x140007989  test    r9w, r9w
0x14000798d  jz      short loc_1400079A3
0x14000798f  mov     [rax], r9w
0x140007993  add     r8, 2
0x140007997  add     rax, 2
0x14000799b  sub     rcx, rbp
0x14000799e  sub     rdx, rbp
0x1400079a1  jnz     short loc_140007980
0x1400079a3  test    rdx, rdx
0x1400079a6  lea     rcx, [rax-2]
0x1400079aa  lea     r8, aP0; "_p0"
0x1400079b1  mov     rdx, r13; unsigned __int64
0x1400079b4  cmovnz  rcx, rax
0x1400079b8  mov     [rcx], r12w
0x1400079bc  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1400079c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400079c6  mov     edx, esi
0x1400079c8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400079d0  and     edx, 7FFFFFFFh; lInitialCount
0x1400079d6  mov     [rsp+288h+dwFlags], r12d; int
0x1400079db  mov     r8d, ebp
0x1400079de  lea     r9, [rsp+288h+Name]; lpName
0x1400079e3  cmova   r8d, edx; lMaximumCount
0x1400079e7  xor     ecx, ecx; lpSemaphoreAttributes
0x1400079e9  call    cs:__imp_CreateSemaphoreExW
0x1400079ef  mov     r15, rax
0x1400079f2  test    rax, rax
0x1400079f5  jnz     short loc_140007A25
0x1400079f7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400079fc  mov     edi, eax
0x1400079fe  test    eax, eax
0x140007a00  jns     short loc_140007A59
0x140007a02  mov     rcx, [rsp+288h]; this
0x140007a0a  lea     r8, aWil; "wil"
0x140007a11  mov     r9d, eax; char *
0x140007a14  mov     edx, 8Bh; void *
0x140007a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007a1e  mov     eax, edi
0x140007a20  jmp     loc_140007AFA
0x140007a25  call    cs:__imp_GetLastError
0x140007a2b  mov     rdi, [rbx]
0x140007a2e  test    rdi, rdi
0x140007a31  jz      short loc_140007A56
0x140007a33  call    cs:__imp_GetLastError
0x140007a39  mov     rcx, rdi; hObject
0x140007a3c  mov     r14d, eax
0x140007a3f  call    cs:__imp_CloseHandle
0x140007a45  test    eax, eax
0x140007a47  jz      loc_140007B3E
0x140007a4d  mov     ecx, r14d; dwErrCode
0x140007a50  call    cs:__imp_SetLastError
0x140007a56  mov     [rbx], r15
0x140007a59  lea     r8, asc_140060F00; "h"
0x140007a60  shr     rsi, 1Fh
0x140007a64  mov     rdx, r13; unsigned __int64
0x140007a67  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140007a6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007a71  test    esi, esi
0x140007a73  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140007a7b  lea     r9, [rsp+288h+Name]; lpName
0x140007a80  mov     [rsp+288h+dwFlags], r12d; int
0x140007a85  cmovnz  ebp, esi
0x140007a88  mov     edx, esi; lInitialCount
0x140007a8a  mov     r8d, ebp; lMaximumCount
0x140007a8d  xor     ecx, ecx; lpSemaphoreAttributes
0x140007a8f  call    cs:__imp_CreateSemaphoreExW
0x140007a95  mov     rbp, rax
0x140007a98  test    rax, rax
0x140007a9b  jnz     short loc_140007AC8
0x140007a9d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007aa2  mov     ebx, eax
0x140007aa4  test    eax, eax
0x140007aa6  jns     short loc_140007AF8
0x140007aa8  mov     rcx, [rsp+288h]; this
0x140007ab0  lea     r8, aWil; "wil"
0x140007ab7  mov     r9d, eax; char *
0x140007aba  mov     edx, 90h; void *
0x140007abf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007ac4  mov     eax, ebx
0x140007ac6  jmp     short loc_140007AFA
0x140007ac8  call    cs:__imp_GetLastError
0x140007ace  mov     rdi, [rbx+8]
0x140007ad2  test    rdi, rdi
0x140007ad5  jz      short loc_140007AF4
0x140007ad7  call    cs:__imp_GetLastError
0x140007add  mov     rcx, rdi; hObject
0x140007ae0  mov     esi, eax
0x140007ae2  call    cs:__imp_CloseHandle
0x140007ae8  test    eax, eax
0x140007aea  jz      short loc_140007B25
0x140007aec  mov     ecx, esi; dwErrCode
0x140007aee  call    cs:__imp_SetLastError
0x140007af4  mov     [rbx+8], rbp
0x140007af8  xor     eax, eax
0x140007afa  mov     rcx, [rsp+288h+var_48]
0x140007b02  xor     rcx, rsp; StackCookie
0x140007b05  call    __security_check_cookie
0x140007b0a  mov     rbx, [rsp+288h+arg_8]
0x140007b12  add     rsp, 250h
0x140007b19  pop     r15
0x140007b1b  pop     r14
0x140007b1d  pop     r13
0x140007b1f  pop     r12
0x140007b21  pop     rdi
0x140007b22  pop     rsi
0x140007b23  pop     rbp
0x140007b24  retn
0x140007b25  mov     rcx, [rsp+288h]; this
0x140007b2d  mov     edx, 0A0Bh; void *
0x140007b32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007b38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140007b3e  mov     rcx, [rsp+288h]; this
0x140007b46  mov     edx, 0A0Bh; void *
0x140007b4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
