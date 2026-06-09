# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007104`
- end: `0x140007450`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `844`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003c20`

## callees

- `0x140001460`
- `0x140004da8`
- `0x1400063c4`
- `0x1400063f0`
- `0x140006e74`
- `0x140007104`
- `0x1400076ec`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400071f9`
- `KERNEL32!CloseHandle` at `0x14000727f`
- `KERNEL32!CloseHandle` at `0x140007290`
- `KERNEL32!CloseHandle` at `0x1400072a8`
- `KERNEL32!CloseHandle` at `0x1400072cd`
- `KERNEL32!CloseHandle` at `0x14000730d`
- `KERNEL32!CloseHandle` at `0x1400071f9`
- `KERNEL32!CloseHandle` at `0x14000727f`
- `KERNEL32!CloseHandle` at `0x140007290`
- `KERNEL32!CloseHandle` at `0x1400072a8`
- `KERNEL32!CloseHandle` at `0x1400072cd`
- `KERNEL32!CloseHandle` at `0x14000730d`
- `KERNEL32!OpenSemaphoreW` at `0x140007198`
- `KERNEL32!OpenSemaphoreW` at `0x140007228`
- `KERNEL32!OpenSemaphoreW` at `0x140007198`
- `KERNEL32!OpenSemaphoreW` at `0x140007228`
- `KERNEL32!GetLastError` at `0x140007320`
- `KERNEL32!GetLastError` at `0x140007320`

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
  unsigned int v14; // r8d
  HANDLE v16; // rax
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  wil::details *v25; // [rsp+28h] [rbp-D8h]
  wil::details *v26; // [rsp+28h] [rbp-D8h]
  wil::details *v27; // [rsp+28h] [rbp-D8h]
  wil::details *v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+298h] [rbp+198h]

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
      return wil::details::in1diag5::Return_GetLastError(
               retaddr,
               (void *)0xD0,
               (unsigned int)"wil",
               "wil::details_abi::SemaphoreValue::TryGetValueInternal",
               0,
               (const char *)v25);
    return 0;
  }
  v30[0] = 0;
  v29 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v30);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    LODWORD(v25) = ValueFromSemaphore;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetValueInternal",
      "GetValueFromSemaphore(semaphoreLow.get(), &countLow)",
      v25,
      v29);
    if ( !CloseHandle(v10) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v14,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        (const char *)v26);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"wil",
                  "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                  "semaphoreHigh",
                  (const char *)v25);
    if ( !CloseHandle(v10) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v24,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        (const char *)v28);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v29);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v22,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        (const char *)v25);
    *a3 = v30[0] | (unsigned __int64)((__int64)v29 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v23,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        (const char *)v25);
    return 0;
  }
  LODWORD(v25) = v18;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0xDE,
    (unsigned int)"wil",
    "wil::details_abi::SemaphoreValue::TryGetValueInternal",
    "GetValueFromSemaphore(semaphoreHigh.get(), &countHigh)",
    v25,
    v29);
  if ( !CloseHandle(v17) )
    wil::details::in1diag5::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v20,
      "wil::details::CloseHandle",
      "::CloseHandle(handle)",
      (const char *)v27);
  if ( !CloseHandle(v10) )
    wil::details::in1diag5::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v21,
      "wil::details::CloseHandle",
      "::CloseHandle(handle)",
      (const char *)v27);
  return v19;
}

```

## disassembly

```asm
0x140007104  push    rbp
0x140007106  push    rbx
0x140007107  push    rsi
0x140007108  push    rdi
0x140007109  push    r14
0x14000710b  push    r15
0x14000710d  lea     rbp, [rsp-168h]
0x140007115  sub     rsp, 268h
0x14000711c  mov     rax, cs:__security_cookie
0x140007123  xor     rax, rsp
0x140007126  mov     [rbp+190h+var_40], rax
0x14000712d  xor     r15d, r15d
0x140007130  lea     rax, [rsp+290h+Name]
0x140007135  mov     [r8], r15
0x140007138  mov     r14, r8
0x14000713b  mov     edx, 104h
0x140007140  mov     r9d, 7FFFFFFEh
0x140007146  test    r9, r9
0x140007149  jz      short loc_14000716A
0x14000714b  movzx   r8d, word ptr [rcx]
0x14000714f  test    r8w, r8w
0x140007153  jz      short loc_14000716A
0x140007155  mov     [rax], r8w
0x140007159  add     rcx, 2
0x14000715d  add     rax, 2
0x140007161  dec     r9
0x140007164  sub     rdx, 1; unsigned __int64
0x140007168  jnz     short loc_140007146
0x14000716a  test    rdx, rdx
0x14000716d  lea     rcx, [rax-2]
0x140007171  lea     r8, aP0; "_p0"
0x140007178  cmovnz  rcx, rax
0x14000717c  mov     [rcx], r15w
0x140007180  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x140007185  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000718a  mov     esi, 1F0003h
0x14000718f  lea     r8, [rsp+290h+Name]; lpName
0x140007194  mov     ecx, esi; dwDesiredAccess
0x140007196  xor     edx, edx; bInheritHandle
0x140007198  call    cs:__imp_OpenSemaphoreW
0x14000719e  mov     rbx, rax
0x1400071a1  test    rax, rax
0x1400071a4  jz      loc_140007320
0x1400071aa  lea     rdx, [rsp+290h+var_25C]; int *
0x1400071af  mov     [rsp+290h+var_25C], r15d
0x1400071b4  mov     rcx, rax; hHandle
0x1400071b7  mov     [rsp+290h+var_260], r15d; int
0x1400071bc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400071c1  mov     edi, eax
0x1400071c3  test    eax, eax
0x1400071c5  jns     short loc_14000720E
0x1400071c7  mov     rcx, [rbp+198h]; this
0x1400071ce  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x1400071d5  mov     dword ptr [rsp+290h+var_268], eax; char *
0x1400071d9  lea     r8, aWil; "wil"
0x1400071e0  lea     rax, aGetvaluefromse_0; "GetValueFromSemaphore(semaphoreLow.get("...
0x1400071e7  mov     edx, 0D6h; void *
0x1400071ec  mov     [rsp+290h+var_270], rax; char *
0x1400071f1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1400071f6  mov     rcx, rbx; hObject
0x1400071f9  call    cs:__imp_CloseHandle
0x1400071ff  test    eax, eax
0x140007201  jz      loc_1400073E1
0x140007207  mov     eax, edi
0x140007209  jmp     loc_140007353
0x14000720e  lea     r8, asc_14000CD5C; "h"
0x140007215  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x14000721a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000721f  lea     r8, [rsp+290h+Name]; lpName
0x140007224  xor     edx, edx; bInheritHandle
0x140007226  mov     ecx, esi; dwDesiredAccess
0x140007228  call    cs:__imp_OpenSemaphoreW
0x14000722e  mov     rdi, rax
0x140007231  test    rax, rax
0x140007234  jz      loc_1400072DD
0x14000723a  lea     rdx, [rsp+290h+var_260]; int *
0x14000723f  mov     rcx, rax; hHandle
0x140007242  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007247  mov     esi, eax
0x140007249  test    eax, eax
0x14000724b  jns     short loc_1400072A5
0x14000724d  mov     rcx, [rbp+198h]; this
0x140007254  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x14000725b  mov     dword ptr [rsp+290h+var_268], eax; char *
0x14000725f  lea     r8, aWil; "wil"
0x140007266  lea     rax, aGetvaluefromse; "GetValueFromSemaphore(semaphoreHigh.get"...
0x14000726d  mov     edx, 0DEh; void *
0x140007272  mov     [rsp+290h+var_270], rax; char *
0x140007277  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x14000727c  mov     rcx, rdi; hObject
0x14000727f  call    cs:__imp_CloseHandle
0x140007285  test    eax, eax
0x140007287  jz      loc_140007406
0x14000728d  mov     rcx, rbx; hObject
0x140007290  call    cs:__imp_CloseHandle
0x140007296  test    eax, eax
0x140007298  jz      loc_14000742B
0x14000729e  mov     eax, esi
0x1400072a0  jmp     loc_140007353
0x1400072a5  mov     rcx, rdi; hObject
0x1400072a8  call    cs:__imp_CloseHandle
0x1400072ae  test    eax, eax
0x1400072b0  jz      loc_140007372
0x1400072b6  movsxd  rax, [rsp+290h+var_25C]
0x1400072bb  movsxd  rcx, [rsp+290h+var_260]
0x1400072c0  shl     rcx, 1Fh
0x1400072c4  or      rcx, rax
0x1400072c7  mov     [r14], rcx
0x1400072ca  mov     rcx, rbx; hObject
0x1400072cd  call    cs:__imp_CloseHandle
0x1400072d3  test    eax, eax
0x1400072d5  jz      loc_140007397
0x1400072db  jmp     short loc_14000732B
0x1400072dd  mov     rcx, [rbp+198h]; this
0x1400072e4  lea     rax, aSemaphorehigh; "semaphoreHigh"
0x1400072eb  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x1400072f2  mov     [rsp+290h+var_270], rax; char *
0x1400072f7  lea     r8, aWil; "wil"
0x1400072fe  mov     edx, 0DCh; void *
0x140007303  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007308  mov     rcx, rbx; hObject
0x14000730b  mov     edi, eax
0x14000730d  call    cs:__imp_CloseHandle
0x140007313  test    eax, eax
0x140007315  jz      loc_1400073BC
0x14000731b  jmp     loc_140007207
0x140007320  call    cs:__imp_GetLastError
0x140007326  cmp     eax, 2
0x140007329  jnz     short loc_14000732F
0x14000732b  xor     eax, eax
0x14000732d  jmp     short loc_140007353
0x14000732f  mov     rcx, [rbp+198h]; this
0x140007336  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x14000733d  lea     r8, aWil; "wil"
0x140007344  mov     [rsp+290h+var_270], r15; char *
0x140007349  mov     edx, 0D0h; void *
0x14000734e  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007353  mov     rcx, [rbp+190h+var_40]
0x14000735a  xor     rcx, rsp; StackCookie
0x14000735d  call    __security_check_cookie
0x140007362  add     rsp, 268h
0x140007369  pop     r15
0x14000736b  pop     r14
0x14000736d  pop     rdi
0x14000736e  pop     rsi
0x14000736f  pop     rbx
0x140007370  pop     rbp
0x140007371  retn
0x140007372  mov     rcx, [rbp+198h]; this
0x140007379  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140007380  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140007387  mov     [rsp+290h+var_270], rax; char *
0x14000738c  mov     edx, 0A0Bh; void *
0x140007391  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007397  mov     rcx, [rbp+198h]; this
0x14000739e  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x1400073a5  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400073ac  mov     [rsp+290h+var_270], rax; char *
0x1400073b1  mov     edx, 0A0Bh; void *
0x1400073b6  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x1400073bc  mov     rcx, [rbp+198h]; this
0x1400073c3  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x1400073ca  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400073d1  mov     [rsp+290h+var_270], rax; char *
0x1400073d6  mov     edx, 0A0Bh; void *
0x1400073db  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x1400073e1  mov     rcx, [rbp+198h]; this
0x1400073e8  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x1400073ef  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400073f6  mov     [rsp+290h+var_270], rax; char *
0x1400073fb  mov     edx, 0A0Bh; void *
0x140007400  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007406  mov     rcx, [rbp+198h]; this
0x14000740d  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140007414  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14000741b  mov     [rsp+290h+var_270], rax; char *
0x140007420  mov     edx, 0A0Bh; void *
0x140007425  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x14000742b  mov     rcx, [rbp+198h]; this
0x140007432  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140007439  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140007440  mov     [rsp+290h+var_270], rax; char *
0x140007445  mov     edx, 0A0Bh; void *
0x14000744a  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
```
