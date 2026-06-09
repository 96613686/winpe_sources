# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005e2c`
- end: `0x140006098`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003830`

## callees

- `0x140004944`
- `0x140005564`
- `0x140005584`
- `0x140005ca0`
- `0x140005e2c`
- `0x140006484`
- `0x14000a370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005ec0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f35`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005ec0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fde`

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
0x140005e2c  push    rbp
0x140005e2e  push    rbx
0x140005e2f  push    rsi
0x140005e30  push    rdi
0x140005e31  push    r14
0x140005e33  push    r15
0x140005e35  lea     rbp, [rsp-158h]
0x140005e3d  sub     rsp, 258h
0x140005e44  mov     rax, cs:__security_cookie
0x140005e4b  xor     rax, rsp
0x140005e4e  mov     [rbp+180h+var_40], rax
0x140005e55  xor     r15d, r15d
0x140005e58  lea     rax, [rsp+280h+Name]
0x140005e5d  mov     [r8], r15
0x140005e60  mov     r14, r8
0x140005e63  mov     edx, 104h
0x140005e68  mov     r9d, 7FFFFFFEh
0x140005e6e  test    r9, r9
0x140005e71  jz      short loc_140005E92
0x140005e73  movzx   r8d, word ptr [rcx]
0x140005e77  test    r8w, r8w
0x140005e7b  jz      short loc_140005E92
0x140005e7d  mov     [rax], r8w
0x140005e81  add     rcx, 2
0x140005e85  add     rax, 2
0x140005e89  dec     r9
0x140005e8c  sub     rdx, 1; unsigned __int64
0x140005e90  jnz     short loc_140005E6E
0x140005e92  test    rdx, rdx
0x140005e95  lea     rcx, [rax-2]
0x140005e99  lea     r8, aP0; "_p0"
0x140005ea0  cmovnz  rcx, rax
0x140005ea4  mov     [rcx], r15w
0x140005ea8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005ead  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005eb2  mov     esi, 1F0003h
0x140005eb7  lea     r8, [rsp+280h+Name]; lpName
0x140005ebc  mov     ecx, esi; dwDesiredAccess
0x140005ebe  xor     edx, edx; bInheritHandle
0x140005ec0  call    cs:__imp_OpenSemaphoreW
0x140005ec6  mov     rbx, rax
0x140005ec9  test    rax, rax
0x140005ecc  jz      loc_140005FED
0x140005ed2  lea     rdx, [rsp+280h+var_25C]; int *
0x140005ed7  mov     [rsp+280h+var_25C], r15d
0x140005edc  mov     rcx, rax; hHandle
0x140005edf  mov     [rsp+280h+var_260], r15d; int
0x140005ee4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005ee9  mov     edi, eax
0x140005eeb  test    eax, eax
0x140005eed  jns     short loc_140005F1B
0x140005eef  mov     rcx, [rbp+188h]; this
0x140005ef6  mov     r9d, eax; char *
0x140005ef9  mov     edx, 0D6h; void *
0x140005efe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f03  mov     rcx, rbx; hObject
0x140005f06  call    cs:__imp_CloseHandle
0x140005f0c  test    eax, eax
0x140005f0e  jz      loc_140006062
0x140005f14  mov     eax, edi
0x140005f16  jmp     loc_14000600D
0x140005f1b  lea     r8, asc_14000CAD8; "h"
0x140005f22  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005f27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f2c  lea     r8, [rsp+280h+Name]; lpName
0x140005f31  xor     edx, edx; bInheritHandle
0x140005f33  mov     ecx, esi; dwDesiredAccess
0x140005f35  call    cs:__imp_OpenSemaphoreW
0x140005f3b  mov     rdi, rax
0x140005f3e  test    rax, rax
0x140005f41  jz      loc_140005FC8
0x140005f47  lea     rdx, [rsp+280h+var_260]; int *
0x140005f4c  mov     rcx, rax; hHandle
0x140005f4f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005f54  mov     esi, eax
0x140005f56  test    eax, eax
0x140005f58  jns     short loc_140005F94
0x140005f5a  mov     rcx, [rbp+188h]; this
0x140005f61  mov     r9d, eax; char *
0x140005f64  mov     edx, 0DEh; void *
0x140005f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f6e  mov     rcx, rdi; hObject
0x140005f71  call    cs:__imp_CloseHandle
0x140005f77  test    eax, eax
0x140005f79  jz      loc_140006074
0x140005f7f  mov     rcx, rbx; hObject
0x140005f82  call    cs:__imp_CloseHandle
0x140005f88  test    eax, eax
0x140005f8a  jz      loc_140006086
0x140005f90  mov     eax, esi
0x140005f92  jmp     short loc_14000600D
0x140005f94  mov     rcx, rdi; hObject
0x140005f97  call    cs:__imp_CloseHandle
0x140005f9d  test    eax, eax
0x140005f9f  jz      loc_14000602C
0x140005fa5  movsxd  rax, [rsp+280h+var_25C]
0x140005faa  movsxd  rcx, [rsp+280h+var_260]
0x140005faf  shl     rcx, 1Fh
0x140005fb3  or      rcx, rax
0x140005fb6  mov     [r14], rcx
0x140005fb9  mov     rcx, rbx; hObject
0x140005fbc  call    cs:__imp_CloseHandle
0x140005fc2  test    eax, eax
0x140005fc4  jz      short loc_14000603E
0x140005fc6  jmp     short loc_140005FF8
0x140005fc8  mov     rcx, [rbp+188h]; this
0x140005fcf  mov     edx, 0DCh; void *
0x140005fd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005fd9  mov     rcx, rbx; hObject
0x140005fdc  mov     edi, eax
0x140005fde  call    cs:__imp_CloseHandle
0x140005fe4  test    eax, eax
0x140005fe6  jz      short loc_140006050
0x140005fe8  jmp     loc_140005F14
0x140005fed  call    cs:__imp_GetLastError
0x140005ff3  cmp     eax, 2
0x140005ff6  jnz     short loc_140005FFC
0x140005ff8  xor     eax, eax
0x140005ffa  jmp     short loc_14000600D
0x140005ffc  mov     rcx, [rbp+188h]; this
0x140006003  mov     edx, 0D0h; void *
0x140006008  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000600d  mov     rcx, [rbp+180h+var_40]
0x140006014  xor     rcx, rsp; StackCookie
0x140006017  call    __security_check_cookie
0x14000601c  add     rsp, 258h
0x140006023  pop     r15
0x140006025  pop     r14
0x140006027  pop     rdi
0x140006028  pop     rsi
0x140006029  pop     rbx
0x14000602a  pop     rbp
0x14000602b  retn
0x14000602c  mov     rcx, [rbp+188h]; this
0x140006033  mov     edx, 0A0Bh; void *
0x140006038  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000603e  mov     rcx, [rbp+188h]; this
0x140006045  mov     edx, 0A0Bh; void *
0x14000604a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006050  mov     rcx, [rbp+188h]; this
0x140006057  mov     edx, 0A0Bh; void *
0x14000605c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006062  mov     rcx, [rbp+188h]; this
0x140006069  mov     edx, 0A0Bh; void *
0x14000606e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006074  mov     rcx, [rbp+188h]; this
0x14000607b  mov     edx, 0A0Bh; void *
0x140006080  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006086  mov     rcx, [rbp+188h]; this
0x14000608d  mov     edx, 0A0Bh; void *
0x140006092  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
