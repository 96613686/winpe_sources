# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800044b8`
- end: `0x1800046e9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800040e8`

## callees

- `0x180001b60`
- `0x1800044b8`
- `0x180004d48`
- `0x180005b04`
- `0x1800063e0`
- `0x1800069ac`
- `0x1800069bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000466f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000466f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004581`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004627`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004581`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000467a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000467a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
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
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
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
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
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
0x1800044b8  mov     [rsp+arg_8], rbx
0x1800044bd  push    rbp
0x1800044be  push    rsi
0x1800044bf  push    rdi
0x1800044c0  push    r12
0x1800044c2  push    r13
0x1800044c4  push    r14
0x1800044c6  push    r15
0x1800044c8  sub     rsp, 250h
0x1800044cf  mov     rax, cs:__security_cookie
0x1800044d6  xor     rax, rsp
0x1800044d9  mov     [rsp+288h+var_48], rax
0x1800044e1  mov     rax, 0C000000000000000h
0x1800044eb  mov     rsi, r9
0x1800044ee  mov     r8, rdx
0x1800044f1  mov     rbx, rcx
0x1800044f4  test    rax, r9
0x1800044f7  jnz     loc_1800046D0
0x1800044fd  xor     r12d, r12d
0x180004500  lea     rax, [rsp+288h+Name]
0x180004505  mov     r13d, 104h
0x18000450b  mov     ecx, 7FFFFFFEh
0x180004510  mov     edx, r13d
0x180004513  lea     ebp, [r12+1]
0x180004518  test    rcx, rcx
0x18000451b  jz      short loc_18000453B
0x18000451d  movzx   r9d, word ptr [r8]
0x180004521  test    r9w, r9w
0x180004525  jz      short loc_18000453B
0x180004527  mov     [rax], r9w
0x18000452b  add     r8, 2
0x18000452f  add     rax, 2
0x180004533  sub     rcx, rbp
0x180004536  sub     rdx, rbp
0x180004539  jnz     short loc_180004518
0x18000453b  test    rdx, rdx
0x18000453e  lea     rcx, [rax-2]
0x180004542  lea     r8, aP0; "_p0"
0x180004549  mov     rdx, r13; unsigned __int64
0x18000454c  cmovnz  rcx, rax
0x180004550  mov     [rcx], r12w
0x180004554  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004559  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000455e  mov     edx, esi
0x180004560  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004568  and     edx, 7FFFFFFFh; lInitialCount
0x18000456e  mov     [rsp+288h+dwFlags], r12d; int
0x180004573  mov     r8d, ebp
0x180004576  lea     r9, [rsp+288h+Name]; lpName
0x18000457b  cmova   r8d, edx; lMaximumCount
0x18000457f  xor     ecx, ecx; lpSemaphoreAttributes
0x180004581  call    cs:__imp_CreateSemaphoreExW
0x180004587  mov     r15, rax
0x18000458a  test    rax, rax
0x18000458d  jnz     short loc_1800045BD
0x18000458f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004594  mov     edi, eax
0x180004596  test    eax, eax
0x180004598  jns     short loc_1800045F1
0x18000459a  mov     rcx, [rsp+288h]; this
0x1800045a2  lea     r8, aWil; "wil"
0x1800045a9  mov     r9d, eax; char *
0x1800045ac  mov     edx, 8Bh; void *
0x1800045b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045b6  mov     eax, edi
0x1800045b8  jmp     loc_180004692
0x1800045bd  call    cs:__imp_GetLastError
0x1800045c3  mov     rdi, [rbx]
0x1800045c6  test    rdi, rdi
0x1800045c9  jz      short loc_1800045EE
0x1800045cb  call    cs:__imp_GetLastError
0x1800045d1  mov     rcx, rdi; hObject
0x1800045d4  mov     r14d, eax
0x1800045d7  call    cs:__imp_CloseHandle
0x1800045dd  test    eax, eax
0x1800045df  jz      loc_1800046D6
0x1800045e5  mov     ecx, r14d; dwErrCode
0x1800045e8  call    cs:__imp_SetLastError
0x1800045ee  mov     [rbx], r15
0x1800045f1  lea     r8, asc_18003B690; "h"
0x1800045f8  shr     rsi, 1Fh
0x1800045fc  mov     rdx, r13; unsigned __int64
0x1800045ff  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004604  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004609  test    esi, esi
0x18000460b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004613  lea     r9, [rsp+288h+Name]; lpName
0x180004618  mov     [rsp+288h+dwFlags], r12d; int
0x18000461d  cmovnz  ebp, esi
0x180004620  mov     edx, esi; lInitialCount
0x180004622  mov     r8d, ebp; lMaximumCount
0x180004625  xor     ecx, ecx; lpSemaphoreAttributes
0x180004627  call    cs:__imp_CreateSemaphoreExW
0x18000462d  mov     rbp, rax
0x180004630  test    rax, rax
0x180004633  jnz     short loc_180004660
0x180004635  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000463a  mov     ebx, eax
0x18000463c  test    eax, eax
0x18000463e  jns     short loc_180004690
0x180004640  mov     rcx, [rsp+288h]; this
0x180004648  lea     r8, aWil; "wil"
0x18000464f  mov     r9d, eax; char *
0x180004652  mov     edx, 90h; void *
0x180004657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000465c  mov     eax, ebx
0x18000465e  jmp     short loc_180004692
0x180004660  call    cs:__imp_GetLastError
0x180004666  mov     rdi, [rbx+8]
0x18000466a  test    rdi, rdi
0x18000466d  jz      short loc_18000468C
0x18000466f  call    cs:__imp_GetLastError
0x180004675  mov     rcx, rdi; hObject
0x180004678  mov     esi, eax
0x18000467a  call    cs:__imp_CloseHandle
0x180004680  test    eax, eax
0x180004682  jz      short loc_1800046BD
0x180004684  mov     ecx, esi; dwErrCode
0x180004686  call    cs:__imp_SetLastError
0x18000468c  mov     [rbx+8], rbp
0x180004690  xor     eax, eax
0x180004692  mov     rcx, [rsp+288h+var_48]
0x18000469a  xor     rcx, rsp; StackCookie
0x18000469d  call    __security_check_cookie
0x1800046a2  mov     rbx, [rsp+288h+arg_8]
0x1800046aa  add     rsp, 250h
0x1800046b1  pop     r15
0x1800046b3  pop     r14
0x1800046b5  pop     r13
0x1800046b7  pop     r12
0x1800046b9  pop     rdi
0x1800046ba  pop     rsi
0x1800046bb  pop     rbp
0x1800046bc  retn
0x1800046bd  mov     rcx, [rsp+288h]; this
0x1800046c5  mov     edx, 0A0Bh; void *
0x1800046ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800046d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800046d6  mov     rcx, [rsp+288h]; this
0x1800046de  mov     edx, 0A0Bh; void *
0x1800046e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
