# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800043ec`
- end: `0x180004616`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004010`
- `0x180009988`

## callees

- `0x1800043ec`
- `0x180004cc8`
- `0x180006074`
- `0x1800067f4`
- `0x180006f00`
- `0x180006f10`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004553`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000458c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000458c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004517`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004517`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045a6`

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
0x1800043ec  mov     [rsp+arg_8], rbx
0x1800043f1  mov     [rsp+arg_10], rbp
0x1800043f6  push    rsi
0x1800043f7  push    rdi
0x1800043f8  push    r12
0x1800043fa  push    r14
0x1800043fc  push    r15
0x1800043fe  sub     rsp, 250h
0x180004405  mov     rax, cs:__security_cookie
0x18000440c  xor     rax, rsp
0x18000440f  mov     [rsp+278h+var_38], rax
0x180004417  mov     rax, 0C000000000000000h
0x180004421  mov     rbp, r9
0x180004424  mov     r8, rdx
0x180004427  mov     rbx, rcx
0x18000442a  test    rax, r9
0x18000442d  jnz     loc_1800045FD
0x180004433  xor     r12d, r12d
0x180004436  lea     rax, [rsp+278h+Name]
0x18000443b  mov     ecx, 7FFFFFFEh
0x180004440  mov     edx, 104h
0x180004445  lea     esi, [r12+1]
0x18000444a  test    rcx, rcx
0x18000444d  jz      short loc_18000446D
0x18000444f  movzx   r9d, word ptr [r8]
0x180004453  test    r9w, r9w
0x180004457  jz      short loc_18000446D
0x180004459  mov     [rax], r9w
0x18000445d  add     r8, 2
0x180004461  add     rax, 2
0x180004465  sub     rcx, rsi
0x180004468  sub     rdx, rsi; unsigned __int64
0x18000446b  jnz     short loc_18000444A
0x18000446d  test    rdx, rdx
0x180004470  lea     rcx, [rax-2]
0x180004474  lea     r8, aP0; "_p0"
0x18000447b  cmovnz  rcx, rax
0x18000447f  mov     [rcx], r12w
0x180004483  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004488  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000448d  mov     edx, ebp
0x18000448f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004497  and     edx, 7FFFFFFFh; lInitialCount
0x18000449d  mov     [rsp+278h+dwFlags], r12d; int
0x1800044a2  mov     r8d, esi
0x1800044a5  lea     r9, [rsp+278h+Name]; lpName
0x1800044aa  cmova   r8d, edx; lMaximumCount
0x1800044ae  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044b0  call    cs:__imp_CreateSemaphoreExW
0x1800044b6  mov     r15, rax
0x1800044b9  test    rax, rax
0x1800044bc  jnz     short loc_1800044EC
0x1800044be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044c3  mov     edi, eax
0x1800044c5  test    eax, eax
0x1800044c7  jns     short loc_180004520
0x1800044c9  mov     rcx, [rsp+278h]; this
0x1800044d1  lea     r8, aWil; "wil"
0x1800044d8  mov     r9d, eax; char *
0x1800044db  mov     edx, 8Bh; void *
0x1800044e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044e5  mov     eax, edi
0x1800044e7  jmp     loc_1800045BE
0x1800044ec  call    cs:__imp_GetLastError
0x1800044f2  mov     rdi, [rbx]
0x1800044f5  test    rdi, rdi
0x1800044f8  jz      short loc_18000451D
0x1800044fa  call    cs:__imp_GetLastError
0x180004500  mov     rcx, rdi; hObject
0x180004503  mov     r14d, eax
0x180004506  call    cs:__imp_CloseHandle
0x18000450c  test    eax, eax
0x18000450e  jz      loc_180004603
0x180004514  mov     ecx, r14d; dwErrCode
0x180004517  call    cs:__imp_SetLastError
0x18000451d  mov     [rbx], r15
0x180004520  lea     r8, asc_180034058; "h"
0x180004527  shr     rbp, 1Fh
0x18000452b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004530  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004535  test    ebp, ebp
0x180004537  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000453f  lea     r9, [rsp+278h+Name]; lpName
0x180004544  mov     [rsp+278h+dwFlags], r12d; int
0x180004549  cmovnz  esi, ebp
0x18000454c  mov     edx, ebp; lInitialCount
0x18000454e  mov     r8d, esi; lMaximumCount
0x180004551  xor     ecx, ecx; lpSemaphoreAttributes
0x180004553  call    cs:__imp_CreateSemaphoreExW
0x180004559  mov     rsi, rax
0x18000455c  test    rax, rax
0x18000455f  jnz     short loc_18000458C
0x180004561  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004566  mov     ebx, eax
0x180004568  test    eax, eax
0x18000456a  jns     short loc_1800045BC
0x18000456c  mov     rcx, [rsp+278h]; this
0x180004574  lea     r8, aWil; "wil"
0x18000457b  mov     r9d, eax; char *
0x18000457e  mov     edx, 90h; void *
0x180004583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004588  mov     eax, ebx
0x18000458a  jmp     short loc_1800045BE
0x18000458c  call    cs:__imp_GetLastError
0x180004592  mov     rdi, [rbx+8]
0x180004596  test    rdi, rdi
0x180004599  jz      short loc_1800045B8
0x18000459b  call    cs:__imp_GetLastError
0x1800045a1  mov     rcx, rdi; hObject
0x1800045a4  mov     ebp, eax
0x1800045a6  call    cs:__imp_CloseHandle
0x1800045ac  test    eax, eax
0x1800045ae  jz      short loc_1800045EA
0x1800045b0  mov     ecx, ebp; dwErrCode
0x1800045b2  call    cs:__imp_SetLastError
0x1800045b8  mov     [rbx+8], rsi
0x1800045bc  xor     eax, eax
0x1800045be  mov     rcx, [rsp+278h+var_38]
0x1800045c6  xor     rcx, rsp; StackCookie
0x1800045c9  call    __security_check_cookie
0x1800045ce  lea     r11, [rsp+278h+var_28]
0x1800045d6  mov     rbx, [r11+38h]
0x1800045da  mov     rbp, [r11+40h]
0x1800045de  mov     rsp, r11
0x1800045e1  pop     r15
0x1800045e3  pop     r14
0x1800045e5  pop     r12
0x1800045e7  pop     rdi
0x1800045e8  pop     rsi
0x1800045e9  retn
0x1800045ea  mov     rcx, [rsp+278h]; this
0x1800045f2  mov     edx, 0A0Bh; void *
0x1800045f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045fd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004603  mov     rcx, [rsp+278h]; this
0x18000460b  mov     edx, 0A0Bh; void *
0x180004610  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
