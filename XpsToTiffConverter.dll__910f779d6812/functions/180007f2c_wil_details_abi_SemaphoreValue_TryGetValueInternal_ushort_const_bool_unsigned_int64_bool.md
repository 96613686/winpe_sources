# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007f2c`
- end: `0x180008198`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ab8`
- `0x180003e5c`

## callees

- `0x1800016a0`
- `0x1800052d4`
- `0x1800070a4`
- `0x1800070c4`
- `0x180007b08`
- `0x180007f2c`
- `0x18000871c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007fc0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008035`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007fc0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008097`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008097`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080de`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180007f2c  push    rbp
0x180007f2e  push    rbx
0x180007f2f  push    rsi
0x180007f30  push    rdi
0x180007f31  push    r14
0x180007f33  push    r15
0x180007f35  lea     rbp, [rsp-158h]
0x180007f3d  sub     rsp, 258h
0x180007f44  mov     rax, cs:__security_cookie
0x180007f4b  xor     rax, rsp
0x180007f4e  mov     [rbp+180h+var_40], rax
0x180007f55  xor     r15d, r15d
0x180007f58  lea     rax, [rsp+280h+Name]
0x180007f5d  mov     [r8], r15
0x180007f60  mov     r14, r8
0x180007f63  mov     edx, 104h
0x180007f68  mov     r9d, 7FFFFFFEh
0x180007f6e  test    r9, r9
0x180007f71  jz      short loc_180007F92
0x180007f73  movzx   r8d, word ptr [rcx]
0x180007f77  test    r8w, r8w
0x180007f7b  jz      short loc_180007F92
0x180007f7d  mov     [rax], r8w
0x180007f81  add     rcx, 2
0x180007f85  add     rax, 2
0x180007f89  dec     r9
0x180007f8c  sub     rdx, 1; unsigned __int64
0x180007f90  jnz     short loc_180007F6E
0x180007f92  test    rdx, rdx
0x180007f95  lea     rcx, [rax-2]
0x180007f99  lea     r8, aP0; "_p0"
0x180007fa0  cmovnz  rcx, rax
0x180007fa4  mov     [rcx], r15w
0x180007fa8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007fad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007fb2  mov     esi, 1F0003h
0x180007fb7  lea     r8, [rsp+280h+Name]; lpName
0x180007fbc  mov     ecx, esi; dwDesiredAccess
0x180007fbe  xor     edx, edx; bInheritHandle
0x180007fc0  call    cs:__imp_OpenSemaphoreW
0x180007fc6  mov     rbx, rax
0x180007fc9  test    rax, rax
0x180007fcc  jz      loc_1800080ED
0x180007fd2  lea     rdx, [rsp+280h+var_25C]; int *
0x180007fd7  mov     [rsp+280h+var_25C], r15d
0x180007fdc  mov     rcx, rax; hHandle
0x180007fdf  mov     [rsp+280h+var_260], r15d; int
0x180007fe4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007fe9  mov     edi, eax
0x180007feb  test    eax, eax
0x180007fed  jns     short loc_18000801B
0x180007fef  mov     rcx, [rbp+188h]; this
0x180007ff6  mov     r9d, eax; char *
0x180007ff9  mov     edx, 0D6h; void *
0x180007ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008003  mov     rcx, rbx; hObject
0x180008006  call    cs:__imp_CloseHandle
0x18000800c  test    eax, eax
0x18000800e  jz      loc_180008162
0x180008014  mov     eax, edi
0x180008016  jmp     loc_18000810D
0x18000801b  lea     r8, asc_18000FEB0; "h"
0x180008022  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008027  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000802c  lea     r8, [rsp+280h+Name]; lpName
0x180008031  xor     edx, edx; bInheritHandle
0x180008033  mov     ecx, esi; dwDesiredAccess
0x180008035  call    cs:__imp_OpenSemaphoreW
0x18000803b  mov     rdi, rax
0x18000803e  test    rax, rax
0x180008041  jz      loc_1800080C8
0x180008047  lea     rdx, [rsp+280h+var_260]; int *
0x18000804c  mov     rcx, rax; hHandle
0x18000804f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008054  mov     esi, eax
0x180008056  test    eax, eax
0x180008058  jns     short loc_180008094
0x18000805a  mov     rcx, [rbp+188h]; this
0x180008061  mov     r9d, eax; char *
0x180008064  mov     edx, 0DEh; void *
0x180008069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000806e  mov     rcx, rdi; hObject
0x180008071  call    cs:__imp_CloseHandle
0x180008077  test    eax, eax
0x180008079  jz      loc_180008174
0x18000807f  mov     rcx, rbx; hObject
0x180008082  call    cs:__imp_CloseHandle
0x180008088  test    eax, eax
0x18000808a  jz      loc_180008186
0x180008090  mov     eax, esi
0x180008092  jmp     short loc_18000810D
0x180008094  mov     rcx, rdi; hObject
0x180008097  call    cs:__imp_CloseHandle
0x18000809d  test    eax, eax
0x18000809f  jz      loc_18000812C
0x1800080a5  movsxd  rax, [rsp+280h+var_25C]
0x1800080aa  movsxd  rcx, [rsp+280h+var_260]
0x1800080af  shl     rcx, 1Fh
0x1800080b3  or      rcx, rax
0x1800080b6  mov     [r14], rcx
0x1800080b9  mov     rcx, rbx; hObject
0x1800080bc  call    cs:__imp_CloseHandle
0x1800080c2  test    eax, eax
0x1800080c4  jz      short loc_18000813E
0x1800080c6  jmp     short loc_1800080F8
0x1800080c8  mov     rcx, [rbp+188h]; this
0x1800080cf  mov     edx, 0DCh; void *
0x1800080d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800080d9  mov     rcx, rbx; hObject
0x1800080dc  mov     edi, eax
0x1800080de  call    cs:__imp_CloseHandle
0x1800080e4  test    eax, eax
0x1800080e6  jz      short loc_180008150
0x1800080e8  jmp     loc_180008014
0x1800080ed  call    cs:__imp_GetLastError
0x1800080f3  cmp     eax, 2
0x1800080f6  jnz     short loc_1800080FC
0x1800080f8  xor     eax, eax
0x1800080fa  jmp     short loc_18000810D
0x1800080fc  mov     rcx, [rbp+188h]; this
0x180008103  mov     edx, 0D0h; void *
0x180008108  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000810d  mov     rcx, [rbp+180h+var_40]
0x180008114  xor     rcx, rsp; StackCookie
0x180008117  call    __security_check_cookie
0x18000811c  add     rsp, 258h
0x180008123  pop     r15
0x180008125  pop     r14
0x180008127  pop     rdi
0x180008128  pop     rsi
0x180008129  pop     rbx
0x18000812a  pop     rbp
0x18000812b  retn
0x18000812c  mov     rcx, [rbp+188h]; this
0x180008133  mov     edx, 0A0Bh; void *
0x180008138  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000813e  mov     rcx, [rbp+188h]; this
0x180008145  mov     edx, 0A0Bh; void *
0x18000814a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008150  mov     rcx, [rbp+188h]; this
0x180008157  mov     edx, 0A0Bh; void *
0x18000815c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008162  mov     rcx, [rbp+188h]; this
0x180008169  mov     edx, 0A0Bh; void *
0x18000816e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008174  mov     rcx, [rbp+188h]; this
0x18000817b  mov     edx, 0A0Bh; void *
0x180008180  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008186  mov     rcx, [rbp+188h]; this
0x18000818d  mov     edx, 0A0Bh; void *
0x180008192  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
