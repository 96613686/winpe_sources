# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007e4c`
- end: `0x1800080b8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bf8`
- `0x180003f9c`

## callees

- `0x1800017c0`
- `0x180005414`
- `0x180006fe4`
- `0x180007004`
- `0x180007a48`
- `0x180007e4c`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007ee0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007ee0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ffe`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180007e4c  push    rbp
0x180007e4e  push    rbx
0x180007e4f  push    rsi
0x180007e50  push    rdi
0x180007e51  push    r14
0x180007e53  push    r15
0x180007e55  lea     rbp, [rsp-158h]
0x180007e5d  sub     rsp, 258h
0x180007e64  mov     rax, cs:__security_cookie
0x180007e6b  xor     rax, rsp
0x180007e6e  mov     [rbp+180h+var_40], rax
0x180007e75  xor     r15d, r15d
0x180007e78  lea     rax, [rsp+280h+Name]
0x180007e7d  mov     [r8], r15
0x180007e80  mov     r14, r8
0x180007e83  mov     edx, 104h
0x180007e88  mov     r9d, 7FFFFFFEh
0x180007e8e  test    r9, r9
0x180007e91  jz      short loc_180007EB2
0x180007e93  movzx   r8d, word ptr [rcx]
0x180007e97  test    r8w, r8w
0x180007e9b  jz      short loc_180007EB2
0x180007e9d  mov     [rax], r8w
0x180007ea1  add     rcx, 2
0x180007ea5  add     rax, 2
0x180007ea9  dec     r9
0x180007eac  sub     rdx, 1; unsigned __int64
0x180007eb0  jnz     short loc_180007E8E
0x180007eb2  test    rdx, rdx
0x180007eb5  lea     rcx, [rax-2]
0x180007eb9  lea     r8, aP0; "_p0"
0x180007ec0  cmovnz  rcx, rax
0x180007ec4  mov     [rcx], r15w
0x180007ec8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007ecd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007ed2  mov     esi, 1F0003h
0x180007ed7  lea     r8, [rsp+280h+Name]; lpName
0x180007edc  mov     ecx, esi; dwDesiredAccess
0x180007ede  xor     edx, edx; bInheritHandle
0x180007ee0  call    cs:__imp_OpenSemaphoreW
0x180007ee6  mov     rbx, rax
0x180007ee9  test    rax, rax
0x180007eec  jz      loc_18000800D
0x180007ef2  lea     rdx, [rsp+280h+var_25C]; int *
0x180007ef7  mov     [rsp+280h+var_25C], r15d
0x180007efc  mov     rcx, rax; hHandle
0x180007eff  mov     [rsp+280h+var_260], r15d; int
0x180007f04  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007f09  mov     edi, eax
0x180007f0b  test    eax, eax
0x180007f0d  jns     short loc_180007F3B
0x180007f0f  mov     rcx, [rbp+188h]; this
0x180007f16  mov     r9d, eax; char *
0x180007f19  mov     edx, 0D6h; void *
0x180007f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f23  mov     rcx, rbx; hObject
0x180007f26  call    cs:__imp_CloseHandle
0x180007f2c  test    eax, eax
0x180007f2e  jz      loc_180008082
0x180007f34  mov     eax, edi
0x180007f36  jmp     loc_18000802D
0x180007f3b  lea     r8, asc_180012A60; "h"
0x180007f42  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007f47  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f4c  lea     r8, [rsp+280h+Name]; lpName
0x180007f51  xor     edx, edx; bInheritHandle
0x180007f53  mov     ecx, esi; dwDesiredAccess
0x180007f55  call    cs:__imp_OpenSemaphoreW
0x180007f5b  mov     rdi, rax
0x180007f5e  test    rax, rax
0x180007f61  jz      loc_180007FE8
0x180007f67  lea     rdx, [rsp+280h+var_260]; int *
0x180007f6c  mov     rcx, rax; hHandle
0x180007f6f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007f74  mov     esi, eax
0x180007f76  test    eax, eax
0x180007f78  jns     short loc_180007FB4
0x180007f7a  mov     rcx, [rbp+188h]; this
0x180007f81  mov     r9d, eax; char *
0x180007f84  mov     edx, 0DEh; void *
0x180007f89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f8e  mov     rcx, rdi; hObject
0x180007f91  call    cs:__imp_CloseHandle
0x180007f97  test    eax, eax
0x180007f99  jz      loc_180008094
0x180007f9f  mov     rcx, rbx; hObject
0x180007fa2  call    cs:__imp_CloseHandle
0x180007fa8  test    eax, eax
0x180007faa  jz      loc_1800080A6
0x180007fb0  mov     eax, esi
0x180007fb2  jmp     short loc_18000802D
0x180007fb4  mov     rcx, rdi; hObject
0x180007fb7  call    cs:__imp_CloseHandle
0x180007fbd  test    eax, eax
0x180007fbf  jz      loc_18000804C
0x180007fc5  movsxd  rax, [rsp+280h+var_25C]
0x180007fca  movsxd  rcx, [rsp+280h+var_260]
0x180007fcf  shl     rcx, 1Fh
0x180007fd3  or      rcx, rax
0x180007fd6  mov     [r14], rcx
0x180007fd9  mov     rcx, rbx; hObject
0x180007fdc  call    cs:__imp_CloseHandle
0x180007fe2  test    eax, eax
0x180007fe4  jz      short loc_18000805E
0x180007fe6  jmp     short loc_180008018
0x180007fe8  mov     rcx, [rbp+188h]; this
0x180007fef  mov     edx, 0DCh; void *
0x180007ff4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007ff9  mov     rcx, rbx; hObject
0x180007ffc  mov     edi, eax
0x180007ffe  call    cs:__imp_CloseHandle
0x180008004  test    eax, eax
0x180008006  jz      short loc_180008070
0x180008008  jmp     loc_180007F34
0x18000800d  call    cs:__imp_GetLastError
0x180008013  cmp     eax, 2
0x180008016  jnz     short loc_18000801C
0x180008018  xor     eax, eax
0x18000801a  jmp     short loc_18000802D
0x18000801c  mov     rcx, [rbp+188h]; this
0x180008023  mov     edx, 0D0h; void *
0x180008028  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000802d  mov     rcx, [rbp+180h+var_40]
0x180008034  xor     rcx, rsp; StackCookie
0x180008037  call    __security_check_cookie
0x18000803c  add     rsp, 258h
0x180008043  pop     r15
0x180008045  pop     r14
0x180008047  pop     rdi
0x180008048  pop     rsi
0x180008049  pop     rbx
0x18000804a  pop     rbp
0x18000804b  retn
0x18000804c  mov     rcx, [rbp+188h]; this
0x180008053  mov     edx, 0A0Bh; void *
0x180008058  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000805e  mov     rcx, [rbp+188h]; this
0x180008065  mov     edx, 0A0Bh; void *
0x18000806a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008070  mov     rcx, [rbp+188h]; this
0x180008077  mov     edx, 0A0Bh; void *
0x18000807c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008082  mov     rcx, [rbp+188h]; this
0x180008089  mov     edx, 0A0Bh; void *
0x18000808e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008094  mov     rcx, [rbp+188h]; this
0x18000809b  mov     edx, 0A0Bh; void *
0x1800080a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800080a6  mov     rcx, [rbp+188h]; this
0x1800080ad  mov     edx, 0A0Bh; void *
0x1800080b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
