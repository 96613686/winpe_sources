# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x14000aea4`
- end: `0x14000b0ce`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000aac8`
- `0x14001373c`

## callees

- `0x140008660`
- `0x14000aea4`
- `0x14000b7e8`
- `0x14000c434`
- `0x14000cd74`
- `0x14000d2dc`
- `0x14000d2ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000af68`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000b00b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000af68`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000b00b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000afcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b06a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000afcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b06a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000afbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b05e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000afbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b05e`

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
0x14000aea4  mov     [rsp+arg_8], rbx
0x14000aea9  mov     [rsp+arg_10], rbp
0x14000aeae  push    rsi
0x14000aeaf  push    rdi
0x14000aeb0  push    r12
0x14000aeb2  push    r14
0x14000aeb4  push    r15
0x14000aeb6  sub     rsp, 250h
0x14000aebd  mov     rax, cs:__security_cookie
0x14000aec4  xor     rax, rsp
0x14000aec7  mov     [rsp+278h+var_38], rax
0x14000aecf  mov     rax, 0C000000000000000h
0x14000aed9  mov     rbp, r9
0x14000aedc  mov     r8, rdx
0x14000aedf  mov     rbx, rcx
0x14000aee2  test    rax, r9
0x14000aee5  jnz     loc_14000B0B5
0x14000aeeb  xor     r12d, r12d
0x14000aeee  lea     rax, [rsp+278h+Name]
0x14000aef3  mov     ecx, 7FFFFFFEh
0x14000aef8  mov     edx, 104h
0x14000aefd  lea     esi, [r12+1]
0x14000af02  test    rcx, rcx
0x14000af05  jz      short loc_14000AF25
0x14000af07  movzx   r9d, word ptr [r8]
0x14000af0b  test    r9w, r9w
0x14000af0f  jz      short loc_14000AF25
0x14000af11  mov     [rax], r9w
0x14000af15  add     r8, 2
0x14000af19  add     rax, 2
0x14000af1d  sub     rcx, rsi
0x14000af20  sub     rdx, rsi; unsigned __int64
0x14000af23  jnz     short loc_14000AF02
0x14000af25  test    rdx, rdx
0x14000af28  lea     rcx, [rax-2]
0x14000af2c  lea     r8, aP0; "_p0"
0x14000af33  cmovnz  rcx, rax
0x14000af37  mov     [rcx], r12w
0x14000af3b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000af40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000af45  mov     edx, ebp
0x14000af47  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000af4f  and     edx, 7FFFFFFFh; lInitialCount
0x14000af55  mov     [rsp+278h+dwFlags], r12d; int
0x14000af5a  mov     r8d, esi
0x14000af5d  lea     r9, [rsp+278h+Name]; lpName
0x14000af62  cmova   r8d, edx; lMaximumCount
0x14000af66  xor     ecx, ecx; lpSemaphoreAttributes
0x14000af68  call    cs:__imp_CreateSemaphoreExW
0x14000af6e  mov     r15, rax
0x14000af71  test    rax, rax
0x14000af74  jnz     short loc_14000AFA4
0x14000af76  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000af7b  mov     edi, eax
0x14000af7d  test    eax, eax
0x14000af7f  jns     short loc_14000AFD8
0x14000af81  mov     rcx, [rsp+278h]; this
0x14000af89  lea     r8, aWil; "wil"
0x14000af90  mov     r9d, eax; char *
0x14000af93  mov     edx, 8Bh; void *
0x14000af98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000af9d  mov     eax, edi
0x14000af9f  jmp     loc_14000B076
0x14000afa4  call    cs:__imp_GetLastError
0x14000afaa  mov     rdi, [rbx]
0x14000afad  test    rdi, rdi
0x14000afb0  jz      short loc_14000AFD5
0x14000afb2  call    cs:__imp_GetLastError
0x14000afb8  mov     rcx, rdi; hObject
0x14000afbb  mov     r14d, eax
0x14000afbe  call    cs:__imp_CloseHandle
0x14000afc4  test    eax, eax
0x14000afc6  jz      loc_14000B0BB
0x14000afcc  mov     ecx, r14d; dwErrCode
0x14000afcf  call    cs:__imp_SetLastError
0x14000afd5  mov     [rbx], r15
0x14000afd8  lea     r8, asc_14001C728; "h"
0x14000afdf  shr     rbp, 1Fh
0x14000afe3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000afe8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000afed  test    ebp, ebp
0x14000afef  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000aff7  lea     r9, [rsp+278h+Name]; lpName
0x14000affc  mov     [rsp+278h+dwFlags], r12d; int
0x14000b001  cmovnz  esi, ebp
0x14000b004  mov     edx, ebp; lInitialCount
0x14000b006  mov     r8d, esi; lMaximumCount
0x14000b009  xor     ecx, ecx; lpSemaphoreAttributes
0x14000b00b  call    cs:__imp_CreateSemaphoreExW
0x14000b011  mov     rsi, rax
0x14000b014  test    rax, rax
0x14000b017  jnz     short loc_14000B044
0x14000b019  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000b01e  mov     ebx, eax
0x14000b020  test    eax, eax
0x14000b022  jns     short loc_14000B074
0x14000b024  mov     rcx, [rsp+278h]; this
0x14000b02c  lea     r8, aWil; "wil"
0x14000b033  mov     r9d, eax; char *
0x14000b036  mov     edx, 90h; void *
0x14000b03b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b040  mov     eax, ebx
0x14000b042  jmp     short loc_14000B076
0x14000b044  call    cs:__imp_GetLastError
0x14000b04a  mov     rdi, [rbx+8]
0x14000b04e  test    rdi, rdi
0x14000b051  jz      short loc_14000B070
0x14000b053  call    cs:__imp_GetLastError
0x14000b059  mov     rcx, rdi; hObject
0x14000b05c  mov     ebp, eax
0x14000b05e  call    cs:__imp_CloseHandle
0x14000b064  test    eax, eax
0x14000b066  jz      short loc_14000B0A2
0x14000b068  mov     ecx, ebp; dwErrCode
0x14000b06a  call    cs:__imp_SetLastError
0x14000b070  mov     [rbx+8], rsi
0x14000b074  xor     eax, eax
0x14000b076  mov     rcx, [rsp+278h+var_38]
0x14000b07e  xor     rcx, rsp; StackCookie
0x14000b081  call    __security_check_cookie
0x14000b086  lea     r11, [rsp+278h+var_28]
0x14000b08e  mov     rbx, [r11+38h]
0x14000b092  mov     rbp, [r11+40h]
0x14000b096  mov     rsp, r11
0x14000b099  pop     r15
0x14000b09b  pop     r14
0x14000b09d  pop     r12
0x14000b09f  pop     rdi
0x14000b0a0  pop     rsi
0x14000b0a1  retn
0x14000b0a2  mov     rcx, [rsp+278h]; this
0x14000b0aa  mov     edx, 0A0Bh; void *
0x14000b0af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b0b5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000b0bb  mov     rcx, [rsp+278h]; this
0x14000b0c3  mov     edx, 0A0Bh; void *
0x14000b0c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
