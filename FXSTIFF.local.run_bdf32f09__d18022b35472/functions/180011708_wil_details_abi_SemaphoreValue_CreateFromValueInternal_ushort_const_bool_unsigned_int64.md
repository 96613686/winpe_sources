# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180011708`
- end: `0x180011917`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `527`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180010f58`
- `0x180011324`

## callees

- `0x180011708`
- `0x180012498`
- `0x180014664`
- `0x180014eec`
- `0x180015b5c`
- `0x180015b6c`
- `0x180017c00`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800117cc`
- `KERNEL32!CreateSemaphoreExW` at `0x180011871`
- `KERNEL32!CreateSemaphoreExW` at `0x1800117cc`
- `KERNEL32!CreateSemaphoreExW` at `0x180011871`
- `KERNEL32!GetLastError` at `0x180011801`
- `KERNEL32!GetLastError` at `0x18001180f`
- `KERNEL32!GetLastError` at `0x180011894`
- `KERNEL32!GetLastError` at `0x1800118a3`
- `KERNEL32!GetLastError` at `0x180011801`
- `KERNEL32!GetLastError` at `0x18001180f`
- `KERNEL32!GetLastError` at `0x180011894`
- `KERNEL32!GetLastError` at `0x1800118a3`
- `KERNEL32!SetLastError` at `0x180011834`
- `KERNEL32!SetLastError` at `0x1800118c2`
- `KERNEL32!SetLastError` at `0x180011834`
- `KERNEL32!SetLastError` at `0x1800118c2`
- `KERNEL32!CloseHandle` at `0x18001181b`
- `KERNEL32!CloseHandle` at `0x1800118ae`
- `KERNEL32!CloseHandle` at `0x18001181b`
- `KERNEL32!CloseHandle` at `0x1800118ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rax
  LONG v10; // esi
  WCHAR v11; // r9
  WCHAR *v12; // rcx
  LONG v13; // r8d
  wil::details *v14; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v16; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  void *v21; // rbx
  DWORD LastError; // r14d
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned __int64 v25; // rbp
  wil::details *v26; // rcx
  HANDLE v27; // rsi
  void *v28; // rbx
  DWORD v29; // ebp
  unsigned int v30; // r8d
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = 2147483646;
  v8 = 260;
  v9 = Name;
  v10 = 1;
  do
  {
    if ( !v7 )
      break;
    v11 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v9++ = v11;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  StringCchCatW(Name, v8, L"_p0");
  v13 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v13 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v13, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v21 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v25 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v25 )
    v10 = v25;
  v27 = CreateSemaphoreExW(0, v25, v10, Name, 0, 0x1F0003u);
  if ( v27 )
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
    *((_QWORD *)this + 1) = v27;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011708  mov     [rsp+arg_8], rbx
0x18001170d  mov     [rsp+arg_10], rbp
0x180011712  push    rsi
0x180011713  push    rdi
0x180011714  push    r12
0x180011716  push    r14
0x180011718  push    r15
0x18001171a  sub     rsp, 250h
0x180011721  mov     rax, cs:__security_cookie
0x180011728  xor     rax, rsp
0x18001172b  mov     [rsp+278h+var_38], rax
0x180011733  mov     rbp, r9
0x180011736  mov     r8, rdx
0x180011739  mov     rdi, rcx
0x18001173c  mov     rax, 0C000000000000000h
0x180011746  test    rax, r9
0x180011749  jnz     loc_180011906
0x18001174f  mov     ecx, 7FFFFFFEh
0x180011754  mov     edx, 104h
0x180011759  lea     rax, [rsp+278h+Name]
0x18001175e  xor     r12d, r12d
0x180011761  lea     esi, [r12+1]
0x180011766  test    rcx, rcx
0x180011769  jz      short loc_180011789
0x18001176b  movzx   r9d, word ptr [r8]
0x18001176f  test    r9w, r9w
0x180011773  jz      short loc_180011789
0x180011775  add     r8, 2
0x180011779  mov     [rax], r9w
0x18001177d  add     rax, 2
0x180011781  sub     rcx, rsi
0x180011784  sub     rdx, rsi; unsigned __int64
0x180011787  jnz     short loc_180011766
0x180011789  lea     rcx, [rax-2]
0x18001178d  test    rdx, rdx
0x180011790  cmovnz  rcx, rax
0x180011794  mov     [rcx], r12w
0x180011798  lea     r8, aP0; "_p0"
0x18001179f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800117a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800117a9  mov     edx, ebp
0x1800117ab  and     edx, 7FFFFFFFh; lInitialCount
0x1800117b1  mov     r8d, esi
0x1800117b4  cmova   r8d, edx; lMaximumCount
0x1800117b8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800117c0  mov     [rsp+278h+dwFlags], r12d; int
0x1800117c5  lea     r9, [rsp+278h+Name]; lpName
0x1800117ca  xor     ecx, ecx; lpSemaphoreAttributes
0x1800117cc  call    cs:__imp_CreateSemaphoreExW
0x1800117d2  mov     r15, rax
0x1800117d5  test    rax, rax
0x1800117d8  jnz     short loc_180011801
0x1800117da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800117df  mov     ebx, eax
0x1800117e1  test    eax, eax
0x1800117e3  jns     short loc_18001183E
0x1800117e5  mov     edx, 8Bh; void *
0x1800117ea  mov     r9d, ebx; char *
0x1800117ed  mov     rcx, [rsp+278h]; this
0x1800117f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117fa  mov     eax, ebx
0x1800117fc  jmp     loc_1800118CF
0x180011801  call    cs:__imp_GetLastError
0x180011807  mov     rbx, [rdi]
0x18001180a  test    rbx, rbx
0x18001180d  jz      short loc_18001183B
0x18001180f  call    cs:__imp_GetLastError
0x180011815  mov     r14d, eax
0x180011818  mov     rcx, rbx; hObject
0x18001181b  call    cs:__imp_CloseHandle
0x180011821  mov     rcx, [rsp+278h]; this
0x180011829  test    eax, eax
0x18001182b  jz      loc_18001190C
0x180011831  mov     ecx, r14d; dwErrCode
0x180011834  call    cs:__imp_SetLastError
0x18001183a  nop
0x18001183b  mov     [rdi], r15
0x18001183e  shr     rbp, 1Fh
0x180011842  lea     r8, asc_18006CC40; "h"
0x180011849  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001184e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011853  test    ebp, ebp
0x180011855  cmovnz  esi, ebp
0x180011858  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180011860  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180011865  lea     r9, [rsp+278h+Name]; lpName
0x18001186a  mov     r8d, esi; lMaximumCount
0x18001186d  mov     edx, ebp; lInitialCount
0x18001186f  xor     ecx, ecx; lpSemaphoreAttributes
0x180011871  call    cs:__imp_CreateSemaphoreExW
0x180011877  mov     rsi, rax
0x18001187a  test    rax, rax
0x18001187d  jnz     short loc_180011894
0x18001187f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011884  mov     ebx, eax
0x180011886  test    eax, eax
0x180011888  jns     short loc_1800118CD
0x18001188a  mov     edx, 90h
0x18001188f  jmp     loc_1800117EA
0x180011894  call    cs:__imp_GetLastError
0x18001189a  mov     rbx, [rdi+8]
0x18001189e  test    rbx, rbx
0x1800118a1  jz      short loc_1800118C9
0x1800118a3  call    cs:__imp_GetLastError
0x1800118a9  mov     ebp, eax
0x1800118ab  mov     rcx, rbx; hObject
0x1800118ae  call    cs:__imp_CloseHandle
0x1800118b4  mov     rcx, [rsp+278h]; this
0x1800118bc  test    eax, eax
0x1800118be  jz      short loc_1800118FB
0x1800118c0  mov     ecx, ebp; dwErrCode
0x1800118c2  call    cs:__imp_SetLastError
0x1800118c8  nop
0x1800118c9  mov     [rdi+8], rsi
0x1800118cd  xor     eax, eax
0x1800118cf  mov     rcx, [rsp+278h+var_38]
0x1800118d7  xor     rcx, rsp; StackCookie
0x1800118da  call    __security_check_cookie
0x1800118df  lea     r11, [rsp+278h+var_28]
0x1800118e7  mov     rbx, [r11+38h]
0x1800118eb  mov     rbp, [r11+40h]
0x1800118ef  mov     rsp, r11
0x1800118f2  pop     r15
0x1800118f4  pop     r14
0x1800118f6  pop     r12
0x1800118f8  pop     rdi
0x1800118f9  pop     rsi
0x1800118fa  retn
0x1800118fb  mov     edx, 0A0Bh; void *
0x180011900  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011906  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001190c  mov     edx, 0A0Bh; void *
0x180011911  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
