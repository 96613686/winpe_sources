# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140009764`
- end: `0x14000998e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008f9c`
- `0x14000936c`

## callees

- `0x1400023d0`
- `0x140006008`
- `0x140009764`
- `0x14000a628`
- `0x14000c188`
- `0x14000c4d0`
- `0x14000db34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000988f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000992a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000988f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000992a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000987e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000991e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000987e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000991e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009828`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400098cb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009828`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400098cb`

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
    wil::details::in1diag4::_FailFastImmediate_Unexpected(this);
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
0x140009764  mov     [rsp+arg_8], rbx
0x140009769  mov     [rsp+arg_10], rbp
0x14000976e  push    rsi
0x14000976f  push    rdi
0x140009770  push    r12
0x140009772  push    r14
0x140009774  push    r15
0x140009776  sub     rsp, 250h
0x14000977d  mov     rax, cs:__security_cookie
0x140009784  xor     rax, rsp
0x140009787  mov     [rsp+278h+var_38], rax
0x14000978f  mov     rax, 0C000000000000000h
0x140009799  mov     rbp, r9
0x14000979c  mov     r8, rdx
0x14000979f  mov     rbx, rcx
0x1400097a2  test    rax, r9
0x1400097a5  jnz     loc_140009975
0x1400097ab  xor     r12d, r12d
0x1400097ae  lea     rax, [rsp+278h+Name]
0x1400097b3  mov     ecx, 7FFFFFFEh
0x1400097b8  mov     edx, 104h
0x1400097bd  lea     esi, [r12+1]
0x1400097c2  test    rcx, rcx
0x1400097c5  jz      short loc_1400097E5
0x1400097c7  movzx   r9d, word ptr [r8]
0x1400097cb  test    r9w, r9w
0x1400097cf  jz      short loc_1400097E5
0x1400097d1  mov     [rax], r9w
0x1400097d5  add     r8, 2
0x1400097d9  add     rax, 2
0x1400097dd  sub     rcx, rsi
0x1400097e0  sub     rdx, rsi; unsigned __int64
0x1400097e3  jnz     short loc_1400097C2
0x1400097e5  test    rdx, rdx
0x1400097e8  lea     rcx, [rax-2]
0x1400097ec  lea     r8, aP0; "_p0"
0x1400097f3  cmovnz  rcx, rax
0x1400097f7  mov     [rcx], r12w
0x1400097fb  lea     rcx, [rsp+278h+Name]; wchar_t *
0x140009800  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140009805  mov     edx, ebp
0x140009807  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000980f  and     edx, 7FFFFFFFh; lInitialCount
0x140009815  mov     [rsp+278h+dwFlags], r12d; int
0x14000981a  mov     r8d, esi
0x14000981d  lea     r9, [rsp+278h+Name]; lpName
0x140009822  cmova   r8d, edx; lMaximumCount
0x140009826  xor     ecx, ecx; lpSemaphoreAttributes
0x140009828  call    cs:__imp_CreateSemaphoreExW
0x14000982e  mov     r15, rax
0x140009831  test    rax, rax
0x140009834  jnz     short loc_140009864
0x140009836  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000983b  mov     edi, eax
0x14000983d  test    eax, eax
0x14000983f  jns     short loc_140009898
0x140009841  mov     rcx, [rsp+278h]; this
0x140009849  lea     r8, aWil; "wil"
0x140009850  mov     r9d, eax; char *
0x140009853  mov     edx, 8Bh; void *
0x140009858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000985d  mov     eax, edi
0x14000985f  jmp     loc_140009936
0x140009864  call    cs:__imp_GetLastError
0x14000986a  mov     rdi, [rbx]
0x14000986d  test    rdi, rdi
0x140009870  jz      short loc_140009895
0x140009872  call    cs:__imp_GetLastError
0x140009878  mov     rcx, rdi; hObject
0x14000987b  mov     r14d, eax
0x14000987e  call    cs:__imp_CloseHandle
0x140009884  test    eax, eax
0x140009886  jz      loc_14000997B
0x14000988c  mov     ecx, r14d; dwErrCode
0x14000988f  call    cs:__imp_SetLastError
0x140009895  mov     [rbx], r15
0x140009898  lea     r8, asc_140014C78; "h"
0x14000989f  shr     rbp, 1Fh
0x1400098a3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1400098a8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400098ad  test    ebp, ebp
0x1400098af  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400098b7  lea     r9, [rsp+278h+Name]; lpName
0x1400098bc  mov     [rsp+278h+dwFlags], r12d; int
0x1400098c1  cmovnz  esi, ebp
0x1400098c4  mov     edx, ebp; lInitialCount
0x1400098c6  mov     r8d, esi; lMaximumCount
0x1400098c9  xor     ecx, ecx; lpSemaphoreAttributes
0x1400098cb  call    cs:__imp_CreateSemaphoreExW
0x1400098d1  mov     rsi, rax
0x1400098d4  test    rax, rax
0x1400098d7  jnz     short loc_140009904
0x1400098d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400098de  mov     ebx, eax
0x1400098e0  test    eax, eax
0x1400098e2  jns     short loc_140009934
0x1400098e4  mov     rcx, [rsp+278h]; this
0x1400098ec  lea     r8, aWil; "wil"
0x1400098f3  mov     r9d, eax; char *
0x1400098f6  mov     edx, 90h; void *
0x1400098fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009900  mov     eax, ebx
0x140009902  jmp     short loc_140009936
0x140009904  call    cs:__imp_GetLastError
0x14000990a  mov     rdi, [rbx+8]
0x14000990e  test    rdi, rdi
0x140009911  jz      short loc_140009930
0x140009913  call    cs:__imp_GetLastError
0x140009919  mov     rcx, rdi; hObject
0x14000991c  mov     ebp, eax
0x14000991e  call    cs:__imp_CloseHandle
0x140009924  test    eax, eax
0x140009926  jz      short loc_140009962
0x140009928  mov     ecx, ebp; dwErrCode
0x14000992a  call    cs:__imp_SetLastError
0x140009930  mov     [rbx+8], rsi
0x140009934  xor     eax, eax
0x140009936  mov     rcx, [rsp+278h+var_38]
0x14000993e  xor     rcx, rsp; StackCookie
0x140009941  call    __security_check_cookie
0x140009946  lea     r11, [rsp+278h+var_28]
0x14000994e  mov     rbx, [r11+38h]
0x140009952  mov     rbp, [r11+40h]
0x140009956  mov     rsp, r11
0x140009959  pop     r15
0x14000995b  pop     r14
0x14000995d  pop     r12
0x14000995f  pop     rdi
0x140009960  pop     rsi
0x140009961  retn
0x140009962  mov     rcx, [rsp+278h]; this
0x14000996a  mov     edx, 0A0Bh; void *
0x14000996f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009975  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x14000997b  mov     rcx, [rsp+278h]; this
0x140009983  mov     edx, 0A0Bh; void *
0x140009988  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
