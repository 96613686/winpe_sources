# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400035e0`
- end: `0x1400037ed`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000323c`

## callees

- `0x140001cd0`
- `0x1400035e0`
- `0x140003e98`
- `0x140005108`
- `0x1400053b0`
- `0x14000589c`
- `0x1400058ac`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1400036a4`
- `KERNEL32!CreateSemaphoreExW` at `0x140003740`
- `KERNEL32!CreateSemaphoreExW` at `0x1400036a4`
- `KERNEL32!CreateSemaphoreExW` at `0x140003740`
- `KERNEL32!SetLastError` at `0x140003704`
- `KERNEL32!SetLastError` at `0x140003789`
- `KERNEL32!SetLastError` at `0x140003704`
- `KERNEL32!SetLastError` at `0x140003789`
- `KERNEL32!GetLastError` at `0x1400036d9`
- `KERNEL32!GetLastError` at `0x1400036e7`
- `KERNEL32!GetLastError` at `0x140003763`
- `KERNEL32!GetLastError` at `0x140003772`
- `KERNEL32!GetLastError` at `0x1400036d9`
- `KERNEL32!GetLastError` at `0x1400036e7`
- `KERNEL32!GetLastError` at `0x140003763`
- `KERNEL32!GetLastError` at `0x140003772`
- `KERNEL32!CloseHandle` at `0x1400036f3`
- `KERNEL32!CloseHandle` at `0x14000377d`
- `KERNEL32!CloseHandle` at `0x1400036f3`
- `KERNEL32!CloseHandle` at `0x14000377d`

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
0x1400035e0  mov     [rsp+arg_8], rbx
0x1400035e5  mov     [rsp+arg_10], rbp
0x1400035ea  push    rsi
0x1400035eb  push    rdi
0x1400035ec  push    r12
0x1400035ee  push    r14
0x1400035f0  push    r15
0x1400035f2  sub     rsp, 250h
0x1400035f9  mov     rax, cs:__security_cookie
0x140003600  xor     rax, rsp
0x140003603  mov     [rsp+278h+var_38], rax
0x14000360b  mov     rax, 0C000000000000000h
0x140003615  mov     rbp, r9
0x140003618  mov     r8, rdx
0x14000361b  mov     rdi, rcx
0x14000361e  test    rax, r9
0x140003621  jnz     loc_1400037D4
0x140003627  xor     r12d, r12d
0x14000362a  lea     rax, [rsp+278h+Name]
0x14000362f  mov     ecx, 7FFFFFFEh
0x140003634  mov     edx, 104h
0x140003639  lea     esi, [r12+1]
0x14000363e  test    rcx, rcx
0x140003641  jz      short loc_140003661
0x140003643  movzx   r9d, word ptr [r8]
0x140003647  test    r9w, r9w
0x14000364b  jz      short loc_140003661
0x14000364d  mov     [rax], r9w
0x140003651  add     r8, 2
0x140003655  add     rax, 2
0x140003659  sub     rcx, rsi
0x14000365c  sub     rdx, rsi; unsigned __int64
0x14000365f  jnz     short loc_14000363E
0x140003661  test    rdx, rdx
0x140003664  lea     rcx, [rax-2]
0x140003668  lea     r8, aP0; "_p0"
0x14000366f  cmovnz  rcx, rax
0x140003673  mov     [rcx], r12w
0x140003677  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000367c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003681  mov     edx, ebp
0x140003683  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000368b  and     edx, 7FFFFFFFh; lInitialCount
0x140003691  mov     [rsp+278h+dwFlags], r12d; int
0x140003696  mov     r8d, esi
0x140003699  lea     r9, [rsp+278h+Name]; lpName
0x14000369e  cmova   r8d, edx; lMaximumCount
0x1400036a2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400036a4  call    cs:__imp_CreateSemaphoreExW
0x1400036aa  mov     r15, rax
0x1400036ad  test    rax, rax
0x1400036b0  jnz     short loc_1400036D9
0x1400036b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400036b7  mov     ebx, eax
0x1400036b9  test    eax, eax
0x1400036bb  jns     short loc_14000370D
0x1400036bd  mov     edx, 8Bh; void *
0x1400036c2  mov     rcx, [rsp+278h]; this
0x1400036ca  mov     r9d, ebx; char *
0x1400036cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400036d2  mov     eax, ebx
0x1400036d4  jmp     loc_140003795
0x1400036d9  call    cs:__imp_GetLastError
0x1400036df  mov     rbx, [rdi]
0x1400036e2  test    rbx, rbx
0x1400036e5  jz      short loc_14000370A
0x1400036e7  call    cs:__imp_GetLastError
0x1400036ed  mov     rcx, rbx; hObject
0x1400036f0  mov     r14d, eax
0x1400036f3  call    cs:__imp_CloseHandle
0x1400036f9  test    eax, eax
0x1400036fb  jz      loc_1400037DA
0x140003701  mov     ecx, r14d; dwErrCode
0x140003704  call    cs:__imp_SetLastError
0x14000370a  mov     [rdi], r15
0x14000370d  lea     r8, asc_140009A88; "h"
0x140003714  shr     rbp, 1Fh
0x140003718  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000371d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003722  test    ebp, ebp
0x140003724  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000372c  lea     r9, [rsp+278h+Name]; lpName
0x140003731  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003736  cmovnz  esi, ebp
0x140003739  mov     edx, ebp; lInitialCount
0x14000373b  mov     r8d, esi; lMaximumCount
0x14000373e  xor     ecx, ecx; lpSemaphoreAttributes
0x140003740  call    cs:__imp_CreateSemaphoreExW
0x140003746  mov     rsi, rax
0x140003749  test    rax, rax
0x14000374c  jnz     short loc_140003763
0x14000374e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003753  mov     ebx, eax
0x140003755  test    eax, eax
0x140003757  jns     short loc_140003793
0x140003759  mov     edx, 90h
0x14000375e  jmp     loc_1400036C2
0x140003763  call    cs:__imp_GetLastError
0x140003769  mov     rbx, [rdi+8]
0x14000376d  test    rbx, rbx
0x140003770  jz      short loc_14000378F
0x140003772  call    cs:__imp_GetLastError
0x140003778  mov     rcx, rbx; hObject
0x14000377b  mov     ebp, eax
0x14000377d  call    cs:__imp_CloseHandle
0x140003783  test    eax, eax
0x140003785  jz      short loc_1400037C1
0x140003787  mov     ecx, ebp; dwErrCode
0x140003789  call    cs:__imp_SetLastError
0x14000378f  mov     [rdi+8], rsi
0x140003793  xor     eax, eax
0x140003795  mov     rcx, [rsp+278h+var_38]
0x14000379d  xor     rcx, rsp; StackCookie
0x1400037a0  call    __security_check_cookie
0x1400037a5  lea     r11, [rsp+278h+var_28]
0x1400037ad  mov     rbx, [r11+38h]
0x1400037b1  mov     rbp, [r11+40h]
0x1400037b5  mov     rsp, r11
0x1400037b8  pop     r15
0x1400037ba  pop     r14
0x1400037bc  pop     r12
0x1400037be  pop     rdi
0x1400037bf  pop     rsi
0x1400037c0  retn
0x1400037c1  mov     rcx, [rsp+278h]; this
0x1400037c9  mov     edx, 0A0Bh; void *
0x1400037ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400037d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400037da  mov     rcx, [rsp+278h]; this
0x1400037e2  mov     edx, 0A0Bh; void *
0x1400037e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
