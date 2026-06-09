# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003470`
- end: `0x18000369a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800030a0`
- `0x180009ed8`

## callees

- `0x180003470`
- `0x180003cf8`
- `0x180004a34`
- `0x1800051b4`
- `0x1800057d4`
- `0x1800057e4`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003534`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035d7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003534`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000359b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003636`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000359b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000361f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000358a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000362a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000358a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000362a`

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
0x180003470  mov     [rsp+arg_8], rbx
0x180003475  mov     [rsp+arg_10], rbp
0x18000347a  push    rsi
0x18000347b  push    rdi
0x18000347c  push    r12
0x18000347e  push    r14
0x180003480  push    r15
0x180003482  sub     rsp, 250h
0x180003489  mov     rax, cs:__security_cookie
0x180003490  xor     rax, rsp
0x180003493  mov     [rsp+278h+var_38], rax
0x18000349b  mov     rax, 0C000000000000000h
0x1800034a5  mov     rbp, r9
0x1800034a8  mov     r8, rdx
0x1800034ab  mov     rbx, rcx
0x1800034ae  test    rax, r9
0x1800034b1  jnz     loc_180003681
0x1800034b7  xor     r12d, r12d
0x1800034ba  lea     rax, [rsp+278h+Name]
0x1800034bf  mov     ecx, 7FFFFFFEh
0x1800034c4  mov     edx, 104h
0x1800034c9  lea     esi, [r12+1]
0x1800034ce  test    rcx, rcx
0x1800034d1  jz      short loc_1800034F1
0x1800034d3  movzx   r9d, word ptr [r8]
0x1800034d7  test    r9w, r9w
0x1800034db  jz      short loc_1800034F1
0x1800034dd  mov     [rax], r9w
0x1800034e1  add     r8, 2
0x1800034e5  add     rax, 2
0x1800034e9  sub     rcx, rsi
0x1800034ec  sub     rdx, rsi; unsigned __int64
0x1800034ef  jnz     short loc_1800034CE
0x1800034f1  test    rdx, rdx
0x1800034f4  lea     rcx, [rax-2]
0x1800034f8  lea     r8, aP0; "_p0"
0x1800034ff  cmovnz  rcx, rax
0x180003503  mov     [rcx], r12w
0x180003507  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000350c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003511  mov     edx, ebp
0x180003513  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000351b  and     edx, 7FFFFFFFh; lInitialCount
0x180003521  mov     [rsp+278h+dwFlags], r12d; int
0x180003526  mov     r8d, esi
0x180003529  lea     r9, [rsp+278h+Name]; lpName
0x18000352e  cmova   r8d, edx; lMaximumCount
0x180003532  xor     ecx, ecx; lpSemaphoreAttributes
0x180003534  call    cs:__imp_CreateSemaphoreExW
0x18000353a  mov     r15, rax
0x18000353d  test    rax, rax
0x180003540  jnz     short loc_180003570
0x180003542  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003547  mov     edi, eax
0x180003549  test    eax, eax
0x18000354b  jns     short loc_1800035A4
0x18000354d  mov     rcx, [rsp+278h]; this
0x180003555  lea     r8, aWil; "wil"
0x18000355c  mov     r9d, eax; char *
0x18000355f  mov     edx, 8Bh; void *
0x180003564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003569  mov     eax, edi
0x18000356b  jmp     loc_180003642
0x180003570  call    cs:__imp_GetLastError
0x180003576  mov     rdi, [rbx]
0x180003579  test    rdi, rdi
0x18000357c  jz      short loc_1800035A1
0x18000357e  call    cs:__imp_GetLastError
0x180003584  mov     rcx, rdi; hObject
0x180003587  mov     r14d, eax
0x18000358a  call    cs:__imp_CloseHandle
0x180003590  test    eax, eax
0x180003592  jz      loc_180003687
0x180003598  mov     ecx, r14d; dwErrCode
0x18000359b  call    cs:__imp_SetLastError
0x1800035a1  mov     [rbx], r15
0x1800035a4  lea     r8, asc_18001B8B0; "h"
0x1800035ab  shr     rbp, 1Fh
0x1800035af  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800035b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800035b9  test    ebp, ebp
0x1800035bb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800035c3  lea     r9, [rsp+278h+Name]; lpName
0x1800035c8  mov     [rsp+278h+dwFlags], r12d; int
0x1800035cd  cmovnz  esi, ebp
0x1800035d0  mov     edx, ebp; lInitialCount
0x1800035d2  mov     r8d, esi; lMaximumCount
0x1800035d5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035d7  call    cs:__imp_CreateSemaphoreExW
0x1800035dd  mov     rsi, rax
0x1800035e0  test    rax, rax
0x1800035e3  jnz     short loc_180003610
0x1800035e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035ea  mov     ebx, eax
0x1800035ec  test    eax, eax
0x1800035ee  jns     short loc_180003640
0x1800035f0  mov     rcx, [rsp+278h]; this
0x1800035f8  lea     r8, aWil; "wil"
0x1800035ff  mov     r9d, eax; char *
0x180003602  mov     edx, 90h; void *
0x180003607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000360c  mov     eax, ebx
0x18000360e  jmp     short loc_180003642
0x180003610  call    cs:__imp_GetLastError
0x180003616  mov     rdi, [rbx+8]
0x18000361a  test    rdi, rdi
0x18000361d  jz      short loc_18000363C
0x18000361f  call    cs:__imp_GetLastError
0x180003625  mov     rcx, rdi; hObject
0x180003628  mov     ebp, eax
0x18000362a  call    cs:__imp_CloseHandle
0x180003630  test    eax, eax
0x180003632  jz      short loc_18000366E
0x180003634  mov     ecx, ebp; dwErrCode
0x180003636  call    cs:__imp_SetLastError
0x18000363c  mov     [rbx+8], rsi
0x180003640  xor     eax, eax
0x180003642  mov     rcx, [rsp+278h+var_38]
0x18000364a  xor     rcx, rsp; StackCookie
0x18000364d  call    __security_check_cookie
0x180003652  lea     r11, [rsp+278h+var_28]
0x18000365a  mov     rbx, [r11+38h]
0x18000365e  mov     rbp, [r11+40h]
0x180003662  mov     rsp, r11
0x180003665  pop     r15
0x180003667  pop     r14
0x180003669  pop     r12
0x18000366b  pop     rdi
0x18000366c  pop     rsi
0x18000366d  retn
0x18000366e  mov     rcx, [rsp+278h]; this
0x180003676  mov     edx, 0A0Bh; void *
0x18000367b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003681  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003687  mov     rcx, [rsp+278h]; this
0x18000368f  mov     edx, 0A0Bh; void *
0x180003694  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
