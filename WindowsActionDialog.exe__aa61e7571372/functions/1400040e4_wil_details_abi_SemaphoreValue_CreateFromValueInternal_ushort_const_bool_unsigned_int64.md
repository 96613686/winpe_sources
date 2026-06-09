# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400040e4`
- end: `0x14000435c`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `632`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003c20`

## callees

- `0x140001460`
- `0x1400040e4`
- `0x1400049c4`
- `0x1400063f0`
- `0x140006e74`
- `0x1400076dc`
- `0x1400076ec`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1400041a8`
- `KERNEL32!CreateSemaphoreExW` at `0x14000425f`
- `KERNEL32!CreateSemaphoreExW` at `0x1400041a8`
- `KERNEL32!CreateSemaphoreExW` at `0x14000425f`
- `KERNEL32!SetLastError` at `0x140004223`
- `KERNEL32!SetLastError` at `0x1400042d2`
- `KERNEL32!SetLastError` at `0x140004223`
- `KERNEL32!SetLastError` at `0x1400042d2`
- `KERNEL32!CloseHandle` at `0x140004212`
- `KERNEL32!CloseHandle` at `0x1400042c6`
- `KERNEL32!CloseHandle` at `0x140004212`
- `KERNEL32!CloseHandle` at `0x1400042c6`
- `KERNEL32!GetLastError` at `0x1400041f8`
- `KERNEL32!GetLastError` at `0x140004206`
- `KERNEL32!GetLastError` at `0x1400042ac`
- `KERNEL32!GetLastError` at `0x1400042bb`
- `KERNEL32!GetLastError` at `0x1400041f8`
- `KERNEL32!GetLastError` at `0x140004206`
- `KERNEL32!GetLastError` at `0x1400042ac`
- `KERNEL32!GetLastError` at `0x1400042bb`

## string_xrefs

- `0x1400041db`: `m_semaphore.create(static_cast<LONG>(lowPart), static_cast<LONG>((lowPart > 0) ? lowPart : 1), localName)`
- `0x1400041c9`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x140004280`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x140004292`: `m_semaphoreHigh.create(static_cast<LONG>(highPart), static_cast<LONG>((highPart > 0) ? highPart : 1), localName)`

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
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  unsigned int v29; // r8d
  wil::details *dwDesiredAccess; // [rsp+28h] [rbp-250h]
  int Name[132]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag5::_FailFastImmediate_Unexpected(this);
  v7 = (WCHAR *)Name;
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
  StringCchCatW((unsigned __int16 *)Name, v9, L"_p0");
  LODWORD(dwDesiredAccess) = 2031619;
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, (LPCWSTR)Name, 0, (DWORD)dwDesiredAccess);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag5::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v21,
          "wil::details::CloseHandle",
          "::CloseHandle(handle)",
          (const char *)dwDesiredAccess);
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
      LODWORD(dwDesiredAccess) = LastErrorFailHr;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        "m_semaphore.create(static_cast<LONG>(lowPart), static_cast<LONG>((lowPart > 0) ? lowPart : 1), localName)",
        dwDesiredAccess,
        Name[0]);
      return v17;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW((unsigned __int16 *)Name, v16, L"h");
  LODWORD(dwDesiredAccess) = 2031619;
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, (LPCWSTR)Name, 0, (DWORD)dwDesiredAccess);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag5::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v29,
          "wil::details::CloseHandle",
          "::CloseHandle(handle)",
          (const char *)dwDesiredAccess);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      LODWORD(dwDesiredAccess) = v25;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        "m_semaphoreHigh.create(static_cast<LONG>(highPart), static_cast<LONG>((highPart > 0) ? highPart : 1), localName)",
        dwDesiredAccess,
        Name[0]);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400040e4  mov     [rsp+arg_8], rbx
0x1400040e9  mov     [rsp+arg_10], rbp
0x1400040ee  push    rsi
0x1400040ef  push    rdi
0x1400040f0  push    r12
0x1400040f2  push    r14
0x1400040f4  push    r15
0x1400040f6  sub     rsp, 250h
0x1400040fd  mov     rax, cs:__security_cookie
0x140004104  xor     rax, rsp
0x140004107  mov     [rsp+278h+var_38], rax
0x14000410f  mov     rax, 0C000000000000000h
0x140004119  mov     rbp, r9
0x14000411c  mov     r8, rdx
0x14000411f  mov     rbx, rcx
0x140004122  test    rax, r9
0x140004125  jnz     loc_140004330
0x14000412b  xor     r12d, r12d
0x14000412e  lea     rax, [rsp+278h+Name]
0x140004133  mov     ecx, 7FFFFFFEh
0x140004138  mov     edx, 104h
0x14000413d  lea     esi, [r12+1]
0x140004142  test    rcx, rcx
0x140004145  jz      short loc_140004165
0x140004147  movzx   r9d, word ptr [r8]
0x14000414b  test    r9w, r9w
0x14000414f  jz      short loc_140004165
0x140004151  mov     [rax], r9w
0x140004155  add     r8, 2
0x140004159  add     rax, 2
0x14000415d  sub     rcx, rsi
0x140004160  sub     rdx, rsi; unsigned __int64
0x140004163  jnz     short loc_140004142
0x140004165  test    rdx, rdx
0x140004168  lea     rcx, [rax-2]
0x14000416c  lea     r8, aP0; "_p0"
0x140004173  cmovnz  rcx, rax
0x140004177  mov     [rcx], r12w
0x14000417b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004180  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004185  mov     edx, ebp
0x140004187  mov     dword ptr [rsp+278h+dwDesiredAccess], 1F0003h; char *
0x14000418f  and     edx, 7FFFFFFFh; lInitialCount
0x140004195  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14000419a  mov     r8d, esi
0x14000419d  lea     r9, [rsp+278h+Name]; lpName
0x1400041a2  cmova   r8d, edx; lMaximumCount
0x1400041a6  xor     ecx, ecx; lpSemaphoreAttributes
0x1400041a8  call    cs:__imp_CreateSemaphoreExW
0x1400041ae  mov     r15, rax
0x1400041b1  test    rax, rax
0x1400041b4  jnz     short loc_1400041F8
0x1400041b6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400041bb  mov     edi, eax
0x1400041bd  test    eax, eax
0x1400041bf  jns     short loc_14000422C
0x1400041c1  mov     rcx, [rsp+278h]; this
0x1400041c9  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x1400041d0  mov     dword ptr [rsp+278h+dwDesiredAccess], eax; wil::details *
0x1400041d4  lea     r8, aWil; "wil"
0x1400041db  lea     rax, aMSemaphoreCrea; "m_semaphore.create(static_cast<LONG>(lo"...
0x1400041e2  mov     edx, 8Bh; void *
0x1400041e7  mov     qword ptr [rsp+278h+dwFlags], rax; char *
0x1400041ec  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1400041f1  mov     eax, edi
0x1400041f3  jmp     loc_1400042DE
0x1400041f8  call    cs:__imp_GetLastError
0x1400041fe  mov     rdi, [rbx]
0x140004201  test    rdi, rdi
0x140004204  jz      short loc_140004229
0x140004206  call    cs:__imp_GetLastError
0x14000420c  mov     rcx, rdi; hObject
0x14000420f  mov     r14d, eax
0x140004212  call    cs:__imp_CloseHandle
0x140004218  test    eax, eax
0x14000421a  jz      loc_140004336
0x140004220  mov     ecx, r14d; dwErrCode
0x140004223  call    cs:__imp_SetLastError
0x140004229  mov     [rbx], r15
0x14000422c  lea     r8, asc_14000CD5C; "h"
0x140004233  shr     rbp, 1Fh
0x140004237  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000423c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004241  test    ebp, ebp
0x140004243  mov     dword ptr [rsp+278h+dwDesiredAccess], 1F0003h; char *
0x14000424b  lea     r9, [rsp+278h+Name]; lpName
0x140004250  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004255  cmovnz  esi, ebp
0x140004258  mov     edx, ebp; lInitialCount
0x14000425a  mov     r8d, esi; lMaximumCount
0x14000425d  xor     ecx, ecx; lpSemaphoreAttributes
0x14000425f  call    cs:__imp_CreateSemaphoreExW
0x140004265  mov     rsi, rax
0x140004268  test    rax, rax
0x14000426b  jnz     short loc_1400042AC
0x14000426d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004272  mov     ebx, eax
0x140004274  test    eax, eax
0x140004276  jns     short loc_1400042DC
0x140004278  mov     rcx, [rsp+278h]; this
0x140004280  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x140004287  mov     dword ptr [rsp+278h+dwDesiredAccess], eax; wil::details *
0x14000428b  lea     r8, aWil; "wil"
0x140004292  lea     rax, aMSemaphorehigh; "m_semaphoreHigh.create(static_cast<LONG"...
0x140004299  mov     edx, 90h; void *
0x14000429e  mov     qword ptr [rsp+278h+dwFlags], rax; char *
0x1400042a3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1400042a8  mov     eax, ebx
0x1400042aa  jmp     short loc_1400042DE
0x1400042ac  call    cs:__imp_GetLastError
0x1400042b2  mov     rdi, [rbx+8]
0x1400042b6  test    rdi, rdi
0x1400042b9  jz      short loc_1400042D8
0x1400042bb  call    cs:__imp_GetLastError
0x1400042c1  mov     rcx, rdi; hObject
0x1400042c4  mov     ebp, eax
0x1400042c6  call    cs:__imp_CloseHandle
0x1400042cc  test    eax, eax
0x1400042ce  jz      short loc_14000430A
0x1400042d0  mov     ecx, ebp; dwErrCode
0x1400042d2  call    cs:__imp_SetLastError
0x1400042d8  mov     [rbx+8], rsi
0x1400042dc  xor     eax, eax
0x1400042de  mov     rcx, [rsp+278h+var_38]
0x1400042e6  xor     rcx, rsp; StackCookie
0x1400042e9  call    __security_check_cookie
0x1400042ee  lea     r11, [rsp+278h+var_28]
0x1400042f6  mov     rbx, [r11+38h]
0x1400042fa  mov     rbp, [r11+40h]
0x1400042fe  mov     rsp, r11
0x140004301  pop     r15
0x140004303  pop     r14
0x140004305  pop     r12
0x140004307  pop     rdi
0x140004308  pop     rsi
0x140004309  retn
0x14000430a  mov     rcx, [rsp+278h]; this
0x140004312  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140004319  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140004320  mov     qword ptr [rsp+278h+dwFlags], rax; char *
0x140004325  mov     edx, 0A0Bh; void *
0x14000432a  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140004330  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
0x140004336  mov     rcx, [rsp+278h]; this
0x14000433e  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140004345  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14000434c  mov     qword ptr [rsp+278h+dwFlags], rax; char *
0x140004351  mov     edx, 0A0Bh; void *
0x140004356  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
```
