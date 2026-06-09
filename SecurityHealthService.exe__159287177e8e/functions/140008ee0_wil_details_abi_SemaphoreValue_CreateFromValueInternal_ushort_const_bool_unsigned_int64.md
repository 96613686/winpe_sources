# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140008ee0`
- end: `0x14000910a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008718`
- `0x140008ae8`

## callees

- `0x1400015d0`
- `0x140006bec`
- `0x140006c10`
- `0x140006e3c`
- `0x140008ee0`
- `0x140009924`
- `0x14000c620`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008fe0`
- `KERNEL32!GetLastError` at `0x140008fee`
- `KERNEL32!GetLastError` at `0x140009080`
- `KERNEL32!GetLastError` at `0x14000908f`
- `KERNEL32!GetLastError` at `0x140008fe0`
- `KERNEL32!GetLastError` at `0x140008fee`
- `KERNEL32!GetLastError` at `0x140009080`
- `KERNEL32!GetLastError` at `0x14000908f`
- `KERNEL32!CloseHandle` at `0x140008ffa`
- `KERNEL32!CloseHandle` at `0x14000909a`
- `KERNEL32!CloseHandle` at `0x140008ffa`
- `KERNEL32!CloseHandle` at `0x14000909a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140008fa4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009047`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140008fa4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009047`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000900b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000900b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090a6`

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
0x140008ee0  mov     [rsp+arg_8], rbx
0x140008ee5  mov     [rsp+arg_10], rbp
0x140008eea  push    rsi
0x140008eeb  push    rdi
0x140008eec  push    r12
0x140008eee  push    r14
0x140008ef0  push    r15
0x140008ef2  sub     rsp, 250h
0x140008ef9  mov     rax, cs:__security_cookie
0x140008f00  xor     rax, rsp
0x140008f03  mov     [rsp+278h+var_38], rax
0x140008f0b  mov     rax, 0C000000000000000h
0x140008f15  mov     rbp, r9
0x140008f18  mov     r8, rdx
0x140008f1b  mov     rbx, rcx
0x140008f1e  test    rax, r9
0x140008f21  jnz     loc_1400090F1
0x140008f27  xor     r12d, r12d
0x140008f2a  lea     rax, [rsp+278h+Name]
0x140008f2f  mov     ecx, 7FFFFFFEh
0x140008f34  mov     edx, 104h
0x140008f39  lea     esi, [r12+1]
0x140008f3e  test    rcx, rcx
0x140008f41  jz      short loc_140008F61
0x140008f43  movzx   r9d, word ptr [r8]
0x140008f47  test    r9w, r9w
0x140008f4b  jz      short loc_140008F61
0x140008f4d  mov     [rax], r9w
0x140008f51  add     r8, 2
0x140008f55  add     rax, 2
0x140008f59  sub     rcx, rsi
0x140008f5c  sub     rdx, rsi; unsigned __int64
0x140008f5f  jnz     short loc_140008F3E
0x140008f61  test    rdx, rdx
0x140008f64  lea     rcx, [rax-2]
0x140008f68  lea     r8, aP0; "_p0"
0x140008f6f  cmovnz  rcx, rax
0x140008f73  mov     [rcx], r12w
0x140008f77  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140008f7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008f81  mov     edx, ebp
0x140008f83  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140008f8b  and     edx, 7FFFFFFFh; lInitialCount
0x140008f91  mov     [rsp+278h+dwFlags], r12d; int
0x140008f96  mov     r8d, esi
0x140008f99  lea     r9, [rsp+278h+Name]; lpName
0x140008f9e  cmova   r8d, edx; lMaximumCount
0x140008fa2  xor     ecx, ecx; lpSemaphoreAttributes
0x140008fa4  call    cs:__imp_CreateSemaphoreExW
0x140008faa  mov     r15, rax
0x140008fad  test    rax, rax
0x140008fb0  jnz     short loc_140008FE0
0x140008fb2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008fb7  mov     edi, eax
0x140008fb9  test    eax, eax
0x140008fbb  jns     short loc_140009014
0x140008fbd  mov     rcx, [rsp+278h]; this
0x140008fc5  lea     r8, aWil; "wil"
0x140008fcc  mov     r9d, eax; char *
0x140008fcf  mov     edx, 8Bh; void *
0x140008fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008fd9  mov     eax, edi
0x140008fdb  jmp     loc_1400090B2
0x140008fe0  call    cs:__imp_GetLastError
0x140008fe6  mov     rdi, [rbx]
0x140008fe9  test    rdi, rdi
0x140008fec  jz      short loc_140009011
0x140008fee  call    cs:__imp_GetLastError
0x140008ff4  mov     rcx, rdi; hObject
0x140008ff7  mov     r14d, eax
0x140008ffa  call    cs:__imp_CloseHandle
0x140009000  test    eax, eax
0x140009002  jz      loc_1400090F7
0x140009008  mov     ecx, r14d; dwErrCode
0x14000900b  call    cs:__imp_SetLastError
0x140009011  mov     [rbx], r15
0x140009014  lea     r8, asc_140015EC0; "h"
0x14000901b  shr     rbp, 1Fh
0x14000901f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140009024  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009029  test    ebp, ebp
0x14000902b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009033  lea     r9, [rsp+278h+Name]; lpName
0x140009038  mov     [rsp+278h+dwFlags], r12d; int
0x14000903d  cmovnz  esi, ebp
0x140009040  mov     edx, ebp; lInitialCount
0x140009042  mov     r8d, esi; lMaximumCount
0x140009045  xor     ecx, ecx; lpSemaphoreAttributes
0x140009047  call    cs:__imp_CreateSemaphoreExW
0x14000904d  mov     rsi, rax
0x140009050  test    rax, rax
0x140009053  jnz     short loc_140009080
0x140009055  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000905a  mov     ebx, eax
0x14000905c  test    eax, eax
0x14000905e  jns     short loc_1400090B0
0x140009060  mov     rcx, [rsp+278h]; this
0x140009068  lea     r8, aWil; "wil"
0x14000906f  mov     r9d, eax; char *
0x140009072  mov     edx, 90h; void *
0x140009077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000907c  mov     eax, ebx
0x14000907e  jmp     short loc_1400090B2
0x140009080  call    cs:__imp_GetLastError
0x140009086  mov     rdi, [rbx+8]
0x14000908a  test    rdi, rdi
0x14000908d  jz      short loc_1400090AC
0x14000908f  call    cs:__imp_GetLastError
0x140009095  mov     rcx, rdi; hObject
0x140009098  mov     ebp, eax
0x14000909a  call    cs:__imp_CloseHandle
0x1400090a0  test    eax, eax
0x1400090a2  jz      short loc_1400090DE
0x1400090a4  mov     ecx, ebp; dwErrCode
0x1400090a6  call    cs:__imp_SetLastError
0x1400090ac  mov     [rbx+8], rsi
0x1400090b0  xor     eax, eax
0x1400090b2  mov     rcx, [rsp+278h+var_38]
0x1400090ba  xor     rcx, rsp; StackCookie
0x1400090bd  call    __security_check_cookie
0x1400090c2  lea     r11, [rsp+278h+var_28]
0x1400090ca  mov     rbx, [r11+38h]
0x1400090ce  mov     rbp, [r11+40h]
0x1400090d2  mov     rsp, r11
0x1400090d5  pop     r15
0x1400090d7  pop     r14
0x1400090d9  pop     r12
0x1400090db  pop     rdi
0x1400090dc  pop     rsi
0x1400090dd  retn
0x1400090de  mov     rcx, [rsp+278h]; this
0x1400090e6  mov     edx, 0A0Bh; void *
0x1400090eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400090f1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400090f7  mov     rcx, [rsp+278h]; this
0x1400090ff  mov     edx, 0A0Bh; void *
0x140009104  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
