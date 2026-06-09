# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007e20`
- end: `0x18000809a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bc4`
- `0x180003f94`

## callees

- `0x180001ac0`
- `0x180005520`
- `0x180007414`
- `0x180007434`
- `0x18000784c`
- `0x180007e20`
- `0x1800086fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007eb4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f30`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007eb4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fe0`

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
0x180007e20  push    rbp
0x180007e22  push    rbx
0x180007e23  push    rsi
0x180007e24  push    rdi
0x180007e25  push    r14
0x180007e27  push    r15
0x180007e29  lea     rbp, [rsp-158h]
0x180007e31  sub     rsp, 258h
0x180007e38  mov     rax, cs:__security_cookie
0x180007e3f  xor     rax, rsp
0x180007e42  mov     [rbp+180h+var_40], rax
0x180007e49  xor     r15d, r15d
0x180007e4c  lea     rax, [rsp+280h+Name]
0x180007e51  mov     [r8], r15
0x180007e54  mov     r14, r8
0x180007e57  mov     edx, 104h
0x180007e5c  mov     r9d, 7FFFFFFEh
0x180007e62  test    r9, r9
0x180007e65  jz      short loc_180007E86
0x180007e67  movzx   r8d, word ptr [rcx]
0x180007e6b  test    r8w, r8w
0x180007e6f  jz      short loc_180007E86
0x180007e71  mov     [rax], r8w
0x180007e75  add     rcx, 2
0x180007e79  add     rax, 2
0x180007e7d  dec     r9
0x180007e80  sub     rdx, 1; unsigned __int64
0x180007e84  jnz     short loc_180007E62
0x180007e86  test    rdx, rdx
0x180007e89  lea     rcx, [rax-2]
0x180007e8d  lea     r8, aP0; "_p0"
0x180007e94  cmovnz  rcx, rax
0x180007e98  mov     [rcx], r15w
0x180007e9c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007ea1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007ea6  mov     esi, 1F0003h
0x180007eab  lea     r8, [rsp+280h+Name]; lpName
0x180007eb0  mov     ecx, esi; dwDesiredAccess
0x180007eb2  xor     edx, edx; bInheritHandle
0x180007eb4  call    cs:__imp_OpenSemaphoreW
0x180007eba  mov     rbx, rax
0x180007ebd  test    rax, rax
0x180007ec0  jz      loc_180007FEF
0x180007ec6  lea     rdx, [rsp+280h+var_25C]; int *
0x180007ecb  mov     [rsp+280h+var_25C], r15d
0x180007ed0  mov     rcx, rax; hHandle
0x180007ed3  mov     [rsp+280h+var_260], r15d; int
0x180007ed8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007edd  mov     edi, eax
0x180007edf  test    eax, eax
0x180007ee1  jns     short loc_180007F16
0x180007ee3  mov     rcx, [rbp+188h]; this
0x180007eea  lea     r8, aWil; "wil"
0x180007ef1  mov     r9d, eax; char *
0x180007ef4  mov     edx, 0D6h; void *
0x180007ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007efe  mov     rcx, rbx; hObject
0x180007f01  call    cs:__imp_CloseHandle
0x180007f07  test    eax, eax
0x180007f09  jz      loc_180008064
0x180007f0f  mov     eax, edi
0x180007f11  jmp     loc_18000800F
0x180007f16  lea     r8, asc_180026CE0; "h"
0x180007f1d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007f22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f27  lea     r8, [rsp+280h+Name]; lpName
0x180007f2c  xor     edx, edx; bInheritHandle
0x180007f2e  mov     ecx, esi; dwDesiredAccess
0x180007f30  call    cs:__imp_OpenSemaphoreW
0x180007f36  mov     rdi, rax
0x180007f39  test    rax, rax
0x180007f3c  jz      loc_180007FCA
0x180007f42  lea     rdx, [rsp+280h+var_260]; int *
0x180007f47  mov     rcx, rax; hHandle
0x180007f4a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007f4f  mov     esi, eax
0x180007f51  test    eax, eax
0x180007f53  jns     short loc_180007F96
0x180007f55  mov     rcx, [rbp+188h]; this
0x180007f5c  lea     r8, aWil; "wil"
0x180007f63  mov     r9d, eax; char *
0x180007f66  mov     edx, 0DEh; void *
0x180007f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f70  mov     rcx, rdi; hObject
0x180007f73  call    cs:__imp_CloseHandle
0x180007f79  test    eax, eax
0x180007f7b  jz      loc_180008076
0x180007f81  mov     rcx, rbx; hObject
0x180007f84  call    cs:__imp_CloseHandle
0x180007f8a  test    eax, eax
0x180007f8c  jz      loc_180008088
0x180007f92  mov     eax, esi
0x180007f94  jmp     short loc_18000800F
0x180007f96  mov     rcx, rdi; hObject
0x180007f99  call    cs:__imp_CloseHandle
0x180007f9f  test    eax, eax
0x180007fa1  jz      loc_18000802E
0x180007fa7  movsxd  rax, [rsp+280h+var_25C]
0x180007fac  movsxd  rcx, [rsp+280h+var_260]
0x180007fb1  shl     rcx, 1Fh
0x180007fb5  or      rcx, rax
0x180007fb8  mov     [r14], rcx
0x180007fbb  mov     rcx, rbx; hObject
0x180007fbe  call    cs:__imp_CloseHandle
0x180007fc4  test    eax, eax
0x180007fc6  jz      short loc_180008040
0x180007fc8  jmp     short loc_180007FFA
0x180007fca  mov     rcx, [rbp+188h]; this
0x180007fd1  mov     edx, 0DCh; void *
0x180007fd6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007fdb  mov     rcx, rbx; hObject
0x180007fde  mov     edi, eax
0x180007fe0  call    cs:__imp_CloseHandle
0x180007fe6  test    eax, eax
0x180007fe8  jz      short loc_180008052
0x180007fea  jmp     loc_180007F0F
0x180007fef  call    cs:__imp_GetLastError
0x180007ff5  cmp     eax, 2
0x180007ff8  jnz     short loc_180007FFE
0x180007ffa  xor     eax, eax
0x180007ffc  jmp     short loc_18000800F
0x180007ffe  mov     rcx, [rbp+188h]; this
0x180008005  mov     edx, 0D0h; void *
0x18000800a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000800f  mov     rcx, [rbp+180h+var_40]
0x180008016  xor     rcx, rsp; StackCookie
0x180008019  call    __security_check_cookie
0x18000801e  add     rsp, 258h
0x180008025  pop     r15
0x180008027  pop     r14
0x180008029  pop     rdi
0x18000802a  pop     rsi
0x18000802b  pop     rbx
0x18000802c  pop     rbp
0x18000802d  retn
0x18000802e  mov     rcx, [rbp+188h]; this
0x180008035  mov     edx, 0A0Bh; void *
0x18000803a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008040  mov     rcx, [rbp+188h]; this
0x180008047  mov     edx, 0A0Bh; void *
0x18000804c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008052  mov     rcx, [rbp+188h]; this
0x180008059  mov     edx, 0A0Bh; void *
0x18000805e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008064  mov     rcx, [rbp+188h]; this
0x18000806b  mov     edx, 0A0Bh; void *
0x180008070  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008076  mov     rcx, [rbp+188h]; this
0x18000807d  mov     edx, 0A0Bh; void *
0x180008082  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008088  mov     rcx, [rbp+188h]; this
0x18000808f  mov     edx, 0A0Bh; void *
0x180008094  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
