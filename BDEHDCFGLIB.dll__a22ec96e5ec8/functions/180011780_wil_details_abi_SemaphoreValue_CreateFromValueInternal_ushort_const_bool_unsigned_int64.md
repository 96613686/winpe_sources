# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180011780`
- end: `0x1800119a3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800113dc`

## callees

- `0x18000990c`
- `0x180011780`
- `0x180012008`
- `0x180012de4`
- `0x18001344c`
- `0x18001345c`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001187e`
- `KERNEL32!GetLastError` at `0x18001188c`
- `KERNEL32!GetLastError` at `0x18001191a`
- `KERNEL32!GetLastError` at `0x180011929`
- `KERNEL32!GetLastError` at `0x18001187e`
- `KERNEL32!GetLastError` at `0x18001188c`
- `KERNEL32!GetLastError` at `0x18001191a`
- `KERNEL32!GetLastError` at `0x180011929`
- `KERNEL32!CloseHandle` at `0x180011898`
- `KERNEL32!CloseHandle` at `0x180011934`
- `KERNEL32!CloseHandle` at `0x180011898`
- `KERNEL32!CloseHandle` at `0x180011934`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011940`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011849`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800118e8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011849`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800118e8`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  __int64 v31; // r8
  const char *v32; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011780  mov     [rsp+arg_8], rbx
0x180011785  push    rbp
0x180011786  push    rsi
0x180011787  push    rdi
0x180011788  push    r12
0x18001178a  push    r13
0x18001178c  push    r14
0x18001178e  push    r15
0x180011790  sub     rsp, 250h
0x180011797  mov     rax, cs:__security_cookie
0x18001179e  xor     rax, rsp
0x1800117a1  mov     [rsp+288h+var_48], rax
0x1800117a9  mov     rax, 0C000000000000000h
0x1800117b3  mov     rsi, r9
0x1800117b6  mov     r8, rdx
0x1800117b9  mov     rbx, rcx
0x1800117bc  test    rax, r9
0x1800117bf  jnz     loc_18001198A
0x1800117c5  xor     r12d, r12d
0x1800117c8  lea     rax, [rsp+288h+Name]
0x1800117cd  mov     r13d, 104h
0x1800117d3  mov     ecx, 7FFFFFFEh
0x1800117d8  mov     edx, r13d
0x1800117db  lea     ebp, [r12+1]
0x1800117e0  test    rcx, rcx
0x1800117e3  jz      short loc_180011803
0x1800117e5  movzx   r9d, word ptr [r8]
0x1800117e9  test    r9w, r9w
0x1800117ed  jz      short loc_180011803
0x1800117ef  mov     [rax], r9w
0x1800117f3  add     r8, 2
0x1800117f7  add     rax, 2
0x1800117fb  sub     rcx, rbp
0x1800117fe  sub     rdx, rbp
0x180011801  jnz     short loc_1800117E0
0x180011803  test    rdx, rdx
0x180011806  lea     rcx, [rax-2]
0x18001180a  lea     r8, aP0; "_p0"
0x180011811  mov     rdx, r13; unsigned __int64
0x180011814  cmovnz  rcx, rax
0x180011818  mov     [rcx], r12w
0x18001181c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180011821  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011826  mov     edx, esi
0x180011828  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180011830  and     edx, 7FFFFFFFh; lInitialCount
0x180011836  mov     [rsp+288h+dwFlags], r12d; int
0x18001183b  mov     r8d, ebp
0x18001183e  lea     r9, [rsp+288h+Name]; lpName
0x180011843  cmova   r8d, edx; lMaximumCount
0x180011847  xor     ecx, ecx; lpSemaphoreAttributes
0x180011849  call    cs:__imp_CreateSemaphoreExW
0x18001184f  mov     r15, rax
0x180011852  test    rax, rax
0x180011855  jnz     short loc_18001187E
0x180011857  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001185c  mov     edi, eax
0x18001185e  test    eax, eax
0x180011860  jns     short loc_1800118B2
0x180011862  mov     rcx, [rsp+288h]; this
0x18001186a  mov     r9d, eax; char *
0x18001186d  mov     edx, 8Bh; void *
0x180011872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011877  mov     eax, edi
0x180011879  jmp     loc_18001194C
0x18001187e  call    cs:__imp_GetLastError
0x180011884  mov     rdi, [rbx]
0x180011887  test    rdi, rdi
0x18001188a  jz      short loc_1800118AF
0x18001188c  call    cs:__imp_GetLastError
0x180011892  mov     rcx, rdi; hObject
0x180011895  mov     r14d, eax
0x180011898  call    cs:__imp_CloseHandle
0x18001189e  test    eax, eax
0x1800118a0  jz      loc_180011990
0x1800118a6  mov     ecx, r14d; dwErrCode
0x1800118a9  call    cs:__imp_SetLastError
0x1800118af  mov     [rbx], r15
0x1800118b2  lea     r8, asc_180017CE8; "h"
0x1800118b9  shr     rsi, 1Fh
0x1800118bd  mov     rdx, r13; unsigned __int64
0x1800118c0  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800118c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800118ca  test    esi, esi
0x1800118cc  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800118d4  lea     r9, [rsp+288h+Name]; lpName
0x1800118d9  mov     [rsp+288h+dwFlags], r12d; int
0x1800118de  cmovnz  ebp, esi
0x1800118e1  mov     edx, esi; lInitialCount
0x1800118e3  mov     r8d, ebp; lMaximumCount
0x1800118e6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800118e8  call    cs:__imp_CreateSemaphoreExW
0x1800118ee  mov     rbp, rax
0x1800118f1  test    rax, rax
0x1800118f4  jnz     short loc_18001191A
0x1800118f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800118fb  mov     ebx, eax
0x1800118fd  test    eax, eax
0x1800118ff  jns     short loc_18001194A
0x180011901  mov     rcx, [rsp+288h]; this
0x180011909  mov     r9d, eax; char *
0x18001190c  mov     edx, 90h; void *
0x180011911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011916  mov     eax, ebx
0x180011918  jmp     short loc_18001194C
0x18001191a  call    cs:__imp_GetLastError
0x180011920  mov     rdi, [rbx+8]
0x180011924  test    rdi, rdi
0x180011927  jz      short loc_180011946
0x180011929  call    cs:__imp_GetLastError
0x18001192f  mov     rcx, rdi; hObject
0x180011932  mov     esi, eax
0x180011934  call    cs:__imp_CloseHandle
0x18001193a  test    eax, eax
0x18001193c  jz      short loc_180011977
0x18001193e  mov     ecx, esi; dwErrCode
0x180011940  call    cs:__imp_SetLastError
0x180011946  mov     [rbx+8], rbp
0x18001194a  xor     eax, eax
0x18001194c  mov     rcx, [rsp+288h+var_48]
0x180011954  xor     rcx, rsp; StackCookie
0x180011957  call    __security_check_cookie
0x18001195c  mov     rbx, [rsp+288h+arg_8]
0x180011964  add     rsp, 250h
0x18001196b  pop     r15
0x18001196d  pop     r14
0x18001196f  pop     r13
0x180011971  pop     r12
0x180011973  pop     rdi
0x180011974  pop     rsi
0x180011975  pop     rbp
0x180011976  retn
0x180011977  mov     rcx, [rsp+288h]; this
0x18001197f  mov     edx, 0A0Bh; void *
0x180011984  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001198a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011990  mov     rcx, [rsp+288h]; this
0x180011998  mov     edx, 0A0Bh; void *
0x18001199d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
