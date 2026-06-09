# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ab1c`
- end: `0x18000ad96`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006238`

## callees

- `0x180004180`
- `0x1800081c4`
- `0x18000a004`
- `0x18000a024`
- `0x18000a9b4`
- `0x18000ab1c`
- `0x18000b1d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000abb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac2c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000abb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acdc`

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
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
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
0x18000ab1c  push    rbp
0x18000ab1e  push    rbx
0x18000ab1f  push    rsi
0x18000ab20  push    rdi
0x18000ab21  push    r14
0x18000ab23  push    r15
0x18000ab25  lea     rbp, [rsp-158h]
0x18000ab2d  sub     rsp, 258h
0x18000ab34  mov     rax, cs:__security_cookie
0x18000ab3b  xor     rax, rsp
0x18000ab3e  mov     [rbp+180h+var_40], rax
0x18000ab45  xor     r15d, r15d
0x18000ab48  lea     rax, [rsp+280h+Name]
0x18000ab4d  mov     [r8], r15
0x18000ab50  mov     r14, r8
0x18000ab53  mov     edx, 104h
0x18000ab58  mov     r9d, 7FFFFFFEh
0x18000ab5e  test    r9, r9
0x18000ab61  jz      short loc_18000AB82
0x18000ab63  movzx   r8d, word ptr [rcx]
0x18000ab67  test    r8w, r8w
0x18000ab6b  jz      short loc_18000AB82
0x18000ab6d  mov     [rax], r8w
0x18000ab71  add     rcx, 2
0x18000ab75  add     rax, 2
0x18000ab79  dec     r9
0x18000ab7c  sub     rdx, 1; unsigned __int64
0x18000ab80  jnz     short loc_18000AB5E
0x18000ab82  test    rdx, rdx
0x18000ab85  lea     rcx, [rax-2]
0x18000ab89  lea     r8, aP0; "_p0"
0x18000ab90  cmovnz  rcx, rax
0x18000ab94  mov     [rcx], r15w
0x18000ab98  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ab9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aba2  mov     esi, 1F0003h
0x18000aba7  lea     r8, [rsp+280h+Name]; lpName
0x18000abac  mov     ecx, esi; dwDesiredAccess
0x18000abae  xor     edx, edx; bInheritHandle
0x18000abb0  call    cs:__imp_OpenSemaphoreW
0x18000abb6  mov     rbx, rax
0x18000abb9  test    rax, rax
0x18000abbc  jz      loc_18000ACEB
0x18000abc2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000abc7  mov     [rsp+280h+var_25C], r15d
0x18000abcc  mov     rcx, rax; hHandle
0x18000abcf  mov     [rsp+280h+var_260], r15d; int
0x18000abd4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000abd9  mov     edi, eax
0x18000abdb  test    eax, eax
0x18000abdd  jns     short loc_18000AC12
0x18000abdf  mov     rcx, [rbp+188h]; this
0x18000abe6  lea     r8, aWil; "wil"
0x18000abed  mov     r9d, eax; char *
0x18000abf0  mov     edx, 0D6h; void *
0x18000abf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abfa  mov     rcx, rbx; hObject
0x18000abfd  call    cs:__imp_CloseHandle
0x18000ac03  test    eax, eax
0x18000ac05  jz      loc_18000AD60
0x18000ac0b  mov     eax, edi
0x18000ac0d  jmp     loc_18000AD0B
0x18000ac12  lea     r8, asc_180051C18; "h"
0x18000ac19  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ac1e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ac23  lea     r8, [rsp+280h+Name]; lpName
0x18000ac28  xor     edx, edx; bInheritHandle
0x18000ac2a  mov     ecx, esi; dwDesiredAccess
0x18000ac2c  call    cs:__imp_OpenSemaphoreW
0x18000ac32  mov     rdi, rax
0x18000ac35  test    rax, rax
0x18000ac38  jz      loc_18000ACC6
0x18000ac3e  lea     rdx, [rsp+280h+var_260]; int *
0x18000ac43  mov     rcx, rax; hHandle
0x18000ac46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ac4b  mov     esi, eax
0x18000ac4d  test    eax, eax
0x18000ac4f  jns     short loc_18000AC92
0x18000ac51  mov     rcx, [rbp+188h]; this
0x18000ac58  lea     r8, aWil; "wil"
0x18000ac5f  mov     r9d, eax; char *
0x18000ac62  mov     edx, 0DEh; void *
0x18000ac67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac6c  mov     rcx, rdi; hObject
0x18000ac6f  call    cs:__imp_CloseHandle
0x18000ac75  test    eax, eax
0x18000ac77  jz      loc_18000AD72
0x18000ac7d  mov     rcx, rbx; hObject
0x18000ac80  call    cs:__imp_CloseHandle
0x18000ac86  test    eax, eax
0x18000ac88  jz      loc_18000AD84
0x18000ac8e  mov     eax, esi
0x18000ac90  jmp     short loc_18000AD0B
0x18000ac92  mov     rcx, rdi; hObject
0x18000ac95  call    cs:__imp_CloseHandle
0x18000ac9b  test    eax, eax
0x18000ac9d  jz      loc_18000AD2A
0x18000aca3  movsxd  rax, [rsp+280h+var_25C]
0x18000aca8  movsxd  rcx, [rsp+280h+var_260]
0x18000acad  shl     rcx, 1Fh
0x18000acb1  or      rcx, rax
0x18000acb4  mov     [r14], rcx
0x18000acb7  mov     rcx, rbx; hObject
0x18000acba  call    cs:__imp_CloseHandle
0x18000acc0  test    eax, eax
0x18000acc2  jz      short loc_18000AD3C
0x18000acc4  jmp     short loc_18000ACF6
0x18000acc6  mov     rcx, [rbp+188h]; this
0x18000accd  mov     edx, 0DCh; void *
0x18000acd2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000acd7  mov     rcx, rbx; hObject
0x18000acda  mov     edi, eax
0x18000acdc  call    cs:__imp_CloseHandle
0x18000ace2  test    eax, eax
0x18000ace4  jz      short loc_18000AD4E
0x18000ace6  jmp     loc_18000AC0B
0x18000aceb  call    cs:__imp_GetLastError
0x18000acf1  cmp     eax, 2
0x18000acf4  jnz     short loc_18000ACFA
0x18000acf6  xor     eax, eax
0x18000acf8  jmp     short loc_18000AD0B
0x18000acfa  mov     rcx, [rbp+188h]; this
0x18000ad01  mov     edx, 0D0h; void *
0x18000ad06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad0b  mov     rcx, [rbp+180h+var_40]
0x18000ad12  xor     rcx, rsp; StackCookie
0x18000ad15  call    __security_check_cookie
0x18000ad1a  add     rsp, 258h
0x18000ad21  pop     r15
0x18000ad23  pop     r14
0x18000ad25  pop     rdi
0x18000ad26  pop     rsi
0x18000ad27  pop     rbx
0x18000ad28  pop     rbp
0x18000ad29  retn
0x18000ad2a  mov     rcx, [rbp+188h]; this
0x18000ad31  mov     edx, 0A0Bh; void *
0x18000ad36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad3c  mov     rcx, [rbp+188h]; this
0x18000ad43  mov     edx, 0A0Bh; void *
0x18000ad48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad4e  mov     rcx, [rbp+188h]; this
0x18000ad55  mov     edx, 0A0Bh; void *
0x18000ad5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad60  mov     rcx, [rbp+188h]; this
0x18000ad67  mov     edx, 0A0Bh; void *
0x18000ad6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad72  mov     rcx, [rbp+188h]; this
0x18000ad79  mov     edx, 0A0Bh; void *
0x18000ad7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad84  mov     rcx, [rbp+188h]; this
0x18000ad8b  mov     edx, 0A0Bh; void *
0x18000ad90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
