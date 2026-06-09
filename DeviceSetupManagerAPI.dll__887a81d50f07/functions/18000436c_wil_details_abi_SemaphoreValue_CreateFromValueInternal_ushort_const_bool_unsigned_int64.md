# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000436c`
- end: `0x180004579`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bf8`
- `0x180003f9c`

## callees

- `0x1800017c0`
- `0x18000436c`
- `0x1800050e8`
- `0x180007004`
- `0x180007a48`
- `0x18000862c`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004430`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044cc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004430`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004515`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000447f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000447f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004509`

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
0x18000436c  mov     [rsp+arg_8], rbx
0x180004371  mov     [rsp+arg_10], rbp
0x180004376  push    rsi
0x180004377  push    rdi
0x180004378  push    r12
0x18000437a  push    r14
0x18000437c  push    r15
0x18000437e  sub     rsp, 250h
0x180004385  mov     rax, cs:__security_cookie
0x18000438c  xor     rax, rsp
0x18000438f  mov     [rsp+278h+var_38], rax
0x180004397  mov     rax, 0C000000000000000h
0x1800043a1  mov     rbp, r9
0x1800043a4  mov     r8, rdx
0x1800043a7  mov     rdi, rcx
0x1800043aa  test    rax, r9
0x1800043ad  jnz     loc_180004560
0x1800043b3  xor     r12d, r12d
0x1800043b6  lea     rax, [rsp+278h+Name]
0x1800043bb  mov     ecx, 7FFFFFFEh
0x1800043c0  mov     edx, 104h
0x1800043c5  lea     esi, [r12+1]
0x1800043ca  test    rcx, rcx
0x1800043cd  jz      short loc_1800043ED
0x1800043cf  movzx   r9d, word ptr [r8]
0x1800043d3  test    r9w, r9w
0x1800043d7  jz      short loc_1800043ED
0x1800043d9  mov     [rax], r9w
0x1800043dd  add     r8, 2
0x1800043e1  add     rax, 2
0x1800043e5  sub     rcx, rsi
0x1800043e8  sub     rdx, rsi; unsigned __int64
0x1800043eb  jnz     short loc_1800043CA
0x1800043ed  test    rdx, rdx
0x1800043f0  lea     rcx, [rax-2]
0x1800043f4  lea     r8, aP0; "_p0"
0x1800043fb  cmovnz  rcx, rax
0x1800043ff  mov     [rcx], r12w
0x180004403  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004408  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000440d  mov     edx, ebp
0x18000440f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004417  and     edx, 7FFFFFFFh; lInitialCount
0x18000441d  mov     [rsp+278h+dwFlags], r12d; int
0x180004422  mov     r8d, esi
0x180004425  lea     r9, [rsp+278h+Name]; lpName
0x18000442a  cmova   r8d, edx; lMaximumCount
0x18000442e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004430  call    cs:__imp_CreateSemaphoreExW
0x180004436  mov     r15, rax
0x180004439  test    rax, rax
0x18000443c  jnz     short loc_180004465
0x18000443e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004443  mov     ebx, eax
0x180004445  test    eax, eax
0x180004447  jns     short loc_180004499
0x180004449  mov     edx, 8Bh; void *
0x18000444e  mov     rcx, [rsp+278h]; this
0x180004456  mov     r9d, ebx; char *
0x180004459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000445e  mov     eax, ebx
0x180004460  jmp     loc_180004521
0x180004465  call    cs:__imp_GetLastError
0x18000446b  mov     rbx, [rdi]
0x18000446e  test    rbx, rbx
0x180004471  jz      short loc_180004496
0x180004473  call    cs:__imp_GetLastError
0x180004479  mov     rcx, rbx; hObject
0x18000447c  mov     r14d, eax
0x18000447f  call    cs:__imp_CloseHandle
0x180004485  test    eax, eax
0x180004487  jz      loc_180004566
0x18000448d  mov     ecx, r14d; dwErrCode
0x180004490  call    cs:__imp_SetLastError
0x180004496  mov     [rdi], r15
0x180004499  lea     r8, asc_180012A60; "h"
0x1800044a0  shr     rbp, 1Fh
0x1800044a4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800044a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800044ae  test    ebp, ebp
0x1800044b0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800044b8  lea     r9, [rsp+278h+Name]; lpName
0x1800044bd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800044c2  cmovnz  esi, ebp
0x1800044c5  mov     edx, ebp; lInitialCount
0x1800044c7  mov     r8d, esi; lMaximumCount
0x1800044ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044cc  call    cs:__imp_CreateSemaphoreExW
0x1800044d2  mov     rsi, rax
0x1800044d5  test    rax, rax
0x1800044d8  jnz     short loc_1800044EF
0x1800044da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044df  mov     ebx, eax
0x1800044e1  test    eax, eax
0x1800044e3  jns     short loc_18000451F
0x1800044e5  mov     edx, 90h
0x1800044ea  jmp     loc_18000444E
0x1800044ef  call    cs:__imp_GetLastError
0x1800044f5  mov     rbx, [rdi+8]
0x1800044f9  test    rbx, rbx
0x1800044fc  jz      short loc_18000451B
0x1800044fe  call    cs:__imp_GetLastError
0x180004504  mov     rcx, rbx; hObject
0x180004507  mov     ebp, eax
0x180004509  call    cs:__imp_CloseHandle
0x18000450f  test    eax, eax
0x180004511  jz      short loc_18000454D
0x180004513  mov     ecx, ebp; dwErrCode
0x180004515  call    cs:__imp_SetLastError
0x18000451b  mov     [rdi+8], rsi
0x18000451f  xor     eax, eax
0x180004521  mov     rcx, [rsp+278h+var_38]
0x180004529  xor     rcx, rsp; StackCookie
0x18000452c  call    __security_check_cookie
0x180004531  lea     r11, [rsp+278h+var_28]
0x180004539  mov     rbx, [r11+38h]
0x18000453d  mov     rbp, [r11+40h]
0x180004541  mov     rsp, r11
0x180004544  pop     r15
0x180004546  pop     r14
0x180004548  pop     r12
0x18000454a  pop     rdi
0x18000454b  pop     rsi
0x18000454c  retn
0x18000454d  mov     rcx, [rsp+278h]; this
0x180004555  mov     edx, 0A0Bh; void *
0x18000455a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004560  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004566  mov     rcx, [rsp+278h]; this
0x18000456e  mov     edx, 0A0Bh; void *
0x180004573  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
