# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015d78`
- end: `0x180015fe4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001223c`
- `0x1800125e0`

## callees

- `0x180001630`
- `0x180013a60`
- `0x180015610`
- `0x180015630`
- `0x180015a4c`
- `0x180015d78`
- `0x1800165c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f2a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e0c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e81`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e0c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e81`

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
0x180015d78  push    rbp
0x180015d7a  push    rbx
0x180015d7b  push    rsi
0x180015d7c  push    rdi
0x180015d7d  push    r14
0x180015d7f  push    r15
0x180015d81  lea     rbp, [rsp-158h]
0x180015d89  sub     rsp, 258h
0x180015d90  mov     rax, cs:__security_cookie
0x180015d97  xor     rax, rsp
0x180015d9a  mov     [rbp+180h+var_40], rax
0x180015da1  xor     r15d, r15d
0x180015da4  lea     rax, [rsp+280h+Name]
0x180015da9  mov     [r8], r15
0x180015dac  mov     r14, r8
0x180015daf  mov     edx, 104h
0x180015db4  mov     r9d, 7FFFFFFEh
0x180015dba  test    r9, r9
0x180015dbd  jz      short loc_180015DDE
0x180015dbf  movzx   r8d, word ptr [rcx]
0x180015dc3  test    r8w, r8w
0x180015dc7  jz      short loc_180015DDE
0x180015dc9  mov     [rax], r8w
0x180015dcd  add     rcx, 2
0x180015dd1  add     rax, 2
0x180015dd5  dec     r9
0x180015dd8  sub     rdx, 1; unsigned __int64
0x180015ddc  jnz     short loc_180015DBA
0x180015dde  test    rdx, rdx
0x180015de1  lea     rcx, [rax-2]
0x180015de5  lea     r8, aP0; "_p0"
0x180015dec  cmovnz  rcx, rax
0x180015df0  mov     [rcx], r15w
0x180015df4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180015df9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015dfe  mov     esi, 1F0003h
0x180015e03  lea     r8, [rsp+280h+Name]; lpName
0x180015e08  mov     ecx, esi; dwDesiredAccess
0x180015e0a  xor     edx, edx; bInheritHandle
0x180015e0c  call    cs:__imp_OpenSemaphoreW
0x180015e12  mov     rbx, rax
0x180015e15  test    rax, rax
0x180015e18  jz      loc_180015F39
0x180015e1e  lea     rdx, [rsp+280h+var_25C]; int *
0x180015e23  mov     [rsp+280h+var_25C], r15d
0x180015e28  mov     rcx, rax; hHandle
0x180015e2b  mov     [rsp+280h+var_260], r15d; int
0x180015e30  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015e35  mov     edi, eax
0x180015e37  test    eax, eax
0x180015e39  jns     short loc_180015E67
0x180015e3b  mov     rcx, [rbp+188h]; this
0x180015e42  mov     r9d, eax; char *
0x180015e45  mov     edx, 0D6h; void *
0x180015e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e4f  mov     rcx, rbx; hObject
0x180015e52  call    cs:__imp_CloseHandle
0x180015e58  test    eax, eax
0x180015e5a  jz      loc_180015FAE
0x180015e60  mov     eax, edi
0x180015e62  jmp     loc_180015F59
0x180015e67  lea     r8, asc_18001E380; "h"
0x180015e6e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180015e73  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015e78  lea     r8, [rsp+280h+Name]; lpName
0x180015e7d  xor     edx, edx; bInheritHandle
0x180015e7f  mov     ecx, esi; dwDesiredAccess
0x180015e81  call    cs:__imp_OpenSemaphoreW
0x180015e87  mov     rdi, rax
0x180015e8a  test    rax, rax
0x180015e8d  jz      loc_180015F14
0x180015e93  lea     rdx, [rsp+280h+var_260]; int *
0x180015e98  mov     rcx, rax; hHandle
0x180015e9b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015ea0  mov     esi, eax
0x180015ea2  test    eax, eax
0x180015ea4  jns     short loc_180015EE0
0x180015ea6  mov     rcx, [rbp+188h]; this
0x180015ead  mov     r9d, eax; char *
0x180015eb0  mov     edx, 0DEh; void *
0x180015eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015eba  mov     rcx, rdi; hObject
0x180015ebd  call    cs:__imp_CloseHandle
0x180015ec3  test    eax, eax
0x180015ec5  jz      loc_180015FC0
0x180015ecb  mov     rcx, rbx; hObject
0x180015ece  call    cs:__imp_CloseHandle
0x180015ed4  test    eax, eax
0x180015ed6  jz      loc_180015FD2
0x180015edc  mov     eax, esi
0x180015ede  jmp     short loc_180015F59
0x180015ee0  mov     rcx, rdi; hObject
0x180015ee3  call    cs:__imp_CloseHandle
0x180015ee9  test    eax, eax
0x180015eeb  jz      loc_180015F78
0x180015ef1  movsxd  rax, [rsp+280h+var_25C]
0x180015ef6  movsxd  rcx, [rsp+280h+var_260]
0x180015efb  shl     rcx, 1Fh
0x180015eff  or      rcx, rax
0x180015f02  mov     [r14], rcx
0x180015f05  mov     rcx, rbx; hObject
0x180015f08  call    cs:__imp_CloseHandle
0x180015f0e  test    eax, eax
0x180015f10  jz      short loc_180015F8A
0x180015f12  jmp     short loc_180015F44
0x180015f14  mov     rcx, [rbp+188h]; this
0x180015f1b  mov     edx, 0DCh; void *
0x180015f20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015f25  mov     rcx, rbx; hObject
0x180015f28  mov     edi, eax
0x180015f2a  call    cs:__imp_CloseHandle
0x180015f30  test    eax, eax
0x180015f32  jz      short loc_180015F9C
0x180015f34  jmp     loc_180015E60
0x180015f39  call    cs:__imp_GetLastError
0x180015f3f  cmp     eax, 2
0x180015f42  jnz     short loc_180015F48
0x180015f44  xor     eax, eax
0x180015f46  jmp     short loc_180015F59
0x180015f48  mov     rcx, [rbp+188h]; this
0x180015f4f  mov     edx, 0D0h; void *
0x180015f54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015f59  mov     rcx, [rbp+180h+var_40]
0x180015f60  xor     rcx, rsp; StackCookie
0x180015f63  call    __security_check_cookie
0x180015f68  add     rsp, 258h
0x180015f6f  pop     r15
0x180015f71  pop     r14
0x180015f73  pop     rdi
0x180015f74  pop     rsi
0x180015f75  pop     rbx
0x180015f76  pop     rbp
0x180015f77  retn
0x180015f78  mov     rcx, [rbp+188h]; this
0x180015f7f  mov     edx, 0A0Bh; void *
0x180015f84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015f8a  mov     rcx, [rbp+188h]; this
0x180015f91  mov     edx, 0A0Bh; void *
0x180015f96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015f9c  mov     rcx, [rbp+188h]; this
0x180015fa3  mov     edx, 0A0Bh; void *
0x180015fa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015fae  mov     rcx, [rbp+188h]; this
0x180015fb5  mov     edx, 0A0Bh; void *
0x180015fba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015fc0  mov     rcx, [rbp+188h]; this
0x180015fc7  mov     edx, 0A0Bh; void *
0x180015fcc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015fd2  mov     rcx, [rbp+188h]; this
0x180015fd9  mov     edx, 0A0Bh; void *
0x180015fde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
