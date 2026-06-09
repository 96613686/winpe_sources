# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800046cc`
- end: `0x1800048d9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f58`
- `0x1800042fc`

## callees

- `0x180001d30`
- `0x1800046cc`
- `0x180005518`
- `0x1800077c4`
- `0x180008208`
- `0x180008fcc`
- `0x180008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004790`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000482c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004790`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000482c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004875`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000484f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000485e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000484f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000485e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004869`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004869`

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
0x1800046cc  mov     [rsp+arg_8], rbx
0x1800046d1  mov     [rsp+arg_10], rbp
0x1800046d6  push    rsi
0x1800046d7  push    rdi
0x1800046d8  push    r12
0x1800046da  push    r14
0x1800046dc  push    r15
0x1800046de  sub     rsp, 250h
0x1800046e5  mov     rax, cs:__security_cookie
0x1800046ec  xor     rax, rsp
0x1800046ef  mov     [rsp+278h+var_38], rax
0x1800046f7  mov     rax, 0C000000000000000h
0x180004701  mov     rbp, r9
0x180004704  mov     r8, rdx
0x180004707  mov     rdi, rcx
0x18000470a  test    rax, r9
0x18000470d  jnz     loc_1800048C0
0x180004713  xor     r12d, r12d
0x180004716  lea     rax, [rsp+278h+Name]
0x18000471b  mov     ecx, 7FFFFFFEh
0x180004720  mov     edx, 104h
0x180004725  lea     esi, [r12+1]
0x18000472a  test    rcx, rcx
0x18000472d  jz      short loc_18000474D
0x18000472f  movzx   r9d, word ptr [r8]
0x180004733  test    r9w, r9w
0x180004737  jz      short loc_18000474D
0x180004739  mov     [rax], r9w
0x18000473d  add     r8, 2
0x180004741  add     rax, 2
0x180004745  sub     rcx, rsi
0x180004748  sub     rdx, rsi; unsigned __int64
0x18000474b  jnz     short loc_18000472A
0x18000474d  test    rdx, rdx
0x180004750  lea     rcx, [rax-2]
0x180004754  lea     r8, aP0; "_p0"
0x18000475b  cmovnz  rcx, rax
0x18000475f  mov     [rcx], r12w
0x180004763  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004768  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000476d  mov     edx, ebp
0x18000476f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004777  and     edx, 7FFFFFFFh; lInitialCount
0x18000477d  mov     [rsp+278h+dwFlags], r12d; int
0x180004782  mov     r8d, esi
0x180004785  lea     r9, [rsp+278h+Name]; lpName
0x18000478a  cmova   r8d, edx; lMaximumCount
0x18000478e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004790  call    cs:__imp_CreateSemaphoreExW
0x180004796  mov     r15, rax
0x180004799  test    rax, rax
0x18000479c  jnz     short loc_1800047C5
0x18000479e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800047a3  mov     ebx, eax
0x1800047a5  test    eax, eax
0x1800047a7  jns     short loc_1800047F9
0x1800047a9  mov     edx, 8Bh; void *
0x1800047ae  mov     rcx, [rsp+278h]; this
0x1800047b6  mov     r9d, ebx; char *
0x1800047b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047be  mov     eax, ebx
0x1800047c0  jmp     loc_180004881
0x1800047c5  call    cs:__imp_GetLastError
0x1800047cb  mov     rbx, [rdi]
0x1800047ce  test    rbx, rbx
0x1800047d1  jz      short loc_1800047F6
0x1800047d3  call    cs:__imp_GetLastError
0x1800047d9  mov     rcx, rbx; hObject
0x1800047dc  mov     r14d, eax
0x1800047df  call    cs:__imp_CloseHandle
0x1800047e5  test    eax, eax
0x1800047e7  jz      loc_1800048C6
0x1800047ed  mov     ecx, r14d; dwErrCode
0x1800047f0  call    cs:__imp_SetLastError
0x1800047f6  mov     [rdi], r15
0x1800047f9  lea     r8, asc_18002C608; "h"
0x180004800  shr     rbp, 1Fh
0x180004804  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004809  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000480e  test    ebp, ebp
0x180004810  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004818  lea     r9, [rsp+278h+Name]; lpName
0x18000481d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004822  cmovnz  esi, ebp
0x180004825  mov     edx, ebp; lInitialCount
0x180004827  mov     r8d, esi; lMaximumCount
0x18000482a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000482c  call    cs:__imp_CreateSemaphoreExW
0x180004832  mov     rsi, rax
0x180004835  test    rax, rax
0x180004838  jnz     short loc_18000484F
0x18000483a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000483f  mov     ebx, eax
0x180004841  test    eax, eax
0x180004843  jns     short loc_18000487F
0x180004845  mov     edx, 90h
0x18000484a  jmp     loc_1800047AE
0x18000484f  call    cs:__imp_GetLastError
0x180004855  mov     rbx, [rdi+8]
0x180004859  test    rbx, rbx
0x18000485c  jz      short loc_18000487B
0x18000485e  call    cs:__imp_GetLastError
0x180004864  mov     rcx, rbx; hObject
0x180004867  mov     ebp, eax
0x180004869  call    cs:__imp_CloseHandle
0x18000486f  test    eax, eax
0x180004871  jz      short loc_1800048AD
0x180004873  mov     ecx, ebp; dwErrCode
0x180004875  call    cs:__imp_SetLastError
0x18000487b  mov     [rdi+8], rsi
0x18000487f  xor     eax, eax
0x180004881  mov     rcx, [rsp+278h+var_38]
0x180004889  xor     rcx, rsp; StackCookie
0x18000488c  call    __security_check_cookie
0x180004891  lea     r11, [rsp+278h+var_28]
0x180004899  mov     rbx, [r11+38h]
0x18000489d  mov     rbp, [r11+40h]
0x1800048a1  mov     rsp, r11
0x1800048a4  pop     r15
0x1800048a6  pop     r14
0x1800048a8  pop     r12
0x1800048aa  pop     rdi
0x1800048ab  pop     rsi
0x1800048ac  retn
0x1800048ad  mov     rcx, [rsp+278h]; this
0x1800048b5  mov     edx, 0A0Bh; void *
0x1800048ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800048c6  mov     rcx, [rsp+278h]; this
0x1800048ce  mov     edx, 0A0Bh; void *
0x1800048d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
