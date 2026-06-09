# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004694`
- end: `0x1800048a1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800042e8`

## callees

- `0x180002650`
- `0x180004694`
- `0x1800050c8`
- `0x180006224`
- `0x180006b00`
- `0x18000716c`
- `0x18000717c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004758`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800047f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004758`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800047f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000483d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000483d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000478d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000479b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000478d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000479b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004826`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004831`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x180004694  mov     [rsp+arg_8], rbx
0x180004699  mov     [rsp+arg_10], rbp
0x18000469e  push    rsi
0x18000469f  push    rdi
0x1800046a0  push    r12
0x1800046a2  push    r14
0x1800046a4  push    r15
0x1800046a6  sub     rsp, 250h
0x1800046ad  mov     rax, cs:__security_cookie
0x1800046b4  xor     rax, rsp
0x1800046b7  mov     [rsp+278h+var_38], rax
0x1800046bf  mov     rax, 0C000000000000000h
0x1800046c9  mov     rbp, r9
0x1800046cc  mov     r8, rdx
0x1800046cf  mov     rdi, rcx
0x1800046d2  test    rax, r9
0x1800046d5  jnz     loc_180004888
0x1800046db  xor     r12d, r12d
0x1800046de  lea     rax, [rsp+278h+Name]
0x1800046e3  mov     ecx, 7FFFFFFEh
0x1800046e8  mov     edx, 104h
0x1800046ed  lea     esi, [r12+1]
0x1800046f2  test    rcx, rcx
0x1800046f5  jz      short loc_180004715
0x1800046f7  movzx   r9d, word ptr [r8]
0x1800046fb  test    r9w, r9w
0x1800046ff  jz      short loc_180004715
0x180004701  mov     [rax], r9w
0x180004705  add     r8, 2
0x180004709  add     rax, 2
0x18000470d  sub     rcx, rsi
0x180004710  sub     rdx, rsi; unsigned __int64
0x180004713  jnz     short loc_1800046F2
0x180004715  test    rdx, rdx
0x180004718  lea     rcx, [rax-2]
0x18000471c  lea     r8, aP0; "_p0"
0x180004723  cmovnz  rcx, rax
0x180004727  mov     [rcx], r12w
0x18000472b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004730  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004735  mov     edx, ebp
0x180004737  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000473f  and     edx, 7FFFFFFFh; lInitialCount
0x180004745  mov     [rsp+278h+dwFlags], r12d; int
0x18000474a  mov     r8d, esi
0x18000474d  lea     r9, [rsp+278h+Name]; lpName
0x180004752  cmova   r8d, edx; lMaximumCount
0x180004756  xor     ecx, ecx; lpSemaphoreAttributes
0x180004758  call    cs:__imp_CreateSemaphoreExW
0x18000475e  mov     r15, rax
0x180004761  test    rax, rax
0x180004764  jnz     short loc_18000478D
0x180004766  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000476b  mov     ebx, eax
0x18000476d  test    eax, eax
0x18000476f  jns     short loc_1800047C1
0x180004771  mov     edx, 8Bh; void *
0x180004776  mov     rcx, [rsp+278h]; this
0x18000477e  mov     r9d, ebx; char *
0x180004781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004786  mov     eax, ebx
0x180004788  jmp     loc_180004849
0x18000478d  call    cs:__imp_GetLastError
0x180004793  mov     rbx, [rdi]
0x180004796  test    rbx, rbx
0x180004799  jz      short loc_1800047BE
0x18000479b  call    cs:__imp_GetLastError
0x1800047a1  mov     rcx, rbx; hObject
0x1800047a4  mov     r14d, eax
0x1800047a7  call    cs:__imp_CloseHandle
0x1800047ad  test    eax, eax
0x1800047af  jz      loc_18000488E
0x1800047b5  mov     ecx, r14d; dwErrCode
0x1800047b8  call    cs:__imp_SetLastError
0x1800047be  mov     [rdi], r15
0x1800047c1  lea     r8, asc_18000F0A8; "h"
0x1800047c8  shr     rbp, 1Fh
0x1800047cc  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800047d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800047d6  test    ebp, ebp
0x1800047d8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800047e0  lea     r9, [rsp+278h+Name]; lpName
0x1800047e5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800047ea  cmovnz  esi, ebp
0x1800047ed  mov     edx, ebp; lInitialCount
0x1800047ef  mov     r8d, esi; lMaximumCount
0x1800047f2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800047f4  call    cs:__imp_CreateSemaphoreExW
0x1800047fa  mov     rsi, rax
0x1800047fd  test    rax, rax
0x180004800  jnz     short loc_180004817
0x180004802  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004807  mov     ebx, eax
0x180004809  test    eax, eax
0x18000480b  jns     short loc_180004847
0x18000480d  mov     edx, 90h
0x180004812  jmp     loc_180004776
0x180004817  call    cs:__imp_GetLastError
0x18000481d  mov     rbx, [rdi+8]
0x180004821  test    rbx, rbx
0x180004824  jz      short loc_180004843
0x180004826  call    cs:__imp_GetLastError
0x18000482c  mov     rcx, rbx; hObject
0x18000482f  mov     ebp, eax
0x180004831  call    cs:__imp_CloseHandle
0x180004837  test    eax, eax
0x180004839  jz      short loc_180004875
0x18000483b  mov     ecx, ebp; dwErrCode
0x18000483d  call    cs:__imp_SetLastError
0x180004843  mov     [rdi+8], rsi
0x180004847  xor     eax, eax
0x180004849  mov     rcx, [rsp+278h+var_38]
0x180004851  xor     rcx, rsp; StackCookie
0x180004854  call    __security_check_cookie
0x180004859  lea     r11, [rsp+278h+var_28]
0x180004861  mov     rbx, [r11+38h]
0x180004865  mov     rbp, [r11+40h]
0x180004869  mov     rsp, r11
0x18000486c  pop     r15
0x18000486e  pop     r14
0x180004870  pop     r12
0x180004872  pop     rdi
0x180004873  pop     rsi
0x180004874  retn
0x180004875  mov     rcx, [rsp+278h]; this
0x18000487d  mov     edx, 0A0Bh; void *
0x180004882  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004888  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000488e  mov     rcx, [rsp+278h]; this
0x180004896  mov     edx, 0A0Bh; void *
0x18000489b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
