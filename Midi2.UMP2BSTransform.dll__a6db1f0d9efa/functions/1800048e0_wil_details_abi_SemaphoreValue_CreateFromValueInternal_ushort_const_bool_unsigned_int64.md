# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800048e0`
- end: `0x180004b0a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003978`

## callees

- `0x180001ef0`
- `0x1800048e0`
- `0x1800055b8`
- `0x180007744`
- `0x1800080d4`
- `0x1800088e4`
- `0x1800088f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049a4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a47`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049a4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004aa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a9a`

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
0x1800048e0  mov     [rsp+arg_8], rbx
0x1800048e5  mov     [rsp+arg_10], rbp
0x1800048ea  push    rsi
0x1800048eb  push    rdi
0x1800048ec  push    r12
0x1800048ee  push    r14
0x1800048f0  push    r15
0x1800048f2  sub     rsp, 250h
0x1800048f9  mov     rax, cs:__security_cookie
0x180004900  xor     rax, rsp
0x180004903  mov     [rsp+278h+var_38], rax
0x18000490b  mov     rax, 0C000000000000000h
0x180004915  mov     rbp, r9
0x180004918  mov     r8, rdx
0x18000491b  mov     rbx, rcx
0x18000491e  test    rax, r9
0x180004921  jnz     loc_180004AF1
0x180004927  xor     r12d, r12d
0x18000492a  lea     rax, [rsp+278h+Name]
0x18000492f  mov     ecx, 7FFFFFFEh
0x180004934  mov     edx, 104h
0x180004939  lea     esi, [r12+1]
0x18000493e  test    rcx, rcx
0x180004941  jz      short loc_180004961
0x180004943  movzx   r9d, word ptr [r8]
0x180004947  test    r9w, r9w
0x18000494b  jz      short loc_180004961
0x18000494d  mov     [rax], r9w
0x180004951  add     r8, 2
0x180004955  add     rax, 2
0x180004959  sub     rcx, rsi
0x18000495c  sub     rdx, rsi; unsigned __int64
0x18000495f  jnz     short loc_18000493E
0x180004961  test    rdx, rdx
0x180004964  lea     rcx, [rax-2]
0x180004968  lea     r8, aP0; "_p0"
0x18000496f  cmovnz  rcx, rax
0x180004973  mov     [rcx], r12w
0x180004977  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000497c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004981  mov     edx, ebp
0x180004983  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000498b  and     edx, 7FFFFFFFh; lInitialCount
0x180004991  mov     [rsp+278h+dwFlags], r12d; int
0x180004996  mov     r8d, esi
0x180004999  lea     r9, [rsp+278h+Name]; lpName
0x18000499e  cmova   r8d, edx; lMaximumCount
0x1800049a2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800049a4  call    cs:__imp_CreateSemaphoreExW
0x1800049aa  mov     r15, rax
0x1800049ad  test    rax, rax
0x1800049b0  jnz     short loc_1800049E0
0x1800049b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049b7  mov     edi, eax
0x1800049b9  test    eax, eax
0x1800049bb  jns     short loc_180004A14
0x1800049bd  mov     rcx, [rsp+278h]; this
0x1800049c5  lea     r8, aWil; "wil"
0x1800049cc  mov     r9d, eax; char *
0x1800049cf  mov     edx, 8Bh; void *
0x1800049d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049d9  mov     eax, edi
0x1800049db  jmp     loc_180004AB2
0x1800049e0  call    cs:__imp_GetLastError
0x1800049e6  mov     rdi, [rbx]
0x1800049e9  test    rdi, rdi
0x1800049ec  jz      short loc_180004A11
0x1800049ee  call    cs:__imp_GetLastError
0x1800049f4  mov     rcx, rdi; hObject
0x1800049f7  mov     r14d, eax
0x1800049fa  call    cs:__imp_CloseHandle
0x180004a00  test    eax, eax
0x180004a02  jz      loc_180004AF7
0x180004a08  mov     ecx, r14d; dwErrCode
0x180004a0b  call    cs:__imp_SetLastError
0x180004a11  mov     [rbx], r15
0x180004a14  lea     r8, asc_180011060; "h"
0x180004a1b  shr     rbp, 1Fh
0x180004a1f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004a24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a29  test    ebp, ebp
0x180004a2b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a33  lea     r9, [rsp+278h+Name]; lpName
0x180004a38  mov     [rsp+278h+dwFlags], r12d; int
0x180004a3d  cmovnz  esi, ebp
0x180004a40  mov     edx, ebp; lInitialCount
0x180004a42  mov     r8d, esi; lMaximumCount
0x180004a45  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a47  call    cs:__imp_CreateSemaphoreExW
0x180004a4d  mov     rsi, rax
0x180004a50  test    rax, rax
0x180004a53  jnz     short loc_180004A80
0x180004a55  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a5a  mov     ebx, eax
0x180004a5c  test    eax, eax
0x180004a5e  jns     short loc_180004AB0
0x180004a60  mov     rcx, [rsp+278h]; this
0x180004a68  lea     r8, aWil; "wil"
0x180004a6f  mov     r9d, eax; char *
0x180004a72  mov     edx, 90h; void *
0x180004a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a7c  mov     eax, ebx
0x180004a7e  jmp     short loc_180004AB2
0x180004a80  call    cs:__imp_GetLastError
0x180004a86  mov     rdi, [rbx+8]
0x180004a8a  test    rdi, rdi
0x180004a8d  jz      short loc_180004AAC
0x180004a8f  call    cs:__imp_GetLastError
0x180004a95  mov     rcx, rdi; hObject
0x180004a98  mov     ebp, eax
0x180004a9a  call    cs:__imp_CloseHandle
0x180004aa0  test    eax, eax
0x180004aa2  jz      short loc_180004ADE
0x180004aa4  mov     ecx, ebp; dwErrCode
0x180004aa6  call    cs:__imp_SetLastError
0x180004aac  mov     [rbx+8], rsi
0x180004ab0  xor     eax, eax
0x180004ab2  mov     rcx, [rsp+278h+var_38]
0x180004aba  xor     rcx, rsp; StackCookie
0x180004abd  call    __security_check_cookie
0x180004ac2  lea     r11, [rsp+278h+var_28]
0x180004aca  mov     rbx, [r11+38h]
0x180004ace  mov     rbp, [r11+40h]
0x180004ad2  mov     rsp, r11
0x180004ad5  pop     r15
0x180004ad7  pop     r14
0x180004ad9  pop     r12
0x180004adb  pop     rdi
0x180004adc  pop     rsi
0x180004add  retn
0x180004ade  mov     rcx, [rsp+278h]; this
0x180004ae6  mov     edx, 0A0Bh; void *
0x180004aeb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004af1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004af7  mov     rcx, [rsp+278h]; this
0x180004aff  mov     edx, 0A0Bh; void *
0x180004b04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
