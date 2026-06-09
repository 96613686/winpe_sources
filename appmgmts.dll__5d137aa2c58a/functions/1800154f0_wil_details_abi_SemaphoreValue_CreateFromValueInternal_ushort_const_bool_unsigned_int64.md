# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800154f0`
- end: `0x180015713`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014d7c`
- `0x180015120`

## callees

- `0x1800016d0`
- `0x18000cc10`
- `0x1800154f0`
- `0x180016298`
- `0x1800181b4`
- `0x1800196ac`
- `0x1800196bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001568a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001568a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015699`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800156b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800156b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156a4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800155b9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015658`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800155b9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015658`

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
0x1800154f0  mov     [rsp+arg_8], rbx
0x1800154f5  push    rbp
0x1800154f6  push    rsi
0x1800154f7  push    rdi
0x1800154f8  push    r12
0x1800154fa  push    r13
0x1800154fc  push    r14
0x1800154fe  push    r15
0x180015500  sub     rsp, 250h
0x180015507  mov     rax, cs:__security_cookie
0x18001550e  xor     rax, rsp
0x180015511  mov     [rsp+288h+var_48], rax
0x180015519  mov     rax, 0C000000000000000h
0x180015523  mov     rsi, r9
0x180015526  mov     r8, rdx
0x180015529  mov     rbx, rcx
0x18001552c  test    rax, r9
0x18001552f  jnz     loc_1800156FA
0x180015535  xor     r12d, r12d
0x180015538  lea     rax, [rsp+288h+Name]
0x18001553d  mov     r13d, 104h
0x180015543  mov     ecx, 7FFFFFFEh
0x180015548  mov     edx, r13d
0x18001554b  lea     ebp, [r12+1]
0x180015550  test    rcx, rcx
0x180015553  jz      short loc_180015573
0x180015555  movzx   r9d, word ptr [r8]
0x180015559  test    r9w, r9w
0x18001555d  jz      short loc_180015573
0x18001555f  mov     [rax], r9w
0x180015563  add     r8, 2
0x180015567  add     rax, 2
0x18001556b  sub     rcx, rbp
0x18001556e  sub     rdx, rbp
0x180015571  jnz     short loc_180015550
0x180015573  test    rdx, rdx
0x180015576  lea     rcx, [rax-2]
0x18001557a  lea     r8, aP0; "_p0"
0x180015581  mov     rdx, r13; unsigned __int64
0x180015584  cmovnz  rcx, rax
0x180015588  mov     [rcx], r12w
0x18001558c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180015591  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015596  mov     edx, esi
0x180015598  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800155a0  and     edx, 7FFFFFFFh; lInitialCount
0x1800155a6  mov     [rsp+288h+dwFlags], r12d; int
0x1800155ab  mov     r8d, ebp
0x1800155ae  lea     r9, [rsp+288h+Name]; lpName
0x1800155b3  cmova   r8d, edx; lMaximumCount
0x1800155b7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800155b9  call    cs:__imp_CreateSemaphoreExW
0x1800155bf  mov     r15, rax
0x1800155c2  test    rax, rax
0x1800155c5  jnz     short loc_1800155EE
0x1800155c7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800155cc  mov     edi, eax
0x1800155ce  test    eax, eax
0x1800155d0  jns     short loc_180015622
0x1800155d2  mov     rcx, [rsp+288h]; this
0x1800155da  mov     r9d, eax; char *
0x1800155dd  mov     edx, 8Bh; void *
0x1800155e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155e7  mov     eax, edi
0x1800155e9  jmp     loc_1800156BC
0x1800155ee  call    cs:__imp_GetLastError
0x1800155f4  mov     rdi, [rbx]
0x1800155f7  test    rdi, rdi
0x1800155fa  jz      short loc_18001561F
0x1800155fc  call    cs:__imp_GetLastError
0x180015602  mov     rcx, rdi; hObject
0x180015605  mov     r14d, eax
0x180015608  call    cs:__imp_CloseHandle
0x18001560e  test    eax, eax
0x180015610  jz      loc_180015700
0x180015616  mov     ecx, r14d; dwErrCode
0x180015619  call    cs:__imp_SetLastError
0x18001561f  mov     [rbx], r15
0x180015622  lea     r8, asc_1800306E0; "h"
0x180015629  shr     rsi, 1Fh
0x18001562d  mov     rdx, r13; unsigned __int64
0x180015630  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180015635  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001563a  test    esi, esi
0x18001563c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180015644  lea     r9, [rsp+288h+Name]; lpName
0x180015649  mov     [rsp+288h+dwFlags], r12d; int
0x18001564e  cmovnz  ebp, esi
0x180015651  mov     edx, esi; lInitialCount
0x180015653  mov     r8d, ebp; lMaximumCount
0x180015656  xor     ecx, ecx; lpSemaphoreAttributes
0x180015658  call    cs:__imp_CreateSemaphoreExW
0x18001565e  mov     rbp, rax
0x180015661  test    rax, rax
0x180015664  jnz     short loc_18001568A
0x180015666  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001566b  mov     ebx, eax
0x18001566d  test    eax, eax
0x18001566f  jns     short loc_1800156BA
0x180015671  mov     rcx, [rsp+288h]; this
0x180015679  mov     r9d, eax; char *
0x18001567c  mov     edx, 90h; void *
0x180015681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015686  mov     eax, ebx
0x180015688  jmp     short loc_1800156BC
0x18001568a  call    cs:__imp_GetLastError
0x180015690  mov     rdi, [rbx+8]
0x180015694  test    rdi, rdi
0x180015697  jz      short loc_1800156B6
0x180015699  call    cs:__imp_GetLastError
0x18001569f  mov     rcx, rdi; hObject
0x1800156a2  mov     esi, eax
0x1800156a4  call    cs:__imp_CloseHandle
0x1800156aa  test    eax, eax
0x1800156ac  jz      short loc_1800156E7
0x1800156ae  mov     ecx, esi; dwErrCode
0x1800156b0  call    cs:__imp_SetLastError
0x1800156b6  mov     [rbx+8], rbp
0x1800156ba  xor     eax, eax
0x1800156bc  mov     rcx, [rsp+288h+var_48]
0x1800156c4  xor     rcx, rsp; StackCookie
0x1800156c7  call    __security_check_cookie
0x1800156cc  mov     rbx, [rsp+288h+arg_8]
0x1800156d4  add     rsp, 250h
0x1800156db  pop     r15
0x1800156dd  pop     r14
0x1800156df  pop     r13
0x1800156e1  pop     r12
0x1800156e3  pop     rdi
0x1800156e4  pop     rsi
0x1800156e5  pop     rbp
0x1800156e6  retn
0x1800156e7  mov     rcx, [rsp+288h]; this
0x1800156ef  mov     edx, 0A0Bh; void *
0x1800156f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800156fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015700  mov     rcx, [rsp+288h]; this
0x180015708  mov     edx, 0A0Bh; void *
0x18001570d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
