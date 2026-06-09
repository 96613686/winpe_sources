# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008ea8`
- end: `0x1800090d2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007de8`

## callees

- `0x180001dc0`
- `0x180008ea8`
- `0x18000adcc`
- `0x18000ed10`
- `0x1800107a0`
- `0x1800107b0`
- `0x18001168c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008f6c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000900f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008f6c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000900f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000906e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000906e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009062`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  wchar_t *v7; // rax
  __int64 v8; // rcx
  size_t v9; // rdx
  LONG v10; // esi
  wchar_t *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  size_t v16; // rdx
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
  wchar_t pszDest[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = pszDest;
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
  StringCchCatW(pszDest, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, pszDest, 0, 0x1F0003u);
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
  StringCchCatW(pszDest, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, pszDest, 0, 0x1F0003u);
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
0x180008ea8  mov     [rsp+arg_8], rbx
0x180008ead  mov     [rsp+arg_10], rbp
0x180008eb2  push    rsi
0x180008eb3  push    rdi
0x180008eb4  push    r12
0x180008eb6  push    r14
0x180008eb8  push    r15
0x180008eba  sub     rsp, 250h
0x180008ec1  mov     rax, cs:__security_cookie
0x180008ec8  xor     rax, rsp
0x180008ecb  mov     [rsp+278h+var_38], rax
0x180008ed3  mov     rax, 0C000000000000000h
0x180008edd  mov     rbp, r9
0x180008ee0  mov     r8, rdx
0x180008ee3  mov     rbx, rcx
0x180008ee6  test    rax, r9
0x180008ee9  jnz     loc_1800090B9
0x180008eef  xor     r12d, r12d
0x180008ef2  lea     rax, [rsp+278h+pszDest]
0x180008ef7  mov     ecx, 7FFFFFFEh
0x180008efc  mov     edx, 104h
0x180008f01  lea     esi, [r12+1]
0x180008f06  test    rcx, rcx
0x180008f09  jz      short loc_180008F29
0x180008f0b  movzx   r9d, word ptr [r8]
0x180008f0f  test    r9w, r9w
0x180008f13  jz      short loc_180008F29
0x180008f15  mov     [rax], r9w
0x180008f19  add     r8, 2
0x180008f1d  add     rax, 2
0x180008f21  sub     rcx, rsi
0x180008f24  sub     rdx, rsi; cchDest
0x180008f27  jnz     short loc_180008F06
0x180008f29  test    rdx, rdx
0x180008f2c  lea     rcx, [rax-2]
0x180008f30  lea     r8, aP0; "_p0"
0x180008f37  cmovnz  rcx, rax
0x180008f3b  mov     [rcx], r12w
0x180008f3f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180008f44  call    StringCchCatW
0x180008f49  mov     edx, ebp
0x180008f4b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008f53  and     edx, 7FFFFFFFh; lInitialCount
0x180008f59  mov     [rsp+278h+dwFlags], r12d; int
0x180008f5e  mov     r8d, esi
0x180008f61  lea     r9, [rsp+278h+pszDest]; lpName
0x180008f66  cmova   r8d, edx; lMaximumCount
0x180008f6a  xor     ecx, ecx; lpSemaphoreAttributes
0x180008f6c  call    cs:__imp_CreateSemaphoreExW
0x180008f72  mov     r15, rax
0x180008f75  test    rax, rax
0x180008f78  jnz     short loc_180008FA8
0x180008f7a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008f7f  mov     edi, eax
0x180008f81  test    eax, eax
0x180008f83  jns     short loc_180008FDC
0x180008f85  mov     rcx, [rsp+278h]; this
0x180008f8d  lea     r8, aWil; "wil"
0x180008f94  mov     r9d, eax; char *
0x180008f97  mov     edx, 8Bh; void *
0x180008f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fa1  mov     eax, edi
0x180008fa3  jmp     loc_18000907A
0x180008fa8  call    cs:__imp_GetLastError
0x180008fae  mov     rdi, [rbx]
0x180008fb1  test    rdi, rdi
0x180008fb4  jz      short loc_180008FD9
0x180008fb6  call    cs:__imp_GetLastError
0x180008fbc  mov     rcx, rdi; hObject
0x180008fbf  mov     r14d, eax
0x180008fc2  call    cs:__imp_CloseHandle
0x180008fc8  test    eax, eax
0x180008fca  jz      loc_1800090BF
0x180008fd0  mov     ecx, r14d; dwErrCode
0x180008fd3  call    cs:__imp_SetLastError
0x180008fd9  mov     [rbx], r15
0x180008fdc  lea     r8, asc_18001D8F8; "h"
0x180008fe3  shr     rbp, 1Fh
0x180008fe7  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180008fec  call    StringCchCatW
0x180008ff1  test    ebp, ebp
0x180008ff3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008ffb  lea     r9, [rsp+278h+pszDest]; lpName
0x180009000  mov     [rsp+278h+dwFlags], r12d; int
0x180009005  cmovnz  esi, ebp
0x180009008  mov     edx, ebp; lInitialCount
0x18000900a  mov     r8d, esi; lMaximumCount
0x18000900d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000900f  call    cs:__imp_CreateSemaphoreExW
0x180009015  mov     rsi, rax
0x180009018  test    rax, rax
0x18000901b  jnz     short loc_180009048
0x18000901d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009022  mov     ebx, eax
0x180009024  test    eax, eax
0x180009026  jns     short loc_180009078
0x180009028  mov     rcx, [rsp+278h]; this
0x180009030  lea     r8, aWil; "wil"
0x180009037  mov     r9d, eax; char *
0x18000903a  mov     edx, 90h; void *
0x18000903f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009044  mov     eax, ebx
0x180009046  jmp     short loc_18000907A
0x180009048  call    cs:__imp_GetLastError
0x18000904e  mov     rdi, [rbx+8]
0x180009052  test    rdi, rdi
0x180009055  jz      short loc_180009074
0x180009057  call    cs:__imp_GetLastError
0x18000905d  mov     rcx, rdi; hObject
0x180009060  mov     ebp, eax
0x180009062  call    cs:__imp_CloseHandle
0x180009068  test    eax, eax
0x18000906a  jz      short loc_1800090A6
0x18000906c  mov     ecx, ebp; dwErrCode
0x18000906e  call    cs:__imp_SetLastError
0x180009074  mov     [rbx+8], rsi
0x180009078  xor     eax, eax
0x18000907a  mov     rcx, [rsp+278h+var_38]
0x180009082  xor     rcx, rsp; StackCookie
0x180009085  call    __security_check_cookie
0x18000908a  lea     r11, [rsp+278h+var_28]
0x180009092  mov     rbx, [r11+38h]
0x180009096  mov     rbp, [r11+40h]
0x18000909a  mov     rsp, r11
0x18000909d  pop     r15
0x18000909f  pop     r14
0x1800090a1  pop     r12
0x1800090a3  pop     rdi
0x1800090a4  pop     rsi
0x1800090a5  retn
0x1800090a6  mov     rcx, [rsp+278h]; this
0x1800090ae  mov     edx, 0A0Bh; void *
0x1800090b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800090b9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800090bf  mov     rcx, [rsp+278h]; this
0x1800090c7  mov     edx, 0A0Bh; void *
0x1800090cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
