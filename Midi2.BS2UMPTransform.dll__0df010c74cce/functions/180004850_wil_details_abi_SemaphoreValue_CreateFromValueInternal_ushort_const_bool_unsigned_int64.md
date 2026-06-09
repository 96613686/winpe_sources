# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004850`
- end: `0x180004a7a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038e8`

## callees

- `0x180001e60`
- `0x180004850`
- `0x180005528`
- `0x1800076b4`
- `0x180008044`
- `0x180008854`
- `0x180008864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004914`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049b7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004914`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000497b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000497b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000495e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000495e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000496a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000496a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a0a`

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
0x180004850  mov     [rsp+arg_8], rbx
0x180004855  mov     [rsp+arg_10], rbp
0x18000485a  push    rsi
0x18000485b  push    rdi
0x18000485c  push    r12
0x18000485e  push    r14
0x180004860  push    r15
0x180004862  sub     rsp, 250h
0x180004869  mov     rax, cs:__security_cookie
0x180004870  xor     rax, rsp
0x180004873  mov     [rsp+278h+var_38], rax
0x18000487b  mov     rax, 0C000000000000000h
0x180004885  mov     rbp, r9
0x180004888  mov     r8, rdx
0x18000488b  mov     rbx, rcx
0x18000488e  test    rax, r9
0x180004891  jnz     loc_180004A61
0x180004897  xor     r12d, r12d
0x18000489a  lea     rax, [rsp+278h+Name]
0x18000489f  mov     ecx, 7FFFFFFEh
0x1800048a4  mov     edx, 104h
0x1800048a9  lea     esi, [r12+1]
0x1800048ae  test    rcx, rcx
0x1800048b1  jz      short loc_1800048D1
0x1800048b3  movzx   r9d, word ptr [r8]
0x1800048b7  test    r9w, r9w
0x1800048bb  jz      short loc_1800048D1
0x1800048bd  mov     [rax], r9w
0x1800048c1  add     r8, 2
0x1800048c5  add     rax, 2
0x1800048c9  sub     rcx, rsi
0x1800048cc  sub     rdx, rsi; unsigned __int64
0x1800048cf  jnz     short loc_1800048AE
0x1800048d1  test    rdx, rdx
0x1800048d4  lea     rcx, [rax-2]
0x1800048d8  lea     r8, aP0; "_p0"
0x1800048df  cmovnz  rcx, rax
0x1800048e3  mov     [rcx], r12w
0x1800048e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800048ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800048f1  mov     edx, ebp
0x1800048f3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800048fb  and     edx, 7FFFFFFFh; lInitialCount
0x180004901  mov     [rsp+278h+dwFlags], r12d; int
0x180004906  mov     r8d, esi
0x180004909  lea     r9, [rsp+278h+Name]; lpName
0x18000490e  cmova   r8d, edx; lMaximumCount
0x180004912  xor     ecx, ecx; lpSemaphoreAttributes
0x180004914  call    cs:__imp_CreateSemaphoreExW
0x18000491a  mov     r15, rax
0x18000491d  test    rax, rax
0x180004920  jnz     short loc_180004950
0x180004922  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004927  mov     edi, eax
0x180004929  test    eax, eax
0x18000492b  jns     short loc_180004984
0x18000492d  mov     rcx, [rsp+278h]; this
0x180004935  lea     r8, aWil; "wil"
0x18000493c  mov     r9d, eax; char *
0x18000493f  mov     edx, 8Bh; void *
0x180004944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004949  mov     eax, edi
0x18000494b  jmp     loc_180004A22
0x180004950  call    cs:__imp_GetLastError
0x180004956  mov     rdi, [rbx]
0x180004959  test    rdi, rdi
0x18000495c  jz      short loc_180004981
0x18000495e  call    cs:__imp_GetLastError
0x180004964  mov     rcx, rdi; hObject
0x180004967  mov     r14d, eax
0x18000496a  call    cs:__imp_CloseHandle
0x180004970  test    eax, eax
0x180004972  jz      loc_180004A67
0x180004978  mov     ecx, r14d; dwErrCode
0x18000497b  call    cs:__imp_SetLastError
0x180004981  mov     [rbx], r15
0x180004984  lea     r8, asc_18000DF90; "h"
0x18000498b  shr     rbp, 1Fh
0x18000498f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004994  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004999  test    ebp, ebp
0x18000499b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800049a3  lea     r9, [rsp+278h+Name]; lpName
0x1800049a8  mov     [rsp+278h+dwFlags], r12d; int
0x1800049ad  cmovnz  esi, ebp
0x1800049b0  mov     edx, ebp; lInitialCount
0x1800049b2  mov     r8d, esi; lMaximumCount
0x1800049b5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800049b7  call    cs:__imp_CreateSemaphoreExW
0x1800049bd  mov     rsi, rax
0x1800049c0  test    rax, rax
0x1800049c3  jnz     short loc_1800049F0
0x1800049c5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049ca  mov     ebx, eax
0x1800049cc  test    eax, eax
0x1800049ce  jns     short loc_180004A20
0x1800049d0  mov     rcx, [rsp+278h]; this
0x1800049d8  lea     r8, aWil; "wil"
0x1800049df  mov     r9d, eax; char *
0x1800049e2  mov     edx, 90h; void *
0x1800049e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049ec  mov     eax, ebx
0x1800049ee  jmp     short loc_180004A22
0x1800049f0  call    cs:__imp_GetLastError
0x1800049f6  mov     rdi, [rbx+8]
0x1800049fa  test    rdi, rdi
0x1800049fd  jz      short loc_180004A1C
0x1800049ff  call    cs:__imp_GetLastError
0x180004a05  mov     rcx, rdi; hObject
0x180004a08  mov     ebp, eax
0x180004a0a  call    cs:__imp_CloseHandle
0x180004a10  test    eax, eax
0x180004a12  jz      short loc_180004A4E
0x180004a14  mov     ecx, ebp; dwErrCode
0x180004a16  call    cs:__imp_SetLastError
0x180004a1c  mov     [rbx+8], rsi
0x180004a20  xor     eax, eax
0x180004a22  mov     rcx, [rsp+278h+var_38]
0x180004a2a  xor     rcx, rsp; StackCookie
0x180004a2d  call    __security_check_cookie
0x180004a32  lea     r11, [rsp+278h+var_28]
0x180004a3a  mov     rbx, [r11+38h]
0x180004a3e  mov     rbp, [r11+40h]
0x180004a42  mov     rsp, r11
0x180004a45  pop     r15
0x180004a47  pop     r14
0x180004a49  pop     r12
0x180004a4b  pop     rdi
0x180004a4c  pop     rsi
0x180004a4d  retn
0x180004a4e  mov     rcx, [rsp+278h]; this
0x180004a56  mov     edx, 0A0Bh; void *
0x180004a5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a61  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a67  mov     rcx, [rsp+278h]; this
0x180004a6f  mov     edx, 0A0Bh; void *
0x180004a74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
