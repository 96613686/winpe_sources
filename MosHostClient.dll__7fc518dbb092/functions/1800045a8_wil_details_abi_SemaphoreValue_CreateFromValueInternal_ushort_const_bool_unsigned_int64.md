# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800045a8`
- end: `0x1800047d2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800041d4`

## callees

- `0x180002550`
- `0x1800045a8`
- `0x180004f68`
- `0x180006214`
- `0x180006b54`
- `0x180007148`
- `0x180007158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000466c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000470f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000466c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000470f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000476e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000476e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004762`

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
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
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
0x1800045a8  mov     [rsp+arg_8], rbx
0x1800045ad  mov     [rsp+arg_10], rbp
0x1800045b2  push    rsi
0x1800045b3  push    rdi
0x1800045b4  push    r12
0x1800045b6  push    r14
0x1800045b8  push    r15
0x1800045ba  sub     rsp, 250h
0x1800045c1  mov     rax, cs:__security_cookie
0x1800045c8  xor     rax, rsp
0x1800045cb  mov     [rsp+278h+var_38], rax
0x1800045d3  mov     rax, 0C000000000000000h
0x1800045dd  mov     rbp, r9
0x1800045e0  mov     r8, rdx
0x1800045e3  mov     rbx, rcx
0x1800045e6  test    rax, r9
0x1800045e9  jnz     loc_1800047B9
0x1800045ef  xor     r12d, r12d
0x1800045f2  lea     rax, [rsp+278h+Name]
0x1800045f7  mov     ecx, 7FFFFFFEh
0x1800045fc  mov     edx, 104h
0x180004601  lea     esi, [r12+1]
0x180004606  test    rcx, rcx
0x180004609  jz      short loc_180004629
0x18000460b  movzx   r9d, word ptr [r8]
0x18000460f  test    r9w, r9w
0x180004613  jz      short loc_180004629
0x180004615  mov     [rax], r9w
0x180004619  add     r8, 2
0x18000461d  add     rax, 2
0x180004621  sub     rcx, rsi
0x180004624  sub     rdx, rsi; unsigned __int64
0x180004627  jnz     short loc_180004606
0x180004629  test    rdx, rdx
0x18000462c  lea     rcx, [rax-2]
0x180004630  lea     r8, aP0; "_p0"
0x180004637  cmovnz  rcx, rax
0x18000463b  mov     [rcx], r12w
0x18000463f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004644  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004649  mov     edx, ebp
0x18000464b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004653  and     edx, 7FFFFFFFh; lInitialCount
0x180004659  mov     [rsp+278h+dwFlags], r12d; int
0x18000465e  mov     r8d, esi
0x180004661  lea     r9, [rsp+278h+Name]; lpName
0x180004666  cmova   r8d, edx; lMaximumCount
0x18000466a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000466c  call    cs:__imp_CreateSemaphoreExW
0x180004672  mov     r15, rax
0x180004675  test    rax, rax
0x180004678  jnz     short loc_1800046A8
0x18000467a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000467f  mov     edi, eax
0x180004681  test    eax, eax
0x180004683  jns     short loc_1800046DC
0x180004685  mov     rcx, [rsp+278h]; this
0x18000468d  lea     r8, aWil; "wil"
0x180004694  mov     r9d, eax; char *
0x180004697  mov     edx, 8Bh; void *
0x18000469c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046a1  mov     eax, edi
0x1800046a3  jmp     loc_18000477A
0x1800046a8  call    cs:__imp_GetLastError
0x1800046ae  mov     rdi, [rbx]
0x1800046b1  test    rdi, rdi
0x1800046b4  jz      short loc_1800046D9
0x1800046b6  call    cs:__imp_GetLastError
0x1800046bc  mov     rcx, rdi; hObject
0x1800046bf  mov     r14d, eax
0x1800046c2  call    cs:__imp_CloseHandle
0x1800046c8  test    eax, eax
0x1800046ca  jz      loc_1800047BF
0x1800046d0  mov     ecx, r14d; dwErrCode
0x1800046d3  call    cs:__imp_SetLastError
0x1800046d9  mov     [rbx], r15
0x1800046dc  lea     r8, asc_180015C48; "h"
0x1800046e3  shr     rbp, 1Fh
0x1800046e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800046ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800046f1  test    ebp, ebp
0x1800046f3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800046fb  lea     r9, [rsp+278h+Name]; lpName
0x180004700  mov     [rsp+278h+dwFlags], r12d; int
0x180004705  cmovnz  esi, ebp
0x180004708  mov     edx, ebp; lInitialCount
0x18000470a  mov     r8d, esi; lMaximumCount
0x18000470d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000470f  call    cs:__imp_CreateSemaphoreExW
0x180004715  mov     rsi, rax
0x180004718  test    rax, rax
0x18000471b  jnz     short loc_180004748
0x18000471d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004722  mov     ebx, eax
0x180004724  test    eax, eax
0x180004726  jns     short loc_180004778
0x180004728  mov     rcx, [rsp+278h]; this
0x180004730  lea     r8, aWil; "wil"
0x180004737  mov     r9d, eax; char *
0x18000473a  mov     edx, 90h; void *
0x18000473f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004744  mov     eax, ebx
0x180004746  jmp     short loc_18000477A
0x180004748  call    cs:__imp_GetLastError
0x18000474e  mov     rdi, [rbx+8]
0x180004752  test    rdi, rdi
0x180004755  jz      short loc_180004774
0x180004757  call    cs:__imp_GetLastError
0x18000475d  mov     rcx, rdi; hObject
0x180004760  mov     ebp, eax
0x180004762  call    cs:__imp_CloseHandle
0x180004768  test    eax, eax
0x18000476a  jz      short loc_1800047A6
0x18000476c  mov     ecx, ebp; dwErrCode
0x18000476e  call    cs:__imp_SetLastError
0x180004774  mov     [rbx+8], rsi
0x180004778  xor     eax, eax
0x18000477a  mov     rcx, [rsp+278h+var_38]
0x180004782  xor     rcx, rsp; StackCookie
0x180004785  call    __security_check_cookie
0x18000478a  lea     r11, [rsp+278h+var_28]
0x180004792  mov     rbx, [r11+38h]
0x180004796  mov     rbp, [r11+40h]
0x18000479a  mov     rsp, r11
0x18000479d  pop     r15
0x18000479f  pop     r14
0x1800047a1  pop     r12
0x1800047a3  pop     rdi
0x1800047a4  pop     rsi
0x1800047a5  retn
0x1800047a6  mov     rcx, [rsp+278h]; this
0x1800047ae  mov     edx, 0A0Bh; void *
0x1800047b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047b9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800047bf  mov     rcx, [rsp+278h]; this
0x1800047c7  mov     edx, 0A0Bh; void *
0x1800047cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
