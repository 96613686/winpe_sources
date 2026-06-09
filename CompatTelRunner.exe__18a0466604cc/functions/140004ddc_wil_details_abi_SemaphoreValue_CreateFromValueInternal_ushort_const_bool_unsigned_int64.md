# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004ddc`
- end: `0x140004fe9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004668`
- `0x140004a0c`

## callees

- `0x140001ba0`
- `0x140004ddc`
- `0x1400061a8`
- `0x1400088f4`
- `0x140009338`
- `0x14000a11c`
- `0x14000a12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004ea0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004f3c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004ea0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004f3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004eef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004eef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f79`

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
0x140004ddc  mov     [rsp+arg_8], rbx
0x140004de1  mov     [rsp+arg_10], rbp
0x140004de6  push    rsi
0x140004de7  push    rdi
0x140004de8  push    r12
0x140004dea  push    r14
0x140004dec  push    r15
0x140004dee  sub     rsp, 250h
0x140004df5  mov     rax, cs:__security_cookie
0x140004dfc  xor     rax, rsp
0x140004dff  mov     [rsp+278h+var_38], rax
0x140004e07  mov     rax, 0C000000000000000h
0x140004e11  mov     rbp, r9
0x140004e14  mov     r8, rdx
0x140004e17  mov     rdi, rcx
0x140004e1a  test    rax, r9
0x140004e1d  jnz     loc_140004FD0
0x140004e23  xor     r12d, r12d
0x140004e26  lea     rax, [rsp+278h+Name]
0x140004e2b  mov     ecx, 7FFFFFFEh
0x140004e30  mov     edx, 104h
0x140004e35  lea     esi, [r12+1]
0x140004e3a  test    rcx, rcx
0x140004e3d  jz      short loc_140004E5D
0x140004e3f  movzx   r9d, word ptr [r8]
0x140004e43  test    r9w, r9w
0x140004e47  jz      short loc_140004E5D
0x140004e49  mov     [rax], r9w
0x140004e4d  add     r8, 2
0x140004e51  add     rax, 2
0x140004e55  sub     rcx, rsi
0x140004e58  sub     rdx, rsi; unsigned __int64
0x140004e5b  jnz     short loc_140004E3A
0x140004e5d  test    rdx, rdx
0x140004e60  lea     rcx, [rax-2]
0x140004e64  lea     r8, aP0; "_p0"
0x140004e6b  cmovnz  rcx, rax
0x140004e6f  mov     [rcx], r12w
0x140004e73  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004e78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004e7d  mov     edx, ebp
0x140004e7f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004e87  and     edx, 7FFFFFFFh; lInitialCount
0x140004e8d  mov     [rsp+278h+dwFlags], r12d; int
0x140004e92  mov     r8d, esi
0x140004e95  lea     r9, [rsp+278h+Name]; lpName
0x140004e9a  cmova   r8d, edx; lMaximumCount
0x140004e9e  xor     ecx, ecx; lpSemaphoreAttributes
0x140004ea0  call    cs:__imp_CreateSemaphoreExW
0x140004ea6  mov     r15, rax
0x140004ea9  test    rax, rax
0x140004eac  jnz     short loc_140004ED5
0x140004eae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004eb3  mov     ebx, eax
0x140004eb5  test    eax, eax
0x140004eb7  jns     short loc_140004F09
0x140004eb9  mov     edx, 8Bh; void *
0x140004ebe  mov     rcx, [rsp+278h]; this
0x140004ec6  mov     r9d, ebx; char *
0x140004ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ece  mov     eax, ebx
0x140004ed0  jmp     loc_140004F91
0x140004ed5  call    cs:__imp_GetLastError
0x140004edb  mov     rbx, [rdi]
0x140004ede  test    rbx, rbx
0x140004ee1  jz      short loc_140004F06
0x140004ee3  call    cs:__imp_GetLastError
0x140004ee9  mov     rcx, rbx; hObject
0x140004eec  mov     r14d, eax
0x140004eef  call    cs:__imp_CloseHandle
0x140004ef5  test    eax, eax
0x140004ef7  jz      loc_140004FD6
0x140004efd  mov     ecx, r14d; dwErrCode
0x140004f00  call    cs:__imp_SetLastError
0x140004f06  mov     [rdi], r15
0x140004f09  lea     r8, asc_1400AD188; "h"
0x140004f10  shr     rbp, 1Fh
0x140004f14  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004f19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f1e  test    ebp, ebp
0x140004f20  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004f28  lea     r9, [rsp+278h+Name]; lpName
0x140004f2d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004f32  cmovnz  esi, ebp
0x140004f35  mov     edx, ebp; lInitialCount
0x140004f37  mov     r8d, esi; lMaximumCount
0x140004f3a  xor     ecx, ecx; lpSemaphoreAttributes
0x140004f3c  call    cs:__imp_CreateSemaphoreExW
0x140004f42  mov     rsi, rax
0x140004f45  test    rax, rax
0x140004f48  jnz     short loc_140004F5F
0x140004f4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004f4f  mov     ebx, eax
0x140004f51  test    eax, eax
0x140004f53  jns     short loc_140004F8F
0x140004f55  mov     edx, 90h
0x140004f5a  jmp     loc_140004EBE
0x140004f5f  call    cs:__imp_GetLastError
0x140004f65  mov     rbx, [rdi+8]
0x140004f69  test    rbx, rbx
0x140004f6c  jz      short loc_140004F8B
0x140004f6e  call    cs:__imp_GetLastError
0x140004f74  mov     rcx, rbx; hObject
0x140004f77  mov     ebp, eax
0x140004f79  call    cs:__imp_CloseHandle
0x140004f7f  test    eax, eax
0x140004f81  jz      short loc_140004FBD
0x140004f83  mov     ecx, ebp; dwErrCode
0x140004f85  call    cs:__imp_SetLastError
0x140004f8b  mov     [rdi+8], rsi
0x140004f8f  xor     eax, eax
0x140004f91  mov     rcx, [rsp+278h+var_38]
0x140004f99  xor     rcx, rsp; StackCookie
0x140004f9c  call    __security_check_cookie
0x140004fa1  lea     r11, [rsp+278h+var_28]
0x140004fa9  mov     rbx, [r11+38h]
0x140004fad  mov     rbp, [r11+40h]
0x140004fb1  mov     rsp, r11
0x140004fb4  pop     r15
0x140004fb6  pop     r14
0x140004fb8  pop     r12
0x140004fba  pop     rdi
0x140004fbb  pop     rsi
0x140004fbc  retn
0x140004fbd  mov     rcx, [rsp+278h]; this
0x140004fc5  mov     edx, 0A0Bh; void *
0x140004fca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004fd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004fd6  mov     rcx, [rsp+278h]; this
0x140004fde  mov     edx, 0A0Bh; void *
0x140004fe3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
