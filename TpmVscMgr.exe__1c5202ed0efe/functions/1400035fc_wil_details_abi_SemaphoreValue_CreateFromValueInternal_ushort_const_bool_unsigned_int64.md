# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400035fc`
- end: `0x140003809`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003258`

## callees

- `0x1400016a0`
- `0x1400035fc`
- `0x140003e78`
- `0x140004db4`
- `0x140005690`
- `0x140005bac`
- `0x140005bbc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140003720`
- `KERNEL32!SetLastError` at `0x1400037a5`
- `KERNEL32!SetLastError` at `0x140003720`
- `KERNEL32!SetLastError` at `0x1400037a5`
- `KERNEL32!GetLastError` at `0x1400036f5`
- `KERNEL32!GetLastError` at `0x140003703`
- `KERNEL32!GetLastError` at `0x14000377f`
- `KERNEL32!GetLastError` at `0x14000378e`
- `KERNEL32!GetLastError` at `0x1400036f5`
- `KERNEL32!GetLastError` at `0x140003703`
- `KERNEL32!GetLastError` at `0x14000377f`
- `KERNEL32!GetLastError` at `0x14000378e`
- `KERNEL32!CloseHandle` at `0x14000370f`
- `KERNEL32!CloseHandle` at `0x140003799`
- `KERNEL32!CloseHandle` at `0x14000370f`
- `KERNEL32!CloseHandle` at `0x140003799`
- `KERNEL32!CreateSemaphoreExW` at `0x1400036c0`
- `KERNEL32!CreateSemaphoreExW` at `0x14000375c`
- `KERNEL32!CreateSemaphoreExW` at `0x1400036c0`
- `KERNEL32!CreateSemaphoreExW` at `0x14000375c`

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
0x1400035fc  mov     [rsp+arg_8], rbx
0x140003601  mov     [rsp+arg_10], rbp
0x140003606  push    rsi
0x140003607  push    rdi
0x140003608  push    r12
0x14000360a  push    r14
0x14000360c  push    r15
0x14000360e  sub     rsp, 250h
0x140003615  mov     rax, cs:__security_cookie
0x14000361c  xor     rax, rsp
0x14000361f  mov     [rsp+278h+var_38], rax
0x140003627  mov     rax, 0C000000000000000h
0x140003631  mov     rbp, r9
0x140003634  mov     r8, rdx
0x140003637  mov     rdi, rcx
0x14000363a  test    rax, r9
0x14000363d  jnz     loc_1400037F0
0x140003643  xor     r12d, r12d
0x140003646  lea     rax, [rsp+278h+Name]
0x14000364b  mov     ecx, 7FFFFFFEh
0x140003650  mov     edx, 104h
0x140003655  lea     esi, [r12+1]
0x14000365a  test    rcx, rcx
0x14000365d  jz      short loc_14000367D
0x14000365f  movzx   r9d, word ptr [r8]
0x140003663  test    r9w, r9w
0x140003667  jz      short loc_14000367D
0x140003669  mov     [rax], r9w
0x14000366d  add     r8, 2
0x140003671  add     rax, 2
0x140003675  sub     rcx, rsi
0x140003678  sub     rdx, rsi; unsigned __int64
0x14000367b  jnz     short loc_14000365A
0x14000367d  test    rdx, rdx
0x140003680  lea     rcx, [rax-2]
0x140003684  lea     r8, aP0; "_p0"
0x14000368b  cmovnz  rcx, rax
0x14000368f  mov     [rcx], r12w
0x140003693  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003698  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000369d  mov     edx, ebp
0x14000369f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400036a7  and     edx, 7FFFFFFFh; lInitialCount
0x1400036ad  mov     [rsp+278h+dwFlags], r12d; int
0x1400036b2  mov     r8d, esi
0x1400036b5  lea     r9, [rsp+278h+Name]; lpName
0x1400036ba  cmova   r8d, edx; lMaximumCount
0x1400036be  xor     ecx, ecx; lpSemaphoreAttributes
0x1400036c0  call    cs:__imp_CreateSemaphoreExW
0x1400036c6  mov     r15, rax
0x1400036c9  test    rax, rax
0x1400036cc  jnz     short loc_1400036F5
0x1400036ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400036d3  mov     ebx, eax
0x1400036d5  test    eax, eax
0x1400036d7  jns     short loc_140003729
0x1400036d9  mov     edx, 8Bh; void *
0x1400036de  mov     rcx, [rsp+278h]; this
0x1400036e6  mov     r9d, ebx; char *
0x1400036e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400036ee  mov     eax, ebx
0x1400036f0  jmp     loc_1400037B1
0x1400036f5  call    cs:__imp_GetLastError
0x1400036fb  mov     rbx, [rdi]
0x1400036fe  test    rbx, rbx
0x140003701  jz      short loc_140003726
0x140003703  call    cs:__imp_GetLastError
0x140003709  mov     rcx, rbx; hObject
0x14000370c  mov     r14d, eax
0x14000370f  call    cs:__imp_CloseHandle
0x140003715  test    eax, eax
0x140003717  jz      loc_1400037F6
0x14000371d  mov     ecx, r14d; dwErrCode
0x140003720  call    cs:__imp_SetLastError
0x140003726  mov     [rdi], r15
0x140003729  lea     r8, asc_140014EA0; "h"
0x140003730  shr     rbp, 1Fh
0x140003734  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003739  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000373e  test    ebp, ebp
0x140003740  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003748  lea     r9, [rsp+278h+Name]; lpName
0x14000374d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003752  cmovnz  esi, ebp
0x140003755  mov     edx, ebp; lInitialCount
0x140003757  mov     r8d, esi; lMaximumCount
0x14000375a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000375c  call    cs:__imp_CreateSemaphoreExW
0x140003762  mov     rsi, rax
0x140003765  test    rax, rax
0x140003768  jnz     short loc_14000377F
0x14000376a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000376f  mov     ebx, eax
0x140003771  test    eax, eax
0x140003773  jns     short loc_1400037AF
0x140003775  mov     edx, 90h
0x14000377a  jmp     loc_1400036DE
0x14000377f  call    cs:__imp_GetLastError
0x140003785  mov     rbx, [rdi+8]
0x140003789  test    rbx, rbx
0x14000378c  jz      short loc_1400037AB
0x14000378e  call    cs:__imp_GetLastError
0x140003794  mov     rcx, rbx; hObject
0x140003797  mov     ebp, eax
0x140003799  call    cs:__imp_CloseHandle
0x14000379f  test    eax, eax
0x1400037a1  jz      short loc_1400037DD
0x1400037a3  mov     ecx, ebp; dwErrCode
0x1400037a5  call    cs:__imp_SetLastError
0x1400037ab  mov     [rdi+8], rsi
0x1400037af  xor     eax, eax
0x1400037b1  mov     rcx, [rsp+278h+var_38]
0x1400037b9  xor     rcx, rsp; StackCookie
0x1400037bc  call    __security_check_cookie
0x1400037c1  lea     r11, [rsp+278h+var_28]
0x1400037c9  mov     rbx, [r11+38h]
0x1400037cd  mov     rbp, [r11+40h]
0x1400037d1  mov     rsp, r11
0x1400037d4  pop     r15
0x1400037d6  pop     r14
0x1400037d8  pop     r12
0x1400037da  pop     rdi
0x1400037db  pop     rsi
0x1400037dc  retn
0x1400037dd  mov     rcx, [rsp+278h]; this
0x1400037e5  mov     edx, 0A0Bh; void *
0x1400037ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400037f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400037f6  mov     rcx, [rsp+278h]; this
0x1400037fe  mov     edx, 0A0Bh; void *
0x140003803  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
