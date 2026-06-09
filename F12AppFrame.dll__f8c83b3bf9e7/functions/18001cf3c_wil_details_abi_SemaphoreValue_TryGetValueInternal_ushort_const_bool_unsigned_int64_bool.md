# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001cf3c`
- end: `0x18001d1b6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001928c`

## callees

- `0x180001800`
- `0x18001a524`
- `0x18001c4a4`
- `0x18001c4c4`
- `0x18001cdd4`
- `0x18001cf3c`
- `0x18001e15c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001d01d`
- `KERNEL32!CloseHandle` at `0x18001d08f`
- `KERNEL32!CloseHandle` at `0x18001d0a0`
- `KERNEL32!CloseHandle` at `0x18001d0b5`
- `KERNEL32!CloseHandle` at `0x18001d0da`
- `KERNEL32!CloseHandle` at `0x18001d0fc`
- `KERNEL32!CloseHandle` at `0x18001d01d`
- `KERNEL32!CloseHandle` at `0x18001d08f`
- `KERNEL32!CloseHandle` at `0x18001d0a0`
- `KERNEL32!CloseHandle` at `0x18001d0b5`
- `KERNEL32!CloseHandle` at `0x18001d0da`
- `KERNEL32!CloseHandle` at `0x18001d0fc`
- `KERNEL32!GetLastError` at `0x18001d10b`
- `KERNEL32!GetLastError` at `0x18001d10b`
- `KERNEL32!OpenSemaphoreW` at `0x18001cfd0`
- `KERNEL32!OpenSemaphoreW` at `0x18001d04c`
- `KERNEL32!OpenSemaphoreW` at `0x18001cfd0`
- `KERNEL32!OpenSemaphoreW` at `0x18001d04c`

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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18001cf3c  push    rbp
0x18001cf3e  push    rbx
0x18001cf3f  push    rsi
0x18001cf40  push    rdi
0x18001cf41  push    r14
0x18001cf43  push    r15
0x18001cf45  lea     rbp, [rsp-158h]
0x18001cf4d  sub     rsp, 258h
0x18001cf54  mov     rax, cs:__security_cookie
0x18001cf5b  xor     rax, rsp
0x18001cf5e  mov     [rbp+180h+var_40], rax
0x18001cf65  xor     r15d, r15d
0x18001cf68  lea     rax, [rsp+280h+Name]
0x18001cf6d  mov     [r8], r15
0x18001cf70  mov     r14, r8
0x18001cf73  mov     edx, 104h
0x18001cf78  mov     r9d, 7FFFFFFEh
0x18001cf7e  test    r9, r9
0x18001cf81  jz      short loc_18001CFA2
0x18001cf83  movzx   r8d, word ptr [rcx]
0x18001cf87  test    r8w, r8w
0x18001cf8b  jz      short loc_18001CFA2
0x18001cf8d  mov     [rax], r8w
0x18001cf91  add     rcx, 2
0x18001cf95  add     rax, 2
0x18001cf99  dec     r9
0x18001cf9c  sub     rdx, 1; unsigned __int64
0x18001cfa0  jnz     short loc_18001CF7E
0x18001cfa2  test    rdx, rdx
0x18001cfa5  lea     rcx, [rax-2]
0x18001cfa9  lea     r8, aP0; "_p0"
0x18001cfb0  cmovnz  rcx, rax
0x18001cfb4  mov     [rcx], r15w
0x18001cfb8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001cfbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cfc2  mov     esi, 1F0003h
0x18001cfc7  lea     r8, [rsp+280h+Name]; lpName
0x18001cfcc  mov     ecx, esi; dwDesiredAccess
0x18001cfce  xor     edx, edx; bInheritHandle
0x18001cfd0  call    cs:__imp_OpenSemaphoreW
0x18001cfd6  mov     rbx, rax
0x18001cfd9  test    rax, rax
0x18001cfdc  jz      loc_18001D10B
0x18001cfe2  lea     rdx, [rsp+280h+var_25C]; int *
0x18001cfe7  mov     [rsp+280h+var_25C], r15d
0x18001cfec  mov     rcx, rax; hHandle
0x18001cfef  mov     [rsp+280h+var_260], r15d; int
0x18001cff4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cff9  mov     edi, eax
0x18001cffb  test    eax, eax
0x18001cffd  jns     short loc_18001D032
0x18001cfff  mov     rcx, [rbp+188h]; this
0x18001d006  lea     r8, aWil; "wil"
0x18001d00d  mov     r9d, eax; char *
0x18001d010  mov     edx, 0D6h; void *
0x18001d015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d01a  mov     rcx, rbx; hObject
0x18001d01d  call    cs:__imp_CloseHandle
0x18001d023  test    eax, eax
0x18001d025  jz      loc_18001D180
0x18001d02b  mov     eax, edi
0x18001d02d  jmp     loc_18001D12B
0x18001d032  lea     r8, asc_18003AD70; "h"
0x18001d039  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001d03e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d043  lea     r8, [rsp+280h+Name]; lpName
0x18001d048  xor     edx, edx; bInheritHandle
0x18001d04a  mov     ecx, esi; dwDesiredAccess
0x18001d04c  call    cs:__imp_OpenSemaphoreW
0x18001d052  mov     rdi, rax
0x18001d055  test    rax, rax
0x18001d058  jz      loc_18001D0E6
0x18001d05e  lea     rdx, [rsp+280h+var_260]; int *
0x18001d063  mov     rcx, rax; hHandle
0x18001d066  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d06b  mov     esi, eax
0x18001d06d  test    eax, eax
0x18001d06f  jns     short loc_18001D0B2
0x18001d071  mov     rcx, [rbp+188h]; this
0x18001d078  lea     r8, aWil; "wil"
0x18001d07f  mov     r9d, eax; char *
0x18001d082  mov     edx, 0DEh; void *
0x18001d087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d08c  mov     rcx, rdi; hObject
0x18001d08f  call    cs:__imp_CloseHandle
0x18001d095  test    eax, eax
0x18001d097  jz      loc_18001D192
0x18001d09d  mov     rcx, rbx; hObject
0x18001d0a0  call    cs:__imp_CloseHandle
0x18001d0a6  test    eax, eax
0x18001d0a8  jz      loc_18001D1A4
0x18001d0ae  mov     eax, esi
0x18001d0b0  jmp     short loc_18001D12B
0x18001d0b2  mov     rcx, rdi; hObject
0x18001d0b5  call    cs:__imp_CloseHandle
0x18001d0bb  test    eax, eax
0x18001d0bd  jz      loc_18001D14A
0x18001d0c3  movsxd  rax, [rsp+280h+var_25C]
0x18001d0c8  movsxd  rcx, [rsp+280h+var_260]
0x18001d0cd  shl     rcx, 1Fh
0x18001d0d1  or      rcx, rax
0x18001d0d4  mov     [r14], rcx
0x18001d0d7  mov     rcx, rbx; hObject
0x18001d0da  call    cs:__imp_CloseHandle
0x18001d0e0  test    eax, eax
0x18001d0e2  jz      short loc_18001D15C
0x18001d0e4  jmp     short loc_18001D116
0x18001d0e6  mov     rcx, [rbp+188h]; this
0x18001d0ed  mov     edx, 0DCh; void *
0x18001d0f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d0f7  mov     rcx, rbx; hObject
0x18001d0fa  mov     edi, eax
0x18001d0fc  call    cs:__imp_CloseHandle
0x18001d102  test    eax, eax
0x18001d104  jz      short loc_18001D16E
0x18001d106  jmp     loc_18001D02B
0x18001d10b  call    cs:__imp_GetLastError
0x18001d111  cmp     eax, 2
0x18001d114  jnz     short loc_18001D11A
0x18001d116  xor     eax, eax
0x18001d118  jmp     short loc_18001D12B
0x18001d11a  mov     rcx, [rbp+188h]; this
0x18001d121  mov     edx, 0D0h; void *
0x18001d126  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d12b  mov     rcx, [rbp+180h+var_40]
0x18001d132  xor     rcx, rsp; StackCookie
0x18001d135  call    __security_check_cookie
0x18001d13a  add     rsp, 258h
0x18001d141  pop     r15
0x18001d143  pop     r14
0x18001d145  pop     rdi
0x18001d146  pop     rsi
0x18001d147  pop     rbx
0x18001d148  pop     rbp
0x18001d149  retn
0x18001d14a  mov     rcx, [rbp+188h]; this
0x18001d151  mov     edx, 0A0Bh; void *
0x18001d156  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d15c  mov     rcx, [rbp+188h]; this
0x18001d163  mov     edx, 0A0Bh; void *
0x18001d168  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d16e  mov     rcx, [rbp+188h]; this
0x18001d175  mov     edx, 0A0Bh; void *
0x18001d17a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d180  mov     rcx, [rbp+188h]; this
0x18001d187  mov     edx, 0A0Bh; void *
0x18001d18c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d192  mov     rcx, [rbp+188h]; this
0x18001d199  mov     edx, 0A0Bh; void *
0x18001d19e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d1a4  mov     rcx, [rbp+188h]; this
0x18001d1ab  mov     edx, 0A0Bh; void *
0x18001d1b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
