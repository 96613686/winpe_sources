# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001978c`
- end: `0x1800199f8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017b0c`

## callees

- `0x180001520`
- `0x180018768`
- `0x180018db4`
- `0x180018dd4`
- `0x1800196b0`
- `0x18001978c`
- `0x180019a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001994d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001994d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001991c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001993e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001991c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001993e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019820`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019895`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019820`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019895`

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
0x18001978c  push    rbp
0x18001978e  push    rbx
0x18001978f  push    rsi
0x180019790  push    rdi
0x180019791  push    r14
0x180019793  push    r15
0x180019795  lea     rbp, [rsp-158h]
0x18001979d  sub     rsp, 258h
0x1800197a4  mov     rax, cs:__security_cookie
0x1800197ab  xor     rax, rsp
0x1800197ae  mov     [rbp+180h+var_40], rax
0x1800197b5  xor     r15d, r15d
0x1800197b8  lea     rax, [rsp+280h+Name]
0x1800197bd  mov     [r8], r15
0x1800197c0  mov     r14, r8
0x1800197c3  mov     edx, 104h
0x1800197c8  mov     r9d, 7FFFFFFEh
0x1800197ce  test    r9, r9
0x1800197d1  jz      short loc_1800197F2
0x1800197d3  movzx   r8d, word ptr [rcx]
0x1800197d7  test    r8w, r8w
0x1800197db  jz      short loc_1800197F2
0x1800197dd  mov     [rax], r8w
0x1800197e1  add     rcx, 2
0x1800197e5  add     rax, 2
0x1800197e9  dec     r9
0x1800197ec  sub     rdx, 1; unsigned __int64
0x1800197f0  jnz     short loc_1800197CE
0x1800197f2  test    rdx, rdx
0x1800197f5  lea     rcx, [rax-2]
0x1800197f9  lea     r8, aP0; "_p0"
0x180019800  cmovnz  rcx, rax
0x180019804  mov     [rcx], r15w
0x180019808  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001980d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019812  mov     esi, 1F0003h
0x180019817  lea     r8, [rsp+280h+Name]; lpName
0x18001981c  mov     ecx, esi; dwDesiredAccess
0x18001981e  xor     edx, edx; bInheritHandle
0x180019820  call    cs:__imp_OpenSemaphoreW
0x180019826  mov     rbx, rax
0x180019829  test    rax, rax
0x18001982c  jz      loc_18001994D
0x180019832  lea     rdx, [rsp+280h+var_25C]; int *
0x180019837  mov     [rsp+280h+var_25C], r15d
0x18001983c  mov     rcx, rax; hHandle
0x18001983f  mov     [rsp+280h+var_260], r15d; int
0x180019844  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019849  mov     edi, eax
0x18001984b  test    eax, eax
0x18001984d  jns     short loc_18001987B
0x18001984f  mov     rcx, [rbp+188h]; this
0x180019856  mov     r9d, eax; char *
0x180019859  mov     edx, 0D6h; void *
0x18001985e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019863  mov     rcx, rbx; hObject
0x180019866  call    cs:__imp_CloseHandle
0x18001986c  test    eax, eax
0x18001986e  jz      loc_1800199C2
0x180019874  mov     eax, edi
0x180019876  jmp     loc_18001996D
0x18001987b  lea     r8, asc_180029D30; "h"
0x180019882  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019887  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001988c  lea     r8, [rsp+280h+Name]; lpName
0x180019891  xor     edx, edx; bInheritHandle
0x180019893  mov     ecx, esi; dwDesiredAccess
0x180019895  call    cs:__imp_OpenSemaphoreW
0x18001989b  mov     rdi, rax
0x18001989e  test    rax, rax
0x1800198a1  jz      loc_180019928
0x1800198a7  lea     rdx, [rsp+280h+var_260]; int *
0x1800198ac  mov     rcx, rax; hHandle
0x1800198af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800198b4  mov     esi, eax
0x1800198b6  test    eax, eax
0x1800198b8  jns     short loc_1800198F4
0x1800198ba  mov     rcx, [rbp+188h]; this
0x1800198c1  mov     r9d, eax; char *
0x1800198c4  mov     edx, 0DEh; void *
0x1800198c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198ce  mov     rcx, rdi; hObject
0x1800198d1  call    cs:__imp_CloseHandle
0x1800198d7  test    eax, eax
0x1800198d9  jz      loc_1800199D4
0x1800198df  mov     rcx, rbx; hObject
0x1800198e2  call    cs:__imp_CloseHandle
0x1800198e8  test    eax, eax
0x1800198ea  jz      loc_1800199E6
0x1800198f0  mov     eax, esi
0x1800198f2  jmp     short loc_18001996D
0x1800198f4  mov     rcx, rdi; hObject
0x1800198f7  call    cs:__imp_CloseHandle
0x1800198fd  test    eax, eax
0x1800198ff  jz      loc_18001998C
0x180019905  movsxd  rax, [rsp+280h+var_25C]
0x18001990a  movsxd  rcx, [rsp+280h+var_260]
0x18001990f  shl     rcx, 1Fh
0x180019913  or      rcx, rax
0x180019916  mov     [r14], rcx
0x180019919  mov     rcx, rbx; hObject
0x18001991c  call    cs:__imp_CloseHandle
0x180019922  test    eax, eax
0x180019924  jz      short loc_18001999E
0x180019926  jmp     short loc_180019958
0x180019928  mov     rcx, [rbp+188h]; this
0x18001992f  mov     edx, 0DCh; void *
0x180019934  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019939  mov     rcx, rbx; hObject
0x18001993c  mov     edi, eax
0x18001993e  call    cs:__imp_CloseHandle
0x180019944  test    eax, eax
0x180019946  jz      short loc_1800199B0
0x180019948  jmp     loc_180019874
0x18001994d  call    cs:__imp_GetLastError
0x180019953  cmp     eax, 2
0x180019956  jnz     short loc_18001995C
0x180019958  xor     eax, eax
0x18001995a  jmp     short loc_18001996D
0x18001995c  mov     rcx, [rbp+188h]; this
0x180019963  mov     edx, 0D0h; void *
0x180019968  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001996d  mov     rcx, [rbp+180h+var_40]
0x180019974  xor     rcx, rsp; StackCookie
0x180019977  call    __security_check_cookie
0x18001997c  add     rsp, 258h
0x180019983  pop     r15
0x180019985  pop     r14
0x180019987  pop     rdi
0x180019988  pop     rsi
0x180019989  pop     rbx
0x18001998a  pop     rbp
0x18001998b  retn
0x18001998c  mov     rcx, [rbp+188h]; this
0x180019993  mov     edx, 0A0Bh; void *
0x180019998  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001999e  mov     rcx, [rbp+188h]; this
0x1800199a5  mov     edx, 0A0Bh; void *
0x1800199aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800199b0  mov     rcx, [rbp+188h]; this
0x1800199b7  mov     edx, 0A0Bh; void *
0x1800199bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800199c2  mov     rcx, [rbp+188h]; this
0x1800199c9  mov     edx, 0A0Bh; void *
0x1800199ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800199d4  mov     rcx, [rbp+188h]; this
0x1800199db  mov     edx, 0A0Bh; void *
0x1800199e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800199e6  mov     rcx, [rbp+188h]; this
0x1800199ed  mov     edx, 0A0Bh; void *
0x1800199f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
