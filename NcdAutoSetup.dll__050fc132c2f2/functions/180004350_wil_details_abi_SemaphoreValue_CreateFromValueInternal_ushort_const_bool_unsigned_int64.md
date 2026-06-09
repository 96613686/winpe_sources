# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004350`
- end: `0x18000455d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a78`
- `0x180003e1c`

## callees

- `0x180004350`
- `0x180005168`
- `0x1800075c0`
- `0x180008150`
- `0x180009474`
- `0x180009484`
- `0x180013840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044f9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004414`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004414`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`

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
0x180004350  mov     [rsp+arg_8], rbx
0x180004355  mov     [rsp+arg_10], rbp
0x18000435a  push    rsi
0x18000435b  push    rdi
0x18000435c  push    r12
0x18000435e  push    r14
0x180004360  push    r15
0x180004362  sub     rsp, 250h
0x180004369  mov     rax, cs:__security_cookie
0x180004370  xor     rax, rsp
0x180004373  mov     [rsp+278h+var_38], rax
0x18000437b  mov     rax, 0C000000000000000h
0x180004385  mov     rbp, r9
0x180004388  mov     r8, rdx
0x18000438b  mov     rdi, rcx
0x18000438e  test    rax, r9
0x180004391  jnz     loc_180004544
0x180004397  xor     r12d, r12d
0x18000439a  lea     rax, [rsp+278h+Name]
0x18000439f  mov     ecx, 7FFFFFFEh
0x1800043a4  mov     edx, 104h
0x1800043a9  lea     esi, [r12+1]
0x1800043ae  test    rcx, rcx
0x1800043b1  jz      short loc_1800043D1
0x1800043b3  movzx   r9d, word ptr [r8]
0x1800043b7  test    r9w, r9w
0x1800043bb  jz      short loc_1800043D1
0x1800043bd  mov     [rax], r9w
0x1800043c1  add     r8, 2
0x1800043c5  add     rax, 2
0x1800043c9  sub     rcx, rsi
0x1800043cc  sub     rdx, rsi; unsigned __int64
0x1800043cf  jnz     short loc_1800043AE
0x1800043d1  test    rdx, rdx
0x1800043d4  lea     rcx, [rax-2]
0x1800043d8  lea     r8, aP0; "_p0"
0x1800043df  cmovnz  rcx, rax
0x1800043e3  mov     [rcx], r12w
0x1800043e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800043ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043f1  mov     edx, ebp
0x1800043f3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043fb  and     edx, 7FFFFFFFh; lInitialCount
0x180004401  mov     [rsp+278h+dwFlags], r12d; int
0x180004406  mov     r8d, esi
0x180004409  lea     r9, [rsp+278h+Name]; lpName
0x18000440e  cmova   r8d, edx; lMaximumCount
0x180004412  xor     ecx, ecx; lpSemaphoreAttributes
0x180004414  call    cs:__imp_CreateSemaphoreExW
0x18000441a  mov     r15, rax
0x18000441d  test    rax, rax
0x180004420  jnz     short loc_180004449
0x180004422  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004427  mov     ebx, eax
0x180004429  test    eax, eax
0x18000442b  jns     short loc_18000447D
0x18000442d  mov     edx, 8Bh; void *
0x180004432  mov     rcx, [rsp+278h]; this
0x18000443a  mov     r9d, ebx; char *
0x18000443d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004442  mov     eax, ebx
0x180004444  jmp     loc_180004505
0x180004449  call    cs:__imp_GetLastError
0x18000444f  mov     rbx, [rdi]
0x180004452  test    rbx, rbx
0x180004455  jz      short loc_18000447A
0x180004457  call    cs:__imp_GetLastError
0x18000445d  mov     rcx, rbx; hObject
0x180004460  mov     r14d, eax
0x180004463  call    cs:__imp_CloseHandle
0x180004469  test    eax, eax
0x18000446b  jz      loc_18000454A
0x180004471  mov     ecx, r14d; dwErrCode
0x180004474  call    cs:__imp_SetLastError
0x18000447a  mov     [rdi], r15
0x18000447d  lea     r8, asc_180015FC0; "h"
0x180004484  shr     rbp, 1Fh
0x180004488  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000448d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004492  test    ebp, ebp
0x180004494  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000449c  lea     r9, [rsp+278h+Name]; lpName
0x1800044a1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800044a6  cmovnz  esi, ebp
0x1800044a9  mov     edx, ebp; lInitialCount
0x1800044ab  mov     r8d, esi; lMaximumCount
0x1800044ae  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044b0  call    cs:__imp_CreateSemaphoreExW
0x1800044b6  mov     rsi, rax
0x1800044b9  test    rax, rax
0x1800044bc  jnz     short loc_1800044D3
0x1800044be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044c3  mov     ebx, eax
0x1800044c5  test    eax, eax
0x1800044c7  jns     short loc_180004503
0x1800044c9  mov     edx, 90h
0x1800044ce  jmp     loc_180004432
0x1800044d3  call    cs:__imp_GetLastError
0x1800044d9  mov     rbx, [rdi+8]
0x1800044dd  test    rbx, rbx
0x1800044e0  jz      short loc_1800044FF
0x1800044e2  call    cs:__imp_GetLastError
0x1800044e8  mov     rcx, rbx; hObject
0x1800044eb  mov     ebp, eax
0x1800044ed  call    cs:__imp_CloseHandle
0x1800044f3  test    eax, eax
0x1800044f5  jz      short loc_180004531
0x1800044f7  mov     ecx, ebp; dwErrCode
0x1800044f9  call    cs:__imp_SetLastError
0x1800044ff  mov     [rdi+8], rsi
0x180004503  xor     eax, eax
0x180004505  mov     rcx, [rsp+278h+var_38]
0x18000450d  xor     rcx, rsp; StackCookie
0x180004510  call    __security_check_cookie
0x180004515  lea     r11, [rsp+278h+var_28]
0x18000451d  mov     rbx, [r11+38h]
0x180004521  mov     rbp, [r11+40h]
0x180004525  mov     rsp, r11
0x180004528  pop     r15
0x18000452a  pop     r14
0x18000452c  pop     r12
0x18000452e  pop     rdi
0x18000452f  pop     rsi
0x180004530  retn
0x180004531  mov     rcx, [rsp+278h]; this
0x180004539  mov     edx, 0A0Bh; void *
0x18000453e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004544  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000454a  mov     rcx, [rsp+278h]; this
0x180004552  mov     edx, 0A0Bh; void *
0x180004557  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
