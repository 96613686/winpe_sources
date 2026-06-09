# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004974`
- end: `0x140004b9e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400040c8`
- `0x140004498`

## callees

- `0x140004974`
- `0x140006190`
- `0x140009384`
- `0x1400099f8`
- `0x14000a764`
- `0x14000a774`
- `0x140015b00`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140004a38`
- `KERNEL32!CreateSemaphoreExW` at `0x140004adb`
- `KERNEL32!CreateSemaphoreExW` at `0x140004a38`
- `KERNEL32!CreateSemaphoreExW` at `0x140004adb`
- `KERNEL32!SetLastError` at `0x140004a9f`
- `KERNEL32!SetLastError` at `0x140004b3a`
- `KERNEL32!SetLastError` at `0x140004a9f`
- `KERNEL32!SetLastError` at `0x140004b3a`
- `KERNEL32!GetLastError` at `0x140004a74`
- `KERNEL32!GetLastError` at `0x140004a82`
- `KERNEL32!GetLastError` at `0x140004b14`
- `KERNEL32!GetLastError` at `0x140004b23`
- `KERNEL32!GetLastError` at `0x140004a74`
- `KERNEL32!GetLastError` at `0x140004a82`
- `KERNEL32!GetLastError` at `0x140004b14`
- `KERNEL32!GetLastError` at `0x140004b23`
- `KERNEL32!CloseHandle` at `0x140004a8e`
- `KERNEL32!CloseHandle` at `0x140004b2e`
- `KERNEL32!CloseHandle` at `0x140004a8e`
- `KERNEL32!CloseHandle` at `0x140004b2e`

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
0x140004974  mov     [rsp+arg_8], rbx
0x140004979  mov     [rsp+arg_10], rbp
0x14000497e  push    rsi
0x14000497f  push    rdi
0x140004980  push    r12
0x140004982  push    r14
0x140004984  push    r15
0x140004986  sub     rsp, 250h
0x14000498d  mov     rax, cs:__security_cookie
0x140004994  xor     rax, rsp
0x140004997  mov     [rsp+278h+var_38], rax
0x14000499f  mov     rax, 0C000000000000000h
0x1400049a9  mov     rbp, r9
0x1400049ac  mov     r8, rdx
0x1400049af  mov     rbx, rcx
0x1400049b2  test    rax, r9
0x1400049b5  jnz     loc_140004B85
0x1400049bb  xor     r12d, r12d
0x1400049be  lea     rax, [rsp+278h+Name]
0x1400049c3  mov     ecx, 7FFFFFFEh
0x1400049c8  mov     edx, 104h
0x1400049cd  lea     esi, [r12+1]
0x1400049d2  test    rcx, rcx
0x1400049d5  jz      short loc_1400049F5
0x1400049d7  movzx   r9d, word ptr [r8]
0x1400049db  test    r9w, r9w
0x1400049df  jz      short loc_1400049F5
0x1400049e1  mov     [rax], r9w
0x1400049e5  add     r8, 2
0x1400049e9  add     rax, 2
0x1400049ed  sub     rcx, rsi
0x1400049f0  sub     rdx, rsi; unsigned __int64
0x1400049f3  jnz     short loc_1400049D2
0x1400049f5  test    rdx, rdx
0x1400049f8  lea     rcx, [rax-2]
0x1400049fc  lea     r8, aP0; "_p0"
0x140004a03  cmovnz  rcx, rax
0x140004a07  mov     [rcx], r12w
0x140004a0b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004a10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004a15  mov     edx, ebp
0x140004a17  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004a1f  and     edx, 7FFFFFFFh; lInitialCount
0x140004a25  mov     [rsp+278h+dwFlags], r12d; int
0x140004a2a  mov     r8d, esi
0x140004a2d  lea     r9, [rsp+278h+Name]; lpName
0x140004a32  cmova   r8d, edx; lMaximumCount
0x140004a36  xor     ecx, ecx; lpSemaphoreAttributes
0x140004a38  call    cs:__imp_CreateSemaphoreExW
0x140004a3e  mov     r15, rax
0x140004a41  test    rax, rax
0x140004a44  jnz     short loc_140004A74
0x140004a46  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004a4b  mov     edi, eax
0x140004a4d  test    eax, eax
0x140004a4f  jns     short loc_140004AA8
0x140004a51  mov     rcx, [rsp+278h]; this
0x140004a59  lea     r8, aWil; "wil"
0x140004a60  mov     r9d, eax; char *
0x140004a63  mov     edx, 8Bh; void *
0x140004a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004a6d  mov     eax, edi
0x140004a6f  jmp     loc_140004B46
0x140004a74  call    cs:__imp_GetLastError
0x140004a7a  mov     rdi, [rbx]
0x140004a7d  test    rdi, rdi
0x140004a80  jz      short loc_140004AA5
0x140004a82  call    cs:__imp_GetLastError
0x140004a88  mov     rcx, rdi; hObject
0x140004a8b  mov     r14d, eax
0x140004a8e  call    cs:__imp_CloseHandle
0x140004a94  test    eax, eax
0x140004a96  jz      loc_140004B8B
0x140004a9c  mov     ecx, r14d; dwErrCode
0x140004a9f  call    cs:__imp_SetLastError
0x140004aa5  mov     [rbx], r15
0x140004aa8  lea     r8, asc_140018FC0; "h"
0x140004aaf  shr     rbp, 1Fh
0x140004ab3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004ab8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004abd  test    ebp, ebp
0x140004abf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004ac7  lea     r9, [rsp+278h+Name]; lpName
0x140004acc  mov     [rsp+278h+dwFlags], r12d; int
0x140004ad1  cmovnz  esi, ebp
0x140004ad4  mov     edx, ebp; lInitialCount
0x140004ad6  mov     r8d, esi; lMaximumCount
0x140004ad9  xor     ecx, ecx; lpSemaphoreAttributes
0x140004adb  call    cs:__imp_CreateSemaphoreExW
0x140004ae1  mov     rsi, rax
0x140004ae4  test    rax, rax
0x140004ae7  jnz     short loc_140004B14
0x140004ae9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004aee  mov     ebx, eax
0x140004af0  test    eax, eax
0x140004af2  jns     short loc_140004B44
0x140004af4  mov     rcx, [rsp+278h]; this
0x140004afc  lea     r8, aWil; "wil"
0x140004b03  mov     r9d, eax; char *
0x140004b06  mov     edx, 90h; void *
0x140004b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b10  mov     eax, ebx
0x140004b12  jmp     short loc_140004B46
0x140004b14  call    cs:__imp_GetLastError
0x140004b1a  mov     rdi, [rbx+8]
0x140004b1e  test    rdi, rdi
0x140004b21  jz      short loc_140004B40
0x140004b23  call    cs:__imp_GetLastError
0x140004b29  mov     rcx, rdi; hObject
0x140004b2c  mov     ebp, eax
0x140004b2e  call    cs:__imp_CloseHandle
0x140004b34  test    eax, eax
0x140004b36  jz      short loc_140004B72
0x140004b38  mov     ecx, ebp; dwErrCode
0x140004b3a  call    cs:__imp_SetLastError
0x140004b40  mov     [rbx+8], rsi
0x140004b44  xor     eax, eax
0x140004b46  mov     rcx, [rsp+278h+var_38]
0x140004b4e  xor     rcx, rsp; StackCookie
0x140004b51  call    __security_check_cookie
0x140004b56  lea     r11, [rsp+278h+var_28]
0x140004b5e  mov     rbx, [r11+38h]
0x140004b62  mov     rbp, [r11+40h]
0x140004b66  mov     rsp, r11
0x140004b69  pop     r15
0x140004b6b  pop     r14
0x140004b6d  pop     r12
0x140004b6f  pop     rdi
0x140004b70  pop     rsi
0x140004b71  retn
0x140004b72  mov     rcx, [rsp+278h]; this
0x140004b7a  mov     edx, 0A0Bh; void *
0x140004b7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004b85  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004b8b  mov     rcx, [rsp+278h]; this
0x140004b93  mov     edx, 0A0Bh; void *
0x140004b98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
