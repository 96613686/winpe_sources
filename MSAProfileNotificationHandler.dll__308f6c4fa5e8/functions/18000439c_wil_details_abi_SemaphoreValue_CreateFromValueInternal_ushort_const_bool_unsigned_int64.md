# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000439c`
- end: `0x1800045a9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ff8`

## callees

- `0x180001cb0`
- `0x18000439c`
- `0x180004c08`
- `0x180005dc4`
- `0x180006070`
- `0x180006efc`
- `0x180006f0c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000451f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000451f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004545`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004545`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004460`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044fc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004460`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044fc`

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
0x18000439c  mov     [rsp+arg_8], rbx
0x1800043a1  mov     [rsp+arg_10], rbp
0x1800043a6  push    rsi
0x1800043a7  push    rdi
0x1800043a8  push    r12
0x1800043aa  push    r14
0x1800043ac  push    r15
0x1800043ae  sub     rsp, 250h
0x1800043b5  mov     rax, cs:__security_cookie
0x1800043bc  xor     rax, rsp
0x1800043bf  mov     [rsp+278h+var_38], rax
0x1800043c7  mov     rax, 0C000000000000000h
0x1800043d1  mov     rbp, r9
0x1800043d4  mov     r8, rdx
0x1800043d7  mov     rdi, rcx
0x1800043da  test    rax, r9
0x1800043dd  jnz     loc_180004590
0x1800043e3  xor     r12d, r12d
0x1800043e6  lea     rax, [rsp+278h+Name]
0x1800043eb  mov     ecx, 7FFFFFFEh
0x1800043f0  mov     edx, 104h
0x1800043f5  lea     esi, [r12+1]
0x1800043fa  test    rcx, rcx
0x1800043fd  jz      short loc_18000441D
0x1800043ff  movzx   r9d, word ptr [r8]
0x180004403  test    r9w, r9w
0x180004407  jz      short loc_18000441D
0x180004409  mov     [rax], r9w
0x18000440d  add     r8, 2
0x180004411  add     rax, 2
0x180004415  sub     rcx, rsi
0x180004418  sub     rdx, rsi; unsigned __int64
0x18000441b  jnz     short loc_1800043FA
0x18000441d  test    rdx, rdx
0x180004420  lea     rcx, [rax-2]
0x180004424  lea     r8, aP0; "_p0"
0x18000442b  cmovnz  rcx, rax
0x18000442f  mov     [rcx], r12w
0x180004433  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004438  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000443d  mov     edx, ebp
0x18000443f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004447  and     edx, 7FFFFFFFh; lInitialCount
0x18000444d  mov     [rsp+278h+dwFlags], r12d; int
0x180004452  mov     r8d, esi
0x180004455  lea     r9, [rsp+278h+Name]; lpName
0x18000445a  cmova   r8d, edx; lMaximumCount
0x18000445e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004460  call    cs:__imp_CreateSemaphoreExW
0x180004466  mov     r15, rax
0x180004469  test    rax, rax
0x18000446c  jnz     short loc_180004495
0x18000446e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004473  mov     ebx, eax
0x180004475  test    eax, eax
0x180004477  jns     short loc_1800044C9
0x180004479  mov     edx, 8Bh; void *
0x18000447e  mov     rcx, [rsp+278h]; this
0x180004486  mov     r9d, ebx; char *
0x180004489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000448e  mov     eax, ebx
0x180004490  jmp     loc_180004551
0x180004495  call    cs:__imp_GetLastError
0x18000449b  mov     rbx, [rdi]
0x18000449e  test    rbx, rbx
0x1800044a1  jz      short loc_1800044C6
0x1800044a3  call    cs:__imp_GetLastError
0x1800044a9  mov     rcx, rbx; hObject
0x1800044ac  mov     r14d, eax
0x1800044af  call    cs:__imp_CloseHandle
0x1800044b5  test    eax, eax
0x1800044b7  jz      loc_180004596
0x1800044bd  mov     ecx, r14d; dwErrCode
0x1800044c0  call    cs:__imp_SetLastError
0x1800044c6  mov     [rdi], r15
0x1800044c9  lea     r8, asc_18000E088; "h"
0x1800044d0  shr     rbp, 1Fh
0x1800044d4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800044d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800044de  test    ebp, ebp
0x1800044e0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800044e8  lea     r9, [rsp+278h+Name]; lpName
0x1800044ed  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800044f2  cmovnz  esi, ebp
0x1800044f5  mov     edx, ebp; lInitialCount
0x1800044f7  mov     r8d, esi; lMaximumCount
0x1800044fa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044fc  call    cs:__imp_CreateSemaphoreExW
0x180004502  mov     rsi, rax
0x180004505  test    rax, rax
0x180004508  jnz     short loc_18000451F
0x18000450a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000450f  mov     ebx, eax
0x180004511  test    eax, eax
0x180004513  jns     short loc_18000454F
0x180004515  mov     edx, 90h
0x18000451a  jmp     loc_18000447E
0x18000451f  call    cs:__imp_GetLastError
0x180004525  mov     rbx, [rdi+8]
0x180004529  test    rbx, rbx
0x18000452c  jz      short loc_18000454B
0x18000452e  call    cs:__imp_GetLastError
0x180004534  mov     rcx, rbx; hObject
0x180004537  mov     ebp, eax
0x180004539  call    cs:__imp_CloseHandle
0x18000453f  test    eax, eax
0x180004541  jz      short loc_18000457D
0x180004543  mov     ecx, ebp; dwErrCode
0x180004545  call    cs:__imp_SetLastError
0x18000454b  mov     [rdi+8], rsi
0x18000454f  xor     eax, eax
0x180004551  mov     rcx, [rsp+278h+var_38]
0x180004559  xor     rcx, rsp; StackCookie
0x18000455c  call    __security_check_cookie
0x180004561  lea     r11, [rsp+278h+var_28]
0x180004569  mov     rbx, [r11+38h]
0x18000456d  mov     rbp, [r11+40h]
0x180004571  mov     rsp, r11
0x180004574  pop     r15
0x180004576  pop     r14
0x180004578  pop     r12
0x18000457a  pop     rdi
0x18000457b  pop     rsi
0x18000457c  retn
0x18000457d  mov     rcx, [rsp+278h]; this
0x180004585  mov     edx, 0A0Bh; void *
0x18000458a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004590  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004596  mov     rcx, [rsp+278h]; this
0x18000459e  mov     edx, 0A0Bh; void *
0x1800045a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
