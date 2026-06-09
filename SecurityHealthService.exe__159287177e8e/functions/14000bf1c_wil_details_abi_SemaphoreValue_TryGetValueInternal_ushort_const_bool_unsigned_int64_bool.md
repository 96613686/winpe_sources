# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000bf1c`
- end: `0x14000c196`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008718`
- `0x140008ae8`

## callees

- `0x1400015d0`
- `0x140006bcc`
- `0x140006bec`
- `0x140006c10`
- `0x140009c50`
- `0x14000bf1c`
- `0x14000c620`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000c0eb`
- `KERNEL32!GetLastError` at `0x14000c0eb`
- `KERNEL32!CloseHandle` at `0x14000bffd`
- `KERNEL32!CloseHandle` at `0x14000c06f`
- `KERNEL32!CloseHandle` at `0x14000c080`
- `KERNEL32!CloseHandle` at `0x14000c095`
- `KERNEL32!CloseHandle` at `0x14000c0ba`
- `KERNEL32!CloseHandle` at `0x14000c0dc`
- `KERNEL32!CloseHandle` at `0x14000bffd`
- `KERNEL32!CloseHandle` at `0x14000c06f`
- `KERNEL32!CloseHandle` at `0x14000c080`
- `KERNEL32!CloseHandle` at `0x14000c095`
- `KERNEL32!CloseHandle` at `0x14000c0ba`
- `KERNEL32!CloseHandle` at `0x14000c0dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bfb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c02c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bfb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c02c`

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
0x14000bf1c  push    rbp
0x14000bf1e  push    rbx
0x14000bf1f  push    rsi
0x14000bf20  push    rdi
0x14000bf21  push    r14
0x14000bf23  push    r15
0x14000bf25  lea     rbp, [rsp-158h]
0x14000bf2d  sub     rsp, 258h
0x14000bf34  mov     rax, cs:__security_cookie
0x14000bf3b  xor     rax, rsp
0x14000bf3e  mov     [rbp+180h+var_40], rax
0x14000bf45  xor     r15d, r15d
0x14000bf48  lea     rax, [rsp+280h+Name]
0x14000bf4d  mov     [r8], r15
0x14000bf50  mov     r14, r8
0x14000bf53  mov     edx, 104h
0x14000bf58  mov     r9d, 7FFFFFFEh
0x14000bf5e  test    r9, r9
0x14000bf61  jz      short loc_14000BF82
0x14000bf63  movzx   r8d, word ptr [rcx]
0x14000bf67  test    r8w, r8w
0x14000bf6b  jz      short loc_14000BF82
0x14000bf6d  mov     [rax], r8w
0x14000bf71  add     rcx, 2
0x14000bf75  add     rax, 2
0x14000bf79  dec     r9
0x14000bf7c  sub     rdx, 1; unsigned __int64
0x14000bf80  jnz     short loc_14000BF5E
0x14000bf82  test    rdx, rdx
0x14000bf85  lea     rcx, [rax-2]
0x14000bf89  lea     r8, aP0; "_p0"
0x14000bf90  cmovnz  rcx, rax
0x14000bf94  mov     [rcx], r15w
0x14000bf98  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000bf9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000bfa2  mov     esi, 1F0003h
0x14000bfa7  lea     r8, [rsp+280h+Name]; lpName
0x14000bfac  mov     ecx, esi; dwDesiredAccess
0x14000bfae  xor     edx, edx; bInheritHandle
0x14000bfb0  call    cs:__imp_OpenSemaphoreW
0x14000bfb6  mov     rbx, rax
0x14000bfb9  test    rax, rax
0x14000bfbc  jz      loc_14000C0EB
0x14000bfc2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000bfc7  mov     [rsp+280h+var_25C], r15d
0x14000bfcc  mov     rcx, rax; hHandle
0x14000bfcf  mov     [rsp+280h+var_260], r15d; int
0x14000bfd4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000bfd9  mov     edi, eax
0x14000bfdb  test    eax, eax
0x14000bfdd  jns     short loc_14000C012
0x14000bfdf  mov     rcx, [rbp+188h]; this
0x14000bfe6  lea     r8, aWil; "wil"
0x14000bfed  mov     r9d, eax; char *
0x14000bff0  mov     edx, 0D6h; void *
0x14000bff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bffa  mov     rcx, rbx; hObject
0x14000bffd  call    cs:__imp_CloseHandle
0x14000c003  test    eax, eax
0x14000c005  jz      loc_14000C160
0x14000c00b  mov     eax, edi
0x14000c00d  jmp     loc_14000C10B
0x14000c012  lea     r8, asc_140015EC0; "h"
0x14000c019  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c01e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c023  lea     r8, [rsp+280h+Name]; lpName
0x14000c028  xor     edx, edx; bInheritHandle
0x14000c02a  mov     ecx, esi; dwDesiredAccess
0x14000c02c  call    cs:__imp_OpenSemaphoreW
0x14000c032  mov     rdi, rax
0x14000c035  test    rax, rax
0x14000c038  jz      loc_14000C0C6
0x14000c03e  lea     rdx, [rsp+280h+var_260]; int *
0x14000c043  mov     rcx, rax; hHandle
0x14000c046  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c04b  mov     esi, eax
0x14000c04d  test    eax, eax
0x14000c04f  jns     short loc_14000C092
0x14000c051  mov     rcx, [rbp+188h]; this
0x14000c058  lea     r8, aWil; "wil"
0x14000c05f  mov     r9d, eax; char *
0x14000c062  mov     edx, 0DEh; void *
0x14000c067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c06c  mov     rcx, rdi; hObject
0x14000c06f  call    cs:__imp_CloseHandle
0x14000c075  test    eax, eax
0x14000c077  jz      loc_14000C172
0x14000c07d  mov     rcx, rbx; hObject
0x14000c080  call    cs:__imp_CloseHandle
0x14000c086  test    eax, eax
0x14000c088  jz      loc_14000C184
0x14000c08e  mov     eax, esi
0x14000c090  jmp     short loc_14000C10B
0x14000c092  mov     rcx, rdi; hObject
0x14000c095  call    cs:__imp_CloseHandle
0x14000c09b  test    eax, eax
0x14000c09d  jz      loc_14000C12A
0x14000c0a3  movsxd  rax, [rsp+280h+var_25C]
0x14000c0a8  movsxd  rcx, [rsp+280h+var_260]
0x14000c0ad  shl     rcx, 1Fh
0x14000c0b1  or      rcx, rax
0x14000c0b4  mov     [r14], rcx
0x14000c0b7  mov     rcx, rbx; hObject
0x14000c0ba  call    cs:__imp_CloseHandle
0x14000c0c0  test    eax, eax
0x14000c0c2  jz      short loc_14000C13C
0x14000c0c4  jmp     short loc_14000C0F6
0x14000c0c6  mov     rcx, [rbp+188h]; this
0x14000c0cd  mov     edx, 0DCh; void *
0x14000c0d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c0d7  mov     rcx, rbx; hObject
0x14000c0da  mov     edi, eax
0x14000c0dc  call    cs:__imp_CloseHandle
0x14000c0e2  test    eax, eax
0x14000c0e4  jz      short loc_14000C14E
0x14000c0e6  jmp     loc_14000C00B
0x14000c0eb  call    cs:__imp_GetLastError
0x14000c0f1  cmp     eax, 2
0x14000c0f4  jnz     short loc_14000C0FA
0x14000c0f6  xor     eax, eax
0x14000c0f8  jmp     short loc_14000C10B
0x14000c0fa  mov     rcx, [rbp+188h]; this
0x14000c101  mov     edx, 0D0h; void *
0x14000c106  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c10b  mov     rcx, [rbp+180h+var_40]
0x14000c112  xor     rcx, rsp; StackCookie
0x14000c115  call    __security_check_cookie
0x14000c11a  add     rsp, 258h
0x14000c121  pop     r15
0x14000c123  pop     r14
0x14000c125  pop     rdi
0x14000c126  pop     rsi
0x14000c127  pop     rbx
0x14000c128  pop     rbp
0x14000c129  retn
0x14000c12a  mov     rcx, [rbp+188h]; this
0x14000c131  mov     edx, 0A0Bh; void *
0x14000c136  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c13c  mov     rcx, [rbp+188h]; this
0x14000c143  mov     edx, 0A0Bh; void *
0x14000c148  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c14e  mov     rcx, [rbp+188h]; this
0x14000c155  mov     edx, 0A0Bh; void *
0x14000c15a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c160  mov     rcx, [rbp+188h]; this
0x14000c167  mov     edx, 0A0Bh; void *
0x14000c16c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c172  mov     rcx, [rbp+188h]; this
0x14000c179  mov     edx, 0A0Bh; void *
0x14000c17e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c184  mov     rcx, [rbp+188h]; this
0x14000c18b  mov     edx, 0A0Bh; void *
0x14000c190  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
