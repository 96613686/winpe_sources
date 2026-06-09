# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003518`
- end: `0x180003725`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003168`
- `0x180007824`

## callees

- `0x180001610`
- `0x180003518`
- `0x180003e28`
- `0x180004cf4`
- `0x180005634`
- `0x180005b4c`
- `0x180005b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003678`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800035dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000369b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000361f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000369b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000363c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000363c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000362b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000362b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036b5`

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
0x180003518  mov     [rsp+arg_8], rbx
0x18000351d  mov     [rsp+arg_10], rbp
0x180003522  push    rsi
0x180003523  push    rdi
0x180003524  push    r12
0x180003526  push    r14
0x180003528  push    r15
0x18000352a  sub     rsp, 250h
0x180003531  mov     rax, cs:__security_cookie
0x180003538  xor     rax, rsp
0x18000353b  mov     [rsp+278h+var_38], rax
0x180003543  mov     rax, 0C000000000000000h
0x18000354d  mov     rbp, r9
0x180003550  mov     r8, rdx
0x180003553  mov     rdi, rcx
0x180003556  test    rax, r9
0x180003559  jnz     loc_18000370C
0x18000355f  xor     r12d, r12d
0x180003562  lea     rax, [rsp+278h+Name]
0x180003567  mov     ecx, 7FFFFFFEh
0x18000356c  mov     edx, 104h
0x180003571  lea     esi, [r12+1]
0x180003576  test    rcx, rcx
0x180003579  jz      short loc_180003599
0x18000357b  movzx   r9d, word ptr [r8]
0x18000357f  test    r9w, r9w
0x180003583  jz      short loc_180003599
0x180003585  mov     [rax], r9w
0x180003589  add     r8, 2
0x18000358d  add     rax, 2
0x180003591  sub     rcx, rsi
0x180003594  sub     rdx, rsi; unsigned __int64
0x180003597  jnz     short loc_180003576
0x180003599  test    rdx, rdx
0x18000359c  lea     rcx, [rax-2]
0x1800035a0  lea     r8, aP0; "_p0"
0x1800035a7  cmovnz  rcx, rax
0x1800035ab  mov     [rcx], r12w
0x1800035af  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800035b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800035b9  mov     edx, ebp
0x1800035bb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800035c3  and     edx, 7FFFFFFFh; lInitialCount
0x1800035c9  mov     [rsp+278h+dwFlags], r12d; int
0x1800035ce  mov     r8d, esi
0x1800035d1  lea     r9, [rsp+278h+Name]; lpName
0x1800035d6  cmova   r8d, edx; lMaximumCount
0x1800035da  xor     ecx, ecx; lpSemaphoreAttributes
0x1800035dc  call    cs:__imp_CreateSemaphoreExW
0x1800035e2  mov     r15, rax
0x1800035e5  test    rax, rax
0x1800035e8  jnz     short loc_180003611
0x1800035ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035ef  mov     ebx, eax
0x1800035f1  test    eax, eax
0x1800035f3  jns     short loc_180003645
0x1800035f5  mov     edx, 8Bh; void *
0x1800035fa  mov     rcx, [rsp+278h]; this
0x180003602  mov     r9d, ebx; char *
0x180003605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000360a  mov     eax, ebx
0x18000360c  jmp     loc_1800036CD
0x180003611  call    cs:__imp_GetLastError
0x180003617  mov     rbx, [rdi]
0x18000361a  test    rbx, rbx
0x18000361d  jz      short loc_180003642
0x18000361f  call    cs:__imp_GetLastError
0x180003625  mov     rcx, rbx; hObject
0x180003628  mov     r14d, eax
0x18000362b  call    cs:__imp_CloseHandle
0x180003631  test    eax, eax
0x180003633  jz      loc_180003712
0x180003639  mov     ecx, r14d; dwErrCode
0x18000363c  call    cs:__imp_SetLastError
0x180003642  mov     [rdi], r15
0x180003645  lea     r8, asc_18000CC38; "h"
0x18000364c  shr     rbp, 1Fh
0x180003650  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003655  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000365a  test    ebp, ebp
0x18000365c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003664  lea     r9, [rsp+278h+Name]; lpName
0x180003669  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000366e  cmovnz  esi, ebp
0x180003671  mov     edx, ebp; lInitialCount
0x180003673  mov     r8d, esi; lMaximumCount
0x180003676  xor     ecx, ecx; lpSemaphoreAttributes
0x180003678  call    cs:__imp_CreateSemaphoreExW
0x18000367e  mov     rsi, rax
0x180003681  test    rax, rax
0x180003684  jnz     short loc_18000369B
0x180003686  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000368b  mov     ebx, eax
0x18000368d  test    eax, eax
0x18000368f  jns     short loc_1800036CB
0x180003691  mov     edx, 90h
0x180003696  jmp     loc_1800035FA
0x18000369b  call    cs:__imp_GetLastError
0x1800036a1  mov     rbx, [rdi+8]
0x1800036a5  test    rbx, rbx
0x1800036a8  jz      short loc_1800036C7
0x1800036aa  call    cs:__imp_GetLastError
0x1800036b0  mov     rcx, rbx; hObject
0x1800036b3  mov     ebp, eax
0x1800036b5  call    cs:__imp_CloseHandle
0x1800036bb  test    eax, eax
0x1800036bd  jz      short loc_1800036F9
0x1800036bf  mov     ecx, ebp; dwErrCode
0x1800036c1  call    cs:__imp_SetLastError
0x1800036c7  mov     [rdi+8], rsi
0x1800036cb  xor     eax, eax
0x1800036cd  mov     rcx, [rsp+278h+var_38]
0x1800036d5  xor     rcx, rsp; StackCookie
0x1800036d8  call    __security_check_cookie
0x1800036dd  lea     r11, [rsp+278h+var_28]
0x1800036e5  mov     rbx, [r11+38h]
0x1800036e9  mov     rbp, [r11+40h]
0x1800036ed  mov     rsp, r11
0x1800036f0  pop     r15
0x1800036f2  pop     r14
0x1800036f4  pop     r12
0x1800036f6  pop     rdi
0x1800036f7  pop     rsi
0x1800036f8  retn
0x1800036f9  mov     rcx, [rsp+278h]; this
0x180003701  mov     edx, 0A0Bh; void *
0x180003706  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000370c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003712  mov     rcx, [rsp+278h]; this
0x18000371a  mov     edx, 0A0Bh; void *
0x18000371f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
