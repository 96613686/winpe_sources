# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004600`
- end: `0x14000480d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003e78`
- `0x14000421c`

## callees

- `0x1400016a0`
- `0x140004600`
- `0x140006560`
- `0x1400098a4`
- `0x14000a750`
- `0x14000b51c`
- `0x14000b52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400046c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004760`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400046c4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004760`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004724`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004724`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400047a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004792`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000479d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000479d`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004600  mov     [rsp+arg_8], rbx
0x140004605  mov     [rsp+arg_10], rbp
0x14000460a  push    rsi
0x14000460b  push    rdi
0x14000460c  push    r12
0x14000460e  push    r14
0x140004610  push    r15
0x140004612  sub     rsp, 250h
0x140004619  mov     rax, cs:__security_cookie
0x140004620  xor     rax, rsp
0x140004623  mov     [rsp+278h+var_38], rax
0x14000462b  mov     rax, 0C000000000000000h
0x140004635  mov     rbp, r9
0x140004638  mov     r8, rdx
0x14000463b  mov     rdi, rcx
0x14000463e  test    rax, r9
0x140004641  jnz     loc_1400047F4
0x140004647  xor     r12d, r12d
0x14000464a  lea     rax, [rsp+278h+Name]
0x14000464f  mov     ecx, 7FFFFFFEh
0x140004654  mov     edx, 104h
0x140004659  lea     esi, [r12+1]
0x14000465e  test    rcx, rcx
0x140004661  jz      short loc_140004681
0x140004663  movzx   r9d, word ptr [r8]
0x140004667  test    r9w, r9w
0x14000466b  jz      short loc_140004681
0x14000466d  mov     [rax], r9w
0x140004671  add     r8, 2
0x140004675  add     rax, 2
0x140004679  sub     rcx, rsi
0x14000467c  sub     rdx, rsi; unsigned __int64
0x14000467f  jnz     short loc_14000465E
0x140004681  test    rdx, rdx
0x140004684  lea     rcx, [rax-2]
0x140004688  lea     r8, aP0; "_p0"
0x14000468f  cmovnz  rcx, rax
0x140004693  mov     [rcx], r12w
0x140004697  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000469c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400046a1  mov     edx, ebp
0x1400046a3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400046ab  and     edx, 7FFFFFFFh; lInitialCount
0x1400046b1  mov     [rsp+278h+dwFlags], r12d; int
0x1400046b6  mov     r8d, esi
0x1400046b9  lea     r9, [rsp+278h+Name]; lpName
0x1400046be  cmova   r8d, edx; lMaximumCount
0x1400046c2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400046c4  call    cs:__imp_CreateSemaphoreExW
0x1400046ca  mov     r15, rax
0x1400046cd  test    rax, rax
0x1400046d0  jnz     short loc_1400046F9
0x1400046d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400046d7  mov     ebx, eax
0x1400046d9  test    eax, eax
0x1400046db  jns     short loc_14000472D
0x1400046dd  mov     edx, 8Bh; void *
0x1400046e2  mov     rcx, [rsp+278h]; this
0x1400046ea  mov     r9d, ebx; char *
0x1400046ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400046f2  mov     eax, ebx
0x1400046f4  jmp     loc_1400047B5
0x1400046f9  call    cs:__imp_GetLastError
0x1400046ff  mov     rbx, [rdi]
0x140004702  test    rbx, rbx
0x140004705  jz      short loc_14000472A
0x140004707  call    cs:__imp_GetLastError
0x14000470d  mov     rcx, rbx; hObject
0x140004710  mov     r14d, eax
0x140004713  call    cs:__imp_CloseHandle
0x140004719  test    eax, eax
0x14000471b  jz      loc_1400047FA
0x140004721  mov     ecx, r14d; dwErrCode
0x140004724  call    cs:__imp_SetLastError
0x14000472a  mov     [rdi], r15
0x14000472d  lea     r8, asc_140013FE0; "h"
0x140004734  shr     rbp, 1Fh
0x140004738  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000473d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004742  test    ebp, ebp
0x140004744  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000474c  lea     r9, [rsp+278h+Name]; lpName
0x140004751  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004756  cmovnz  esi, ebp
0x140004759  mov     edx, ebp; lInitialCount
0x14000475b  mov     r8d, esi; lMaximumCount
0x14000475e  xor     ecx, ecx; lpSemaphoreAttributes
0x140004760  call    cs:__imp_CreateSemaphoreExW
0x140004766  mov     rsi, rax
0x140004769  test    rax, rax
0x14000476c  jnz     short loc_140004783
0x14000476e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004773  mov     ebx, eax
0x140004775  test    eax, eax
0x140004777  jns     short loc_1400047B3
0x140004779  mov     edx, 90h
0x14000477e  jmp     loc_1400046E2
0x140004783  call    cs:__imp_GetLastError
0x140004789  mov     rbx, [rdi+8]
0x14000478d  test    rbx, rbx
0x140004790  jz      short loc_1400047AF
0x140004792  call    cs:__imp_GetLastError
0x140004798  mov     rcx, rbx; hObject
0x14000479b  mov     ebp, eax
0x14000479d  call    cs:__imp_CloseHandle
0x1400047a3  test    eax, eax
0x1400047a5  jz      short loc_1400047E1
0x1400047a7  mov     ecx, ebp; dwErrCode
0x1400047a9  call    cs:__imp_SetLastError
0x1400047af  mov     [rdi+8], rsi
0x1400047b3  xor     eax, eax
0x1400047b5  mov     rcx, [rsp+278h+var_38]
0x1400047bd  xor     rcx, rsp; StackCookie
0x1400047c0  call    __security_check_cookie
0x1400047c5  lea     r11, [rsp+278h+var_28]
0x1400047cd  mov     rbx, [r11+38h]
0x1400047d1  mov     rbp, [r11+40h]
0x1400047d5  mov     rsp, r11
0x1400047d8  pop     r15
0x1400047da  pop     r14
0x1400047dc  pop     r12
0x1400047de  pop     rdi
0x1400047df  pop     rsi
0x1400047e0  retn
0x1400047e1  mov     rcx, [rsp+278h]; this
0x1400047e9  mov     edx, 0A0Bh; void *
0x1400047ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400047fa  mov     rcx, [rsp+278h]; this
0x140004802  mov     edx, 0A0Bh; void *
0x140004807  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
