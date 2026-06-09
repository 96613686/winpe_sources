# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180017eb0`
- end: `0x1800180bd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017b0c`

## callees

- `0x180001520`
- `0x18000ab78`
- `0x180017eb0`
- `0x18001843c`
- `0x180018dd4`
- `0x1800196b0`
- `0x180019a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001804d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001804d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180017f74`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018010`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180017f74`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018010`

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
0x180017eb0  mov     [rsp+arg_8], rbx
0x180017eb5  mov     [rsp+arg_10], rbp
0x180017eba  push    rsi
0x180017ebb  push    rdi
0x180017ebc  push    r12
0x180017ebe  push    r14
0x180017ec0  push    r15
0x180017ec2  sub     rsp, 250h
0x180017ec9  mov     rax, cs:__security_cookie
0x180017ed0  xor     rax, rsp
0x180017ed3  mov     [rsp+278h+var_38], rax
0x180017edb  mov     rax, 0C000000000000000h
0x180017ee5  mov     rbp, r9
0x180017ee8  mov     r8, rdx
0x180017eeb  mov     rdi, rcx
0x180017eee  test    rax, r9
0x180017ef1  jnz     loc_1800180A4
0x180017ef7  xor     r12d, r12d
0x180017efa  lea     rax, [rsp+278h+Name]
0x180017eff  mov     ecx, 7FFFFFFEh
0x180017f04  mov     edx, 104h
0x180017f09  lea     esi, [r12+1]
0x180017f0e  test    rcx, rcx
0x180017f11  jz      short loc_180017F31
0x180017f13  movzx   r9d, word ptr [r8]
0x180017f17  test    r9w, r9w
0x180017f1b  jz      short loc_180017F31
0x180017f1d  mov     [rax], r9w
0x180017f21  add     r8, 2
0x180017f25  add     rax, 2
0x180017f29  sub     rcx, rsi
0x180017f2c  sub     rdx, rsi; unsigned __int64
0x180017f2f  jnz     short loc_180017F0E
0x180017f31  test    rdx, rdx
0x180017f34  lea     rcx, [rax-2]
0x180017f38  lea     r8, aP0; "_p0"
0x180017f3f  cmovnz  rcx, rax
0x180017f43  mov     [rcx], r12w
0x180017f47  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180017f4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017f51  mov     edx, ebp
0x180017f53  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180017f5b  and     edx, 7FFFFFFFh; lInitialCount
0x180017f61  mov     [rsp+278h+dwFlags], r12d; int
0x180017f66  mov     r8d, esi
0x180017f69  lea     r9, [rsp+278h+Name]; lpName
0x180017f6e  cmova   r8d, edx; lMaximumCount
0x180017f72  xor     ecx, ecx; lpSemaphoreAttributes
0x180017f74  call    cs:__imp_CreateSemaphoreExW
0x180017f7a  mov     r15, rax
0x180017f7d  test    rax, rax
0x180017f80  jnz     short loc_180017FA9
0x180017f82  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017f87  mov     ebx, eax
0x180017f89  test    eax, eax
0x180017f8b  jns     short loc_180017FDD
0x180017f8d  mov     edx, 8Bh; void *
0x180017f92  mov     rcx, [rsp+278h]; this
0x180017f9a  mov     r9d, ebx; char *
0x180017f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fa2  mov     eax, ebx
0x180017fa4  jmp     loc_180018065
0x180017fa9  call    cs:__imp_GetLastError
0x180017faf  mov     rbx, [rdi]
0x180017fb2  test    rbx, rbx
0x180017fb5  jz      short loc_180017FDA
0x180017fb7  call    cs:__imp_GetLastError
0x180017fbd  mov     rcx, rbx; hObject
0x180017fc0  mov     r14d, eax
0x180017fc3  call    cs:__imp_CloseHandle
0x180017fc9  test    eax, eax
0x180017fcb  jz      loc_1800180AA
0x180017fd1  mov     ecx, r14d; dwErrCode
0x180017fd4  call    cs:__imp_SetLastError
0x180017fda  mov     [rdi], r15
0x180017fdd  lea     r8, asc_180029D30; "h"
0x180017fe4  shr     rbp, 1Fh
0x180017fe8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180017fed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017ff2  test    ebp, ebp
0x180017ff4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180017ffc  lea     r9, [rsp+278h+Name]; lpName
0x180018001  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180018006  cmovnz  esi, ebp
0x180018009  mov     edx, ebp; lInitialCount
0x18001800b  mov     r8d, esi; lMaximumCount
0x18001800e  xor     ecx, ecx; lpSemaphoreAttributes
0x180018010  call    cs:__imp_CreateSemaphoreExW
0x180018016  mov     rsi, rax
0x180018019  test    rax, rax
0x18001801c  jnz     short loc_180018033
0x18001801e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018023  mov     ebx, eax
0x180018025  test    eax, eax
0x180018027  jns     short loc_180018063
0x180018029  mov     edx, 90h
0x18001802e  jmp     loc_180017F92
0x180018033  call    cs:__imp_GetLastError
0x180018039  mov     rbx, [rdi+8]
0x18001803d  test    rbx, rbx
0x180018040  jz      short loc_18001805F
0x180018042  call    cs:__imp_GetLastError
0x180018048  mov     rcx, rbx; hObject
0x18001804b  mov     ebp, eax
0x18001804d  call    cs:__imp_CloseHandle
0x180018053  test    eax, eax
0x180018055  jz      short loc_180018091
0x180018057  mov     ecx, ebp; dwErrCode
0x180018059  call    cs:__imp_SetLastError
0x18001805f  mov     [rdi+8], rsi
0x180018063  xor     eax, eax
0x180018065  mov     rcx, [rsp+278h+var_38]
0x18001806d  xor     rcx, rsp; StackCookie
0x180018070  call    __security_check_cookie
0x180018075  lea     r11, [rsp+278h+var_28]
0x18001807d  mov     rbx, [r11+38h]
0x180018081  mov     rbp, [r11+40h]
0x180018085  mov     rsp, r11
0x180018088  pop     r15
0x18001808a  pop     r14
0x18001808c  pop     r12
0x18001808e  pop     rdi
0x18001808f  pop     rsi
0x180018090  retn
0x180018091  mov     rcx, [rsp+278h]; this
0x180018099  mov     edx, 0A0Bh; void *
0x18001809e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800180a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800180aa  mov     rcx, [rsp+278h]; this
0x1800180b2  mov     edx, 0A0Bh; void *
0x1800180b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
