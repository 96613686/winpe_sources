# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000ac6c`
- end: `0x14000aed8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003e78`
- `0x14000421c`

## callees

- `0x1400016a0`
- `0x1400069f4`
- `0x140009884`
- `0x1400098a4`
- `0x14000a750`
- `0x14000ac6c`
- `0x14000b52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ad00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ad75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ad00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ad75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000add7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ae1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000add7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ae1e`

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
0x14000ac6c  push    rbp
0x14000ac6e  push    rbx
0x14000ac6f  push    rsi
0x14000ac70  push    rdi
0x14000ac71  push    r14
0x14000ac73  push    r15
0x14000ac75  lea     rbp, [rsp-158h]
0x14000ac7d  sub     rsp, 258h
0x14000ac84  mov     rax, cs:__security_cookie
0x14000ac8b  xor     rax, rsp
0x14000ac8e  mov     [rbp+180h+var_40], rax
0x14000ac95  xor     r15d, r15d
0x14000ac98  lea     rax, [rsp+280h+Name]
0x14000ac9d  mov     [r8], r15
0x14000aca0  mov     r14, r8
0x14000aca3  mov     edx, 104h
0x14000aca8  mov     r9d, 7FFFFFFEh
0x14000acae  test    r9, r9
0x14000acb1  jz      short loc_14000ACD2
0x14000acb3  movzx   r8d, word ptr [rcx]
0x14000acb7  test    r8w, r8w
0x14000acbb  jz      short loc_14000ACD2
0x14000acbd  mov     [rax], r8w
0x14000acc1  add     rcx, 2
0x14000acc5  add     rax, 2
0x14000acc9  dec     r9
0x14000accc  sub     rdx, 1; unsigned __int64
0x14000acd0  jnz     short loc_14000ACAE
0x14000acd2  test    rdx, rdx
0x14000acd5  lea     rcx, [rax-2]
0x14000acd9  lea     r8, aP0; "_p0"
0x14000ace0  cmovnz  rcx, rax
0x14000ace4  mov     [rcx], r15w
0x14000ace8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000aced  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000acf2  mov     esi, 1F0003h
0x14000acf7  lea     r8, [rsp+280h+Name]; lpName
0x14000acfc  mov     ecx, esi; dwDesiredAccess
0x14000acfe  xor     edx, edx; bInheritHandle
0x14000ad00  call    cs:__imp_OpenSemaphoreW
0x14000ad06  mov     rbx, rax
0x14000ad09  test    rax, rax
0x14000ad0c  jz      loc_14000AE2D
0x14000ad12  lea     rdx, [rsp+280h+var_25C]; int *
0x14000ad17  mov     [rsp+280h+var_25C], r15d
0x14000ad1c  mov     rcx, rax; hHandle
0x14000ad1f  mov     [rsp+280h+var_260], r15d; int
0x14000ad24  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000ad29  mov     edi, eax
0x14000ad2b  test    eax, eax
0x14000ad2d  jns     short loc_14000AD5B
0x14000ad2f  mov     rcx, [rbp+188h]; this
0x14000ad36  mov     r9d, eax; char *
0x14000ad39  mov     edx, 0D6h; void *
0x14000ad3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ad43  mov     rcx, rbx; hObject
0x14000ad46  call    cs:__imp_CloseHandle
0x14000ad4c  test    eax, eax
0x14000ad4e  jz      loc_14000AEA2
0x14000ad54  mov     eax, edi
0x14000ad56  jmp     loc_14000AE4D
0x14000ad5b  lea     r8, asc_140013FE0; "h"
0x14000ad62  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ad67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ad6c  lea     r8, [rsp+280h+Name]; lpName
0x14000ad71  xor     edx, edx; bInheritHandle
0x14000ad73  mov     ecx, esi; dwDesiredAccess
0x14000ad75  call    cs:__imp_OpenSemaphoreW
0x14000ad7b  mov     rdi, rax
0x14000ad7e  test    rax, rax
0x14000ad81  jz      loc_14000AE08
0x14000ad87  lea     rdx, [rsp+280h+var_260]; int *
0x14000ad8c  mov     rcx, rax; hHandle
0x14000ad8f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000ad94  mov     esi, eax
0x14000ad96  test    eax, eax
0x14000ad98  jns     short loc_14000ADD4
0x14000ad9a  mov     rcx, [rbp+188h]; this
0x14000ada1  mov     r9d, eax; char *
0x14000ada4  mov     edx, 0DEh; void *
0x14000ada9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000adae  mov     rcx, rdi; hObject
0x14000adb1  call    cs:__imp_CloseHandle
0x14000adb7  test    eax, eax
0x14000adb9  jz      loc_14000AEB4
0x14000adbf  mov     rcx, rbx; hObject
0x14000adc2  call    cs:__imp_CloseHandle
0x14000adc8  test    eax, eax
0x14000adca  jz      loc_14000AEC6
0x14000add0  mov     eax, esi
0x14000add2  jmp     short loc_14000AE4D
0x14000add4  mov     rcx, rdi; hObject
0x14000add7  call    cs:__imp_CloseHandle
0x14000addd  test    eax, eax
0x14000addf  jz      loc_14000AE6C
0x14000ade5  movsxd  rax, [rsp+280h+var_25C]
0x14000adea  movsxd  rcx, [rsp+280h+var_260]
0x14000adef  shl     rcx, 1Fh
0x14000adf3  or      rcx, rax
0x14000adf6  mov     [r14], rcx
0x14000adf9  mov     rcx, rbx; hObject
0x14000adfc  call    cs:__imp_CloseHandle
0x14000ae02  test    eax, eax
0x14000ae04  jz      short loc_14000AE7E
0x14000ae06  jmp     short loc_14000AE38
0x14000ae08  mov     rcx, [rbp+188h]; this
0x14000ae0f  mov     edx, 0DCh; void *
0x14000ae14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000ae19  mov     rcx, rbx; hObject
0x14000ae1c  mov     edi, eax
0x14000ae1e  call    cs:__imp_CloseHandle
0x14000ae24  test    eax, eax
0x14000ae26  jz      short loc_14000AE90
0x14000ae28  jmp     loc_14000AD54
0x14000ae2d  call    cs:__imp_GetLastError
0x14000ae33  cmp     eax, 2
0x14000ae36  jnz     short loc_14000AE3C
0x14000ae38  xor     eax, eax
0x14000ae3a  jmp     short loc_14000AE4D
0x14000ae3c  mov     rcx, [rbp+188h]; this
0x14000ae43  mov     edx, 0D0h; void *
0x14000ae48  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000ae4d  mov     rcx, [rbp+180h+var_40]
0x14000ae54  xor     rcx, rsp; StackCookie
0x14000ae57  call    __security_check_cookie
0x14000ae5c  add     rsp, 258h
0x14000ae63  pop     r15
0x14000ae65  pop     r14
0x14000ae67  pop     rdi
0x14000ae68  pop     rsi
0x14000ae69  pop     rbx
0x14000ae6a  pop     rbp
0x14000ae6b  retn
0x14000ae6c  mov     rcx, [rbp+188h]; this
0x14000ae73  mov     edx, 0A0Bh; void *
0x14000ae78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae7e  mov     rcx, [rbp+188h]; this
0x14000ae85  mov     edx, 0A0Bh; void *
0x14000ae8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae90  mov     rcx, [rbp+188h]; this
0x14000ae97  mov     edx, 0A0Bh; void *
0x14000ae9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000aea2  mov     rcx, [rbp+188h]; this
0x14000aea9  mov     edx, 0A0Bh; void *
0x14000aeae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000aeb4  mov     rcx, [rbp+188h]; this
0x14000aebb  mov     edx, 0A0Bh; void *
0x14000aec0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000aec6  mov     rcx, [rbp+188h]; this
0x14000aecd  mov     edx, 0A0Bh; void *
0x14000aed2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
