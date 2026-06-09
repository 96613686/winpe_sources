# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800b0594`
- end: `0x1800b07a1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800aed6c`
- `0x1800af110`

## callees

- `0x1800b0594`
- `0x1800b2028`
- `0x1800b6e74`
- `0x1800b72f8`
- `0x1800b7fac`
- `0x1800b7fbc`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b06a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b06a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b06b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b073d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b06b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b073d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b068d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b069b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b068d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b069b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0726`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800b0658`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800b06f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800b0658`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800b06f4`

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
0x1800b0594  mov     [rsp+arg_8], rbx
0x1800b0599  mov     [rsp+arg_10], rbp
0x1800b059e  push    rsi
0x1800b059f  push    rdi
0x1800b05a0  push    r12
0x1800b05a2  push    r14
0x1800b05a4  push    r15
0x1800b05a6  sub     rsp, 250h
0x1800b05ad  mov     rax, cs:__security_cookie
0x1800b05b4  xor     rax, rsp
0x1800b05b7  mov     [rsp+278h+var_38], rax
0x1800b05bf  mov     rax, 0C000000000000000h
0x1800b05c9  mov     rbp, r9
0x1800b05cc  mov     r8, rdx
0x1800b05cf  mov     rdi, rcx
0x1800b05d2  test    rax, r9
0x1800b05d5  jnz     loc_1800B0788
0x1800b05db  xor     r12d, r12d
0x1800b05de  lea     rax, [rsp+278h+Name]
0x1800b05e3  mov     ecx, 7FFFFFFEh
0x1800b05e8  mov     edx, 104h
0x1800b05ed  lea     esi, [r12+1]
0x1800b05f2  test    rcx, rcx
0x1800b05f5  jz      short loc_1800B0615
0x1800b05f7  movzx   r9d, word ptr [r8]
0x1800b05fb  test    r9w, r9w
0x1800b05ff  jz      short loc_1800B0615
0x1800b0601  mov     [rax], r9w
0x1800b0605  add     r8, 2
0x1800b0609  add     rax, 2
0x1800b060d  sub     rcx, rsi
0x1800b0610  sub     rdx, rsi; unsigned __int64
0x1800b0613  jnz     short loc_1800B05F2
0x1800b0615  test    rdx, rdx
0x1800b0618  lea     rcx, [rax-2]
0x1800b061c  lea     r8, aP0; "_p0"
0x1800b0623  cmovnz  rcx, rax
0x1800b0627  mov     [rcx], r12w
0x1800b062b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800b0630  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b0635  mov     edx, ebp
0x1800b0637  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800b063f  and     edx, 7FFFFFFFh; lInitialCount
0x1800b0645  mov     [rsp+278h+dwFlags], r12d; int
0x1800b064a  mov     r8d, esi
0x1800b064d  lea     r9, [rsp+278h+Name]; lpName
0x1800b0652  cmova   r8d, edx; lMaximumCount
0x1800b0656  xor     ecx, ecx; lpSemaphoreAttributes
0x1800b0658  call    cs:__imp_CreateSemaphoreExW
0x1800b065e  mov     r15, rax
0x1800b0661  test    rax, rax
0x1800b0664  jnz     short loc_1800B068D
0x1800b0666  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800b066b  mov     ebx, eax
0x1800b066d  test    eax, eax
0x1800b066f  jns     short loc_1800B06C1
0x1800b0671  mov     edx, 8Bh; void *
0x1800b0676  mov     rcx, [rsp+278h]; this
0x1800b067e  mov     r9d, ebx; char *
0x1800b0681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0686  mov     eax, ebx
0x1800b0688  jmp     loc_1800B0749
0x1800b068d  call    cs:__imp_GetLastError
0x1800b0693  mov     rbx, [rdi]
0x1800b0696  test    rbx, rbx
0x1800b0699  jz      short loc_1800B06BE
0x1800b069b  call    cs:__imp_GetLastError
0x1800b06a1  mov     rcx, rbx; hObject
0x1800b06a4  mov     r14d, eax
0x1800b06a7  call    cs:__imp_CloseHandle
0x1800b06ad  test    eax, eax
0x1800b06af  jz      loc_1800B078E
0x1800b06b5  mov     ecx, r14d; dwErrCode
0x1800b06b8  call    cs:__imp_SetLastError
0x1800b06be  mov     [rdi], r15
0x1800b06c1  lea     r8, asc_1800FA9B4; "h"
0x1800b06c8  shr     rbp, 1Fh
0x1800b06cc  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800b06d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b06d6  test    ebp, ebp
0x1800b06d8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800b06e0  lea     r9, [rsp+278h+Name]; lpName
0x1800b06e5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1800b06ea  cmovnz  esi, ebp
0x1800b06ed  mov     edx, ebp; lInitialCount
0x1800b06ef  mov     r8d, esi; lMaximumCount
0x1800b06f2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800b06f4  call    cs:__imp_CreateSemaphoreExW
0x1800b06fa  mov     rsi, rax
0x1800b06fd  test    rax, rax
0x1800b0700  jnz     short loc_1800B0717
0x1800b0702  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800b0707  mov     ebx, eax
0x1800b0709  test    eax, eax
0x1800b070b  jns     short loc_1800B0747
0x1800b070d  mov     edx, 90h
0x1800b0712  jmp     loc_1800B0676
0x1800b0717  call    cs:__imp_GetLastError
0x1800b071d  mov     rbx, [rdi+8]
0x1800b0721  test    rbx, rbx
0x1800b0724  jz      short loc_1800B0743
0x1800b0726  call    cs:__imp_GetLastError
0x1800b072c  mov     rcx, rbx; hObject
0x1800b072f  mov     ebp, eax
0x1800b0731  call    cs:__imp_CloseHandle
0x1800b0737  test    eax, eax
0x1800b0739  jz      short loc_1800B0775
0x1800b073b  mov     ecx, ebp; dwErrCode
0x1800b073d  call    cs:__imp_SetLastError
0x1800b0743  mov     [rdi+8], rsi
0x1800b0747  xor     eax, eax
0x1800b0749  mov     rcx, [rsp+278h+var_38]
0x1800b0751  xor     rcx, rsp; StackCookie
0x1800b0754  call    __security_check_cookie
0x1800b0759  lea     r11, [rsp+278h+var_28]
0x1800b0761  mov     rbx, [r11+38h]
0x1800b0765  mov     rbp, [r11+40h]
0x1800b0769  mov     rsp, r11
0x1800b076c  pop     r15
0x1800b076e  pop     r14
0x1800b0770  pop     r12
0x1800b0772  pop     rdi
0x1800b0773  pop     rsi
0x1800b0774  retn
0x1800b0775  mov     rcx, [rsp+278h]; this
0x1800b077d  mov     edx, 0A0Bh; void *
0x1800b0782  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b0788  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b078e  mov     rcx, [rsp+278h]; this
0x1800b0796  mov     edx, 0A0Bh; void *
0x1800b079b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
