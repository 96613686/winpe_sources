# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140008824`
- end: `0x140008a4e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140008448`

## callees

- `0x1400054c0`
- `0x140008824`
- `0x14000914c`
- `0x14000a6b4`
- `0x14000b01c`
- `0x14000c54c`
- `0x14000c55c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400088e8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000898b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400088e8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000898b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000894f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400089ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000894f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400089ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400089d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000893e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000893e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089de`

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
0x140008824  mov     [rsp+arg_8], rbx
0x140008829  mov     [rsp+arg_10], rbp
0x14000882e  push    rsi
0x14000882f  push    rdi
0x140008830  push    r12
0x140008832  push    r14
0x140008834  push    r15
0x140008836  sub     rsp, 250h
0x14000883d  mov     rax, cs:__security_cookie
0x140008844  xor     rax, rsp
0x140008847  mov     [rsp+278h+var_38], rax
0x14000884f  mov     rax, 0C000000000000000h
0x140008859  mov     rbp, r9
0x14000885c  mov     r8, rdx
0x14000885f  mov     rbx, rcx
0x140008862  test    rax, r9
0x140008865  jnz     loc_140008A35
0x14000886b  xor     r12d, r12d
0x14000886e  lea     rax, [rsp+278h+Name]
0x140008873  mov     ecx, 7FFFFFFEh
0x140008878  mov     edx, 104h
0x14000887d  lea     esi, [r12+1]
0x140008882  test    rcx, rcx
0x140008885  jz      short loc_1400088A5
0x140008887  movzx   r9d, word ptr [r8]
0x14000888b  test    r9w, r9w
0x14000888f  jz      short loc_1400088A5
0x140008891  mov     [rax], r9w
0x140008895  add     r8, 2
0x140008899  add     rax, 2
0x14000889d  sub     rcx, rsi
0x1400088a0  sub     rdx, rsi; unsigned __int64
0x1400088a3  jnz     short loc_140008882
0x1400088a5  test    rdx, rdx
0x1400088a8  lea     rcx, [rax-2]
0x1400088ac  lea     r8, aP0; "_p0"
0x1400088b3  cmovnz  rcx, rax
0x1400088b7  mov     [rcx], r12w
0x1400088bb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400088c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400088c5  mov     edx, ebp
0x1400088c7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400088cf  and     edx, 7FFFFFFFh; lInitialCount
0x1400088d5  mov     [rsp+278h+dwFlags], r12d; int
0x1400088da  mov     r8d, esi
0x1400088dd  lea     r9, [rsp+278h+Name]; lpName
0x1400088e2  cmova   r8d, edx; lMaximumCount
0x1400088e6  xor     ecx, ecx; lpSemaphoreAttributes
0x1400088e8  call    cs:__imp_CreateSemaphoreExW
0x1400088ee  mov     r15, rax
0x1400088f1  test    rax, rax
0x1400088f4  jnz     short loc_140008924
0x1400088f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400088fb  mov     edi, eax
0x1400088fd  test    eax, eax
0x1400088ff  jns     short loc_140008958
0x140008901  mov     rcx, [rsp+278h]; this
0x140008909  lea     r8, aWil; "wil"
0x140008910  mov     r9d, eax; char *
0x140008913  mov     edx, 8Bh; void *
0x140008918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000891d  mov     eax, edi
0x14000891f  jmp     loc_1400089F6
0x140008924  call    cs:__imp_GetLastError
0x14000892a  mov     rdi, [rbx]
0x14000892d  test    rdi, rdi
0x140008930  jz      short loc_140008955
0x140008932  call    cs:__imp_GetLastError
0x140008938  mov     rcx, rdi; hObject
0x14000893b  mov     r14d, eax
0x14000893e  call    cs:__imp_CloseHandle
0x140008944  test    eax, eax
0x140008946  jz      loc_140008A3B
0x14000894c  mov     ecx, r14d; dwErrCode
0x14000894f  call    cs:__imp_SetLastError
0x140008955  mov     [rbx], r15
0x140008958  lea     r8, asc_14007ACA8; "h"
0x14000895f  shr     rbp, 1Fh
0x140008963  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140008968  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000896d  test    ebp, ebp
0x14000896f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140008977  lea     r9, [rsp+278h+Name]; lpName
0x14000897c  mov     [rsp+278h+dwFlags], r12d; int
0x140008981  cmovnz  esi, ebp
0x140008984  mov     edx, ebp; lInitialCount
0x140008986  mov     r8d, esi; lMaximumCount
0x140008989  xor     ecx, ecx; lpSemaphoreAttributes
0x14000898b  call    cs:__imp_CreateSemaphoreExW
0x140008991  mov     rsi, rax
0x140008994  test    rax, rax
0x140008997  jnz     short loc_1400089C4
0x140008999  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000899e  mov     ebx, eax
0x1400089a0  test    eax, eax
0x1400089a2  jns     short loc_1400089F4
0x1400089a4  mov     rcx, [rsp+278h]; this
0x1400089ac  lea     r8, aWil; "wil"
0x1400089b3  mov     r9d, eax; char *
0x1400089b6  mov     edx, 90h; void *
0x1400089bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400089c0  mov     eax, ebx
0x1400089c2  jmp     short loc_1400089F6
0x1400089c4  call    cs:__imp_GetLastError
0x1400089ca  mov     rdi, [rbx+8]
0x1400089ce  test    rdi, rdi
0x1400089d1  jz      short loc_1400089F0
0x1400089d3  call    cs:__imp_GetLastError
0x1400089d9  mov     rcx, rdi; hObject
0x1400089dc  mov     ebp, eax
0x1400089de  call    cs:__imp_CloseHandle
0x1400089e4  test    eax, eax
0x1400089e6  jz      short loc_140008A22
0x1400089e8  mov     ecx, ebp; dwErrCode
0x1400089ea  call    cs:__imp_SetLastError
0x1400089f0  mov     [rbx+8], rsi
0x1400089f4  xor     eax, eax
0x1400089f6  mov     rcx, [rsp+278h+var_38]
0x1400089fe  xor     rcx, rsp; StackCookie
0x140008a01  call    __security_check_cookie
0x140008a06  lea     r11, [rsp+278h+var_28]
0x140008a0e  mov     rbx, [r11+38h]
0x140008a12  mov     rbp, [r11+40h]
0x140008a16  mov     rsp, r11
0x140008a19  pop     r15
0x140008a1b  pop     r14
0x140008a1d  pop     r12
0x140008a1f  pop     rdi
0x140008a20  pop     rsi
0x140008a21  retn
0x140008a22  mov     rcx, [rsp+278h]; this
0x140008a2a  mov     edx, 0A0Bh; void *
0x140008a2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a35  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008a3b  mov     rcx, [rsp+278h]; this
0x140008a43  mov     edx, 0A0Bh; void *
0x140008a48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
