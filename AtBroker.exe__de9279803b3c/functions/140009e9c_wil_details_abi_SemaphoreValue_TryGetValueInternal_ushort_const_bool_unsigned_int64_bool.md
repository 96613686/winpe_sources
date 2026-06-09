# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140009e9c`
- end: `0x14000a116`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400040c8`
- `0x140004498`

## callees

- `0x1400064b8`
- `0x140009364`
- `0x140009384`
- `0x1400099f8`
- `0x140009e9c`
- `0x14000a774`
- `0x140015b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a06b`
- `KERNEL32!GetLastError` at `0x14000a06b`
- `KERNEL32!OpenSemaphoreW` at `0x140009f30`
- `KERNEL32!OpenSemaphoreW` at `0x140009fac`
- `KERNEL32!OpenSemaphoreW` at `0x140009f30`
- `KERNEL32!OpenSemaphoreW` at `0x140009fac`
- `KERNEL32!CloseHandle` at `0x140009f7d`
- `KERNEL32!CloseHandle` at `0x140009fef`
- `KERNEL32!CloseHandle` at `0x14000a000`
- `KERNEL32!CloseHandle` at `0x14000a015`
- `KERNEL32!CloseHandle` at `0x14000a03a`
- `KERNEL32!CloseHandle` at `0x14000a05c`
- `KERNEL32!CloseHandle` at `0x140009f7d`
- `KERNEL32!CloseHandle` at `0x140009fef`
- `KERNEL32!CloseHandle` at `0x14000a000`
- `KERNEL32!CloseHandle` at `0x14000a015`
- `KERNEL32!CloseHandle` at `0x14000a03a`
- `KERNEL32!CloseHandle` at `0x14000a05c`

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
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x140009e9c  push    rbp
0x140009e9e  push    rbx
0x140009e9f  push    rsi
0x140009ea0  push    rdi
0x140009ea1  push    r14
0x140009ea3  push    r15
0x140009ea5  lea     rbp, [rsp-158h]
0x140009ead  sub     rsp, 258h
0x140009eb4  mov     rax, cs:__security_cookie
0x140009ebb  xor     rax, rsp
0x140009ebe  mov     [rbp+180h+var_40], rax
0x140009ec5  xor     r15d, r15d
0x140009ec8  lea     rax, [rsp+280h+Name]
0x140009ecd  mov     [r8], r15
0x140009ed0  mov     r14, r8
0x140009ed3  mov     edx, 104h
0x140009ed8  mov     r9d, 7FFFFFFEh
0x140009ede  test    r9, r9
0x140009ee1  jz      short loc_140009F02
0x140009ee3  movzx   r8d, word ptr [rcx]
0x140009ee7  test    r8w, r8w
0x140009eeb  jz      short loc_140009F02
0x140009eed  mov     [rax], r8w
0x140009ef1  add     rcx, 2
0x140009ef5  add     rax, 2
0x140009ef9  dec     r9
0x140009efc  sub     rdx, 1; unsigned __int64
0x140009f00  jnz     short loc_140009EDE
0x140009f02  test    rdx, rdx
0x140009f05  lea     rcx, [rax-2]
0x140009f09  lea     r8, aP0; "_p0"
0x140009f10  cmovnz  rcx, rax
0x140009f14  mov     [rcx], r15w
0x140009f18  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009f1d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009f22  mov     esi, 1F0003h
0x140009f27  lea     r8, [rsp+280h+Name]; lpName
0x140009f2c  mov     ecx, esi; dwDesiredAccess
0x140009f2e  xor     edx, edx; bInheritHandle
0x140009f30  call    cs:__imp_OpenSemaphoreW
0x140009f36  mov     rbx, rax
0x140009f39  test    rax, rax
0x140009f3c  jz      loc_14000A06B
0x140009f42  lea     rdx, [rsp+280h+var_25C]; int *
0x140009f47  mov     [rsp+280h+var_25C], r15d
0x140009f4c  mov     rcx, rax; hHandle
0x140009f4f  mov     [rsp+280h+var_260], r15d; int
0x140009f54  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009f59  mov     edi, eax
0x140009f5b  test    eax, eax
0x140009f5d  jns     short loc_140009F92
0x140009f5f  mov     rcx, [rbp+188h]; this
0x140009f66  lea     r8, aWil; "wil"
0x140009f6d  mov     r9d, eax; char *
0x140009f70  mov     edx, 0D6h; void *
0x140009f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009f7a  mov     rcx, rbx; hObject
0x140009f7d  call    cs:__imp_CloseHandle
0x140009f83  test    eax, eax
0x140009f85  jz      loc_14000A0E0
0x140009f8b  mov     eax, edi
0x140009f8d  jmp     loc_14000A08B
0x140009f92  lea     r8, asc_140018FC0; "h"
0x140009f99  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009f9e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009fa3  lea     r8, [rsp+280h+Name]; lpName
0x140009fa8  xor     edx, edx; bInheritHandle
0x140009faa  mov     ecx, esi; dwDesiredAccess
0x140009fac  call    cs:__imp_OpenSemaphoreW
0x140009fb2  mov     rdi, rax
0x140009fb5  test    rax, rax
0x140009fb8  jz      loc_14000A046
0x140009fbe  lea     rdx, [rsp+280h+var_260]; int *
0x140009fc3  mov     rcx, rax; hHandle
0x140009fc6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009fcb  mov     esi, eax
0x140009fcd  test    eax, eax
0x140009fcf  jns     short loc_14000A012
0x140009fd1  mov     rcx, [rbp+188h]; this
0x140009fd8  lea     r8, aWil; "wil"
0x140009fdf  mov     r9d, eax; char *
0x140009fe2  mov     edx, 0DEh; void *
0x140009fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009fec  mov     rcx, rdi; hObject
0x140009fef  call    cs:__imp_CloseHandle
0x140009ff5  test    eax, eax
0x140009ff7  jz      loc_14000A0F2
0x140009ffd  mov     rcx, rbx; hObject
0x14000a000  call    cs:__imp_CloseHandle
0x14000a006  test    eax, eax
0x14000a008  jz      loc_14000A104
0x14000a00e  mov     eax, esi
0x14000a010  jmp     short loc_14000A08B
0x14000a012  mov     rcx, rdi; hObject
0x14000a015  call    cs:__imp_CloseHandle
0x14000a01b  test    eax, eax
0x14000a01d  jz      loc_14000A0AA
0x14000a023  movsxd  rax, [rsp+280h+var_25C]
0x14000a028  movsxd  rcx, [rsp+280h+var_260]
0x14000a02d  shl     rcx, 1Fh
0x14000a031  or      rcx, rax
0x14000a034  mov     [r14], rcx
0x14000a037  mov     rcx, rbx; hObject
0x14000a03a  call    cs:__imp_CloseHandle
0x14000a040  test    eax, eax
0x14000a042  jz      short loc_14000A0BC
0x14000a044  jmp     short loc_14000A076
0x14000a046  mov     rcx, [rbp+188h]; this
0x14000a04d  mov     edx, 0DCh; void *
0x14000a052  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a057  mov     rcx, rbx; hObject
0x14000a05a  mov     edi, eax
0x14000a05c  call    cs:__imp_CloseHandle
0x14000a062  test    eax, eax
0x14000a064  jz      short loc_14000A0CE
0x14000a066  jmp     loc_140009F8B
0x14000a06b  call    cs:__imp_GetLastError
0x14000a071  cmp     eax, 2
0x14000a074  jnz     short loc_14000A07A
0x14000a076  xor     eax, eax
0x14000a078  jmp     short loc_14000A08B
0x14000a07a  mov     rcx, [rbp+188h]; this
0x14000a081  mov     edx, 0D0h; void *
0x14000a086  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a08b  mov     rcx, [rbp+180h+var_40]
0x14000a092  xor     rcx, rsp; StackCookie
0x14000a095  call    __security_check_cookie
0x14000a09a  add     rsp, 258h
0x14000a0a1  pop     r15
0x14000a0a3  pop     r14
0x14000a0a5  pop     rdi
0x14000a0a6  pop     rsi
0x14000a0a7  pop     rbx
0x14000a0a8  pop     rbp
0x14000a0a9  retn
0x14000a0aa  mov     rcx, [rbp+188h]; this
0x14000a0b1  mov     edx, 0A0Bh; void *
0x14000a0b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0bc  mov     rcx, [rbp+188h]; this
0x14000a0c3  mov     edx, 0A0Bh; void *
0x14000a0c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0ce  mov     rcx, [rbp+188h]; this
0x14000a0d5  mov     edx, 0A0Bh; void *
0x14000a0da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0e0  mov     rcx, [rbp+188h]; this
0x14000a0e7  mov     edx, 0A0Bh; void *
0x14000a0ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0f2  mov     rcx, [rbp+188h]; this
0x14000a0f9  mov     edx, 0A0Bh; void *
0x14000a0fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a104  mov     rcx, [rbp+188h]; this
0x14000a10b  mov     edx, 0A0Bh; void *
0x14000a110  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
