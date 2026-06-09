# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800060e0`
- end: `0x1800062ed`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000596c`
- `0x180005d10`

## callees

- `0x1800060e0`
- `0x180006e68`
- `0x180008cf0`
- `0x180009110`
- `0x180009c9c`
- `0x180009cac`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800061a4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006240`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800061a4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006240`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000627d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000627d`

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
0x1800060e0  mov     [rsp+arg_8], rbx
0x1800060e5  mov     [rsp+arg_10], rbp
0x1800060ea  push    rsi
0x1800060eb  push    rdi
0x1800060ec  push    r12
0x1800060ee  push    r14
0x1800060f0  push    r15
0x1800060f2  sub     rsp, 250h
0x1800060f9  mov     rax, cs:__security_cookie
0x180006100  xor     rax, rsp
0x180006103  mov     [rsp+278h+var_38], rax
0x18000610b  mov     rax, 0C000000000000000h
0x180006115  mov     rbp, r9
0x180006118  mov     r8, rdx
0x18000611b  mov     rdi, rcx
0x18000611e  test    rax, r9
0x180006121  jnz     loc_1800062D4
0x180006127  xor     r12d, r12d
0x18000612a  lea     rax, [rsp+278h+Name]
0x18000612f  mov     ecx, 7FFFFFFEh
0x180006134  mov     edx, 104h
0x180006139  lea     esi, [r12+1]
0x18000613e  test    rcx, rcx
0x180006141  jz      short loc_180006161
0x180006143  movzx   r9d, word ptr [r8]
0x180006147  test    r9w, r9w
0x18000614b  jz      short loc_180006161
0x18000614d  mov     [rax], r9w
0x180006151  add     r8, 2
0x180006155  add     rax, 2
0x180006159  sub     rcx, rsi
0x18000615c  sub     rdx, rsi; unsigned __int64
0x18000615f  jnz     short loc_18000613E
0x180006161  test    rdx, rdx
0x180006164  lea     rcx, [rax-2]
0x180006168  lea     r8, aP0; "_p0"
0x18000616f  cmovnz  rcx, rax
0x180006173  mov     [rcx], r12w
0x180006177  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000617c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006181  mov     edx, ebp
0x180006183  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000618b  and     edx, 7FFFFFFFh; lInitialCount
0x180006191  mov     [rsp+278h+dwFlags], r12d; int
0x180006196  mov     r8d, esi
0x180006199  lea     r9, [rsp+278h+Name]; lpName
0x18000619e  cmova   r8d, edx; lMaximumCount
0x1800061a2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800061a4  call    cs:__imp_CreateSemaphoreExW
0x1800061aa  mov     r15, rax
0x1800061ad  test    rax, rax
0x1800061b0  jnz     short loc_1800061D9
0x1800061b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800061b7  mov     ebx, eax
0x1800061b9  test    eax, eax
0x1800061bb  jns     short loc_18000620D
0x1800061bd  mov     edx, 8Bh; void *
0x1800061c2  mov     rcx, [rsp+278h]; this
0x1800061ca  mov     r9d, ebx; char *
0x1800061cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061d2  mov     eax, ebx
0x1800061d4  jmp     loc_180006295
0x1800061d9  call    cs:__imp_GetLastError
0x1800061df  mov     rbx, [rdi]
0x1800061e2  test    rbx, rbx
0x1800061e5  jz      short loc_18000620A
0x1800061e7  call    cs:__imp_GetLastError
0x1800061ed  mov     rcx, rbx; hObject
0x1800061f0  mov     r14d, eax
0x1800061f3  call    cs:__imp_CloseHandle
0x1800061f9  test    eax, eax
0x1800061fb  jz      loc_1800062DA
0x180006201  mov     ecx, r14d; dwErrCode
0x180006204  call    cs:__imp_SetLastError
0x18000620a  mov     [rdi], r15
0x18000620d  lea     r8, asc_18000E800; "h"
0x180006214  shr     rbp, 1Fh
0x180006218  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000621d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006222  test    ebp, ebp
0x180006224  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000622c  lea     r9, [rsp+278h+Name]; lpName
0x180006231  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180006236  cmovnz  esi, ebp
0x180006239  mov     edx, ebp; lInitialCount
0x18000623b  mov     r8d, esi; lMaximumCount
0x18000623e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006240  call    cs:__imp_CreateSemaphoreExW
0x180006246  mov     rsi, rax
0x180006249  test    rax, rax
0x18000624c  jnz     short loc_180006263
0x18000624e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006253  mov     ebx, eax
0x180006255  test    eax, eax
0x180006257  jns     short loc_180006293
0x180006259  mov     edx, 90h
0x18000625e  jmp     loc_1800061C2
0x180006263  call    cs:__imp_GetLastError
0x180006269  mov     rbx, [rdi+8]
0x18000626d  test    rbx, rbx
0x180006270  jz      short loc_18000628F
0x180006272  call    cs:__imp_GetLastError
0x180006278  mov     rcx, rbx; hObject
0x18000627b  mov     ebp, eax
0x18000627d  call    cs:__imp_CloseHandle
0x180006283  test    eax, eax
0x180006285  jz      short loc_1800062C1
0x180006287  mov     ecx, ebp; dwErrCode
0x180006289  call    cs:__imp_SetLastError
0x18000628f  mov     [rdi+8], rsi
0x180006293  xor     eax, eax
0x180006295  mov     rcx, [rsp+278h+var_38]
0x18000629d  xor     rcx, rsp; StackCookie
0x1800062a0  call    __security_check_cookie
0x1800062a5  lea     r11, [rsp+278h+var_28]
0x1800062ad  mov     rbx, [r11+38h]
0x1800062b1  mov     rbp, [r11+40h]
0x1800062b5  mov     rsp, r11
0x1800062b8  pop     r15
0x1800062ba  pop     r14
0x1800062bc  pop     r12
0x1800062be  pop     rdi
0x1800062bf  pop     rsi
0x1800062c0  retn
0x1800062c1  mov     rcx, [rsp+278h]; this
0x1800062c9  mov     edx, 0A0Bh; void *
0x1800062ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800062da  mov     rcx, [rsp+278h]; this
0x1800062e2  mov     edx, 0A0Bh; void *
0x1800062e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
