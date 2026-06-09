# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003474`
- end: `0x140003681`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400030b0`
- `0x1400063bc`

## callees

- `0x140003474`
- `0x140003e48`
- `0x140004ce0`
- `0x140004ffc`
- `0x1400054ec`
- `0x1400054fc`
- `0x1400134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003538`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400035d4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003538`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400035d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000361d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000361d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000356d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000357b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400035f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000356d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000357b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400035f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003611`

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
0x140003474  mov     [rsp+arg_8], rbx
0x140003479  mov     [rsp+arg_10], rbp
0x14000347e  push    rsi
0x14000347f  push    rdi
0x140003480  push    r12
0x140003482  push    r14
0x140003484  push    r15
0x140003486  sub     rsp, 250h
0x14000348d  mov     rax, cs:__security_cookie
0x140003494  xor     rax, rsp
0x140003497  mov     [rsp+278h+var_38], rax
0x14000349f  mov     rax, 0C000000000000000h
0x1400034a9  mov     rbp, r9
0x1400034ac  mov     r8, rdx
0x1400034af  mov     rdi, rcx
0x1400034b2  test    rax, r9
0x1400034b5  jnz     loc_140003668
0x1400034bb  xor     r12d, r12d
0x1400034be  lea     rax, [rsp+278h+Name]
0x1400034c3  mov     ecx, 7FFFFFFEh
0x1400034c8  mov     edx, 104h
0x1400034cd  lea     esi, [r12+1]
0x1400034d2  test    rcx, rcx
0x1400034d5  jz      short loc_1400034F5
0x1400034d7  movzx   r9d, word ptr [r8]
0x1400034db  test    r9w, r9w
0x1400034df  jz      short loc_1400034F5
0x1400034e1  mov     [rax], r9w
0x1400034e5  add     r8, 2
0x1400034e9  add     rax, 2
0x1400034ed  sub     rcx, rsi
0x1400034f0  sub     rdx, rsi; unsigned __int64
0x1400034f3  jnz     short loc_1400034D2
0x1400034f5  test    rdx, rdx
0x1400034f8  lea     rcx, [rax-2]
0x1400034fc  lea     r8, aP0; "_p0"
0x140003503  cmovnz  rcx, rax
0x140003507  mov     [rcx], r12w
0x14000350b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003510  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003515  mov     edx, ebp
0x140003517  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000351f  and     edx, 7FFFFFFFh; lInitialCount
0x140003525  mov     [rsp+278h+dwFlags], r12d; int
0x14000352a  mov     r8d, esi
0x14000352d  lea     r9, [rsp+278h+Name]; lpName
0x140003532  cmova   r8d, edx; lMaximumCount
0x140003536  xor     ecx, ecx; lpSemaphoreAttributes
0x140003538  call    cs:__imp_CreateSemaphoreExW
0x14000353e  mov     r15, rax
0x140003541  test    rax, rax
0x140003544  jnz     short loc_14000356D
0x140003546  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000354b  mov     ebx, eax
0x14000354d  test    eax, eax
0x14000354f  jns     short loc_1400035A1
0x140003551  mov     edx, 8Bh; void *
0x140003556  mov     rcx, [rsp+278h]; this
0x14000355e  mov     r9d, ebx; char *
0x140003561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003566  mov     eax, ebx
0x140003568  jmp     loc_140003629
0x14000356d  call    cs:__imp_GetLastError
0x140003573  mov     rbx, [rdi]
0x140003576  test    rbx, rbx
0x140003579  jz      short loc_14000359E
0x14000357b  call    cs:__imp_GetLastError
0x140003581  mov     rcx, rbx; hObject
0x140003584  mov     r14d, eax
0x140003587  call    cs:__imp_CloseHandle
0x14000358d  test    eax, eax
0x14000358f  jz      loc_14000366E
0x140003595  mov     ecx, r14d; dwErrCode
0x140003598  call    cs:__imp_SetLastError
0x14000359e  mov     [rdi], r15
0x1400035a1  lea     r8, asc_140015AC8; "h"
0x1400035a8  shr     rbp, 1Fh
0x1400035ac  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400035b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400035b6  test    ebp, ebp
0x1400035b8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400035c0  lea     r9, [rsp+278h+Name]; lpName
0x1400035c5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1400035ca  cmovnz  esi, ebp
0x1400035cd  mov     edx, ebp; lInitialCount
0x1400035cf  mov     r8d, esi; lMaximumCount
0x1400035d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400035d4  call    cs:__imp_CreateSemaphoreExW
0x1400035da  mov     rsi, rax
0x1400035dd  test    rax, rax
0x1400035e0  jnz     short loc_1400035F7
0x1400035e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400035e7  mov     ebx, eax
0x1400035e9  test    eax, eax
0x1400035eb  jns     short loc_140003627
0x1400035ed  mov     edx, 90h
0x1400035f2  jmp     loc_140003556
0x1400035f7  call    cs:__imp_GetLastError
0x1400035fd  mov     rbx, [rdi+8]
0x140003601  test    rbx, rbx
0x140003604  jz      short loc_140003623
0x140003606  call    cs:__imp_GetLastError
0x14000360c  mov     rcx, rbx; hObject
0x14000360f  mov     ebp, eax
0x140003611  call    cs:__imp_CloseHandle
0x140003617  test    eax, eax
0x140003619  jz      short loc_140003655
0x14000361b  mov     ecx, ebp; dwErrCode
0x14000361d  call    cs:__imp_SetLastError
0x140003623  mov     [rdi+8], rsi
0x140003627  xor     eax, eax
0x140003629  mov     rcx, [rsp+278h+var_38]
0x140003631  xor     rcx, rsp; StackCookie
0x140003634  call    __security_check_cookie
0x140003639  lea     r11, [rsp+278h+var_28]
0x140003641  mov     rbx, [r11+38h]
0x140003645  mov     rbp, [r11+40h]
0x140003649  mov     rsp, r11
0x14000364c  pop     r15
0x14000364e  pop     r14
0x140003650  pop     r12
0x140003652  pop     rdi
0x140003653  pop     rsi
0x140003654  retn
0x140003655  mov     rcx, [rsp+278h]; this
0x14000365d  mov     edx, 0A0Bh; void *
0x140003662  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003668  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000366e  mov     rcx, [rsp+278h]; this
0x140003676  mov     edx, 0A0Bh; void *
0x14000367b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
