# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18002409c`
- end: `0x1800242cd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800238d4`
- `0x180023ca4`

## callees

- `0x180001ee0`
- `0x18001fe90`
- `0x18002409c`
- `0x180024f0c`
- `0x180026e80`
- `0x180027dac`
- `0x180027dbc`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180024165`
- `KERNEL32!CreateSemaphoreExW` at `0x18002420b`
- `KERNEL32!CreateSemaphoreExW` at `0x180024165`
- `KERNEL32!CreateSemaphoreExW` at `0x18002420b`
- `KERNEL32!CloseHandle` at `0x1800241bb`
- `KERNEL32!CloseHandle` at `0x18002425e`
- `KERNEL32!CloseHandle` at `0x1800241bb`
- `KERNEL32!CloseHandle` at `0x18002425e`
- `KERNEL32!SetLastError` at `0x1800241cc`
- `KERNEL32!SetLastError` at `0x18002426a`
- `KERNEL32!SetLastError` at `0x1800241cc`
- `KERNEL32!SetLastError` at `0x18002426a`
- `KERNEL32!GetLastError` at `0x1800241a1`
- `KERNEL32!GetLastError` at `0x1800241af`
- `KERNEL32!GetLastError` at `0x180024244`
- `KERNEL32!GetLastError` at `0x180024253`
- `KERNEL32!GetLastError` at `0x1800241a1`
- `KERNEL32!GetLastError` at `0x1800241af`
- `KERNEL32!GetLastError` at `0x180024244`
- `KERNEL32!GetLastError` at `0x180024253`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  wchar_t *v11; // rcx
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
  wchar_t pszDest[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, pszDest, 0, 0x1F0003u);
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
  StringCchCatW(pszDest, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, pszDest, 0, 0x1F0003u);
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
0x18002409c  mov     [rsp+arg_8], rbx
0x1800240a1  push    rbp
0x1800240a2  push    rsi
0x1800240a3  push    rdi
0x1800240a4  push    r12
0x1800240a6  push    r13
0x1800240a8  push    r14
0x1800240aa  push    r15
0x1800240ac  sub     rsp, 250h
0x1800240b3  mov     rax, cs:__security_cookie
0x1800240ba  xor     rax, rsp
0x1800240bd  mov     [rsp+288h+var_48], rax
0x1800240c5  mov     rax, 0C000000000000000h
0x1800240cf  mov     rsi, r9
0x1800240d2  mov     r8, rdx
0x1800240d5  mov     rbx, rcx
0x1800240d8  test    rax, r9
0x1800240db  jnz     loc_1800242B4
0x1800240e1  xor     r12d, r12d
0x1800240e4  lea     rax, [rsp+288h+pszDest]
0x1800240e9  mov     r13d, 104h
0x1800240ef  mov     ecx, 7FFFFFFEh
0x1800240f4  mov     edx, r13d
0x1800240f7  lea     ebp, [r12+1]
0x1800240fc  test    rcx, rcx
0x1800240ff  jz      short loc_18002411F
0x180024101  movzx   r9d, word ptr [r8]
0x180024105  test    r9w, r9w
0x180024109  jz      short loc_18002411F
0x18002410b  mov     [rax], r9w
0x18002410f  add     r8, 2
0x180024113  add     rax, 2
0x180024117  sub     rcx, rbp
0x18002411a  sub     rdx, rbp
0x18002411d  jnz     short loc_1800240FC
0x18002411f  test    rdx, rdx
0x180024122  lea     rcx, [rax-2]
0x180024126  lea     r8, aP0; "_p0"
0x18002412d  mov     rdx, r13; cchDest
0x180024130  cmovnz  rcx, rax
0x180024134  mov     [rcx], r12w
0x180024138  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18002413d  call    StringCchCatW
0x180024142  mov     edx, esi
0x180024144  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002414c  and     edx, 7FFFFFFFh; lInitialCount
0x180024152  mov     [rsp+288h+dwFlags], r12d; int
0x180024157  mov     r8d, ebp
0x18002415a  lea     r9, [rsp+288h+pszDest]; lpName
0x18002415f  cmova   r8d, edx; lMaximumCount
0x180024163  xor     ecx, ecx; lpSemaphoreAttributes
0x180024165  call    cs:__imp_CreateSemaphoreExW
0x18002416b  mov     r15, rax
0x18002416e  test    rax, rax
0x180024171  jnz     short loc_1800241A1
0x180024173  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024178  mov     edi, eax
0x18002417a  test    eax, eax
0x18002417c  jns     short loc_1800241D5
0x18002417e  mov     rcx, [rsp+288h]; this
0x180024186  lea     r8, aWil; "wil"
0x18002418d  mov     r9d, eax; char *
0x180024190  mov     edx, 8Bh; void *
0x180024195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002419a  mov     eax, edi
0x18002419c  jmp     loc_180024276
0x1800241a1  call    cs:__imp_GetLastError
0x1800241a7  mov     rdi, [rbx]
0x1800241aa  test    rdi, rdi
0x1800241ad  jz      short loc_1800241D2
0x1800241af  call    cs:__imp_GetLastError
0x1800241b5  mov     rcx, rdi; hObject
0x1800241b8  mov     r14d, eax
0x1800241bb  call    cs:__imp_CloseHandle
0x1800241c1  test    eax, eax
0x1800241c3  jz      loc_1800242BA
0x1800241c9  mov     ecx, r14d; dwErrCode
0x1800241cc  call    cs:__imp_SetLastError
0x1800241d2  mov     [rbx], r15
0x1800241d5  lea     r8, asc_180064E00; "h"
0x1800241dc  shr     rsi, 1Fh
0x1800241e0  mov     rdx, r13; cchDest
0x1800241e3  lea     rcx, [rsp+288h+pszDest]; pszDest
0x1800241e8  call    StringCchCatW
0x1800241ed  test    esi, esi
0x1800241ef  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800241f7  lea     r9, [rsp+288h+pszDest]; lpName
0x1800241fc  mov     [rsp+288h+dwFlags], r12d; int
0x180024201  cmovnz  ebp, esi
0x180024204  mov     edx, esi; lInitialCount
0x180024206  mov     r8d, ebp; lMaximumCount
0x180024209  xor     ecx, ecx; lpSemaphoreAttributes
0x18002420b  call    cs:__imp_CreateSemaphoreExW
0x180024211  mov     rbp, rax
0x180024214  test    rax, rax
0x180024217  jnz     short loc_180024244
0x180024219  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002421e  mov     ebx, eax
0x180024220  test    eax, eax
0x180024222  jns     short loc_180024274
0x180024224  mov     rcx, [rsp+288h]; this
0x18002422c  lea     r8, aWil; "wil"
0x180024233  mov     r9d, eax; char *
0x180024236  mov     edx, 90h; void *
0x18002423b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024240  mov     eax, ebx
0x180024242  jmp     short loc_180024276
0x180024244  call    cs:__imp_GetLastError
0x18002424a  mov     rdi, [rbx+8]
0x18002424e  test    rdi, rdi
0x180024251  jz      short loc_180024270
0x180024253  call    cs:__imp_GetLastError
0x180024259  mov     rcx, rdi; hObject
0x18002425c  mov     esi, eax
0x18002425e  call    cs:__imp_CloseHandle
0x180024264  test    eax, eax
0x180024266  jz      short loc_1800242A1
0x180024268  mov     ecx, esi; dwErrCode
0x18002426a  call    cs:__imp_SetLastError
0x180024270  mov     [rbx+8], rbp
0x180024274  xor     eax, eax
0x180024276  mov     rcx, [rsp+288h+var_48]
0x18002427e  xor     rcx, rsp; StackCookie
0x180024281  call    __security_check_cookie
0x180024286  mov     rbx, [rsp+288h+arg_8]
0x18002428e  add     rsp, 250h
0x180024295  pop     r15
0x180024297  pop     r14
0x180024299  pop     r13
0x18002429b  pop     r12
0x18002429d  pop     rdi
0x18002429e  pop     rsi
0x18002429f  pop     rbp
0x1800242a0  retn
0x1800242a1  mov     rcx, [rsp+288h]; this
0x1800242a9  mov     edx, 0A0Bh; void *
0x1800242ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800242b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800242ba  mov     rcx, [rsp+288h]; this
0x1800242c2  mov     edx, 0A0Bh; void *
0x1800242c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
